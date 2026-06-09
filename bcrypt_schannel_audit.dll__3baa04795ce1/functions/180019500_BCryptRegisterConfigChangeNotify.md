# BCryptRegisterConfigChangeNotify

- ea: `0x180019500`
- end: `0x1800195cf`
- name: `BCryptRegisterConfigChangeNotify`
- size: `207`
- prototype: `NTSTATUS __stdcall(HANDLE *phEvent)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800010ac`
- `0x18000997c`
- `0x180010ed4`
- `0x180019500`
- `0x18001b7a9`
- `0x18001b7e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180019538`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180019538`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180019553`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180019553`

## pseudocode

```c
NTSTATUS __stdcall BCryptRegisterConfigChangeNotify(HANDLE *phEvent)
{
  HANDLE CurrentProcess; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  DWORD dwSize; // [rsp+30h] [rbp-238h] BYREF
  WCHAR *v10; // [rsp+38h] [rbp-230h] BYREF
  WCHAR ExeName[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(ExeName, 0, 0x20Au);
  dwSize = 261;
  CurrentProcess = GetCurrentProcess();
  if ( !QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize) )
    ExeName[0] = 0;
  if ( (unsigned int)dword_180024050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180024050, 0x200000000000LL, v3, v4) )
  {
    v10 = ExeName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v5,
      (unsigned int)&unk_18001F940,
      v6,
      v7,
      (__int64)&v10);
  }
  return BcpRegisterConfigChangeNotifyNoLogging(phEvent);
}

```

## disassembly

```asm
0x180019500  push    rbx
0x180019502  sub     rsp, 260h
0x180019509  mov     rax, cs:__security_cookie
0x180019510  xor     rax, rsp
0x180019513  mov     [rsp+268h+var_18], rax
0x18001951b  mov     rbx, rcx
0x18001951e  xor     edx, edx; Val
0x180019520  lea     rcx, [rsp+268h+ExeName]; void *
0x180019525  mov     r8d, 20Ah; Size
0x18001952b  call    memset_0
0x180019530  mov     [rsp+268h+dwSize], 105h
0x180019538  call    cs:__imp_GetCurrentProcess
0x18001953f  nop     dword ptr [rax+rax+00h]
0x180019544  lea     r9, [rsp+268h+dwSize]; lpdwSize
0x180019549  xor     edx, edx; dwFlags
0x18001954b  mov     rcx, rax; hProcess
0x18001954e  lea     r8, [rsp+268h+ExeName]; lpExeName
0x180019553  call    cs:__imp_QueryFullProcessImageNameW
0x18001955a  nop     dword ptr [rax+rax+00h]
0x18001955f  test    eax, eax
0x180019561  jnz     short loc_180019568
0x180019563  mov     [rsp+268h+ExeName], ax
0x180019568  mov     eax, cs:dword_180024050
0x18001956e  cmp     eax, 5
0x180019571  jbe     short loc_1800195AD
0x180019573  mov     rdx, 200000000000h
0x18001957d  lea     rcx, dword_180024050
0x180019584  call    _tlgKeywordOn
0x180019589  test    al, al
0x18001958b  jz      short loc_1800195AD
0x18001958d  lea     rax, [rsp+268h+ExeName]
0x180019592  mov     [rsp+268h+var_230], rax
0x180019597  lea     rdx, unk_18001F940
0x18001959e  lea     rax, [rsp+268h+var_230]
0x1800195a3  mov     [rsp+268h+var_248], rax
0x1800195a8  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800195ad  mov     rcx, rbx
0x1800195b0  call    BcpRegisterConfigChangeNotifyNoLogging
0x1800195b5  mov     rcx, [rsp+268h+var_18]
0x1800195bd  xor     rcx, rsp; StackCookie
0x1800195c0  call    __security_check_cookie
0x1800195c5  add     rsp, 260h
0x1800195cc  pop     rbx
0x1800195cd  retn
```
