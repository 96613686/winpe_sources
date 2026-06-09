# APP_POOL_HASH_MAPPER::CheckAndAddAppPool(ushort const *,STRU *)

- ea: `0x180007878`
- end: `0x180007af3`
- name: `?CheckAndAddAppPool@APP_POOL_HASH_MAPPER@@QEAAJPEBGPEAVSTRU@@@Z`
- size: `635`
- prototype: `__int64 __fastcall(APP_POOL_HASH_MAPPER *this, const unsigned __int16 *, struct STRU *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800027c0`

## callees

- `0x180001008`
- `0x180001048`
- `0x180007878`
- `0x18000885c`

## import_xrefs

- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800078b0`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800079a5`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800078b0`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800079a5`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180007a78`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180007ad4`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180007a78`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180007ad4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007951`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007951`
- `iisutil!PuDbgPrintError` at `0x180007920`
- `iisutil!PuDbgPrintError` at `0x180007aba`
- `iisutil!PuDbgPrintError` at `0x180007920`
- `iisutil!PuDbgPrintError` at `0x180007aba`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800078c5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800079ba`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007a5a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800078c5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800079ba`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007a5a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007a2f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007a2f`

## string_xrefs

- `0x180007912`: `servercommon\inetsrv\iis\iisrearc\core\common\apppoolhashmapper\app_pool_hash_mapper.cxx`
- `0x180007aac`: `servercommon\inetsrv\iis\iisrearc\core\common\apppoolhashmapper\app_pool_hash_mapper.cxx`

## pseudocode

```c
__int64 __fastcall APP_POOL_HASH_MAPPER::CheckAndAddAppPool(
        APP_POOL_HASH_MAPPER *this,
        const unsigned __int16 *a2,
        struct STRU *a3)
{
  int Key; // eax
  char *v7; // rbx
  int v8; // edi
  struct APP_POOL_HASH *v10; // r15
  int v11; // eax
  char *v12; // rax
  __int64 v13; // r8
  void *Block; // [rsp+60h] [rbp+8h] BYREF
  struct APP_POOL_HASH *v15; // [rsp+78h] [rbp+20h] BYREF

  v15 = 0;
  Block = 0;
  Key = CLKRHashTable::FindKey((char *)this + 8, a2, &Block);
  v7 = (char *)Block;
  if ( !Key )
  {
    v8 = STRU::Copy(a3, a2);
    if ( v8 >= 0 )
    {
      v8 = -2147024844;
      *((_DWORD *)v7 + 18) = 0;
      goto LABEL_9;
    }
LABEL_8:
    if ( !v7 )
      return (unsigned int)v8;
    goto LABEL_9;
  }
  if ( Key != 2 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\apppoolhashmapper\\app_pool_hash_mapper.cxx",
        144,
        "APP_POOL_HASH_MAPPER::CheckAndAddAppPool",
        -2147467259,
        "AppPoolToHash hash table lookup failed\n");
LABEL_7:
    v8 = -2147467259;
    goto LABEL_8;
  }
  v8 = CalculateAppPoolHash(a2, &v15);
  if ( v8 < 0 )
    goto LABEL_8;
  Block = 0;
  v10 = v15;
  v11 = CLKRHashTable::FindKey((char *)this + 80, v15, &Block);
  v7 = (char *)Block;
  if ( !v11 )
  {
    v8 = STRU::Copy(a3, a2);
    if ( v8 >= 0 )
    {
      v8 = -2147022882;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7, 0xFFFFFFFF) == 1 && v7 )
        goto LABEL_10;
      return (unsigned int)v8;
    }
    goto LABEL_8;
  }
  if ( v11 != 2 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\apppoolhashmapper\\app_pool_hash_mapper.cxx",
        181,
        "APP_POOL_HASH_MAPPER::CheckAndAddAppPool",
        -2147467259,
        "AppPool hash table lookup failed\n");
    goto LABEL_7;
  }
  v12 = (char *)operator new(0x60u);
  v7 = v12;
  Block = v12;
  if ( v12 )
  {
    *(_DWORD *)v12 = 1;
    STRU::STRU((STRU *)(v12 + 8));
    *((_QWORD *)v7 + 8) = 0;
    *((_DWORD *)v7 + 18) = 1;
  }
  else
  {
    v7 = 0;
  }
  if ( !v7 )
    return (unsigned int)-2147024882;
  v8 = STRU::Copy((STRU *)(v7 + 8), a2);
  if ( v8 >= 0 )
  {
    *((_QWORD *)v7 + 8) = v10;
    if ( (unsigned int)CLKRHashTable::InsertRecord((char *)this + 8, v7, 0) )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
      {
LABEL_31:
        v8 = -2147467259;
        goto LABEL_9;
      }
      v13 = 211;
LABEL_30:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\apppoolhashmapper\\app_pool_hash_mapper.cxx",
        v13,
        "APP_POOL_HASH_MAPPER::CheckAndAddAppPool",
        -2147467259,
        "Inserting application into hashtable failed\n");
      goto LABEL_31;
    }
    if ( (unsigned int)CLKRHashTable::InsertRecord((char *)this + 80, v7, 0) )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_31;
      v13 = 226;
      goto LABEL_30;
    }
  }
LABEL_9:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7, 0xFFFFFFFF) == 1 )
  {
LABEL_10:
    operator delete(*((void **)v7 + 8));
    *((_QWORD *)v7 + 8) = 0;
    STRU::~STRU((STRU *)(v7 + 8));
    operator delete(v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007878  mov     rax, rsp
0x18000787b  mov     [rax+10h], rbx
0x18000787f  mov     [rax+18h], rbp
0x180007883  push    rsi
0x180007884  push    rdi
0x180007885  push    r12
0x180007887  push    r14
0x180007889  push    r15
0x18000788b  sub     rsp, 30h
0x18000788f  mov     rbp, r8
0x180007892  mov     rsi, rdx
0x180007895  mov     r14, rcx
0x180007898  mov     qword ptr [rax+20h], 0
0x1800078a0  mov     qword ptr [rax+8], 0
0x1800078a8  lea     r8, [rax+8]
0x1800078ac  add     rcx, 8
0x1800078b0  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800078b6  mov     rbx, [rsp+58h+Block]
0x1800078bb  test    eax, eax
0x1800078bd  jnz     short loc_1800078DF
0x1800078bf  mov     rdx, rsi
0x1800078c2  mov     rcx, rbp
0x1800078c5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800078cb  mov     edi, eax
0x1800078cd  test    eax, eax
0x1800078cf  js      short loc_18000792B
0x1800078d1  mov     edi, 80070034h
0x1800078d6  mov     dword ptr [rbx+48h], 0
0x1800078dd  jmp     short loc_180007930
0x1800078df  cmp     eax, 2
0x1800078e2  jz      loc_180007978
0x1800078e8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800078ef  jz      short loc_180007926
0x1800078f1  lea     rax, aApppooltohashH; "AppPoolToHash hash table lookup failed"...
0x1800078f8  mov     r8d, 90h
0x1800078fe  mov     [rsp+58h+var_30], rax
0x180007903  lea     r9, aAppPoolHashMap; "APP_POOL_HASH_MAPPER::CheckAndAddAppPoo"...
0x18000790a  mov     [rsp+58h+var_38], 80004005h
0x180007912  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180007919  mov     rcx, cs:g_pDebug
0x180007920  call    cs:__imp_PuDbgPrintError
0x180007926  mov     edi, 80004005h
0x18000792b  test    rbx, rbx
0x18000792e  jz      short loc_18000795F
0x180007930  or      eax, 0FFFFFFFFh
0x180007933  lock xadd [rbx], eax
0x180007937  cmp     eax, 1
0x18000793a  jnz     short loc_18000795F
0x18000793c  mov     rcx, [rbx+40h]; Block
0x180007940  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007945  mov     qword ptr [rbx+40h], 0
0x18000794d  lea     rcx, [rbx+8]
0x180007951  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007957  mov     rcx, rbx; Block
0x18000795a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000795f  mov     eax, edi
0x180007961  mov     rbx, [rsp+58h+arg_8]
0x180007966  mov     rbp, [rsp+58h+arg_10]
0x18000796b  add     rsp, 30h
0x18000796f  pop     r15
0x180007971  pop     r14
0x180007973  pop     r12
0x180007975  pop     rdi
0x180007976  pop     rsi
0x180007977  retn
0x180007978  lea     rdx, [rsp+58h+arg_18]; struct APP_POOL_HASH **
0x18000797d  mov     rcx, rsi; Src
0x180007980  call    ?CalculateAppPoolHash@@YAJPEBGPEAPEAUAPP_POOL_HASH@@@Z; CalculateAppPoolHash(ushort const *,APP_POOL_HASH * *)
0x180007985  mov     edi, eax
0x180007987  test    eax, eax
0x180007989  js      short loc_18000792B
0x18000798b  mov     [rsp+58h+Block], 0
0x180007994  lea     r8, [rsp+58h+Block]
0x180007999  mov     r15, [rsp+58h+arg_18]
0x18000799e  mov     rdx, r15
0x1800079a1  lea     rcx, [r14+50h]
0x1800079a5  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800079ab  mov     rbx, [rsp+58h+Block]
0x1800079b0  test    eax, eax
0x1800079b2  jnz     short loc_1800079E9
0x1800079b4  mov     rdx, rsi
0x1800079b7  mov     rcx, rbp
0x1800079ba  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800079c0  mov     edi, eax
0x1800079c2  test    eax, eax
0x1800079c4  js      loc_18000792B
0x1800079ca  mov     edi, 800707DEh
0x1800079cf  or      eax, 0FFFFFFFFh
0x1800079d2  lock xadd [rbx], eax
0x1800079d6  cmp     eax, 1
0x1800079d9  jnz     short loc_18000795F
0x1800079db  test    rbx, rbx
0x1800079de  jz      loc_18000795F
0x1800079e4  jmp     loc_18000793C
0x1800079e9  cmp     eax, 2
0x1800079ec  jz      short loc_180007A0D
0x1800079ee  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800079f5  jz      loc_180007926
0x1800079fb  lea     rax, aApppoolHashTab; "AppPool hash table lookup failed\n"
0x180007a02  mov     r8d, 0B5h
0x180007a08  jmp     loc_1800078FE
0x180007a0d  mov     ecx, 60h ; '`'; Size
0x180007a12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007a17  mov     rbx, rax
0x180007a1a  mov     [rsp+58h+Block], rax
0x180007a1f  test    rax, rax
0x180007a22  jz      short loc_180007A42
0x180007a24  mov     edi, 1
0x180007a29  mov     [rax], edi
0x180007a2b  lea     rcx, [rax+8]
0x180007a2f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180007a35  mov     qword ptr [rbx+40h], 0
0x180007a3d  mov     [rbx+48h], edi
0x180007a40  jmp     short loc_180007A44
0x180007a42  xor     ebx, ebx
0x180007a44  test    rbx, rbx
0x180007a47  jnz     short loc_180007A53
0x180007a49  mov     edi, 8007000Eh
0x180007a4e  jmp     loc_18000795F
0x180007a53  lea     rcx, [rbx+8]
0x180007a57  mov     rdx, rsi
0x180007a5a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180007a60  mov     edi, eax
0x180007a62  test    eax, eax
0x180007a64  js      loc_180007930
0x180007a6a  mov     [rbx+40h], r15
0x180007a6e  xor     r8d, r8d
0x180007a71  mov     rdx, rbx
0x180007a74  lea     rcx, [r14+8]
0x180007a78  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180007a7e  test    eax, eax
0x180007a80  jz      short loc_180007ACA
0x180007a82  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007a89  jz      short loc_180007AC0
0x180007a8b  mov     r8d, 0D3h
0x180007a91  lea     rax, aInsertingAppli; "Inserting application into hashtable fa"...
0x180007a98  mov     [rsp+58h+var_30], rax
0x180007a9d  lea     r9, aAppPoolHashMap; "APP_POOL_HASH_MAPPER::CheckAndAddAppPoo"...
0x180007aa4  mov     [rsp+58h+var_38], 80004005h
0x180007aac  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180007ab3  mov     rcx, cs:g_pDebug
0x180007aba  call    cs:__imp_PuDbgPrintError
0x180007ac0  mov     edi, 80004005h
0x180007ac5  jmp     loc_180007930
0x180007aca  xor     r8d, r8d
0x180007acd  mov     rdx, rbx
0x180007ad0  lea     rcx, [r14+50h]
0x180007ad4  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180007ada  test    eax, eax
0x180007adc  jz      loc_180007930
0x180007ae2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007ae9  jz      short loc_180007AC0
0x180007aeb  mov     r8d, 0E2h
0x180007af1  jmp     short loc_180007A91
```
