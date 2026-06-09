# CloudPrint::CloudPrintHelper::GetTokenResult(bool,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics> &,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> &,Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount> &,bool,HWND__ *,Windows::Security::Authentication::Web::Core::WebTokenRequestStatus *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>>)

- ea: `0x180017144`
- end: `0x1800173fd`
- name: `?GetTokenResult@CloudPrintHelper@CloudPrint@@KAJ_NAEAV?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@45@AEAV?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@45@0PEAUHWND__@@PEAW4WebTokenRequestStatus@Core@Web@Authentication@Security@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@45@@Z`
- size: `697`
- prototype: `__int64 __fastcall(char, __int64 **, _QWORD *, _QWORD *, char, HWND, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180013a2c`

## callees

- `0x180009fc0`
- `0x18000c4cc`
- `0x1800108f8`
- `0x180012700`
- `0x180017144`
- `0x18001b0e8`
- `0x18001bfe4`
- `0x18002b010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x18001720a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x18001720a`

## string_xrefs

- `0x180017164`: `GetTokenResult`

## pseudocode

```c
__int64 __fastcall CloudPrint::CloudPrintHelper::GetTokenResult(
        char a1,
        __int64 **a2,
        _QWORD *a3,
        _QWORD *a4,
        char a5,
        HWND a6,
        __int64 a7,
        _QWORD *a8)
{
  __int64 *v12; // rbx
  __int64 v13; // rdi
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  const char *v17; // rax
  __int64 v18; // rdx
  HWND DesktopWindow; // rsi
  __int64 *v20; // rdi
  __int64 (__fastcall *v21)(__int64 *, GUID *, _QWORD **); // rbx
  int v22; // eax
  __int64 v23; // rdx
  _QWORD *v24; // rdi
  __int64 v25; // rax
  __int64 (__fastcall *v26)(_QWORD *, HWND, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v27)(_QWORD *, HWND, _QWORD, GUID *); // rbx
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // rsi
  DWORD v29; // edx
  int v30; // r8d
  int v31; // edi
  GUID *v33; // [rsp+20h] [rbp-79h]
  const char *v34; // [rsp+28h] [rbp-71h]
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-59h] BYREF
  _QWORD *v36; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v37[128]; // [rsp+50h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+3Fh]

  CloudPrintHelperTelemetry::WatchCurrentThread(v37, "GetTokenResult");
  v35 = 0;
  if ( a1 )
  {
    v12 = *a2;
    v13 = **a2;
    if ( *a4 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
      v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v13 + 56))(
              v12,
              *a3,
              *a4,
              &v35);
      v15 = v14;
      if ( v14 < 0 )
      {
        v16 = 2240;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
          (const char *)(unsigned int)v14,
          (int)v33);
        goto LABEL_31;
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
      v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(v13 + 48))(v12, *a3, &v35);
      v15 = v14;
      if ( v14 < 0 )
      {
        v16 = 2245;
        goto LABEL_27;
      }
    }
    goto LABEL_21;
  }
  if ( a5 )
  {
    if ( a6 )
    {
      v17 = "Both promptOnDesktopWindow AND appWindow cannot be specified at the same time";
      v18 = 2253;
LABEL_30:
      v15 = -2147024809;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v18,
        (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
        (const char *)0x80070057LL,
        (int)v17,
        v34);
      goto LABEL_31;
    }
    DesktopWindow = GetDesktopWindow();
  }
  else
  {
    DesktopWindow = a6;
    if ( !a6 )
    {
      v17 = "Either promptOnDesktopWindow OR appWindow must be specified";
      v18 = 2265;
      goto LABEL_30;
    }
  }
  v36 = 0;
  v20 = *a2;
  v21 = *(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD **))*v20;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  v22 = v21(v20, &GUID_f4b8e804_811e_4436_b69c_44cb67b72084, &v36);
  v15 = v22;
  if ( v22 < 0 )
  {
    v23 = 2270;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
      (const char *)(unsigned int)v22,
      (int)v33);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    goto LABEL_31;
  }
  v24 = v36;
  v25 = *v36;
  if ( *a4 )
  {
    v26 = *(__int64 (__fastcall **)(_QWORD *, HWND, _QWORD, _QWORD))(v25 + 56);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    v33 = &GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9;
    v22 = v26(v24, DesktopWindow, *a3, *a4);
    v15 = v22;
    if ( v22 < 0 )
    {
      v23 = 2277;
      goto LABEL_14;
    }
  }
  else
  {
    v27 = *(__int64 (__fastcall **)(_QWORD *, HWND, _QWORD, GUID *))(v25 + 48);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    v33 = (GUID *)&v35;
    v22 = v27(v24, DesktopWindow, *a3, &GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9);
    v15 = v22;
    if ( v22 < 0 )
    {
      v23 = 2281;
      goto LABEL_14;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
LABEL_21:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a8);
  v28 = v35;
  v31 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(
          v35,
          v29,
          v30);
  if ( v31 >= 0 )
    v31 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD *))(*v28)[8])(v28, a8);
  if ( v31 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a8 + 56LL))(*a8, a7);
    v15 = v14;
    if ( v14 >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v37);
      return 0;
    }
    v16 = 2287;
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8EE,
    (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
    (const char *)(unsigned int)v31,
    (int)v33);
  v15 = v31;
LABEL_31:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v37);
  return v15;
}

```

## disassembly

```asm
0x180017144  push    rbp
0x180017146  push    rbx
0x180017147  push    rsi
0x180017148  push    rdi
0x180017149  push    r14
0x18001714b  push    r15
0x18001714d  lea     rbp, [rsp-0Fh]
0x180017152  sub     rsp, 0A8h
0x180017159  mov     r14, r9
0x18001715c  mov     r15, r8
0x18001715f  mov     rdi, rdx
0x180017162  mov     bl, cl
0x180017164  lea     rdx, aGettokenresult; "GetTokenResult"
0x18001716b  lea     rcx, [rbp+37h+var_80]
0x18001716f  call    ?WatchCurrentThread@CloudPrintHelperTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; CloudPrintHelperTelemetry::WatchCurrentThread(char const *)
0x180017174  nop
0x180017175  mov     [rbp+37h+var_90], 0
0x18001717d  test    bl, bl
0x18001717f  jz      short loc_1800171EC
0x180017181  mov     rbx, [rdi]
0x180017184  mov     rdi, [rbx]
0x180017187  lea     rcx, [rbp+37h+var_90]
0x18001718b  cmp     qword ptr [r14], 0
0x18001718f  jz      short loc_1800171C0
0x180017191  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017196  lea     r9, [rbp+37h+var_90]
0x18001719a  mov     r8, [r14]
0x18001719d  mov     rdx, [r15]
0x1800171a0  mov     rcx, rbx
0x1800171a3  mov     rax, [rdi+38h]
0x1800171a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171ac  mov     ebx, eax
0x1800171ae  test    eax, eax
0x1800171b0  jns     loc_180017312
0x1800171b6  mov     edx, 8C0h
0x1800171bb  jmp     loc_180017382
0x1800171c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800171c5  lea     r8, [rbp+37h+var_90]
0x1800171c9  mov     rdx, [r15]
0x1800171cc  mov     rcx, rbx
0x1800171cf  mov     rax, [rdi+30h]
0x1800171d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171d8  mov     ebx, eax
0x1800171da  test    eax, eax
0x1800171dc  jns     loc_180017312
0x1800171e2  mov     edx, 8C5h
0x1800171e7  jmp     loc_180017382
0x1800171ec  cmp     [rbp+37h+arg_20], 0
0x1800171f0  jz      short loc_180017215
0x1800171f2  cmp     [rbp+37h+arg_28], 0
0x1800171f7  jz      short loc_18001720A
0x1800171f9  lea     rax, aBothPromptonde; "Both promptOnDesktopWindow AND appWindo"...
0x180017200  mov     edx, 8CDh
0x180017205  jmp     loc_1800173BA
0x18001720a  call    cs:__imp_GetDesktopWindow
0x180017210  mov     rsi, rax
0x180017213  jmp     short loc_180017222
0x180017215  mov     rsi, [rbp+37h+arg_28]
0x180017219  test    rsi, rsi
0x18001721c  jz      loc_1800173AE
0x180017222  mov     [rbp+37h+var_88], 0
0x18001722a  mov     rdi, [rdi]
0x18001722d  mov     rax, [rdi]
0x180017230  mov     rbx, [rax]
0x180017233  lea     rcx, [rbp+37h+var_88]
0x180017237  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001723c  lea     r8, [rbp+37h+var_88]
0x180017240  lea     rdx, _GUID_f4b8e804_811e_4436_b69c_44cb67b72084
0x180017247  mov     rcx, rdi
0x18001724a  mov     rax, rbx
0x18001724d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017252  mov     ebx, eax
0x180017254  test    eax, eax
0x180017256  jns     short loc_18001727F
0x180017258  mov     edx, 8DEh; void *
0x18001725d  mov     rcx, [rbp+3Fh]; this
0x180017261  mov     r9d, eax; char *
0x180017264  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001726b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017270  nop
0x180017271  lea     rcx, [rbp+37h+var_88]
0x180017275  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001727a  jmp     loc_1800173D8
0x18001727f  mov     rdi, [rbp+37h+var_88]
0x180017283  lea     rcx, [rbp+37h+var_90]
0x180017287  mov     rax, [rdi]
0x18001728a  cmp     qword ptr [r14], 0
0x18001728e  jz      short loc_1800172CF
0x180017290  mov     rbx, [rax+38h]
0x180017294  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017299  lea     rax, [rbp+37h+var_90]
0x18001729d  mov     [rsp+0D0h+var_A8], rax
0x1800172a2  lea     r9, _GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9
0x1800172a9  mov     qword ptr [rsp+0D0h+var_B0], r9; int
0x1800172ae  mov     r9, [r14]
0x1800172b1  mov     r8, [r15]
0x1800172b4  mov     rdx, rsi
0x1800172b7  mov     rcx, rdi
0x1800172ba  mov     rax, rbx
0x1800172bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172c2  mov     ebx, eax
0x1800172c4  test    eax, eax
0x1800172c6  jns     short loc_180017309
0x1800172c8  mov     edx, 8E5h
0x1800172cd  jmp     short loc_18001725D
0x1800172cf  mov     rbx, [rax+30h]
0x1800172d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800172d8  lea     rax, [rbp+37h+var_90]
0x1800172dc  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800172e1  lea     r9, _GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9
0x1800172e8  mov     r8, [r15]
0x1800172eb  mov     rdx, rsi
0x1800172ee  mov     rcx, rdi
0x1800172f1  mov     rax, rbx
0x1800172f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172f9  mov     ebx, eax
0x1800172fb  test    eax, eax
0x1800172fd  jns     short loc_180017309
0x1800172ff  mov     edx, 8E9h
0x180017304  jmp     loc_18001725D
0x180017309  lea     rcx, [rbp+37h+var_88]
0x18001730d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017312  mov     rbx, [rbp+37h+arg_38]
0x180017316  mov     rcx, rbx
0x180017319  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001731e  mov     rsi, [rbp+37h+var_90]
0x180017322  mov     rcx, rsi
0x180017325  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18001732a  mov     edi, eax
0x18001732c  test    eax, eax
0x18001732e  js      short loc_180017344
0x180017330  mov     rax, [rsi]
0x180017333  mov     rdx, rbx
0x180017336  mov     rcx, rsi
0x180017339  mov     rax, [rax+40h]
0x18001733d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017342  mov     edi, eax
0x180017344  test    edi, edi
0x180017346  jns     short loc_180017364
0x180017348  mov     rcx, [rbp+3Fh]; this
0x18001734c  mov     r9d, edi; char *
0x18001734f  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180017356  mov     edx, 8EEh; void *
0x18001735b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017360  mov     ebx, edi
0x180017362  jmp     short loc_1800173D8
0x180017364  mov     rcx, [rbx]
0x180017367  mov     rax, [rcx]
0x18001736a  mov     rdx, [rbp+37h+arg_30]
0x18001736e  mov     rax, [rax+38h]
0x180017372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017377  mov     ebx, eax
0x180017379  test    eax, eax
0x18001737b  jns     short loc_180017397
0x18001737d  mov     edx, 8EFh; void *
0x180017382  mov     r9d, eax; char *
0x180017385  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001738c  mov     rcx, [rbp+3Fh]; this
0x180017390  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017395  jmp     short loc_1800173D8
0x180017397  lea     rcx, [rbp+37h+var_90]
0x18001739b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800173a0  nop
0x1800173a1  lea     rcx, [rbp+37h+var_80]; this
0x1800173a5  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800173aa  xor     eax, eax
0x1800173ac  jmp     short loc_1800173ED
0x1800173ae  lea     rax, aEitherPrompton; "Either promptOnDesktopWindow OR appWind"...
0x1800173b5  mov     edx, 8D9h; void *
0x1800173ba  mov     ebx, 80070057h
0x1800173bf  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800173c4  mov     r9d, ebx; char *
0x1800173c7  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x1800173ce  mov     rcx, [rbp+3Fh]; this
0x1800173d2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800173d7  nop
0x1800173d8  lea     rcx, [rbp+37h+var_90]
0x1800173dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800173e1  nop
0x1800173e2  lea     rcx, [rbp+37h+var_80]; this
0x1800173e6  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800173eb  mov     eax, ebx
0x1800173ed  add     rsp, 0A8h
0x1800173f4  pop     r15
0x1800173f6  pop     r14
0x1800173f8  pop     rdi
0x1800173f9  pop     rsi
0x1800173fa  pop     rbx
0x1800173fb  pop     rbp
0x1800173fc  retn
```
