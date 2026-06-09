# BCryptUnregisterConfigChangeNotify

- ea: `0x180019920`
- end: `0x1800199ef`
- name: `BCryptUnregisterConfigChangeNotify`
- size: `207`
- prototype: `NTSTATUS __stdcall(HANDLE hEvent)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800010ac`
- `0x180010ed4`
- `0x180019920`
- `0x180019b1c`
- `0x18001b7a9`
- `0x18001b7e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180019958`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180019958`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180019973`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180019973`

## pseudocode

```c
NTSTATUS __stdcall BCryptUnregisterConfigChangeNotify(HANDLE hEvent)
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
      (unsigned int)word_18001F982,
      v6,
      v7,
      (__int64)&v10);
  }
  return BcpUnregisterConfigChangeNotifyNoLogging(hEvent);
}

```

## disassembly

```asm
0x180019920  push    rbx
0x180019922  sub     rsp, 260h
0x180019929  mov     rax, cs:__security_cookie
0x180019930  xor     rax, rsp
0x180019933  mov     [rsp+268h+var_18], rax
0x18001993b  mov     rbx, rcx
0x18001993e  xor     edx, edx; Val
0x180019940  lea     rcx, [rsp+268h+ExeName]; void *
0x180019945  mov     r8d, 20Ah; Size
0x18001994b  call    memset_0
0x180019950  mov     [rsp+268h+dwSize], 105h
0x180019958  call    cs:__imp_GetCurrentProcess
0x18001995f  nop     dword ptr [rax+rax+00h]
0x180019964  lea     r9, [rsp+268h+dwSize]; lpdwSize
0x180019969  xor     edx, edx; dwFlags
0x18001996b  mov     rcx, rax; hProcess
0x18001996e  lea     r8, [rsp+268h+ExeName]; lpExeName
0x180019973  call    cs:__imp_QueryFullProcessImageNameW
0x18001997a  nop     dword ptr [rax+rax+00h]
0x18001997f  test    eax, eax
0x180019981  jnz     short loc_180019988
0x180019983  mov     [rsp+268h+ExeName], ax
0x180019988  mov     eax, cs:dword_180024050
0x18001998e  cmp     eax, 5
0x180019991  jbe     short loc_1800199CD
0x180019993  mov     rdx, 200000000000h
0x18001999d  lea     rcx, dword_180024050
0x1800199a4  call    _tlgKeywordOn
0x1800199a9  test    al, al
0x1800199ab  jz      short loc_1800199CD
0x1800199ad  lea     rax, [rsp+268h+ExeName]
0x1800199b2  mov     [rsp+268h+var_230], rax
0x1800199b7  lea     rdx, word_18001F982
0x1800199be  lea     rax, [rsp+268h+var_230]
0x1800199c3  mov     [rsp+268h+var_248], rax
0x1800199c8  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800199cd  mov     rcx, rbx; void *
0x1800199d0  call    BcpUnregisterConfigChangeNotifyNoLogging
0x1800199d5  mov     rcx, [rsp+268h+var_18]
0x1800199dd  xor     rcx, rsp; StackCookie
0x1800199e0  call    __security_check_cookie
0x1800199e5  add     rsp, 260h
0x1800199ec  pop     rbx
0x1800199ed  retn
```
