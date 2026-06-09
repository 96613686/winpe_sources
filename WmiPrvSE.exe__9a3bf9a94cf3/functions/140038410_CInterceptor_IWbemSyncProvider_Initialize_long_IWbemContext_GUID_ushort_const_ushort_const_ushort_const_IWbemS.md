# CInterceptor_IWbemSyncProvider::Initialize(long,IWbemContext *,_GUID *,ushort const *,ushort const *,ushort const *,IWbemServices *,IWbemServices *,IWbemProviderInitSink *)

- ea: `0x140038410`
- end: `0x140038aa8`
- name: `?Initialize@CInterceptor_IWbemSyncProvider@@UEAAJJPEAUIWbemContext@@PEAU_GUID@@PEBG22PEAUIWbemServices@@3PEAUIWbemProviderInitSink@@@Z`
- size: `1688`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, unsigned int, struct IWbemContext *, struct _GUID *, OLECHAR *psz, OLECHAR *, OLECHAR *, struct IWbemServices *, struct IWbemServices *, struct IWbemProviderInitSink *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x140003a44`
- `0x14000a530`
- `0x1400182c4`
- `0x14001b3d0`
- `0x140020820`
- `0x1400209a0`
- `0x1400234b8`
- `0x14002944c`
- `0x140029c94`
- `0x140029d34`
- `0x14002a684`
- `0x1400302bc`
- `0x140038410`
- `0x14003c630`
- `0x140046430`
- `0x140048010`

## import_xrefs

- `msvcrt!wcschr` at `0x14003878b`
- `msvcrt!wcschr` at `0x14003878b`
- `msvcrt!_ui64tow_s` at `0x1400389ab`
- `msvcrt!_ui64tow_s` at `0x1400389ab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400385c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400385c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400389b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400389b1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140038674`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400386b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400386e7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140038674`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400386b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400386e7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140038a00`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140038a00`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14003886d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14003886d`
- `wbemcomn!GetMemLogObject` at `0x140038a42`
- `wbemcomn!GetMemLogObject` at `0x140038a42`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140038a4d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140038a4d`
- `OLEAUT32!__imp_SysAllocString` at `0x1400384fc`
- `OLEAUT32!__imp_SysAllocString` at `0x140038516`
- `OLEAUT32!__imp_SysAllocString` at `0x140038530`
- `OLEAUT32!__imp_SysAllocString` at `0x140038567`
- `OLEAUT32!__imp_SysAllocString` at `0x1400384fc`
- `OLEAUT32!__imp_SysAllocString` at `0x140038516`
- `OLEAUT32!__imp_SysAllocString` at `0x140038530`
- `OLEAUT32!__imp_SysAllocString` at `0x140038567`
- `OLEAUT32!__imp_SysStringLen` at `0x1400385f4`
- `OLEAUT32!__imp_SysStringLen` at `0x1400385f4`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140038739`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140038739`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140038744`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140038744`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14003855d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14003855d`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140038627`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x14003881f`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140038627`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x14003881f`

## string_xrefs

- `0x1400389ba`: `ProcessID: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_IWbemSyncProvider::Initialize(
        CInterceptor_IWbemSyncProvider *this,
        unsigned int a2,
        struct IWbemContext *a3,
        struct _GUID *a4,
        OLECHAR *psz,
        OLECHAR *a6,
        OLECHAR *a7,
        struct IWbemServices *a8,
        struct IWbemServices *a9,
        struct IWbemProviderInitSink *a10)
{
  __int64 v12; // r9
  struct IWbemProviderInitSink *v14; // r8
  _UNKNOWN **v15; // rdx
  int v16; // esi
  BSTR v17; // rax
  BSTR v18; // rax
  BSTR v19; // rax
  HANDLE EventW; // rax
  const WCHAR ***v21; // r12
  _QWORD *v22; // rcx
  OLECHAR *v23; // rcx
  HKEY v24; // rbx
  OLECHAR *v25; // rdi
  const wchar_t **v26; // rax
  const wchar_t **v27; // rbx
  UINT v28; // eax
  BSTR v29; // rax
  wchar_t *v30; // rax
  struct _FILETIME *v31; // rdx
  __int64 v32; // rcx
  int v33; // r8d
  LSTATUS v34; // r15d
  _bstr_t::Data_t *v35; // rax
  const WCHAR **v36; // rax
  const WCHAR *v37; // rdx
  const WCHAR *v38; // rdx
  HKEY v39; // rbx
  _QWORD *v40; // rcx
  const WCHAR **v41; // rdi
  char *v42; // rax
  DWORD CurrentProcessId; // eax
  __int64 v44; // rax
  CMemoryLog *MemLogObject; // rax
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp-98h] BYREF
  DWORD pdwType; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned __int64 Value; // [rsp+70h] [rbp-90h] BYREF
  HKEY v51; // [rsp+78h] [rbp-88h] BYREF
  _bstr_t::Data_t *v52; // [rsp+80h] [rbp-80h] BYREF
  struct IWbemProviderInitSink *v53; // [rsp+88h] [rbp-78h]
  HKEY v54; // [rsp+90h] [rbp-70h]
  wchar_t Buffer[36]; // [rsp+98h] [rbp-68h] BYREF
  OLECHAR sz[264]; // [rsp+E0h] [rbp-20h] BYREF

  v12 = a2;
  v14 = a10;
  v53 = a10;
  v15 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dqSSSqqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      180,
      (unsigned int)WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      v12,
      (char)a3,
      (__int64)psz,
      (__int64)a6,
      (__int64)a7,
      (char)a9,
      (char)a10,
      (char)a4);
  }
  if ( *((_BYTE *)this + 160) )
  {
    if ( (unsigned int)ProxyContainer::Initialize((char *)this + 312, v15, v14, v12)
      || psz && (v17 = SysAllocString(psz), (*((_QWORD *)this + 61) = v17) == 0)
      || a6 && (v18 = SysAllocString(a6), (*((_QWORD *)this + 60) = v18) == 0)
      || a7 && (v19 = SysAllocString(a7), (*((_QWORD *)this + 62) = v19) == 0) )
    {
      v16 = -2147217402;
    }
    else
    {
      v16 = 0;
      if ( a4 )
      {
        StringFromGUID2(a4, sz, 78);
        *((_QWORD *)this + 63) = SysAllocString(sz);
      }
    }
  }
  else
  {
    v16 = -2147217402;
  }
  if ( a8 )
    v16 = ((__int64 (__fastcall *)(struct IWbemServices *, const wchar_t *, _QWORD, struct IWbemContext *, char *, _QWORD))a8->lpVtbl->GetObjectA)(
            a8,
            L"__ExtendedStatus",
            0,
            a3,
            (char *)this + 296,
            0);
  if ( v16 >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 50) = EventW;
    if ( !EventW )
      v16 = -2147217402;
    v21 = (const WCHAR ***)((char *)this + 440);
    v22 = (_QWORD *)*((_QWORD *)this + 55);
    v23 = v22 ? (OLECHAR *)*v22 : 0LL;
    if ( !SysStringLen(v23) )
    {
      phkResult = 0;
      pdwType = 0;
      pcbData = 4;
      if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\Tracing\\Providers", &phkResult) )
      {
        v24 = phkResult;
        v51 = phkResult;
        RegGetValueW(phkResult, 0, L"Enabled", 0x10u, &pdwType, (char *)this + 452, &pcbData);
        if ( *((_DWORD *)this + 113) )
        {
          RegGetValueW(phkResult, 0, L"IsToCleanupTraces", 0x10u, &pdwType, (char *)this + 448, &pcbData);
          RegGetValueW(phkResult, 0, L"IsTrackingOperationOnly", 0x10u, &pdwType, (char *)this + 456, &pcbData);
        }
        else
        {
          *((_DWORD *)this + 112) = 0;
        }
        DLRegCloseKey(v24);
      }
      if ( *((_DWORD *)this + 113) )
      {
        v25 = (OLECHAR *)*((_QWORD *)this + 62);
        v26 = (const wchar_t **)operator new(0x18u);
        v27 = v26;
        v51 = (HKEY)v26;
        if ( v26 )
        {
          v26[1] = 0;
          *((_DWORD *)v26 + 4) = 1;
          if ( v25 )
          {
            v28 = SysStringByteLen(v25);
            v29 = SysAllocStringByteLen((LPCSTR)v25, v28);
            *v27 = v29;
            if ( !v29 )
              _com_issue_error(-2147024882);
          }
          else
          {
            *v26 = 0;
          }
        }
        else
        {
          v27 = 0;
        }
        v51 = (HKEY)v27;
        if ( !v27 )
          _com_issue_error(-2147024882);
        while ( 1 )
        {
          v30 = wcschr(*v27, 0x5Cu);
          if ( !v30 )
            break;
          *v30 = 47;
        }
        v34 = StringCchPrintfW(
                sz,
                0x104u,
                L"%s\\%s @ %s",
                L"Software\\Microsoft\\WBEM\\Tracing\\Providers",
                *(_QWORD *)(*((_QWORD *)this + 59) + 1768LL),
                *v27);
        if ( v34 >= 0 )
        {
          _bstr_t::~_bstr_t((CInterceptor_IWbemSyncProvider *)((char *)this + 440));
          v35 = (_bstr_t::Data_t *)operator new(0x18u);
          v52 = v35;
          if ( v35 )
            v36 = (const WCHAR **)_bstr_t::Data_t::Data_t(v35, sz);
          else
            v36 = 0;
          *v21 = v36;
          if ( v36 )
            v37 = *v36;
          else
            v37 = 0;
          v34 = RegOpenKeyW(HKEY_LOCAL_MACHINE, v37, &phkResult);
        }
        if ( v34 == 2 )
        {
          if ( *v21 )
            v38 = **v21;
          else
            v38 = 0;
          v34 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v38, 0, 0, 0, 2u, 0, &phkResult, 0);
        }
        v39 = phkResult;
        v54 = phkResult;
        if ( !v34 )
        {
          if ( !lpMem
            || (v52 = (_bstr_t::Data_t *)*((_QWORD *)this + 52),
                (unsigned int)WmiHashTable<unsigned __int64,unsigned long,4>::Find(v32, &v52, &Value)) )
          {
            Value = 0;
            GetFileTimeInUi64(&Value, v31);
            _ui64tow_s(Value, Buffer, 0x1Eu, 10);
            CurrentProcessId = GetCurrentProcessId();
            StringCchPrintfW(sz, 0x104u, L"ProcessID: %d", CurrentProcessId);
            v44 = -1;
            do
              ++v44;
            while ( sz[v44] );
            RegSetValueExW(phkResult, Buffer, 0, 1u, (const BYTE *)sz, 2 * v44);
          }
          goto LABEL_79;
        }
        if ( v34 == -2147024774 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              181,
              WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
              2147942522LL);
          }
          goto LABEL_79;
        }
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
LABEL_79:
          DLRegCloseKey(v39);
          _bstr_t::~_bstr_t((_bstr_t *)&v51);
          goto LABEL_80;
        }
        v41 = *v21;
        if ( *v21 )
        {
          v42 = (char *)v41[1];
          if ( v42 )
          {
LABEL_72:
            WPP_SF_sD(v40[2], (_DWORD)v31, v33, (_DWORD)v42, v34);
            goto LABEL_79;
          }
          v42 = _com_util::ConvertBSTRToString(*v41);
          v41[1] = (const WCHAR *)v42;
          if ( v42 )
          {
            v40 = WPP_GLOBAL_Control;
            goto LABEL_72;
          }
          if ( *v41 )
            _com_issue_error(-2147024882);
          v40 = WPP_GLOBAL_Control;
        }
        LODWORD(v42) = 0;
        goto LABEL_72;
      }
    }
  }
LABEL_80:
  ((void (__fastcall *)(struct IWbemProviderInitSink *, _QWORD, _QWORD))v53->lpVtbl->SetStatus)(
    v53,
    (unsigned int)v16,
    0);
  if ( v16 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v16);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      183,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v16);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140038410  push    rbp
0x140038412  push    rbx
0x140038413  push    rsi
0x140038414  push    rdi
0x140038415  push    r12
0x140038417  push    r13
0x140038419  push    r14
0x14003841b  push    r15
0x14003841d  lea     rbp, [rsp-208h]
0x140038425  sub     rsp, 308h
0x14003842c  mov     rax, cs:__security_cookie
0x140038433  xor     rax, rsp
0x140038436  mov     [rbp+240h+var_50], rax
0x14003843d  mov     r15, r9
0x140038440  mov     r13, r8
0x140038443  mov     r9d, edx
0x140038446  mov     r14, rcx
0x140038449  mov     rbx, [rbp+240h+psz]
0x140038450  mov     rdi, [rbp+240h+arg_28]
0x140038457  mov     rsi, [rbp+240h+arg_30]
0x14003845e  mov     r12, [rbp+240h+arg_38]
0x140038465  mov     rax, [rbp+240h+arg_40]
0x14003846c  mov     r8, [rbp+240h+arg_48]
0x140038473  mov     [rbp+240h+var_2B8], r8
0x140038477  lea     rdx, WPP_GLOBAL_Control
0x14003847e  mov     rcx, cs:WPP_GLOBAL_Control
0x140038485  cmp     rcx, rdx
0x140038488  jz      short loc_1400384CE
0x14003848a  test    byte ptr [rcx+1Ch], 4
0x14003848e  jz      short loc_1400384CE
0x140038490  cmp     byte ptr [rcx+19h], 5
0x140038494  jb      short loc_1400384CE
0x140038496  mov     edx, 0B4h
0x14003849b  mov     [rsp+340h+var_2F0], r15
0x1400384a0  mov     [rsp+340h+var_2F8], r8
0x1400384a5  mov     [rsp+340h+lpdwDisposition], rax
0x1400384aa  mov     [rsp+340h+var_308], rsi
0x1400384af  mov     [rsp+340h+pcbData], rdi
0x1400384b4  mov     [rsp+340h+pvData], rbx
0x1400384b9  mov     [rsp+340h+pdwType], r13
0x1400384be  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x1400384c5  mov     rcx, [rcx+10h]
0x1400384c9  call    WPP_SF_dqSSSqqq
0x1400384ce  cmp     byte ptr [r14+0A0h], 0
0x1400384d6  jnz     short loc_1400384E4
0x1400384d8  mov     esi, 80041006h
0x1400384dd  mov     ebx, esi
0x1400384df  jmp     loc_140038579
0x1400384e4  lea     rcx, [r14+138h]
0x1400384eb  call    ?Initialize@ProxyContainer@@QEAA?AW4WmiStatusCode@@XZ; ProxyContainer::Initialize(void)
0x1400384f0  test    eax, eax
0x1400384f2  jnz     short loc_140038542
0x1400384f4  test    rbx, rbx
0x1400384f7  jz      short loc_14003850E
0x1400384f9  mov     rcx, rbx; psz
0x1400384fc  call    cs:__imp_SysAllocString
0x140038502  mov     [r14+1E8h], rax
0x140038509  test    rax, rax
0x14003850c  jz      short loc_140038542
0x14003850e  test    rdi, rdi
0x140038511  jz      short loc_140038528
0x140038513  mov     rcx, rdi; psz
0x140038516  call    cs:__imp_SysAllocString
0x14003851c  mov     [r14+1E0h], rax
0x140038523  test    rax, rax
0x140038526  jz      short loc_140038542
0x140038528  test    rsi, rsi
0x14003852b  jz      short loc_14003854B
0x14003852d  mov     rcx, rsi; psz
0x140038530  call    cs:__imp_SysAllocString
0x140038536  mov     [r14+1F0h], rax
0x14003853d  test    rax, rax
0x140038540  jnz     short loc_14003854B
0x140038542  mov     ebx, 80041006h
0x140038547  mov     esi, ebx
0x140038549  jmp     short loc_140038579
0x14003854b  xor     esi, esi
0x14003854d  test    r15, r15
0x140038550  jz      short loc_140038574
0x140038552  lea     r8d, [rsi+4Eh]; cchMax
0x140038556  lea     rdx, [rbp+240h+sz]; lpsz
0x14003855a  mov     rcx, r15; rguid
0x14003855d  call    cs:__imp_StringFromGUID2
0x140038563  lea     rcx, [rbp+240h+sz]; psz
0x140038567  call    cs:__imp_SysAllocString
0x14003856d  mov     [r14+1F8h], rax
0x140038574  mov     ebx, 80041006h
0x140038579  test    r12, r12
0x14003857c  jz      short loc_1400385B2
0x14003857e  mov     rax, [r12]
0x140038582  lea     rdx, [r14+128h]
0x140038589  mov     [rsp+340h+pvData], 0
0x140038592  mov     [rsp+340h+pdwType], rdx
0x140038597  mov     r9, r13
0x14003859a  xor     r8d, r8d
0x14003859d  lea     rdx, aExtendedstatus; "__ExtendedStatus"
0x1400385a4  mov     rcx, r12
0x1400385a7  mov     rax, [rax+30h]
0x1400385ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400385b0  mov     esi, eax
0x1400385b2  xor     r13d, r13d
0x1400385b5  test    esi, esi
0x1400385b7  js      loc_140038A22
0x1400385bd  xor     r9d, r9d; lpName
0x1400385c0  xor     r8d, r8d; bInitialState
0x1400385c3  lea     edx, [r13+1]; bManualReset
0x1400385c7  xor     ecx, ecx; lpEventAttributes
0x1400385c9  call    cs:__imp_CreateEventW
0x1400385cf  mov     [r14+190h], rax
0x1400385d6  test    rax, rax
0x1400385d9  cmovz   esi, ebx
0x1400385dc  lea     r12, [r14+1B8h]
0x1400385e3  mov     rcx, [r12]
0x1400385e7  test    rcx, rcx
0x1400385ea  jz      short loc_1400385F1
0x1400385ec  mov     rcx, [rcx]
0x1400385ef  jmp     short loc_1400385F4
0x1400385f1  mov     rcx, r13; pbstr
0x1400385f4  call    cs:__imp_SysStringLen
0x1400385fa  test    eax, eax
0x1400385fc  jnz     loc_140038A22
0x140038602  mov     [rsp+340h+phkResult], r13
0x140038607  mov     [rsp+340h+var_2D4], r13d
0x14003860c  mov     [rsp+340h+var_2D8], 4
0x140038614  lea     r8, [rsp+340h+phkResult]; phkResult
0x140038619  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\Tracing\\Pro"...
0x140038620  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140038627  call    cs:__imp_RegOpenKeyW
0x14003862d  test    eax, eax
0x14003862f  jnz     loc_1400386FB
0x140038635  mov     rbx, [rsp+340h+phkResult]
0x14003863a  mov     [rsp+340h+var_2C8], rbx
0x14003863f  lea     rdi, [r14+1C4h]
0x140038646  lea     rax, [rsp+340h+var_2D8]
0x14003864b  mov     [rsp+340h+pcbData], rax; pcbData
0x140038650  mov     [rsp+340h+pvData], rdi; pvData
0x140038655  lea     rax, [rsp+340h+var_2D4]
0x14003865a  mov     [rsp+340h+pdwType], rax; pdwType
0x14003865f  mov     r15d, 10h
0x140038665  mov     r9d, r15d; dwFlags
0x140038668  lea     r8, aEnabled; "Enabled"
0x14003866f  xor     edx, edx; lpSubKey
0x140038671  mov     rcx, rbx; hkey
0x140038674  call    cs:__imp_RegGetValueW
0x14003867a  lea     rax, [r14+1C0h]
0x140038681  cmp     [rdi], r13d
0x140038684  jz      short loc_1400386EF
0x140038686  lea     rcx, [rsp+340h+var_2D8]
0x14003868b  mov     [rsp+340h+pcbData], rcx; pcbData
0x140038690  mov     [rsp+340h+pvData], rax; pvData
0x140038695  lea     rax, [rsp+340h+var_2D4]
0x14003869a  mov     [rsp+340h+pdwType], rax; pdwType
0x14003869f  mov     r9d, r15d; dwFlags
0x1400386a2  lea     r8, aIstocleanuptra; "IsToCleanupTraces"
0x1400386a9  xor     edx, edx; lpSubKey
0x1400386ab  mov     rcx, [rsp+340h+phkResult]; hkey
0x1400386b0  call    cs:__imp_RegGetValueW
0x1400386b6  lea     rax, [r14+1C8h]
0x1400386bd  lea     rcx, [rsp+340h+var_2D8]
0x1400386c2  mov     [rsp+340h+pcbData], rcx; pcbData
0x1400386c7  mov     [rsp+340h+pvData], rax; pvData
0x1400386cc  lea     rax, [rsp+340h+var_2D4]
0x1400386d1  mov     [rsp+340h+pdwType], rax; pdwType
0x1400386d6  mov     r9d, r15d; dwFlags
0x1400386d9  lea     r8, aIstrackingoper; "IsTrackingOperationOnly"
0x1400386e0  xor     edx, edx; lpSubKey
0x1400386e2  mov     rcx, [rsp+340h+phkResult]; hkey
0x1400386e7  call    cs:__imp_RegGetValueW
0x1400386ed  jmp     short loc_1400386F2
0x1400386ef  mov     [rax], r13d
0x1400386f2  mov     rcx, rbx
0x1400386f5  call    DLRegCloseKey
0x1400386fa  nop
0x1400386fb  cmp     [r14+1C4h], r13d
0x140038702  jz      loc_140038A22
0x140038708  mov     rdi, [r14+1F0h]
0x14003870f  mov     ecx, 18h; dwBytes
0x140038714  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140038719  mov     rbx, rax
0x14003871c  mov     [rsp+340h+var_2C8], rax
0x140038721  test    rax, rax
0x140038724  jz      short loc_140038762
0x140038726  mov     [rax+8], r13
0x14003872a  mov     dword ptr [rax+10h], 1
0x140038731  test    rdi, rdi
0x140038734  jz      short loc_14003875D
0x140038736  mov     rcx, rdi; bstr
0x140038739  call    cs:__imp_SysStringByteLen
0x14003873f  mov     edx, eax; len
0x140038741  mov     rcx, rdi; psz
0x140038744  call    cs:__imp_SysAllocStringByteLen
0x14003874a  mov     [rbx], rax
0x14003874d  test    rax, rax
0x140038750  jnz     short loc_140038765
0x140038752  mov     ecx, 8007000Eh; int
0x140038757  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14003875d  mov     [rax], rdi
0x140038760  jmp     short loc_140038765
0x140038762  mov     rbx, r13
0x140038765  mov     [rsp+340h+var_2C8], rbx
0x14003876a  test    rbx, rbx
0x14003876d  jnz     short loc_14003877A
0x14003876f  mov     ecx, 8007000Eh; int
0x140038774  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14003877a  mov     edi, 5Ch ; '\'
0x14003877f  jmp     short loc_140038786
0x140038781  mov     word ptr [rax], 2Fh ; '/'
0x140038786  mov     edx, edi; Ch
0x140038788  mov     rcx, [rbx]; Str
0x14003878b  call    cs:__imp_wcschr
0x140038791  test    rax, rax
0x140038794  jnz     short loc_140038781
0x140038796  mov     rdx, [r14+1D8h]
0x14003879d  mov     rax, [rbx]
0x1400387a0  mov     [rsp+340h+pvData], rax
0x1400387a5  mov     rax, [rdx+6E8h]
0x1400387ac  mov     [rsp+340h+pdwType], rax
0x1400387b1  lea     r9, SubKey; "Software\\Microsoft\\WBEM\\Tracing\\Pro"...
0x1400387b8  lea     r8, aSSS; "%s\\%s @ %s"
0x1400387bf  mov     edi, 104h
0x1400387c4  mov     edx, edi; unsigned __int64
0x1400387c6  lea     rcx, [rbp+240h+sz]; unsigned __int16 *
0x1400387ca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400387cf  mov     r15d, eax
0x1400387d2  test    eax, eax
0x1400387d4  js      short loc_140038828
0x1400387d6  mov     rcx, r12; this
0x1400387d9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1400387de  mov     ecx, 18h; dwBytes
0x1400387e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400387e8  mov     [rbp+240h+var_2C0], rax
0x1400387ec  test    rax, rax
0x1400387ef  jz      short loc_1400387FF
0x1400387f1  lea     rdx, [rbp+240h+sz]; unsigned __int16 *
0x1400387f5  mov     rcx, rax; this
0x1400387f8  call    ??0Data_t@_bstr_t@@QEAA@PEBG@Z; _bstr_t::Data_t::Data_t(ushort const *)
0x1400387fd  jmp     short loc_140038802
0x1400387ff  mov     rax, r13
0x140038802  mov     [r12], rax
0x140038806  test    rax, rax
0x140038809  jz      short loc_140038810
0x14003880b  mov     rdx, [rax]
0x14003880e  jmp     short loc_140038813
0x140038810  mov     rdx, r13; lpSubKey
0x140038813  lea     r8, [rsp+340h+phkResult]; phkResult
0x140038818  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003881f  call    cs:__imp_RegOpenKeyW
0x140038825  mov     r15d, eax
0x140038828  cmp     r15d, 2
0x14003882c  jnz     short loc_140038876
0x14003882e  mov     rax, [r12]
0x140038832  test    rax, rax
0x140038835  jz      short loc_14003883C
0x140038837  mov     rdx, [rax]
0x14003883a  jmp     short loc_14003883F
0x14003883c  mov     rdx, r13; lpSubKey
0x14003883f  mov     [rsp+340h+lpdwDisposition], r13; lpdwDisposition
0x140038844  lea     rax, [rsp+340h+phkResult]
0x140038849  mov     [rsp+340h+var_308], rax; phkResult
0x14003884e  mov     [rsp+340h+pcbData], r13; lpSecurityAttributes
0x140038853  mov     dword ptr [rsp+340h+pvData], 2; samDesired
0x14003885b  mov     dword ptr [rsp+340h+pdwType], r13d; dwOptions
0x140038860  xor     r9d, r9d; lpClass
0x140038863  xor     r8d, r8d; Reserved
0x140038866  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003886d  call    cs:__imp_RegCreateKeyExW
0x140038873  mov     r15d, eax
0x140038876  mov     rbx, [rsp+340h+phkResult]
0x14003887b  mov     [rbp+240h+var_2B0], rbx
0x14003887f  test    r15d, r15d
0x140038882  jz      loc_140038963
0x140038888  cmp     r15d, 8007007Ah
0x14003888f  jnz     short loc_1400388DC
0x140038891  mov     rcx, cs:WPP_GLOBAL_Control
0x140038898  lea     r14, WPP_GLOBAL_Control
0x14003889f  cmp     rcx, r14
0x1400388a2  jz      loc_140038A0D
0x1400388a8  test    byte ptr [rcx+1Ch], 4
0x1400388ac  jz      loc_140038A0D
0x1400388b2  cmp     byte ptr [rcx+19h], 5
0x1400388b6  jb      loc_140038A0D
0x1400388bc  mov     edx, 0B5h
0x1400388c1  mov     r9d, 8007007Ah
0x1400388c7  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x1400388ce  mov     rcx, [rcx+10h]
0x1400388d2  call    WPP_SF_d
0x1400388d7  jmp     loc_140038A0D
0x1400388dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400388e3  lea     r14, WPP_GLOBAL_Control
0x1400388ea  cmp     rcx, r14
0x1400388ed  jz      loc_140038A0D
0x1400388f3  test    byte ptr [rcx+1Ch], 4
0x1400388f7  jz      loc_140038A0D
0x1400388fd  cmp     byte ptr [rcx+19h], 5
0x140038901  jb      loc_140038A0D
0x140038907  mov     rdi, [r12]
0x14003890b  test    rdi, rdi
0x14003890e  jz      short loc_140038941
0x140038910  mov     rax, [rdi+8]
0x140038914  test    rax, rax
  ... truncated ...
```
