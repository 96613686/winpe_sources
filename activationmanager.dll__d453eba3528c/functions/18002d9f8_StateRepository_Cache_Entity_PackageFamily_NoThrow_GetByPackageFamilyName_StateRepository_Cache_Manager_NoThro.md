# StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18002d9f8`
- end: `0x18002dcdf`
- name: `?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `743`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18002ce50`
- `0x18008df24`

## callees

- `0x18000a980`
- `0x18000b5c0`
- `0x18000cb80`
- `0x18002d9f8`
- `0x18005ae90`
- `0x18005ba40`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002db9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002db9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18002dc32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18002dc32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002da56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002da56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002da7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dac9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dbc0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dc13`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dc90`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dcba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002da7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dac9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dbc0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dc13`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dc90`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002dcba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002db64`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002dca5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002db64`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002dca5`

## string_xrefs

- `0x18002da8b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002dbd1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002dc45`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002daab`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002db3d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002dbf1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  int *v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  char v24; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+258h] [rbp+158h]
  __int64 v28; // [rsp+260h] [rbp+160h]
  _BYTE *v29; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v24 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v20 = 0;
  v22 = v20;
  v23 = 0;
  v6 = SRCacheContext_Open(v3, L"PackageFamily\\Index\\PackageFamilyName", 0, &v23);
  if ( v24 )
  {
    v7 = *(_QWORD *)v22;
    *(_QWORD *)v22 = v23;
    if ( v7 )
      SRCacheContext_Close(v7);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
    v8 = 193;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
LABEL_7:
    v9 = *(_QWORD *)v20;
    *(_QWORD *)v20 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    return (unsigned int)v6;
  }
  if ( !*(_QWORD *)v20 )
  {
    v6 = -2140733422;
    v8 = 194;
    goto LABEL_6;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v29 = v26;
  v28 = 256;
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a2);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v11,
      v20[0]);
LABEL_14:
    v12 = v25;
    v25 = 0;
    if ( v12 )
      SRCache_Free();
    goto LABEL_7;
  }
  v22 = (int *)&v21;
  v21 = 0;
  v23 = 0;
  v24 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v20, v29, 0, &v23);
  if ( v24 )
  {
    v13 = *(_QWORD *)v22;
    *(_QWORD *)v22 = v23;
    if ( v13 )
      SRCacheContext_Close(v13);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
    v14 = 201;
    goto LABEL_21;
  }
  if ( v21 )
  {
    v16 = SRCacheContext_EnumerateData(v21, 0, a3);
    v6 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v16,
        v20[0]);
      v14 = 204;
      goto LABEL_21;
    }
  }
  v6 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v20,
         L"PackageFamily\\Index\\PackageFamilyName");
  if ( v6 < 0 )
  {
    v14 = 207;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
    v15 = v21;
    v21 = 0;
    if ( v15 )
      SRCacheContext_Close(v15);
    goto LABEL_14;
  }
  v17 = v21;
  v21 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  v18 = v25;
  v25 = 0;
  if ( v18 )
    SRCache_Free();
  v19 = *(_QWORD *)v20;
  *(_QWORD *)v20 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  return 0;
}

```

## disassembly

```asm
0x18002d9f8  push    rbp
0x18002d9fa  push    rbx
0x18002d9fb  push    rsi
0x18002d9fc  push    rdi
0x18002d9fd  push    r14
0x18002d9ff  lea     rbp, [rsp-180h]
0x18002da07  sub     rsp, 280h
0x18002da0e  mov     rax, cs:__security_cookie
0x18002da15  xor     rax, rsp
0x18002da18  mov     [rbp+1A0h+var_30], rax
0x18002da1f  xor     r14d, r14d
0x18002da22  mov     [rsp+2A0h+var_260], 1
0x18002da27  mov     [r8], r14
0x18002da2a  lea     rax, [rsp+2A0h+var_280]
0x18002da2f  mov     rcx, [rcx]
0x18002da32  lea     r9, [rsp+2A0h+var_268]
0x18002da37  mov     rdi, r8
0x18002da3a  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18002da3f  mov     rsi, rdx
0x18002da42  mov     [rsp+2A0h+var_270], rax
0x18002da47  xor     r8d, r8d
0x18002da4a  mov     [rsp+2A0h+var_268], r14
0x18002da4f  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x18002da56  call    cs:__imp_SRCacheContext_Open
0x18002da5c  mov     ebx, eax
0x18002da5e  cmp     [rsp+2A0h+var_260], r14b
0x18002da63  jz      short loc_18002DA80
0x18002da65  mov     r8, [rsp+2A0h+var_270]
0x18002da6a  mov     rdx, [rsp+2A0h+var_268]
0x18002da6f  mov     rcx, [r8]
0x18002da72  mov     [r8], rdx
0x18002da75  test    rcx, rcx
0x18002da78  jz      short loc_18002DA80
0x18002da7a  call    cs:__imp_SRCacheContext_Close
0x18002da80  test    ebx, ebx
0x18002da82  jns     short loc_18002DAD6
0x18002da84  mov     rcx, [rbp+1A8h]; this
0x18002da8b  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002da92  mov     r9d, ebx; char *
0x18002da95  mov     edx, 18Ch; void *
0x18002da9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002da9f  mov     edx, 0C1h; void *
0x18002daa4  mov     rcx, [rbp+1A8h]; this
0x18002daab  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dab2  mov     r9d, ebx; char *
0x18002dab5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002daba  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18002dabf  mov     qword ptr [rsp+2A0h+var_280], r14
0x18002dac4  test    rcx, rcx
0x18002dac7  jz      short loc_18002DACF
0x18002dac9  call    cs:__imp_SRCacheContext_Close
0x18002dacf  mov     eax, ebx
0x18002dad1  jmp     loc_18002DCC2
0x18002dad6  cmp     qword ptr [rsp+2A0h+var_280], r14
0x18002dadb  setnz   al
0x18002dade  test    al, al
0x18002dae0  jnz     short loc_18002DAEE
0x18002dae2  mov     ebx, 80670012h
0x18002dae7  mov     edx, 0C2h
0x18002daec  jmp     short loc_18002DAA4
0x18002daee  xor     edx, edx; Val
0x18002daf0  mov     [rsp+2A0h+var_250], r14
0x18002daf5  mov     r8d, 200h; Size
0x18002dafb  lea     rcx, [rsp+2A0h+var_248]; void *
0x18002db00  call    memset_0
0x18002db05  lea     rax, [rsp+2A0h+var_248]
0x18002db0a  mov     [rbp+1A0h+var_48], r14
0x18002db11  mov     rdx, rsi; unsigned __int16 *
0x18002db14  mov     [rbp+1A0h+var_38], rax
0x18002db1b  lea     rcx, [rsp+2A0h+var_250]; this
0x18002db20  mov     [rbp+1A0h+var_40], 100h
0x18002db2b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18002db30  mov     ebx, eax
0x18002db32  test    eax, eax
0x18002db34  jns     short loc_18002DB6F
0x18002db36  mov     rcx, [rbp+1A8h]; this
0x18002db3d  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002db44  mov     r9d, eax; char *
0x18002db47  mov     edx, 0C5h; void *
0x18002db4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002db51  mov     rcx, [rsp+2A0h+var_250]
0x18002db56  mov     [rsp+2A0h+var_250], r14
0x18002db5b  test    rcx, rcx
0x18002db5e  jz      loc_18002DABA
0x18002db64  call    cs:__imp_SRCache_Free
0x18002db6a  jmp     loc_18002DABA
0x18002db6f  mov     rdx, [rbp+1A0h+var_38]
0x18002db76  lea     rax, [rsp+2A0h+var_278]
0x18002db7b  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18002db80  lea     r9, [rsp+2A0h+var_268]
0x18002db85  xor     r8d, r8d
0x18002db88  mov     [rsp+2A0h+var_270], rax
0x18002db8d  mov     [rsp+2A0h+var_278], r14
0x18002db92  mov     [rsp+2A0h+var_268], r14
0x18002db97  mov     [rsp+2A0h+var_260], 1
0x18002db9c  call    cs:__imp_SRCacheContext_OpenSubContext
0x18002dba2  mov     ebx, eax
0x18002dba4  cmp     [rsp+2A0h+var_260], r14b
0x18002dba9  jz      short loc_18002DBC6
0x18002dbab  mov     r8, [rsp+2A0h+var_270]
0x18002dbb0  mov     rdx, [rsp+2A0h+var_268]
0x18002dbb5  mov     rcx, [r8]
0x18002dbb8  mov     [r8], rdx
0x18002dbbb  test    rcx, rcx
0x18002dbbe  jz      short loc_18002DBC6
0x18002dbc0  call    cs:__imp_SRCacheContext_Close
0x18002dbc6  test    ebx, ebx
0x18002dbc8  jns     short loc_18002DC1E
0x18002dbca  mov     rcx, [rbp+1A8h]; this
0x18002dbd1  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dbd8  mov     r9d, ebx; char *
0x18002dbdb  mov     edx, 1B0h; void *
0x18002dbe0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dbe5  mov     edx, 0C9h; void *
0x18002dbea  mov     rcx, [rbp+1A8h]; this
0x18002dbf1  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dbf8  mov     r9d, ebx; char *
0x18002dbfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dc00  mov     rcx, [rsp+2A0h+var_278]
0x18002dc05  mov     [rsp+2A0h+var_278], r14
0x18002dc0a  test    rcx, rcx
0x18002dc0d  jz      loc_18002DB51
0x18002dc13  call    cs:__imp_SRCacheContext_Close
0x18002dc19  jmp     loc_18002DB51
0x18002dc1e  mov     rcx, [rsp+2A0h+var_278]
0x18002dc23  test    rcx, rcx
0x18002dc26  setnz   al
0x18002dc29  test    al, al
0x18002dc2b  jz      short loc_18002DC60
0x18002dc2d  mov     r8, rdi
0x18002dc30  xor     edx, edx
0x18002dc32  call    cs:__imp_SRCacheContext_EnumerateData
0x18002dc38  mov     ebx, eax
0x18002dc3a  test    eax, eax
0x18002dc3c  jns     short loc_18002DC60
0x18002dc3e  mov     rcx, [rbp+1A8h]; this
0x18002dc45  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dc4c  mov     r9d, eax; char *
0x18002dc4f  mov     edx, 2A6h; void *
0x18002dc54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dc59  mov     edx, 0CCh
0x18002dc5e  jmp     short loc_18002DBEA
0x18002dc60  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x18002dc67  lea     rcx, [rsp+2A0h+var_280]; this
0x18002dc6c  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18002dc71  mov     ebx, eax
0x18002dc73  test    eax, eax
0x18002dc75  jns     short loc_18002DC81
0x18002dc77  mov     edx, 0CFh
0x18002dc7c  jmp     loc_18002DBEA
0x18002dc81  mov     rcx, [rsp+2A0h+var_278]
0x18002dc86  mov     [rsp+2A0h+var_278], r14
0x18002dc8b  test    rcx, rcx
0x18002dc8e  jz      short loc_18002DC96
0x18002dc90  call    cs:__imp_SRCacheContext_Close
0x18002dc96  mov     rcx, [rsp+2A0h+var_250]
0x18002dc9b  mov     [rsp+2A0h+var_250], r14
0x18002dca0  test    rcx, rcx
0x18002dca3  jz      short loc_18002DCAB
0x18002dca5  call    cs:__imp_SRCache_Free
0x18002dcab  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18002dcb0  mov     qword ptr [rsp+2A0h+var_280], r14
0x18002dcb5  test    rcx, rcx
0x18002dcb8  jz      short loc_18002DCC0
0x18002dcba  call    cs:__imp_SRCacheContext_Close
0x18002dcc0  xor     eax, eax
0x18002dcc2  mov     rcx, [rbp+1A0h+var_30]
0x18002dcc9  xor     rcx, rsp; StackCookie
0x18002dccc  call    __security_check_cookie
0x18002dcd1  add     rsp, 280h
0x18002dcd8  pop     r14
0x18002dcda  pop     rdi
0x18002dcdb  pop     rsi
0x18002dcdc  pop     rbx
0x18002dcdd  pop     rbp
0x18002dcde  retn
```
