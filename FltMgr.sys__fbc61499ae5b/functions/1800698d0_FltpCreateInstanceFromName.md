# FltpCreateInstanceFromName

- ea: `0x1800698d0`
- end: `0x180069c7c`
- name: `FltpCreateInstanceFromName`
- size: `940`
- prototype: `__int64 __usercall@<rax>(PVOID FltObject@<rcx>, PCUNICODE_STRING SourceString, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180069430`
- `0x180074810`

## callees

- `0x180009f20`
- `0x180024940`
- `0x1800698d0`
- `0x180069c90`
- `0x18006a860`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180069acc`
- `ntoskrnl!ExFreePoolWithTag` at `0x180069b8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180069c4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007a6ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x180069acc`
- `ntoskrnl!ExFreePoolWithTag` at `0x180069b8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180069c4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007a6ef`
- `ntoskrnl!ExAllocatePool2` at `0x180069957`
- `ntoskrnl!ExAllocatePool2` at `0x180069bac`
- `ntoskrnl!ExAllocatePool2` at `0x18007a70d`
- `ntoskrnl!ExAllocatePool2` at `0x18007a74b`
- `ntoskrnl!ExAllocatePool2` at `0x180069957`
- `ntoskrnl!ExAllocatePool2` at `0x180069bac`
- `ntoskrnl!ExAllocatePool2` at `0x18007a70d`
- `ntoskrnl!ExAllocatePool2` at `0x18007a74b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800699e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x180069a48`
- `ntoskrnl!RtlInitUnicodeString` at `0x180069be3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800699e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x180069a48`
- `ntoskrnl!RtlInitUnicodeString` at `0x180069be3`
- `ntoskrnl!ZwClose` at `0x180069b16`
- `ntoskrnl!ZwClose` at `0x180069c6b`
- `ntoskrnl!ZwClose` at `0x180069b16`
- `ntoskrnl!ZwClose` at `0x180069c6b`
- `ntoskrnl!ZwOpenKey` at `0x1800699c0`
- `ntoskrnl!ZwOpenKey` at `0x1800699c0`
- `ntoskrnl!ZwQueryValueKey` at `0x180069a0c`
- `ntoskrnl!ZwQueryValueKey` at `0x180069a73`
- `ntoskrnl!ZwQueryValueKey` at `0x18007a6ad`
- `ntoskrnl!ZwQueryValueKey` at `0x180069a0c`
- `ntoskrnl!ZwQueryValueKey` at `0x180069a73`
- `ntoskrnl!ZwQueryValueKey` at `0x18007a6ad`

## pseudocode

```c
__int64 __fastcall FltpCreateInstanceFromName(
        char *FltObject,
        char *a2,
        unsigned int a3,
        void *a4,
        UNICODE_STRING *SourceString,
        __int64 *a6,
        __int64 a7)
{
  ULONG Length; // r15d
  _WORD *Pool2; // rdi
  UNICODE_STRING *v12; // r14
  int inited; // ebx
  NTSTATUS v14; // eax
  void *v16; // rax
  HANDLE Handle; // [rsp+38h] [rbp-61h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-59h] BYREF
  __int64 v19; // [rsp+48h] [rbp-51h] BYREF
  PVOID P; // [rsp+50h] [rbp-49h]
  UNICODE_STRING DestinationString; // [rsp+58h] [rbp-41h] BYREF
  UNICODE_STRING v22; // [rsp+68h] [rbp-31h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-21h] BYREF
  ULONG ResultLength; // [rsp+100h] [rbp+67h] BYREF

  Handle = 0;
  KeyHandle = 0;
  v19 = 0;
  ResultLength = 0;
  P = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  v22 = 0;
  if ( a4 )
  {
    Handle = a4;
  }
  else
  {
    inited = FltpOpenInstancesRegistryKey(*((_QWORD *)FltObject + 13), &Handle);
    if ( (int)FltpDbgStatus((unsigned int)inited, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 1559, 3221225524LL) < 0 )
      goto LABEL_15;
  }
  Length = 80;
  Pool2 = (_WORD *)ExAllocatePool2(256, 80, 1920224582);
  if ( Pool2 )
  {
    v12 = SourceString;
    if ( !SourceString )
    {
      RtlInitUnicodeString(&DestinationString, L"DEFAULTINSTANCE");
      while ( 1 )
      {
        inited = ZwQueryValueKey(Handle, &DestinationString, KeyValuePartialInformation, Pool2, Length, &ResultLength);
        if ( (int)FltpDbgStatus((unsigned int)inited, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 1606, 0) >= 0 )
          break;
        if ( inited != -1073741789 && inited != -2147483643 )
          goto LABEL_14;
        ExFreePoolWithTag(Pool2, 0x72744D46u);
        Length = ResultLength;
        Pool2 = (_WORD *)ExAllocatePool2(256, ResultLength, 1920224582);
        if ( !Pool2 )
        {
          inited = -1073741670;
          goto LABEL_15;
        }
      }
      WORD1(v19) = Pool2[4];
      LOWORD(v19) = WORD1(v19) - 2;
      v16 = (void *)ExAllocatePool2(256, WORD1(v19), 1920224582);
      P = v16;
      if ( !v16 )
      {
        inited = -1073741670;
        goto LABEL_14;
      }
      memmove(v16, Pool2 + 6, (unsigned __int16)v19);
      v12 = (UNICODE_STRING *)&v19;
    }
    if ( a7 && *(unsigned __int16 *)(a7 + 2) < (unsigned __int64)v12->Length + 2 )
    {
      inited = -2145648639;
LABEL_14:
      ExFreePoolWithTag(Pool2, 0x72744D46u);
      goto LABEL_15;
    }
    ObjectAttributes.RootDirectory = Handle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.ObjectName = v12;
    inited = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( inited < 0 )
      goto LABEL_14;
    RtlInitUnicodeString(&DestinationString, L"FLAGS");
    inited = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, Pool2, Length, &ResultLength);
    if ( inited < 0 )
      goto LABEL_14;
    if ( (a3 & 1) != 0 && (*((_DWORD *)Pool2 + 3) & 1) != 0 )
    {
      inited = -1071906801;
      goto LABEL_14;
    }
    if ( (a3 & 2) != 0 && (*((_DWORD *)Pool2 + 3) & 2) != 0 )
    {
      inited = -1071906801;
      goto LABEL_14;
    }
    RtlInitUnicodeString(&DestinationString, L"ALTITUDE");
    do
    {
      v14 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, Pool2, Length, &ResultLength);
      inited = v14;
      if ( v14 >= 0 )
      {
        v22.Length = Pool2[4] - 2;
        v22.MaximumLength = v22.Length;
        v22.Buffer = Pool2 + 6;
        inited = FltpInitInstance(FltObject, a2, a3, &v22, v12, a6);
        goto LABEL_14;
      }
      if ( v14 != -1073741789 && v14 != -2147483643 )
        goto LABEL_14;
      ExFreePoolWithTag(Pool2, 0x72744D46u);
      Length = ResultLength;
      Pool2 = (_WORD *)ExAllocatePool2(256, ResultLength, 1920224582);
    }
    while ( Pool2 );
    inited = -1073741670;
  }
  else
  {
    inited = -1073741670;
  }
LABEL_15:
  if ( P )
    ExFreePoolWithTag(P, 0x72744D46u);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( !a4 && Handle )
    ZwClose(Handle);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800698d0  mov     rax, rsp
0x1800698d3  mov     [rax+10h], rdx
0x1800698d7  push    rbp
0x1800698d8  push    rbx
0x1800698d9  lea     rbp, [rax-47h]
0x1800698dd  sub     rsp, 0C8h
0x1800698e4  mov     [rax+8], rsi
0x1800698e8  xorps   xmm0, xmm0
0x1800698eb  mov     [rax-18h], rdi
0x1800698ef  xorps   xmm1, xmm1
0x1800698f2  xor     edi, edi
0x1800698f4  mov     [rax-20h], r12
0x1800698f8  mov     [rax-28h], r13
0x1800698fc  mov     rsi, r9
0x1800698ff  xor     eax, eax
0x180069901  mov     [rbp+3Fh+Handle], rdi
0x180069905  mov     [rbp+3Fh+KeyHandle], rdi
0x180069909  mov     r12d, r8d
0x18006990c  mov     [rbp+3Fh+var_90], rdi
0x180069910  mov     r13, rcx
0x180069913  mov     [rbp+3Fh+ResultLength], edi
0x180069916  mov     [rbp+3Fh+P], rdi
0x18006991a  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x18006991e  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x180069922  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x180069926  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x18006992a  movups  [rbp+3Fh+var_70], xmm1
0x18006992e  test    r9, r9
0x180069931  jz      loc_180069B40
0x180069937  mov     [rbp+3Fh+Handle], r9
0x18006993b  mov     [rsp+0D0h+var_30], r15
0x180069943  mov     r8d, 72744D46h
0x180069949  mov     r15d, 50h ; 'P'
0x18006994f  mov     ecx, 100h
0x180069954  mov     edx, r15d
0x180069957  call    cs:__imp_ExAllocatePool2
0x18006995e  nop     dword ptr [rax+rax+00h]
0x180069963  mov     rdi, rax
0x180069966  test    rax, rax
0x180069969  jz      loc_180069BCE
0x18006996f  mov     [rsp+0D0h+var_28], r14
0x180069977  mov     r14, [rbp+3Fh+SourceString]
0x18006997b  test    r14, r14
0x18006997e  jz      loc_180069BD8
0x180069984  mov     rax, [rbp+3Fh+arg_30]
0x180069988  test    rax, rax
0x18006998b  jnz     loc_180069BFA
0x180069991  mov     rax, [rbp+3Fh+Handle]
0x180069995  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x180069999  xorps   xmm0, xmm0
0x18006999c  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rax
0x1800699a0  mov     edx, 20019h; DesiredAccess
0x1800699a5  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x1800699ac  lea     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x1800699b0  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x1800699b7  movdqu  xmmword ptr [rbp-1], xmm0
0x1800699bc  mov     [rbp+3Fh+ObjectAttributes.ObjectName], r14
0x1800699c0  call    cs:__imp_ZwOpenKey
0x1800699c7  nop     dword ptr [rax+rax+00h]
0x1800699cc  mov     ebx, eax
0x1800699ce  test    eax, eax
0x1800699d0  js      loc_180069AC4
0x1800699d6  lea     rdx, FltpRegFlagsValueName; "FLAGS"
0x1800699dd  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1800699e1  call    cs:__imp_RtlInitUnicodeString
0x1800699e8  nop     dword ptr [rax+rax+00h]
0x1800699ed  mov     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x1800699f1  lea     rax, [rbp+3Fh+ResultLength]
0x1800699f5  mov     [rsp+28h], rax; ResultLength
0x1800699fa  lea     rdx, [rbp+3Fh+DestinationString]; ValueName
0x1800699fe  mov     r9, rdi; KeyValueInformation
0x180069a01  mov     [rsp+0D0h+Length], r15d; Length
0x180069a06  mov     r8d, 2; KeyValueInformationClass
0x180069a0c  call    cs:__imp_ZwQueryValueKey
0x180069a13  nop     dword ptr [rax+rax+00h]
0x180069a18  mov     ebx, eax
0x180069a1a  test    eax, eax
0x180069a1c  js      loc_180069AC4
0x180069a22  test    r12b, 1
0x180069a26  jz      short loc_180069A33
0x180069a28  mov     eax, [rdi+0Ch]
0x180069a2b  test    al, 1
0x180069a2d  jnz     loc_180069C19
0x180069a33  test    r12b, 2
0x180069a37  jnz     loc_180069C23
0x180069a3d  lea     rdx, FltpRegAltitudeValueName; "ALTITUDE"
0x180069a44  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x180069a48  call    cs:__imp_RtlInitUnicodeString
0x180069a4f  nop     dword ptr [rax+rax+00h]
0x180069a54  mov     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x180069a58  lea     rax, [rbp+3Fh+ResultLength]
0x180069a5c  mov     [rsp+28h], rax; ResultLength
0x180069a61  lea     rdx, [rbp+3Fh+DestinationString]; ValueName
0x180069a65  mov     r9, rdi; KeyValueInformation
0x180069a68  mov     [rsp+0D0h+Length], r15d; Length
0x180069a6d  mov     r8d, 2; KeyValueInformationClass
0x180069a73  call    cs:__imp_ZwQueryValueKey
0x180069a7a  nop     dword ptr [rax+rax+00h]
0x180069a7f  mov     ebx, eax
0x180069a81  test    eax, eax
0x180069a83  js      loc_180069B7B
0x180069a89  movzx   eax, word ptr [rdi+8]
0x180069a8d  lea     r9, [rbp+3Fh+var_70]
0x180069a91  mov     rdx, [rbp+3Fh+arg_8]; PVOID
0x180069a95  sub     ax, 2
0x180069a99  mov     word ptr [rbp+3Fh+var_70], ax
0x180069a9d  mov     r8d, r12d
0x180069aa0  mov     word ptr [rbp+3Fh+var_70+2], ax
0x180069aa4  mov     rcx, r13; FltObject
0x180069aa7  lea     rax, [rdi+0Ch]
0x180069aab  mov     qword ptr [rbp+3Fh+var_70+8], rax
0x180069aaf  mov     rax, [rbp+3Fh+arg_28]
0x180069ab3  mov     [rsp+28h], rax; __int64
0x180069ab8  mov     qword ptr [rsp+0D0h+Length], r14; SourceString
0x180069abd  call    FltpInitInstance
0x180069ac2  mov     ebx, eax
0x180069ac4  mov     edx, 72744D46h; Tag
0x180069ac9  mov     rcx, rdi; P
0x180069acc  call    cs:__imp_ExFreePoolWithTag
0x180069ad3  nop     dword ptr [rax+rax+00h]
0x180069ad8  mov     r14, [rsp+0D0h+var_28]
0x180069ae0  mov     r15, [rsp+0D0h+var_30]
0x180069ae8  mov     rcx, [rbp+3Fh+P]; P
0x180069aec  mov     r13, [rsp+0D0h+var_20]
0x180069af4  mov     r12, [rsp+0D0h+var_18]
0x180069afc  mov     rdi, [rsp+0C0h]
0x180069b04  test    rcx, rcx
0x180069b07  jnz     loc_180069C48
0x180069b0d  mov     rcx, [rbp+3Fh+KeyHandle]; Handle
0x180069b11  test    rcx, rcx
0x180069b14  jz      short loc_180069B22
0x180069b16  call    cs:__imp_ZwClose
0x180069b1d  nop     dword ptr [rax+rax+00h]
0x180069b22  test    rsi, rsi
0x180069b25  mov     rsi, [rsp+0D0h+arg_0]
0x180069b2d  jz      loc_180069C5E
0x180069b33  mov     eax, ebx
0x180069b35  add     rsp, 0C8h
0x180069b3c  pop     rbx
0x180069b3d  pop     rbp
0x180069b3e  retn
0x180069b40  mov     rcx, [rcx+68h]
0x180069b44  lea     rdx, [rbp+3Fh+Handle]
0x180069b48  call    FltpOpenInstancesRegistryKey
0x180069b4d  mov     r8d, 617h
0x180069b53  mov     qword ptr [rsp+0D0h+Length], rdi
0x180069b58  mov     r9d, 0C0000034h
0x180069b5e  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x180069b65  mov     ecx, eax
0x180069b67  mov     ebx, eax
0x180069b69  call    FltpDbgStatus
0x180069b6e  test    eax, eax
0x180069b70  js      loc_180069AE8
0x180069b76  jmp     loc_18006993B
0x180069b7b  cmp     eax, 0C0000023h
0x180069b80  jnz     loc_180069C38
0x180069b86  mov     edx, 72744D46h; Tag
0x180069b8b  mov     rcx, rdi; P
0x180069b8e  call    cs:__imp_ExFreePoolWithTag
0x180069b95  nop     dword ptr [rax+rax+00h]
0x180069b9a  mov     r15d, [rbp+3Fh+ResultLength]
0x180069b9e  mov     ecx, 100h
0x180069ba3  mov     edx, r15d
0x180069ba6  mov     r8d, 72744D46h
0x180069bac  call    cs:__imp_ExAllocatePool2
0x180069bb3  nop     dword ptr [rax+rax+00h]
0x180069bb8  mov     rdi, rax
0x180069bbb  test    rax, rax
0x180069bbe  jnz     loc_180069A54
0x180069bc4  mov     ebx, 0C000009Ah
0x180069bc9  jmp     loc_180069AD8
0x180069bce  mov     ebx, 0C000009Ah
0x180069bd3  jmp     loc_180069AE0
0x180069bd8  lea     rdx, FltpRegDefaultInstanceValueName; "DEFAULTINSTANCE"
0x180069bdf  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x180069be3  call    cs:__imp_RtlInitUnicodeString
0x180069bea  nop     dword ptr [rax+rax+00h]
0x180069bef  mov     r14d, 646h
0x180069bf5  jmp     loc_18007A68E
0x180069bfa  movzx   ecx, word ptr [r14]
0x180069bfe  movzx   eax, word ptr [rax+2]
0x180069c02  add     rcx, 2
0x180069c06  cmp     rax, rcx
0x180069c09  jnb     loc_180069991
0x180069c0f  mov     ebx, 801C0001h
0x180069c14  jmp     loc_180069AC4
0x180069c19  mov     ebx, 0C01C000Fh
0x180069c1e  jmp     loc_180069AC4
0x180069c23  mov     eax, [rdi+0Ch]
0x180069c26  test    al, 2
0x180069c28  jz      loc_180069A3D
0x180069c2e  mov     ebx, 0C01C000Fh
0x180069c33  jmp     loc_180069AC4
0x180069c38  cmp     eax, 80000005h
0x180069c3d  jnz     loc_180069AC4
0x180069c43  jmp     loc_180069B86
0x180069c48  mov     edx, 72744D46h; Tag
0x180069c4d  call    cs:__imp_ExFreePoolWithTag
0x180069c54  nop     dword ptr [rax+rax+00h]
0x180069c59  jmp     loc_180069B0D
0x180069c5e  mov     rcx, [rbp+3Fh+Handle]; Handle
0x180069c62  test    rcx, rcx
0x180069c65  jz      loc_180069B33
0x180069c6b  call    cs:__imp_ZwClose
0x180069c72  nop     dword ptr [rax+rax+00h]
0x180069c77  jmp     loc_180069B33
0x18007a68e  mov     rcx, [rbp+3Fh+Handle]; KeyHandle
0x18007a692  lea     rax, [rbp+3Fh+ResultLength]
0x18007a696  mov     [rsp+28h], rax; ResultLength
0x18007a69b  lea     rdx, [rbp+3Fh+DestinationString]; ValueName
0x18007a69f  mov     r9, rdi; KeyValueInformation
0x18007a6a2  mov     [rsp+0D0h+Length], r15d; Length
0x18007a6a7  mov     r8d, 2; KeyValueInformationClass
0x18007a6ad  call    cs:__imp_ZwQueryValueKey
0x18007a6b4  nop     dword ptr [rax+rax+00h]
0x18007a6b9  xor     r9d, r9d
0x18007a6bc  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x18007a6c3  mov     ecx, eax
0x18007a6c5  mov     r8d, r14d
0x18007a6c8  mov     ebx, eax
0x18007a6ca  call    FltpDbgStatus
0x18007a6cf  test    eax, eax
0x18007a6d1  jns     short loc_18007A72F
0x18007a6d3  cmp     ebx, 0C0000023h
0x18007a6d9  jz      short loc_18007A6E7
0x18007a6db  cmp     ebx, 80000005h
0x18007a6e1  jnz     loc_180069AC4
0x18007a6e7  mov     edx, 72744D46h; Tag
0x18007a6ec  mov     rcx, rdi; P
0x18007a6ef  call    cs:__imp_ExFreePoolWithTag
0x18007a6f6  nop     dword ptr [rax+rax+00h]
0x18007a6fb  mov     r15d, [rbp+3Fh+ResultLength]
0x18007a6ff  mov     ecx, 100h
0x18007a704  mov     edx, r15d
0x18007a707  mov     r8d, 72744D46h
0x18007a70d  call    cs:__imp_ExAllocatePool2
0x18007a714  nop     dword ptr [rax+rax+00h]
0x18007a719  mov     rdi, rax
0x18007a71c  test    rax, rax
0x18007a71f  jnz     loc_18007A68E
0x18007a725  mov     ebx, 0C000009Ah
0x18007a72a  jmp     loc_180069AD8
0x18007a72f  movzx   ecx, word ptr [rdi+8]
0x18007a733  mov     r8d, 72744D46h
0x18007a739  mov     word ptr [rbp+3Fh+var_90+2], cx
0x18007a73d  mov     edx, ecx
0x18007a73f  lea     eax, [rcx-2]
0x18007a742  mov     ecx, 100h
0x18007a747  mov     word ptr [rbp+3Fh+var_90], ax
0x18007a74b  call    cs:__imp_ExAllocatePool2
0x18007a752  nop     dword ptr [rax+rax+00h]
0x18007a757  mov     [rbp+3Fh+P], rax
0x18007a75b  test    rax, rax
0x18007a75e  jnz     short loc_18007A76A
0x18007a760  mov     ebx, 0C000009Ah
0x18007a765  jmp     loc_180069AC4
0x18007a76a  movzx   r8d, word ptr [rbp+3Fh+var_90]; Size
0x18007a76f  lea     rdx, [rdi+0Ch]; Src
0x18007a773  mov     rcx, rax; void *
0x18007a776  call    memmove
0x18007a77b  lea     r14, [rbp+3Fh+var_90]
0x18007a77f  jmp     loc_180069984
```
