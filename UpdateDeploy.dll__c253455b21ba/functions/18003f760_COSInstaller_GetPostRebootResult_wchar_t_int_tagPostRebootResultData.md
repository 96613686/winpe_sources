# COSInstaller::GetPostRebootResult(wchar_t *,int,tagPostRebootResultData *)

- ea: `0x18003f760`
- end: `0x18003fd75`
- name: `?GetPostRebootResult@COSInstaller@@UEAAJPEA_WHPEAUtagPostRebootResultData@@@Z`
- size: `1557`
- prototype: `int(COSInstaller *__hidden this, wchar_t *, int, struct tagPostRebootResultData *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180003180`
- `0x18000dce4`
- `0x1800110fc`
- `0x18003f760`
- `0x180041bac`
- `0x180042654`
- `0x180048bf0`
- `0x18004bb50`
- `0x18004fa38`
- `0x180061960`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18003f800`
- `OLEAUT32!__imp_SysStringLen` at `0x18003f800`

## string_xrefs

- `0x18003f829`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003fc94`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003fc50`: `GetPostRebootResultFromUpdateAgent failed`
- `0x18003fc0f`: `Updateagent is in use. Will try again later`
- `0x18003fcd0`: `Using product info to determine if the update was successfully installed`
- `0x18003fd1a`: `Reporting cookie product version and current installed product version match. We have successfully updated`

## pseudocode

```c
__int64 __fastcall COSInstaller::GetPostRebootResult(
        COSInstaller *this,
        wchar_t *a2,
        int a3,
        struct tagPostRebootResultData *a4)
{
  char v8; // r15
  int IsProductCurrent; // ebx
  __int64 v10; // rdx
  int v11; // edi
  __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  wchar_t *v16; // rbx
  char v17; // r14
  const wchar_t *v18; // rax
  COSInstaller *v19; // rcx
  int PostRebootResultFromUpdateAgent; // eax
  bool *v21; // r9
  int v22; // [rsp+20h] [rbp-A9h]
  wchar_t **v23; // [rsp+20h] [rbp-A9h]
  unsigned __int64 v24; // [rsp+70h] [rbp-59h] BYREF
  wchar_t *v25; // [rsp+78h] [rbp-51h] BYREF
  wchar_t *v26; // [rsp+80h] [rbp-49h] BYREF
  wchar_t *v27; // [rsp+88h] [rbp-41h] BYREF
  wchar_t *v28; // [rsp+90h] [rbp-39h] BYREF
  wchar_t *v29; // [rsp+98h] [rbp-31h] BYREF
  wchar_t *v30; // [rsp+A0h] [rbp-29h] BYREF
  void *lpMem; // [rsp+A8h] [rbp-21h] BYREF
  wchar_t *v32; // [rsp+B0h] [rbp-19h] BYREF
  wchar_t *v33; // [rsp+B8h] [rbp-11h] BYREF
  wchar_t *v34; // [rsp+C0h] [rbp-9h] BYREF
  wchar_t *v35; // [rsp+C8h] [rbp-1h] BYREF
  wchar_t v36[4]; // [rsp+D0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v30 = 0;
  v26 = 0;
  v29 = 0;
  v35 = 0;
  v28 = 0;
  v34 = 0;
  v27 = 0;
  v33 = 0;
  v32 = 0;
  lpMem = 0;
  v8 = 0;
  *(_QWORD *)v36 = 0;
  v25 = 0;
  LOBYTE(v24) = 0;
  WUTrace(0, 0, 4096, 4, 0, L"Enter GetPostRebootResult for Deployment handler. Reporting cookie data:  %ws");
  if ( !SysStringLen(a2) )
  {
    IsProductCurrent = -2147024809;
    v10 = 1464;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)(unsigned int)IsProductCurrent,
      v22);
    goto LABEL_30;
  }
  if ( !a4 )
  {
    IsProductCurrent = -2147467261;
    v10 = 1465;
    goto LABEL_5;
  }
  if ( !a3 )
  {
    IsProductCurrent = -2145116156;
    goto LABEL_30;
  }
  *(_OWORD *)a4 = 0;
  *((_OWORD *)a4 + 1) = 0;
  *((_QWORD *)a4 + 4) = 0;
  *(_DWORD *)a4 = -2145116138;
  if ( v32 )
    SusFree(v32);
  if ( v33 )
    SusFree(v33);
  if ( v27 )
    SusFree(v27);
  if ( v34 )
    SusFree(v34);
  if ( v28 )
    SusFree(v28);
  if ( v35 )
    SusFree(v35);
  if ( v29 )
    SusFree(v29);
  if ( v26 )
    SusFree(v26);
  if ( v30 )
    SusFree(v30);
  IsProductCurrent = COSInstaller::ExtractReportingCookieData(
                       (COSInstaller *)((char *)this - 8),
                       a2,
                       &v30,
                       &v26,
                       &v29,
                       &v35,
                       &v28,
                       &v34,
                       &v27,
                       &v33,
                       &v32,
                       (wchar_t **)&lpMem,
                       (unsigned __int64 *)v36);
  v11 = IsProductCurrent;
  if ( IsProductCurrent != -2089484279 )
  {
    if ( IsProductCurrent < 0 )
    {
      v13 = (unsigned int)IsProductCurrent;
      v14 = 1507;
LABEL_83:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
        (const char *)v13,
        (int)v23);
      goto LABEL_29;
    }
    if ( !v30 )
    {
      IsProductCurrent = -2147467261;
      v14 = 1510;
      v13 = 2147500035LL;
      goto LABEL_83;
    }
    if ( !v26 )
    {
      IsProductCurrent = -2147467261;
      v14 = 1511;
      v13 = 2147500035LL;
      goto LABEL_83;
    }
    if ( !v28 )
    {
      IsProductCurrent = -2147467261;
      v14 = 1512;
      v13 = 2147500035LL;
      goto LABEL_83;
    }
    if ( !v27 )
    {
      IsProductCurrent = -2147467261;
      v14 = 1513;
      v13 = 2147500035LL;
      goto LABEL_83;
    }
    if ( !v33 )
    {
      IsProductCurrent = -2147467261;
      v14 = 1514;
      v13 = 2147500035LL;
      goto LABEL_83;
    }
    v15 = ConvertFileVerToStringW(*(unsigned __int64 *)v36, &v25);
    IsProductCurrent = v15;
    v11 = v15;
    if ( v15 < 0 )
    {
      v13 = (unsigned int)v15;
      v14 = 1517;
      goto LABEL_83;
    }
    v16 = v29;
    if ( v29 && *v29 )
    {
      v17 = 1;
    }
    else
    {
      v16 = v26;
      v17 = 0;
    }
    v11 = CheckIfDirExists(v16);
    v18 = L"Deployment";
    if ( v11 < 0 )
    {
      if ( v17 )
        v18 = L"Merged";
      WUTrace(0, 0, 4096, 4, 0, L"%ws sandbox folder %ws does not exist", v18, v16);
    }
    else
    {
      if ( v17 )
        v18 = L"Merged";
      WUTrace(0, 0, 4096, 4, 0, L"%ws sandbox folder %ws exists", v18, v16);
      PostRebootResultFromUpdateAgent = COSInstaller::GetPostRebootResultFromUpdateAgent(
                                          v19,
                                          v27,
                                          v26,
                                          v29,
                                          v35,
                                          v28,
                                          v34,
                                          v32,
                                          (wchar_t *const)lpMem,
                                          (bool *)&v24,
                                          a4);
      v8 = v24;
      v11 = PostRebootResultFromUpdateAgent;
      if ( PostRebootResultFromUpdateAgent < 0 )
      {
        if ( PostRebootResultFromUpdateAgent == -2147024864 )
        {
          WUTrace(0, 0, 4096, 3, 0, L"Updateagent is in use. Will try again later");
          *(_DWORD *)a4 = -2145116140;
          *((_DWORD *)a4 + 2) = 1;
          *((_DWORD *)a4 + 9) = 1;
LABEL_77:
          v11 = 0;
          goto LABEL_28;
        }
        if ( (_BYTE)v24 )
        {
          LODWORD(v23) = PostRebootResultFromUpdateAgent;
          WUTrace(0, 0, 4096, 2, v23, L"GetPostRebootResultFromUpdateAgent failed");
          *(_DWORD *)a4 = -2145116138;
          goto LABEL_77;
        }
      }
      if ( PostRebootResultFromUpdateAgent >= 0 )
        goto LABEL_81;
    }
    if ( !v8 )
    {
      LOBYTE(v24) = 0;
      WUTrace(0, 0, 4096, 4, 0, L"Using product info to determine if the update was successfully installed");
      IsProductCurrent = ProductDatabase::GetIsProductCurrent((ProductDatabase *)v30, v36, &v24, v21);
      v11 = IsProductCurrent;
      if ( IsProductCurrent >= 0 )
      {
        if ( (_BYTE)v24 )
        {
          WUTrace(
            0,
            0,
            4096,
            4,
            0,
            L"Reporting cookie product version and current installed product version match. We have successfully updated");
          *(_DWORD *)a4 = 0;
          goto LABEL_29;
        }
        goto LABEL_28;
      }
      LODWORD(v23) = IsProductCurrent;
      WUTrace(0, 0, 4096, 2, v23, L"Failed to get the product version for product: %ws");
LABEL_82:
      v13 = (unsigned int)v11;
      v14 = 1626;
      goto LABEL_83;
    }
LABEL_81:
    IsProductCurrent = v11;
    if ( v11 >= 0 )
      goto LABEL_28;
    goto LABEL_82;
  }
  LODWORD(v23) = -2089484279;
  WUTrace(0, 0, 4096, 2, v23, L"ExtractReportingCookieData failed");
LABEL_28:
  IsProductCurrent = 0;
LABEL_29:
  LODWORD(v23) = v11;
  WUTrace(0, 0, 4096, ((v11 >> 31) & 0xFFFFFFFE) + 4, v23, L"Leave GetPostRebootResult for Deployment handler");
LABEL_30:
  if ( v25 )
    SusFree(v25);
  if ( lpMem )
  {
    SusFree(lpMem);
    lpMem = 0;
  }
  if ( v32 )
  {
    SusFree(v32);
    v32 = 0;
  }
  if ( v33 )
  {
    SusFree(v33);
    v33 = 0;
  }
  if ( v27 )
  {
    SusFree(v27);
    v27 = 0;
  }
  if ( v34 )
  {
    SusFree(v34);
    v34 = 0;
  }
  if ( v28 )
  {
    SusFree(v28);
    v28 = 0;
  }
  if ( v35 )
  {
    SusFree(v35);
    v35 = 0;
  }
  if ( v29 )
  {
    SusFree(v29);
    v29 = 0;
  }
  if ( v26 )
  {
    SusFree(v26);
    v26 = 0;
  }
  if ( v30 )
    SusFree(v30);
  return (unsigned int)IsProductCurrent;
}

```

## disassembly

```asm
0x18003f760  mov     [rsp-8+arg_10], rbx
0x18003f765  push    rbp
0x18003f766  push    rsi
0x18003f767  push    rdi
0x18003f768  push    r12
0x18003f76a  push    r13
0x18003f76c  push    r14
0x18003f76e  push    r15
0x18003f770  lea     rbp, [rsp-27h]
0x18003f775  sub     rsp, 0F0h
0x18003f77c  mov     rax, cs:__security_cookie
0x18003f783  xor     rax, rsp
0x18003f786  mov     [rbp+57h+var_40], rax
0x18003f78a  xor     r12d, r12d
0x18003f78d  mov     [rsp+120h+var_F0], rdx
0x18003f792  lea     rax, aEnterGetpostre; "Enter GetPostRebootResult for Deploymen"...
0x18003f799  mov     [rbp+57h+var_80], r12
0x18003f79d  mov     rsi, r9
0x18003f7a0  mov     [rsp+120h+var_F8], rax
0x18003f7a5  mov     ebx, r8d
0x18003f7a8  mov     [rbp+57h+var_A0], r12
0x18003f7ac  mov     rdi, rdx
0x18003f7af  mov     [rbp+57h+var_88], r12
0x18003f7b3  mov     r14, rcx
0x18003f7b6  mov     [rbp+57h+var_58], r12
0x18003f7ba  mov     r13d, 1000h
0x18003f7c0  mov     [rbp+57h+var_90], r12
0x18003f7c4  lea     r9d, [r12+4]
0x18003f7c9  mov     [rbp+57h+var_60], r12
0x18003f7cd  mov     r8d, r13d
0x18003f7d0  mov     [rbp+57h+var_98], r12
0x18003f7d4  xor     edx, edx
0x18003f7d6  mov     [rbp+57h+var_68], r12
0x18003f7da  xor     ecx, ecx
0x18003f7dc  mov     [rbp+57h+var_70], r12
0x18003f7e0  mov     [rbp+57h+lpMem], r12
0x18003f7e4  mov     r15b, r12b
0x18003f7e7  mov     qword ptr [rbp+57h+var_50], r12
0x18003f7eb  mov     [rbp+57h+var_A8], r12
0x18003f7ef  mov     byte ptr [rbp+57h+var_B0], r12b
0x18003f7f3  mov     [rsp+120h+var_100], r12; int
0x18003f7f8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003f7fd  mov     rcx, rdi; pbstr
0x18003f800  call    cs:__imp_SysStringLen
0x18003f806  test    eax, eax
0x18003f808  jnz     short loc_18003F816
0x18003f80a  mov     ebx, 80070057h
0x18003f80f  mov     edx, 5B8h
0x18003f814  jmp     short loc_18003F825
0x18003f816  test    rsi, rsi
0x18003f819  jnz     short loc_18003F83D
0x18003f81b  mov     ebx, 80004003h
0x18003f820  mov     edx, 5B9h; void *
0x18003f825  mov     rcx, [rbp+5Fh]; this
0x18003f829  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003f830  mov     r9d, ebx; char *
0x18003f833  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f838  jmp     loc_18003F9B1
0x18003f83d  test    ebx, ebx
0x18003f83f  jnz     short loc_18003F84B
0x18003f841  mov     ebx, 80242004h
0x18003f846  jmp     loc_18003F9B1
0x18003f84b  mov     rcx, [rbp+57h+lpMem]; lpMem
0x18003f84f  xorps   xmm0, xmm0
0x18003f852  movups  xmmword ptr [rsi], xmm0
0x18003f855  xor     eax, eax
0x18003f857  movups  xmmword ptr [rsi+10h], xmm0
0x18003f85b  mov     [rsi+20h], rax
0x18003f85f  mov     dword ptr [rsi], 80242016h
0x18003f865  test    rcx, rcx
0x18003f868  jz      short loc_18003F86F
0x18003f86a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003f86f  mov     rcx, [rbp+57h+var_70]; lpMem
0x18003f873  test    rcx, rcx
0x18003f876  jz      short loc_18003F87D
0x18003f878  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003f87d  mov     rcx, [rbp+57h+var_68]; lpMem
0x18003f881  test    rcx, rcx
0x18003f884  jz      short loc_18003F88B
0x18003f886  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003f88b  mov     rcx, [rbp+57h+var_98]; lpMem
0x18003f88f  test    rcx, rcx
0x18003f892  jz      short loc_18003F899
0x18003f894  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003f899  mov     rcx, [rbp+57h+var_60]; lpMem
0x18003f89d  test    rcx, rcx
0x18003f8a0  jz      short loc_18003F8A7
0x18003f8a2  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003f8a7  mov     rcx, [rbp+57h+var_90]; lpMem
0x18003f8ab  test    rcx, rcx
0x18003f8ae  jz      short loc_18003F8B5
0x18003f8b0  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003f8b5  mov     rcx, [rbp+57h+var_58]; lpMem
0x18003f8b9  test    rcx, rcx
0x18003f8bc  jz      short loc_18003F8C3
0x18003f8be  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003f8c3  mov     rcx, [rbp+57h+var_88]; lpMem
0x18003f8c7  test    rcx, rcx
0x18003f8ca  jz      short loc_18003F8D1
0x18003f8cc  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003f8d1  mov     rcx, [rbp+57h+var_A0]; lpMem
0x18003f8d5  test    rcx, rcx
0x18003f8d8  jz      short loc_18003F8DF
0x18003f8da  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003f8df  mov     rcx, [rbp+57h+var_80]; lpMem
0x18003f8e3  test    rcx, rcx
0x18003f8e6  jz      short loc_18003F8ED
0x18003f8e8  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003f8ed  lea     rax, [rbp+57h+var_50]
0x18003f8f1  mov     rdx, rdi; wchar_t *
0x18003f8f4  mov     [rsp+120h+var_C0], rax; unsigned __int64 *
0x18003f8f9  lea     rcx, [r14-8]; this
0x18003f8fd  lea     rax, [rbp+57h+lpMem]
0x18003f901  mov     [rsp+120h+var_C8], rax; wchar_t **
0x18003f906  lea     r9, [rbp+57h+var_A0]; wchar_t **
0x18003f90a  lea     rax, [rbp+57h+var_70]
0x18003f90e  mov     [rsp+120h+var_D0], rax; wchar_t **
0x18003f913  lea     r8, [rbp+57h+var_80]; wchar_t **
0x18003f917  lea     rax, [rbp+57h+var_68]
0x18003f91b  mov     [rsp+120h+var_D8], rax; wchar_t **
0x18003f920  lea     rax, [rbp+57h+var_98]
0x18003f924  mov     [rsp+120h+var_E0], rax; wchar_t **
0x18003f929  lea     rax, [rbp+57h+var_60]
0x18003f92d  mov     [rsp+120h+var_E8], rax; wchar_t **
0x18003f932  lea     rax, [rbp+57h+var_90]
0x18003f936  mov     [rsp+120h+var_F0], rax; wchar_t **
0x18003f93b  lea     rax, [rbp+57h+var_58]
0x18003f93f  mov     [rsp+120h+var_F8], rax; wchar_t **
0x18003f944  lea     rax, [rbp+57h+var_88]
0x18003f948  mov     [rsp+120h+var_100], rax; wchar_t **
0x18003f94d  call    ?ExtractReportingCookieData@COSInstaller@@AEAAJPEA_WPEAPEA_W111111111PEA_K@Z; COSInstaller::ExtractReportingCookieData(wchar_t *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,unsigned __int64 *)
0x18003f952  mov     ebx, eax
0x18003f954  mov     edi, eax
0x18003f956  cmp     eax, 83750009h
0x18003f95b  jnz     loc_18003FA98
0x18003f961  lea     rax, aExtractreporti; "ExtractReportingCookieData failed"
0x18003f968  mov     r9d, 2
0x18003f96e  mov     [rsp+120h+var_F8], rax
0x18003f973  mov     r8d, r13d
0x18003f976  xor     edx, edx
0x18003f978  mov     dword ptr [rsp+120h+var_100], ebx
0x18003f97c  xor     ecx, ecx
0x18003f97e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003f983  mov     ebx, r12d
0x18003f986  mov     r9d, edi
0x18003f989  lea     rax, aLeaveGetpostre; "Leave GetPostRebootResult for Deploymen"...
0x18003f990  sar     r9d, 1Fh
0x18003f994  mov     r8d, r13d
0x18003f997  and     r9d, 0FFFFFFFEh
0x18003f99b  mov     [rsp+120h+var_F8], rax
0x18003f9a0  add     r9d, 4
0x18003f9a4  mov     dword ptr [rsp+120h+var_100], edi
0x18003f9a8  xor     edx, edx
0x18003f9aa  xor     ecx, ecx
0x18003f9ac  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003f9b1  mov     rcx, [rbp+57h+var_A8]; lpMem
0x18003f9b5  test    rcx, rcx
0x18003f9b8  jz      short loc_18003F9BF
0x18003f9ba  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003f9bf  mov     rcx, [rbp+57h+lpMem]; lpMem
0x18003f9c3  test    rcx, rcx
0x18003f9c6  jz      short loc_18003F9D1
0x18003f9c8  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003f9cd  mov     [rbp+57h+lpMem], r12
0x18003f9d1  mov     rcx, [rbp+57h+var_70]; lpMem
0x18003f9d5  test    rcx, rcx
0x18003f9d8  jz      short loc_18003F9E3
0x18003f9da  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003f9df  mov     [rbp+57h+var_70], r12
0x18003f9e3  mov     rcx, [rbp+57h+var_68]; lpMem
0x18003f9e7  test    rcx, rcx
0x18003f9ea  jz      short loc_18003F9F5
0x18003f9ec  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003f9f1  mov     [rbp+57h+var_68], r12
0x18003f9f5  mov     rcx, [rbp+57h+var_98]; lpMem
0x18003f9f9  test    rcx, rcx
0x18003f9fc  jz      short loc_18003FA07
0x18003f9fe  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003fa03  mov     [rbp+57h+var_98], r12
0x18003fa07  mov     rcx, [rbp+57h+var_60]; lpMem
0x18003fa0b  test    rcx, rcx
0x18003fa0e  jz      short loc_18003FA19
0x18003fa10  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003fa15  mov     [rbp+57h+var_60], r12
0x18003fa19  mov     rcx, [rbp+57h+var_90]; lpMem
0x18003fa1d  test    rcx, rcx
0x18003fa20  jz      short loc_18003FA2B
0x18003fa22  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003fa27  mov     [rbp+57h+var_90], r12
0x18003fa2b  mov     rcx, [rbp+57h+var_58]; lpMem
0x18003fa2f  test    rcx, rcx
0x18003fa32  jz      short loc_18003FA3D
0x18003fa34  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003fa39  mov     [rbp+57h+var_58], r12
0x18003fa3d  mov     rcx, [rbp+57h+var_88]; lpMem
0x18003fa41  test    rcx, rcx
0x18003fa44  jz      short loc_18003FA4F
0x18003fa46  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003fa4b  mov     [rbp+57h+var_88], r12
0x18003fa4f  mov     rcx, [rbp+57h+var_A0]; lpMem
0x18003fa53  test    rcx, rcx
0x18003fa56  jz      short loc_18003FA61
0x18003fa58  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003fa5d  mov     [rbp+57h+var_A0], r12
0x18003fa61  mov     rcx, [rbp+57h+var_80]; lpMem
0x18003fa65  test    rcx, rcx
0x18003fa68  jz      short loc_18003FA6F
0x18003fa6a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003fa6f  mov     eax, ebx
0x18003fa71  mov     rcx, [rbp+57h+var_40]
0x18003fa75  xor     rcx, rsp; StackCookie
0x18003fa78  call    __security_check_cookie
0x18003fa7d  mov     rbx, [rsp+120h+arg_10]
0x18003fa85  add     rsp, 0F0h
0x18003fa8c  pop     r15
0x18003fa8e  pop     r14
0x18003fa90  pop     r13
0x18003fa92  pop     r12
0x18003fa94  pop     rdi
0x18003fa95  pop     rsi
0x18003fa96  pop     rbp
0x18003fa97  retn
0x18003fa98  test    ebx, ebx
0x18003fa9a  jns     short loc_18003FAA9
0x18003fa9c  mov     r9d, ebx
0x18003fa9f  mov     edx, 5E3h
0x18003faa4  jmp     loc_18003FC90
0x18003faa9  cmp     [rbp+57h+var_80], r12
0x18003faad  jnz     short loc_18003FAC1
0x18003faaf  mov     ebx, 80004003h
0x18003fab4  mov     edx, 5E6h
0x18003fab9  mov     r9d, ebx
0x18003fabc  jmp     loc_18003FC90
0x18003fac1  cmp     [rbp+57h+var_A0], r12
0x18003fac5  jnz     short loc_18003FAD9
0x18003fac7  mov     ebx, 80004003h
0x18003facc  mov     edx, 5E7h
0x18003fad1  mov     r9d, ebx
0x18003fad4  jmp     loc_18003FC90
0x18003fad9  cmp     [rbp+57h+var_90], r12
0x18003fadd  jnz     short loc_18003FAF1
0x18003fadf  mov     ebx, 80004003h
0x18003fae4  mov     edx, 5E8h
0x18003fae9  mov     r9d, ebx
0x18003faec  jmp     loc_18003FC90
0x18003faf1  cmp     [rbp+57h+var_98], r12
0x18003faf5  jnz     short loc_18003FB09
0x18003faf7  mov     ebx, 80004003h
0x18003fafc  mov     edx, 5E9h
0x18003fb01  mov     r9d, ebx
0x18003fb04  jmp     loc_18003FC90
0x18003fb09  cmp     [rbp+57h+var_68], r12
0x18003fb0d  jnz     short loc_18003FB21
0x18003fb0f  mov     ebx, 80004003h
0x18003fb14  mov     edx, 5EAh
0x18003fb19  mov     r9d, ebx
0x18003fb1c  jmp     loc_18003FC90
0x18003fb21  mov     rcx, qword ptr [rbp+57h+var_50]; unsigned __int64
0x18003fb25  lea     rdx, [rbp+57h+var_A8]; wchar_t **
0x18003fb29  call    ?ConvertFileVerToStringW@@YAJ_KPEAPEA_W@Z; ConvertFileVerToStringW(unsigned __int64,wchar_t * *)
0x18003fb2e  mov     ebx, eax
0x18003fb30  mov     edi, eax
0x18003fb32  test    eax, eax
0x18003fb34  jns     short loc_18003FB43
0x18003fb36  mov     r9d, eax
0x18003fb39  mov     edx, 5EDh
0x18003fb3e  jmp     loc_18003FC90
0x18003fb43  mov     rbx, [rbp+57h+var_88]
0x18003fb47  test    rbx, rbx
0x18003fb4a  jz      short loc_18003FB57
0x18003fb4c  cmp     [rbx], r12w
0x18003fb50  jz      short loc_18003FB57
0x18003fb52  mov     r14b, 1
0x18003fb55  jmp     short loc_18003FB5E
0x18003fb57  mov     rbx, [rbp+57h+var_A0]
0x18003fb5b  mov     r14b, r12b
0x18003fb5e  mov     rcx, rbx; wchar_t *
0x18003fb61  call    ?CheckIfDirExists@@YAJPEB_W@Z; CheckIfDirExists(wchar_t const *)
0x18003fb66  mov     edi, eax
0x18003fb68  mov     [rsp+120h+var_E8], rbx
0x18003fb6d  test    eax, eax
0x18003fb6f  lea     rcx, aMerged_0; "Merged"
0x18003fb76  lea     rax, aDeployment; "Deployment"
0x18003fb7d  mov     r9d, 4
0x18003fb83  mov     r8d, r13d
0x18003fb86  js      loc_18003FCA5
0x18003fb8c  test    r14b, r14b
0x18003fb8f  cmovnz  rax, rcx
0x18003fb93  xor     edx, edx
0x18003fb95  mov     [rsp+120h+var_F0], rax
0x18003fb9a  xor     ecx, ecx
0x18003fb9c  lea     rax, aWsSandboxFolde_0; "%ws sandbox folder %ws exists"
0x18003fba3  mov     [rsp+120h+var_F8], rax
0x18003fba8  mov     [rsp+120h+var_100], r12
0x18003fbad  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003fbb2  mov     r9, [rbp+57h+var_88]; wchar_t *
0x18003fbb6  lea     rax, [rbp+57h+var_B0]
0x18003fbba  mov     r8, [rbp+57h+var_A0]; wchar_t *
0x18003fbbe  mov     rdx, [rbp+57h+var_98]; wchar_t *
0x18003fbc2  mov     [rsp+120h+var_D0], rsi; struct tagPostRebootResultData *
  ... truncated ...
```
