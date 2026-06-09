# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x18002bf3c`
- end: `0x18002c11b`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002c124`

## callees

- `0x18001b8ac`
- `0x18002bf3c`
- `0x18002c40c`
- `0x18002c66c`
- `0x18002c91c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18002c00d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002c04f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002c0e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002c00d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002c04f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002c0e3`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x18002bfe4`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x18002bfe4`

## string_xrefs

- `0x18002bf7e`: `Security`

## pseudocode

```c
__int64 __fastcall PiRegStateReadStackCreationSettingsFromKey(HANDLE KeyHandle, __int64 a2)
{
  _DWORD *v2; // r13
  _DWORD *v3; // r15
  _DWORD *v4; // r12
  PVOID v7; // rsi
  NTSTATUS inited; // ebx
  __int64 v9; // r8
  void *v10; // r10
  int FullBuffer; // eax
  __int64 v12; // r9
  PVOID v13; // rax
  int Dword; // eax
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // r8
  int v18; // eax
  void *v19; // rcx
  PVOID P; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 v23; // [rsp+98h] [rbp+48h] BYREF
  int v24; // [rsp+A0h] [rbp+50h] BYREF
  PVOID SecurityDescriptor; // [rsp+A8h] [rbp+58h] BYREF

  v2 = (_DWORD *)(a2 + 4);
  v3 = (_DWORD *)(a2 + 16);
  *(_DWORD *)a2 = 0;
  v4 = (_DWORD *)(a2 + 20);
  *(_QWORD *)(a2 + 8) = 0;
  SecurityDescriptor = 0;
  v24 = 0;
  v23 = 0;
  P = 0;
  *(_DWORD *)(a2 + 4) = 0;
  v7 = 0;
  *(_DWORD *)(a2 + 16) = 0;
  *(_DWORD *)(a2 + 20) = 0;
  DestinationString = 0;
  inited = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"Security");
  if ( inited < 0
    || (FullBuffer = CmRegUtilUcValueGetFullBuffer(KeyHandle, &DestinationString, (__int64)&P),
        v7 = P,
        v10 = 0,
        inited = FullBuffer,
        FullBuffer < 0) )
  {
    if ( inited == -1073741772 )
    {
      SecurityDescriptor = v10;
      inited = (int)v10;
    }
  }
  else
  {
    LOBYTE(v12) = 1;
    inited = SeCaptureSecurityDescriptor((char *)P + *((unsigned int *)P + 2), 0, 1, v12, &SecurityDescriptor);
  }
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( inited < 0 )
    goto LABEL_24;
  if ( SecurityDescriptor )
  {
    inited = SeUtilSecurityInfoFromSecurityDescriptor(SecurityDescriptor, &v23, &v24);
    if ( inited < 0 )
      goto LABEL_24;
    if ( v23 )
    {
      ExFreePoolWithTag(SecurityDescriptor, 0);
    }
    else
    {
      v13 = SecurityDescriptor;
      *(_DWORD *)a2 |= 2u;
      *(_QWORD *)(a2 + 8) = v13;
    }
  }
  Dword = CmRegUtilWstrValueGetDword(KeyHandle, L"DeviceType", v9, v2);
  inited = Dword;
  if ( Dword < 0 )
  {
    if ( Dword != -1073741772 )
      goto LABEL_24;
  }
  else
  {
    *(_DWORD *)a2 |= 1u;
  }
  v16 = CmRegUtilWstrValueGetDword(KeyHandle, L"DeviceCharacteristics", v15, v3);
  inited = v16;
  if ( v16 < 0 )
  {
    if ( v16 != -1073741772 )
      goto LABEL_24;
  }
  else
  {
    *(_DWORD *)a2 |= 4u;
  }
  v18 = CmRegUtilWstrValueGetDword(KeyHandle, L"Exclusive", v17, v4);
  inited = v18;
  if ( v18 >= 0 )
  {
    *(_DWORD *)a2 |= 8u;
    return (unsigned int)inited;
  }
  if ( v18 == -1073741772 )
    return 0;
LABEL_24:
  v19 = *(void **)(a2 + 8);
  if ( v19 )
    ExFreePoolWithTag(v19, 0);
  *(_DWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *v2 = 0;
  *v3 = 0;
  *v4 = 0;
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18002bf3c  mov     [rsp-38h+arg_0], rbx
0x18002bf41  push    rbp
0x18002bf42  push    rsi
0x18002bf43  push    rdi
0x18002bf44  push    r12
0x18002bf46  push    r13
0x18002bf48  push    r14
0x18002bf4a  push    r15
0x18002bf4c  mov     rbp, rsp
0x18002bf4f  sub     rsp, 50h
0x18002bf53  xor     r10d, r10d
0x18002bf56  lea     r13, [rdx+4]
0x18002bf5a  lea     r15, [rdx+10h]
0x18002bf5e  mov     [rdx], r10d
0x18002bf61  lea     r12, [rdx+14h]
0x18002bf65  mov     [rdx+8], r10
0x18002bf69  mov     rdi, rdx
0x18002bf6c  mov     [rbp+SecurityDescriptor], r10
0x18002bf70  mov     r14, rcx
0x18002bf73  mov     [rbp+arg_10], r10d
0x18002bf77  xorps   xmm0, xmm0
0x18002bf7a  mov     [rbp+arg_8], r10b
0x18002bf7e  lea     rdx, aSecurity; "Security"
0x18002bf85  mov     [rbp+P], r10
0x18002bf89  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002bf8d  mov     [r13+0], r10d
0x18002bf91  mov     esi, r10d
0x18002bf94  mov     [r15], r10d
0x18002bf97  mov     [r12], r10d
0x18002bf9b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002bf9f  call    WdmlibRtlInitUnicodeStringEx
0x18002bfa4  mov     ebx, eax
0x18002bfa6  test    eax, eax
0x18002bfa8  js      short loc_18002BFF4
0x18002bfaa  lea     rax, [rbp+P]
0x18002bfae  mov     rcx, r14; KeyHandle
0x18002bfb1  lea     rdx, [rbp+DestinationString]; ValueName
0x18002bfb5  mov     [rsp+50h+var_30], rax; __int64
0x18002bfba  call    CmRegUtilUcValueGetFullBuffer
0x18002bfbf  mov     rsi, [rbp+P]
0x18002bfc3  xor     r10d, r10d
0x18002bfc6  mov     ebx, eax
0x18002bfc8  test    eax, eax
0x18002bfca  js      short loc_18002BFF4
0x18002bfcc  mov     ecx, [rsi+8]
0x18002bfcf  lea     rax, [rbp+SecurityDescriptor]
0x18002bfd3  add     rcx, rsi
0x18002bfd6  mov     [rsp+50h+var_30], rax
0x18002bfdb  mov     r9b, 1
0x18002bfde  lea     r8d, [r10+1]
0x18002bfe2  xor     edx, edx
0x18002bfe4  call    cs:__imp_SeCaptureSecurityDescriptor
0x18002bfeb  nop     dword ptr [rax+rax+00h]
0x18002bff0  mov     ebx, eax
0x18002bff2  jmp     short loc_18002C003
0x18002bff4  cmp     ebx, 0C0000034h
0x18002bffa  jnz     short loc_18002C003
0x18002bffc  mov     [rbp+SecurityDescriptor], r10
0x18002c000  mov     ebx, r10d
0x18002c003  test    rsi, rsi
0x18002c006  jz      short loc_18002C019
0x18002c008  xor     edx, edx; Tag
0x18002c00a  mov     rcx, rsi; P
0x18002c00d  call    cs:__imp_ExFreePoolWithTag
0x18002c014  nop     dword ptr [rax+rax+00h]
0x18002c019  xor     esi, esi
0x18002c01b  test    ebx, ebx
0x18002c01d  js      loc_18002C0D8
0x18002c023  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18002c027  test    rcx, rcx
0x18002c02a  jz      short loc_18002C068
0x18002c02c  lea     r8, [rbp+arg_10]
0x18002c030  lea     rdx, [rbp+arg_8]
0x18002c034  call    SeUtilSecurityInfoFromSecurityDescriptor
0x18002c039  mov     ebx, eax
0x18002c03b  test    eax, eax
0x18002c03d  js      loc_18002C0D8
0x18002c043  cmp     [rbp+arg_8], sil
0x18002c047  jz      short loc_18002C05D
0x18002c049  mov     rcx, [rbp+SecurityDescriptor]; P
0x18002c04d  xor     edx, edx; Tag
0x18002c04f  call    cs:__imp_ExFreePoolWithTag
0x18002c056  nop     dword ptr [rax+rax+00h]
0x18002c05b  jmp     short loc_18002C068
0x18002c05d  mov     rax, [rbp+SecurityDescriptor]
0x18002c061  or      dword ptr [rdi], 2
0x18002c064  mov     [rdi+8], rax
0x18002c068  mov     r9, r13
0x18002c06b  lea     rdx, aDevicetype; "DeviceType"
0x18002c072  mov     rcx, r14
0x18002c075  call    CmRegUtilWstrValueGetDword
0x18002c07a  mov     ebx, eax
0x18002c07c  test    eax, eax
0x18002c07e  js      short loc_18002C085
0x18002c080  or      dword ptr [rdi], 1
0x18002c083  jmp     short loc_18002C08C
0x18002c085  cmp     eax, 0C0000034h
0x18002c08a  jnz     short loc_18002C0D8
0x18002c08c  mov     r9, r15
0x18002c08f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x18002c096  mov     rcx, r14
0x18002c099  call    CmRegUtilWstrValueGetDword
0x18002c09e  mov     ebx, eax
0x18002c0a0  test    eax, eax
0x18002c0a2  js      short loc_18002C0A9
0x18002c0a4  or      dword ptr [rdi], 4
0x18002c0a7  jmp     short loc_18002C0B0
0x18002c0a9  cmp     eax, 0C0000034h
0x18002c0ae  jnz     short loc_18002C0D8
0x18002c0b0  mov     r9, r12
0x18002c0b3  lea     rdx, aExclusive; "Exclusive"
0x18002c0ba  mov     rcx, r14
0x18002c0bd  call    CmRegUtilWstrValueGetDword
0x18002c0c2  mov     ebx, eax
0x18002c0c4  test    eax, eax
0x18002c0c6  js      short loc_18002C0CD
0x18002c0c8  or      dword ptr [rdi], 8
0x18002c0cb  jmp     short loc_18002C100
0x18002c0cd  cmp     eax, 0C0000034h
0x18002c0d2  jnz     short loc_18002C0D8
0x18002c0d4  mov     ebx, esi
0x18002c0d6  jmp     short loc_18002C100
0x18002c0d8  mov     rcx, [rdi+8]; P
0x18002c0dc  test    rcx, rcx
0x18002c0df  jz      short loc_18002C0EF
0x18002c0e1  xor     edx, edx; Tag
0x18002c0e3  call    cs:__imp_ExFreePoolWithTag
0x18002c0ea  nop     dword ptr [rax+rax+00h]
0x18002c0ef  mov     [rdi], esi
0x18002c0f1  mov     [rdi+8], rsi
0x18002c0f5  mov     [r13+0], esi
0x18002c0f9  mov     [r15], esi
0x18002c0fc  mov     [r12], esi
0x18002c100  mov     eax, ebx
0x18002c102  mov     rbx, [rsp+50h+arg_0]
0x18002c10a  add     rsp, 50h
0x18002c10e  pop     r15
0x18002c110  pop     r14
0x18002c112  pop     r13
0x18002c114  pop     r12
0x18002c116  pop     rdi
0x18002c117  pop     rsi
0x18002c118  pop     rbp
0x18002c119  retn
```
