# UninitializeLoader

- ea: `0x18001a2fc`
- end: `0x18001a3c4`
- name: `UninitializeLoader`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016068`

## callees

- `0x180005060`
- `0x18000ccf0`
- `0x18001a2fc`
- `0x18001a998`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a3a8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a3a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a345`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a345`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a332`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a332`

## string_xrefs

- `0x18001a30f`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
void UninitializeLoader()
{
  __int64 v0; // rax

  if ( g_fLoaderInitialized )
  {
    EnterCriticalSection(&g_csLoaderLock);
    LeaveCriticalSection(&g_csLoaderLock);
    v0 = g_pLoadedProviderList;
    if ( g_pLoadedProviderList )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_9;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_321c0d2313123f81ee86e6c36df24469_Traceguids);
      while ( 1 )
      {
        v0 = g_pLoadedProviderList;
LABEL_9:
        if ( !v0 )
          break;
        UnloadProvider(v0);
      }
    }
    DeleteCriticalSection(&g_csLoaderLock);
    g_fLoaderInitialized = 0;
  }
  else
  {
    DebugTraceError(2148073504LL, "NTE_FAIL", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", 1987);
  }
}

```

## disassembly

```asm
0x18001a2fc  sub     rsp, 28h
0x18001a300  cmp     cs:g_fLoaderInitialized, 0
0x18001a307  jnz     short loc_18001A32B
0x18001a309  mov     r9d, 7C3h
0x18001a30f  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001a316  lea     rdx, aNteFail; "NTE_FAIL"
0x18001a31d  mov     ecx, 80090020h
0x18001a322  add     rsp, 28h
0x18001a326  jmp     DebugTraceError
0x18001a32b  lea     rcx, g_csLoaderLock; lpCriticalSection
0x18001a332  call    cs:__imp_EnterCriticalSection
0x18001a339  nop     dword ptr [rax+rax+00h]
0x18001a33e  lea     rcx, g_csLoaderLock; lpCriticalSection
0x18001a345  call    cs:__imp_LeaveCriticalSection
0x18001a34c  nop     dword ptr [rax+rax+00h]
0x18001a351  mov     rax, cs:g_pLoadedProviderList
0x18001a358  test    rax, rax
0x18001a35b  jz      short loc_18001A3A1
0x18001a35d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a364  lea     rdx, WPP_GLOBAL_Control
0x18001a36b  cmp     rcx, rdx
0x18001a36e  jz      short loc_18001A39C
0x18001a370  test    byte ptr [rcx+1Ch], 2
0x18001a374  jz      short loc_18001A39C
0x18001a376  mov     rcx, [rcx+10h]
0x18001a37a  lea     r8, WPP_321c0d2313123f81ee86e6c36df24469_Traceguids
0x18001a381  mov     edx, 19h
0x18001a386  call    WPP_SF_
0x18001a38b  jmp     short loc_18001A395
0x18001a38d  mov     rcx, rax
0x18001a390  call    UnloadProvider
0x18001a395  mov     rax, cs:g_pLoadedProviderList
0x18001a39c  test    rax, rax
0x18001a39f  jnz     short loc_18001A38D
0x18001a3a1  lea     rcx, g_csLoaderLock; lpCriticalSection
0x18001a3a8  call    cs:__imp_DeleteCriticalSection
0x18001a3af  nop     dword ptr [rax+rax+00h]
0x18001a3b4  mov     cs:g_fLoaderInitialized, 0
0x18001a3be  add     rsp, 28h
0x18001a3c2  retn
```
