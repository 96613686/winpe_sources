# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x14000e03c`
- end: `0x14000e21b`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000e224`

## callees

- `0x1400022c0`
- `0x14000e03c`
- `0x14000e50c`
- `0x14000e7a4`
- `0x14000ea54`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e10d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e14f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e1e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e10d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e14f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e1e3`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000e0e4`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000e0e4`

## string_xrefs

- `0x14000e07e`: `Security`

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
0x14000e03c  mov     [rsp-38h+arg_0], rbx
0x14000e041  push    rbp
0x14000e042  push    rsi
0x14000e043  push    rdi
0x14000e044  push    r12
0x14000e046  push    r13
0x14000e048  push    r14
0x14000e04a  push    r15
0x14000e04c  mov     rbp, rsp
0x14000e04f  sub     rsp, 50h
0x14000e053  xor     r10d, r10d
0x14000e056  lea     r13, [rdx+4]
0x14000e05a  lea     r15, [rdx+10h]
0x14000e05e  mov     [rdx], r10d
0x14000e061  lea     r12, [rdx+14h]
0x14000e065  mov     [rdx+8], r10
0x14000e069  mov     rdi, rdx
0x14000e06c  mov     [rbp+SecurityDescriptor], r10
0x14000e070  mov     r14, rcx
0x14000e073  mov     [rbp+arg_10], r10d
0x14000e077  xorps   xmm0, xmm0
0x14000e07a  mov     [rbp+arg_8], r10b
0x14000e07e  lea     rdx, aSecurity; "Security"
0x14000e085  mov     [rbp+P], r10
0x14000e089  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000e08d  mov     [r13+0], r10d
0x14000e091  mov     esi, r10d
0x14000e094  mov     [r15], r10d
0x14000e097  mov     [r12], r10d
0x14000e09b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000e09f  call    WdmlibRtlInitUnicodeStringEx
0x14000e0a4  mov     ebx, eax
0x14000e0a6  test    eax, eax
0x14000e0a8  js      short loc_14000E0F4
0x14000e0aa  lea     rax, [rbp+P]
0x14000e0ae  mov     rcx, r14; KeyHandle
0x14000e0b1  lea     rdx, [rbp+DestinationString]; ValueName
0x14000e0b5  mov     [rsp+50h+var_30], rax; __int64
0x14000e0ba  call    CmRegUtilUcValueGetFullBuffer
0x14000e0bf  mov     rsi, [rbp+P]
0x14000e0c3  xor     r10d, r10d
0x14000e0c6  mov     ebx, eax
0x14000e0c8  test    eax, eax
0x14000e0ca  js      short loc_14000E0F4
0x14000e0cc  mov     ecx, [rsi+8]
0x14000e0cf  lea     rax, [rbp+SecurityDescriptor]
0x14000e0d3  add     rcx, rsi
0x14000e0d6  mov     [rsp+50h+var_30], rax
0x14000e0db  mov     r9b, 1
0x14000e0de  lea     r8d, [r10+1]
0x14000e0e2  xor     edx, edx
0x14000e0e4  call    cs:__imp_SeCaptureSecurityDescriptor
0x14000e0eb  nop     dword ptr [rax+rax+00h]
0x14000e0f0  mov     ebx, eax
0x14000e0f2  jmp     short loc_14000E103
0x14000e0f4  cmp     ebx, 0C0000034h
0x14000e0fa  jnz     short loc_14000E103
0x14000e0fc  mov     [rbp+SecurityDescriptor], r10
0x14000e100  mov     ebx, r10d
0x14000e103  test    rsi, rsi
0x14000e106  jz      short loc_14000E119
0x14000e108  xor     edx, edx; Tag
0x14000e10a  mov     rcx, rsi; P
0x14000e10d  call    cs:__imp_ExFreePoolWithTag
0x14000e114  nop     dword ptr [rax+rax+00h]
0x14000e119  xor     esi, esi
0x14000e11b  test    ebx, ebx
0x14000e11d  js      loc_14000E1D8
0x14000e123  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000e127  test    rcx, rcx
0x14000e12a  jz      short loc_14000E168
0x14000e12c  lea     r8, [rbp+arg_10]
0x14000e130  lea     rdx, [rbp+arg_8]
0x14000e134  call    SeUtilSecurityInfoFromSecurityDescriptor
0x14000e139  mov     ebx, eax
0x14000e13b  test    eax, eax
0x14000e13d  js      loc_14000E1D8
0x14000e143  cmp     [rbp+arg_8], sil
0x14000e147  jz      short loc_14000E15D
0x14000e149  mov     rcx, [rbp+SecurityDescriptor]; P
0x14000e14d  xor     edx, edx; Tag
0x14000e14f  call    cs:__imp_ExFreePoolWithTag
0x14000e156  nop     dword ptr [rax+rax+00h]
0x14000e15b  jmp     short loc_14000E168
0x14000e15d  mov     rax, [rbp+SecurityDescriptor]
0x14000e161  or      dword ptr [rdi], 2
0x14000e164  mov     [rdi+8], rax
0x14000e168  mov     r9, r13
0x14000e16b  lea     rdx, aDevicetype; "DeviceType"
0x14000e172  mov     rcx, r14
0x14000e175  call    CmRegUtilWstrValueGetDword
0x14000e17a  mov     ebx, eax
0x14000e17c  test    eax, eax
0x14000e17e  js      short loc_14000E185
0x14000e180  or      dword ptr [rdi], 1
0x14000e183  jmp     short loc_14000E18C
0x14000e185  cmp     eax, 0C0000034h
0x14000e18a  jnz     short loc_14000E1D8
0x14000e18c  mov     r9, r15
0x14000e18f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x14000e196  mov     rcx, r14
0x14000e199  call    CmRegUtilWstrValueGetDword
0x14000e19e  mov     ebx, eax
0x14000e1a0  test    eax, eax
0x14000e1a2  js      short loc_14000E1A9
0x14000e1a4  or      dword ptr [rdi], 4
0x14000e1a7  jmp     short loc_14000E1B0
0x14000e1a9  cmp     eax, 0C0000034h
0x14000e1ae  jnz     short loc_14000E1D8
0x14000e1b0  mov     r9, r12
0x14000e1b3  lea     rdx, aExclusive; "Exclusive"
0x14000e1ba  mov     rcx, r14
0x14000e1bd  call    CmRegUtilWstrValueGetDword
0x14000e1c2  mov     ebx, eax
0x14000e1c4  test    eax, eax
0x14000e1c6  js      short loc_14000E1CD
0x14000e1c8  or      dword ptr [rdi], 8
0x14000e1cb  jmp     short loc_14000E200
0x14000e1cd  cmp     eax, 0C0000034h
0x14000e1d2  jnz     short loc_14000E1D8
0x14000e1d4  mov     ebx, esi
0x14000e1d6  jmp     short loc_14000E200
0x14000e1d8  mov     rcx, [rdi+8]; P
0x14000e1dc  test    rcx, rcx
0x14000e1df  jz      short loc_14000E1EF
0x14000e1e1  xor     edx, edx; Tag
0x14000e1e3  call    cs:__imp_ExFreePoolWithTag
0x14000e1ea  nop     dword ptr [rax+rax+00h]
0x14000e1ef  mov     [rdi], esi
0x14000e1f1  mov     [rdi+8], rsi
0x14000e1f5  mov     [r13+0], esi
0x14000e1f9  mov     [r15], esi
0x14000e1fc  mov     [r12], esi
0x14000e200  mov     eax, ebx
0x14000e202  mov     rbx, [rsp+50h+arg_0]
0x14000e20a  add     rsp, 50h
0x14000e20e  pop     r15
0x14000e210  pop     r14
0x14000e212  pop     r13
0x14000e214  pop     r12
0x14000e216  pop     rdi
0x14000e217  pop     rsi
0x14000e218  pop     rbp
0x14000e219  retn
```
