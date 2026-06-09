# SmartlockerGetSubSessionID

- ea: `0x140001bbc`
- end: `0x140001ca7`
- name: `SmartlockerGetSubSessionID`
- size: `235`
- prototype: `__int64 __fastcall(struct _KPROCESS *, _OWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14001f3c0`

## callees

- `0x140001bbc`
- `0x140030ab0`
- `0x140035c50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001c73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001c73`
- `ntoskrnl!PsGetProcessId` at `0x140001bf3`
- `ntoskrnl!PsGetProcessId` at `0x140001bf3`
- `ntoskrnl!ZwClose` at `0x140001c88`
- `ntoskrnl!ZwClose` at `0x140001c88`

## pseudocode

```c
__int64 __fastcall SmartlockerGetSubSessionID(struct _KPROCESS *a1, _OWORD *a2, _DWORD *a3)
{
  HANDLE ProcessId; // rax
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  HANDLE Handle; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+38h] [rbp-18h] BYREF
  PVOID P[2]; // [rsp+40h] [rbp-10h] BYREF
  int v13; // [rsp+78h] [rbp+28h] BYREF

  Handle = 0;
  v11 = 0;
  v13 = 0;
  P[0] = 0;
  ProcessId = PsGetProcessId(a1);
  AiOpenTokenByProcessId(ProcessId, &Handle);
  v6 = SmartlockerOriginClaimProcessTokenCheck((_DWORD)Handle, 0, 0, (unsigned int)&v13, (__int64)&v11, (__int64)P);
  if ( v6 >= 0 || v6 == -1073741823 && v11 )
  {
    v8 = *(_DWORD *)(v11 + 8);
    *a2 = *(_OWORD *)(v11 + 32);
    v7 = 1;
    if ( (v8 & 0xFFFFFFFA) == 0 && v8 != 5 )
      *a3 = 1;
  }
  else
  {
    v7 = 0;
  }
  if ( P[0] )
    ExFreePoolWithTag(P[0], 0x41746D73u);
  if ( Handle )
    ZwClose(Handle);
  return v7;
}

```

## disassembly

```asm
0x140001bbc  mov     [rsp-8+arg_0], rbx
0x140001bc1  mov     [rsp-8+arg_8], rdi
0x140001bc6  push    rbp
0x140001bc7  mov     rbp, rsp
0x140001bca  sub     rsp, 50h
0x140001bce  mov     rdi, r8
0x140001bd1  mov     [rbp+Handle], 0
0x140001bd9  mov     rbx, rdx
0x140001bdc  mov     [rbp+var_18], 0
0x140001be4  mov     [rbp+arg_18], 0
0x140001beb  mov     [rbp+P], 0
0x140001bf3  call    cs:__imp_PsGetProcessId
0x140001bfa  nop     dword ptr [rax+rax+00h]
0x140001bff  mov     rcx, rax
0x140001c02  lea     rdx, [rbp+Handle]
0x140001c06  call    AiOpenTokenByProcessId
0x140001c0b  mov     rcx, [rbp+Handle]
0x140001c0f  lea     rax, [rbp+P]
0x140001c13  mov     [rsp+50h+var_28], rax
0x140001c18  lea     r9, [rbp+arg_18]
0x140001c1c  lea     rax, [rbp+var_18]
0x140001c20  xor     r8d, r8d
0x140001c23  xor     edx, edx
0x140001c25  mov     [rsp+50h+var_30], rax
0x140001c2a  call    SmartlockerOriginClaimProcessTokenCheck
0x140001c2f  mov     rcx, [rbp+var_18]
0x140001c33  test    eax, eax
0x140001c35  jns     short loc_140001C47
0x140001c37  cmp     eax, 0C0000001h
0x140001c3c  jnz     short loc_140001C43
0x140001c3e  test    rcx, rcx
0x140001c41  jnz     short loc_140001C47
0x140001c43  xor     ebx, ebx
0x140001c45  jmp     short loc_140001C65
0x140001c47  movups  xmm0, xmmword ptr [rcx+20h]
0x140001c4b  mov     eax, [rcx+8]
0x140001c4e  movdqu  xmmword ptr [rbx], xmm0
0x140001c52  mov     ebx, 1
0x140001c57  test    eax, 0FFFFFFFAh
0x140001c5c  jnz     short loc_140001C65
0x140001c5e  cmp     eax, 5
0x140001c61  jz      short loc_140001C65
0x140001c63  mov     [rdi], ebx
0x140001c65  mov     rcx, [rbp+P]; P
0x140001c69  test    rcx, rcx
0x140001c6c  jz      short loc_140001C7F
0x140001c6e  mov     edx, 41746D73h; Tag
0x140001c73  call    cs:__imp_ExFreePoolWithTag
0x140001c7a  nop     dword ptr [rax+rax+00h]
0x140001c7f  mov     rcx, [rbp+Handle]; Handle
0x140001c83  test    rcx, rcx
0x140001c86  jz      short loc_140001C94
0x140001c88  call    cs:__imp_ZwClose
0x140001c8f  nop     dword ptr [rax+rax+00h]
0x140001c94  mov     rdi, [rsp+50h+arg_8]
0x140001c99  mov     eax, ebx
0x140001c9b  mov     rbx, [rsp+50h+arg_0]
0x140001ca0  add     rsp, 50h
0x140001ca4  pop     rbp
0x140001ca5  retn
```
