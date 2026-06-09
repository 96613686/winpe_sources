# CCommonAttributeProvider::AppendDeviceTarget(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)

- ea: `0x14003612c`
- end: `0x1400364a5`
- name: `?AppendDeviceTarget@CCommonAttributeProvider@@AEAAJPEA_W_KPEAPEA_WPEA_K@Z`
- size: `889`
- prototype: `__int64 __fastcall(CCommonAttributeProvider *this, wchar_t *, unsigned __int64, wchar_t **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140034ccc`

## callees

- `0x1400154b4`
- `0x140033160`
- `0x14003612c`
- `0x14003d2c0`
- `0x14003e814`
- `0x140045dc0`
- `0x14004cd80`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140036185`
- `OLEAUT32!__imp_SysFreeString` at `0x140036195`
- `OLEAUT32!__imp_SysFreeString` at `0x140036466`
- `OLEAUT32!__imp_SysFreeString` at `0x140036476`
- `OLEAUT32!__imp_SysFreeString` at `0x140036185`
- `OLEAUT32!__imp_SysFreeString` at `0x140036195`
- `OLEAUT32!__imp_SysFreeString` at `0x140036466`
- `OLEAUT32!__imp_SysFreeString` at `0x140036476`
- `OLEAUT32!__imp_SysStringLen` at `0x140036212`
- `OLEAUT32!__imp_SysStringLen` at `0x140036339`
- `OLEAUT32!__imp_SysStringLen` at `0x140036212`
- `OLEAUT32!__imp_SysStringLen` at `0x140036339`

## string_xrefs

- `0x1400361e6`: `GetComputerInfoFromWMI`
- `0x1400361cb`: `WMI-related computer info disabled; WMI isn't present.`
- `0x140036380`: `Computer Model Value percent-encoding`
- `0x140036259`: `Computer Make Value percent-encoding`
- `0x140036454`: `CCommonAttributeProvider::AppendDeviceTarget`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCommonAttributeProvider::AppendDeviceTarget(
        CCommonAttributeProvider *this,
        wchar_t *a2,
        unsigned __int64 a3,
        wchar_t **a4,
        unsigned __int64 *a5)
{
  unsigned __int64 v5; // r15
  wchar_t *v6; // r14
  int ComputerInfoFromWMI; // eax
  int v8; // ebx
  signed int v9; // eax
  signed int v10; // esi
  unsigned __int64 v11; // r9
  int v12; // eax
  signed int v13; // eax
  signed int v14; // esi
  unsigned __int64 v15; // r9
  int v16; // eax
  wchar_t **v18; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v19; // [rsp+28h] [rbp-D8h]
  const wchar_t *v20; // [rsp+28h] [rbp-D8h]
  unsigned int v21; // [rsp+30h] [rbp-D0h]
  unsigned int v22; // [rsp+30h] [rbp-D0h]
  unsigned int v23; // [rsp+30h] [rbp-D0h]
  unsigned int v24; // [rsp+30h] [rbp-D0h]
  unsigned int v25; // [rsp+30h] [rbp-D0h]
  wchar_t *v26; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  BSTR pbstr; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v30; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v31[382]; // [rsp+62h] [rbp-9Eh] BYREF

  v5 = a3;
  v6 = a2;
  v26 = a2;
  v27 = a3;
  bstrString = 0;
  *a4 = a2;
  *a5 = a3;
  SysFreeString(0);
  pbstr = 0;
  SysFreeString(bstrString);
  bstrString = 0;
  ComputerInfoFromWMI = WBemUtil::GetComputerInfoFromWMI((WBemUtil *)&bstrString, &pbstr, 0, 0, 0, (wchar_t **)v19);
  v8 = ComputerInfoFromWMI;
  if ( ComputerInfoFromWMI >= 0 )
  {
    v9 = SysStringLen(bstrString);
    v10 = v9;
    if ( v9 > 0 && (unsigned int)v9 < 0x40 )
    {
      v30 = 0;
      memset(v31, 0, sizeof(v31));
      v12 = EncodeQueryStringValue(bstrString, v10 + 1, &v30, v11);
      if ( v12 >= 0 )
      {
        v8 = StringCchCatNExW(v6, v5, L"&", 1u, &v26, &v27, v21);
        if ( v8 < 0 )
          goto LABEL_23;
        v8 = StringCchCatNExW(v26, v27, L"MK=", 4u, &v26, &v27, v22);
        if ( v8 < 0 )
          goto LABEL_23;
        v8 = StringCchCatNExW(v26, v27, &v30, 0xC0u, &v26, &v27, v23);
        if ( v8 < 0 )
          goto LABEL_23;
        v6 = v26;
        v5 = v27;
      }
      else
      {
        LODWORD(v18) = v12;
        WUTrace(0, 0, 4, 3, v18, L"Computer Make Value percent-encoding");
        v8 = 0;
      }
    }
    v13 = SysStringLen(pbstr);
    v14 = v13;
    if ( v13 > 0 && (unsigned int)v13 < 0x40 )
    {
      v30 = 0;
      memset(v31, 0, sizeof(v31));
      v16 = EncodeQueryStringValue(pbstr, v14 + 1, &v30, v15);
      if ( v16 < 0 )
      {
        v20 = L"Computer Model Value percent-encoding";
        LODWORD(v18) = v16;
        goto LABEL_5;
      }
      v8 = StringCchCatNExW(v6, v5, L"&", 1u, &v26, &v27, v21);
      if ( v8 < 0 || (v8 = StringCchCatNExW(v26, v27, L"MD=", 4u, &v26, &v27, v24), v8 < 0) )
      {
LABEL_23:
        LODWORD(v18) = v8;
        WUTrace("CCommonAttributeProvider::AppendDeviceTarget", 825, 4, 1, v18, L"Method failed");
        goto LABEL_24;
      }
      v8 = StringCchCatNExW(v26, v27, &v30, 0xC0u, &v26, &v27, v25);
    }
    if ( v8 >= 0 )
      goto LABEL_24;
    goto LABEL_23;
  }
  if ( ComputerInfoFromWMI != -2145124266 )
  {
    v20 = L"GetComputerInfoFromWMI";
    LODWORD(v18) = ComputerInfoFromWMI;
LABEL_5:
    WUTrace(0, 0, 4, 3, v18, v20);
    goto LABEL_6;
  }
  WUTrace(0, 0, 4, 4, 0, L"WMI-related computer info disabled; WMI isn't present.");
LABEL_6:
  v8 = 0;
LABEL_24:
  SysFreeString(pbstr);
  pbstr = 0;
  SysFreeString(bstrString);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14003612c  mov     [rsp-8+arg_0], rbx
0x140036131  push    rbp
0x140036132  push    rsi
0x140036133  push    r12
0x140036135  push    r14
0x140036137  push    r15
0x140036139  lea     rbp, [rsp-0F0h]
0x140036141  sub     rsp, 1F0h
0x140036148  mov     rax, cs:__security_cookie
0x14003614f  xor     rax, rsp
0x140036152  mov     [rbp+110h+var_30], rax
0x140036159  mov     r15, r8
0x14003615c  mov     r14, rdx
0x14003615f  mov     [rsp+210h+var_1D0], rdx
0x140036164  mov     [rsp+210h+var_1C8], r8
0x140036169  mov     rax, [rbp+110h+arg_20]
0x140036170  xor     r12d, r12d
0x140036173  mov     [rsp+210h+bstrString], r12
0x140036178  mov     [rsp+210h+pbstr], r12
0x14003617d  mov     [r9], rdx
0x140036180  mov     [rax], r8
0x140036183  xor     ecx, ecx; bstrString
0x140036185  call    cs:__imp_SysFreeString
0x14003618b  mov     [rsp+210h+pbstr], r12
0x140036190  mov     rcx, [rsp+210h+bstrString]; bstrString
0x140036195  call    cs:__imp_SysFreeString
0x14003619b  mov     [rsp+210h+bstrString], r12
0x1400361a0  mov     [rsp+210h+var_1F0], r12; wchar_t **
0x1400361a5  xor     r9d, r9d; wchar_t **
0x1400361a8  xor     r8d, r8d; wchar_t **
0x1400361ab  lea     rdx, [rsp+210h+pbstr]; wchar_t **
0x1400361b0  lea     rcx, [rsp+210h+bstrString]; this
0x1400361b5  call    ?GetComputerInfoFromWMI@WBemUtil@@YAJPEAPEA_W0000@Z; WBemUtil::GetComputerInfoFromWMI(wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *)
0x1400361ba  mov     ebx, eax
0x1400361bc  test    eax, eax
0x1400361be  jns     short loc_14003620D
0x1400361c0  xor     edx, edx
0x1400361c2  xor     ecx, ecx
0x1400361c4  cmp     eax, 80240056h
0x1400361c9  jnz     short loc_1400361E6
0x1400361cb  lea     rax, aWmiRelatedComp; "WMI-related computer info disabled; WMI"...
0x1400361d2  mov     [rsp+210h+var_1E8], rax
0x1400361d7  mov     [rsp+210h+var_1F0], r12
0x1400361dc  lea     r9d, [r12+4]
0x1400361e1  mov     r8d, r9d
0x1400361e4  jmp     short loc_140036200
0x1400361e6  lea     rax, aGetcomputerinf; "GetComputerInfoFromWMI"
0x1400361ed  mov     [rsp+210h+var_1E8], rax
0x1400361f2  mov     dword ptr [rsp+210h+var_1F0], ebx
0x1400361f6  mov     r9d, 3
0x1400361fc  lea     r8d, [r9+1]
0x140036200  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140036205  mov     ebx, r12d
0x140036208  jmp     loc_140036461
0x14003620d  mov     rcx, [rsp+210h+bstrString]; pbstr
0x140036212  call    cs:__imp_SysStringLen
0x140036218  mov     esi, eax
0x14003621a  test    eax, eax
0x14003621c  jle     loc_140036334
0x140036222  cmp     eax, 40h ; '@'
0x140036225  jnb     loc_140036334
0x14003622b  mov     [rsp+210h+var_1B0], r12w
0x140036231  xor     edx, edx; Val
0x140036233  mov     r8d, 17Eh; Size
0x140036239  lea     rcx, [rsp+210h+var_1AE]; void *
0x14003623e  call    memset
0x140036243  lea     edx, [rsi+1]; unsigned int
0x140036246  lea     r8, [rsp+210h+var_1B0]; wchar_t *
0x14003624b  mov     rcx, [rsp+210h+bstrString]; wchar_t *
0x140036250  call    ?EncodeQueryStringValue@@YAJPEB_WIPEA_W_K@Z; EncodeQueryStringValue(wchar_t const *,uint,wchar_t *,unsigned __int64)
0x140036255  test    eax, eax
0x140036257  jns     short loc_140036282
0x140036259  lea     rcx, aComputerMakeVa; "Computer Make Value percent-encoding"
0x140036260  mov     [rsp+210h+var_1E8], rcx
0x140036265  mov     dword ptr [rsp+210h+var_1F0], eax
0x140036269  xor     edx, edx
0x14003626b  xor     ecx, ecx
0x14003626d  lea     r9d, [rdx+3]
0x140036271  lea     r8d, [rdx+4]
0x140036275  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003627a  mov     ebx, r12d
0x14003627d  jmp     loc_140036334
0x140036282  lea     rax, [rsp+210h+var_1C8]
0x140036287  mov     [rsp+210h+var_1E8], rax; unsigned __int64 *
0x14003628c  lea     rax, [rsp+210h+var_1D0]
0x140036291  mov     [rsp+210h+var_1F0], rax; wchar_t **
0x140036296  mov     r9d, 1; unsigned __int64
0x14003629c  lea     r8, asc_14006C8E0; "&"
0x1400362a3  mov     rdx, r15; unsigned __int64
0x1400362a6  mov     rcx, r14; wchar_t *
0x1400362a9  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x1400362ae  mov     ebx, eax
0x1400362b0  test    eax, eax
0x1400362b2  js      loc_140036435
0x1400362b8  lea     rax, [rsp+210h+var_1C8]
0x1400362bd  mov     [rsp+210h+var_1E8], rax; unsigned __int64 *
0x1400362c2  lea     rax, [rsp+210h+var_1D0]
0x1400362c7  mov     [rsp+210h+var_1F0], rax; wchar_t **
0x1400362cc  mov     r9d, 4; unsigned __int64
0x1400362d2  lea     r8, aMk; "MK="
0x1400362d9  mov     rdx, [rsp+210h+var_1C8]; unsigned __int64
0x1400362de  mov     rcx, [rsp+210h+var_1D0]; wchar_t *
0x1400362e3  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x1400362e8  mov     ebx, eax
0x1400362ea  test    eax, eax
0x1400362ec  js      loc_140036435
0x1400362f2  lea     rax, [rsp+210h+var_1C8]
0x1400362f7  mov     [rsp+210h+var_1E8], rax; unsigned __int64 *
0x1400362fc  lea     rax, [rsp+210h+var_1D0]
0x140036301  mov     [rsp+210h+var_1F0], rax; wchar_t **
0x140036306  mov     r9d, 0C0h; unsigned __int64
0x14003630c  lea     r8, [rsp+210h+var_1B0]; wchar_t *
0x140036311  mov     rdx, [rsp+210h+var_1C8]; unsigned __int64
0x140036316  mov     rcx, [rsp+210h+var_1D0]; wchar_t *
0x14003631b  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140036320  mov     ebx, eax
0x140036322  test    eax, eax
0x140036324  js      loc_140036435
0x14003632a  mov     r14, [rsp+210h+var_1D0]
0x14003632f  mov     r15, [rsp+210h+var_1C8]
0x140036334  mov     rcx, [rsp+210h+pbstr]; pbstr
0x140036339  call    cs:__imp_SysStringLen
0x14003633f  mov     esi, eax
0x140036341  test    eax, eax
0x140036343  jle     loc_140036431
0x140036349  cmp     eax, 40h ; '@'
0x14003634c  jnb     loc_140036431
0x140036352  mov     [rsp+210h+var_1B0], r12w
0x140036358  xor     edx, edx; Val
0x14003635a  mov     r8d, 17Eh; Size
0x140036360  lea     rcx, [rsp+210h+var_1AE]; void *
0x140036365  call    memset
0x14003636a  lea     edx, [rsi+1]; unsigned int
0x14003636d  lea     r8, [rsp+210h+var_1B0]; wchar_t *
0x140036372  mov     rcx, [rsp+210h+pbstr]; wchar_t *
0x140036377  call    ?EncodeQueryStringValue@@YAJPEB_WIPEA_W_K@Z; EncodeQueryStringValue(wchar_t const *,uint,wchar_t *,unsigned __int64)
0x14003637c  test    eax, eax
0x14003637e  jns     short loc_140036399
0x140036380  lea     rcx, aComputerModelV; "Computer Model Value percent-encoding"
0x140036387  mov     [rsp+210h+var_1E8], rcx
0x14003638c  mov     dword ptr [rsp+210h+var_1F0], eax
0x140036390  xor     edx, edx
0x140036392  xor     ecx, ecx
0x140036394  jmp     loc_1400361F6
0x140036399  lea     rax, [rsp+210h+var_1C8]
0x14003639e  mov     [rsp+210h+var_1E8], rax; unsigned __int64 *
0x1400363a3  lea     rax, [rsp+210h+var_1D0]
0x1400363a8  mov     [rsp+210h+var_1F0], rax; wchar_t **
0x1400363ad  mov     r9d, 1; unsigned __int64
0x1400363b3  lea     r8, asc_14006C8E0; "&"
0x1400363ba  mov     rdx, r15; unsigned __int64
0x1400363bd  mov     rcx, r14; wchar_t *
0x1400363c0  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x1400363c5  mov     ebx, eax
0x1400363c7  test    eax, eax
0x1400363c9  js      short loc_140036435
0x1400363cb  lea     rax, [rsp+210h+var_1C8]
0x1400363d0  mov     [rsp+210h+var_1E8], rax; unsigned __int64 *
0x1400363d5  lea     rax, [rsp+210h+var_1D0]
0x1400363da  mov     [rsp+210h+var_1F0], rax; wchar_t **
0x1400363df  mov     r9d, 4; unsigned __int64
0x1400363e5  lea     r8, aMd; "MD="
0x1400363ec  mov     rdx, [rsp+210h+var_1C8]; unsigned __int64
0x1400363f1  mov     rcx, [rsp+210h+var_1D0]; wchar_t *
0x1400363f6  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x1400363fb  mov     ebx, eax
0x1400363fd  test    eax, eax
0x1400363ff  js      short loc_140036435
0x140036401  lea     rax, [rsp+210h+var_1C8]
0x140036406  mov     [rsp+210h+var_1E8], rax; unsigned __int64 *
0x14003640b  lea     rax, [rsp+210h+var_1D0]
0x140036410  mov     [rsp+210h+var_1F0], rax; wchar_t **
0x140036415  mov     r9d, 0C0h; unsigned __int64
0x14003641b  lea     r8, [rsp+210h+var_1B0]; wchar_t *
0x140036420  mov     rdx, [rsp+210h+var_1C8]; unsigned __int64
0x140036425  mov     rcx, [rsp+210h+var_1D0]; wchar_t *
0x14003642a  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x14003642f  mov     ebx, eax
0x140036431  test    ebx, ebx
0x140036433  jns     short loc_140036461
0x140036435  lea     rax, aMethodFailed; "Method failed"
0x14003643c  mov     [rsp+210h+var_1E8], rax
0x140036441  mov     dword ptr [rsp+210h+var_1F0], ebx
0x140036445  mov     edx, 339h
0x14003644a  mov     r9d, 1
0x140036450  lea     r8d, [r9+3]
0x140036454  lea     rcx, aCcommonattribu_4; "CCommonAttributeProvider::AppendDeviceT"...
0x14003645b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140036460  nop
0x140036461  mov     rcx, [rsp+210h+pbstr]; bstrString
0x140036466  call    cs:__imp_SysFreeString
0x14003646c  mov     [rsp+210h+pbstr], r12
0x140036471  mov     rcx, [rsp+210h+bstrString]; bstrString
0x140036476  call    cs:__imp_SysFreeString
0x14003647c  mov     eax, ebx
0x14003647e  mov     rcx, [rbp+110h+var_30]
0x140036485  xor     rcx, rsp; StackCookie
0x140036488  call    __security_check_cookie
0x14003648d  mov     rbx, [rsp+210h+arg_0]
0x140036495  add     rsp, 1F0h
0x14003649c  pop     r15
0x14003649e  pop     r14
0x1400364a0  pop     r12
0x1400364a2  pop     rsi
0x1400364a3  pop     rbp
0x1400364a4  retn
```
