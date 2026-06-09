# RegOpenKeyExInternalA

- ea: `0x18005e9c0`
- end: `0x18005ee24`
- name: `RegOpenKeyExInternalA`
- size: `1124`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, PCSZ Source@<rdx>, PHANDLE, __int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18005e990`
- `0x180096db0`
- `0x1800ddcfc`
- `0x1800deb40`

## callees

- `0x18005b460`
- `0x18005bb80`
- `0x18005bf10`
- `0x18005d2c0`
- `0x18005e9c0`
- `0x1800a6e58`
- `0x18012d578`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18005eaf8`
- `ntdll!RtlFreeUnicodeString` at `0x18005eaf8`
- `ntdll!RtlEnterCriticalSection` at `0x18005eb68`
- `ntdll!RtlEnterCriticalSection` at `0x18005eb68`
- `ntdll!RtlLeaveCriticalSection` at `0x18005eb98`
- `ntdll!RtlLeaveCriticalSection` at `0x18005eb98`
- `ntdll!RtlNtStatusToDosError` at `0x18005ed38`
- `ntdll!RtlNtStatusToDosError` at `0x18005edf5`
- `ntdll!RtlNtStatusToDosError` at `0x18005ed38`
- `ntdll!RtlNtStatusToDosError` at `0x18005edf5`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005eb56`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005eb56`
- `ntdll!NtClose` at `0x18005eba3`
- `ntdll!NtClose` at `0x18005eba3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005ec28`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005ec28`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005ec59`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005ec59`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18005eaa6`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18005eaa6`
- `ntdll!RtlFreeHeap` at `0x18005ec16`
- `ntdll!RtlFreeHeap` at `0x18005ec83`
- `ntdll!RtlFreeHeap` at `0x18005ec16`
- `ntdll!RtlFreeHeap` at `0x18005ec83`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18005edc3`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18005edc3`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegCloseKey` at `0x18005ed21`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegCloseKey` at `0x18005ed21`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegOpenKey` at `0x18005ed7d`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegOpenKey` at `0x18005ed7d`

## pseudocode

```c
LSTATUS __fastcall RegOpenKeyExInternalA(
        HKEY hKey,
        PCSZ Source,
        unsigned int a3,
        unsigned int a4,
        PHANDLE a5,
        __int64 a6)
{
  HKEY *v9; // r12
  HANDLE v10; // rcx
  PHANDLE v11; // rsi
  const char *v12; // rdi
  ULONG v13; // r13d
  unsigned __int64 v14; // rbx
  __int64 v15; // r14
  HANDLE v16; // rsi
  _QWORD *v17; // rcx
  _QWORD *v18; // rdi
  _QWORD *i; // rbx
  int v20; // eax
  LSTATUS result; // eax
  _QWORD *v22; // rax
  __int64 v23; // r8
  _QWORD *v25; // rax
  __int64 v26; // rcx
  _QWORD *v27; // rdx
  _QWORD *v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // r9
  bool v32; // al
  __int64 v33; // r9
  unsigned __int64 v34; // rbx
  int v35; // [rsp+20h] [rbp-78h]
  char v36; // [rsp+40h] [rbp-58h] BYREF
  ULONG v37; // [rsp+44h] [rbp-54h]
  void *v38; // [rsp+48h] [rbp-50h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-48h] BYREF
  __int64 v40; // [rsp+58h] [rbp-40h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+60h] [rbp-38h] BYREF
  HANDLE KeyHandle; // [rsp+A0h] [rbp+8h] BYREF

  KeyHandle = hKey;
  Destination = 0;
  v36 = 0;
  v9 = 0;
  v10 = 0;
  v38 = 0;
  v40 = 0;
  if ( hKey == HKEY_PERFORMANCE_DATA || hKey == HKEY_PERFORMANCE_TEXT || hKey == HKEY_PERFORMANCE_NLSTEXT )
    return 6;
  v11 = a5;
  if ( !a5 )
    return 87;
  v12 = &v36;
  if ( Source )
    v12 = Source;
  if ( ((unsigned __int64)(hKey + 0x20000000) & 0xFFFFFFFFFFFFFFF8uLL) != 0 || (a4 & 0x300) != 0 || v12 && *v12 )
  {
    if ( !v12 )
    {
      v13 = 1010;
      goto LABEL_18;
    }
    v13 = MapPredefinedHandleInternal(hKey, &KeyHandle, &v38, &v40);
    if ( !v13 )
    {
      if ( RtlCreateUnicodeStringFromAsciiz(&Destination, v12) )
      {
        Destination.Length += 2;
        v14 = (unsigned __int64)KeyHandle;
        if ( ((unsigned __int8)KeyHandle & 1) != 0 )
        {
          if ( (unsigned __int8)IsBaseRegCloseKeyPresent() )
          {
            LODWORD(KeyHandle) = 0;
            v34 = v14 & 0xFFFFFFFFFFFFFFFEuLL;
            v32 = (unsigned __int8)IsBaseRegCloseKeyPresent()
               && !(unsigned int)BaseRegGetVersion(v34, &KeyHandle)
               && (_DWORD)KeyHandle == 6;
            v33 = a4 & 0xFFFFFCFF;
            if ( v32 )
              v33 = a4;
            v13 = BaseRegOpenKey(v34, &Destination, a3, v33, v11);
            v37 = v13;
            if ( !v13 )
              *v11 = (HANDLE)((unsigned __int64)*v11 | 1);
          }
        }
        else
        {
          v13 = BaseRegOpenKeyInternal(KeyHandle, &Destination, a3, a4, v35, v11, a6);
        }
        RtlFreeUnicodeString(&Destination);
      }
      else
      {
        v13 = RtlNtStatusToDosError(-1073741801);
      }
    }
    goto LABEL_17;
  }
  if ( hKey == HKEY_CLASSES_ROOT )
  {
LABEL_55:
    *v11 = hKey;
    v13 = 0;
    goto LABEL_18;
  }
  result = RegCloseKey(hKey);
  if ( result )
    return result;
  v13 = MapPredefinedHandleInternal(hKey, 0, &v38, &v40);
  if ( !v13 )
  {
    v10 = v38;
    goto LABEL_55;
  }
LABEL_17:
  v10 = v38;
LABEL_18:
  Handle = v10;
  v15 = v40;
  if ( v10 )
  {
    if ( v10 == (HANDLE)-2147483644LL || v10 == (HANDLE)-2147483568LL || v10 == (HANDLE)-2147483552LL )
    {
      if ( (unsigned __int8)IsBaseRegCloseKeyPresent() )
        PerfRegCloseKey(&Handle);
    }
    else
    {
      if ( ((unsigned __int8)v10 & 2) != 0 )
      {
        RtlRunOnceExecuteOnce(&gClassesEnumTableInit, ClassesEnumTableInitFn, 0, 0);
        v16 = Handle;
        RtlEnterCriticalSection(&CriticalSection);
        v17 = (_QWORD *)qword_18039F308;
        if ( qword_18039F308 )
        {
          do
          {
            v18 = (_QWORD *)*v17;
            for ( i = (_QWORD *)v17[3]; i; i = (_QWORD *)*i )
            {
              if ( v16 == (HANDLE)i[2] )
              {
                if ( i != (_QWORD *)v17[3] )
                {
                  v27 = (_QWORD *)i[1];
                  v28 = (_QWORD *)*i;
                  if ( v27 )
                    *v27 = v28;
                  if ( v28 )
                    v28[1] = v27;
                  v29 = v17[3];
                  if ( v29 )
                  {
                    *i = v29;
                    *(_QWORD *)(v17[3] + 8LL) = i;
                  }
                  v17[3] = i;
                  i[1] = 0;
                }
                v22 = (_QWORD *)*i;
                v17[3] = *i;
                if ( v22 )
                  v22[1] = 0;
                EnumStateClear(i);
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, i);
                break;
              }
            }
            v17 = v18;
          }
          while ( v18 );
        }
        RtlLeaveCriticalSection(&CriticalSection);
        v10 = Handle;
      }
      v20 = NtClose(v10);
      if ( v20 < 0 )
        RtlNtStatusToDosError(v20);
      else
        Handle = 0;
    }
  }
  if ( v15 )
  {
    RtlAcquireSRWLockExclusive(PredefinedHandleTableSRWLock);
    if ( (*(_DWORD *)(v15 + 8))-- == 1 )
    {
      v25 = *(_QWORD **)(v15 + 16);
      v26 = v25[1];
      if ( v15 != v26 || *(_QWORD *)v15 != *v25 )
      {
        v9 = (HKEY *)v15;
        v30 = RemoveUnitFromList(v26, v15, v23);
        *(_QWORD *)(v31 + 8) = v30;
      }
    }
    RtlReleaseSRWLockExclusive(PredefinedHandleTableSRWLock);
    if ( v9 )
    {
      RegCloseKey(*v9);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18005e9c0  mov     rax, rsp
0x18005e9c3  mov     [rax+10h], rbx
0x18005e9c7  mov     [rax+18h], rsi
0x18005e9cb  mov     [rax+8], rcx
0x18005e9cf  push    rdi
0x18005e9d0  push    r12
0x18005e9d2  push    r13
0x18005e9d4  push    r14
0x18005e9d6  push    r15
0x18005e9d8  sub     rsp, 70h
0x18005e9dc  mov     r14d, r9d
0x18005e9df  mov     r15d, r8d
0x18005e9e2  mov     rbx, rcx
0x18005e9e5  xorps   xmm0, xmm0
0x18005e9e8  movups  xmmword ptr [rax-38h], xmm0
0x18005e9ec  mov     byte ptr [rax-58h], 0
0x18005e9f0  xor     r12d, r12d
0x18005e9f3  mov     ecx, r12d
0x18005e9f6  mov     [rax-50h], rcx
0x18005e9fa  mov     [rax-40h], r12
0x18005e9fe  cmp     rbx, 0FFFFFFFF80000004h
0x18005ea05  jz      loc_18005ED2C
0x18005ea0b  cmp     rbx, 0FFFFFFFF80000050h
0x18005ea12  jz      loc_18005ED2C
0x18005ea18  cmp     rbx, 0FFFFFFFF80000060h
0x18005ea1f  jz      loc_18005ED2C
0x18005ea25  mov     rsi, [rsp+98h+arg_20]
0x18005ea2d  test    rsi, rsi
0x18005ea30  jz      loc_18005EDDB
0x18005ea36  lea     rdi, [rax-58h]
0x18005ea3a  test    rdx, rdx
0x18005ea3d  cmovnz  rdi, rdx
0x18005ea41  mov     eax, 80000000h
0x18005ea46  add     rax, rbx
0x18005ea49  test    rax, 0FFFFFFFFFFFFFFF8h
0x18005ea4f  jnz     short loc_18005EA74
0x18005ea51  cmp     rbx, 0FFFFFFFF80000004h
0x18005ea58  jz      short loc_18005EA74
0x18005ea5a  test    r9d, 300h
0x18005ea61  jnz     short loc_18005EA74
0x18005ea63  test    rdi, rdi
0x18005ea66  jz      loc_18005ECC7
0x18005ea6c  cmp     [rdi], cl
0x18005ea6e  jz      loc_18005ECC7
0x18005ea74  test    rdi, rdi
0x18005ea77  jz      loc_18005EDE5
0x18005ea7d  lea     r9, [rsp+98h+var_40]
0x18005ea82  lea     r8, [rsp+98h+var_50]
0x18005ea87  lea     rdx, [rsp+98h+KeyHandle]
0x18005ea8f  mov     rcx, rbx
0x18005ea92  call    MapPredefinedHandleInternal
0x18005ea97  mov     r13d, eax
0x18005ea9a  test    eax, eax
0x18005ea9c  jnz     short loc_18005EAFE
0x18005ea9e  mov     rdx, rdi; Source
0x18005eaa1  lea     rcx, [rsp+98h+Destination]; Destination
0x18005eaa6  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18005eaac  test    al, al
0x18005eaae  jz      loc_18005EDF0
0x18005eab4  add     [rsp+98h+Destination.Length], 2
0x18005eaba  mov     rbx, [rsp+98h+KeyHandle]
0x18005eac2  test    bl, 1
0x18005eac5  jnz     loc_18005EE03
0x18005eacb  mov     rax, [rsp+98h+arg_28]
0x18005ead3  mov     [rsp+98h+var_68], rax; __int64
0x18005ead8  mov     [rsp+98h+var_70], rsi; PHANDLE
0x18005eadd  mov     r9d, r14d
0x18005eae0  mov     r8d, r15d
0x18005eae3  lea     rdx, [rsp+98h+Destination]; Source
0x18005eae8  mov     rcx, rbx; KeyHandle
0x18005eaeb  call    BaseRegOpenKeyInternal
0x18005eaf0  mov     r13d, eax
0x18005eaf3  lea     rcx, [rsp+98h+Destination]; UnicodeString
0x18005eaf8  call    cs:__imp_RtlFreeUnicodeString
0x18005eafe  mov     rcx, [rsp+98h+var_50]
0x18005eb03  mov     [rsp+98h+Handle], rcx
0x18005eb08  mov     r14, [rsp+98h+var_40]
0x18005eb0d  test    rcx, rcx
0x18005eb10  jz      loc_18005EBB6
0x18005eb16  cmp     rcx, 0FFFFFFFF80000004h
0x18005eb1d  jz      loc_18005ED0F
0x18005eb23  cmp     rcx, 0FFFFFFFF80000050h
0x18005eb2a  jz      loc_18005ED0F
0x18005eb30  cmp     rcx, 0FFFFFFFF80000060h
0x18005eb37  jz      loc_18005ED0F
0x18005eb3d  test    cl, 2
0x18005eb40  jz      short loc_18005EBA3
0x18005eb42  xor     r9d, r9d
0x18005eb45  xor     r8d, r8d
0x18005eb48  lea     rdx, ClassesEnumTableInitFn
0x18005eb4f  lea     rcx, gClassesEnumTableInit
0x18005eb56  call    cs:__imp_RtlRunOnceExecuteOnce
0x18005eb5c  mov     rsi, [rsp+98h+Handle]
0x18005eb61  lea     rcx, CriticalSection; CriticalSection
0x18005eb68  call    cs:__imp_RtlEnterCriticalSection
0x18005eb6e  mov     rcx, cs:qword_18039F308
0x18005eb75  test    rcx, rcx
0x18005eb78  jz      short loc_18005EB91
0x18005eb7a  mov     rdi, [rcx]
0x18005eb7d  mov     rax, [rcx+18h]
0x18005eb81  mov     rbx, rax
0x18005eb84  test    rbx, rbx
0x18005eb87  jnz     short loc_18005EBD8
0x18005eb89  mov     rcx, rdi
0x18005eb8c  test    rdi, rdi
0x18005eb8f  jnz     short loc_18005EB7A
0x18005eb91  lea     rcx, CriticalSection; CriticalSection
0x18005eb98  call    cs:__imp_RtlLeaveCriticalSection
0x18005eb9e  mov     rcx, [rsp+98h+Handle]; Handle
0x18005eba3  call    cs:__imp_NtClose
0x18005eba9  test    eax, eax
0x18005ebab  js      loc_18005ED36
0x18005ebb1  mov     [rsp+98h+Handle], r12
0x18005ebb6  test    r14, r14
0x18005ebb9  jnz     short loc_18005EC21
0x18005ebbb  mov     eax, r13d
0x18005ebbe  lea     r11, [rsp+98h+var_28]
0x18005ebc3  mov     rbx, [r11+38h]
0x18005ebc7  mov     rsi, [r11+40h]
0x18005ebcb  mov     rsp, r11
0x18005ebce  pop     r15
0x18005ebd0  pop     r14
0x18005ebd2  pop     r13
0x18005ebd4  pop     r12
0x18005ebd6  pop     rdi
0x18005ebd7  retn
0x18005ebd8  cmp     rsi, [rbx+10h]
0x18005ebdc  jz      short loc_18005EBE3
0x18005ebde  mov     rbx, [rbx]
0x18005ebe1  jmp     short loc_18005EB84
0x18005ebe3  cmp     rbx, rax
0x18005ebe6  jnz     loc_18005EC8E
0x18005ebec  mov     rax, [rbx]
0x18005ebef  mov     [rcx+18h], rax
0x18005ebf3  test    rax, rax
0x18005ebf6  jz      short loc_18005EBFC
0x18005ebf8  mov     [rax+8], r12
0x18005ebfc  mov     rcx, rbx; void *
0x18005ebff  call    EnumStateClear
0x18005ec04  mov     rcx, gs:60h
0x18005ec0d  mov     r8, rbx; P
0x18005ec10  xor     edx, edx; Flags
0x18005ec12  mov     rcx, [rcx+30h]; HeapHandle
0x18005ec16  call    cs:__imp_RtlFreeHeap
0x18005ec1c  jmp     loc_18005EB89
0x18005ec21  lea     rcx, PredefinedHandleTableSRWLock
0x18005ec28  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18005ec2e  add     dword ptr [r14+8], 0FFFFFFFFh
0x18005ec33  jnz     short loc_18005EC52
0x18005ec35  mov     rax, [r14+10h]
0x18005ec39  mov     rcx, [rax+8]
0x18005ec3d  cmp     r14, rcx
0x18005ec40  jnz     loc_18005ED43
0x18005ec46  mov     rax, [rax]
0x18005ec49  cmp     [r14], rax
0x18005ec4c  jnz     loc_18005ED43
0x18005ec52  lea     rcx, PredefinedHandleTableSRWLock
0x18005ec59  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005ec5f  test    r12, r12
0x18005ec62  jz      loc_18005EBBB
0x18005ec68  mov     rcx, [r12]; hKey
0x18005ec6c  call    RegCloseKey
0x18005ec71  mov     rcx, gs:60h
0x18005ec7a  mov     r8, r12; P
0x18005ec7d  xor     edx, edx; Flags
0x18005ec7f  mov     rcx, [rcx+30h]; HeapHandle
0x18005ec83  call    cs:__imp_RtlFreeHeap
0x18005ec89  jmp     loc_18005EBBB
0x18005ec8e  mov     rdx, [rbx+8]
0x18005ec92  mov     rax, [rbx]
0x18005ec95  test    rdx, rdx
0x18005ec98  jz      short loc_18005EC9D
0x18005ec9a  mov     [rdx], rax
0x18005ec9d  test    rax, rax
0x18005eca0  jz      short loc_18005ECA6
0x18005eca2  mov     [rax+8], rdx
0x18005eca6  mov     rax, [rcx+18h]
0x18005ecaa  test    rax, rax
0x18005ecad  jz      short loc_18005ECBA
0x18005ecaf  mov     [rbx], rax
0x18005ecb2  mov     rax, [rcx+18h]
0x18005ecb6  mov     [rax+8], rbx
0x18005ecba  mov     [rcx+18h], rbx
0x18005ecbe  mov     [rbx+8], r12
0x18005ecc2  jmp     loc_18005EBEC
0x18005ecc7  cmp     rbx, 0FFFFFFFF80000000h
0x18005ecce  jz      short loc_18005ED04
0x18005ecd0  mov     rcx, rbx; hKey
0x18005ecd3  call    RegCloseKey
0x18005ecd8  test    eax, eax
0x18005ecda  jnz     loc_18005EBBE
0x18005ece0  lea     r9, [rsp+98h+var_40]
0x18005ece5  lea     r8, [rsp+98h+var_50]
0x18005ecea  xor     edx, edx
0x18005ecec  mov     rcx, rbx
0x18005ecef  call    MapPredefinedHandleInternal
0x18005ecf4  mov     r13d, eax
0x18005ecf7  test    eax, eax
0x18005ecf9  jnz     loc_18005EAFE
0x18005ecff  mov     rcx, [rsp+98h+var_50]
0x18005ed04  mov     [rsi], rbx
0x18005ed07  mov     r13d, r12d
0x18005ed0a  jmp     loc_18005EB03
0x18005ed0f  call    IsBaseRegCloseKeyPresent
0x18005ed14  test    al, al
0x18005ed16  jz      loc_18005EBB6
0x18005ed1c  lea     rcx, [rsp+98h+Handle]
0x18005ed21  call    cs:__imp_PerfRegCloseKey
0x18005ed27  jmp     loc_18005EBB6
0x18005ed2c  mov     eax, 6
0x18005ed31  jmp     loc_18005EBBE
0x18005ed36  mov     ecx, eax; Status
0x18005ed38  call    cs:__imp_RtlNtStatusToDosError
0x18005ed3e  jmp     loc_18005EBB6
0x18005ed43  mov     r12, r14
0x18005ed46  mov     r9, [r14+10h]
0x18005ed4a  mov     rdx, r14
0x18005ed4d  call    RemoveUnitFromList
0x18005ed52  mov     [r9+8], rax
0x18005ed56  jmp     loc_18005EC52
0x18005ed5b  xor     al, al
0x18005ed5d  mov     r9d, r14d
0x18005ed60  and     r9d, 0FFFFFCFFh
0x18005ed67  test    al, al
0x18005ed69  cmovnz  r9d, r14d
0x18005ed6d  mov     [rsp+98h+var_78], rsi
0x18005ed72  mov     r8d, r15d
0x18005ed75  lea     rdx, [rsp+98h+Destination]
0x18005ed7a  mov     rcx, rbx
0x18005ed7d  call    cs:__imp_BaseRegOpenKey
0x18005ed83  mov     r13d, eax
0x18005ed86  mov     [rsp+98h+var_54], eax
0x18005ed8a  jmp     loc_18005EE12
0x18005ed8f  mov     r13d, eax
0x18005ed92  mov     [rsp+98h+var_54], eax
0x18005ed96  xor     r12d, r12d
0x18005ed99  mov     rsi, [rsp+98h+arg_20]
0x18005eda1  jmp     short loc_18005EE12
0x18005eda3  mov     dword ptr [rsp+98h+KeyHandle], r12d
0x18005edab  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18005edaf  call    IsBaseRegCloseKeyPresent
0x18005edb4  test    al, al
0x18005edb6  jz      short loc_18005ED5B
0x18005edb8  lea     rdx, [rsp+98h+KeyHandle]
0x18005edc0  mov     rcx, rbx
0x18005edc3  call    cs:__imp_BaseRegGetVersion
0x18005edc9  test    eax, eax
0x18005edcb  jnz     short loc_18005ED5B
0x18005edcd  cmp     dword ptr [rsp+98h+KeyHandle], 6
0x18005edd5  jnz     short loc_18005ED5B
0x18005edd7  mov     al, 1
0x18005edd9  jmp     short loc_18005ED5D
0x18005eddb  mov     eax, 57h ; 'W'
0x18005ede0  jmp     loc_18005EBBE
0x18005ede5  mov     r13d, 3F2h
0x18005edeb  jmp     loc_18005EB03
0x18005edf0  mov     ecx, 0C0000017h; Status
0x18005edf5  call    cs:__imp_RtlNtStatusToDosError
0x18005edfb  mov     r13d, eax
0x18005edfe  jmp     loc_18005EAFE
0x18005ee03  call    IsBaseRegCloseKeyPresent
0x18005ee08  test    al, al
0x18005ee0a  jz      loc_18005EAF3
0x18005ee10  jmp     short loc_18005EDA3
0x18005ee12  test    r13d, r13d
0x18005ee15  jnz     loc_18005EAF3
0x18005ee1b  or      qword ptr [rsi], 1
0x18005ee1f  jmp     loc_18005EAF3
```
