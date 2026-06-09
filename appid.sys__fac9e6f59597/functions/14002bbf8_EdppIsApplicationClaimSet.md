# EdppIsApplicationClaimSet

- ea: `0x14002bbf8`
- end: `0x14002bd33`
- name: `EdppIsApplicationClaimSet`
- size: `315`
- prototype: `__int64 __fastcall(__int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003ec0`

## callees

- `0x14002bbf8`
- `0x14002f434`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14002bc85`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14002bc85`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14002bc4d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14002bc4d`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14002bd17`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14002bd17`
- `ntoskrnl!ZwQueryInformationToken` at `0x14002bcb4`
- `ntoskrnl!ZwQueryInformationToken` at `0x14002bcb4`
- `ntoskrnl!RtlCapabilityCheck` at `0x14002bcd6`
- `ntoskrnl!RtlCapabilityCheck` at `0x14002bcd6`
- `ntoskrnl!ZwClose` at `0x14002bd03`
- `ntoskrnl!ZwClose` at `0x14002bd03`

## pseudocode

```c
__int64 __fastcall EdppIsApplicationClaimSet(__int64 a1, __int64 a2, _BYTE *a3)
{
  PACCESS_TOKEN v3; // rbp
  _BYTE *v4; // rdi
  _QWORD *v6; // rcx
  __int64 v7; // rax
  NTSTATUS IsApplicationEDPResourceSetKernel; // esi
  __int64 v9; // rdx
  int TokenInformation; // [rsp+60h] [rbp+8h] BYREF
  ULONG ReturnLength; // [rsp+70h] [rbp+18h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  v4 = a3;
  Handle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  *a3 = 0;
  if ( (_DWORD)a1 == 1 )
    goto LABEL_10;
  v6 = *(_QWORD **)(a2 + 72);
  v7 = *v6 - 0x4896EF1A58125A50LL;
  if ( *v6 == 0x4896EF1A58125A50LL )
    v7 = v6[1] - 0x6CCAB39AC6D657BALL;
  if ( v7 )
  {
    a1 = 0;
LABEL_10:
    v9 = *(_QWORD *)(a2 + 32);
    goto LABEL_11;
  }
  v3 = PsReferencePrimaryToken(*(PEPROCESS *)(a2 + 8));
  IsApplicationEDPResourceSetKernel = ObOpenObjectByPointer(v3, 0x200u, 0, 8u, 0, 0, &Handle);
  if ( IsApplicationEDPResourceSetKernel < 0 )
    goto LABEL_12;
  ZwQueryInformationToken(*(HANDLE *)(a2 + 48), TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
  a3 = v4;
  if ( TokenInformation )
  {
    RtlCapabilityCheck(Handle, L"(*", v4);
    goto LABEL_12;
  }
  v9 = *(_QWORD *)(a2 + 32);
  a1 = 0;
LABEL_11:
  IsApplicationEDPResourceSetKernel = SrppIsApplicationEDPResourceSetKernel(a1, v9, a3);
LABEL_12:
  if ( Handle )
    ZwClose(Handle);
  if ( v3 )
    PsDereferencePrimaryToken(v3);
  return (unsigned int)IsApplicationEDPResourceSetKernel;
}

```

## disassembly

```asm
0x14002bbf8  mov     rax, rsp
0x14002bbfb  mov     [rax+10h], rbx
0x14002bbff  push    rbp
0x14002bc00  push    rsi
0x14002bc01  push    rdi
0x14002bc02  sub     rsp, 40h
0x14002bc06  xor     ebp, ebp
0x14002bc08  mov     rdi, r8
0x14002bc0b  mov     [rax+20h], rbp
0x14002bc0f  mov     rbx, rdx
0x14002bc12  mov     [rax+8], ebp
0x14002bc15  mov     [rax+18h], ebp
0x14002bc18  mov     [r8], bpl
0x14002bc1b  cmp     ecx, 1
0x14002bc1e  jnz     short loc_14002BC25
0x14002bc20  jmp     loc_14002BCEE
0x14002bc25  mov     rcx, [rdx+48h]
0x14002bc29  mov     rax, [rcx]
0x14002bc2c  sub     rax, cs:qword_14000DB20
0x14002bc33  jnz     short loc_14002BC40
0x14002bc35  mov     rax, [rcx+8]
0x14002bc39  sub     rax, cs:qword_14000DB28
0x14002bc40  test    rax, rax
0x14002bc43  jnz     loc_14002BCEC
0x14002bc49  mov     rcx, [rdx+8]; Process
0x14002bc4d  call    cs:__imp_PsReferencePrimaryToken
0x14002bc54  nop     dword ptr [rax+rax+00h]
0x14002bc59  mov     r9d, 8; DesiredAccess
0x14002bc5f  xor     r8d, r8d; PassedAccessState
0x14002bc62  mov     rbp, rax
0x14002bc65  mov     edx, 200h; HandleAttributes
0x14002bc6a  lea     rax, [rsp+58h+arg_18]
0x14002bc6f  mov     rcx, rbp; Object
0x14002bc72  mov     [rsp+58h+Handle], rax; Handle
0x14002bc77  mov     [rsp+58h+AccessMode], 0; AccessMode
0x14002bc7c  mov     [rsp+58h+ObjectType], 0; ObjectType
0x14002bc85  call    cs:__imp_ObOpenObjectByPointer
0x14002bc8c  nop     dword ptr [rax+rax+00h]
0x14002bc91  mov     esi, eax
0x14002bc93  test    eax, eax
0x14002bc95  js      short loc_14002BCF9
0x14002bc97  mov     rcx, [rbx+30h]; TokenHandle
0x14002bc9b  lea     rax, [rsp+58h+ReturnLength]
0x14002bca0  mov     r9d, 4; TokenInformationLength
0x14002bca6  mov     [rsp+58h+ObjectType], rax; ReturnLength
0x14002bcab  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x14002bcb0  lea     edx, [r9+19h]; TokenInformationClass
0x14002bcb4  call    cs:__imp_ZwQueryInformationToken
0x14002bcbb  nop     dword ptr [rax+rax+00h]
0x14002bcc0  cmp     [rsp+58h+TokenInformation], 0
0x14002bcc5  mov     r8, rdi
0x14002bcc8  jz      short loc_14002BCE4
0x14002bcca  mov     rcx, [rsp+58h+arg_18]
0x14002bccf  lea     rdx, enterpriseDataPolicyCapability; "(*"
0x14002bcd6  call    cs:__imp_RtlCapabilityCheck
0x14002bcdd  nop     dword ptr [rax+rax+00h]
0x14002bce2  jmp     short loc_14002BCF9
0x14002bce4  mov     rdx, [rbx+20h]
0x14002bce8  xor     ecx, ecx
0x14002bcea  jmp     short loc_14002BCF2
0x14002bcec  xor     ecx, ecx
0x14002bcee  mov     rdx, [rdx+20h]
0x14002bcf2  call    SrppIsApplicationEDPResourceSetKernel
0x14002bcf7  mov     esi, eax
0x14002bcf9  mov     rcx, [rsp+58h+arg_18]; Handle
0x14002bcfe  test    rcx, rcx
0x14002bd01  jz      short loc_14002BD0F
0x14002bd03  call    cs:__imp_ZwClose
0x14002bd0a  nop     dword ptr [rax+rax+00h]
0x14002bd0f  test    rbp, rbp
0x14002bd12  jz      short loc_14002BD23
0x14002bd14  mov     rcx, rbp; PrimaryToken
0x14002bd17  call    cs:__imp_PsDereferencePrimaryToken
0x14002bd1e  nop     dword ptr [rax+rax+00h]
0x14002bd23  mov     rbx, [rsp+58h+arg_8]
0x14002bd28  mov     eax, esi
0x14002bd2a  add     rsp, 40h
0x14002bd2e  pop     rdi
0x14002bd2f  pop     rsi
0x14002bd30  pop     rbp
0x14002bd31  retn
```
