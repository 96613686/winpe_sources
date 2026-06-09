# APP_POOL_HASH_MAPPER::DeleteAppPool(ushort const *)

- ea: `0x180007afc`
- end: `0x180007c54`
- name: `?DeleteAppPool@APP_POOL_HASH_MAPPER@@QEAAJPEBG@Z`
- size: `344`
- prototype: `__int64 __fastcall(APP_POOL_HASH_MAPPER *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800024ac`

## callees

- `0x180001048`
- `0x180007afc`

## import_xrefs

- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180007b20`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180007b20`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x180007b37`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x180007bfc`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x180007b37`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x180007bfc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007bb6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007be8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007bb6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007be8`
- `iisutil!PuDbgPrintError` at `0x180007b7d`
- `iisutil!PuDbgPrintError` at `0x180007c3e`
- `iisutil!PuDbgPrintError` at `0x180007b7d`
- `iisutil!PuDbgPrintError` at `0x180007c3e`

## string_xrefs

- `0x180007b76`: `servercommon\inetsrv\iis\iisrearc\core\common\apppoolhashmapper\app_pool_hash_mapper.cxx`
- `0x180007c37`: `servercommon\inetsrv\iis\iisrearc\core\common\apppoolhashmapper\app_pool_hash_mapper.cxx`
- `0x180007b61`: `APP_POOL_HASH_MAPPER::DeleteAppPool`
- `0x180007c22`: `APP_POOL_HASH_MAPPER::DeleteAppPool`

## pseudocode

```c
__int64 __fastcall APP_POOL_HASH_MAPPER::DeleteAppPool(APP_POOL_HASH_MAPPER *this, const unsigned __int16 *a2)
{
  char *v2; // rbp
  int Key; // eax
  void **v6; // rdi
  unsigned int v7; // ebx
  void *Block; // [rsp+60h] [rbp+8h] BYREF

  v2 = (char *)this + 8;
  Block = 0;
  Key = CLKRHashTable::FindKey((char *)this + 8, a2, &Block);
  v6 = (void **)Block;
  if ( Key )
  {
LABEL_5:
    v7 = -2147467259;
    if ( v6 && _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
    {
      operator delete(v6[8]);
      v6[8] = 0;
      STRU::~STRU((STRU *)(v6 + 1));
      operator delete(v6);
    }
    return v7;
  }
  if ( (unsigned int)CLKRHashTable::DeleteKey((char *)this + 80, *((_QWORD *)Block + 8)) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\apppoolhashmapper\\app_pool_hash_mapper.cxx",
        379,
        "APP_POOL_HASH_MAPPER::DeleteAppPool",
        -2147467259,
        "Removing entry from hashtable failed\n");
    goto LABEL_5;
  }
  v7 = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
  {
    operator delete(v6[8]);
    v6[8] = 0;
    STRU::~STRU((STRU *)(v6 + 1));
    operator delete(v6);
  }
  if ( (unsigned int)CLKRHashTable::DeleteKey(v2, a2) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\apppoolhashmapper\\app_pool_hash_mapper.cxx",
        397,
        "APP_POOL_HASH_MAPPER::DeleteAppPool",
        -2147467259,
        "Removing entry from hashtable failed\n");
    return (unsigned int)-2147467259;
  }
  return v7;
}

```

## disassembly

```asm
0x180007afc  push    rbx
0x180007afe  push    rbp
0x180007aff  push    rsi
0x180007b00  push    rdi
0x180007b01  sub     rsp, 38h
0x180007b05  lea     rbp, [rcx+8]
0x180007b09  mov     [rsp+58h+Block], 0
0x180007b12  mov     rbx, rcx
0x180007b15  lea     r8, [rsp+58h+Block]
0x180007b1a  mov     rcx, rbp
0x180007b1d  mov     rsi, rdx
0x180007b20  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180007b26  mov     rdi, [rsp+58h+Block]
0x180007b2b  test    eax, eax
0x180007b2d  jnz     short loc_180007B83
0x180007b2f  mov     rdx, [rdi+40h]
0x180007b33  lea     rcx, [rbx+50h]
0x180007b37  call    cs:__imp_?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z; CLKRHashTable::DeleteKey(unsigned __int64)
0x180007b3d  test    eax, eax
0x180007b3f  jz      loc_180007BC9
0x180007b45  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007b4c  jz      short loc_180007B83
0x180007b4e  mov     rcx, cs:g_pDebug
0x180007b55  lea     rax, aRemovingEntryF; "Removing entry from hashtable failed\n"
0x180007b5c  mov     [rsp+58h+var_30], rax
0x180007b61  lea     r9, aAppPoolHashMap_0; "APP_POOL_HASH_MAPPER::DeleteAppPool"
0x180007b68  mov     r8d, 17Bh
0x180007b6e  mov     [rsp+58h+var_38], 80004005h
0x180007b76  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180007b7d  call    cs:__imp_PuDbgPrintError
0x180007b83  mov     ebx, 80004005h
0x180007b88  test    rdi, rdi
0x180007b8b  jz      loc_180007C49
0x180007b91  or      eax, 0FFFFFFFFh
0x180007b94  lock xadd [rdi], eax
0x180007b98  cmp     eax, 1
0x180007b9b  jnz     loc_180007C49
0x180007ba1  mov     rcx, [rdi+40h]; Block
0x180007ba5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007baa  lea     rcx, [rdi+8]
0x180007bae  mov     qword ptr [rdi+40h], 0
0x180007bb6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007bbc  mov     rcx, rdi; Block
0x180007bbf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007bc4  jmp     loc_180007C49
0x180007bc9  xor     ebx, ebx
0x180007bcb  or      eax, 0FFFFFFFFh
0x180007bce  lock xadd [rdi], eax
0x180007bd2  cmp     eax, 1
0x180007bd5  jnz     short loc_180007BF6
0x180007bd7  mov     rcx, [rdi+40h]; Block
0x180007bdb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007be0  lea     rcx, [rdi+8]
0x180007be4  mov     [rdi+40h], rbx
0x180007be8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007bee  mov     rcx, rdi; Block
0x180007bf1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007bf6  mov     rdx, rsi
0x180007bf9  mov     rcx, rbp
0x180007bfc  call    cs:__imp_?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z; CLKRHashTable::DeleteKey(unsigned __int64)
0x180007c02  test    eax, eax
0x180007c04  jz      short loc_180007C49
0x180007c06  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007c0d  jz      short loc_180007C44
0x180007c0f  mov     rcx, cs:g_pDebug
0x180007c16  lea     rax, aRemovingEntryF; "Removing entry from hashtable failed\n"
0x180007c1d  mov     [rsp+58h+var_30], rax
0x180007c22  lea     r9, aAppPoolHashMap_0; "APP_POOL_HASH_MAPPER::DeleteAppPool"
0x180007c29  mov     r8d, 18Dh
0x180007c2f  mov     [rsp+58h+var_38], 80004005h
0x180007c37  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180007c3e  call    cs:__imp_PuDbgPrintError
0x180007c44  mov     ebx, 80004005h
0x180007c49  mov     eax, ebx
0x180007c4b  add     rsp, 38h
0x180007c4f  pop     rdi
0x180007c50  pop     rsi
0x180007c51  pop     rbp
0x180007c52  pop     rbx
0x180007c53  retn
```
