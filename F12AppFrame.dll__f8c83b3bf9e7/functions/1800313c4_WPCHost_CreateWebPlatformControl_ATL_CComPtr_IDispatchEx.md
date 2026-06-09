# WPCHost::CreateWebPlatformControl(ATL::CComPtr<IDispatchEx> &)

- ea: `0x1800313c4`
- end: `0x1800316ae`
- name: `?CreateWebPlatformControl@WPCHost@@AEAAJAEAV?$CComPtr@UIDispatchEx@@@ATL@@@Z`
- size: `746`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ec34`

## callees

- `0x180002678`
- `0x1800313c4`
- `0x180031a20`
- `0x180035010`

## import_xrefs

- `KERNEL32!AddAtomW` at `0x1800314ec`
- `KERNEL32!AddAtomW` at `0x1800314ec`
- `KERNEL32!FindAtomW` at `0x180031491`
- `KERNEL32!FindAtomW` at `0x180031491`
- `KERNEL32!EnterCriticalSection` at `0x1800313fb`
- `KERNEL32!EnterCriticalSection` at `0x180031484`
- `KERNEL32!EnterCriticalSection` at `0x1800313fb`
- `KERNEL32!EnterCriticalSection` at `0x180031484`
- `KERNEL32!LeaveCriticalSection` at `0x180031476`
- `KERNEL32!LeaveCriticalSection` at `0x1800314cf`
- `KERNEL32!LeaveCriticalSection` at `0x1800314d9`
- `KERNEL32!LeaveCriticalSection` at `0x1800314f5`
- `KERNEL32!LeaveCriticalSection` at `0x18003151f`
- `KERNEL32!LeaveCriticalSection` at `0x180031559`
- `KERNEL32!LeaveCriticalSection` at `0x180031476`
- `KERNEL32!LeaveCriticalSection` at `0x1800314cf`
- `KERNEL32!LeaveCriticalSection` at `0x1800314d9`
- `KERNEL32!LeaveCriticalSection` at `0x1800314f5`
- `KERNEL32!LeaveCriticalSection` at `0x18003151f`
- `KERNEL32!LeaveCriticalSection` at `0x180031559`
- `urlmon!RegisterWebPlatformPermanentSecurityManager` at `0x1800314b6`
- `urlmon!RegisterWebPlatformPermanentSecurityManager` at `0x1800314b6`
- `iertutil!__imp_SetWebPlatformSecurityManagerFactoryCallback` at `0x1800314a3`
- `iertutil!__imp_SetWebPlatformSecurityManagerFactoryCallback` at `0x1800314a3`
- `MSHTML!GetWebPlatformObject` at `0x180031612`
- `MSHTML!GetWebPlatformObject` at `0x180031612`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WPCHost::CreateWebPlatformControl(__int64 a1, __int64 *a2)
{
  __int64 v4; // rbx
  int v5; // ebx
  char *v6; // rsi
  __int64 v7; // rcx
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  _DWORD v12[2]; // [rsp+20h] [rbp-B9h] BYREF
  __int64 v13; // [rsp+28h] [rbp-B1h]
  const wchar_t *v14; // [rsp+30h] [rbp-A9h]
  const wchar_t *v15; // [rsp+38h] [rbp-A1h]
  __int64 v16; // [rsp+40h] [rbp-99h]
  int v17; // [rsp+48h] [rbp-91h]
  __int64 v18; // [rsp+4Ch] [rbp-8Dh]
  int v19; // [rsp+54h] [rbp-85h]
  __int64 v20; // [rsp+58h] [rbp-81h]
  int v21; // [rsp+60h] [rbp-79h]
  __int64 v22; // [rsp+64h] [rbp-75h]
  int v23; // [rsp+6Ch] [rbp-6Dh]
  void *v24; // [rsp+70h] [rbp-69h]
  char v25; // [rsp+78h] [rbp-61h]
  int v26; // [rsp+80h] [rbp-59h] BYREF
  __int64 v27; // [rsp+88h] [rbp-51h]
  __int128 v28; // [rsp+90h] [rbp-49h]
  __int64 v29; // [rsp+A0h] [rbp-39h]
  __int64 v30; // [rsp+A8h] [rbp-31h]
  __int64 v31; // [rsp+B0h] [rbp-29h]
  __int64 v32; // [rsp+B8h] [rbp-21h]
  __int128 v33; // [rsp+C0h] [rbp-19h]
  __int128 v34; // [rsp+D0h] [rbp-9h]
  char *v35; // [rsp+150h] [rbp+77h] BYREF
  __int64 v36; // [rsp+158h] [rbp+7Fh]

  v36 = 0;
  v24 = &WPCSecurityManager::s_csInitializeLock;
  EnterCriticalSection((LPCRITICAL_SECTION)&WPCSecurityManager::s_csInitializeLock);
  v25 = 1;
  v4 = WPCSecurityManager::s_spSecurityManager;
  if ( !WPCSecurityManager::s_spSecurityManager )
  {
    v35 = 0;
    v5 = ATL::CComObject<WPCSecurityManager>::CreateInstance(&v35);
    v6 = v35;
    v7 = WPCSecurityManager::s_spSecurityManager;
    if ( (char *)WPCSecurityManager::s_spSecurityManager != v35 )
    {
      if ( v35 )
      {
        (*(void (__fastcall **)(char *))(*(_QWORD *)v35 + 8LL))(v35);
        v7 = WPCSecurityManager::s_spSecurityManager;
      }
      WPCSecurityManager::s_spSecurityManager = (__int64)v6;
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    if ( v5 )
    {
      if ( v5 >= 0 )
        v5 = -2147467259;
      LeaveCriticalSection((LPCRITICAL_SECTION)&WPCSecurityManager::s_csInitializeLock);
      return (unsigned int)v5;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)&WPCSecurityManager::s_csInitializeLock);
    if ( !FindAtomW(L"{44A9A18E-A2AE-4554-B56E-085F7471105F}") )
    {
      v5 = SetWebPlatformSecurityManagerFactoryCallback(WPCSecurityManager::GetWebPlatformSecurityManager);
      if ( v5 || (v5 = RegisterWebPlatformPermanentSecurityManager(WPCSecurityManager::s_spSecurityManager)) != 0 )
      {
        if ( v5 >= 0 )
          v5 = -2147467259;
        LeaveCriticalSection((LPCRITICAL_SECTION)&WPCSecurityManager::s_csInitializeLock);
        LeaveCriticalSection((LPCRITICAL_SECTION)&WPCSecurityManager::s_csInitializeLock);
        return (unsigned int)v5;
      }
      AddAtomW(L"{44A9A18E-A2AE-4554-B56E-085F7471105F}");
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)&WPCSecurityManager::s_csInitializeLock);
    v4 = WPCSecurityManager::s_spSecurityManager;
  }
  if ( !v4 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)&WPCSecurityManager::s_csInitializeLock);
    return (unsigned int)-2147467262;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  v36 = v4;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  LeaveCriticalSection((LPCRITICAL_SECTION)&WPCSecurityManager::s_csInitializeLock);
  v18 = 0;
  v19 = 0;
  v22 = 0;
  v23 = 0;
  v12[0] = 80;
  v12[1] = 2;
  v13 = 0;
  v14 = L"InternetExplorer";
  v15 = L"InternetExplorer";
  v16 = 0;
  v20 = 0;
  v21 = 0;
  v17 = 67110657;
  memset_0(&v26, 0, 0x80u);
  v26 = 128;
  if ( a1 )
    v27 = a1 + 8;
  else
    v27 = 0;
  v28 = 0;
  v29 = *a2;
  v30 = 0;
  v31 = v4;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v9 = ((__int64 (__fastcall *)(_DWORD *, int *, GUID *, __int64))GetWebPlatformObject)(
         v12,
         &v26,
         &GUID_dedcdb67_0e27_4593_81e5_437734383fd2,
         a1 + 104);
  v10 = v9;
  if ( v9 )
  {
    if ( v9 >= 0 )
      v10 = -2147467259;
LABEL_29:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    return v10;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 104) + 104LL))(*(_QWORD *)(a1 + 104), a1 + 112);
  v10 = v11;
  if ( v11 )
  {
    if ( v11 >= 0 )
      v10 = -2147467259;
    goto LABEL_29;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x1800313c4  mov     [rsp-8+arg_0], rbx
0x1800313c9  push    rbp
0x1800313ca  push    rsi
0x1800313cb  push    rdi
0x1800313cc  push    r12
0x1800313ce  push    r13
0x1800313d0  push    r14
0x1800313d2  push    r15
0x1800313d4  lea     rbp, [rsp-27h]
0x1800313d9  sub     rsp, 100h
0x1800313e0  mov     r15, rdx
0x1800313e3  mov     r14, rcx
0x1800313e6  xor     r12d, r12d
0x1800313e9  mov     [rbp+57h+arg_18], r12
0x1800313ed  lea     r13, ?s_csInitializeLock@WPCSecurityManager@@0VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection WPCSecurityManager::s_csInitializeLock
0x1800313f4  mov     [rbp+57h+var_C0], r13
0x1800313f8  mov     rcx, r13; lpCriticalSection
0x1800313fb  call    cs:__imp_EnterCriticalSection
0x180031401  mov     [rbp+57h+var_B8], 1
0x180031405  mov     rbx, cs:?s_spSecurityManager@WPCSecurityManager@@0V?$CComObjPtr@VWPCSecurityManager@@@@A; CComObjPtr<WPCSecurityManager> WPCSecurityManager::s_spSecurityManager
0x18003140c  test    rbx, rbx
0x18003140f  jnz     loc_180031502
0x180031415  mov     [rbp+57h+arg_10], r12
0x180031419  lea     rcx, [rbp+57h+arg_10]
0x18003141d  call    ?CreateInstance@?$CComObject@VWPCSecurityManager@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<WPCSecurityManager>::CreateInstance(ATL::CComObject<WPCSecurityManager> * *)
0x180031422  mov     ebx, eax
0x180031424  mov     rsi, [rbp+57h+arg_10]
0x180031428  mov     rcx, cs:?s_spSecurityManager@WPCSecurityManager@@0V?$CComObjPtr@VWPCSecurityManager@@@@A; CComObjPtr<WPCSecurityManager> WPCSecurityManager::s_spSecurityManager
0x18003142f  cmp     rcx, rsi
0x180031432  jz      short loc_180031467
0x180031434  test    rsi, rsi
0x180031437  jz      short loc_18003144F
0x180031439  mov     rax, [rsi]
0x18003143c  mov     rcx, rsi
0x18003143f  mov     rax, [rax+8]
0x180031443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031448  mov     rcx, cs:?s_spSecurityManager@WPCSecurityManager@@0V?$CComObjPtr@VWPCSecurityManager@@@@A; CComObjPtr<WPCSecurityManager> WPCSecurityManager::s_spSecurityManager
0x18003144f  mov     cs:?s_spSecurityManager@WPCSecurityManager@@0V?$CComObjPtr@VWPCSecurityManager@@@@A, rsi; CComObjPtr<WPCSecurityManager> WPCSecurityManager::s_spSecurityManager
0x180031456  test    rcx, rcx
0x180031459  jz      short loc_180031467
0x18003145b  mov     rax, [rcx]
0x18003145e  mov     rax, [rax+10h]
0x180031462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031467  test    ebx, ebx
0x180031469  jz      short loc_180031481
0x18003146b  mov     esi, 80004005h
0x180031470  cmovns  ebx, esi
0x180031473  mov     rcx, r13; lpCriticalSection
0x180031476  call    cs:__imp_LeaveCriticalSection
0x18003147c  jmp     loc_18003152A
0x180031481  mov     rcx, r13; lpCriticalSection
0x180031484  call    cs:__imp_EnterCriticalSection
0x18003148a  lea     rcx, a44a9a18eA2ae45; "{44A9A18E-A2AE-4554-B56E-085F7471105F}"
0x180031491  call    cs:__imp_FindAtomW
0x180031497  test    ax, ax
0x18003149a  jnz     short loc_1800314F2
0x18003149c  lea     rcx, ?GetWebPlatformSecurityManager@WPCSecurityManager@@SAJPEAPEAUIWebPlatformPermanentSecurityManager@@@Z; WPCSecurityManager::GetWebPlatformSecurityManager(IWebPlatformPermanentSecurityManager * *)
0x1800314a3  call    cs:__imp_SetWebPlatformSecurityManagerFactoryCallback
0x1800314a9  mov     ebx, eax
0x1800314ab  test    eax, eax
0x1800314ad  jnz     short loc_1800314C2
0x1800314af  mov     rcx, cs:?s_spSecurityManager@WPCSecurityManager@@0V?$CComObjPtr@VWPCSecurityManager@@@@A; CComObjPtr<WPCSecurityManager> WPCSecurityManager::s_spSecurityManager
0x1800314b6  call    cs:__imp_RegisterWebPlatformPermanentSecurityManager
0x1800314bc  mov     ebx, eax
0x1800314be  test    eax, eax
0x1800314c0  jz      short loc_1800314E5
0x1800314c2  test    ebx, ebx
0x1800314c4  mov     esi, 80004005h
0x1800314c9  cmovns  ebx, esi
0x1800314cc  mov     rcx, r13; lpCriticalSection
0x1800314cf  call    cs:__imp_LeaveCriticalSection
0x1800314d5  nop
0x1800314d6  mov     rcx, r13; lpCriticalSection
0x1800314d9  call    cs:__imp_LeaveCriticalSection
0x1800314df  test    ebx, ebx
0x1800314e1  jns     short loc_18003152C
0x1800314e3  jmp     short loc_18003152A
0x1800314e5  lea     rcx, a44a9a18eA2ae45; "{44A9A18E-A2AE-4554-B56E-085F7471105F}"
0x1800314ec  call    cs:__imp_AddAtomW
0x1800314f2  mov     rcx, r13; lpCriticalSection
0x1800314f5  call    cs:__imp_LeaveCriticalSection
0x1800314fb  mov     rbx, cs:?s_spSecurityManager@WPCSecurityManager@@0V?$CComObjPtr@VWPCSecurityManager@@@@A; CComObjPtr<WPCSecurityManager> WPCSecurityManager::s_spSecurityManager
0x180031502  test    rbx, rbx
0x180031505  jz      short loc_180031517
0x180031507  mov     rax, [rbx]
0x18003150a  mov     rcx, rbx
0x18003150d  mov     rax, [rax+8]
0x180031511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031516  nop
0x180031517  test    rbx, rbx
0x18003151a  jnz     short loc_180031533
0x18003151c  mov     rcx, r13; lpCriticalSection
0x18003151f  call    cs:__imp_LeaveCriticalSection
0x180031525  mov     ebx, 80004002h
0x18003152a  mov     esi, ebx
0x18003152c  mov     eax, esi
0x18003152e  jmp     loc_180031693
0x180031533  mov     rax, [rbx]
0x180031536  mov     rcx, rbx
0x180031539  mov     rax, [rax+8]
0x18003153d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031542  mov     [rbp+57h+arg_18], rbx
0x180031546  mov     rax, [rbx]
0x180031549  mov     rcx, rbx
0x18003154c  mov     rax, [rax+10h]
0x180031550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031555  nop
0x180031556  mov     rcx, r13; lpCriticalSection
0x180031559  call    cs:__imp_LeaveCriticalSection
0x18003155f  mov     [rsp+130h+var_E4], r12
0x180031564  mov     [rsp+130h+var_DC], r12d
0x180031569  mov     [rbp+57h+var_CC], r12
0x18003156d  mov     [rbp+57h+var_C4], r12d
0x180031571  mov     [rsp+130h+var_110], 50h ; 'P'
0x180031579  mov     [rsp+130h+var_10C], 2
0x180031581  mov     [rsp+130h+var_108], r12
0x180031586  lea     rax, aInternetexplor; "InternetExplorer"
0x18003158d  mov     [rsp+130h+var_100], rax
0x180031592  mov     [rsp+130h+var_F8], rax
0x180031597  mov     [rsp+130h+var_F0], r12
0x18003159c  mov     [rsp+130h+var_D8], r12
0x1800315a1  mov     [rbp+57h+var_D0], r12d
0x1800315a5  mov     [rsp+130h+var_E8], 4000701h
0x1800315ad  mov     edi, 80h
0x1800315b2  mov     r8d, edi; Size
0x1800315b5  xor     edx, edx; Val
0x1800315b7  lea     rcx, [rbp+57h+var_B0]; void *
0x1800315bb  call    memset_0
0x1800315c0  mov     [rbp+57h+var_B0], edi
0x1800315c3  test    r14, r14
0x1800315c6  jz      short loc_1800315D2
0x1800315c8  lea     rax, [r14+8]
0x1800315cc  mov     [rbp+57h+var_A8], rax
0x1800315d0  jmp     short loc_1800315D6
0x1800315d2  mov     [rbp+57h+var_A8], r12
0x1800315d6  xorps   xmm0, xmm0
0x1800315d9  movdqa  [rbp+57h+var_A0], xmm0
0x1800315de  mov     rax, [r15]
0x1800315e1  mov     [rbp+57h+var_90], rax
0x1800315e5  mov     [rbp+57h+var_88], r12
0x1800315e9  mov     [rbp+57h+var_80], rbx
0x1800315ed  mov     [rbp+57h+var_78], r12
0x1800315f1  movdqa  [rbp+57h+var_70], xmm0
0x1800315f6  xorps   xmm1, xmm1
0x1800315f9  movdqa  [rbp+57h+var_60], xmm1
0x1800315fe  lea     r9, [r14+68h]
0x180031602  lea     r8, _GUID_dedcdb67_0e27_4593_81e5_437734383fd2
0x180031609  lea     rdx, [rbp+57h+var_B0]
0x18003160d  lea     rcx, [rsp+130h+var_110]
0x180031612  call    cs:__imp_GetWebPlatformObject
0x180031618  mov     edi, eax
0x18003161a  test    eax, eax
0x18003161c  jz      short loc_180031641
0x18003161e  mov     esi, 80004005h
0x180031623  test    eax, eax
0x180031625  cmovns  edi, esi
0x180031628  test    rbx, rbx
0x18003162b  jz      short loc_18003163D
0x18003162d  mov     rcx, [rbx]
0x180031630  mov     rax, [rcx+10h]
0x180031634  mov     rcx, rbx
0x180031637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003163c  nop
0x18003163d  mov     eax, edi
0x18003163f  jmp     short loc_180031693
0x180031641  mov     rcx, [r14+68h]
0x180031645  mov     rax, [rcx]
0x180031648  lea     rdx, [r14+70h]
0x18003164c  mov     rax, [rax+68h]
0x180031650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031655  mov     edi, eax
0x180031657  test    eax, eax
0x180031659  jz      short loc_18003167C
0x18003165b  mov     esi, 80004005h
0x180031660  test    eax, eax
0x180031662  cmovns  edi, esi
0x180031665  test    rbx, rbx
0x180031668  jz      short loc_18003167A
0x18003166a  mov     rcx, [rbx]
0x18003166d  mov     rax, [rcx+10h]
0x180031671  mov     rcx, rbx
0x180031674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031679  nop
0x18003167a  jmp     short loc_18003163D
0x18003167c  test    rbx, rbx
0x18003167f  jz      short loc_180031691
0x180031681  mov     rax, [rbx]
0x180031684  mov     rcx, rbx
0x180031687  mov     rax, [rax+10h]
0x18003168b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031690  nop
0x180031691  xor     eax, eax
0x180031693  mov     rbx, [rsp+130h+arg_0]
0x18003169b  add     rsp, 100h
0x1800316a2  pop     r15
0x1800316a4  pop     r14
0x1800316a6  pop     r13
0x1800316a8  pop     r12
0x1800316aa  pop     rdi
0x1800316ab  pop     rsi
0x1800316ac  pop     rbp
0x1800316ad  retn
```
