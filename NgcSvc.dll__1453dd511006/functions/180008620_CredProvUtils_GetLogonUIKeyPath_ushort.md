# CredProvUtils::GetLogonUIKeyPath(ushort * *)

- ea: `0x180008620`
- end: `0x1800088d2`
- name: `?GetLogonUIKeyPath@CredProvUtils@@YAJPEAPEAG@Z`
- size: `690`
- prototype: `__int64 __fastcall(CredProvUtils *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800083d0`
- `0x1800c0a30`

## callees

- `0x18000782c`
- `0x180008620`
- `0x180009e94`
- `0x18000b744`
- `0x180048304`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008658`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008658`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800086cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008722`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800087f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008857`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000889e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800086cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008722`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800087f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008857`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000889e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008798`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008798`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800086ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800086ec`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180008698`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800087c0`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180008698`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800087c0`

## string_xrefs

- `0x1800086b5`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x180008709`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x18000876b`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x1800087d6`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x180008814`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x18000883e`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CredProvUtils::GetLogonUIKeyPath(CredProvUtils *this, unsigned __int16 **a2)
{
  unsigned int PersistedRegistryLocationW; // eax
  unsigned int v4; // ebx
  unsigned __int16 *v6; // rsi
  int v7; // eax
  unsigned int v8; // esi
  unsigned int v9; // eax
  unsigned int v10; // ebx
  LPVOID v11; // rax
  SIZE_T *p_cb; // [rsp+20h] [rbp-38h]
  LPVOID pv; // [rsp+30h] [rbp-28h] BYREF
  __int64 v14; // [rsp+38h] [rbp-20h]
  __int64 v15; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  SIZE_T cb; // [rsp+60h] [rbp+8h] BYREF

  if ( !this )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
      (const char *)0x80004003LL,
      (int)p_cb);
    return 2147500035LL;
  }
  if ( !::pv || !*::pv )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !::pv || !*::pv )
    {
      LODWORD(cb) = 0;
      PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                     L"LogonUI",
                                     L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
                                     0,
                                     0);
      if ( !PersistedRegistryLocationW )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x23,
          (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
          (const char *)0x8000FFFFLL,
          (int)&cb);
        ReleaseSRWLockExclusive(&SRWLock);
        return 2147549183LL;
      }
      if ( PersistedRegistryLocationW != 234 )
      {
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x27,
               (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
               (const char *)PersistedRegistryLocationW,
               (unsigned int)&cb);
        ReleaseSRWLockExclusive(&SRWLock);
        return v4;
      }
      v6 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)cb);
      if ( !v6 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B,
          (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
          (const char *)0x8007000ELL,
          (int)&cb);
        ReleaseSRWLockExclusive(&SRWLock);
        return 2147942414LL;
      }
      p_cb = &cb;
      v9 = GetPersistedRegistryLocationW(
             L"LogonUI",
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
             v6,
             (unsigned int)cb);
      if ( v9 )
      {
        v10 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x32,
                (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
                (const char *)v9,
                (unsigned int)&cb);
        ReleaseSRWLockExclusive(&SRWLock);
        return v10;
      }
      if ( ::pv )
        CoTaskMemFree(::pv);
      ::pv = v6;
      qword_180123338 = -1;
      qword_180123330 = -1;
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  pv = 0;
  v14 = 0;
  v15 = 0;
  v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(&pv, a2);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v11 = pv;
    pv = 0;
    v15 = 0;
    v14 = 0;
    *(_QWORD *)this = v11;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
      (const char *)(unsigned int)v7,
      (int)p_cb);
    if ( pv )
      CoTaskMemFree(pv);
    return v8;
  }
}

```

## disassembly

```asm
0x180008620  mov     [rsp+arg_8], rbx
0x180008625  mov     [rsp+arg_10], rsi
0x18000862a  push    rdi
0x18000862b  sub     rsp, 50h
0x18000862f  mov     rbx, rcx
0x180008632  test    rcx, rcx
0x180008635  jz      loc_180008809
0x18000863b  mov     rax, cs:pv
0x180008642  test    rax, rax
0x180008645  jz      short loc_180008651
0x180008647  cmp     word ptr [rax], 0
0x18000864b  jnz     loc_18000873E
0x180008651  lea     rcx, SRWLock; SRWLock
0x180008658  call    cs:__imp_AcquireSRWLockExclusive
0x18000865e  mov     rax, cs:pv
0x180008665  test    rax, rax
0x180008668  jz      short loc_180008674
0x18000866a  cmp     word ptr [rax], 0
0x18000866e  jnz     loc_18000882F
0x180008674  xor     edi, edi
0x180008676  mov     dword ptr [rsp+58h+cb], edi
0x18000867a  lea     rax, [rsp+58h+cb]
0x18000867f  mov     qword ptr [rsp+58h+var_38], rax; int
0x180008684  xor     r9d, r9d
0x180008687  xor     r8d, r8d
0x18000868a  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180008691  lea     rcx, aLogonui; "LogonUI"
0x180008698  call    cs:__imp_GetPersistedRegistryLocationW
0x18000869e  test    eax, eax
0x1800086a0  jz      loc_180008833
0x1800086a6  cmp     eax, 0EAh
0x1800086ab  jz      short loc_1800086E8
0x1800086ad  mov     rcx, [rsp+58h]; this
0x1800086b2  mov     r9d, eax; char *
0x1800086b5  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x1800086bc  mov     edx, 27h ; '''; void *
0x1800086c1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800086c6  mov     ebx, eax
0x1800086c8  lea     rcx, SRWLock; SRWLock
0x1800086cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800086d5  nop
0x1800086d6  mov     eax, ebx
0x1800086d8  mov     rbx, [rsp+58h+arg_8]
0x1800086dd  mov     rsi, [rsp+58h+arg_10]
0x1800086e2  add     rsp, 50h
0x1800086e6  pop     rdi
0x1800086e7  retn
0x1800086e8  mov     ecx, dword ptr [rsp+58h+cb]; cb
0x1800086ec  call    cs:__imp_CoTaskMemAlloc
0x1800086f2  mov     rsi, rax
0x1800086f5  test    rax, rax
0x1800086f8  jnz     loc_1800087A0
0x1800086fe  mov     rcx, [rsp+58h]; this
0x180008703  mov     r9d, 8007000Eh; char *
0x180008709  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x180008710  mov     edx, 2Bh ; '+'; void *
0x180008715  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000871a  nop
0x18000871b  lea     rcx, SRWLock; SRWLock
0x180008722  call    cs:__imp_ReleaseSRWLockExclusive
0x180008728  nop
0x180008729  mov     eax, 8007000Eh
0x18000872e  mov     rbx, [rsp+58h+arg_8]
0x180008733  mov     rsi, [rsp+58h+arg_10]
0x180008738  add     rsp, 50h
0x18000873c  pop     rdi
0x18000873d  retn
0x18000873e  xor     edi, edi
0x180008740  mov     [rsp+58h+pv], rdi
0x180008745  mov     [rsp+58h+var_20], rdi
0x18000874a  mov     [rsp+58h+var_18], rdi
0x18000874f  lea     rcx, [rsp+58h+pv]
0x180008754  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x180008759  mov     esi, eax
0x18000875b  test    eax, eax
0x18000875d  jns     loc_1800088AA
0x180008763  mov     rcx, [rsp+58h]; this
0x180008768  mov     r9d, eax; char *
0x18000876b  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x180008772  mov     edx, 39h ; '9'; void *
0x180008777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000877c  mov     rcx, [rsp+58h+pv]; pv
0x180008781  test    rcx, rcx
0x180008784  jnz     short loc_180008798
0x180008786  mov     eax, esi
0x180008788  mov     rbx, [rsp+58h+arg_8]
0x18000878d  mov     rsi, [rsp+58h+arg_10]
0x180008792  add     rsp, 50h
0x180008796  pop     rdi
0x180008797  retn
0x180008798  call    cs:__imp_CoTaskMemFree
0x18000879e  jmp     short loc_180008786
0x1800087a0  lea     rax, [rsp+58h+cb]
0x1800087a5  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x1800087aa  mov     r9d, dword ptr [rsp+58h+cb]
0x1800087af  mov     r8, rsi
0x1800087b2  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800087b9  lea     rcx, aLogonui; "LogonUI"
0x1800087c0  call    cs:__imp_GetPersistedRegistryLocationW
0x1800087c6  test    eax, eax
0x1800087c8  jz      loc_180008868
0x1800087ce  mov     rcx, [rsp+58h]; this
0x1800087d3  mov     r9d, eax; char *
0x1800087d6  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x1800087dd  mov     edx, 32h ; '2'; void *
0x1800087e2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800087e7  mov     ebx, eax
0x1800087e9  lea     rcx, SRWLock; SRWLock
0x1800087f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800087f6  nop
0x1800087f7  mov     eax, ebx
0x1800087f9  mov     rbx, [rsp+58h+arg_8]
0x1800087fe  mov     rsi, [rsp+58h+arg_10]
0x180008803  add     rsp, 50h
0x180008807  pop     rdi
0x180008808  retn
0x180008809  mov     rcx, [rsp+58h]; this
0x18000880e  mov     r9d, 80004003h; char *
0x180008814  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x18000881b  mov     edx, 13h; void *
0x180008820  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008825  mov     eax, 80004003h
0x18000882a  jmp     loc_1800086D8
0x18000882f  xor     edi, edi
0x180008831  jmp     short loc_180008897
0x180008833  mov     rcx, [rsp+58h]; this
0x180008838  mov     r9d, 8000FFFFh; char *
0x18000883e  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x180008845  mov     edx, 23h ; '#'; void *
0x18000884a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000884f  nop
0x180008850  lea     rcx, SRWLock; SRWLock
0x180008857  call    cs:__imp_ReleaseSRWLockExclusive
0x18000885d  nop
0x18000885e  mov     eax, 8000FFFFh
0x180008863  jmp     loc_1800086D8
0x180008868  mov     rcx, cs:pv; pv
0x18000886f  test    rcx, rcx
0x180008872  jz      short loc_18000887A
0x180008874  call    cs:__imp_CoTaskMemFree
0x18000887a  mov     cs:pv, rsi
0x180008881  mov     cs:qword_180123338, 0FFFFFFFFFFFFFFFFh
0x18000888c  mov     cs:qword_180123330, 0FFFFFFFFFFFFFFFFh
0x180008897  lea     rcx, SRWLock; SRWLock
0x18000889e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800088a4  nop
0x1800088a5  jmp     loc_180008740
0x1800088aa  mov     rax, [rsp+58h+pv]
0x1800088af  mov     [rsp+58h+pv], rdi
0x1800088b4  mov     [rsp+58h+var_18], rdi
0x1800088b9  mov     [rsp+58h+var_20], rdi
0x1800088be  mov     [rbx], rax
0x1800088c1  lea     rcx, [rsp+58h+pv]
0x1800088c6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800088cb  xor     eax, eax
0x1800088cd  jmp     loc_1800086D8
```
