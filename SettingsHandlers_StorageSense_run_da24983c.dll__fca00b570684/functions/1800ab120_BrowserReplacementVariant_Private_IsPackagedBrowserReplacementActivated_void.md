# BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated(void)

- ea: `0x1800ab120`
- end: `0x1800ab223`
- name: `?IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ`
- size: `259`
- prototype: `bool __fastcall(BrowserReplacementVariant::Private *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ab22c`

## callees

- `0x18000e6ac`
- `0x1800ab120`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800ab192`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800ab192`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800ab13f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800ab13f`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800ab177`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800ab177`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab1cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab1cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ab206`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ab206`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab216`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab216`

## string_xrefs

- `0x1800ab1dc`: `PackagedReplacementEnabled`

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
  if ( InitOnceBeginInitialize(
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
0x1800ab120  push    rbx
0x1800ab122  sub     rsp, 40h
0x1800ab126  xor     r9d, r9d; lpContext
0x1800ab129  mov     [rsp+48h+fPending], 0
0x1800ab131  lea     r8, [rsp+48h+fPending]; fPending
0x1800ab136  xor     edx, edx; dwFlags
0x1800ab138  lea     rcx, ?s_checkIfOneCoreOnce@?1??IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ@4T_RTL_RUN_ONCE@@A; lpInitOnce
0x1800ab13f  call    cs:__imp_InitOnceBeginInitialize
0x1800ab145  test    eax, eax
0x1800ab147  jnz     short loc_1800AB16B
0x1800ab149  mov     rcx, [rsp+48h]; this
0x1800ab14e  lea     r8, aWil; "wil"
0x1800ab155  mov     edx, 37Ah; void *
0x1800ab15a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ab15f  test    eax, eax
0x1800ab161  jns     short loc_1800AB198
0x1800ab163  xor     al, al
0x1800ab165  add     rsp, 40h
0x1800ab169  pop     rbx
0x1800ab16a  retn
0x1800ab16b  cmp     [rsp+48h+fPending], 0
0x1800ab170  jz      short loc_1800AB198
0x1800ab172  mov     ecx, 1800h; nIndex
0x1800ab177  call    cs:__imp_GetSystemMetrics
0x1800ab17d  test    eax, eax
0x1800ab17f  lea     rcx, ?s_checkIfOneCoreOnce@?1??IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ@4T_RTL_RUN_ONCE@@A; lpInitOnce
0x1800ab186  setz    cs:?s_isOneCore@?1??IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ@4_NA; bool `BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated(void)'::`2'::s_isOneCore
0x1800ab18d  xor     r8d, r8d; lpContext
0x1800ab190  xor     edx, edx; dwFlags
0x1800ab192  call    cs:__imp_InitOnceComplete
0x1800ab198  cmp     cs:?s_isOneCore@?1??IsPackagedBrowserReplacementActivated@Private@BrowserReplacementVariant@@YA_NXZ@4_NA, 0; bool `BrowserReplacementVariant::Private::IsPackagedBrowserReplacementActivated(void)'::`2'::s_isOneCore
0x1800ab19f  jz      short loc_1800AB163
0x1800ab1a1  lea     rax, [rsp+48h+hkey]
0x1800ab1a6  mov     [rsp+48h+hkey], 0
0x1800ab1af  mov     r9d, 20019h; samDesired
0x1800ab1b5  mov     [rsp+48h+phkResult], rax; phkResult
0x1800ab1ba  xor     r8d, r8d; ulOptions
0x1800ab1bd  lea     rdx, aSoftwareMicros_24; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800ab1c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ab1cb  xor     bl, bl
0x1800ab1cd  call    cs:__imp_RegOpenKeyExW
0x1800ab1d3  test    eax, eax
0x1800ab1d5  jnz     short loc_1800AB21C
0x1800ab1d7  mov     rcx, [rsp+48h+hkey]; hkey
0x1800ab1dc  lea     r8, aPackagedreplac; "PackagedReplacementEnabled"
0x1800ab1e3  mov     [rsp+48h+pcbData], 0; pcbData
0x1800ab1ec  mov     r9d, 0FFFFh; dwFlags
0x1800ab1f2  mov     [rsp+48h+pvData], 0; pvData
0x1800ab1fb  xor     edx, edx; lpSubKey
0x1800ab1fd  mov     [rsp+48h+phkResult], 0; pdwType
0x1800ab206  call    cs:__imp_RegGetValueW
0x1800ab20c  mov     rcx, [rsp+48h+hkey]; hKey
0x1800ab211  test    eax, eax
0x1800ab213  setz    bl
0x1800ab216  call    cs:__imp_RegCloseKey
0x1800ab21c  mov     al, bl
0x1800ab21e  jmp     loc_1800AB165
```
