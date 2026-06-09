# IsServiceInSafeModeList(ushort const *,ESystemStartMode,int *)

- ea: `0x140008510`
- end: `0x14000870a`
- name: `?IsServiceInSafeModeList@@YAJPEBGW4ESystemStartMode@@PEAH@Z`
- size: `506`
- prototype: `__int64 __fastcall(__int64, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400068bc`

## callees

- `0x140002c08`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x140008510`
- `0x14000ae32`
- `0x14000ae60`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140008628`
- `ADVAPI32!RegOpenKeyExW` at `0x140008628`
- `ADVAPI32!RegCloseKey` at `0x1400086d9`
- `ADVAPI32!RegCloseKey` at `0x1400086d9`
- `KERNEL32!IsDebuggerPresent` at `0x1400085c9`
- `KERNEL32!IsDebuggerPresent` at `0x140008682`
- `KERNEL32!IsDebuggerPresent` at `0x1400085c9`
- `KERNEL32!IsDebuggerPresent` at `0x140008682`

## string_xrefs

- `0x1400085a6`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14000865f`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14000859c`: `IsServiceInSafeModeList`
- `0x140008655`: `IsServiceInSafeModeList`

## pseudocode

```c
__int64 __fastcall IsServiceInSafeModeList(__int64 a1, unsigned int a2, _DWORD *a3)
{
  const unsigned __int16 *v5; // r8
  int v6; // eax
  const unsigned __int16 *v7; // r15
  const unsigned __int16 *v8; // r14
  __int64 v9; // r9
  __int64 v10; // r8
  LSTATUS v11; // eax
  unsigned int v13; // [rsp+30h] [rbp-258h]
  unsigned int v14; // [rsp+38h] [rbp-250h]
  HKEY hKey; // [rsp+40h] [rbp-248h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-238h] BYREF

  memset_0(SubKey, 0, 0x208u);
  hKey = 0;
  if ( !a2 )
    return a2;
  v5 = L"SYSTEM\\CurrentControlSet\\Control\\Safeboot\\Minimal\\{0}";
  if ( a2 != 1 )
    v5 = L"SYSTEM\\CurrentControlSet\\Control\\Safeboot\\Network\\{0}";
  v6 = StringCchPrintfW(SubKey, 0x104u, v5, L"Wms");
  a2 = v6;
  if ( v6 < 0 )
  {
    v7 = L"CHRA";
    v8 = L"hr";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0xB23u,
      L"IsServiceInSafeModeList",
      L"CHRA",
      L"hr",
      v6);
    if ( IsDebuggerPresent() )
    {
      v9 = 2851;
LABEL_15:
      v14 = a2;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v9,
        L"IsServiceInSafeModeList",
        v7,
        v8,
        v14);
      goto LABEL_18;
    }
    v10 = 2851;
    goto LABEL_8;
  }
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
  if ( (v11 & 0xFFFFFFFD) != 0 )
  {
    if ( v11 > 0 )
      a2 = (unsigned __int16)v11 | 0x80070000;
    else
      a2 = v11;
    v7 = L"CBRAEx";
    v8 = L"(lr == 0L) || (lr == 2L)";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0xB26u,
      L"IsServiceInSafeModeList",
      L"CBRAEx",
      L"(lr == 0L) || (lr == 2L)",
      a2);
    if ( IsDebuggerPresent() )
    {
      v9 = 2854;
      goto LABEL_15;
    }
    v10 = 2854;
LABEL_8:
    v13 = a2;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v10,
      L"IsServiceInSafeModeList",
      v7,
      v8,
      v13);
    goto LABEL_18;
  }
  *a3 = v11 == 0;
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  return a2;
}

```

## disassembly

```asm
0x140008510  mov     [rsp+arg_0], rbx
0x140008515  mov     [rsp+arg_8], rsi
0x14000851a  push    rdi
0x14000851b  push    r14
0x14000851d  push    r15
0x14000851f  sub     rsp, 270h
0x140008526  mov     rax, cs:__security_cookie
0x14000852d  xor     rax, rsp
0x140008530  mov     [rsp+288h+var_28], rax
0x140008538  mov     rdi, r8
0x14000853b  lea     rcx, [rsp+288h+SubKey]; void *
0x140008540  mov     ebx, edx
0x140008542  mov     r8d, 208h; Size
0x140008548  xor     edx, edx; Val
0x14000854a  call    memset_0
0x14000854f  mov     [rsp+288h+hKey], 0
0x140008558  test    ebx, ebx
0x14000855a  jz      loc_1400086DF
0x140008560  lea     rax, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Saf"...
0x140008567  cmp     ebx, 1
0x14000856a  lea     r8, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\Saf"...
0x140008571  mov     edx, 104h; unsigned __int64
0x140008576  cmovnz  r8, rax; unsigned __int16 *
0x14000857a  lea     r9, ServiceName; "Wms"
0x140008581  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x140008586  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000858b  mov     ebx, eax
0x14000858d  test    eax, eax
0x14000858f  jns     short loc_140008609
0x140008591  mov     [rsp+288h+var_260], eax; int
0x140008595  lea     r15, aChra; "CHRA"
0x14000859c  lea     rsi, aIsserviceinsaf; "IsServiceInSafeModeList"
0x1400085a3  mov     r9, r15; unsigned __int16 *
0x1400085a6  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400085ad  mov     r8, rsi; unsigned __int16 *
0x1400085b0  lea     r14, aHr; "hr"
0x1400085b7  mov     rcx, rdi; unsigned __int16 *
0x1400085ba  mov     edx, 0B23h; unsigned int
0x1400085bf  mov     [rsp+288h+phkResult], r14; unsigned __int16 *
0x1400085c4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400085c9  call    cs:__imp_IsDebuggerPresent
0x1400085cf  test    eax, eax
0x1400085d1  jz      short loc_1400085DE
0x1400085d3  mov     r9d, 0B23h
0x1400085d9  jmp     loc_140008692
0x1400085de  mov     r8d, 0B23h
0x1400085e4  mov     dword ptr [rsp+288h+var_258], ebx
0x1400085e8  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400085ef  mov     qword ptr [rsp+288h+var_260], r14
0x1400085f4  mov     r9, rsi
0x1400085f7  mov     rdx, rdi
0x1400085fa  mov     [rsp+288h+phkResult], r15
0x1400085ff  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140008604  jmp     loc_1400086CF
0x140008609  lea     rax, [rsp+288h+hKey]
0x14000860e  mov     r9d, 1; samDesired
0x140008614  xor     r8d, r8d; ulOptions
0x140008617  mov     [rsp+288h+phkResult], rax; phkResult
0x14000861c  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x140008621  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140008628  call    cs:__imp_RegOpenKeyExW
0x14000862e  test    eax, 0FFFFFFFDh
0x140008633  jz      loc_1400086C6
0x140008639  test    eax, eax
0x14000863b  jg      short loc_140008641
0x14000863d  mov     ebx, eax
0x14000863f  jmp     short loc_14000864A
0x140008641  movzx   ebx, ax
0x140008644  or      ebx, 80070000h
0x14000864a  lea     r15, aCbraex; "CBRAEx"
0x140008651  mov     [rsp+288h+var_260], ebx; int
0x140008655  lea     rsi, aIsserviceinsaf; "IsServiceInSafeModeList"
0x14000865c  mov     r9, r15; unsigned __int16 *
0x14000865f  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140008666  mov     r8, rsi; unsigned __int16 *
0x140008669  lea     r14, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x140008670  mov     rcx, rdi; unsigned __int16 *
0x140008673  mov     edx, 0B26h; unsigned int
0x140008678  mov     [rsp+288h+phkResult], r14; unsigned __int16 *
0x14000867d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140008682  call    cs:__imp_IsDebuggerPresent
0x140008688  test    eax, eax
0x14000868a  jz      short loc_1400086BB
0x14000868c  mov     r9d, 0B26h
0x140008692  mov     [rsp+288h+var_250], ebx
0x140008696  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000869d  mov     [rsp+288h+var_258], r14
0x1400086a2  mov     r8, rdi
0x1400086a5  mov     qword ptr [rsp+288h+var_260], r15
0x1400086aa  mov     ecx, 2; unsigned __int8
0x1400086af  mov     [rsp+288h+phkResult], rsi
0x1400086b4  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400086b9  jmp     short loc_1400086CF
0x1400086bb  mov     r8d, 0B26h
0x1400086c1  jmp     loc_1400085E4
0x1400086c6  xor     ecx, ecx
0x1400086c8  test    eax, eax
0x1400086ca  setz    cl
0x1400086cd  mov     [rdi], ecx
0x1400086cf  mov     rcx, [rsp+288h+hKey]; hKey
0x1400086d4  test    rcx, rcx
0x1400086d7  jz      short loc_1400086DF
0x1400086d9  call    cs:__imp_RegCloseKey
0x1400086df  mov     eax, ebx
0x1400086e1  mov     rcx, [rsp+288h+var_28]
0x1400086e9  xor     rcx, rsp; StackCookie
0x1400086ec  call    __security_check_cookie
0x1400086f1  lea     r11, [rsp+288h+var_18]
0x1400086f9  mov     rbx, [r11+20h]
0x1400086fd  mov     rsi, [r11+28h]
0x140008701  mov     rsp, r11
0x140008704  pop     r15
0x140008706  pop     r14
0x140008708  pop     rdi
0x140008709  retn
```
