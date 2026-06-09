# I_ServerCacheWriteDataToDisk(void)

- ea: `0x18002b214`
- end: `0x18002b35d`
- name: `?I_ServerCacheWriteDataToDisk@@YAKXZ`
- size: `329`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024710`

## callees

- `0x1800075d0`
- `0x180014dc0`
- `0x180028b78`
- `0x18002ab90`
- `0x18002b214`
- `0x180030eb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b2b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b2b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b2e7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b2e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b2f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b2f9`

## string_xrefs

- `0x18002b2a8`: `Software\Microsoft\Cryptography\Calais\Cache`
- `0x18002b2cf`: `Cache`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall I_ServerCacheWriteDataToDisk(__int64 a1)
{
  unsigned int v1; // ebx
  BYTE *v2; // rcx
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  lpData = 0;
  cbData = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_647da024c2503459d7fafff2f0112b72_Traceguids, WPP_pszIndent);
  }
  v1 = ScCacheSerializeCache(g_pCacheHandle, 0, &lpData, &cbData);
  if ( !v1 )
  {
    v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Cryptography\\Calais\\Cache", 0, 2u, &hKey);
    if ( !v1 )
      v1 = RegSetValueExW(hKey, L"Cache", 0, 3u, lpData, cbData);
  }
  if ( hKey )
    RegCloseKey(hKey);
  v2 = lpData;
  if ( lpData )
    ConstStringHeapFree((const unsigned __int16 *)lpData);
  WppTraceIndent(v2, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)&WPP_647da024c2503459d7fafff2f0112b72_Traceguids,
      (_DWORD)WPP_pszIndent,
      v1);
  }
  return v1;
}

```

## disassembly

```asm
0x18002b214  mov     rax, rsp
0x18002b217  mov     [rax+20h], rbx
0x18002b21b  push    rsi
0x18002b21c  sub     rsp, 30h
0x18002b220  xor     edx, edx
0x18002b222  mov     qword ptr [rax+10h], 0
0x18002b22a  mov     qword ptr [rax+18h], 0
0x18002b232  mov     dword ptr [rax+8], 0
0x18002b239  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b23e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b245  lea     rsi, WPP_GLOBAL_Control
0x18002b24c  cmp     rcx, rsi
0x18002b24f  jz      short loc_18002B279
0x18002b251  test    byte ptr [rcx+1Ch], 2
0x18002b255  jz      short loc_18002B279
0x18002b257  cmp     byte ptr [rcx+19h], 5
0x18002b25b  jb      short loc_18002B279
0x18002b25d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002b264  lea     r8, WPP_647da024c2503459d7fafff2f0112b72_Traceguids
0x18002b26b  mov     rcx, [rcx+10h]
0x18002b26f  mov     edx, 0Ah
0x18002b274  call    WPP_SF_s
0x18002b279  mov     rcx, cs:?g_pCacheHandle@@3_KA; unsigned __int64 g_pCacheHandle
0x18002b280  lea     r9, [rsp+38h+arg_0]
0x18002b285  lea     r8, [rsp+38h+lpData]
0x18002b28a  xor     edx, edx
0x18002b28c  call    ScCacheSerializeCache
0x18002b291  mov     ebx, eax
0x18002b293  test    eax, eax
0x18002b295  jnz     short loc_18002B2EF
0x18002b297  lea     rax, [rsp+38h+hKey]
0x18002b29c  xor     r8d, r8d; ulOptions
0x18002b29f  lea     r9d, [rbx+2]; samDesired
0x18002b2a3  mov     [rsp+38h+phkResult], rax; phkResult
0x18002b2a8  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Cryptography\\Cala"...
0x18002b2af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b2b6  call    cs:__imp_RegOpenKeyExW
0x18002b2bc  mov     ebx, eax
0x18002b2be  test    eax, eax
0x18002b2c0  jnz     short loc_18002B2EF
0x18002b2c2  mov     eax, [rsp+38h+arg_0]
0x18002b2c6  lea     r9d, [rbx+3]; dwType
0x18002b2ca  mov     rcx, [rsp+38h+hKey]; hKey
0x18002b2cf  lea     rdx, aCache; "Cache"
0x18002b2d6  mov     [rsp+38h+cbData], eax; cbData
0x18002b2da  xor     r8d, r8d; Reserved
0x18002b2dd  mov     rax, [rsp+38h+lpData]
0x18002b2e2  mov     [rsp+38h+phkResult], rax; lpData
0x18002b2e7  call    cs:__imp_RegSetValueExW
0x18002b2ed  mov     ebx, eax
0x18002b2ef  mov     rcx, [rsp+38h+hKey]; hKey
0x18002b2f4  test    rcx, rcx
0x18002b2f7  jz      short loc_18002B2FF
0x18002b2f9  call    cs:__imp_RegCloseKey
0x18002b2ff  mov     rcx, [rsp+38h+lpData]; unsigned __int16 *
0x18002b304  test    rcx, rcx
0x18002b307  jz      short loc_18002B30E
0x18002b309  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x18002b30e  mov     edx, 1
0x18002b313  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b318  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b31f  cmp     rcx, rsi
0x18002b322  jz      short loc_18002B350
0x18002b324  test    byte ptr [rcx+1Ch], 2
0x18002b328  jz      short loc_18002B350
0x18002b32a  cmp     byte ptr [rcx+19h], 5
0x18002b32e  jb      short loc_18002B350
0x18002b330  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002b337  lea     r8, WPP_647da024c2503459d7fafff2f0112b72_Traceguids
0x18002b33e  mov     rcx, [rcx+10h]
0x18002b342  mov     edx, 0Bh
0x18002b347  mov     dword ptr [rsp+38h+phkResult], ebx
0x18002b34b  call    WPP_SF_sD
0x18002b350  mov     eax, ebx
0x18002b352  mov     rbx, [rsp+38h+arg_18]
0x18002b357  add     rsp, 30h
0x18002b35b  pop     rsi
0x18002b35c  retn
```
