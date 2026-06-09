# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x14002553c`
- end: `0x14002571b`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140025724`

## callees

- `0x1400138e0`
- `0x14002553c`
- `0x140025a0c`
- `0x140025c6c`
- `0x140025f1c`

## import_xrefs

- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400255e4`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400255e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002560d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002564f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400256e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002560d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002564f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400256e3`

## string_xrefs

- `0x14002557e`: `Security`

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
0x14002553c  mov     [rsp-38h+arg_0], rbx
0x140025541  push    rbp
0x140025542  push    rsi
0x140025543  push    rdi
0x140025544  push    r12
0x140025546  push    r13
0x140025548  push    r14
0x14002554a  push    r15
0x14002554c  mov     rbp, rsp
0x14002554f  sub     rsp, 50h
0x140025553  xor     r10d, r10d
0x140025556  lea     r13, [rdx+4]
0x14002555a  lea     r15, [rdx+10h]
0x14002555e  mov     [rdx], r10d
0x140025561  lea     r12, [rdx+14h]
0x140025565  mov     [rdx+8], r10
0x140025569  mov     rdi, rdx
0x14002556c  mov     [rbp+SecurityDescriptor], r10
0x140025570  mov     r14, rcx
0x140025573  mov     [rbp+arg_10], r10d
0x140025577  xorps   xmm0, xmm0
0x14002557a  mov     [rbp+arg_8], r10b
0x14002557e  lea     rdx, aSecurity; "Security"
0x140025585  mov     [rbp+P], r10
0x140025589  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002558d  mov     [r13+0], r10d
0x140025591  mov     esi, r10d
0x140025594  mov     [r15], r10d
0x140025597  mov     [r12], r10d
0x14002559b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002559f  call    WdmlibRtlInitUnicodeStringEx
0x1400255a4  mov     ebx, eax
0x1400255a6  test    eax, eax
0x1400255a8  js      short loc_1400255F4
0x1400255aa  lea     rax, [rbp+P]
0x1400255ae  mov     rcx, r14; KeyHandle
0x1400255b1  lea     rdx, [rbp+DestinationString]; ValueName
0x1400255b5  mov     [rsp+50h+var_30], rax; __int64
0x1400255ba  call    CmRegUtilUcValueGetFullBuffer
0x1400255bf  mov     rsi, [rbp+P]
0x1400255c3  xor     r10d, r10d
0x1400255c6  mov     ebx, eax
0x1400255c8  test    eax, eax
0x1400255ca  js      short loc_1400255F4
0x1400255cc  mov     ecx, [rsi+8]
0x1400255cf  lea     rax, [rbp+SecurityDescriptor]
0x1400255d3  add     rcx, rsi
0x1400255d6  mov     [rsp+50h+var_30], rax
0x1400255db  mov     r9b, 1
0x1400255de  lea     r8d, [r10+1]
0x1400255e2  xor     edx, edx
0x1400255e4  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400255eb  nop     dword ptr [rax+rax+00h]
0x1400255f0  mov     ebx, eax
0x1400255f2  jmp     short loc_140025603
0x1400255f4  cmp     ebx, 0C0000034h
0x1400255fa  jnz     short loc_140025603
0x1400255fc  mov     [rbp+SecurityDescriptor], r10
0x140025600  mov     ebx, r10d
0x140025603  test    rsi, rsi
0x140025606  jz      short loc_140025619
0x140025608  xor     edx, edx; Tag
0x14002560a  mov     rcx, rsi; P
0x14002560d  call    cs:__imp_ExFreePoolWithTag
0x140025614  nop     dword ptr [rax+rax+00h]
0x140025619  xor     esi, esi
0x14002561b  test    ebx, ebx
0x14002561d  js      loc_1400256D8
0x140025623  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140025627  test    rcx, rcx
0x14002562a  jz      short loc_140025668
0x14002562c  lea     r8, [rbp+arg_10]
0x140025630  lea     rdx, [rbp+arg_8]
0x140025634  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140025639  mov     ebx, eax
0x14002563b  test    eax, eax
0x14002563d  js      loc_1400256D8
0x140025643  cmp     [rbp+arg_8], sil
0x140025647  jz      short loc_14002565D
0x140025649  mov     rcx, [rbp+SecurityDescriptor]; P
0x14002564d  xor     edx, edx; Tag
0x14002564f  call    cs:__imp_ExFreePoolWithTag
0x140025656  nop     dword ptr [rax+rax+00h]
0x14002565b  jmp     short loc_140025668
0x14002565d  mov     rax, [rbp+SecurityDescriptor]
0x140025661  or      dword ptr [rdi], 2
0x140025664  mov     [rdi+8], rax
0x140025668  mov     r9, r13
0x14002566b  lea     rdx, aDevicetype; "DeviceType"
0x140025672  mov     rcx, r14
0x140025675  call    CmRegUtilWstrValueGetDword
0x14002567a  mov     ebx, eax
0x14002567c  test    eax, eax
0x14002567e  js      short loc_140025685
0x140025680  or      dword ptr [rdi], 1
0x140025683  jmp     short loc_14002568C
0x140025685  cmp     eax, 0C0000034h
0x14002568a  jnz     short loc_1400256D8
0x14002568c  mov     r9, r15
0x14002568f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x140025696  mov     rcx, r14
0x140025699  call    CmRegUtilWstrValueGetDword
0x14002569e  mov     ebx, eax
0x1400256a0  test    eax, eax
0x1400256a2  js      short loc_1400256A9
0x1400256a4  or      dword ptr [rdi], 4
0x1400256a7  jmp     short loc_1400256B0
0x1400256a9  cmp     eax, 0C0000034h
0x1400256ae  jnz     short loc_1400256D8
0x1400256b0  mov     r9, r12
0x1400256b3  lea     rdx, aExclusive; "Exclusive"
0x1400256ba  mov     rcx, r14
0x1400256bd  call    CmRegUtilWstrValueGetDword
0x1400256c2  mov     ebx, eax
0x1400256c4  test    eax, eax
0x1400256c6  js      short loc_1400256CD
0x1400256c8  or      dword ptr [rdi], 8
0x1400256cb  jmp     short loc_140025700
0x1400256cd  cmp     eax, 0C0000034h
0x1400256d2  jnz     short loc_1400256D8
0x1400256d4  mov     ebx, esi
0x1400256d6  jmp     short loc_140025700
0x1400256d8  mov     rcx, [rdi+8]; P
0x1400256dc  test    rcx, rcx
0x1400256df  jz      short loc_1400256EF
0x1400256e1  xor     edx, edx; Tag
0x1400256e3  call    cs:__imp_ExFreePoolWithTag
0x1400256ea  nop     dword ptr [rax+rax+00h]
0x1400256ef  mov     [rdi], esi
0x1400256f1  mov     [rdi+8], rsi
0x1400256f5  mov     [r13+0], esi
0x1400256f9  mov     [r15], esi
0x1400256fc  mov     [r12], esi
0x140025700  mov     eax, ebx
0x140025702  mov     rbx, [rsp+50h+arg_0]
0x14002570a  add     rsp, 50h
0x14002570e  pop     r15
0x140025710  pop     r14
0x140025712  pop     r13
0x140025714  pop     r12
0x140025716  pop     rdi
0x140025717  pop     rsi
0x140025718  pop     rbp
0x140025719  retn
```
