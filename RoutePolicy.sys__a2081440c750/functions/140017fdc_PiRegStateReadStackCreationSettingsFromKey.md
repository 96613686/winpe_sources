# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x140017fdc`
- end: `0x1400181bb`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400181c4`

## callees

- `0x140008c0c`
- `0x140017fdc`
- `0x1400184ac`
- `0x14001870c`
- `0x1400189bc`

## import_xrefs

- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140018084`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140018084`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400180ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400180ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018183`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400180ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400180ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018183`

## string_xrefs

- `0x14001801e`: `Security`

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
0x140017fdc  mov     [rsp-38h+arg_0], rbx
0x140017fe1  push    rbp
0x140017fe2  push    rsi
0x140017fe3  push    rdi
0x140017fe4  push    r12
0x140017fe6  push    r13
0x140017fe8  push    r14
0x140017fea  push    r15
0x140017fec  mov     rbp, rsp
0x140017fef  sub     rsp, 50h
0x140017ff3  xor     r10d, r10d
0x140017ff6  lea     r13, [rdx+4]
0x140017ffa  lea     r15, [rdx+10h]
0x140017ffe  mov     [rdx], r10d
0x140018001  lea     r12, [rdx+14h]
0x140018005  mov     [rdx+8], r10
0x140018009  mov     rdi, rdx
0x14001800c  mov     [rbp+SecurityDescriptor], r10
0x140018010  mov     r14, rcx
0x140018013  mov     [rbp+arg_10], r10d
0x140018017  xorps   xmm0, xmm0
0x14001801a  mov     [rbp+arg_8], r10b
0x14001801e  lea     rdx, aSecurity; "Security"
0x140018025  mov     [rbp+P], r10
0x140018029  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001802d  mov     [r13+0], r10d
0x140018031  mov     esi, r10d
0x140018034  mov     [r15], r10d
0x140018037  mov     [r12], r10d
0x14001803b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001803f  call    WdmlibRtlInitUnicodeStringEx
0x140018044  mov     ebx, eax
0x140018046  test    eax, eax
0x140018048  js      short loc_140018094
0x14001804a  lea     rax, [rbp+P]
0x14001804e  mov     rcx, r14; KeyHandle
0x140018051  lea     rdx, [rbp+DestinationString]; ValueName
0x140018055  mov     [rsp+50h+var_30], rax; __int64
0x14001805a  call    CmRegUtilUcValueGetFullBuffer
0x14001805f  mov     rsi, [rbp+P]
0x140018063  xor     r10d, r10d
0x140018066  mov     ebx, eax
0x140018068  test    eax, eax
0x14001806a  js      short loc_140018094
0x14001806c  mov     ecx, [rsi+8]
0x14001806f  lea     rax, [rbp+SecurityDescriptor]
0x140018073  add     rcx, rsi
0x140018076  mov     [rsp+50h+var_30], rax
0x14001807b  mov     r9b, 1
0x14001807e  lea     r8d, [r10+1]
0x140018082  xor     edx, edx
0x140018084  call    cs:__imp_SeCaptureSecurityDescriptor
0x14001808b  nop     dword ptr [rax+rax+00h]
0x140018090  mov     ebx, eax
0x140018092  jmp     short loc_1400180A3
0x140018094  cmp     ebx, 0C0000034h
0x14001809a  jnz     short loc_1400180A3
0x14001809c  mov     [rbp+SecurityDescriptor], r10
0x1400180a0  mov     ebx, r10d
0x1400180a3  test    rsi, rsi
0x1400180a6  jz      short loc_1400180B9
0x1400180a8  xor     edx, edx; Tag
0x1400180aa  mov     rcx, rsi; P
0x1400180ad  call    cs:__imp_ExFreePoolWithTag
0x1400180b4  nop     dword ptr [rax+rax+00h]
0x1400180b9  xor     esi, esi
0x1400180bb  test    ebx, ebx
0x1400180bd  js      loc_140018178
0x1400180c3  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400180c7  test    rcx, rcx
0x1400180ca  jz      short loc_140018108
0x1400180cc  lea     r8, [rbp+arg_10]
0x1400180d0  lea     rdx, [rbp+arg_8]
0x1400180d4  call    SeUtilSecurityInfoFromSecurityDescriptor
0x1400180d9  mov     ebx, eax
0x1400180db  test    eax, eax
0x1400180dd  js      loc_140018178
0x1400180e3  cmp     [rbp+arg_8], sil
0x1400180e7  jz      short loc_1400180FD
0x1400180e9  mov     rcx, [rbp+SecurityDescriptor]; P
0x1400180ed  xor     edx, edx; Tag
0x1400180ef  call    cs:__imp_ExFreePoolWithTag
0x1400180f6  nop     dword ptr [rax+rax+00h]
0x1400180fb  jmp     short loc_140018108
0x1400180fd  mov     rax, [rbp+SecurityDescriptor]
0x140018101  or      dword ptr [rdi], 2
0x140018104  mov     [rdi+8], rax
0x140018108  mov     r9, r13
0x14001810b  lea     rdx, aDevicetype; "DeviceType"
0x140018112  mov     rcx, r14
0x140018115  call    CmRegUtilWstrValueGetDword
0x14001811a  mov     ebx, eax
0x14001811c  test    eax, eax
0x14001811e  js      short loc_140018125
0x140018120  or      dword ptr [rdi], 1
0x140018123  jmp     short loc_14001812C
0x140018125  cmp     eax, 0C0000034h
0x14001812a  jnz     short loc_140018178
0x14001812c  mov     r9, r15
0x14001812f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x140018136  mov     rcx, r14
0x140018139  call    CmRegUtilWstrValueGetDword
0x14001813e  mov     ebx, eax
0x140018140  test    eax, eax
0x140018142  js      short loc_140018149
0x140018144  or      dword ptr [rdi], 4
0x140018147  jmp     short loc_140018150
0x140018149  cmp     eax, 0C0000034h
0x14001814e  jnz     short loc_140018178
0x140018150  mov     r9, r12
0x140018153  lea     rdx, aExclusive; "Exclusive"
0x14001815a  mov     rcx, r14
0x14001815d  call    CmRegUtilWstrValueGetDword
0x140018162  mov     ebx, eax
0x140018164  test    eax, eax
0x140018166  js      short loc_14001816D
0x140018168  or      dword ptr [rdi], 8
0x14001816b  jmp     short loc_1400181A0
0x14001816d  cmp     eax, 0C0000034h
0x140018172  jnz     short loc_140018178
0x140018174  mov     ebx, esi
0x140018176  jmp     short loc_1400181A0
0x140018178  mov     rcx, [rdi+8]; P
0x14001817c  test    rcx, rcx
0x14001817f  jz      short loc_14001818F
0x140018181  xor     edx, edx; Tag
0x140018183  call    cs:__imp_ExFreePoolWithTag
0x14001818a  nop     dword ptr [rax+rax+00h]
0x14001818f  mov     [rdi], esi
0x140018191  mov     [rdi+8], rsi
0x140018195  mov     [r13+0], esi
0x140018199  mov     [r15], esi
0x14001819c  mov     [r12], esi
0x1400181a0  mov     eax, ebx
0x1400181a2  mov     rbx, [rsp+50h+arg_0]
0x1400181aa  add     rsp, 50h
0x1400181ae  pop     r15
0x1400181b0  pop     r14
0x1400181b2  pop     r13
0x1400181b4  pop     r12
0x1400181b6  pop     rdi
0x1400181b7  pop     rsi
0x1400181b8  pop     rbp
0x1400181b9  retn
```
