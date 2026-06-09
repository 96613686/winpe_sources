# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x140037d04`
- end: `0x140037ee3`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140037eec`

## callees

- `0x140007854`
- `0x140037d04`
- `0x140038194`
- `0x1400384dc`
- `0x14003874c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140037dd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037e17`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037eab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037dd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037e17`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037eab`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140037dac`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140037dac`

## string_xrefs

- `0x140037d46`: `Security`

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
0x140037d04  mov     [rsp-38h+arg_0], rbx
0x140037d09  push    rbp
0x140037d0a  push    rsi
0x140037d0b  push    rdi
0x140037d0c  push    r12
0x140037d0e  push    r13
0x140037d10  push    r14
0x140037d12  push    r15
0x140037d14  mov     rbp, rsp
0x140037d17  sub     rsp, 50h
0x140037d1b  xor     r10d, r10d
0x140037d1e  lea     r13, [rdx+4]
0x140037d22  lea     r15, [rdx+10h]
0x140037d26  mov     [rdx], r10d
0x140037d29  lea     r12, [rdx+14h]
0x140037d2d  mov     [rdx+8], r10
0x140037d31  mov     rdi, rdx
0x140037d34  mov     [rbp+SecurityDescriptor], r10
0x140037d38  mov     r14, rcx
0x140037d3b  mov     [rbp+arg_10], r10d
0x140037d3f  xorps   xmm0, xmm0
0x140037d42  mov     [rbp+arg_8], r10b
0x140037d46  lea     rdx, aSecurity; "Security"
0x140037d4d  mov     [rbp+P], r10
0x140037d51  lea     rcx, [rbp+DestinationString]; DestinationString
0x140037d55  mov     [r13+0], r10d
0x140037d59  mov     esi, r10d
0x140037d5c  mov     [r15], r10d
0x140037d5f  mov     [r12], r10d
0x140037d63  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140037d67  call    WdmlibRtlInitUnicodeStringEx
0x140037d6c  mov     ebx, eax
0x140037d6e  test    eax, eax
0x140037d70  js      short loc_140037DBC
0x140037d72  lea     rax, [rbp+P]
0x140037d76  mov     rcx, r14; KeyHandle
0x140037d79  lea     rdx, [rbp+DestinationString]; ValueName
0x140037d7d  mov     [rsp+50h+var_30], rax; __int64
0x140037d82  call    CmRegUtilUcValueGetFullBuffer
0x140037d87  mov     rsi, [rbp+P]
0x140037d8b  xor     r10d, r10d
0x140037d8e  mov     ebx, eax
0x140037d90  test    eax, eax
0x140037d92  js      short loc_140037DBC
0x140037d94  mov     ecx, [rsi+8]
0x140037d97  lea     rax, [rbp+SecurityDescriptor]
0x140037d9b  add     rcx, rsi
0x140037d9e  mov     [rsp+50h+var_30], rax
0x140037da3  mov     r9b, 1
0x140037da6  lea     r8d, [r10+1]
0x140037daa  xor     edx, edx
0x140037dac  call    cs:__imp_SeCaptureSecurityDescriptor
0x140037db3  nop     dword ptr [rax+rax+00h]
0x140037db8  mov     ebx, eax
0x140037dba  jmp     short loc_140037DCB
0x140037dbc  cmp     ebx, 0C0000034h
0x140037dc2  jnz     short loc_140037DCB
0x140037dc4  mov     [rbp+SecurityDescriptor], r10
0x140037dc8  mov     ebx, r10d
0x140037dcb  test    rsi, rsi
0x140037dce  jz      short loc_140037DE1
0x140037dd0  xor     edx, edx; Tag
0x140037dd2  mov     rcx, rsi; P
0x140037dd5  call    cs:__imp_ExFreePoolWithTag
0x140037ddc  nop     dword ptr [rax+rax+00h]
0x140037de1  xor     esi, esi
0x140037de3  test    ebx, ebx
0x140037de5  js      loc_140037EA0
0x140037deb  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140037def  test    rcx, rcx
0x140037df2  jz      short loc_140037E30
0x140037df4  lea     r8, [rbp+arg_10]
0x140037df8  lea     rdx, [rbp+arg_8]
0x140037dfc  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140037e01  mov     ebx, eax
0x140037e03  test    eax, eax
0x140037e05  js      loc_140037EA0
0x140037e0b  cmp     [rbp+arg_8], sil
0x140037e0f  jz      short loc_140037E25
0x140037e11  mov     rcx, [rbp+SecurityDescriptor]; P
0x140037e15  xor     edx, edx; Tag
0x140037e17  call    cs:__imp_ExFreePoolWithTag
0x140037e1e  nop     dword ptr [rax+rax+00h]
0x140037e23  jmp     short loc_140037E30
0x140037e25  mov     rax, [rbp+SecurityDescriptor]
0x140037e29  or      dword ptr [rdi], 2
0x140037e2c  mov     [rdi+8], rax
0x140037e30  mov     r9, r13
0x140037e33  lea     rdx, aDevicetype; "DeviceType"
0x140037e3a  mov     rcx, r14
0x140037e3d  call    CmRegUtilWstrValueGetDword
0x140037e42  mov     ebx, eax
0x140037e44  test    eax, eax
0x140037e46  js      short loc_140037E4D
0x140037e48  or      dword ptr [rdi], 1
0x140037e4b  jmp     short loc_140037E54
0x140037e4d  cmp     eax, 0C0000034h
0x140037e52  jnz     short loc_140037EA0
0x140037e54  mov     r9, r15
0x140037e57  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x140037e5e  mov     rcx, r14
0x140037e61  call    CmRegUtilWstrValueGetDword
0x140037e66  mov     ebx, eax
0x140037e68  test    eax, eax
0x140037e6a  js      short loc_140037E71
0x140037e6c  or      dword ptr [rdi], 4
0x140037e6f  jmp     short loc_140037E78
0x140037e71  cmp     eax, 0C0000034h
0x140037e76  jnz     short loc_140037EA0
0x140037e78  mov     r9, r12
0x140037e7b  lea     rdx, aExclusive; "Exclusive"
0x140037e82  mov     rcx, r14
0x140037e85  call    CmRegUtilWstrValueGetDword
0x140037e8a  mov     ebx, eax
0x140037e8c  test    eax, eax
0x140037e8e  js      short loc_140037E95
0x140037e90  or      dword ptr [rdi], 8
0x140037e93  jmp     short loc_140037EC8
0x140037e95  cmp     eax, 0C0000034h
0x140037e9a  jnz     short loc_140037EA0
0x140037e9c  mov     ebx, esi
0x140037e9e  jmp     short loc_140037EC8
0x140037ea0  mov     rcx, [rdi+8]; P
0x140037ea4  test    rcx, rcx
0x140037ea7  jz      short loc_140037EB7
0x140037ea9  xor     edx, edx; Tag
0x140037eab  call    cs:__imp_ExFreePoolWithTag
0x140037eb2  nop     dword ptr [rax+rax+00h]
0x140037eb7  mov     [rdi], esi
0x140037eb9  mov     [rdi+8], rsi
0x140037ebd  mov     [r13+0], esi
0x140037ec1  mov     [r15], esi
0x140037ec4  mov     [r12], esi
0x140037ec8  mov     eax, ebx
0x140037eca  mov     rbx, [rsp+50h+arg_0]
0x140037ed2  add     rsp, 50h
0x140037ed6  pop     r15
0x140037ed8  pop     r14
0x140037eda  pop     r13
0x140037edc  pop     r12
0x140037ede  pop     rdi
0x140037edf  pop     rsi
0x140037ee0  pop     rbp
0x140037ee1  retn
```
