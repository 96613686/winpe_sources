# CSingleViewShellExperience::RuntimeClassInitialize(IWeakReferenceSource *,IServiceProvider *,HSTRING__ *,HSTRING__ *)

- ea: `0x180013220`
- end: `0x180013714`
- name: `?RuntimeClassInitialize@CSingleViewShellExperience@@QEAAJPEAUIWeakReferenceSource@@PEAUIServiceProvider@@PEAUHSTRING__@@2@Z`
- size: `1268`
- prototype: `__int64 __usercall@<rax>(CSingleViewShellExperience *__hidden this@<rcx>, struct IWeakReferenceSource *@<rdx>, struct IServiceProvider *@<r8>, HSTRING@<r9>, HSTRING)`
- caller_count: `8`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011310`
- `0x1800117e4`
- `0x18001f630`
- `0x1800c51a8`
- `0x180204600`
- `0x18021b4a0`
- `0x1802296c0`
- `0x18022cc90`

## callees

- `0x180009dfc`
- `0x1800115c4`
- `0x180013220`
- `0x1800378dc`
- `0x180037b9c`
- `0x1800eb924`
- `0x180142e10`
- `0x180145275`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013265`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800132a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800132da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013265`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800132a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800132da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001327a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800132b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800132ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001327a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800132b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800132ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013414`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013414`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180013446`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180013446`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSingleViewShellExperience::RuntimeClassInitialize(
        CSingleViewShellExperience *this,
        struct IWeakReferenceSource *a2,
        struct IServiceProvider *a3,
        HSTRING a4,
        HSTRING string)
{
  HSTRING *v9; // r15
  HRESULT v10; // ebx
  HSTRING *v11; // rbx
  HRESULT v12; // eax
  unsigned int v13; // edi
  HSTRING v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  _QWORD *v18; // r12
  __int64 v19; // rdx
  HRESULT v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  HSTRING v24; // rbx
  _QWORD *v25; // r14
  __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  HRESULT (__stdcall *QueryService)(IServiceProvider *, const GUID *const, const IID *const, void **); // rbx
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v32)(_QWORD, GUID *, __int64 *); // rbx
  int v33; // eax
  wil::details::in1diag3 *v34; // rcx
  __int64 v35; // rdx
  int v36; // [rsp+20h] [rbp-58h]
  __int64 v37; // [rsp+30h] [rbp-48h] BYREF
  __int64 v38; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-38h] BYREF
  HSTRING v40; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v9 = (HSTRING *)((char *)this + 8);
  if ( !a4 || a4 != *v9 )
  {
    WindowsDeleteString(*v9);
    *v9 = 0;
    v10 = WindowsDuplicateString(a4, v9);
    if ( v10 < 0 )
    {
      v19 = 67;
      goto LABEL_19;
    }
  }
  v11 = (HSTRING *)((char *)this + 16);
  if ( !string || string != *v11 )
  {
    WindowsDeleteString(*v11);
    *v11 = 0;
    v12 = WindowsDuplicateString(string, (HSTRING *)this + 2);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\singleviewexperience.cpp",
        (const char *)(unsigned int)v12,
        v36);
      return v13;
    }
  }
  v14 = *v11;
  if ( !v14 || v14 != *(HSTRING *)this )
  {
    WindowsDeleteString(*(HSTRING *)this);
    *(_QWORD *)this = 0;
    v10 = WindowsDuplicateString(v14, (HSTRING *)this);
    if ( v10 < 0 )
    {
      v19 = 69;
      goto LABEL_19;
    }
  }
  v15 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = 0;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  v38 = 0;
  v10 = ((__int64 (__fastcall *)(struct IWeakReferenceSource *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
          a2,
          &GUID_00000038_0000_0000_c000_000000000046,
          &v38);
  v16 = v38;
  if ( v10 < 0 )
    goto LABEL_14;
  v37 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 24LL))(v38, &v37);
  if ( v10 < 0 )
  {
    v17 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v16 = v38;
LABEL_14:
    if ( v16 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    goto LABEL_16;
  }
  v26 = v37;
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
  v27 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = v26;
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  v28 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v10 = 0;
LABEL_16:
  if ( v10 < 0 )
  {
    v19 = 71;
    goto LABEL_19;
  }
  v18 = (_QWORD *)((char *)this + 80);
  v10 = (*(__int64 (__fastcall **)(_QWORD, CSingleViewShellExperience *, char *))(**((_QWORD **)this + 11) + 136LL))(
          *((_QWORD *)this + 11),
          this,
          (char *)this + 80);
  if ( v10 < 0 )
  {
    v19 = 73;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\singleviewexperience.cpp",
      (const char *)(unsigned int)v10,
      v36);
    return (unsigned int)v10;
  }
  v40 = 0;
  v21 = WindowsCreateStringReference(L"Windows.Foundation.Collections.PropertySet", 0x2Au, &hstringHeader, &v40);
  if ( v21 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
    __debugbreak();
  }
  v24 = v40;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 32);
  *((_QWORD *)this + 4) = 0;
  v37 = 0;
  v10 = RoActivateInstance(v24, &v37);
  if ( v10 >= 0 )
  {
    if ( !memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *((_QWORD *)this + 4) = v37;
    }
    else
    {
      v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v37)(
              v37,
              &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
              (char *)this + 32);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
  }
  if ( v10 < 0 )
  {
    v19 = 76;
    goto LABEL_19;
  }
  if ( (*((_BYTE *)this + 132) & 0x10) == 0 )
  {
    QueryService = a3->lpVtbl->QueryService;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 104);
    v10 = ((__int64 (__fastcall *)(struct IServiceProvider *, GUID *, GUID *, char *))QueryService)(
            a3,
            &GUID_be47f3f2_56c0_40dd_a5ad_ba88325ea0ce,
            &GUID_69bb2711_c5f2_41da_8d6d_448a336a24c5,
            (char *)this + 104);
    if ( v10 < 0 )
    {
      v19 = 80;
      goto LABEL_19;
    }
  }
  v25 = (_QWORD *)((char *)this + 112);
  v10 = CSingleViewShellExperience::RegisterAumid(this, *v9, (struct EventRegistrationToken *)this + 14);
  if ( v10 < 0 )
  {
    v19 = 83;
    goto LABEL_19;
  }
  if ( (*((_BYTE *)this + 132) & 4) == 0 || !*v25 )
    goto LABEL_28;
  v37 = 0;
  v31 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 13);
  v32 = **v31;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v33 = v32(v31, &GUID_b18447e2_209d_43d3_add5_a3434f4d558b, &v37);
  v34 = retaddr;
  if ( v33 < 0 )
  {
    v35 = 90;
    goto LABEL_58;
  }
  v33 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v37 + 48LL))(v37, *v25);
  v34 = retaddr;
  if ( v33 < 0 )
  {
    v35 = 92;
LABEL_58:
    wil::details::in1diag3::_Log_Hr(
      v34,
      (void *)v35,
      (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\singleviewexperience.cpp",
      (const char *)(unsigned int)v33,
      v36);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
LABEL_28:
  v10 = (*(__int64 (__fastcall **)(_QWORD, struct IServiceProvider *))(*(_QWORD *)*v18 + 16LL))(*v18, a3);
  if ( v10 < 0 )
  {
    v19 = 97;
    goto LABEL_19;
  }
  if ( (*((_BYTE *)this + 132) & 1) != 0 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, struct IServiceProvider *))(*(_QWORD *)*v18 + 24LL))(*v18, a3);
    if ( v10 < 0 )
    {
      v19 = 103;
      goto LABEL_19;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180013220  push    rbp
0x180013222  push    rbx
0x180013223  push    rsi
0x180013224  push    rdi
0x180013225  push    r12
0x180013227  push    r13
0x180013229  push    r14
0x18001322b  push    r15
0x18001322d  mov     rbp, rsp
0x180013230  sub     rsp, 78h
0x180013234  mov     rax, cs:__security_cookie
0x18001323b  xor     rax, rsp
0x18001323e  mov     [rbp+var_18], rax
0x180013242  mov     rbx, r9
0x180013245  mov     r13, r8
0x180013248  mov     r14, rdx
0x18001324b  mov     rsi, rcx
0x18001324e  mov     rdi, [rbp+string]
0x180013252  lea     r15, [rcx+8]
0x180013256  xor     r12d, r12d
0x180013259  test    r9, r9
0x18001325c  jnz     loc_1800134F3
0x180013262  mov     rcx, [r15]; string
0x180013265  call    cs:__imp_WindowsDeleteString
0x18001326c  nop     dword ptr [rax+rax+00h]
0x180013271  mov     [r15], r12
0x180013274  mov     rdx, r15; newString
0x180013277  mov     rcx, rbx; string
0x18001327a  call    cs:__imp_WindowsDuplicateString
0x180013281  nop     dword ptr [rax+rax+00h]
0x180013286  mov     ebx, eax
0x180013288  test    eax, eax
0x18001328a  js      loc_180013633
0x180013290  lea     rbx, [rsi+10h]
0x180013294  test    rdi, rdi
0x180013297  jnz     loc_180013501
0x18001329d  mov     rcx, [rbx]; string
0x1800132a0  call    cs:__imp_WindowsDeleteString
0x1800132a7  nop     dword ptr [rax+rax+00h]
0x1800132ac  mov     [rbx], r12
0x1800132af  mov     rdx, rbx; newString
0x1800132b2  mov     rcx, rdi; string
0x1800132b5  call    cs:__imp_WindowsDuplicateString
0x1800132bc  nop     dword ptr [rax+rax+00h]
0x1800132c1  mov     edi, eax
0x1800132c3  test    eax, eax
0x1800132c5  js      loc_1800136C2
0x1800132cb  mov     rbx, [rbx]
0x1800132ce  test    rbx, rbx
0x1800132d1  jnz     loc_18001350F
0x1800132d7  mov     rcx, [rsi]; string
0x1800132da  call    cs:__imp_WindowsDeleteString
0x1800132e1  nop     dword ptr [rax+rax+00h]
0x1800132e6  mov     [rsi], r12
0x1800132e9  mov     rdx, rsi; newString
0x1800132ec  mov     rcx, rbx; string
0x1800132ef  call    cs:__imp_WindowsDuplicateString
0x1800132f6  nop     dword ptr [rax+rax+00h]
0x1800132fb  mov     ebx, eax
0x1800132fd  test    eax, eax
0x1800132ff  js      loc_1800136E1
0x180013305  mov     rcx, [rsi+60h]
0x180013309  mov     [rsi+60h], r12
0x18001330d  test    rcx, rcx
0x180013310  jz      short loc_18001331F
0x180013312  mov     rax, [rcx]
0x180013315  mov     rax, [rax+10h]
0x180013319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001331e  nop
0x18001331f  mov     [rbp+var_40], r12
0x180013323  mov     rax, [r14]
0x180013326  lea     r8, [rbp+var_40]
0x18001332a  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x180013331  mov     rcx, r14
0x180013334  mov     rax, [rax]
0x180013337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001333c  mov     ebx, eax
0x18001333e  mov     rcx, [rbp+var_40]
0x180013342  test    eax, eax
0x180013344  js      short loc_180013381
0x180013346  mov     [rbp+var_48], r12
0x18001334a  mov     rax, [rcx]
0x18001334d  lea     rdx, [rbp+var_48]
0x180013351  mov     rax, [rax+18h]
0x180013355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001335a  mov     ebx, eax
0x18001335c  test    eax, eax
0x18001335e  jns     loc_18001354D
0x180013364  mov     rcx, [rbp+var_48]
0x180013368  test    rcx, rcx
0x18001336b  jz      short loc_18001337D
0x18001336d  mov     [rbp+var_48], r12
0x180013371  mov     rax, [rcx]
0x180013374  mov     rax, [rax+10h]
0x180013378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001337d  mov     rcx, [rbp+var_40]
0x180013381  test    rcx, rcx
0x180013384  jz      short loc_180013397
0x180013386  mov     [rbp+var_40], r12
0x18001338a  mov     rax, [rcx]
0x18001338d  mov     rax, [rax+10h]
0x180013391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013396  nop
0x180013397  test    ebx, ebx
0x180013399  js      loc_1800136EB
0x18001339f  mov     rcx, [rsi+58h]
0x1800133a3  lea     r12, [rsi+50h]
0x1800133a7  mov     rax, [rcx]
0x1800133aa  mov     r8, r12
0x1800133ad  mov     rdx, rsi
0x1800133b0  mov     rax, [rax+88h]
0x1800133b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133bc  mov     ebx, eax
0x1800133be  xor     r14d, r14d
0x1800133c1  test    eax, eax
0x1800133c3  jns     short loc_1800133FC
0x1800133c5  lea     edx, [r14+49h]; void *
0x1800133c9  mov     rcx, [rbp+40h]; this
0x1800133cd  mov     r9d, ebx; char *
0x1800133d0  lea     r8, aShellTwinuiExp_6; "shell\\twinui\\experiencemanagers\\core"...
0x1800133d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800133dc  mov     eax, ebx
0x1800133de  mov     rcx, [rbp+var_18]
0x1800133e2  xor     rcx, rsp; StackCookie
0x1800133e5  call    __security_check_cookie
0x1800133ea  add     rsp, 78h
0x1800133ee  pop     r15
0x1800133f0  pop     r14
0x1800133f2  pop     r13
0x1800133f4  pop     r12
0x1800133f6  pop     rdi
0x1800133f7  pop     rsi
0x1800133f8  pop     rbx
0x1800133f9  pop     rbp
0x1800133fa  retn
0x1800133fc  mov     [rbp+var_20], r14
0x180013400  lea     r9, [rbp+var_20]; string
0x180013404  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180013408  mov     edx, 2Ah ; '*'; length
0x18001340d  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x180013414  call    cs:__imp_WindowsCreateStringReference
0x18001341b  nop     dword ptr [rax+rax+00h]
0x180013420  test    eax, eax
0x180013422  js      loc_1800136F5
0x180013428  lea     rdi, [rsi+20h]
0x18001342c  mov     rbx, [rbp+var_20]
0x180013430  mov     rcx, rdi
0x180013433  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013438  mov     [rdi], r14
0x18001343b  mov     [rbp+var_48], r14
0x18001343f  lea     rdx, [rbp+var_48]
0x180013443  mov     rcx, rbx
0x180013446  call    cs:__imp_RoActivateInstance
0x18001344d  nop     dword ptr [rax+rax+00h]
0x180013452  mov     ebx, eax
0x180013454  test    eax, eax
0x180013456  js      short loc_180013480
0x180013458  mov     r8d, 10h; Size
0x18001345e  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180013465  lea     rcx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; Buf1
0x18001346c  call    memcmp_0
0x180013471  test    eax, eax
0x180013473  jnz     loc_18001351D
0x180013479  mov     rax, [rbp+var_48]
0x18001347d  mov     [rdi], rax
0x180013480  test    ebx, ebx
0x180013482  js      loc_18001363D
0x180013488  lea     rdi, [rsi+68h]
0x18001348c  test    byte ptr [rsi+84h], 10h
0x180013493  jz      loc_1800135C2
0x180013499  lea     r14, [rsi+70h]
0x18001349d  mov     r8, r14; struct EventRegistrationToken *
0x1800134a0  mov     rdx, [r15]; HSTRING
0x1800134a3  mov     rcx, rsi; this
0x1800134a6  call    ?RegisterAumid@CSingleViewShellExperience@@AEAAJPEAUHSTRING__@@PEAUEventRegistrationToken@@@Z; CSingleViewShellExperience::RegisterAumid(HSTRING__ *,EventRegistrationToken *)
0x1800134ab  mov     ebx, eax
0x1800134ad  test    eax, eax
0x1800134af  js      loc_1800135B8
0x1800134b5  test    byte ptr [rsi+84h], 4
0x1800134bc  jnz     loc_1800136FD
0x1800134c2  mov     rcx, [r12]
0x1800134c6  mov     rax, [rcx]
0x1800134c9  mov     rdx, r13
0x1800134cc  mov     rax, [rax+10h]
0x1800134d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134d5  mov     ebx, eax
0x1800134d7  test    eax, eax
0x1800134d9  js      loc_180013602
0x1800134df  test    byte ptr [rsi+84h], 1
0x1800134e6  jnz     loc_18001360C
0x1800134ec  xor     eax, eax
0x1800134ee  jmp     loc_1800133DE
0x1800134f3  cmp     rbx, [r15]
0x1800134f6  jnz     loc_180013262
0x1800134fc  jmp     loc_180013290
0x180013501  cmp     rdi, [rbx]
0x180013504  jnz     loc_18001329D
0x18001350a  jmp     loc_1800132CB
0x18001350f  cmp     rbx, [rsi]
0x180013512  jnz     loc_1800132D7
0x180013518  jmp     loc_180013305
0x18001351d  mov     rcx, [rbp+var_48]
0x180013521  mov     rax, [rcx]
0x180013524  mov     r8, rdi
0x180013527  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x18001352e  mov     rax, [rax]
0x180013531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013536  mov     ebx, eax
0x180013538  mov     rcx, [rbp+var_48]
0x18001353c  mov     rax, [rcx]
0x18001353f  mov     rax, [rax+10h]
0x180013543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013548  jmp     loc_180013480
0x18001354d  mov     rbx, [rbp+var_48]
0x180013551  test    rbx, rbx
0x180013554  jz      short loc_180013565
0x180013556  mov     rax, [rbx]
0x180013559  mov     rcx, rbx
0x18001355c  mov     rax, [rax+8]
0x180013560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013565  mov     rcx, [rsi+60h]
0x180013569  mov     [rsi+60h], rbx
0x18001356d  test    rcx, rcx
0x180013570  jz      short loc_18001357E
0x180013572  mov     rax, [rcx]
0x180013575  mov     rax, [rax+10h]
0x180013579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001357e  mov     rcx, [rbp+var_48]
0x180013582  test    rcx, rcx
0x180013585  jz      short loc_180013597
0x180013587  mov     [rbp+var_48], r12
0x18001358b  mov     rax, [rcx]
0x18001358e  mov     rax, [rax+10h]
0x180013592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013597  mov     rcx, [rbp+var_40]
0x18001359b  test    rcx, rcx
0x18001359e  jz      short loc_1800135B0
0x1800135a0  mov     [rbp+var_40], r12
0x1800135a4  mov     rax, [rcx]
0x1800135a7  mov     rax, [rax+10h]
0x1800135ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135b0  mov     ebx, r12d
0x1800135b3  jmp     loc_180013397
0x1800135b8  mov     edx, 53h ; 'S'
0x1800135bd  jmp     loc_1800133C9
0x1800135c2  mov     rax, [r13+0]
0x1800135c6  mov     rbx, [rax+18h]
0x1800135ca  mov     rcx, rdi
0x1800135cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800135d2  mov     r9, rdi
0x1800135d5  lea     r8, _GUID_69bb2711_c5f2_41da_8d6d_448a336a24c5
0x1800135dc  lea     rdx, _GUID_be47f3f2_56c0_40dd_a5ad_ba88325ea0ce
0x1800135e3  mov     rcx, r13
0x1800135e6  mov     rax, rbx
0x1800135e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135ee  mov     ebx, eax
0x1800135f0  test    eax, eax
0x1800135f2  jns     loc_180013499
0x1800135f8  mov     edx, 50h ; 'P'
0x1800135fd  jmp     loc_1800133C9
0x180013602  mov     edx, 61h ; 'a'
0x180013607  jmp     loc_1800133C9
0x18001360c  mov     rcx, [r12]
0x180013610  mov     rax, [rcx]
0x180013613  mov     rdx, r13
0x180013616  mov     rax, [rax+18h]
0x18001361a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001361f  mov     ebx, eax
0x180013621  test    eax, eax
0x180013623  jns     loc_1800134EC
0x180013629  mov     edx, 67h ; 'g'
0x18001362e  jmp     loc_1800133C9
0x180013633  mov     edx, 43h ; 'C'
0x180013638  jmp     loc_1800133C9
0x18001363d  mov     edx, 4Ch ; 'L'
0x180013642  jmp     loc_1800133C9
0x180013647  mov     [rbp+var_48], 0
0x18001364f  mov     rdi, [rdi]
0x180013652  mov     rax, [rdi]
0x180013655  mov     rbx, [rax]
0x180013658  lea     rcx, [rbp+var_48]
0x18001365c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013661  lea     r8, [rbp+var_48]
0x180013665  lea     rdx, _GUID_b18447e2_209d_43d3_add5_a3434f4d558b
0x18001366c  mov     rcx, rdi
0x18001366f  mov     rax, rbx
0x180013672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013677  nop
0x180013678  mov     rcx, [rbp+40h]
0x18001367c  test    eax, eax
0x18001367e  js      loc_18001370C
0x180013684  mov     rcx, [rbp+var_48]
0x180013688  mov     rax, [rcx]
0x18001368b  mov     rdx, [r14]
0x18001368e  mov     rax, [rax+30h]
0x180013692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013697  mov     rcx, [rbp+40h]; this
0x18001369b  test    eax, eax
0x18001369d  jns     short loc_1800136B4
0x18001369f  mov     edx, 5Ch ; '\'; void *
  ... truncated ...
```
