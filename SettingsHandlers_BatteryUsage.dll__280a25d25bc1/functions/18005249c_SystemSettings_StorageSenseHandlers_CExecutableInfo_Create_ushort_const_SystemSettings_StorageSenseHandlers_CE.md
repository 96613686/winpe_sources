# SystemSettings::StorageSenseHandlers::CExecutableInfo::Create(ushort const *,SystemSettings::StorageSenseHandlers::CExecutableInfo * *)

- ea: `0x18005249c`
- end: `0x1800526a4`
- name: `?Create@CExecutableInfo@StorageSenseHandlers@SystemSettings@@SAJPEBGPEAPEAV123@@Z`
- size: `520`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers *this, struct SystemSettings::StorageSenseHandlers::CExecutableInfo **)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003fb8c`
- `0x18003ff70`

## callees

- `0x1800028d0`
- `0x1800033a0`
- `0x180004cfc`
- `0x180010c8c`
- `0x180013be0`
- `0x18001d728`
- `0x180021534`
- `0x180051a50`
- `0x180051b34`
- `0x180051d0c`
- `0x18005222c`
- `0x18005249c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180052554`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180052554`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180052623`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18005264c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180052623`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18005264c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::StorageSenseHandlers::CExecutableInfo::Create(
        SystemSettings::StorageSenseHandlers *this,
        struct SystemSettings::StorageSenseHandlers::CExecutableInfo **a2)
{
  __int64 v4; // rsi
  HRESULT v5; // ebx
  unsigned __int16 *v6; // r8
  unsigned int v7; // r9d
  void *v8; // rdi
  __int64 (__fastcall *v9)(void *, _QWORD, __int64 *); // rbx
  unsigned __int64 v10; // r14
  const unsigned __int16 *v11; // r9
  unsigned int v12; // r8d
  const unsigned __int16 *v13; // rdx
  char v14; // r8
  char v15; // r8
  unsigned int v17[2]; // [rsp+20h] [rbp-E0h] BYREF
  void *ppv; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h]
  __int64 v21; // [rsp+40h] [rbp-C0h]
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF

  *a2 = 0;
  Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CExecutableInfo,>(v17);
  v4 = *(_QWORD *)v17;
  if ( *(_QWORD *)v17 )
  {
    *(_BYTE *)(*(_QWORD *)v17 + 108LL) = 0;
    memset_0(pszPath, 0, 0x208u);
    v5 = SystemSettings::StorageSenseHandlers::ConvertDOSAppPathToDriveAppPath(this, pszPath, v6, v7);
    if ( v5 < 0 )
    {
      ppv = PathFindFileNameW((LPCWSTR)this);
      Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
        (Microsoft::WRL::Wrappers::HString *)(v4 + 88),
        (__int64 *)&ppv,
        v15);
      goto LABEL_18;
    }
    ppv = 0;
    Microsoft::WRL::Wrappers::HString::Set<260>(v4 + 96, pszPath);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v5 = SHCreateItemFromParsingName(pszPath, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
    if ( v5 < 0 )
      goto LABEL_16;
    v5 = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Initialize<IShellItem2>(v4 + 32, ppv);
    if ( v5 < 0 )
    {
LABEL_15:
      *(_QWORD *)v17 = PathFindFileNameW((LPCWSTR)this);
      Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
        (Microsoft::WRL::Wrappers::HString *)(v4 + 88),
        (__int64 *)v17,
        v14);
      goto LABEL_16;
    }
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v8 = ppv;
    v9 = *(__int64 (__fastcall **)(void *, _QWORD, __int64 *))(*(_QWORD *)ppv + 40LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
    v10 = -1;
    v20 = -1;
    v21 = -1;
    v5 = v9(v8, 0, &v19);
    if ( v5 >= 0 )
    {
      if ( !v19 )
      {
        v12 = 0;
        v13 = &word_180065238;
        goto LABEL_13;
      }
      v17[0] = 0;
      do
        ++v10;
      while ( *(_WORD *)(v19 + 2 * v10) );
      v5 = ULongLongToUInt(v10, v17);
      if ( v5 >= 0 )
      {
        v12 = v17[0];
        v13 = v11;
LABEL_13:
        v5 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)(v4 + 88), v13, v12);
      }
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
    if ( v5 < 0 )
      goto LABEL_15;
LABEL_16:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
LABEL_18:
    *(_QWORD *)v17 = 0;
    *a2 = (struct SystemSettings::StorageSenseHandlers::CExecutableInfo *)v4;
    goto LABEL_19;
  }
  v5 = -2147024882;
LABEL_19:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005249c  mov     [rsp-8+arg_10], rbx
0x1800524a1  push    rbp
0x1800524a2  push    rsi
0x1800524a3  push    rdi
0x1800524a4  push    r12
0x1800524a6  push    r13
0x1800524a8  push    r14
0x1800524aa  push    r15
0x1800524ac  lea     rbp, [rsp-170h]
0x1800524b4  sub     rsp, 270h
0x1800524bb  mov     rax, cs:__security_cookie
0x1800524c2  xor     rax, rsp
0x1800524c5  mov     [rbp+1A0h+var_40], rax
0x1800524cc  mov     r12, rdx
0x1800524cf  mov     r15, rcx
0x1800524d2  xor     r13d, r13d
0x1800524d5  mov     [rdx], r13
0x1800524d8  lea     rcx, [rsp+2A0h+var_280]
0x1800524dd  call    ??$Make@VCExecutableInfo@StorageSenseHandlers@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCExecutableInfo@StorageSenseHandlers@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CExecutableInfo,>(void)
0x1800524e2  nop
0x1800524e3  mov     rsi, qword ptr [rsp+2A0h+var_280]
0x1800524e8  test    rsi, rsi
0x1800524eb  jnz     short loc_1800524F7
0x1800524ed  mov     ebx, 8007000Eh
0x1800524f2  jmp     loc_18005266E
0x1800524f7  mov     [rsi+6Ch], r13b
0x1800524fb  xor     edx, edx; Val
0x1800524fd  mov     r8d, 208h; Size
0x180052503  lea     rcx, [rsp+2A0h+pszPath]; void *
0x180052508  call    memset_0
0x18005250d  lea     rdx, [rsp+2A0h+pszPath]; unsigned __int16 *
0x180052512  mov     rcx, r15; this
0x180052515  call    ?ConvertDOSAppPathToDriveAppPath@StorageSenseHandlers@SystemSettings@@YAJPEBGPEAGK@Z; SystemSettings::StorageSenseHandlers::ConvertDOSAppPathToDriveAppPath(ushort const *,ushort *,ulong)
0x18005251a  mov     ebx, eax
0x18005251c  test    eax, eax
0x18005251e  js      loc_180052649
0x180052524  mov     [rsp+2A0h+ppv], r13
0x180052529  lea     rcx, [rsi+60h]
0x18005252d  lea     rdx, [rsp+2A0h+pszPath]
0x180052532  call    ??$Set@$0BAE@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HString::Set<260>(ushort (&)[260])
0x180052537  lea     rcx, [rsp+2A0h+ppv]
0x18005253c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052541  lea     r9, [rsp+2A0h+ppv]; ppv
0x180052546  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18005254d  xor     edx, edx; pbc
0x18005254f  lea     rcx, [rsp+2A0h+pszPath]; pszPath
0x180052554  call    cs:__imp_SHCreateItemFromParsingName
0x18005255a  mov     ebx, eax
0x18005255c  test    eax, eax
0x18005255e  js      loc_18005263D
0x180052564  lea     rcx, [rsi+20h]
0x180052568  mov     rdx, [rsp+2A0h+ppv]
0x18005256d  call    ??$Initialize@UIShellItem2@@@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@QEAAJPEAUIShellItem2@@@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Initialize<IShellItem2>(IShellItem2 *)
0x180052572  mov     ebx, eax
0x180052574  test    eax, eax
0x180052576  js      loc_180052620
0x18005257c  mov     [rsp+2A0h+var_270], r13
0x180052581  mov     [rsp+2A0h+var_268], r13
0x180052586  mov     [rsp+2A0h+var_260], r13
0x18005258b  mov     rdi, [rsp+2A0h+ppv]
0x180052590  mov     rax, [rdi]
0x180052593  mov     rbx, [rax+28h]
0x180052597  lea     rcx, [rsp+2A0h+var_270]
0x18005259c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800525a1  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800525a5  mov     [rsp+2A0h+var_268], r14
0x1800525aa  mov     [rsp+2A0h+var_260], r14
0x1800525af  lea     r8, [rsp+2A0h+var_270]
0x1800525b4  xor     edx, edx
0x1800525b6  mov     rcx, rdi
0x1800525b9  mov     rax, rbx
0x1800525bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800525c1  mov     ebx, eax
0x1800525c3  test    eax, eax
0x1800525c5  js      short loc_180052612
0x1800525c7  mov     r9, [rsp+2A0h+var_270]
0x1800525cc  test    r9, r9
0x1800525cf  jz      short loc_1800525FD
0x1800525d1  mov     [rsp+2A0h+var_280], r13d
0x1800525d6  inc     r14
0x1800525d9  cmp     [r9+r14*2], r13w
0x1800525de  jnz     short loc_1800525D6
0x1800525e0  lea     rdx, [rsp+2A0h+var_280]; unsigned int *
0x1800525e5  mov     rcx, r14; unsigned __int64
0x1800525e8  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800525ed  mov     ebx, eax
0x1800525ef  test    eax, eax
0x1800525f1  js      short loc_180052612
0x1800525f3  mov     r8d, [rsp+2A0h+var_280]
0x1800525f8  mov     rdx, r9
0x1800525fb  jmp     short loc_180052607
0x1800525fd  xor     r8d, r8d; unsigned int
0x180052600  lea     rdx, word_180065238; unsigned __int16 *
0x180052607  lea     rcx, [rsi+58h]; this
0x18005260b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180052610  mov     ebx, eax
0x180052612  lea     rcx, [rsp+2A0h+var_270]
0x180052617  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005261c  test    ebx, ebx
0x18005261e  jns     short loc_18005263D
0x180052620  mov     rcx, r15; pszPath
0x180052623  call    cs:__imp_PathFindFileNameW
0x180052629  mov     qword ptr [rsp+2A0h+var_280], rax
0x18005262e  lea     rcx, [rsi+58h]
0x180052632  lea     rdx, [rsp+2A0h+var_280]
0x180052637  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18005263c  nop
0x18005263d  lea     rcx, [rsp+2A0h+ppv]
0x180052642  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052647  jmp     short loc_180052665
0x180052649  mov     rcx, r15; pszPath
0x18005264c  call    cs:__imp_PathFindFileNameW
0x180052652  mov     [rsp+2A0h+ppv], rax
0x180052657  lea     rcx, [rsi+58h]
0x18005265b  lea     rdx, [rsp+2A0h+ppv]
0x180052660  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180052665  mov     qword ptr [rsp+2A0h+var_280], r13
0x18005266a  mov     [r12], rsi
0x18005266e  lea     rcx, [rsp+2A0h+var_280]
0x180052673  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052678  mov     eax, ebx
0x18005267a  mov     rcx, [rbp+1A0h+var_40]
0x180052681  xor     rcx, rsp; StackCookie
0x180052684  call    __security_check_cookie
0x180052689  mov     rbx, [rsp+2A0h+arg_10]
0x180052691  add     rsp, 270h
0x180052698  pop     r15
0x18005269a  pop     r14
0x18005269c  pop     r13
0x18005269e  pop     r12
0x1800526a0  pop     rdi
0x1800526a1  pop     rsi
0x1800526a2  pop     rbp
0x1800526a3  retn
```
