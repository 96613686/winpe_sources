# GEL::DWriteFontLinker::DWriteFontLinker(wchar_t const *,uint,GEL::DWriteTypefaceList const &,GEL::Font const &,uint)

- ea: `0x1800b0108`
- end: `0x1800b039c`
- name: `??0DWriteFontLinker@GEL@@QEAA@PEB_WIAEBVDWriteTypefaceList@1@AEBUFont@1@I@Z`
- size: `660`
- prototype: `__int64 __fastcall(GEL::DWriteFontLinker *__hidden this, const wchar_t *, unsigned int, const struct GEL::DWriteTypefaceList *, const struct GEL::Font *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180112fa0`
- `0x18018f160`

## callees

- `0x1800565ba`
- `0x1800578b0`
- `0x180057e70`
- `0x1800909b8`
- `0x1800afac0`
- `0x1800b0108`

## import_xrefs

- `KERNEL32!LCIDToLocaleName` at `0x1800b0185`
- `KERNEL32!LCIDToLocaleName` at `0x1800b0185`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1800b02c3`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1800b0309`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1800b02c3`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1800b0309`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x1800b01fe`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x1800b030f`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x1800b01fe`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x1800b030f`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1800b0172`
- `Mso30Win32Client!__imp_MsoGetInstallLcid` at `0x1800b0172`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800b02ac`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800b02ac`

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
  __int64 v10; // rax
  Mso::DWriteAssistant *v11; // rcx
  __int64 v12; // rdx
  struct Mso::DWriteAssistant::ResourceManager *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  GEL::Typeface *v17; // rsi
  const wchar_t *v18; // r8
  Mso::DWriteAssistant *v19; // rcx
  struct Mso::DWriteAssistant::ResourceManager *ResourceManagerInstance; // rax
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v24[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+B0h] [rbp-50h]
  int v26; // [rsp+B8h] [rbp-48h]
  WCHAR Name[88]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Destination[88]; // [rsp+170h] [rbp+70h] BYREF

  *(_QWORD *)this = 0;
  memset_0((char *)this + 8, 0, 0x5Cu);
  memset_0((char *)this + 100, 0, 0x5Cu);
  *((_DWORD *)this + 48) = a3;
  InstallLcid = MsoGetInstallLcid();
  if ( !LCIDToLocaleName(InstallLcid, Name, 85, 0) )
    goto LABEL_15;
  while ( 1 )
  {
    memset_0(&v23, 0, 0x5Cu);
    GEL::CreateDWAFontFromGelFont(&v22, a4, a5, &v23);
    if ( v22 )
      break;
    CrashWithRecovery(0x1E3C3840u, 0);
LABEL_15:
    wcscpy_s(Name, 0x55u, L"en-us");
  }
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 24LL))(v22);
  v12 = v10;
  v21 = v10;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  if ( BYTE5(xmmword_180523DD0) )
  {
    v17 = (GEL::Typeface *)*a5;
    if ( (*(unsigned __int8 (__fastcall **)(const void *, __int64))(*(_QWORD *)*a5 + 32LL))(*a5, v12) )
      v18 = GEL::Typeface::InternalName(v17, 4u, a5[3]);
    else
      v18 = (const wchar_t *)v24 + 6;
    wcscpy_s(Destination, 0x55u, v18);
    ResourceManagerInstance = Mso::DWriteAssistant::GetResourceManagerInstance(v19);
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
    v13 = Mso::DWriteAssistant::GetResourceManagerInstance(v11);
    (*(void (__fastcall **)(_QWORD, const wchar_t *, _QWORD, __int64 *, WCHAR *, int, GEL::DWriteFontLinker *))(**((_QWORD **)v13 + 10) + 80LL))(
      *((_QWORD *)v13 + 10),
      a2,
      a3,
      &v21,
      Name,
      4,
      this);
  }
  if ( *(_QWORD *)this )
  {
    *(_OWORD *)((char *)this + 8) = v23;
    *(_OWORD *)((char *)this + 24) = v24[0];
    *(_OWORD *)((char *)this + 40) = v24[1];
    *(_OWORD *)((char *)this + 56) = v24[2];
    *(_OWORD *)((char *)this + 72) = v24[3];
    *((_QWORD *)this + 11) = v25;
    *((_DWORD *)this + 24) = v26;
  }
  v14 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  }
  return this;
}

```

## disassembly

```asm
0x1800b0108  push    rbp
0x1800b010a  push    rbx
0x1800b010b  push    rsi
0x1800b010c  push    rdi
0x1800b010d  push    r12
0x1800b010f  push    r14
0x1800b0111  push    r15
0x1800b0113  lea     rbp, [rsp-130h]
0x1800b011b  sub     rsp, 230h
0x1800b0122  mov     rax, cs:__security_cookie
0x1800b0129  xor     rax, rsp
0x1800b012c  mov     [rbp+160h+var_40], rax
0x1800b0133  mov     rsi, r9
0x1800b0136  mov     r15d, r8d
0x1800b0139  mov     r12, rdx
0x1800b013c  mov     rdi, rcx
0x1800b013f  mov     r14, [rbp+160h+arg_20]
0x1800b0146  mov     qword ptr [rcx], 0
0x1800b014d  xor     edx, edx; Val
0x1800b014f  lea     r8d, [rdx+5Ch]; Size
0x1800b0153  add     rcx, 8; void *
0x1800b0157  call    memset_0
0x1800b015c  lea     rcx, [rdi+64h]; void *
0x1800b0160  xor     edx, edx; Val
0x1800b0162  lea     r8d, [rdx+5Ch]; Size
0x1800b0166  call    memset_0
0x1800b016b  mov     [rdi+0C0h], r15d
0x1800b0172  call    cs:__imp_MsoGetInstallLcid
0x1800b0178  mov     ecx, eax; Locale
0x1800b017a  xor     r9d, r9d; dwFlags
0x1800b017d  lea     r8d, [r9+55h]; cchName
0x1800b0181  lea     rdx, [rbp+160h+Name]; lpName
0x1800b0185  call    cs:__imp_LCIDToLocaleName
0x1800b018b  test    eax, eax
0x1800b018d  jz      loc_1800B02B3
0x1800b0193  xor     edx, edx; Val
0x1800b0195  lea     r8d, [rdx+5Ch]; Size
0x1800b0199  lea     rcx, [rsp+260h+var_200]; void *
0x1800b019e  call    memset_0
0x1800b01a3  lea     r9, [rsp+260h+var_200]
0x1800b01a8  mov     r8, r14
0x1800b01ab  mov     rdx, rsi
0x1800b01ae  lea     rcx, [rsp+260h+var_208]
0x1800b01b3  call    ?CreateDWAFontFromGelFont@GEL@@YA?AV?$TCntPtr@UIFont@DWriteAssistant@Mso@@@Mso@@AEBUITypefaceList@1@AEBUFont@1@PEAUtagLOGFONTW@@@Z; GEL::CreateDWAFontFromGelFont(GEL::ITypefaceList const &,GEL::Font const &,tagLOGFONTW *)
0x1800b01b8  mov     rcx, [rsp+260h+var_208]
0x1800b01bd  test    rcx, rcx
0x1800b01c0  jz      loc_1800B02A5
0x1800b01c6  mov     rax, [rcx]
0x1800b01c9  mov     rax, [rax+18h]
0x1800b01cd  call    cs:__guard_dispatch_icall_fptr
0x1800b01d3  mov     rdx, rax
0x1800b01d6  mov     [rsp+260h+var_210], rax
0x1800b01db  test    rax, rax
0x1800b01de  jz      short loc_1800B01F1
0x1800b01e0  mov     rcx, [rax]
0x1800b01e3  mov     rax, [rcx+8]
0x1800b01e7  mov     rcx, rdx
0x1800b01ea  call    cs:__guard_dispatch_icall_fptr
0x1800b01f0  nop
0x1800b01f1  cmp     byte ptr cs:xmmword_180523DD0+5, 0
0x1800b01f8  jnz     loc_1800B02CE
0x1800b01fe  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x1800b0204  mov     rcx, [rax+50h]
0x1800b0208  mov     rax, [rcx]
0x1800b020b  mov     [rsp+260h+var_230], rdi
0x1800b0210  mov     dword ptr [rsp+260h+var_238], 4
0x1800b0218  lea     rdx, [rbp+160h+Name]
0x1800b021c  mov     [rsp+260h+var_240], rdx
0x1800b0221  lea     r9, [rsp+260h+var_210]
0x1800b0226  mov     r8d, r15d
0x1800b0229  mov     rdx, r12
0x1800b022c  mov     rax, [rax+50h]
0x1800b0230  call    cs:__guard_dispatch_icall_fptr
0x1800b0236  cmp     qword ptr [rdi], 0
0x1800b023a  jnz     loc_1800B035C
0x1800b0240  mov     rcx, [rsp+260h+var_210]
0x1800b0245  test    rcx, rcx
0x1800b0248  jz      short loc_1800B0261
0x1800b024a  mov     [rsp+260h+var_210], 0
0x1800b0253  mov     rax, [rcx]
0x1800b0256  mov     rax, [rax+10h]
0x1800b025a  call    cs:__guard_dispatch_icall_fptr
0x1800b0260  nop
0x1800b0261  mov     rcx, [rsp+260h+var_208]
0x1800b0266  test    rcx, rcx
0x1800b0269  jz      short loc_1800B0281
0x1800b026b  mov     [rsp+260h+var_208], 0
0x1800b0274  mov     rdx, [rcx]
0x1800b0277  mov     rax, [rdx+8]
0x1800b027b  call    cs:__guard_dispatch_icall_fptr
0x1800b0281  mov     rax, rdi
0x1800b0284  mov     rcx, [rbp+160h+var_40]
0x1800b028b  xor     rcx, rsp; StackCookie
0x1800b028e  call    __security_check_cookie
0x1800b0293  add     rsp, 230h
0x1800b029a  pop     r15
0x1800b029c  pop     r14
0x1800b029e  pop     r12
0x1800b02a0  pop     rdi
0x1800b02a1  pop     rsi
0x1800b02a2  pop     rbx
0x1800b02a3  pop     rbp
0x1800b02a4  retn
0x1800b02a5  xor     edx, edx
0x1800b02a7  mov     ecx, 1E3C3840h
0x1800b02ac  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800b02b2  nop
0x1800b02b3  lea     r8, aEnUs; "en-us"
0x1800b02ba  mov     edx, 55h ; 'U'; SizeInWords
0x1800b02bf  lea     rcx, [rbp+160h+Name]; Destination
0x1800b02c3  call    cs:__imp_wcscpy_s
0x1800b02c9  jmp     loc_1800B0193
0x1800b02ce  mov     rsi, [r14]
0x1800b02d1  mov     rax, [rsi]
0x1800b02d4  mov     rcx, rsi
0x1800b02d7  mov     rax, [rax+20h]
0x1800b02db  call    cs:__guard_dispatch_icall_fptr
0x1800b02e1  test    al, al
0x1800b02e3  jnz     short loc_1800B02EC
0x1800b02e5  lea     r8, [rsp+260h+var_1E4]
0x1800b02ea  jmp     short loc_1800B0300
0x1800b02ec  mov     r8, [r14+18h]; void *
0x1800b02f0  mov     edx, 4; unsigned int
0x1800b02f5  mov     rcx, rsi; this
0x1800b02f8  call    ?InternalName@Typeface@GEL@@QEBAPEB_WIPEBX@Z; GEL::Typeface::InternalName(uint,void const *)
0x1800b02fd  mov     r8, rax; Source
0x1800b0300  mov     edx, 55h ; 'U'; SizeInWords
0x1800b0305  lea     rcx, [rbp+160h+Destination]; Destination
0x1800b0309  call    cs:__imp_wcscpy_s
0x1800b030f  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x1800b0315  mov     rcx, [rax+50h]
0x1800b0319  mov     rax, [rcx]
0x1800b031c  mov     [rsp+260h+var_220], rdi
0x1800b0321  mov     [rsp+260h+var_228], 4
0x1800b0329  mov     dword ptr [rsp+260h+var_230], 0
0x1800b0331  mov     [rsp+260h+var_238], 0
0x1800b033a  lea     rdx, [rbp+160h+Name]
0x1800b033e  mov     [rsp+260h+var_240], rdx
0x1800b0343  lea     r9, [rbp+160h+Destination]
0x1800b0347  mov     r8d, r15d
0x1800b034a  mov     rdx, r12
0x1800b034d  mov     rax, [rax+58h]
0x1800b0351  call    cs:__guard_dispatch_icall_fptr
0x1800b0357  jmp     loc_1800B0236
0x1800b035c  movaps  xmm0, [rsp+260h+var_200]
0x1800b0361  movups  xmmword ptr [rdi+8], xmm0
0x1800b0365  movaps  xmm1, xmmword ptr [rsp+70h]
0x1800b036a  movups  xmmword ptr [rdi+18h], xmm1
0x1800b036e  movaps  xmm0, [rbp+160h+var_1E0]
0x1800b0372  movups  xmmword ptr [rdi+28h], xmm0
0x1800b0376  movaps  xmm1, [rbp+160h+var_1D0]
0x1800b037a  movups  xmmword ptr [rdi+38h], xmm1
0x1800b037e  movaps  xmm0, [rbp+160h+var_1C0]
0x1800b0382  movups  xmmword ptr [rdi+48h], xmm0
0x1800b0386  movsd   xmm1, [rbp+160h+var_1B0]
0x1800b038b  movsd   qword ptr [rdi+58h], xmm1
0x1800b0390  mov     eax, [rbp+160h+var_1A8]
0x1800b0393  mov     [rdi+60h], eax
0x1800b0396  jmp     loc_1800B0240
```
