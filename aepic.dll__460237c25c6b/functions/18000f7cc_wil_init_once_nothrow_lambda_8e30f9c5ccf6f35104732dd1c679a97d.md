# wil::init_once_nothrow__lambda_8e30f9c5ccf6f35104732dd1c679a97d___

- ea: `0x18000f7cc`
- end: `0x18000f860`
- name: `wil::init_once_nothrow__lambda_8e30f9c5ccf6f35104732dd1c679a97d___`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013e40`

## callees

- `0x18000c35c`
- `0x18000f7cc`
- `0x180015cf0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f7ed`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f7ed`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f853`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f853`

## pseudocode

```c
__int64 wil::init_once_nothrow__lambda_8e30f9c5ccf6f35104732dd1c679a97d___()
{
  const char *v0; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  WINBOOL fPending; // [rsp+58h] [rbp+10h] BYREF

  fPending = 0;
  if ( !InitOnceBeginInitialize(&InitOnce, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v0);
  if ( fPending )
  {
    TelCacheProvider::Initialize(qword_180122CF0, L"FileLastRuntime", 0, 0, 3, 0, 0);
    InitOnceComplete(&InitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f7cc  mov     byte ptr [rsp+fPending], dl
0x18000f7d0  sub     rsp, 48h
0x18000f7d4  mov     [rsp+48h+fPending], 0
0x18000f7dc  xor     r9d, r9d; lpContext
0x18000f7df  lea     r8, [rsp+48h+fPending]; fPending
0x18000f7e4  xor     edx, edx; dwFlags
0x18000f7e6  lea     rcx, InitOnce; lpInitOnce
0x18000f7ed  call    cs:__imp_InitOnceBeginInitialize
0x18000f7f3  test    eax, eax
0x18000f7f5  jnz     short loc_18000F80F
0x18000f7f7  mov     rcx, [rsp+48h]; this
0x18000f7fc  lea     r8, aWil; "wil"
0x18000f803  mov     edx, 37Ah; void *
0x18000f808  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f80d  jmp     short loc_18000F85B
0x18000f80f  cmp     [rsp+48h+fPending], 0
0x18000f814  jz      short loc_18000F859
0x18000f816  mov     [rsp+48h+var_18], 0
0x18000f81e  mov     [rsp+48h+var_20], 0
0x18000f826  mov     [rsp+48h+var_28], 3
0x18000f82e  xor     r9d, r9d
0x18000f831  xor     r8d, r8d
0x18000f834  lea     rdx, ?CacheProviderName@FileLastRuntimeTracker@@2QBGB; "FileLastRuntime"
0x18000f83b  lea     rcx, qword_180122CF0
0x18000f842  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x18000f847  xor     r8d, r8d; lpContext
0x18000f84a  xor     edx, edx; dwFlags
0x18000f84c  lea     rcx, InitOnce; lpInitOnce
0x18000f853  call    cs:__imp_InitOnceComplete
0x18000f859  xor     eax, eax
0x18000f85b  add     rsp, 48h
0x18000f85f  retn
```
