# UnlockRpcCache(_RPC_CACHE_TYPE)

- ea: `0x18000fc80`
- end: `0x18000fcb6`
- name: `?UnlockRpcCache@@YAXW4_RPC_CACHE_TYPE@@@Z`
- size: `54`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019274`

## callees

- `0x18000fc80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000fcab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000fcab`

## pseudocode

```c
void __fastcall UnlockRpcCache(int a1)
{
  int v1; // ecx
  RTL_SRWLOCK *v2; // rcx

  if ( a1 )
  {
    v1 = a1 - 1;
    if ( v1 )
    {
      if ( v1 != 1 )
        return;
      v2 = &g_RPCHandleCacheLock;
    }
    else
    {
      v2 = &stru_1800234E8;
    }
  }
  else
  {
    v2 = &stru_180023508;
  }
  ReleaseSRWLockShared(v2);
}

```

## disassembly

```asm
0x18000fc80  sub     rsp, 28h
0x18000fc84  test    ecx, ecx
0x18000fc86  jz      short loc_18000FCA4
0x18000fc88  sub     ecx, 1
0x18000fc8b  jz      short loc_18000FC9B
0x18000fc8d  cmp     ecx, 1
0x18000fc90  jnz     short loc_18000FCB1
0x18000fc92  lea     rcx, ?g_RPCHandleCacheLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_RPCHandleCacheLock
0x18000fc99  jmp     short loc_18000FCAB
0x18000fc9b  lea     rcx, stru_1800234E8
0x18000fca2  jmp     short loc_18000FCAB
0x18000fca4  lea     rcx, stru_180023508; SRWLock
0x18000fcab  call    cs:__imp_ReleaseSRWLockShared
0x18000fcb1  add     rsp, 28h
0x18000fcb5  retn
```
