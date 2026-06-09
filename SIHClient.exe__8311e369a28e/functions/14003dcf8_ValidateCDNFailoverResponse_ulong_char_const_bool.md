# ValidateCDNFailoverResponse(ulong,char const *,bool *)

- ea: `0x14003dcf8`
- end: `0x14003e23a`
- name: `?ValidateCDNFailoverResponse@@YAJKPEBDPEA_N@Z`
- size: `1346`
- prototype: `__int64 __fastcall(unsigned int, const char *, bool *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400333b4`

## callees

- `0x140003de4`
- `0x140008de4`
- `0x14000ce30`
- `0x14000fc20`
- `0x1400113a4`
- `0x1400154b4`
- `0x140017bd0`
- `0x140018658`
- `0x14001869c`
- `0x14003d4ac`
- `0x14003d4fc`
- `0x14003dcf8`
- `0x140045dc0`
- `0x14004cd00`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14003e131`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14003e131`
- `OLEAUT32!__imp_SysStringLen` at `0x14003dfb1`
- `OLEAUT32!__imp_SysStringLen` at `0x14003dfb1`
- `OLEAUT32!__imp_VariantInit` at `0x14003df51`
- `OLEAUT32!__imp_VariantInit` at `0x14003e070`
- `OLEAUT32!__imp_VariantInit` at `0x14003df51`
- `OLEAUT32!__imp_VariantInit` at `0x14003e070`
- `OLEAUT32!__imp_VariantClear` at `0x14003dff8`
- `OLEAUT32!__imp_VariantClear` at `0x14003e150`
- `OLEAUT32!__imp_VariantClear` at `0x14003e175`
- `OLEAUT32!__imp_VariantClear` at `0x14003e1a4`
- `OLEAUT32!__imp_VariantClear` at `0x14003dff8`
- `OLEAUT32!__imp_VariantClear` at `0x14003e150`
- `OLEAUT32!__imp_VariantClear` at `0x14003e175`
- `OLEAUT32!__imp_VariantClear` at `0x14003e1a4`

## string_xrefs

- `0x14003dd9f`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x14003dd98`: `SLSCDNXML`
- `0x14003de6e`: `/ServiceEnvironment`
- `0x14003e0eb`: `C:\__w\1\s\src\Client\lib\util\XmlSchemaUtil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=44
__int64 __fastcall ValidateCDNFailoverResponse(unsigned int a1, const char *a2, bool *a3)
{
  char *pcVal; // rbx
  unsigned int v8; // edi
  __int64 v9; // rcx
  BSTR bstrVal; // rcx
  int v11; // edi
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  unsigned int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  int v21; // edi
  int v22; // r8d
  int v23; // [rsp+20h] [rbp-E0h]
  __int64 v24; // [rsp+20h] [rbp-E0h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v26; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h] BYREF
  struct _FILETIME v30; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v32[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
      (const char *)0x80004003LL,
      v23);
    return 2147500035LL;
  }
  *a3 = 0;
  pcVal = 0;
  v8 = 0;
  if ( (unsigned int)AreTestKeysAllowed() )
  {
    memset(v32, 0, 520);
    if ( (int)RegQueryStringValue(
                v9,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                (__int64)L"SLSCDNXML",
                (__int64)v32,
                260) >= 0 )
    {
      *(_QWORD *)&pvarg.vt = &CSafeBuffer<unsigned char>::`vftable';
      *(_OWORD *)&pvarg.decVal.Lo32 = 0u;
      if ( (int)ReadFileToSafeByteBuffer(v32, (__int64)&pvarg) < 0 )
      {
        bstrVal = pvarg.bstrVal;
      }
      else
      {
        pcVal = pvarg.pcVal;
        bstrVal = 0;
        v8 = *((_DWORD *)&pvarg.decVal + 5);
      }
      SusFree(bstrVal);
    }
  }
  v26 = 0;
  if ( !pcVal || !v8 )
  {
    v11 = CWUSLSParse::Init((CWUSLSParse *)&v26, a1, a2);
    if ( v11 < 0 )
    {
      v12 = 1225;
      goto LABEL_15;
    }
LABEL_16:
    v29 = 0;
    v13 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 *))(*(_QWORD *)v26 + 296LL))(
            v26,
            L"/ServiceEnvironment",
            &v29);
    v11 = v13;
    if ( v13 == 1 )
    {
      v11 = 0;
      goto LABEL_64;
    }
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D4,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
        (const char *)(unsigned int)v13,
        v23);
LABEL_64:
      if ( v29 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        v29 = 0;
      }
      goto LABEL_66;
    }
    v28 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 136LL))(v29, &v28);
    v11 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D7,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
        (const char *)(unsigned int)v14,
        v23);
LABEL_62:
      if ( v28 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        v28 = 0;
      }
      goto LABEL_64;
    }
    v27 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v28 + 56LL))(v28, L"CDN", &v27);
    v11 = v15;
    if ( v15 == 1 )
    {
      v11 = 0;
      goto LABEL_60;
    }
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E0,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
        (const char *)(unsigned int)v15,
        v23);
      goto LABEL_60;
    }
    VariantInit(&pvarg);
    v11 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v27 + 64LL))(v27, &pvarg);
    if ( v11 < 0 )
    {
      v16 = 1251;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
        (const char *)(unsigned int)v11,
        v23);
LABEL_59:
      VariantClear(&pvarg);
LABEL_60:
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      goto LABEL_62;
    }
    if ( pvarg.vt != 8 )
    {
      v11 = -2145103617;
      v16 = 1252;
      goto LABEL_30;
    }
    v17 = SysStringLen(pvarg.bstrVal) + 1;
    if ( !pvarg.llVal
      || v17 <= 1
      || (v17 != 2 || *pvarg.bstrVal != 49) && WUCompareStringCchI(L"true", pvarg.bstrVal, v17) != 2 )
    {
      v11 = 0;
      goto LABEL_59;
    }
    VariantClear(&pvarg);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v28 + 56LL))(
            v28,
            L"Expiration",
            &v27);
    v11 = v18;
    if ( v18 == 1 )
    {
      v11 = 0;
      goto LABEL_52;
    }
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F3,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
        (const char *)(unsigned int)v18,
        v23);
      goto LABEL_52;
    }
    VariantInit(&pvarg);
    v11 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v27 + 64LL))(v27, &pvarg);
    if ( v11 >= 0 )
    {
      if ( pvarg.vt == 8 )
      {
        v30 = 0;
        v20 = StringToFileTime(pvarg.llVal, &v30, 0);
        v21 = v20;
        if ( v20 >= 0 )
        {
          SystemTimeAsFileTime = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          if ( (int)TimeDiff(&SystemTimeAsFileTime, &v30, v22) > 0 )
          {
            VariantClear(&pvarg);
            if ( v27 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
            *a3 = 1;
            v11 = 0;
            goto LABEL_62;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x26,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\XmlSchemaUtil.cpp",
            (const char *)(unsigned int)v20,
            v23);
          LODWORD(v24) = v21;
          WUTrace(0, 0, 4, 3, v24, L"Failed to convert dateTime to Filetime =>%ws<=");
        }
        v11 = 0;
        goto LABEL_51;
      }
      v11 = -2145103617;
      v19 = 1271;
    }
    else
    {
      v19 = 1270;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
      (const char *)(unsigned int)v11,
      v23);
LABEL_51:
    VariantClear(&pvarg);
LABEL_52:
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    goto LABEL_62;
  }
  v11 = CWUSLSParse::Init((CWUSLSParse *)&v26, v8, pcVal);
  if ( v11 >= 0 )
    goto LABEL_16;
  v12 = 1221;
LABEL_15:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
    (const char *)(unsigned int)v11,
    v23);
LABEL_66:
  CWUSLSParse::~CWUSLSParse((CWUSLSParse *)&v26);
  if ( pcVal )
    SusFree(pcVal);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14003dcf8  mov     [rsp-8+arg_18], rbx
0x14003dcfd  push    rbp
0x14003dcfe  push    rsi
0x14003dcff  push    rdi
0x14003dd00  push    r12
0x14003dd02  push    r13
0x14003dd04  push    r14
0x14003dd06  push    r15
0x14003dd08  lea     rbp, [rsp-1C0h]
0x14003dd10  sub     rsp, 2C0h
0x14003dd17  mov     rax, cs:__security_cookie
0x14003dd1e  xor     rax, rsp
0x14003dd21  mov     [rbp+1F0h+var_40], rax
0x14003dd28  mov     r15, r8
0x14003dd2b  mov     r14, rdx
0x14003dd2e  mov     esi, ecx
0x14003dd30  xor     r13d, r13d
0x14003dd33  test    r8, r8
0x14003dd36  jnz     short loc_14003DD5F
0x14003dd38  mov     rcx, [rbp+1F8h]; this
0x14003dd3f  mov     ebx, 80004003h
0x14003dd44  mov     r9d, ebx; char *
0x14003dd47  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003dd4e  mov     edx, 4A5h; void *
0x14003dd53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003dd58  mov     eax, ebx
0x14003dd5a  jmp     loc_14003E210
0x14003dd5f  mov     [r8], r13b
0x14003dd62  mov     rbx, r13
0x14003dd65  mov     [rsp+2F0h+var_2B0], rbx
0x14003dd6a  mov     edi, r13d
0x14003dd6d  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x14003dd72  test    eax, eax
0x14003dd74  jz      short loc_14003DDF4
0x14003dd76  mov     [rbp+1F0h+var_250], r13w
0x14003dd7b  xor     edx, edx; Val
0x14003dd7d  mov     r8d, 206h; Size
0x14003dd83  lea     rcx, [rbp+1F0h+var_24E]; void *
0x14003dd87  call    memset
0x14003dd8c  mov     dword ptr [rsp+2F0h+var_2D0], 104h; int
0x14003dd94  lea     r9, [rbp+1F0h+var_250]
0x14003dd98  lea     r8, ?c_szRegSLSCDNXML@@3QB_WB; "SLSCDNXML"
0x14003dd9f  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14003dda6  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEA_WKW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t *,ulong,RegistryHiveType)
0x14003ddab  test    eax, eax
0x14003ddad  js      short loc_14003DDF4
0x14003ddaf  lea     rax, ??_7?$CSafeBuffer@E@@6B@; const CSafeBuffer<uchar>::`vftable'
0x14003ddb6  mov     qword ptr [rsp+2F0h+pvarg], rax
0x14003ddbb  mov     qword ptr [rsp+2F0h+pvarg+8], r13
0x14003ddc0  mov     qword ptr [rsp+2F0h+pvarg+10h], r13
0x14003ddc5  lea     rdx, [rsp+2F0h+pvarg]
0x14003ddca  lea     rcx, [rbp+1F0h+var_250]
0x14003ddce  call    ?ReadFileToSafeByteBuffer@@YAJPEB_WPEAV?$CSafeBuffer@E@@@Z; ReadFileToSafeByteBuffer(wchar_t const *,CSafeBuffer<uchar> *)
0x14003ddd3  test    eax, eax
0x14003ddd5  js      short loc_14003DDEA
0x14003ddd7  mov     rbx, qword ptr [rsp+2F0h+pvarg+8]
0x14003dddc  mov     rcx, r13
0x14003dddf  mov     [rsp+2F0h+var_2B0], rbx
0x14003dde4  mov     edi, dword ptr [rsp+2F0h+pvarg+14h]
0x14003dde8  jmp     short loc_14003DDEF
0x14003ddea  mov     rcx, qword ptr [rsp+2F0h+pvarg+8]; lpMem
0x14003ddef  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14003ddf4  xorps   xmm1, xmm1
0x14003ddf7  movdqu  [rsp+2F0h+var_290], xmm1
0x14003ddfd  test    rbx, rbx
0x14003de00  setz    r12b
0x14003de04  test    rbx, rbx
0x14003de07  jz      short loc_14003DE29
0x14003de09  test    edi, edi
0x14003de0b  jz      short loc_14003DE29
0x14003de0d  mov     r8, rbx; char *
0x14003de10  mov     edx, edi; unsigned int
0x14003de12  lea     rcx, [rsp+2F0h+var_290]; this
0x14003de17  call    ?Init@CWUSLSParse@@QEAAJKPEBD@Z; CWUSLSParse::Init(ulong,char const *)
0x14003de1c  mov     edi, eax
0x14003de1e  test    eax, eax
0x14003de20  jns     short loc_14003DE5E
0x14003de22  mov     edx, 4C5h
0x14003de27  jmp     short loc_14003DE43
0x14003de29  mov     r8, r14; char *
0x14003de2c  mov     edx, esi; unsigned int
0x14003de2e  lea     rcx, [rsp+2F0h+var_290]; this
0x14003de33  call    ?Init@CWUSLSParse@@QEAAJKPEBD@Z; CWUSLSParse::Init(ulong,char const *)
0x14003de38  mov     edi, eax
0x14003de3a  test    eax, eax
0x14003de3c  jns     short loc_14003DE5E
0x14003de3e  mov     edx, 4C9h; void *
0x14003de43  mov     rcx, [rbp+1F8h]; this
0x14003de4a  mov     r9d, edi; char *
0x14003de4d  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003de54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003de59  jmp     loc_14003E1F6
0x14003de5e  mov     [rbp+1F0h+var_270], r13
0x14003de62  mov     rcx, qword ptr [rsp+2F0h+var_290]
0x14003de67  mov     rax, [rcx]
0x14003de6a  lea     r8, [rbp+1F0h+var_270]
0x14003de6e  lea     rdx, aServiceenviron_2; "/ServiceEnvironment"
0x14003de75  mov     rax, [rax+128h]
0x14003de7c  call    _guard_dispatch_icall
0x14003de81  mov     edi, eax
0x14003de83  cmp     eax, 1
0x14003de86  jnz     short loc_14003DE90
0x14003de88  mov     edi, r13d
0x14003de8b  jmp     loc_14003E1DD
0x14003de90  test    eax, eax
0x14003de92  jns     short loc_14003DEB4
0x14003de94  mov     rcx, [rbp+1F8h]; this
0x14003de9b  mov     r9d, eax; char *
0x14003de9e  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003dea5  mov     edx, 4D4h; void *
0x14003deaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003deaf  jmp     loc_14003E1DD
0x14003deb4  mov     [rsp+2F0h+var_278], r13
0x14003deb9  mov     rcx, [rbp+1F0h+var_270]
0x14003debd  mov     rax, [rcx]
0x14003dec0  lea     rdx, [rsp+2F0h+var_278]
0x14003dec5  mov     rax, [rax+88h]
0x14003decc  call    _guard_dispatch_icall
0x14003ded1  mov     edi, eax
0x14003ded3  test    eax, eax
0x14003ded5  jns     short loc_14003DEF7
0x14003ded7  mov     rcx, [rbp+1F8h]; this
0x14003dede  mov     r9d, eax; char *
0x14003dee1  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003dee8  mov     edx, 4D7h; void *
0x14003deed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003def2  jmp     loc_14003E1C2
0x14003def7  mov     [rsp+2F0h+var_280], r13
0x14003defc  mov     rcx, [rsp+2F0h+var_278]
0x14003df01  mov     rax, [rcx]
0x14003df04  lea     r8, [rsp+2F0h+var_280]
0x14003df09  lea     rdx, aCdn; "CDN"
0x14003df10  mov     rax, [rax+38h]
0x14003df14  call    _guard_dispatch_icall
0x14003df19  mov     edi, eax
0x14003df1b  cmp     eax, 1
0x14003df1e  jnz     short loc_14003DF28
0x14003df20  mov     edi, r13d
0x14003df23  jmp     loc_14003E1AB
0x14003df28  test    eax, eax
0x14003df2a  jns     short loc_14003DF4C
0x14003df2c  mov     rcx, [rbp+1F8h]; this
0x14003df33  mov     r9d, eax; char *
0x14003df36  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003df3d  mov     edx, 4E0h; void *
0x14003df42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003df47  jmp     loc_14003E1AB
0x14003df4c  lea     rcx, [rsp+2F0h+pvarg]; pvarg
0x14003df51  call    cs:__imp_VariantInit
0x14003df57  nop
0x14003df58  mov     rcx, [rsp+2F0h+var_280]
0x14003df5d  mov     rax, [rcx]
0x14003df60  lea     rdx, [rsp+2F0h+pvarg]
0x14003df65  mov     rax, [rax+40h]
0x14003df69  call    _guard_dispatch_icall
0x14003df6e  mov     edi, eax
0x14003df70  test    eax, eax
0x14003df72  jns     short loc_14003DF7B
0x14003df74  mov     edx, 4E3h
0x14003df79  jmp     short loc_14003DF91
0x14003df7b  mov     esi, 8
0x14003df80  cmp     si, word ptr [rsp+2F0h+pvarg]
0x14003df85  jz      short loc_14003DFAC
0x14003df87  mov     edi, 802450FFh
0x14003df8c  mov     edx, 4E4h; void *
0x14003df91  mov     rcx, [rbp+1F8h]; this
0x14003df98  mov     r9d, edi; char *
0x14003df9b  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003dfa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003dfa7  jmp     loc_14003E19F
0x14003dfac  mov     rcx, qword ptr [rsp+2F0h+pvarg+8]; pbstr
0x14003dfb1  call    cs:__imp_SysStringLen
0x14003dfb7  inc     eax
0x14003dfb9  mov     rdx, qword ptr [rsp+2F0h+pvarg+8]; wchar_t *
0x14003dfbe  test    rdx, rdx
0x14003dfc1  jz      loc_14003E19C
0x14003dfc7  cmp     eax, 1
0x14003dfca  jbe     loc_14003E19C
0x14003dfd0  cmp     eax, 2
0x14003dfd3  jnz     short loc_14003DFDB
0x14003dfd5  cmp     word ptr [rdx], 31h ; '1'
0x14003dfd9  jz      short loc_14003DFF3
0x14003dfdb  mov     r8d, eax; unsigned int
0x14003dfde  lea     rcx, aTrue; "true"
0x14003dfe5  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x14003dfea  cmp     eax, 2
0x14003dfed  jnz     loc_14003E19C
0x14003dff3  lea     rcx, [rsp+2F0h+pvarg]; pvarg
0x14003dff8  call    cs:__imp_VariantClear
0x14003dffe  nop
0x14003dfff  mov     rcx, [rsp+2F0h+var_280]
0x14003e004  test    rcx, rcx
0x14003e007  jz      short loc_14003E016
0x14003e009  mov     rax, [rcx]
0x14003e00c  mov     rax, [rax+10h]
0x14003e010  call    _guard_dispatch_icall
0x14003e015  nop
0x14003e016  mov     [rsp+2F0h+var_280], r13
0x14003e01b  mov     rcx, [rsp+2F0h+var_278]
0x14003e020  mov     rax, [rcx]
0x14003e023  lea     r8, [rsp+2F0h+var_280]
0x14003e028  lea     rdx, aExpiration; "Expiration"
0x14003e02f  mov     rax, [rax+38h]
0x14003e033  call    _guard_dispatch_icall
0x14003e038  mov     edi, eax
0x14003e03a  cmp     eax, 1
0x14003e03d  jnz     short loc_14003E047
0x14003e03f  mov     edi, r13d
0x14003e042  jmp     loc_14003E157
0x14003e047  test    eax, eax
0x14003e049  jns     short loc_14003E06B
0x14003e04b  mov     rcx, [rbp+1F8h]; this
0x14003e052  mov     r9d, eax; char *
0x14003e055  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003e05c  mov     edx, 4F3h; void *
0x14003e061  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e066  jmp     loc_14003E157
0x14003e06b  lea     rcx, [rsp+2F0h+pvarg]; pvarg
0x14003e070  call    cs:__imp_VariantInit
0x14003e076  nop
0x14003e077  mov     rcx, [rsp+2F0h+var_280]
0x14003e07c  mov     rax, [rcx]
0x14003e07f  lea     rdx, [rsp+2F0h+pvarg]
0x14003e084  mov     rax, [rax+40h]
0x14003e088  call    _guard_dispatch_icall
0x14003e08d  mov     edi, eax
0x14003e08f  test    eax, eax
0x14003e091  jns     short loc_14003E09A
0x14003e093  mov     edx, 4F6h
0x14003e098  jmp     short loc_14003E0AB
0x14003e09a  cmp     si, word ptr [rsp+2F0h+pvarg]
0x14003e09f  jz      short loc_14003E0C6
0x14003e0a1  mov     edi, 802450FFh
0x14003e0a6  mov     edx, 4F7h; void *
0x14003e0ab  mov     rcx, [rbp+1F8h]; this
0x14003e0b2  mov     r9d, edi; char *
0x14003e0b5  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003e0bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e0c1  jmp     loc_14003E14B
0x14003e0c6  mov     qword ptr [rbp+1F0h+var_268.dwLowDateTime], r13
0x14003e0ca  xor     r8d, r8d
0x14003e0cd  lea     rdx, [rbp+1F0h+var_268]
0x14003e0d1  mov     rcx, qword ptr [rsp+2F0h+pvarg+8]
0x14003e0d6  call    StringToFileTime
0x14003e0db  mov     edi, eax
0x14003e0dd  test    eax, eax
0x14003e0df  jns     short loc_14003E129
0x14003e0e1  mov     rcx, [rbp+1F8h]; this
0x14003e0e8  mov     r9d, eax; char *
0x14003e0eb  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003e0f2  mov     edx, 26h ; '&'; void *
0x14003e0f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e0fc  mov     rcx, qword ptr [rsp+2F0h+pvarg+8]
0x14003e101  mov     [rsp+2F0h+var_2C0], rcx
0x14003e106  lea     rax, aFailedToConver; "Failed to convert dateTime to Filetime "...
0x14003e10d  mov     [rsp+2F0h+var_2C8], rax
0x14003e112  mov     dword ptr [rsp+2F0h+var_2D0], edi
0x14003e116  xor     edx, edx
0x14003e118  xor     ecx, ecx
0x14003e11a  lea     r9d, [rdx+3]
0x14003e11e  lea     r8d, [rdx+4]
0x14003e122  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003e127  jmp     short loc_14003E148
0x14003e129  mov     qword ptr [rbp+1F0h+SystemTimeAsFileTime.dwLowDateTime], r13
0x14003e12d  lea     rcx, [rbp+1F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14003e131  call    cs:__imp_GetSystemTimeAsFileTime
0x14003e137  lea     rdx, [rbp+1F0h+var_268]; struct _FILETIME *
0x14003e13b  lea     rcx, [rbp+1F0h+SystemTimeAsFileTime]; struct _FILETIME *
0x14003e13f  call    ?TimeDiff@@YAHAEBU_FILETIME@@0H@Z; TimeDiff(_FILETIME const &,_FILETIME const &,int)
0x14003e144  test    eax, eax
0x14003e146  jg      short loc_14003E170
0x14003e148  mov     edi, r13d
0x14003e14b  lea     rcx, [rsp+2F0h+pvarg]; pvarg
0x14003e150  call    cs:__imp_VariantClear
0x14003e156  nop
0x14003e157  mov     rcx, [rsp+2F0h+var_280]
0x14003e15c  test    rcx, rcx
0x14003e15f  jz      short loc_14003E16E
0x14003e161  mov     rax, [rcx]
0x14003e164  mov     rax, [rax+10h]
0x14003e168  call    _guard_dispatch_icall
0x14003e16d  nop
0x14003e16e  jmp     short loc_14003E1C2
0x14003e170  lea     rcx, [rsp+2F0h+pvarg]; pvarg
0x14003e175  call    cs:__imp_VariantClear
0x14003e17b  nop
0x14003e17c  mov     rcx, [rsp+2F0h+var_280]
0x14003e181  test    rcx, rcx
0x14003e184  jz      short loc_14003E193
0x14003e186  mov     rax, [rcx]
0x14003e189  mov     rax, [rax+10h]
0x14003e18d  call    _guard_dispatch_icall
0x14003e192  nop
0x14003e193  mov     byte ptr [r15], 1
0x14003e197  mov     edi, r13d
0x14003e19a  jmp     short loc_14003E1C2
0x14003e19c  mov     edi, r13d
0x14003e19f  lea     rcx, [rsp+2F0h+pvarg]; pvarg
0x14003e1a4  call    cs:__imp_VariantClear
0x14003e1aa  nop
  ... truncated ...
```
