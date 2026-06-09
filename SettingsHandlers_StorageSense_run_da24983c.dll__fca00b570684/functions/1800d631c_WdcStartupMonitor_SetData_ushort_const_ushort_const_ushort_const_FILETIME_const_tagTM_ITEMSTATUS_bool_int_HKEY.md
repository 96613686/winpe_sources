# WdcStartupMonitor::SetData(ushort const *,ushort const *,ushort const *,_FILETIME const *,_tagTM_ITEMSTATUS,bool,int,HKEY__ *,_STARTUP_LOCATION,HSTRING__ * *,_WDC_STARTUP_INFO * *)

- ea: `0x1800d631c`
- end: `0x1800d66fb`
- name: `?SetData@WdcStartupMonitor@@QEAAJPEBG00PEBU_FILETIME@@W4_tagTM_ITEMSTATUS@@_NHPEAUHKEY__@@W4_STARTUP_LOCATION@@PEAPEAUHSTRING__@@PEAPEAU_WDC_STARTUP_INFO@@@Z`
- size: `991`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _FILETIME *, enum _tagTM_ITEMSTATUS, bool, int, HKEY, enum _STARTUP_LOCATION, HSTRING *, struct _WDC_STARTUP_INFO **)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d4d24`
- `0x1800d5540`

## callees

- `0x18000e6cc`
- `0x180034cd8`
- `0x180044d90`
- `0x1800cff18`
- `0x1800d0614`
- `0x1800d0960`
- `0x1800d1d1c`
- `0x1800d20dc`
- `0x1800d26ec`
- `0x1800d284c`
- `0x1800d631c`
- `0x1800d6704`
- `0x1800d6bd8`
- `0x1800d6cd8`
- `0x1800d7558`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d63a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d63b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d63c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d6580`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d66ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d66b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d66c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d66d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d63a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d63b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d63c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d6580`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d66ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d66b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d66c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d66d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d6594`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d65a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d65c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d65f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d663a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d6594`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d65a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d65c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d65f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d663a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d6425`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d64ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d64e9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d6425`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d64ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d64e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d6415`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d649c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d64d9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d6415`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d649c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d64d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WdcStartupMonitor::SetData(
        WdcStartupMonitor *a1,
        const unsigned __int16 *a2,
        const OLECHAR *a3,
        const OLECHAR *a4,
        _QWORD *a5,
        unsigned int a6,
        char a7,
        int a8,
        __int64 a9,
        unsigned int a10,
        HSTRING a11,
        HSTRING *a12)
{
  HSTRING *v15; // r15
  unsigned int v16; // edx
  int v17; // esi
  HSTRING v18; // rbx
  int DetailsFromCrudeCmdLine; // edi
  __int64 v20; // rdx
  OLECHAR *v21; // rcx
  BSTR v22; // rax
  __int64 v23; // rdx
  OLECHAR *v24; // rcx
  BSTR v25; // rax
  OLECHAR *v26; // rcx
  BSTR v27; // rax
  __int64 v28; // rcx
  const unsigned __int16 *StringRawBuffer; // rdi
  const unsigned __int16 *v30; // rax
  WdcStartupMonitor *v31; // rcx
  const unsigned __int16 *v32; // rax
  WdcStartupMonitor *v33; // r14
  bool v34; // r8
  HSTRING v35; // rax
  const unsigned __int16 *v36; // rax
  bool v37; // r8
  const unsigned __int16 *v38; // rax
  WdcStartupMonitor *v39; // rcx
  WdcStartupMonitor *v40; // rcx
  int v41; // eax
  HSTRING v43; // [rsp+20h] [rbp-38h] BYREF
  HSTRING v44; // [rsp+28h] [rbp-30h] BYREF
  HSTRING v45; // [rsp+30h] [rbp-28h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h] BYREF
  HSTRING v47[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]

  v47[0] = 0;
  v45 = 0;
  v44 = 0;
  string = 0;
  v43 = 0;
  v15 = (HSTRING *)a11;
  *(_QWORD *)a11 = 0;
  *a12 = 0;
  a11 = 0;
  v17 = WdcStartupMonitor::CreateEntry(a1, &a11, 0x2000);
  if ( v17 < 0 )
  {
    WdcStartupMonitor::DataExpire((struct _WDC_DATA_INFO *)a11, v16);
    goto LABEL_45;
  }
  v18 = a11;
  v47[0] = a11;
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v44);
  v44 = 0;
  WindowsDeleteString(v45);
  v45 = 0;
  DetailsFromCrudeCmdLine = TmGetDetailsFromCrudeCmdLine(a2, &v45, &v44, &string);
  if ( DetailsFromCrudeCmdLine < 0 )
  {
    v20 = 1576;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
      (const char *)(unsigned int)DetailsFromCrudeCmdLine,
      (int)v43);
    v17 = DetailsFromCrudeCmdLine;
    goto LABEL_45;
  }
  v21 = (OLECHAR *)*((_QWORD *)v18 + 67);
  if ( v21 )
  {
    SysFreeString(v21);
    *((_QWORD *)v18 + 67) = 0;
  }
  v22 = SysAllocString(a2);
  if ( a2 && !v22 )
  {
    v23 = 1578;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
      (const char *)0x8007000ELL,
      (int)v43);
    v17 = -2147024882;
    goto LABEL_45;
  }
  *((_QWORD *)v18 + 67) = v22;
  a11 = v45;
  DetailsFromCrudeCmdLine = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v18 + 55, &a11);
  if ( DetailsFromCrudeCmdLine < 0 )
  {
    v20 = 1580;
    goto LABEL_5;
  }
  v24 = (OLECHAR *)*((_QWORD *)v18 + 65);
  if ( v24 )
  {
    SysFreeString(v24);
    *((_QWORD *)v18 + 65) = 0;
  }
  v25 = SysAllocString(a3);
  if ( a3 && !v25 )
  {
    v23 = 1582;
    goto LABEL_11;
  }
  *((_QWORD *)v18 + 65) = v25;
  v26 = (OLECHAR *)*((_QWORD *)v18 + 66);
  if ( v26 )
  {
    SysFreeString(v26);
    *((_QWORD *)v18 + 66) = 0;
  }
  v27 = SysAllocString(a4);
  if ( a4 && !v27 )
  {
    v23 = 1584;
    goto LABEL_11;
  }
  *((_QWORD *)v18 + 66) = v27;
  *((_QWORD *)v18 + 52) = *a5;
  *((double *)v18 + 21) = (double)(int)TmGetStatusStringFromItemStatus(a6);
  *((_BYTE *)v18 + 576) = a7;
  DetailsFromCrudeCmdLine = WdcStartupMonitor::SetStartupLocationType(v28, a10, v18);
  if ( DetailsFromCrudeCmdLine < 0 )
  {
    v20 = 1593;
    goto LABEL_5;
  }
  if ( a10 )
    *((_DWORD *)v18 + 142) = a8;
  else
    *((_QWORD *)v18 + 70) = a9;
  WindowsDeleteString(v43);
  v43 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v30 = WindowsGetStringRawBuffer(v45, 0);
  if ( WdcStartupMonitor::_VerifyAndGetSpecialExeFilePath(v31, v30, StringRawBuffer, &v43) < 0 )
  {
    v33 = a1;
  }
  else
  {
    v32 = WindowsGetStringRawBuffer(v43, 0);
    v33 = a1;
    if ( WdcStartupMonitor::SetFileData(a1, v32, v34, (struct _WDC_STARTUP_INFO *)v18) >= 0 )
    {
      v35 = v43;
      v43 = 0;
      goto LABEL_36;
    }
  }
  v36 = WindowsGetStringRawBuffer(v44, 0);
  DetailsFromCrudeCmdLine = WdcStartupMonitor::SetFileData(v33, v36, v37, (struct _WDC_STARTUP_INFO *)v18);
  if ( DetailsFromCrudeCmdLine < 0 )
  {
    v20 = 1616;
    goto LABEL_5;
  }
  v35 = v44;
  v44 = 0;
LABEL_36:
  *v15 = v35;
  if ( *(HSTRING *)v18 == v18 )
    InsertSortedList((struct _LIST_ENTRY *)v33, (struct _LIST_ENTRY *)v18);
  v38 = WindowsGetStringRawBuffer(*v15, 0);
  WdcStartupMonitor::_CheckAndSetInvalidPathFlag(v39, v38, (struct _WDC_STARTUP_INFO *)v18);
  if ( *((_QWORD *)v18 + 70) && (*((_BYTE *)v18 + 578) || *((_BYTE *)v18 + 579)) )
    WdcStartupMonitor::ConfigureItemToShowMalformedOrNetworkPath(v40, (struct _WDC_STARTUP_INFO *)v18);
  v41 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v18 + 75, v15);
  if ( v41 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x65C,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
      (const char *)(unsigned int)v41,
      (int)v43);
  v47[0] = 0;
  *a12 = v18;
LABEL_45:
  WindowsDeleteString(v43);
  v43 = 0;
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v44);
  v44 = 0;
  WindowsDeleteString(v45);
  v45 = 0;
  std::unique_ptr<_WDC_STARTUP_INFO *,WdcStartupMonitor::StartupInfoDeleter>::~unique_ptr<_WDC_STARTUP_INFO *,WdcStartupMonitor::StartupInfoDeleter>(v47);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800d631c  mov     [rsp-40h+arg_0], rcx
0x1800d6321  push    rbp
0x1800d6322  push    rbx
0x1800d6323  push    rsi
0x1800d6324  push    rdi
0x1800d6325  push    r12
0x1800d6327  push    r13
0x1800d6329  push    r14
0x1800d632b  push    r15
0x1800d632d  mov     rbp, rsp
0x1800d6330  sub     rsp, 58h
0x1800d6334  mov     r13, r9
0x1800d6337  mov     r12, r8
0x1800d633a  mov     r14, rdx
0x1800d633d  xor     edi, edi
0x1800d633f  mov     [rbp+var_18], rdi
0x1800d6343  mov     [rbp+var_28], rdi
0x1800d6347  mov     [rbp+var_30], rdi
0x1800d634b  mov     [rbp+string], rdi
0x1800d634f  mov     [rbp+var_38], rdi
0x1800d6353  mov     r15, [rbp+arg_50]
0x1800d635a  mov     [r15], rdi
0x1800d635d  mov     rax, [rbp+arg_58]
0x1800d6364  mov     [rax], rdi
0x1800d6367  mov     [rbp+arg_50], rdi
0x1800d636e  mov     r8d, 2000h
0x1800d6374  lea     rdx, [rbp+arg_50]
0x1800d637b  call    ?CreateEntry@WdcStartupMonitor@@QEAAJPEAPEAU_WDC_STARTUP_INFO@@W4_tagTM_ITEMTYPE@@@Z; WdcStartupMonitor::CreateEntry(_WDC_STARTUP_INFO * *,_tagTM_ITEMTYPE)
0x1800d6380  mov     esi, eax
0x1800d6382  test    eax, eax
0x1800d6384  jns     short loc_1800D6397
0x1800d6386  mov     rcx, [rbp+arg_50]; struct _WDC_DATA_INFO *
0x1800d638d  call    ?DataExpire@WdcStartupMonitor@@SAJPEAU_WDC_DATA_INFO@@K@Z; WdcStartupMonitor::DataExpire(_WDC_DATA_INFO *,ulong)
0x1800d6392  jmp     loc_1800D66A7
0x1800d6397  mov     rbx, [rbp+arg_50]
0x1800d639e  mov     [rbp+var_18], rbx
0x1800d63a2  mov     rcx, [rbp+string]; string
0x1800d63a6  call    cs:__imp_WindowsDeleteString
0x1800d63ac  mov     [rbp+string], rdi
0x1800d63b0  mov     rcx, [rbp+var_30]; string
0x1800d63b4  call    cs:__imp_WindowsDeleteString
0x1800d63ba  mov     [rbp+var_30], rdi
0x1800d63be  mov     rcx, [rbp+var_28]; string
0x1800d63c2  call    cs:__imp_WindowsDeleteString
0x1800d63c8  mov     [rbp+var_28], rdi
0x1800d63cc  lea     r9, [rbp+string]; HSTRING *
0x1800d63d0  lea     r8, [rbp+var_30]; HSTRING *
0x1800d63d4  lea     rdx, [rbp+var_28]; HSTRING *
0x1800d63d8  mov     rcx, r14; unsigned __int16 *
0x1800d63db  call    ?TmGetDetailsFromCrudeCmdLine@@YAJPEBGPEAPEAUHSTRING__@@11@Z; TmGetDetailsFromCrudeCmdLine(ushort const *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1800d63e0  mov     edi, eax
0x1800d63e2  test    eax, eax
0x1800d63e4  jns     short loc_1800D6407
0x1800d63e6  mov     edx, 628h; void *
0x1800d63eb  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d63f2  mov     r9d, edi; char *
0x1800d63f5  mov     rcx, [rbp+40h]; this
0x1800d63f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d63fe  mov     esi, edi
0x1800d6400  xor     edi, edi
0x1800d6402  jmp     loc_1800D66A7
0x1800d6407  mov     rcx, [rbx+218h]; bstrString
0x1800d640e  xor     edi, edi
0x1800d6410  test    rcx, rcx
0x1800d6413  jz      short loc_1800D6422
0x1800d6415  call    cs:__imp_SysFreeString
0x1800d641b  mov     [rbx+218h], rdi
0x1800d6422  mov     rcx, r14; psz
0x1800d6425  call    cs:__imp_SysAllocString
0x1800d642b  test    r14, r14
0x1800d642e  jz      short loc_1800D6459
0x1800d6430  test    rax, rax
0x1800d6433  jnz     short loc_1800D6459
0x1800d6435  mov     edx, 62Ah; void *
0x1800d643a  mov     ebx, 8007000Eh
0x1800d643f  mov     rcx, [rbp+40h]; this
0x1800d6443  mov     r9d, ebx; char *
0x1800d6446  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d644d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d6452  mov     esi, ebx
0x1800d6454  jmp     loc_1800D66A7
0x1800d6459  mov     [rbx+218h], rax
0x1800d6460  mov     rax, [rbp+var_28]
0x1800d6464  mov     [rbp+arg_50], rax
0x1800d646b  lea     rcx, [rbx+1B8h]; newString
0x1800d6472  lea     rdx, [rbp+arg_50]; HSTRING *
0x1800d6479  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800d647e  mov     edi, eax
0x1800d6480  test    eax, eax
0x1800d6482  jns     short loc_1800D648E
0x1800d6484  mov     edx, 62Ch
0x1800d6489  jmp     loc_1800D63EB
0x1800d648e  mov     rcx, [rbx+208h]; bstrString
0x1800d6495  xor     edi, edi
0x1800d6497  test    rcx, rcx
0x1800d649a  jz      short loc_1800D64A9
0x1800d649c  call    cs:__imp_SysFreeString
0x1800d64a2  mov     [rbx+208h], rdi
0x1800d64a9  mov     rcx, r12; psz
0x1800d64ac  call    cs:__imp_SysAllocString
0x1800d64b2  test    r12, r12
0x1800d64b5  jz      short loc_1800D64C6
0x1800d64b7  test    rax, rax
0x1800d64ba  jnz     short loc_1800D64C6
0x1800d64bc  mov     edx, 62Eh
0x1800d64c1  jmp     loc_1800D643A
0x1800d64c6  mov     [rbx+208h], rax
0x1800d64cd  mov     rcx, [rbx+210h]; bstrString
0x1800d64d4  test    rcx, rcx
0x1800d64d7  jz      short loc_1800D64E6
0x1800d64d9  call    cs:__imp_SysFreeString
0x1800d64df  mov     [rbx+210h], rdi
0x1800d64e6  mov     rcx, r13; psz
0x1800d64e9  call    cs:__imp_SysAllocString
0x1800d64ef  test    r13, r13
0x1800d64f2  jz      short loc_1800D6503
0x1800d64f4  test    rax, rax
0x1800d64f7  jnz     short loc_1800D6503
0x1800d64f9  mov     edx, 630h
0x1800d64fe  jmp     loc_1800D643A
0x1800d6503  mov     [rbx+210h], rax
0x1800d650a  mov     rax, [rbp+arg_20]
0x1800d650e  mov     rax, [rax]
0x1800d6511  mov     [rbx+1A0h], rax
0x1800d6518  mov     ecx, [rbp+arg_28]
0x1800d651b  call    ?TmGetStatusStringFromItemStatus@@YAHW4_tagTM_ITEMSTATUS@@@Z; TmGetStatusStringFromItemStatus(_tagTM_ITEMSTATUS)
0x1800d6520  movd    xmm0, eax
0x1800d6524  cvtdq2pd xmm0, xmm0
0x1800d6528  movsd   qword ptr [rbx+0A8h], xmm0
0x1800d6530  mov     al, [rbp+arg_30]
0x1800d6533  mov     [rbx+240h], al
0x1800d6539  mov     r8, rbx
0x1800d653c  mov     r14d, [rbp+arg_48]
0x1800d6543  mov     edx, r14d
0x1800d6546  call    ?SetStartupLocationType@WdcStartupMonitor@@QEAAJW4_STARTUP_LOCATION@@PEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::SetStartupLocationType(_STARTUP_LOCATION,_WDC_STARTUP_INFO *)
0x1800d654b  mov     edi, eax
0x1800d654d  test    eax, eax
0x1800d654f  jns     short loc_1800D655B
0x1800d6551  mov     edx, 639h
0x1800d6556  jmp     loc_1800D63EB
0x1800d655b  test    r14d, r14d
0x1800d655e  jnz     short loc_1800D6570
0x1800d6560  mov     rax, [rbp+arg_40]
0x1800d6567  mov     [rbx+230h], rax
0x1800d656e  jmp     short loc_1800D657C
0x1800d6570  mov     eax, [rbp+arg_38]
0x1800d6576  mov     [rbx+238h], eax
0x1800d657c  mov     rcx, [rbp+var_38]; string
0x1800d6580  call    cs:__imp_WindowsDeleteString
0x1800d6586  mov     [rbp+var_38], 0
0x1800d658e  xor     edx, edx; length
0x1800d6590  mov     rcx, [rbp+string]; string
0x1800d6594  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d659a  mov     rdi, rax
0x1800d659d  xor     edx, edx; length
0x1800d659f  mov     rcx, [rbp+var_28]; string
0x1800d65a3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d65a9  lea     r9, [rbp+var_38]; HSTRING *
0x1800d65ad  mov     r8, rdi; unsigned __int16 *
0x1800d65b0  mov     rdx, rax; unsigned __int16 *
0x1800d65b3  call    ?_VerifyAndGetSpecialExeFilePath@WdcStartupMonitor@@AEAAJPEBG0PEAPEAUHSTRING__@@@Z; WdcStartupMonitor::_VerifyAndGetSpecialExeFilePath(ushort const *,ushort const *,HSTRING__ * *)
0x1800d65b8  xor     edi, edi
0x1800d65ba  test    eax, eax
0x1800d65bc  js      short loc_1800D65EA
0x1800d65be  xor     edx, edx; length
0x1800d65c0  mov     rcx, [rbp+var_38]; string
0x1800d65c4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d65ca  mov     r9, rbx; struct _WDC_STARTUP_INFO *
0x1800d65cd  mov     rdx, rax; unsigned __int16 *
0x1800d65d0  mov     r14, [rbp+arg_0]
0x1800d65d4  mov     rcx, r14; this
0x1800d65d7  call    ?SetFileData@WdcStartupMonitor@@QEAAJPEBG_NPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::SetFileData(ushort const *,bool,_WDC_STARTUP_INFO *)
0x1800d65dc  test    eax, eax
0x1800d65de  js      short loc_1800D65EE
0x1800d65e0  mov     rax, [rbp+var_38]
0x1800d65e4  mov     [rbp+var_38], rdi
0x1800d65e8  jmp     short loc_1800D6622
0x1800d65ea  mov     r14, [rbp+arg_0]
0x1800d65ee  xor     edx, edx; length
0x1800d65f0  mov     rcx, [rbp+var_30]; string
0x1800d65f4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d65fa  mov     r9, rbx; struct _WDC_STARTUP_INFO *
0x1800d65fd  mov     rdx, rax; unsigned __int16 *
0x1800d6600  mov     rcx, r14; this
0x1800d6603  call    ?SetFileData@WdcStartupMonitor@@QEAAJPEBG_NPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::SetFileData(ushort const *,bool,_WDC_STARTUP_INFO *)
0x1800d6608  mov     edi, eax
0x1800d660a  test    eax, eax
0x1800d660c  jns     short loc_1800D6618
0x1800d660e  mov     edx, 650h
0x1800d6613  jmp     loc_1800D63EB
0x1800d6618  mov     rax, [rbp+var_30]
0x1800d661c  xor     edi, edi
0x1800d661e  mov     [rbp+var_30], rdi
0x1800d6622  mov     [r15], rax
0x1800d6625  cmp     [rbx], rbx
0x1800d6628  jnz     short loc_1800D6635
0x1800d662a  mov     rdx, rbx; struct _LIST_ENTRY *
0x1800d662d  mov     rcx, r14; struct _LIST_ENTRY *
0x1800d6630  call    ?InsertSortedList@@YAXPEAU_LIST_ENTRY@@0@Z; InsertSortedList(_LIST_ENTRY *,_LIST_ENTRY *)
0x1800d6635  xor     edx, edx; length
0x1800d6637  mov     rcx, [r15]; string
0x1800d663a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d6640  mov     r8, rbx; struct _WDC_STARTUP_INFO *
0x1800d6643  mov     rdx, rax; unsigned __int16 *
0x1800d6646  call    ?_CheckAndSetInvalidPathFlag@WdcStartupMonitor@@AEAAXPEBGPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::_CheckAndSetInvalidPathFlag(ushort const *,_WDC_STARTUP_INFO *)
0x1800d664b  cmp     [rbx+230h], rdi
0x1800d6652  jz      short loc_1800D666E
0x1800d6654  cmp     [rbx+242h], dil
0x1800d665b  jnz     short loc_1800D6666
0x1800d665d  cmp     [rbx+243h], dil
0x1800d6664  jz      short loc_1800D666E
0x1800d6666  mov     rdx, rbx; struct _WDC_STARTUP_INFO *
0x1800d6669  call    ?ConfigureItemToShowMalformedOrNetworkPath@WdcStartupMonitor@@AEAAXPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::ConfigureItemToShowMalformedOrNetworkPath(_WDC_STARTUP_INFO *)
0x1800d666e  lea     rcx, [rbx+258h]; newString
0x1800d6675  mov     rdx, r15; HSTRING *
0x1800d6678  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800d667d  mov     rcx, [rbp+40h]; this
0x1800d6681  test    eax, eax
0x1800d6683  jns     short loc_1800D6699
0x1800d6685  mov     r9d, eax; char *
0x1800d6688  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d668f  mov     edx, 65Ch; void *
0x1800d6694  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d6699  mov     [rbp+var_18], rdi
0x1800d669d  mov     rax, [rbp+arg_58]
0x1800d66a4  mov     [rax], rbx
0x1800d66a7  mov     rcx, [rbp+var_38]; string
0x1800d66ab  call    cs:__imp_WindowsDeleteString
0x1800d66b1  mov     [rbp+var_38], rdi
0x1800d66b5  mov     rcx, [rbp+string]; string
0x1800d66b9  call    cs:__imp_WindowsDeleteString
0x1800d66bf  mov     [rbp+string], rdi
0x1800d66c3  mov     rcx, [rbp+var_30]; string
0x1800d66c7  call    cs:__imp_WindowsDeleteString
0x1800d66cd  mov     [rbp+var_30], rdi
0x1800d66d1  mov     rcx, [rbp+var_28]; string
0x1800d66d5  call    cs:__imp_WindowsDeleteString
0x1800d66db  mov     [rbp+var_28], rdi
0x1800d66df  lea     rcx, [rbp+var_18]
0x1800d66e3  call    ??1?$unique_ptr@PEAU_WDC_STARTUP_INFO@@UStartupInfoDeleter@WdcStartupMonitor@@@std@@QEAA@XZ; std::unique_ptr<_WDC_STARTUP_INFO *,WdcStartupMonitor::StartupInfoDeleter>::~unique_ptr<_WDC_STARTUP_INFO *,WdcStartupMonitor::StartupInfoDeleter>(void)
0x1800d66e8  mov     eax, esi
0x1800d66ea  add     rsp, 58h
0x1800d66ee  pop     r15
0x1800d66f0  pop     r14
0x1800d66f2  pop     r13
0x1800d66f4  pop     r12
0x1800d66f6  pop     rdi
0x1800d66f7  pop     rsi
0x1800d66f8  pop     rbx
0x1800d66f9  pop     rbp
0x1800d66fa  retn
```
