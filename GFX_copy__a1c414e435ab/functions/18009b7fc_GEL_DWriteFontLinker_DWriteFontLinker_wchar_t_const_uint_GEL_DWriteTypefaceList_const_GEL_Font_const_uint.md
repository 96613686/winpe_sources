# GEL::DWriteFontLinker::DWriteFontLinker(wchar_t const *,uint,GEL::DWriteTypefaceList const &,GEL::Font const &,uint)

- ea: `0x18009b7fc`
- end: `0x18009ba8d`
- name: `??0DWriteFontLinker@GEL@@QEAA@PEB_WIAEBVDWriteTypefaceList@1@AEBUFont@1@I@Z`
- size: `657`
- prototype: `__int64 __fastcall(GEL::DWriteFontLinker *__hidden this, const wchar_t *, unsigned int, const struct GEL::DWriteTypefaceList *, const struct GEL::Font *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180117340`
- `0x180117fd0`

## callees

- `0x180055b26`
- `0x180056ee0`
- `0x1800573f0`
- `0x180079ad4`
- `0x18009a02c`
- `0x18009b7fc`

## import_xrefs

- `KERNEL32!LCIDToLocaleName` at `0x18009b879`
- `KERNEL32!LCIDToLocaleName` at `0x18009b879`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x18009b9b4`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x18009b9fa`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x18009b9b4`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x18009b9fa`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18009b8fd`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18009ba00`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18009b8fd`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18009ba00`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x18009b866`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x18009b866`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18009b8bd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18009b8bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
GEL::DWriteFontLinker *__fastcall GEL::DWriteFontLinker::DWriteFontLinker(
        GEL::DWriteFontLinker *this,
        const wchar_t *a2,
        unsigned int a3,
        const struct GEL::DWriteTypefaceList *a4,
        const void **a5)
{
  LCID InstallLcid; // eax
  __int64 v10; // rcx
  __int64 v11; // rax
  Mso::DWriteAssistant *v12; // rcx
  __int64 v13; // rdx
  struct Mso::DWriteAssistant::ResourceManager *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  GEL::Typeface *v18; // rsi
  const wchar_t *v19; // r8
  Mso::DWriteAssistant *v20; // rcx
  struct Mso::DWriteAssistant::ResourceManager *ResourceManagerInstance; // rax
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v24; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v25[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+B0h] [rbp-50h]
  int v27; // [rsp+B8h] [rbp-48h]
  WCHAR Name[88]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Destination[88]; // [rsp+170h] [rbp+70h] BYREF

  *(_QWORD *)this = 0;
  memset_0((char *)this + 8, 0, 0x5Cu);
  memset_0((char *)this + 100, 0, 0x5Cu);
  *((_DWORD *)this + 48) = a3;
  InstallLcid = MsoGetInstallLcid();
  if ( !LCIDToLocaleName(InstallLcid, Name, 85, 0) )
    wcscpy_s(Name, 0x55u, L"en-us");
  memset_0(&v24, 0, 0x5Cu);
  GEL::CreateDWAFontFromGelFont(&v23, a4, a5, &v24);
  v10 = v23;
  if ( !v23 )
    CrashWithRecovery(0x1E3C3840u, 0);
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 24LL))(v10);
  v13 = v11;
  v22 = v11;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  if ( BYTE5(xmmword_18051FD50) )
  {
    v18 = (GEL::Typeface *)*a5;
    if ( (*(unsigned __int8 (__fastcall **)(const void *, __int64))(*(_QWORD *)*a5 + 32LL))(*a5, v13) )
      v19 = GEL::Typeface::InternalName(v18, 4u, a5[3]);
    else
      v19 = (const wchar_t *)v25 + 6;
    wcscpy_s(Destination, 0x55u, v19);
    ResourceManagerInstance = Mso::DWriteAssistant::GetResourceManagerInstance(v20);
    (*(void (__fastcall **)(_QWORD, const wchar_t *, _QWORD, wchar_t *, WCHAR *, _QWORD, _DWORD, int, GEL::DWriteFontLinker *))(**((_QWORD **)ResourceManagerInstance + 10) + 88LL))(
      *((_QWORD *)ResourceManagerInstance + 10),
      a2,
      a3,
      Destination,
      Name,
      0,
      0,
      4,
      this);
  }
  else
  {
    v14 = Mso::DWriteAssistant::GetResourceManagerInstance(v12);
    (*(void (__fastcall **)(_QWORD, const wchar_t *, _QWORD, __int64 *, WCHAR *, int, GEL::DWriteFontLinker *))(**((_QWORD **)v14 + 10) + 80LL))(
      *((_QWORD *)v14 + 10),
      a2,
      a3,
      &v22,
      Name,
      4,
      this);
  }
  if ( *(_QWORD *)this )
  {
    *(_OWORD *)((char *)this + 8) = v24;
    *(_OWORD *)((char *)this + 24) = v25[0];
    *(_OWORD *)((char *)this + 40) = v25[1];
    *(_OWORD *)((char *)this + 56) = v25[2];
    *(_OWORD *)((char *)this + 72) = v25[3];
    *((_QWORD *)this + 11) = v26;
    *((_DWORD *)this + 24) = v27;
  }
  v15 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
  }
  return this;
}

```

## disassembly

```asm
0x18009b7fc  push    rbp
0x18009b7fe  push    rbx
0x18009b7ff  push    rsi
0x18009b800  push    rdi
0x18009b801  push    r12
0x18009b803  push    r14
0x18009b805  push    r15
0x18009b807  lea     rbp, [rsp-130h]
0x18009b80f  sub     rsp, 230h
0x18009b816  mov     rax, cs:__security_cookie
0x18009b81d  xor     rax, rsp
0x18009b820  mov     [rbp+160h+var_40], rax
0x18009b827  mov     rsi, r9
0x18009b82a  mov     r15d, r8d
0x18009b82d  mov     r12, rdx
0x18009b830  mov     rdi, rcx
0x18009b833  mov     r14, [rbp+160h+arg_20]
0x18009b83a  mov     qword ptr [rcx], 0
0x18009b841  xor     edx, edx; Val
0x18009b843  lea     r8d, [rdx+5Ch]; Size
0x18009b847  add     rcx, 8; void *
0x18009b84b  call    memset_0
0x18009b850  lea     rcx, [rdi+64h]; void *
0x18009b854  xor     edx, edx; Val
0x18009b856  lea     r8d, [rdx+5Ch]; Size
0x18009b85a  call    memset_0
0x18009b85f  mov     [rdi+0C0h], r15d
0x18009b866  call    cs:__imp_MsoGetInstallLcid
0x18009b86c  mov     ecx, eax; Locale
0x18009b86e  xor     r9d, r9d; dwFlags
0x18009b871  lea     r8d, [r9+55h]; cchName
0x18009b875  lea     rdx, [rbp+160h+Name]; lpName
0x18009b879  call    cs:__imp_LCIDToLocaleName
0x18009b87f  test    eax, eax
0x18009b881  jz      loc_18009B9A4
0x18009b887  xor     edx, edx; Val
0x18009b889  lea     r8d, [rdx+5Ch]; Size
0x18009b88d  lea     rcx, [rsp+260h+var_200]; void *
0x18009b892  call    memset_0
0x18009b897  lea     r9, [rsp+260h+var_200]
0x18009b89c  mov     r8, r14
0x18009b89f  mov     rdx, rsi
0x18009b8a2  lea     rcx, [rsp+260h+var_208]
0x18009b8a7  call    ?CreateDWAFontFromGelFont@GEL@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@Mso@@AEBUITypefaceList@1@AEBUFont@1@PEAUtagLOGFONTW@@@Z; GEL::CreateDWAFontFromGelFont(GEL::ITypefaceList const &,GEL::Font const &,tagLOGFONTW *)
0x18009b8ac  mov     rcx, [rsp+260h+var_208]
0x18009b8b1  test    rcx, rcx
0x18009b8b4  jnz     short loc_18009B8C4
0x18009b8b6  xor     edx, edx
0x18009b8b8  mov     ecx, 1E3C3840h
0x18009b8bd  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18009b8c3  nop
0x18009b8c4  mov     rax, [rcx]
0x18009b8c7  mov     rax, [rax+18h]
0x18009b8cb  call    cs:__guard_dispatch_icall_fptr
0x18009b8d1  mov     rdx, rax
0x18009b8d4  mov     [rsp+260h+var_210], rax
0x18009b8d9  test    rax, rax
0x18009b8dc  jz      short loc_18009B8F0
0x18009b8de  mov     rcx, [rax]
0x18009b8e1  mov     rax, [rcx+8]
0x18009b8e5  mov     rcx, rdx
0x18009b8e8  call    cs:__guard_dispatch_icall_fptr
0x18009b8ee  nop
0x18009b8ef  nop
0x18009b8f0  cmp     byte ptr cs:xmmword_18051FD50+5, 0
0x18009b8f7  jnz     loc_18009B9BF
0x18009b8fd  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x18009b903  mov     rcx, [rax+50h]
0x18009b907  mov     rax, [rcx]
0x18009b90a  mov     [rsp+260h+var_230], rdi
0x18009b90f  mov     dword ptr [rsp+260h+var_238], 4
0x18009b917  lea     rdx, [rbp+160h+Name]
0x18009b91b  mov     [rsp+260h+var_240], rdx
0x18009b920  lea     r9, [rsp+260h+var_210]
0x18009b925  mov     r8d, r15d
0x18009b928  mov     rdx, r12
0x18009b92b  mov     rax, [rax+50h]
0x18009b92f  call    cs:__guard_dispatch_icall_fptr
0x18009b935  cmp     qword ptr [rdi], 0
0x18009b939  jnz     loc_18009BA4D
0x18009b93f  mov     rcx, [rsp+260h+var_210]
0x18009b944  test    rcx, rcx
0x18009b947  jz      short loc_18009B960
0x18009b949  mov     [rsp+260h+var_210], 0
0x18009b952  mov     rax, [rcx]
0x18009b955  mov     rax, [rax+10h]
0x18009b959  call    cs:__guard_dispatch_icall_fptr
0x18009b95f  nop
0x18009b960  mov     rcx, [rsp+260h+var_208]
0x18009b965  test    rcx, rcx
0x18009b968  jz      short loc_18009B980
0x18009b96a  mov     [rsp+260h+var_208], 0
0x18009b973  mov     rdx, [rcx]
0x18009b976  mov     rax, [rdx+8]
0x18009b97a  call    cs:__guard_dispatch_icall_fptr
0x18009b980  mov     rax, rdi
0x18009b983  mov     rcx, [rbp+160h+var_40]
0x18009b98a  xor     rcx, rsp; StackCookie
0x18009b98d  call    __security_check_cookie
0x18009b992  add     rsp, 230h
0x18009b999  pop     r15
0x18009b99b  pop     r14
0x18009b99d  pop     r12
0x18009b99f  pop     rdi
0x18009b9a0  pop     rsi
0x18009b9a1  pop     rbx
0x18009b9a2  pop     rbp
0x18009b9a3  retn
0x18009b9a4  lea     r8, aEnUs; "en-us"
0x18009b9ab  mov     edx, 55h ; 'U'; SizeInWords
0x18009b9b0  lea     rcx, [rbp+160h+Name]; Destination
0x18009b9b4  call    cs:__imp_wcscpy_s
0x18009b9ba  jmp     loc_18009B887
0x18009b9bf  mov     rsi, [r14]
0x18009b9c2  mov     rax, [rsi]
0x18009b9c5  mov     rcx, rsi
0x18009b9c8  mov     rax, [rax+20h]
0x18009b9cc  call    cs:__guard_dispatch_icall_fptr
0x18009b9d2  test    al, al
0x18009b9d4  jnz     short loc_18009B9DD
0x18009b9d6  lea     r8, [rsp+260h+var_1E4]
0x18009b9db  jmp     short loc_18009B9F1
0x18009b9dd  mov     r8, [r14+18h]; void *
0x18009b9e1  mov     edx, 4; unsigned int
0x18009b9e6  mov     rcx, rsi; this
0x18009b9e9  call    ?InternalName@Typeface@GEL@@QEBAPEB_WIPEBX@Z; GEL::Typeface::InternalName(uint,void const *)
0x18009b9ee  mov     r8, rax; Source
0x18009b9f1  mov     edx, 55h ; 'U'; SizeInWords
0x18009b9f6  lea     rcx, [rbp+160h+Destination]; Destination
0x18009b9fa  call    cs:__imp_wcscpy_s
0x18009ba00  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x18009ba06  mov     rcx, [rax+50h]
0x18009ba0a  mov     rax, [rcx]
0x18009ba0d  mov     [rsp+260h+var_220], rdi
0x18009ba12  mov     [rsp+260h+var_228], 4
0x18009ba1a  mov     dword ptr [rsp+260h+var_230], 0
0x18009ba22  mov     [rsp+260h+var_238], 0
0x18009ba2b  lea     rdx, [rbp+160h+Name]
0x18009ba2f  mov     [rsp+260h+var_240], rdx
0x18009ba34  lea     r9, [rbp+160h+Destination]
0x18009ba38  mov     r8d, r15d
0x18009ba3b  mov     rdx, r12
0x18009ba3e  mov     rax, [rax+58h]
0x18009ba42  call    cs:__guard_dispatch_icall_fptr
0x18009ba48  jmp     loc_18009B935
0x18009ba4d  movaps  xmm0, [rsp+260h+var_200]
0x18009ba52  movups  xmmword ptr [rdi+8], xmm0
0x18009ba56  movaps  xmm1, xmmword ptr [rsp+70h]
0x18009ba5b  movups  xmmword ptr [rdi+18h], xmm1
0x18009ba5f  movaps  xmm0, [rbp+160h+var_1E0]
0x18009ba63  movups  xmmword ptr [rdi+28h], xmm0
0x18009ba67  movaps  xmm1, [rbp+160h+var_1D0]
0x18009ba6b  movups  xmmword ptr [rdi+38h], xmm1
0x18009ba6f  movaps  xmm0, [rbp+160h+var_1C0]
0x18009ba73  movups  xmmword ptr [rdi+48h], xmm0
0x18009ba77  movsd   xmm1, [rbp+160h+var_1B0]
0x18009ba7c  movsd   qword ptr [rdi+58h], xmm1
0x18009ba81  mov     eax, [rbp+160h+var_1A8]
0x18009ba84  mov     [rdi+60h], eax
0x18009ba87  jmp     loc_18009B93F
```
