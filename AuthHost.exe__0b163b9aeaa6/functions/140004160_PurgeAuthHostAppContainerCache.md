# _PurgeAuthHostAppContainerCache

- ea: `0x140004160`
- end: `0x140004295`
- name: `_PurgeAuthHostAppContainerCache`
- size: `309`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003b70`
- `0x14000407c`

## callees

- `0x14000116c`
- `0x1400011e4`
- `0x140004160`
- `0x140012f22`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400041ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000421a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400041ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000421a`
- `WININET!GetUrlCacheConfigInfoW` at `0x1400041c4`
- `WININET!GetUrlCacheConfigInfoW` at `0x1400041c4`
- `WININET!FreeUrlCacheSpaceW` at `0x140004210`
- `WININET!FreeUrlCacheSpaceW` at `0x140004210`

## pseudocode

```c
__int64 __fastcall PurgeAuthHostAppContainerCache(int a1)
{
  unsigned int v1; // ebx
  __int64 v2; // rdi
  DWORD v4; // r8d
  signed int v5; // eax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  char *v9; // rdx
  signed int LastError; // eax
  DWORD dwFieldControl[4]; // [rsp+30h] [rbp-D0h]
  _INTERNET_CACHE_CONFIG_INFOW CacheConfigInfo; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+298h] [rbp+198h] BYREF
  unsigned int v15; // [rsp+2A0h] [rbp+1A0h] BYREF

  v1 = 0;
  dwFieldControl[0] = 256;
  v2 = 0;
  dwFieldControl[1] = 512;
  dwFieldControl[2] = 1024;
  do
  {
    memset_0(&CacheConfigInfo, 0, sizeof(CacheConfigInfo));
    v4 = dwFieldControl[v2];
    if ( (v4 & a1) == 0 )
      goto LABEL_16;
    CacheConfigInfo.dwStructSize = 560;
    if ( GetUrlCacheConfigInfoW(&CacheConfigInfo, 0, v4) )
    {
      if ( !FreeUrlCacheSpaceW(CacheConfigInfo.CachePath, 0x64u, 0) )
      {
        LastError = GetLastError();
        v1 = LastError;
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)dword_14001D000 > 5 && (unsigned __int8)tlgKeywordOn() )
        {
          v9 = byte_140018D19;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v5 = GetLastError();
      v1 = v5;
      if ( v5 > 0 )
        v1 = (unsigned __int16)v5 | 0x80070000;
      if ( (unsigned int)dword_14001D000 > 5 && (unsigned __int8)tlgKeywordOn() )
      {
        v9 = byte_140018D65;
LABEL_15:
        v14 = a1;
        v15 = v1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v6,
          (_DWORD)v9,
          v7,
          v8,
          (__int64)&v15,
          (__int64)&v14);
      }
    }
LABEL_16:
    ++v2;
  }
  while ( v2 != 3 );
  return v1;
}

```

## disassembly

```asm
0x140004160  mov     [rsp-8+arg_0], rbx
0x140004165  push    rbp
0x140004166  push    rsi
0x140004167  push    rdi
0x140004168  lea     rbp, [rsp-170h]
0x140004170  sub     rsp, 270h
0x140004177  xor     ebx, ebx
0x140004179  mov     [rsp+280h+dwFieldControl], 100h
0x140004181  xor     edi, edi
0x140004183  mov     [rsp+280h+var_24C], 200h
0x14000418b  mov     esi, ecx
0x14000418d  mov     [rsp+280h+var_248], 400h
0x140004195  xor     edx, edx; Val
0x140004197  lea     rcx, [rsp+280h+CacheConfigInfo]; void *
0x14000419c  mov     r8d, 230h; Size
0x1400041a2  call    memset_0
0x1400041a7  mov     r8d, [rsp+rdi*4+280h+dwFieldControl]; dwFieldControl
0x1400041ac  test    esi, r8d
0x1400041af  jz      loc_140004273
0x1400041b5  xor     edx, edx; lpcbCacheConfigInfo
0x1400041b7  mov     [rsp+280h+CacheConfigInfo.dwStructSize], 230h
0x1400041bf  lea     rcx, [rsp+280h+CacheConfigInfo]; lpCacheConfigInfo
0x1400041c4  call    cs:__imp_GetUrlCacheConfigInfoW
0x1400041ca  test    eax, eax
0x1400041cc  jnz     short loc_140004204
0x1400041ce  call    cs:__imp_GetLastError
0x1400041d4  mov     ebx, eax
0x1400041d6  test    eax, eax
0x1400041d8  jle     short loc_1400041E3
0x1400041da  movzx   ebx, ax
0x1400041dd  or      ebx, 80070000h
0x1400041e3  mov     eax, cs:dword_14001D000
0x1400041e9  cmp     eax, 5
0x1400041ec  jbe     loc_140004273
0x1400041f2  call    _tlgKeywordOn
0x1400041f7  test    al, al
0x1400041f9  jz      short loc_140004273
0x1400041fb  lea     rdx, byte_140018D65
0x140004202  jmp     short loc_14000424A
0x140004204  xor     r8d, r8d; dwFilter
0x140004207  lea     rcx, [rsp+280h+CacheConfigInfo.1Ch]; lpszCachePath
0x14000420c  lea     edx, [r8+64h]; dwSize
0x140004210  call    cs:__imp_FreeUrlCacheSpaceW
0x140004216  test    eax, eax
0x140004218  jnz     short loc_140004273
0x14000421a  call    cs:__imp_GetLastError
0x140004220  mov     ebx, eax
0x140004222  test    eax, eax
0x140004224  jle     short loc_14000422F
0x140004226  movzx   ebx, ax
0x140004229  or      ebx, 80070000h
0x14000422f  mov     eax, cs:dword_14001D000
0x140004235  cmp     eax, 5
0x140004238  jbe     short loc_140004273
0x14000423a  call    _tlgKeywordOn
0x14000423f  test    al, al
0x140004241  jz      short loc_140004273
0x140004243  lea     rdx, byte_140018D19
0x14000424a  lea     rax, [rbp+180h+arg_8]
0x140004251  mov     [rsp+280h+var_258], rax
0x140004256  lea     rax, [rbp+180h+arg_10]
0x14000425d  mov     [rsp+280h+var_260], rax
0x140004262  mov     [rbp+180h+arg_8], esi
0x140004268  mov     [rbp+180h+arg_10], ebx
0x14000426e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140004273  inc     rdi
0x140004276  cmp     rdi, 3
0x14000427a  jnz     loc_140004195
0x140004280  mov     eax, ebx
0x140004282  mov     rbx, [rsp+280h+arg_0]
0x14000428a  add     rsp, 270h
0x140004291  pop     rdi
0x140004292  pop     rsi
0x140004293  pop     rbp
0x140004294  retn
```
