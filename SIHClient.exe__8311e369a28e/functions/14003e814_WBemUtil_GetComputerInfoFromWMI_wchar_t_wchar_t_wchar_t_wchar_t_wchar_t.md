# WBemUtil::GetComputerInfoFromWMI(wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *)

- ea: `0x14003e814`
- end: `0x14003eb70`
- name: `?GetComputerInfoFromWMI@WBemUtil@@YAJPEAPEA_W0000@Z`
- size: `860`
- prototype: `__int64 __fastcall(WBemUtil *this, wchar_t **, wchar_t **, wchar_t **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14003612c`

## callees

- `0x140008de4`
- `0x1400326d0`
- `0x14003e428`
- `0x14003e598`
- `0x14003e814`
- `0x14003eeec`
- `0x140044664`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14003e8a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14003e8a0`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e8df`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e999`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e9d3`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ea08`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ea3e`
- `OLEAUT32!__imp_SysFreeString` at `0x14003eaa7`
- `OLEAUT32!__imp_SysFreeString` at `0x14003eab0`
- `OLEAUT32!__imp_SysFreeString` at `0x14003eab9`
- `OLEAUT32!__imp_SysFreeString` at `0x14003eac2`
- `OLEAUT32!__imp_SysFreeString` at `0x14003eacb`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ead4`
- `OLEAUT32!__imp_SysFreeString` at `0x14003eb2a`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e8df`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e999`
- `OLEAUT32!__imp_SysFreeString` at `0x14003e9d3`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ea08`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ea3e`
- `OLEAUT32!__imp_SysFreeString` at `0x14003eaa7`
- `OLEAUT32!__imp_SysFreeString` at `0x14003eab0`
- `OLEAUT32!__imp_SysFreeString` at `0x14003eab9`
- `OLEAUT32!__imp_SysFreeString` at `0x14003eac2`
- `OLEAUT32!__imp_SysFreeString` at `0x14003eacb`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ead4`
- `OLEAUT32!__imp_SysFreeString` at `0x14003eb2a`

## pseudocode

```c
__int64 __fastcall WBemUtil::GetComputerInfoFromWMI(WBemUtil *this, wchar_t **a2, wchar_t **a3, wchar_t **a4)
{
  HRESULT Instance; // ebx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  unsigned int v10; // edx
  int *v11; // r8
  struct IWbemClassObject **v12; // r9
  struct IWbemClassObject **v13; // r9
  __int64 v14; // rbx
  bool v15; // sf
  BSTR v16; // rax
  __int64 v17; // r8
  wchar_t *v18; // rax
  wchar_t **ppv; // [rsp+20h] [rbp-61h]
  wchar_t **ppva; // [rsp+20h] [rbp-61h]
  BSTR v22; // [rsp+30h] [rbp-51h] BYREF
  BSTR v23; // [rsp+38h] [rbp-49h] BYREF
  _QWORD v24[7]; // [rsp+40h] [rbp-41h] BYREF
  wchar_t v25[4]; // [rsp+78h] [rbp-9h] BYREF
  struct IUnknown *v26; // [rsp+80h] [rbp-1h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+7h] BYREF
  wchar_t v28[4]; // [rsp+90h] [rbp+Fh] BYREF
  wchar_t *v29; // [rsp+98h] [rbp+17h] BYREF
  wchar_t v30[8]; // [rsp+A0h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v29 = 0;
  bstrString = 0;
  v26 = 0;
  *(_QWORD *)v25 = 0;
  *(_QWORD *)v28 = 0;
  memset(&v24[3], 0, 32);
  wcscpy(v30, L"Unknown");
  v22 = 0;
  v23 = 0;
  *(_QWORD *)this = 0;
  *a2 = 0;
  Instance = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, (LPVOID *)&v29);
  if ( Instance == -2147221164 )
  {
LABEL_31:
    Instance = -2145124266;
    goto LABEL_32;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2145124266 )
    {
      v7 = (unsigned int)Instance;
      v8 = 231;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wbemutil.cpp",
        (const char *)v7,
        (int)ppv);
      goto LABEL_32;
    }
    goto LABEL_31;
  }
  if ( L"\\\\.\\root\\cimv2" != bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
    v9 = CSusBSTR::Append((CSusBSTR *)&bstrString, L"\\\\.\\root\\cimv2", 0xEu);
    Instance = v9;
    if ( v9 < 0 )
    {
      v8 = 233;
LABEL_12:
      v7 = (unsigned int)v9;
      goto LABEL_13;
    }
  }
  v24[0] = &v29;
  v24[1] = &bstrString;
  v24[2] = &v26;
  v9 = WUComTimeout::ComTimeout::MakeComCall__lambda_910c479648d882804510b1671eed198a___(v24);
  Instance = v9;
  if ( v9 < 0 )
  {
    v8 = 244;
    goto LABEL_12;
  }
  v9 = SetProxyBlanketImpersonationLevel(v26, v10, v11);
  Instance = v9;
  if ( v9 < 0 )
  {
    v8 = 246;
    goto LABEL_12;
  }
  if ( *(_QWORD *)v25 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v25 + 16LL))(*(_QWORD *)v25);
    *(_QWORD *)v25 = 0;
  }
  if ( WBemUtil::GetFirstWbemObject((WBemUtil *)v26, (struct IWbemServices *)&stru_14006EAC0, v25, v12) >= 0 )
  {
    SysFreeString(0);
    v22 = 0;
    v14 = -1;
    v15 = WBemUtil::GetWbemObjectBSTR(
            *(WBemUtil **)v25,
            (struct IWbemClassObject *)&stru_14006EAA0,
            v30,
            (const wchar_t *)&v22,
            ppv) < 0;
    v16 = v22;
    if ( v15 && v30 != v22 )
    {
      SysFreeString(v22);
      v22 = 0;
      v17 = -1;
      do
        ++v17;
      while ( v30[v17] );
      CSusBSTR::Append((CSusBSTR *)&v22, v30, v17);
      v16 = v22;
    }
    v22 = 0;
    *(_QWORD *)this = v16;
    SysFreeString(0);
    v23 = 0;
    v15 = WBemUtil::GetWbemObjectBSTR(
            *(WBemUtil **)v25,
            (struct IWbemClassObject *)&stru_14006EB08,
            v30,
            (const wchar_t *)&v23,
            ppva) < 0;
    v18 = v23;
    if ( v15 && v30 != v23 )
    {
      SysFreeString(v23);
      v23 = 0;
      do
        ++v14;
      while ( v30[v14] );
      CSusBSTR::Append((CSusBSTR *)&v23, v30, v14);
      v18 = v23;
    }
    v23 = 0;
    *a2 = v18;
  }
  if ( *(_QWORD *)v28 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 16LL))(*(_QWORD *)v28);
    *(_QWORD *)v28 = 0;
  }
  WBemUtil::GetFirstWbemObject((WBemUtil *)v26, (struct IWbemServices *)&stru_14006EAF0, v28, v13);
  Instance = 0;
LABEL_32:
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(0);
  if ( *(_QWORD *)v28 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 16LL))(*(_QWORD *)v28);
    *(_QWORD *)v28 = 0;
  }
  if ( *(_QWORD *)v25 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v25 + 16LL))(*(_QWORD *)v25);
    *(_QWORD *)v25 = 0;
  }
  if ( v26 )
  {
    ((void (__fastcall *)(struct IUnknown *))v26->lpVtbl->Release)(v26);
    v26 = 0;
  }
  SysFreeString(bstrString);
  bstrString = 0;
  if ( v29 )
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v29 + 16LL))(v29);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x14003e814  mov     [rsp-8+arg_10], rbx
0x14003e819  mov     [rsp-8+arg_18], rsi
0x14003e81e  push    rbp
0x14003e81f  push    rdi
0x14003e820  push    r14
0x14003e822  lea     rbp, [rsp-3Fh]
0x14003e827  sub     rsp, 0C0h
0x14003e82e  mov     rax, cs:__security_cookie
0x14003e835  xor     rax, rsp
0x14003e838  mov     [rbp+4Fh+var_20], rax
0x14003e83c  mov     rdi, rdx
0x14003e83f  mov     rsi, rcx
0x14003e842  xor     r14d, r14d
0x14003e845  mov     [rbp+4Fh+var_38], r14
0x14003e849  mov     [rbp+4Fh+bstrString], r14
0x14003e84d  mov     [rbp+4Fh+var_50], r14
0x14003e851  mov     qword ptr [rbp+4Fh+var_58], r14
0x14003e855  mov     qword ptr [rbp+4Fh+var_40], r14
0x14003e859  mov     [rbp+4Fh+var_78], r14
0x14003e85d  movups  xmm0, xmmword ptr cs:aUnknown; "Unknown"
0x14003e864  movdqu  xmmword ptr [rbp+4Fh+var_30], xmm0
0x14003e869  mov     [rbp+4Fh+var_A0], r14
0x14003e86d  mov     [rbp+4Fh+var_98], r14
0x14003e871  mov     [rbp+4Fh+var_70], r14
0x14003e875  mov     [rbp+4Fh+var_68], r14
0x14003e879  mov     [rbp+4Fh+var_60], r14
0x14003e87d  mov     [rcx], r14
0x14003e880  mov     [rdx], r14
0x14003e883  lea     rax, [rbp+4Fh+var_38]
0x14003e887  mov     [rsp+0D0h+ppv], rax; wchar_t **
0x14003e88c  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x14003e893  xor     edx, edx; pUnkOuter
0x14003e895  lea     r8d, [r14+1]; dwClsContext
0x14003e899  lea     rcx, CLSID_WbemLocator; rclsid
0x14003e8a0  call    cs:__imp_CoCreateInstance
0x14003e8a6  mov     ebx, eax
0x14003e8a8  mov     eax, 80240056h
0x14003e8ad  cmp     ebx, 80040154h
0x14003e8b3  jz      loc_14003EAA3
0x14003e8b9  test    ebx, ebx
0x14003e8bb  jns     short loc_14003E8CF
0x14003e8bd  cmp     ebx, eax
0x14003e8bf  jz      loc_14003EAA3
0x14003e8c5  mov     r9d, ebx
0x14003e8c8  mov     edx, 0E7h
0x14003e8cd  jmp     short loc_14003E94D
0x14003e8cf  lea     rbx, aRootCimv2; "\\\\.\\root\\cimv2"
0x14003e8d6  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x14003e8da  cmp     rbx, rcx
0x14003e8dd  jz      short loc_14003E908
0x14003e8df  call    cs:__imp_SysFreeString
0x14003e8e5  mov     [rbp+4Fh+bstrString], r14
0x14003e8e9  mov     r8d, 0Eh; unsigned int
0x14003e8ef  mov     rdx, rbx; wchar_t *
0x14003e8f2  lea     rcx, [rbp+4Fh+bstrString]; this
0x14003e8f6  call    ?Append@CSusBSTR@@QEAAJPEB_WK@Z; CSusBSTR::Append(wchar_t const *,ulong)
0x14003e8fb  mov     ebx, eax
0x14003e8fd  test    eax, eax
0x14003e8ff  jns     short loc_14003E908
0x14003e901  mov     edx, 0E9h
0x14003e906  jmp     short loc_14003E94A
0x14003e908  lea     rax, [rbp+4Fh+var_38]
0x14003e90c  mov     [rbp+4Fh+var_90], rax
0x14003e910  lea     rax, [rbp+4Fh+bstrString]
0x14003e914  mov     [rbp+4Fh+var_88], rax
0x14003e918  lea     rax, [rbp+4Fh+var_50]
0x14003e91c  mov     [rbp+4Fh+var_80], rax
0x14003e920  lea     rcx, [rbp+4Fh+var_90]
0x14003e924  call    WUComTimeout__ComTimeout__MakeComCall__lambda_910c479648d882804510b1671eed198a___
0x14003e929  mov     ebx, eax
0x14003e92b  test    eax, eax
0x14003e92d  jns     short loc_14003E936
0x14003e92f  mov     edx, 0F4h
0x14003e934  jmp     short loc_14003E94A
0x14003e936  mov     rcx, [rbp+4Fh+var_50]; struct IUnknown *
0x14003e93a  call    ?SetProxyBlanketImpersonationLevel@@YAJPEAUIUnknown@@KPEAH@Z; SetProxyBlanketImpersonationLevel(IUnknown *,ulong,int *)
0x14003e93f  mov     ebx, eax
0x14003e941  test    eax, eax
0x14003e943  jns     short loc_14003E962
0x14003e945  mov     edx, 0F6h; void *
0x14003e94a  mov     r9d, eax; char *
0x14003e94d  lea     r8, aCW1SSrcClientL_38; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003e954  mov     rcx, [rbp+57h]; this
0x14003e958  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e95d  jmp     loc_14003EAA5
0x14003e962  mov     rcx, qword ptr [rbp+4Fh+var_58]
0x14003e966  test    rcx, rcx
0x14003e969  jz      short loc_14003E97B
0x14003e96b  mov     rax, [rcx]
0x14003e96e  mov     rax, [rax+10h]
0x14003e972  call    _guard_dispatch_icall
0x14003e977  mov     qword ptr [rbp+4Fh+var_58], r14
0x14003e97b  lea     r8, [rbp+4Fh+var_58]; wchar_t *
0x14003e97f  lea     rdx, stru_14006EAC0; struct IWbemServices *
0x14003e986  mov     rcx, [rbp+4Fh+var_50]; this
0x14003e98a  call    ?GetFirstWbemObject@WBemUtil@@YAJPEAUIWbemServices@@PEB_WPEAPEAUIWbemClassObject@@@Z; WBemUtil::GetFirstWbemObject(IWbemServices *,wchar_t const *,IWbemClassObject * *)
0x14003e98f  test    eax, eax
0x14003e991  js      loc_14003EA71
0x14003e997  xor     ecx, ecx; bstrString
0x14003e999  call    cs:__imp_SysFreeString
0x14003e99f  mov     [rbp+4Fh+var_A0], r14
0x14003e9a3  lea     r9, [rbp+4Fh+var_A0]; wchar_t *
0x14003e9a7  lea     r8, [rbp+4Fh+var_30]; wchar_t *
0x14003e9ab  lea     rdx, stru_14006EAA0; struct IWbemClassObject *
0x14003e9b2  mov     rcx, qword ptr [rbp+4Fh+var_58]; this
0x14003e9b6  call    ?GetWbemObjectBSTR@WBemUtil@@YAJPEAUIWbemClassObject@@PEB_W1PEAPEA_W@Z; WBemUtil::GetWbemObjectBSTR(IWbemClassObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x14003e9bb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14003e9bf  test    eax, eax
0x14003e9c1  mov     rax, [rbp+4Fh+var_A0]
0x14003e9c5  jns     short loc_14003E9FF
0x14003e9c7  lea     rcx, [rbp+4Fh+var_30]
0x14003e9cb  cmp     rcx, rax
0x14003e9ce  jz      short loc_14003E9FF
0x14003e9d0  mov     rcx, rax; bstrString
0x14003e9d3  call    cs:__imp_SysFreeString
0x14003e9d9  mov     [rbp+4Fh+var_A0], r14
0x14003e9dd  lea     rax, [rbp+4Fh+var_30]
0x14003e9e1  mov     r8, rbx
0x14003e9e4  inc     r8; unsigned int
0x14003e9e7  cmp     [rax+r8*2], r14w
0x14003e9ec  jnz     short loc_14003E9E4
0x14003e9ee  lea     rdx, [rbp+4Fh+var_30]; wchar_t *
0x14003e9f2  lea     rcx, [rbp+4Fh+var_A0]; this
0x14003e9f6  call    ?Append@CSusBSTR@@QEAAJPEB_WK@Z; CSusBSTR::Append(wchar_t const *,ulong)
0x14003e9fb  mov     rax, [rbp+4Fh+var_A0]
0x14003e9ff  mov     [rbp+4Fh+var_A0], r14
0x14003ea03  mov     [rsi], rax
0x14003ea06  xor     ecx, ecx; bstrString
0x14003ea08  call    cs:__imp_SysFreeString
0x14003ea0e  mov     [rbp+4Fh+var_98], r14
0x14003ea12  lea     r9, [rbp+4Fh+var_98]; wchar_t *
0x14003ea16  lea     r8, [rbp+4Fh+var_30]; wchar_t *
0x14003ea1a  lea     rdx, stru_14006EB08; struct IWbemClassObject *
0x14003ea21  mov     rcx, qword ptr [rbp+4Fh+var_58]; this
0x14003ea25  call    ?GetWbemObjectBSTR@WBemUtil@@YAJPEAUIWbemClassObject@@PEB_W1PEAPEA_W@Z; WBemUtil::GetWbemObjectBSTR(IWbemClassObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x14003ea2a  test    eax, eax
0x14003ea2c  mov     rax, [rbp+4Fh+var_98]
0x14003ea30  jns     short loc_14003EA6A
0x14003ea32  lea     rcx, [rbp+4Fh+var_30]
0x14003ea36  cmp     rcx, rax
0x14003ea39  jz      short loc_14003EA6A
0x14003ea3b  mov     rcx, rax; bstrString
0x14003ea3e  call    cs:__imp_SysFreeString
0x14003ea44  mov     [rbp+4Fh+var_98], r14
0x14003ea48  lea     rax, [rbp+4Fh+var_30]
0x14003ea4c  inc     rbx
0x14003ea4f  cmp     [rax+rbx*2], r14w
0x14003ea54  jnz     short loc_14003EA4C
0x14003ea56  mov     r8d, ebx; unsigned int
0x14003ea59  lea     rdx, [rbp+4Fh+var_30]; wchar_t *
0x14003ea5d  lea     rcx, [rbp+4Fh+var_98]; this
0x14003ea61  call    ?Append@CSusBSTR@@QEAAJPEB_WK@Z; CSusBSTR::Append(wchar_t const *,ulong)
0x14003ea66  mov     rax, [rbp+4Fh+var_98]
0x14003ea6a  mov     [rbp+4Fh+var_98], r14
0x14003ea6e  mov     [rdi], rax
0x14003ea71  mov     rcx, qword ptr [rbp+4Fh+var_40]
0x14003ea75  test    rcx, rcx
0x14003ea78  jz      short loc_14003EA8A
0x14003ea7a  mov     rax, [rcx]
0x14003ea7d  mov     rax, [rax+10h]
0x14003ea81  call    _guard_dispatch_icall
0x14003ea86  mov     qword ptr [rbp+4Fh+var_40], r14
0x14003ea8a  lea     r8, [rbp+4Fh+var_40]; wchar_t *
0x14003ea8e  lea     rdx, stru_14006EAF0; struct IWbemServices *
0x14003ea95  mov     rcx, [rbp+4Fh+var_50]; this
0x14003ea99  call    ?GetFirstWbemObject@WBemUtil@@YAJPEAUIWbemServices@@PEB_WPEAPEAUIWbemClassObject@@@Z; WBemUtil::GetFirstWbemObject(IWbemServices *,wchar_t const *,IWbemClassObject * *)
0x14003ea9e  mov     ebx, r14d
0x14003eaa1  jmp     short loc_14003EAA5
0x14003eaa3  mov     ebx, eax
0x14003eaa5  xor     ecx, ecx; bstrString
0x14003eaa7  call    cs:__imp_SysFreeString
0x14003eaad  nop
0x14003eaae  xor     ecx, ecx; bstrString
0x14003eab0  call    cs:__imp_SysFreeString
0x14003eab6  nop
0x14003eab7  xor     ecx, ecx; bstrString
0x14003eab9  call    cs:__imp_SysFreeString
0x14003eabf  nop
0x14003eac0  xor     ecx, ecx; bstrString
0x14003eac2  call    cs:__imp_SysFreeString
0x14003eac8  nop
0x14003eac9  xor     ecx, ecx; bstrString
0x14003eacb  call    cs:__imp_SysFreeString
0x14003ead1  nop
0x14003ead2  xor     ecx, ecx; bstrString
0x14003ead4  call    cs:__imp_SysFreeString
0x14003eada  nop
0x14003eadb  mov     rcx, qword ptr [rbp+4Fh+var_40]
0x14003eadf  test    rcx, rcx
0x14003eae2  jz      short loc_14003EAF4
0x14003eae4  mov     rax, [rcx]
0x14003eae7  mov     rax, [rax+10h]
0x14003eaeb  call    _guard_dispatch_icall
0x14003eaf0  mov     qword ptr [rbp+4Fh+var_40], r14
0x14003eaf4  mov     rcx, qword ptr [rbp+4Fh+var_58]
0x14003eaf8  test    rcx, rcx
0x14003eafb  jz      short loc_14003EB0D
0x14003eafd  mov     rax, [rcx]
0x14003eb00  mov     rax, [rax+10h]
0x14003eb04  call    _guard_dispatch_icall
0x14003eb09  mov     qword ptr [rbp+4Fh+var_58], r14
0x14003eb0d  mov     rcx, [rbp+4Fh+var_50]
0x14003eb11  test    rcx, rcx
0x14003eb14  jz      short loc_14003EB26
0x14003eb16  mov     rax, [rcx]
0x14003eb19  mov     rax, [rax+10h]
0x14003eb1d  call    _guard_dispatch_icall
0x14003eb22  mov     [rbp+4Fh+var_50], r14
0x14003eb26  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x14003eb2a  call    cs:__imp_SysFreeString
0x14003eb30  mov     [rbp+4Fh+bstrString], r14
0x14003eb34  mov     rcx, [rbp+4Fh+var_38]
0x14003eb38  test    rcx, rcx
0x14003eb3b  jz      short loc_14003EB4A
0x14003eb3d  mov     rdx, [rcx]
0x14003eb40  mov     rax, [rdx+10h]
0x14003eb44  call    _guard_dispatch_icall
0x14003eb49  nop
0x14003eb4a  mov     eax, ebx
0x14003eb4c  mov     rcx, [rbp+4Fh+var_20]
0x14003eb50  xor     rcx, rsp; StackCookie
0x14003eb53  call    __security_check_cookie
0x14003eb58  lea     r11, [rsp+0D0h+var_10]
0x14003eb60  mov     rbx, [r11+30h]
0x14003eb64  mov     rsi, [r11+38h]
0x14003eb68  mov     rsp, r11
0x14003eb6b  pop     r14
0x14003eb6d  pop     rdi
0x14003eb6e  pop     rbp
0x14003eb6f  retn
```
