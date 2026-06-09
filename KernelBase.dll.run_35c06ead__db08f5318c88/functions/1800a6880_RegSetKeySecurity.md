# RegSetKeySecurity

- ea: `0x1800a6880`
- end: `0x1800a6e28`
- name: `RegSetKeySecurity`
- size: `1448`
- prototype: `LSTATUS __stdcall(HKEY hKey, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180051660`
- `0x1800a5dec`

## callees

- `0x180049440`
- `0x18005b460`
- `0x18005bb80`
- `0x18005cf00`
- `0x18005d6f0`
- `0x18005dd30`
- `0x1800a6880`
- `0x1800a6e30`
- `0x1800a6e58`
- `0x18012d119`
- `0x18012d578`
- `0x18012ffa4`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800a6a2b`
- `ntdll!RtlNtStatusToDosError` at `0x1800a6ab4`
- `ntdll!RtlNtStatusToDosError` at `0x1800a6d83`
- `ntdll!RtlNtStatusToDosError` at `0x1800a6a2b`
- `ntdll!RtlNtStatusToDosError` at `0x1800a6ab4`
- `ntdll!RtlNtStatusToDosError` at `0x1800a6d83`
- `ntdll!NtClose` at `0x1800a6e13`
- `ntdll!NtClose` at `0x1800a6e13`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800a6cf0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800a6cf0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800a6d1c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800a6d1c`
- `ntdll!RtlValidSecurityDescriptor` at `0x1800a69c3`
- `ntdll!RtlValidSecurityDescriptor` at `0x1800a69c3`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800a69d4`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800a69d4`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800a6a23`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800a6a23`
- `ntdll!NtSetSecurityObject` at `0x1800a6aa2`
- `ntdll!NtSetSecurityObject` at `0x1800a6aa2`
- `ntdll!RtlFreeHeap` at `0x1800a6ad0`
- `ntdll!RtlFreeHeap` at `0x1800a6dfb`
- `ntdll!RtlFreeHeap` at `0x1800a6ad0`
- `ntdll!RtlFreeHeap` at `0x1800a6dfb`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800a6a89`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800a6a89`
- `ntdll!RtlAllocateHeap` at `0x1800a69fc`
- `ntdll!RtlAllocateHeap` at `0x1800a69fc`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegSetKeySecurity` at `0x1800a6c94`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegSetKeySecurity` at `0x1800a6c94`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvSetKeySecurity` at `0x1800a6d58`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvSetKeySecurity` at `0x1800a6d58`

## pseudocode

```c
LSTATUS __stdcall RegSetKeySecurity(
        HKEY hKey,
        SECURITY_INFORMATION SecurityInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  HKEY *v6; // rbx
  HKEY v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // r13d
  int v10; // eax
  LSTATUS result; // eax
  ULONG v12; // esi
  HANDLE v13; // r12
  void *v14; // r12
  ULONG v15; // edi
  PVOID Heap; // rax
  NTSTATUS SelfRelativeSD; // eax
  HANDLE v18; // rdi
  int v19; // esi
  __int64 v20; // rdi
  NTSTATUS KeySemantics; // eax
  int v22; // eax
  void **v23; // rcx
  void *v24; // rax
  _QWORD *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // r8
  HANDLE Handle; // [rsp+40h] [rbp-258h] BYREF
  ULONG BufferLength[4]; // [rsp+48h] [rbp-250h] BYREF
  HANDLE v32; // [rsp+58h] [rbp-240h] BYREF
  HKEY hKeya; // [rsp+60h] [rbp-238h] BYREF
  ULONG v34; // [rsp+68h] [rbp-230h]
  HANDLE v35; // [rsp+70h] [rbp-228h] BYREF
  void *v36; // [rsp+78h] [rbp-220h]
  HKEY v37; // [rsp+80h] [rbp-218h] BYREF
  __int64 v38; // [rsp+88h] [rbp-210h] BYREF
  int v39; // [rsp+90h] [rbp-208h] BYREF
  __int64 v40; // [rsp+94h] [rbp-204h]
  int v41; // [rsp+9Ch] [rbp-1FCh]
  PVOID P; // [rsp+A0h] [rbp-1F8h]
  UNICODE_STRING Source; // [rsp+A8h] [rbp-1F0h] BYREF
  _BYTE v44[400]; // [rsp+C0h] [rbp-1D8h] BYREF

  Handle = hKey;
  *(_OWORD *)BufferLength = 0;
  v6 = 0;
  v37 = 0;
  v38 = 0;
  if ( hKey == HKEY_PERFORMANCE_DATA )
    return 6;
  v7 = hKey + 0x20000000;
  v8 = 239;
  if ( ((unsigned __int64)v7 > 7 || !_bittest64(&v8, (unsigned __int64)v7))
    && hKey != HKEY_PERFORMANCE_TEXT
    && hKey != HKEY_PERFORMANCE_NLSTEXT
    || (SecurityInformation & 8) == 0 )
  {
    hKeya = 0;
    v12 = MapPredefinedHandleInternal(hKey, &Handle, &v37, &v38);
    v9 = 0x2000000;
    v13 = Handle;
LABEL_14:
    if ( !v12 )
    {
      v36 = 0;
      if ( ((unsigned __int8)v13 & 1) != 0 || ((unsigned __int8)v13 & 2) == 0 && hKey != HKEY_CLASSES_ROOT )
        goto LABEL_16;
      v40 = 0;
      Source = 0;
      memset_0(v44, 0, 0x18Au);
      v32 = 0;
      v35 = 0;
      P = v44;
      v41 = 394;
      v39 = 0;
      KeySemantics = BaseRegGetKeySemantics(v13, &Source);
      if ( KeySemantics >= 0 )
      {
        if ( (v39 & 2) != 0 )
        {
          v32 = v13;
          v22 = 2;
          v23 = &v35;
        }
        else
        {
          v35 = v13;
          v22 = 1;
          v23 = &v32;
        }
        BaseRegOpenClassKeyFromLocation(&v39, v13, &Source, v9 & 0x1000300 | 0x2000000, v22, 0, v23, 0);
        if ( (v39 & 0x20) != 0 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        if ( v32 )
        {
          v24 = v35;
          if ( v35 )
          {
            v14 = v35;
            if ( v32 != Handle )
              v14 = v32;
            v36 = v14;
            if ( hKey == HKEY_CLASSES_ROOT )
              v24 = v32;
            Handle = v24;
LABEL_17:
            *(_QWORD *)BufferLength = 0;
            if ( !RtlValidSecurityDescriptor(pSecurityDescriptor) )
            {
              v12 = 87;
              goto LABEL_22;
            }
            v15 = RtlLengthSecurityDescriptor(pSecurityDescriptor);
            Heap = *(PVOID *)BufferLength;
            if ( *(_QWORD *)BufferLength )
            {
              if ( BufferLength[2] >= v15 )
                goto LABEL_21;
              v12 = 14;
            }
            else
            {
              Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
              *(_QWORD *)BufferLength = Heap;
              if ( Heap )
              {
                BufferLength[2] = v15;
LABEL_21:
                BufferLength[3] = v15;
                SelfRelativeSD = RtlMakeSelfRelativeSD(pSecurityDescriptor, Heap, &BufferLength[2]);
                v12 = RtlNtStatusToDosError(SelfRelativeSD);
LABEL_22:
                Heap = *(PVOID *)BufferLength;
                goto LABEL_23;
              }
              v12 = 14;
            }
LABEL_23:
            if ( !v12 )
            {
              v18 = Handle;
              if ( ((unsigned __int8)Handle & 1) != 0 )
              {
                if ( (unsigned __int8)IsBaseRegCloseKeyPresent() )
                {
                  v12 = BaseRegSetKeySecurity(
                          (unsigned __int64)Handle & 0xFFFFFFFFFFFFFFFEuLL,
                          SecurityInformation,
                          BufferLength);
                  v34 = v12;
                }
              }
              else if ( Heap )
              {
                if ( Handle == (HANDLE)-2147483644LL
                  || Handle == (HANDLE)-2147483568LL
                  || Handle == (HANDLE)-2147483552LL )
                {
                  v19 = -1073741816;
                }
                else
                {
                  if ( RtlValidRelativeSecurityDescriptor(Heap, BufferLength[2], SecurityInformation) )
                    v19 = NtSetSecurityObject(v18, SecurityInformation, *(PSECURITY_DESCRIPTOR *)BufferLength);
                  else
                    v19 = -1073741811;
                  if ( v19 >= 0 && (unsigned __int8)IsTermsrvDeleteKeyPresent() )
                    TermsrvSetKeySecurity(v18, SecurityInformation, *(_QWORD *)BufferLength);
                }
                v12 = RtlNtStatusToDosError(v19);
              }
              else
              {
                v12 = 87;
              }
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)BufferLength);
              if ( v14 )
                NtClose(v14);
            }
            goto LABEL_35;
          }
        }
LABEL_16:
        v14 = 0;
        goto LABEL_17;
      }
      v12 = RtlNtStatusToDosError(KeySemantics);
    }
LABEL_35:
    if ( hKeya )
      RegCloseKey(hKeya);
    hKeya = v37;
    v20 = v38;
    if ( v37 )
      BaseRegCloseKeyInternal(&hKeya);
    if ( v20 )
    {
      RtlAcquireSRWLockExclusive(PredefinedHandleTableSRWLock);
      if ( (*(_DWORD *)(v20 + 8))-- == 1 )
      {
        v26 = *(_QWORD **)(v20 + 16);
        v27 = v26[1];
        if ( v20 != v27 || *(_QWORD *)v20 != *v26 )
        {
          v6 = (HKEY *)v20;
          v28 = RemoveUnitFromList(v27, v20, *(_QWORD *)(v20 + 16));
          *(_QWORD *)(v29 + 8) = v28;
        }
      }
      RtlReleaseSRWLockExclusive(PredefinedHandleTableSRWLock);
      if ( v6 )
      {
        RegCloseKey(*v6);
        FreeEnvironmentStringsW((LPWCH)v6);
      }
    }
    return v12;
  }
  if ( (SecurityInformation & 4) != 0 )
  {
    v9 = 50593792;
  }
  else
  {
    v9 = 50331648;
    if ( (SecurityInformation & 1) != 0 )
      v9 = 50855936;
  }
  if ( ((unsigned __int64)(hKey + 0x20000000) > 7 || !_bittest64(&v8, (unsigned __int64)(hKey + 0x20000000)))
    && hKey != HKEY_PERFORMANCE_TEXT
    && hKey != HKEY_PERFORMANCE_NLSTEXT )
  {
    return 1010;
  }
  v10 = MapPredefinedRegistryHandleToIndex((unsigned int)hKey);
  result = ((__int64 (__fastcall *)(_QWORD, _QWORD, HANDLE *))*(&off_18039C1E0 + 4 * v10))(0, v9, &Handle);
  if ( !result )
  {
    v12 = 0;
    v13 = Handle;
    hKeya = (HKEY)Handle;
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x1800a6880  push    rbx
0x1800a6882  push    rsi
0x1800a6883  push    rdi
0x1800a6884  push    r12
0x1800a6886  push    r13
0x1800a6888  push    r14
0x1800a688a  push    r15
0x1800a688c  sub     rsp, 260h
0x1800a6893  mov     rax, cs:__security_cookie
0x1800a689a  xor     rax, rsp
0x1800a689d  mov     [rsp+298h+var_48], rax
0x1800a68a5  mov     r14, r8
0x1800a68a8  mov     r15d, edx
0x1800a68ab  mov     rdi, rcx
0x1800a68ae  mov     [rsp+298h+Handle], rcx
0x1800a68b3  xorps   xmm0, xmm0
0x1800a68b6  movups  xmmword ptr [rsp+298h+BufferLength], xmm0
0x1800a68bb  xor     ebx, ebx
0x1800a68bd  mov     [rsp+298h+var_218], rbx
0x1800a68c5  mov     [rsp+298h+var_210], rbx
0x1800a68cd  cmp     rcx, 0FFFFFFFF80000004h
0x1800a68d4  jz      loc_1800A6C6C
0x1800a68da  mov     edx, 80000000h
0x1800a68df  lea     rax, [rcx+rdx]
0x1800a68e3  mov     ecx, 0EFh
0x1800a68e8  cmp     rax, 7
0x1800a68ec  ja      short loc_1800A6960
0x1800a68ee  bt      rcx, rax
0x1800a68f2  jnb     short loc_1800A6960
0x1800a68f4  test    r15b, 8
0x1800a68f8  jz      short loc_1800A6972
0x1800a68fa  test    r15b, 4
0x1800a68fe  jz      loc_1800A6DA8
0x1800a6904  mov     r13d, 3040000h
0x1800a690a  lea     rax, [rdi+rdx]
0x1800a690e  cmp     rax, 7
0x1800a6912  ja      loc_1800A6DC0
0x1800a6918  bt      rcx, rax
0x1800a691c  jnb     loc_1800A6DC0
0x1800a6922  mov     ecx, edi
0x1800a6924  call    MapPredefinedRegistryHandleToIndex
0x1800a6929  movsxd  rcx, eax
0x1800a692c  shl     rcx, 5
0x1800a6930  lea     rax, off_18039C1E0
0x1800a6937  mov     rax, [rcx+rax]
0x1800a693b  lea     r8, [rsp+298h+Handle]
0x1800a6940  mov     edx, r13d
0x1800a6943  xor     ecx, ecx
0x1800a6945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a694a  test    eax, eax
0x1800a694c  jnz     loc_1800A6B1C
0x1800a6952  mov     esi, ebx
0x1800a6954  mov     r12, [rsp+298h+Handle]
0x1800a6959  mov     [rsp+298h+hKey], r12
0x1800a695e  jmp     short loc_1800A69A1
0x1800a6960  cmp     rdi, 0FFFFFFFF80000050h
0x1800a6967  jz      short loc_1800A68F4
0x1800a6969  cmp     rdi, 0FFFFFFFF80000060h
0x1800a6970  jz      short loc_1800A68F4
0x1800a6972  mov     [rsp+298h+hKey], rbx
0x1800a6977  lea     r9, [rsp+298h+var_210]
0x1800a697f  lea     r8, [rsp+298h+var_218]
0x1800a6987  lea     rdx, [rsp+298h+Handle]
0x1800a698c  mov     rcx, rdi
0x1800a698f  call    MapPredefinedHandleInternal
0x1800a6994  mov     esi, eax
0x1800a6996  mov     r13d, 2000000h
0x1800a699c  mov     r12, [rsp+298h+Handle]
0x1800a69a1  test    esi, esi
0x1800a69a3  jnz     loc_1800A6ADF
0x1800a69a9  mov     [rsp+298h+var_220], rbx
0x1800a69ae  test    r12b, 1
0x1800a69b2  jz      loc_1800A6B3F
0x1800a69b8  mov     r12, rbx
0x1800a69bb  mov     qword ptr [rsp+298h+BufferLength], rbx
0x1800a69c0  mov     rcx, r14; SecurityDescriptor
0x1800a69c3  call    cs:__imp_RtlValidSecurityDescriptor
0x1800a69c9  test    al, al
0x1800a69cb  jz      loc_1800A6CB7
0x1800a69d1  mov     rcx, r14; SecurityDescriptor
0x1800a69d4  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800a69da  mov     edi, eax
0x1800a69dc  mov     rax, qword ptr [rsp+298h+BufferLength]
0x1800a69e1  test    rax, rax
0x1800a69e4  jnz     loc_1800A6CD5
0x1800a69ea  mov     r8d, edi; Size
0x1800a69ed  mov     rcx, gs:60h
0x1800a69f6  xor     edx, edx; Flags
0x1800a69f8  mov     rcx, [rcx+30h]; HeapHandle
0x1800a69fc  call    cs:__imp_RtlAllocateHeap
0x1800a6a02  mov     qword ptr [rsp+298h+BufferLength], rax
0x1800a6a07  test    rax, rax
0x1800a6a0a  jz      loc_1800A6D77
0x1800a6a10  mov     [rsp+298h+BufferLength+8], edi
0x1800a6a14  mov     [rsp+298h+BufferLength+0Ch], edi
0x1800a6a18  lea     r8, [rsp+298h+BufferLength+8]; BufferLength
0x1800a6a1d  mov     rdx, rax; SelfRelativeSD
0x1800a6a20  mov     rcx, r14; AbsoluteSD
0x1800a6a23  call    cs:__imp_RtlMakeSelfRelativeSD
0x1800a6a29  mov     ecx, eax; Status
0x1800a6a2b  call    cs:__imp_RtlNtStatusToDosError
0x1800a6a31  mov     esi, eax
0x1800a6a33  mov     rax, qword ptr [rsp+298h+BufferLength]
0x1800a6a38  test    esi, esi
0x1800a6a3a  jnz     loc_1800A6ADF
0x1800a6a40  mov     rdi, [rsp+298h+Handle]
0x1800a6a45  test    dil, 1
0x1800a6a49  jnz     loc_1800A6C76
0x1800a6a4f  test    rax, rax
0x1800a6a52  jz      loc_1800A6E06
0x1800a6a58  cmp     rdi, 0FFFFFFFF80000004h
0x1800a6a5f  jz      loc_1800A6CCB
0x1800a6a65  cmp     rdi, 0FFFFFFFF80000050h
0x1800a6a6c  jz      loc_1800A6CCB
0x1800a6a72  cmp     rdi, 0FFFFFFFF80000060h
0x1800a6a79  jz      loc_1800A6CCB
0x1800a6a7f  mov     r8d, r15d; RequiredInformation
0x1800a6a82  mov     edx, [rsp+298h+BufferLength+8]; SecurityDescriptorLength
0x1800a6a86  mov     rcx, rax; SecurityDescriptorInput
0x1800a6a89  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1800a6a8f  test    al, al
0x1800a6a91  jz      loc_1800A6CC1
0x1800a6a97  mov     r8, qword ptr [rsp+298h+BufferLength]; SecurityDescriptor
0x1800a6a9c  mov     edx, r15d; SecurityInformation
0x1800a6a9f  mov     rcx, rdi; Handle
0x1800a6aa2  call    cs:__imp_NtSetSecurityObject
0x1800a6aa8  mov     esi, eax
0x1800a6aaa  test    esi, esi
0x1800a6aac  jns     loc_1800A6D40
0x1800a6ab2  mov     ecx, esi; Status
0x1800a6ab4  call    cs:__imp_RtlNtStatusToDosError
0x1800a6aba  mov     esi, eax
0x1800a6abc  mov     rcx, gs:60h
0x1800a6ac5  mov     r8, qword ptr [rsp+298h+BufferLength]; P
0x1800a6aca  xor     edx, edx; Flags
0x1800a6acc  mov     rcx, [rcx+30h]; HeapHandle
0x1800a6ad0  call    cs:__imp_RtlFreeHeap
0x1800a6ad6  test    r12, r12
0x1800a6ad9  jnz     loc_1800A6E10
0x1800a6adf  mov     rcx, [rsp+298h+hKey]; hKey
0x1800a6ae4  test    rcx, rcx
0x1800a6ae7  jnz     loc_1800A6E1E
0x1800a6aed  mov     rax, [rsp+298h+var_218]
0x1800a6af5  mov     [rsp+298h+hKey], rax
0x1800a6afa  mov     rdi, [rsp+298h+var_210]
0x1800a6b02  test    rax, rax
0x1800a6b05  jz      short loc_1800A6B11
0x1800a6b07  lea     rcx, [rsp+298h+hKey]
0x1800a6b0c  call    BaseRegCloseKeyInternal
0x1800a6b11  test    rdi, rdi
0x1800a6b14  jnz     loc_1800A6CE9
0x1800a6b1a  mov     eax, esi
0x1800a6b1c  mov     rcx, [rsp+298h+var_48]
0x1800a6b24  xor     rcx, rsp; StackCookie
0x1800a6b27  call    __security_check_cookie
0x1800a6b2c  add     rsp, 260h
0x1800a6b33  pop     r15
0x1800a6b35  pop     r14
0x1800a6b37  pop     r13
0x1800a6b39  pop     r12
0x1800a6b3b  pop     rdi
0x1800a6b3c  pop     rsi
0x1800a6b3d  pop     rbx
0x1800a6b3e  retn
0x1800a6b3f  test    r12b, 2
0x1800a6b43  jnz     short loc_1800A6B52
0x1800a6b45  cmp     rdi, 0FFFFFFFF80000000h
0x1800a6b4c  jnz     loc_1800A69B8
0x1800a6b52  mov     [rsp+298h+var_204], rbx
0x1800a6b5a  xorps   xmm0, xmm0
0x1800a6b5d  movups  xmmword ptr [rsp+298h+Source.Length], xmm0
0x1800a6b65  xor     edx, edx; Val
0x1800a6b67  mov     r8d, 18Ah; Size
0x1800a6b6d  lea     rcx, [rsp+298h+var_1D8]; void *
0x1800a6b75  call    memset_0
0x1800a6b7a  mov     [rsp+298h+var_240], rbx
0x1800a6b7f  mov     [rsp+298h+var_228], rbx
0x1800a6b84  lea     rax, [rsp+298h+var_1D8]
0x1800a6b8c  mov     [rsp+298h+P], rax
0x1800a6b94  mov     [rsp+298h+var_1FC], 18Ah
0x1800a6b9f  mov     [rsp+298h+var_208], ebx
0x1800a6ba6  lea     r8, [rsp+298h+var_208]
0x1800a6bae  lea     rdx, [rsp+298h+Source]; Source
0x1800a6bb6  mov     rcx, r12; KeyHandle
0x1800a6bb9  call    BaseRegGetKeySemantics
0x1800a6bbe  test    eax, eax
0x1800a6bc0  js      loc_1800A6D81
0x1800a6bc6  test    byte ptr [rsp+298h+var_208], 2
0x1800a6bce  jz      loc_1800A6D63
0x1800a6bd4  mov     [rsp+298h+var_240], r12
0x1800a6bd9  mov     eax, 2
0x1800a6bde  lea     rcx, [rsp+298h+var_228]
0x1800a6be3  and     r13d, 1000300h
0x1800a6bea  bts     r13d, 19h
0x1800a6bef  mov     [rsp+298h+var_260], rbx
0x1800a6bf4  mov     [rsp+298h+var_268], rcx
0x1800a6bf9  mov     [rsp+298h+var_270], ebx
0x1800a6bfd  mov     [rsp+298h+var_278], eax
0x1800a6c01  mov     r9d, r13d
0x1800a6c04  lea     r8, [rsp+298h+Source]
0x1800a6c0c  mov     rdx, r12
0x1800a6c0f  lea     rcx, [rsp+298h+var_208]
0x1800a6c17  call    BaseRegOpenClassKeyFromLocation
0x1800a6c1c  test    byte ptr [rsp+298h+var_208], 20h
0x1800a6c24  jnz     loc_1800A6DE4
0x1800a6c2a  mov     rcx, [rsp+298h+var_240]
0x1800a6c2f  test    rcx, rcx
0x1800a6c32  jz      loc_1800A69B8
0x1800a6c38  mov     rax, [rsp+298h+var_228]
0x1800a6c3d  test    rax, rax
0x1800a6c40  jz      loc_1800A69B8
0x1800a6c46  mov     r12, rax
0x1800a6c49  cmp     rcx, [rsp+298h+Handle]
0x1800a6c4e  cmovnz  r12, rcx
0x1800a6c52  mov     [rsp+298h+var_220], r12
0x1800a6c57  cmp     rdi, 0FFFFFFFF80000000h
0x1800a6c5e  cmovz   rax, rcx
0x1800a6c62  mov     [rsp+298h+Handle], rax
0x1800a6c67  jmp     loc_1800A69BB
0x1800a6c6c  mov     eax, 6
0x1800a6c71  jmp     loc_1800A6B1C
0x1800a6c76  call    IsBaseRegCloseKeyPresent
0x1800a6c7b  test    al, al
0x1800a6c7d  jz      loc_1800A6ABC
0x1800a6c83  mov     rcx, [rsp+298h+Handle]
0x1800a6c88  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800a6c8c  lea     r8, [rsp+298h+BufferLength]
0x1800a6c91  mov     edx, r15d
0x1800a6c94  call    cs:__imp_BaseRegSetKeySecurity
0x1800a6c9a  mov     esi, eax
0x1800a6c9c  mov     [rsp+298h+var_230], eax
0x1800a6ca0  jmp     loc_1800A6ABC
0x1800a6ca5  mov     esi, eax
0x1800a6ca7  mov     [rsp+298h+var_230], eax
0x1800a6cab  xor     ebx, ebx
0x1800a6cad  mov     r12, [rsp+298h+var_220]
0x1800a6cb2  jmp     loc_1800A6ABC
0x1800a6cb7  mov     esi, 57h ; 'W'
0x1800a6cbc  jmp     loc_1800A6A33
0x1800a6cc1  mov     esi, 0C000000Dh
0x1800a6cc6  jmp     loc_1800A6AAA
0x1800a6ccb  mov     esi, 0C0000008h
0x1800a6cd0  jmp     loc_1800A6AB2
0x1800a6cd5  cmp     [rsp+298h+BufferLength+8], edi
0x1800a6cd9  jnb     loc_1800A6A14
0x1800a6cdf  mov     esi, 0Eh
0x1800a6ce4  jmp     loc_1800A6A38
0x1800a6ce9  lea     rcx, PredefinedHandleTableSRWLock
0x1800a6cf0  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800a6cf6  add     dword ptr [rdi+8], 0FFFFFFFFh
0x1800a6cfa  jnz     short loc_1800A6D15
0x1800a6cfc  mov     rax, [rdi+10h]
0x1800a6d00  mov     rcx, [rax+8]
0x1800a6d04  cmp     rdi, rcx
0x1800a6d07  jnz     loc_1800A6D90
0x1800a6d0d  mov     rax, [rax]
0x1800a6d10  cmp     [rdi], rax
0x1800a6d13  jnz     short loc_1800A6D90
0x1800a6d15  lea     rcx, PredefinedHandleTableSRWLock
0x1800a6d1c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800a6d22  test    rbx, rbx
0x1800a6d25  jz      loc_1800A6B1A
0x1800a6d2b  mov     rcx, [rbx]; hKey
0x1800a6d2e  call    RegCloseKey
0x1800a6d33  mov     rcx, rbx; penv
0x1800a6d36  call    FreeEnvironmentStringsW
0x1800a6d3b  jmp     loc_1800A6B1A
0x1800a6d40  call    IsTermsrvDeleteKeyPresent
0x1800a6d45  test    al, al
0x1800a6d47  jz      loc_1800A6AB2
0x1800a6d4d  mov     r8, qword ptr [rsp+298h+BufferLength]
0x1800a6d52  mov     edx, r15d
0x1800a6d55  mov     rcx, rdi
0x1800a6d58  call    cs:__imp_TermsrvSetKeySecurity
0x1800a6d5e  jmp     loc_1800A6AB2
0x1800a6d63  mov     [rsp+298h+var_228], r12
0x1800a6d68  mov     eax, 1
0x1800a6d6d  lea     rcx, [rsp+298h+var_240]
0x1800a6d72  jmp     loc_1800A6BE3
0x1800a6d77  mov     esi, 0Eh
0x1800a6d7c  jmp     loc_1800A6A38
0x1800a6d81  mov     ecx, eax; Status
0x1800a6d83  call    cs:__imp_RtlNtStatusToDosError
0x1800a6d89  mov     esi, eax
0x1800a6d8b  jmp     loc_1800A6ADF
0x1800a6d90  mov     rbx, rdi
0x1800a6d93  mov     r8, [rdi+10h]
0x1800a6d97  mov     rdx, rdi
0x1800a6d9a  call    RemoveUnitFromList
0x1800a6d9f  mov     [r8+8], rax
0x1800a6da3  jmp     loc_1800A6D15
0x1800a6da8  mov     r13d, 3000000h
0x1800a6dae  test    r15b, 1
0x1800a6db2  mov     eax, 3080000h
0x1800a6db7  cmovnz  r13d, eax
0x1800a6dbb  jmp     loc_1800A690A
0x1800a6dc0  cmp     rdi, 0FFFFFFFF80000050h
0x1800a6dc7  jz      loc_1800A6922
0x1800a6dcd  cmp     rdi, 0FFFFFFFF80000060h
0x1800a6dd4  jz      loc_1800A6922
  ... truncated ...
```
