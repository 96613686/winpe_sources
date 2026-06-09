# RegGetKeySecurity

- ea: `0x1800d9710`
- end: `0x1800d9bd2`
- name: `RegGetKeySecurity`
- size: `1218`
- prototype: `LSTATUS __stdcall(HKEY hKey, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor, LPDWORD lpcbSecurityDescriptor)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180051660`

## callees

- `0x18005b460`
- `0x18005bb80`
- `0x18005cb00`
- `0x18005d0a0`
- `0x18005e150`
- `0x1800d9710`
- `0x1800d9bd8`
- `0x18012d578`
- `0x180188eb9`

## import_xrefs

- `ntdll!NtQuerySecurityObject` at `0x1800d98bc`
- `ntdll!NtQuerySecurityObject` at `0x1800d98bc`
- `ntdll!RtlNtStatusToDosError` at `0x1800d9931`
- `ntdll!RtlNtStatusToDosError` at `0x1800d99b2`
- `ntdll!RtlNtStatusToDosError` at `0x180193eb7`
- `ntdll!RtlNtStatusToDosError` at `0x1800d9931`
- `ntdll!RtlNtStatusToDosError` at `0x1800d99b2`
- `ntdll!RtlNtStatusToDosError` at `0x180193eb7`
- `ntdll!RtlInitUnicodeStringEx` at `0x180193e48`
- `ntdll!RtlInitUnicodeStringEx` at `0x180193e48`
- `ntdll!NtClose` at `0x1800d9a48`
- `ntdll!NtClose` at `0x1800d9bc7`
- `ntdll!NtClose` at `0x1800d9a48`
- `ntdll!NtClose` at `0x1800d9bc7`
- `ntdll!RtlValidSecurityDescriptor` at `0x1800d98c9`
- `ntdll!RtlValidSecurityDescriptor` at `0x1800d9b99`
- `ntdll!RtlValidSecurityDescriptor` at `0x1800d98c9`
- `ntdll!RtlValidSecurityDescriptor` at `0x1800d9b99`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800d98da`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800d98da`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800d9929`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800d9929`
- `ntdll!RtlFreeHeap` at `0x1800d995b`
- `ntdll!RtlFreeHeap` at `0x1800d995b`
- `ntdll!RtlAllocateHeap` at `0x1800d9893`
- `ntdll!RtlAllocateHeap` at `0x1800d9902`
- `ntdll!RtlAllocateHeap` at `0x1800d9893`
- `ntdll!RtlAllocateHeap` at `0x1800d9902`
- `ext-ms-win-advapi32-registry-l1-1-0!SafeBaseRegGetKeySecurity` at `0x1800d9afc`
- `ext-ms-win-advapi32-registry-l1-1-0!SafeBaseRegGetKeySecurity` at `0x1800d9afc`
- `ext-ms-win-advapi32-registry-l1-1-0!MIDL_user_free_Ext` at `0x1800d9b73`
- `ext-ms-win-advapi32-registry-l1-1-0!MIDL_user_free_Ext` at `0x1800d9b73`

## string_xrefs

- `0x180193e3c`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib`

## pseudocode

```c
LSTATUS __stdcall RegGetKeySecurity(
        HKEY hKey,
        SECURITY_INFORMATION SecurityInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        LPDWORD lpcbSecurityDescriptor)
{
  BOOL v5; // r13d
  __int64 v6; // r8
  void *v7; // rcx
  LSTATUS KeySecurity; // edi
  unsigned int v9; // r15d
  void *v10; // r12
  LPDWORD v11; // r13
  ULONG v12; // eax
  HANDLE v13; // rsi
  void *v14; // r15
  SECURITY_INFORMATION v15; // edi
  PVOID Heap; // r14
  int SecurityObject; // eax
  ULONG v18; // edi
  PVOID v19; // rax
  HKEY v20; // rsi
  LSTATUS result; // eax
  NTSTATUS UserAndMachineClass; // eax
  void *v23; // rax
  __int64 v24; // rcx
  NTSTATUS v25; // eax
  ULONG Length[4]; // [rsp+30h] [rbp-C8h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-B8h]
  size_t Size[2]; // [rsp+48h] [rbp-B0h] BYREF
  ULONG LengthNeeded[2]; // [rsp+58h] [rbp-A0h] BYREF
  LSTATUS v30; // [rsp+60h] [rbp-98h]
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-90h] BYREF
  LPWCH v32; // [rsp+78h] [rbp-80h] BYREF
  HKEY v33; // [rsp+80h] [rbp-78h] BYREF
  _DWORD v34[2]; // [rsp+88h] [rbp-70h] BYREF
  __int64 v35; // [rsp+90h] [rbp-68h]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+98h] [rbp-60h]
  int v37; // [rsp+A0h] [rbp-58h]
  int v38; // [rsp+A4h] [rbp-54h]
  __int128 v39; // [rsp+A8h] [rbp-50h]
  HANDLE Handle; // [rsp+100h] [rbp+8h] BYREF
  SECURITY_INFORMATION SecurityInformationa; // [rsp+108h] [rbp+10h]
  PSECURITY_DESCRIPTOR v42; // [rsp+110h] [rbp+18h]
  LPDWORD v43; // [rsp+118h] [rbp+20h]

  v43 = lpcbSecurityDescriptor;
  v42 = pSecurityDescriptor;
  SecurityInformationa = SecurityInformation;
  Handle = hKey;
  *(_OWORD *)Length = 0;
  *(_QWORD *)LengthNeeded = 0;
  Size[0] = 0;
  v33 = 0;
  v32 = 0;
  if ( hKey == HKEY_PERFORMANCE_DATA )
    return 6;
  if ( !lpcbSecurityDescriptor )
    return 87;
  v5 = hKey == HKEY_CLASSES_ROOT;
  if ( ((unsigned __int64)(hKey + 0x20000000) <= 7 && (v6 = 239, _bittest64(&v6, (unsigned __int64)(hKey + 0x20000000)))
     || hKey == HKEY_PERFORMANCE_TEXT
     || hKey == HKEY_PERFORMANCE_NLSTEXT)
    && (SecurityInformation & 8) != 0 )
  {
    v9 = (SecurityInformation & 7) != 0 ? 16908288 : 0x1000000;
    result = OpenPredefinedKeyForSpecialAccess(hKey, v9, &Handle);
    KeySecurity = result;
    if ( result )
      return result;
    hKeya = (HKEY)Handle;
  }
  else
  {
    hKeya = 0;
    KeySecurity = MapPredefinedHandleInternal(hKey, (HKEY *)&Handle, &v33, &v32);
    v9 = 0x2000000;
  }
  v10 = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  if ( KeySecurity )
    goto LABEL_39;
  if ( ((unsigned __int8)Handle & 1) != 0 || ((unsigned __int8)Handle & 2) == 0 && !v5 )
    goto LABEL_12;
  UserAndMachineClass = BaseRegGetUserAndMachineClass(0, Handle, v9, LengthNeeded, Size);
  if ( UserAndMachineClass < 0 )
  {
    KeySecurity = RtlNtStatusToDosError(UserAndMachineClass);
LABEL_39:
    v20 = hKeya;
    goto LABEL_32;
  }
  v7 = *(void **)LengthNeeded;
  if ( *(_QWORD *)LengthNeeded )
  {
    v23 = (void *)Size[0];
    if ( Size[0] )
    {
      v10 = (void *)Size[0];
      if ( *(HANDLE *)LengthNeeded != Handle )
        v10 = *(void **)LengthNeeded;
      *(_QWORD *)&DestinationString.Length = v10;
      if ( v5 )
        v23 = *(void **)LengthNeeded;
      Handle = v23;
    }
  }
LABEL_12:
  *(_QWORD *)Length = pSecurityDescriptor;
  v11 = v43;
  v12 = *v43;
  Length[2] = *v43;
  Length[3] = 0;
  v13 = Handle;
  if ( ((unsigned __int8)Handle & 1) != 0 )
  {
    if ( (unsigned __int8)IsBaseRegCloseKeyPresent(v7) )
    {
      *(_OWORD *)Size = 0;
      KeySecurity = SafeBaseRegGetKeySecurity(
                      (unsigned __int64)Handle & 0xFFFFFFFFFFFFFFFEuLL,
                      SecurityInformationa,
                      Length,
                      Size);
      v30 = KeySecurity;
      v20 = hKeya;
      if ( !KeySecurity )
      {
        if ( LODWORD(Size[1]) <= Length[2] && Size[0] )
          memcpy_0(*(void **)Length, (const void *)Size[0], LODWORD(Size[1]));
        else
          KeySecurity = 1783;
      }
      Length[2] = Size[1];
      if ( Size[0] && (unsigned __int8)IsBaseRegCloseKeyPresent(v24) )
        MIDL_user_free_Ext(Size[0]);
      if ( (!KeySecurity || KeySecurity == 234) && Length[2] > 0x7FFF0000
        || !KeySecurity && pSecurityDescriptor && !RtlValidSecurityDescriptor(pSecurityDescriptor) )
      {
        KeySecurity = 13;
        goto LABEL_32;
      }
      goto LABEL_31;
    }
  }
  else
  {
    LengthNeeded[0] = 0;
    v14 = 0;
    Size[0] = 0;
    v34[1] = 0;
    v38 = 0;
    if ( Handle != (HANDLE)-2147483644LL && Handle != (HANDLE)-2147483568LL && Handle != (HANDLE)-2147483552LL )
    {
      v15 = SecurityInformationa;
      goto LABEL_17;
    }
    DestinationString = 0;
    RtlInitUnicodeStringEx(
      &DestinationString,
      L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib");
    v34[0] = 48;
    v35 = 0;
    v37 = 64;
    p_DestinationString = &DestinationString;
    v39 = 0;
    v15 = SecurityInformationa;
    v25 = Wow64NtOpenKey((unsigned int)Size, (SecurityInformationa & 8 | 0x10) << 21, (unsigned int)v34, 0, 0);
    if ( v25 >= 0 )
    {
      v14 = (void *)Size[0];
      v13 = (HANDLE)Size[0];
      v12 = Length[2];
LABEL_17:
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      if ( !Heap )
      {
        KeySecurity = 14;
LABEL_28:
        if ( v14 )
          NtClose(v14);
        goto LABEL_30;
      }
      SecurityObject = NtQuerySecurityObject(v13, v15, Heap, Length[2], LengthNeeded);
      if ( SecurityObject < 0 )
        goto LABEL_24;
      if ( !RtlValidSecurityDescriptor(Heap) )
      {
        KeySecurity = 87;
        goto LABEL_25;
      }
      v18 = RtlLengthSecurityDescriptor(Heap);
      v19 = *(PVOID *)Length;
      if ( *(_QWORD *)Length )
      {
        if ( Length[2] >= v18 )
          goto LABEL_23;
      }
      else
      {
        v19 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
        *(_QWORD *)Length = v19;
        if ( v19 )
        {
          Length[2] = v18;
LABEL_23:
          Length[3] = v18;
          SecurityObject = RtlMakeSelfRelativeSD(Heap, v19, &Length[2]);
LABEL_24:
          KeySecurity = RtlNtStatusToDosError(SecurityObject);
LABEL_25:
          if ( KeySecurity )
          {
            Length[2] = LengthNeeded[0];
            Length[3] = 0;
          }
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
          goto LABEL_28;
        }
      }
      KeySecurity = 14;
      goto LABEL_25;
    }
    KeySecurity = RtlNtStatusToDosError(v25);
    *(_QWORD *)&Length[2] = 0;
  }
LABEL_30:
  v20 = hKeya;
LABEL_31:
  *v11 = Length[2];
LABEL_32:
  if ( v10 )
    NtClose(v10);
  if ( v20 )
    RegCloseKey(v20);
  CLOSE_LOCAL_HANDLE_INTERNAL(v33, v32);
  return KeySecurity;
}

```

## disassembly

```asm
0x1800d9710  mov     r11, rsp
0x1800d9713  mov     [r11+20h], r9
0x1800d9717  mov     [r11+18h], r8
0x1800d971b  mov     [rsp+SecurityInformation], edx
0x1800d971f  mov     [r11+8], rcx
0x1800d9723  push    rbx
0x1800d9724  push    rsi
0x1800d9725  push    rdi
0x1800d9726  push    r12
0x1800d9728  push    r13
0x1800d972a  push    r14
0x1800d972c  push    r15
0x1800d972e  sub     rsp, 0C0h
0x1800d9735  mov     rax, r9
0x1800d9738  mov     r14, r8
0x1800d973b  xorps   xmm0, xmm0
0x1800d973e  movups  xmmword ptr [rsp+0F8h+Length], xmm0
0x1800d9743  xor     ebx, ebx
0x1800d9745  mov     qword ptr [rsp+0F8h+var_A0], rbx
0x1800d974a  mov     [rsp+0F8h+Size], rbx
0x1800d974f  mov     [r11-78h], rbx
0x1800d9753  mov     [r11-80h], rbx
0x1800d9757  cmp     rcx, 0FFFFFFFF80000004h
0x1800d975e  jz      loc_1800D9AC0
0x1800d9764  test    rax, rax
0x1800d9767  jz      loc_1800D99DF
0x1800d976d  mov     r13d, ebx
0x1800d9770  lea     eax, [rbx+1]
0x1800d9773  cmp     rcx, 0FFFFFFFF80000000h
0x1800d977a  cmovz   r13d, eax
0x1800d977e  mov     eax, 80000000h
0x1800d9783  add     rax, rcx
0x1800d9786  cmp     rax, 7
0x1800d978a  ja      short loc_1800D979C
0x1800d978c  mov     r8d, 0EFh
0x1800d9792  bt      r8, rax
0x1800d9796  jb      loc_1800D99E6
0x1800d979c  cmp     rcx, 0FFFFFFFF80000050h
0x1800d97a3  jz      loc_1800D99E6
0x1800d97a9  cmp     rcx, 0FFFFFFFF80000060h
0x1800d97b0  jz      loc_1800D99E6
0x1800d97b6  mov     [rsp+0F8h+hKey], rbx
0x1800d97bb  lea     r9, [rsp+0F8h+var_80]
0x1800d97c0  lea     r8, [rsp+0F8h+var_78]
0x1800d97c8  lea     rdx, [rsp+0F8h+Handle]
0x1800d97d0  call    MapPredefinedHandleInternal
0x1800d97d5  mov     edi, eax
0x1800d97d7  mov     r15d, 2000000h
0x1800d97dd  mov     r12, rbx
0x1800d97e0  mov     qword ptr [rsp+0F8h+DestinationString.Length], rbx
0x1800d97e5  test    edi, edi
0x1800d97e7  jnz     loc_1800D99BA
0x1800d97ed  mov     rsi, [rsp+0F8h+Handle]
0x1800d97f5  test    sil, 1
0x1800d97f9  jnz     short loc_1800D980E
0x1800d97fb  test    sil, 2
0x1800d97ff  jnz     loc_1800D9A53
0x1800d9805  test    r13d, r13d
0x1800d9808  jnz     loc_1800D9A53
0x1800d980e  mov     qword ptr [rsp+0F8h+Length], r14
0x1800d9813  mov     r13, [rsp+0F8h+arg_18]
0x1800d981b  mov     eax, [r13+0]
0x1800d981f  mov     [rsp+0F8h+Length+8], eax
0x1800d9823  mov     [rsp+0F8h+Length+0Ch], ebx
0x1800d9827  mov     rsi, [rsp+0F8h+Handle]
0x1800d982f  test    sil, 1
0x1800d9833  jnz     loc_1800D9ACA
0x1800d9839  mov     [rsp+0F8h+var_A0], ebx
0x1800d983d  mov     r15, rbx
0x1800d9840  mov     [rsp+0F8h+Size], rbx
0x1800d9845  mov     [rsp+0F8h+var_6C], ebx
0x1800d984c  mov     [rsp+0F8h+var_54], ebx
0x1800d9853  cmp     rsi, 0FFFFFFFF80000004h
0x1800d985a  jz      loc_180193E34
0x1800d9860  cmp     rsi, 0FFFFFFFF80000050h
0x1800d9867  jz      loc_180193E34
0x1800d986d  cmp     rsi, 0FFFFFFFF80000060h
0x1800d9874  jz      loc_180193E34
0x1800d987a  mov     edi, [rsp+0F8h+SecurityInformation]
0x1800d9881  mov     r8d, eax; Size
0x1800d9884  mov     rcx, gs:60h
0x1800d988d  xor     edx, edx; Flags
0x1800d988f  mov     rcx, [rcx+30h]; HeapHandle
0x1800d9893  call    cs:__imp_RtlAllocateHeap
0x1800d9899  mov     r14, rax
0x1800d989c  test    rax, rax
0x1800d989f  jz      loc_1800D9A2E
0x1800d98a5  lea     rax, [rsp+0F8h+var_A0]
0x1800d98aa  mov     [rsp+0F8h+LengthNeeded], rax; LengthNeeded
0x1800d98af  mov     r9d, [rsp+0F8h+Length+8]; Length
0x1800d98b4  mov     r8, r14; SecurityDescriptor
0x1800d98b7  mov     edx, edi; SecurityInformation
0x1800d98b9  mov     rcx, rsi; Handle
0x1800d98bc  call    cs:__imp_NtQuerySecurityObject
0x1800d98c2  test    eax, eax
0x1800d98c4  js      short loc_1800D992F
0x1800d98c6  mov     rcx, r14; SecurityDescriptor
0x1800d98c9  call    cs:__imp_RtlValidSecurityDescriptor
0x1800d98cf  test    al, al
0x1800d98d1  jz      loc_1800D99C1
0x1800d98d7  mov     rcx, r14; SecurityDescriptor
0x1800d98da  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800d98e0  mov     edi, eax
0x1800d98e2  mov     rax, qword ptr [rsp+0F8h+Length]
0x1800d98e7  test    rax, rax
0x1800d98ea  jnz     loc_1800D99CB
0x1800d98f0  mov     r8d, edi; Size
0x1800d98f3  mov     rcx, gs:60h
0x1800d98fc  xor     edx, edx; Flags
0x1800d98fe  mov     rcx, [rcx+30h]; HeapHandle
0x1800d9902  call    cs:__imp_RtlAllocateHeap
0x1800d9908  mov     qword ptr [rsp+0F8h+Length], rax
0x1800d990d  test    rax, rax
0x1800d9910  jz      loc_1800D99D5
0x1800d9916  mov     [rsp+0F8h+Length+8], edi
0x1800d991a  mov     [rsp+0F8h+Length+0Ch], edi
0x1800d991e  lea     r8, [rsp+0F8h+Length+8]; BufferLength
0x1800d9923  mov     rdx, rax; SelfRelativeSD
0x1800d9926  mov     rcx, r14; AbsoluteSD
0x1800d9929  call    cs:__imp_RtlMakeSelfRelativeSD
0x1800d992f  mov     ecx, eax; Status
0x1800d9931  call    cs:__imp_RtlNtStatusToDosError
0x1800d9937  mov     edi, eax
0x1800d9939  test    edi, edi
0x1800d993b  jz      short loc_1800D9949
0x1800d993d  mov     eax, [rsp+0F8h+var_A0]
0x1800d9941  mov     [rsp+0F8h+Length+8], eax
0x1800d9945  mov     [rsp+0F8h+Length+0Ch], ebx
0x1800d9949  mov     rcx, gs:60h
0x1800d9952  mov     r8, r14; P
0x1800d9955  xor     edx, edx; Flags
0x1800d9957  mov     rcx, [rcx+30h]; HeapHandle
0x1800d995b  call    cs:__imp_RtlFreeHeap
0x1800d9961  test    r15, r15
0x1800d9964  jnz     loc_1800D9BC4
0x1800d996a  mov     rsi, [rsp+0F8h+hKey]
0x1800d996f  mov     eax, [rsp+0F8h+Length+8]
0x1800d9973  mov     [r13+0], eax
0x1800d9977  test    r12, r12
0x1800d997a  jnz     loc_1800D9A45
0x1800d9980  test    rsi, rsi
0x1800d9983  jnz     loc_1800D9A38
0x1800d9989  mov     rdx, [rsp+0F8h+var_80]
0x1800d998e  mov     rcx, [rsp+0F8h+var_78]
0x1800d9996  call    CLOSE_LOCAL_HANDLE_INTERNAL
0x1800d999b  mov     eax, edi
0x1800d999d  add     rsp, 0C0h
0x1800d99a4  pop     r15
0x1800d99a6  pop     r14
0x1800d99a8  pop     r13
0x1800d99aa  pop     r12
0x1800d99ac  pop     rdi
0x1800d99ad  pop     rsi
0x1800d99ae  pop     rbx
0x1800d99af  retn
0x1800d99b0  mov     ecx, eax; Status
0x1800d99b2  call    cs:__imp_RtlNtStatusToDosError
0x1800d99b8  mov     edi, eax
0x1800d99ba  mov     rsi, [rsp+0F8h+hKey]
0x1800d99bf  jmp     short loc_1800D9977
0x1800d99c1  mov     edi, 57h ; 'W'
0x1800d99c6  jmp     loc_1800D9939
0x1800d99cb  cmp     [rsp+0F8h+Length+8], edi
0x1800d99cf  jnb     loc_1800D991A
0x1800d99d5  mov     edi, 0Eh
0x1800d99da  jmp     loc_1800D9939
0x1800d99df  mov     eax, 57h ; 'W'
0x1800d99e4  jmp     short loc_1800D999D
0x1800d99e6  test    dl, 8
0x1800d99e9  jz      loc_1800D97B6
0x1800d99ef  mov     eax, edx
0x1800d99f1  and     al, 7
0x1800d99f3  neg     al
0x1800d99f5  sbb     r15d, r15d
0x1800d99f8  and     r15d, 20000h
0x1800d99ff  add     r15d, 1000000h
0x1800d9a06  lea     r8, [rsp+0F8h+Handle]
0x1800d9a0e  mov     edx, r15d
0x1800d9a11  call    OpenPredefinedKeyForSpecialAccess
0x1800d9a16  mov     edi, eax
0x1800d9a18  test    eax, eax
0x1800d9a1a  jnz     short loc_1800D999D
0x1800d9a1c  mov     rsi, [rsp+0F8h+Handle]
0x1800d9a24  mov     [rsp+0F8h+hKey], rsi
0x1800d9a29  jmp     loc_1800D97DD
0x1800d9a2e  mov     edi, 0Eh
0x1800d9a33  jmp     loc_1800D9961
0x1800d9a38  mov     rcx, rsi; hKey
0x1800d9a3b  call    RegCloseKey
0x1800d9a40  jmp     loc_1800D9989
0x1800d9a45  mov     rcx, r12; Handle
0x1800d9a48  call    cs:__imp_NtClose
0x1800d9a4e  jmp     loc_1800D9980
0x1800d9a53  lea     rax, [rsp+0F8h+Size]
0x1800d9a58  mov     [rsp+0F8h+LengthNeeded], rax
0x1800d9a5d  lea     r9, [rsp+0F8h+var_A0]
0x1800d9a62  mov     r8d, r15d
0x1800d9a65  mov     rdx, [rsp+0F8h+Handle]
0x1800d9a6d  xor     ecx, ecx
0x1800d9a6f  call    BaseRegGetUserAndMachineClass
0x1800d9a74  test    eax, eax
0x1800d9a76  js      loc_1800D99B0
0x1800d9a7c  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x1800d9a81  test    rcx, rcx
0x1800d9a84  jz      loc_1800D980E
0x1800d9a8a  mov     rax, [rsp+0F8h+Size]
0x1800d9a8f  test    rax, rax
0x1800d9a92  jz      loc_1800D980E
0x1800d9a98  mov     r12, rax
0x1800d9a9b  cmp     rcx, [rsp+0F8h+Handle]
0x1800d9aa3  cmovnz  r12, rcx
0x1800d9aa7  mov     qword ptr [rsp+0F8h+DestinationString.Length], r12
0x1800d9aac  test    r13d, r13d
0x1800d9aaf  cmovnz  rax, rcx
0x1800d9ab3  mov     [rsp+0F8h+Handle], rax
0x1800d9abb  jmp     loc_1800D980E
0x1800d9ac0  mov     eax, 6
0x1800d9ac5  jmp     loc_1800D999D
0x1800d9aca  call    IsBaseRegCloseKeyPresent
0x1800d9acf  test    al, al
0x1800d9ad1  jz      loc_1800D996A
0x1800d9ad7  xorps   xmm0, xmm0
0x1800d9ada  movups  xmmword ptr [rsp+0F8h+Size], xmm0
0x1800d9adf  mov     rcx, [rsp+0F8h+Handle]
0x1800d9ae7  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800d9aeb  lea     r9, [rsp+0F8h+Size]
0x1800d9af0  lea     r8, [rsp+0F8h+Length]
0x1800d9af5  mov     edx, [rsp+0F8h+SecurityInformation]
0x1800d9afc  call    cs:__imp_SafeBaseRegGetKeySecurity
0x1800d9b02  mov     edi, eax
0x1800d9b04  mov     [rsp+0F8h+var_98], eax
0x1800d9b08  mov     rsi, [rsp+0F8h+hKey]
0x1800d9b0d  jmp     short loc_1800D9B31
0x1800d9b0f  mov     edi, eax
0x1800d9b11  mov     [rsp+0F8h+var_98], eax
0x1800d9b15  xor     ebx, ebx
0x1800d9b17  mov     r14, [rsp+0F8h+arg_10]
0x1800d9b1f  mov     rsi, [rsp+0F8h+hKey]
0x1800d9b24  mov     r12, qword ptr [rsp+0F8h+DestinationString.Length]
0x1800d9b29  mov     r13, [rsp+0F8h+arg_18]
0x1800d9b31  test    edi, edi
0x1800d9b33  jnz     short loc_1800D9B56
0x1800d9b35  mov     eax, dword ptr [rsp+0F8h+Size+8]
0x1800d9b39  cmp     eax, [rsp+0F8h+Length+8]
0x1800d9b3d  ja      short loc_1800D9BA9
0x1800d9b3f  mov     rdx, [rsp+0F8h+Size]; Src
0x1800d9b44  test    rdx, rdx
0x1800d9b47  jz      short loc_1800D9BA9
0x1800d9b49  mov     r8d, eax; Size
0x1800d9b4c  mov     rcx, qword ptr [rsp+0F8h+Length]; void *
0x1800d9b51  call    memcpy_0
0x1800d9b56  mov     eax, dword ptr [rsp+0F8h+Size+8]
0x1800d9b5a  mov     [rsp+0F8h+Length+8], eax
0x1800d9b5e  cmp     [rsp+0F8h+Size], rbx
0x1800d9b63  jz      short loc_1800D9B79
0x1800d9b65  call    IsBaseRegCloseKeyPresent
0x1800d9b6a  test    al, al
0x1800d9b6c  jz      short loc_1800D9B79
0x1800d9b6e  mov     rcx, [rsp+0F8h+Size]
0x1800d9b73  call    cs:__imp_MIDL_user_free_Ext
0x1800d9b79  test    edi, edi
0x1800d9b7b  jz      short loc_1800D9BB0
0x1800d9b7d  cmp     edi, 0EAh
0x1800d9b83  jz      short loc_1800D9BB0
0x1800d9b85  test    edi, edi
0x1800d9b87  jnz     loc_1800D996F
0x1800d9b8d  test    r14, r14
0x1800d9b90  jz      loc_1800D996F
0x1800d9b96  mov     rcx, r14; SecurityDescriptor
0x1800d9b99  call    cs:__imp_RtlValidSecurityDescriptor
0x1800d9b9f  test    al, al
0x1800d9ba1  jnz     loc_1800D996F
0x1800d9ba7  jmp     short loc_1800D9BBA
0x1800d9ba9  mov     edi, 6F7h
0x1800d9bae  jmp     short loc_1800D9B56
0x1800d9bb0  cmp     [rsp+0F8h+Length+8], 7FFF0000h
0x1800d9bb8  jbe     short loc_1800D9B85
0x1800d9bba  mov     edi, 0Dh
0x1800d9bbf  jmp     loc_1800D9977
0x1800d9bc4  mov     rcx, r15; Handle
0x1800d9bc7  call    cs:__imp_NtClose
0x1800d9bcd  jmp     loc_1800D996A
0x180193e34  xorps   xmm0, xmm0
0x180193e37  movups  xmmword ptr [rsp+0F8h+DestinationString.Length], xmm0
0x180193e3c  lea     rdx, aRegistryMachin_34; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180193e43  lea     rcx, [rsp+0F8h+DestinationString]; DestinationString
0x180193e48  call    cs:__imp_RtlInitUnicodeStringEx
0x180193e4e  mov     [rsp+0F8h+var_70], 30h ; '0'
0x180193e59  mov     [rsp+0F8h+var_68], rbx
0x180193e61  mov     [rsp+0F8h+var_58], 40h ; '@'
0x180193e6c  lea     rax, [rsp+0F8h+DestinationString]
0x180193e71  mov     [rsp+0F8h+var_60], rax
0x180193e79  xorps   xmm0, xmm0
0x180193e7c  movdqu  [rsp+0F8h+var_50], xmm0
0x180193e85  mov     edi, [rsp+0F8h+SecurityInformation]
0x180193e8c  mov     edx, edi
0x180193e8e  and     edx, 8
0x180193e91  or      edx, 10h
0x180193e94  shl     edx, 15h
0x180193e97  mov     [rsp+0F8h+LengthNeeded], rbx
  ... truncated ...
```
