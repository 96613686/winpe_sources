# BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated(void)

- ea: `0x180086568`
- end: `0x18008666b`
- name: `?IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ`
- size: `259`
- prototype: `bool __fastcall(BrowserReplacementVariant::Private *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180086674`

## callees

- `0x180044408`
- `0x180086568`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180086587`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180086587`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800865da`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800865da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008665e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008665e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008664e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008664e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180086615`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180086615`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800865bf`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800865bf`

## string_xrefs

- `0x180086624`: `PackagedReplacementEnabled`

## pseudocode

```c
bool __fastcall BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated(
        BrowserReplacementVariant::Private *this)
{
  const char *v1; // r9
  bool v3; // bl
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  WINBOOL fPending; // [rsp+50h] [rbp+8h] BYREF
  HKEY hkey; // [rsp+58h] [rbp+10h] BYREF

  fPending = 0;
  if ( __std_init_once_begin_initialize(
         &`BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated'::`2'::s_checkIfOneCoreOnce,
         0,
         &fPending,
         0) )
  {
    if ( fPending )
    {
      `BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated'::`2'::s_isOneCore = GetSystemMetrics(6144) == 0;
      InitOnceComplete(
        &`BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated'::`2'::s_checkIfOneCoreOnce,
        0,
        0);
    }
  }
  else if ( (int)wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v1) < 0 )
  {
    return 0;
  }
  if ( !`BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated'::`2'::s_isOneCore )
    return 0;
  hkey = 0;
  v3 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MicrosoftEdge",
          0,
          0x20019u,
          &hkey) )
  {
    v3 = RegGetValueW(hkey, 0, L"PackagedReplacementEnabled", 0xFFFFu, 0, 0, 0) == 0;
    RegCloseKey(hkey);
  }
  return v3;
}

```

## disassembly

```asm
0x180086568  push    rbx
0x18008656a  sub     rsp, 40h
0x18008656e  xor     r9d, r9d; lpContext
0x180086571  mov     [rsp+48h+fPending], 0
0x180086579  lea     r8, [rsp+48h+fPending]; fPending
0x18008657e  xor     edx, edx; dwFlags
0x180086580  lea     rcx, ?s_checkIfOneCoreOnce@?1??IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ@4T_RTL_RUN_ONCE@@A; lpInitOnce
0x180086587  call    cs:__imp___std_init_once_begin_initialize
0x18008658d  test    eax, eax
0x18008658f  jnz     short loc_1800865B3
0x180086591  mov     rcx, [rsp+48h]; this
0x180086596  lea     r8, aWil; "wil"
0x18008659d  mov     edx, 37Ah; void *
0x1800865a2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800865a7  test    eax, eax
0x1800865a9  jns     short loc_1800865E0
0x1800865ab  xor     al, al
0x1800865ad  add     rsp, 40h
0x1800865b1  pop     rbx
0x1800865b2  retn
0x1800865b3  cmp     [rsp+48h+fPending], 0
0x1800865b8  jz      short loc_1800865E0
0x1800865ba  mov     ecx, 1800h; nIndex
0x1800865bf  call    cs:__imp_GetSystemMetrics
0x1800865c5  test    eax, eax
0x1800865c7  lea     rcx, ?s_checkIfOneCoreOnce@?1??IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ@4T_RTL_RUN_ONCE@@A; lpInitOnce
0x1800865ce  setz    cs:?s_isOneCore@?1??IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ@4_NA; bool `BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated(void)'::`2'::s_isOneCore
0x1800865d5  xor     r8d, r8d; lpContext
0x1800865d8  xor     edx, edx; dwFlags
0x1800865da  call    cs:__imp_InitOnceComplete
0x1800865e0  cmp     cs:?s_isOneCore@?1??IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ@4_NA, 0; bool `BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated(void)'::`2'::s_isOneCore
0x1800865e7  jz      short loc_1800865AB
0x1800865e9  lea     rax, [rsp+48h+hkey]
0x1800865ee  mov     [rsp+48h+hkey], 0
0x1800865f7  mov     r9d, 20019h; samDesired
0x1800865fd  mov     [rsp+48h+phkResult], rax; phkResult
0x180086602  xor     r8d, r8d; ulOptions
0x180086605  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18008660c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180086613  xor     bl, bl
0x180086615  call    cs:__imp_RegOpenKeyExW
0x18008661b  test    eax, eax
0x18008661d  jnz     short loc_180086664
0x18008661f  mov     rcx, [rsp+48h+hkey]; hkey
0x180086624  lea     r8, aPackagedreplac; "PackagedReplacementEnabled"
0x18008662b  mov     [rsp+48h+pcbData], 0; pcbData
0x180086634  mov     r9d, 0FFFFh; dwFlags
0x18008663a  mov     [rsp+48h+pvData], 0; pvData
0x180086643  xor     edx, edx; lpSubKey
0x180086645  mov     [rsp+48h+phkResult], 0; pdwType
0x18008664e  call    cs:__imp_RegGetValueW
0x180086654  mov     rcx, [rsp+48h+hkey]; hKey
0x180086659  test    eax, eax
0x18008665b  setz    bl
0x18008665e  call    cs:__imp_RegCloseKey
0x180086664  mov     al, bl
0x180086666  jmp     loc_1800865AD
```
