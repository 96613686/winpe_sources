# StateRepository::Cache::Entity::Package_NoThrow::GetByUserAndPackageFullName(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)

- ea: `0x18001afd4`
- end: `0x18001b279`
- name: `?GetByUserAndPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `677`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800514a0`

## callees

- `0x18001a1f0`
- `0x18001a29c`
- `0x18001afd4`
- `0x18001b280`
- `0x18001b308`
- `0x18001b5f8`
- `0x18001b988`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b0b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b23c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b0b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b23c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b109`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b154`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b16f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b18a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b1ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b109`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b154`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b16f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b18a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b1ab`

## string_xrefs

- `0x18001b1e7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001b20e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001b220`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001b24b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 StateRepository::Cache::Entity::Package_NoThrow::GetByUserAndPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        ...)
{
  bool *v3; // rdi
  unsigned int v6; // ebx
  bool *v7; // rsi
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  _QWORD *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28[2]; // [rsp+28h] [rbp-49h] BYREF
  __int64 v29; // [rsp+38h] [rbp-39h]
  __int64 v30; // [rsp+40h] [rbp-31h]
  __int64 v31; // [rsp+48h] [rbp-29h]
  __int64 v32; // [rsp+50h] [rbp-21h]
  __int64 v33; // [rsp+58h] [rbp-19h]
  __int64 v34; // [rsp+60h] [rbp-11h]
  __int128 v35; // [rsp+68h] [rbp-9h]
  int v36; // [rsp+78h] [rbp+7h]
  __int64 v37; // [rsp+80h] [rbp+Fh]
  __int64 v38; // [rsp+88h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+4Fh]
  __int64 v40; // [rsp+E0h] [rbp+6Fh] BYREF
  va_list va; // [rsp+E0h] [rbp+6Fh]
  _QWORD *v42; // [rsp+E8h] [rbp+77h]
  bool *v43; // [rsp+F0h] [rbp+7Fh] BYREF
  va_list va1; // [rsp+F0h] [rbp+7Fh]
  va_list va2; // [rsp+F8h] [rbp+87h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v40 = va_arg(va1, _QWORD);
  v42 = va_arg(va1, _QWORD *);
  va_copy(va2, va1);
  v43 = va_arg(va2, bool *);
  v3 = v43;
  *v43 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8DA,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)0x80070057LL,
      v28[0]);
    return v6;
  }
  v29 = 0;
  *(_OWORD *)v28 = 0;
  v35 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v43 = 0;
  v6 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(a1, a3, (__int64 *)va1);
  if ( (v6 & 0x80000000) != 0 )
  {
    v26 = 1165;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      v28[0]);
    v23 = v6;
    v24 = 2269;
    goto LABEL_28;
  }
  v7 = v43;
  if ( !v43 )
    goto LABEL_9;
  v40 = 0;
  v8 = StateRepository::Cache::Entity::Package_NoThrow::Open(
         a1,
         (unsigned __int64)v43,
         (struct StateRepository::Cache::Context_NoThrow *)va,
         v3);
  v6 = v8;
  if ( v8 < 0 )
  {
    v27 = 1110;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
    v25 = v40;
    v40 = 0;
    if ( v25 )
      SRCacheContext_Close(v25);
    v26 = 1168;
    goto LABEL_32;
  }
  if ( *v3 )
  {
    v8 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject((__int64 *)va, v28, 0, v7);
    v6 = v8;
    if ( v8 < 0 )
    {
      v27 = 1115;
      goto LABEL_29;
    }
  }
  v9 = v40;
  v40 = 0;
  if ( v9 )
    SRCacheContext_Close(v9);
LABEL_9:
  if ( *v3 )
  {
    v10 = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(a1, a2, v28[0], v3);
    v6 = v10;
    if ( v10 >= 0 )
    {
      if ( *v3 )
      {
        v11 = v42;
        *v42 = v28[0];
        v12 = v11[1];
        v13 = v28[1];
        v28[1] = 0;
        v11[1] = v13;
        if ( v12 )
          SRCache_Free(v12);
        v11[2] = v29;
        v11[3] = v30;
        v11[4] = v31;
        v11[5] = v32;
        v11[6] = v33;
        v14 = v11[7];
        v15 = v34;
        v34 = 0;
        v11[7] = v15;
        if ( v14 )
          SRCache_Free(v14);
        v16 = v11[8];
        v17 = v35;
        *(_QWORD *)&v35 = 0;
        v11[8] = v17;
        if ( v16 )
          SRCache_Free(v16);
        v18 = v11[9];
        v19 = *((_QWORD *)&v35 + 1);
        *((_QWORD *)&v35 + 1) = 0;
        v11[9] = v19;
        if ( v18 )
          SRCache_Free(v18);
        *((_DWORD *)v11 + 20) = v36;
        v20 = v11[11];
        v21 = v37;
        v37 = 0;
        v11[11] = v21;
        if ( v20 )
          SRCache_Free(v20);
        v11[12] = v38;
      }
      goto LABEL_23;
    }
    v23 = (unsigned int)v10;
    v24 = 2272;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v23,
      v28[0]);
    goto LABEL_24;
  }
LABEL_23:
  v6 = 0;
LABEL_24:
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v28);
  return v6;
}

```

## disassembly

```asm
0x18001afd4  mov     rax, rsp
0x18001afd7  mov     [rax+8], rbx
0x18001afdb  mov     [rax+10h], rsi
0x18001afdf  mov     [rax+20h], r9
0x18001afe3  push    rbp
0x18001afe4  push    rdi
0x18001afe5  push    r12
0x18001afe7  push    r14
0x18001afe9  push    r15
0x18001afeb  lea     rbp, [rax-4Fh]
0x18001afef  sub     rsp, 90h
0x18001aff6  mov     rdi, [rbp+47h+arg_28]
0x18001affa  xor     r12d, r12d
0x18001affd  mov     rax, r8
0x18001b000  mov     r15, rdx
0x18001b003  mov     r14, rcx
0x18001b006  mov     [rdi], r12b
0x18001b009  test    rdx, rdx
0x18001b00c  jz      loc_18001B1E3
0x18001b012  xorps   xmm0, xmm0
0x18001b015  mov     [rbp+47h+var_80], r12
0x18001b019  lea     r8, [rbp+47h+arg_28]; __int64 *
0x18001b01d  movdqa  xmmword ptr [rbp+47h+var_90], xmm0
0x18001b022  mov     rdx, rax; unsigned __int16 *
0x18001b025  movdqa  [rbp+47h+var_50], xmm0
0x18001b02a  mov     [rbp+47h+var_78], r12
0x18001b02e  mov     [rbp+47h+var_70], r12
0x18001b032  mov     [rbp+47h+var_68], r12
0x18001b036  mov     [rbp+47h+var_60], r12
0x18001b03a  mov     [rbp+47h+var_58], r12
0x18001b03e  mov     [rbp+47h+var_40], r12d
0x18001b042  mov     [rbp+47h+var_38], r12
0x18001b046  mov     [rbp+47h+var_30], r12
0x18001b04a  mov     [rbp+47h+arg_28], r12
0x18001b04e  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18001b053  mov     ebx, eax
0x18001b055  test    eax, eax
0x18001b057  js      loc_18001B264
0x18001b05d  mov     rsi, [rbp+47h+arg_28]
0x18001b061  test    rsi, rsi
0x18001b064  jz      short loc_18001B0BB
0x18001b066  mov     r9, rdi; bool *
0x18001b069  mov     [rbp+47h+arg_18], r12
0x18001b06d  lea     r8, [rbp+47h+arg_18]; struct StateRepository::Cache::Context_NoThrow *
0x18001b071  mov     rdx, rsi; __int64
0x18001b074  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x18001b077  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18001b07c  mov     ebx, eax
0x18001b07e  test    eax, eax
0x18001b080  js      loc_18001B26B
0x18001b086  cmp     [rdi], r12b
0x18001b089  jz      short loc_18001B0A8
0x18001b08b  mov     r9, rsi
0x18001b08e  lea     rdx, [rbp+47h+var_90]
0x18001b092  xor     r8d, r8d
0x18001b095  lea     rcx, [rbp+47h+arg_18]
0x18001b099  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x18001b09e  mov     ebx, eax
0x18001b0a0  test    eax, eax
0x18001b0a2  js      loc_18001B272
0x18001b0a8  mov     rcx, [rbp+47h+arg_18]
0x18001b0ac  mov     [rbp+47h+arg_18], r12
0x18001b0b0  test    rcx, rcx
0x18001b0b3  jz      short loc_18001B0BB
0x18001b0b5  call    cs:__imp_SRCacheContext_Close
0x18001b0bb  cmp     [rdi], r12b
0x18001b0be  jz      loc_18001B1B9
0x18001b0c4  mov     r8, [rbp+47h+var_90]; __int64
0x18001b0c8  mov     r9, rdi; bool *
0x18001b0cb  mov     rdx, r15; __int64
0x18001b0ce  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x18001b0d1  call    ?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x18001b0d6  mov     ebx, eax
0x18001b0d8  test    eax, eax
0x18001b0da  js      loc_18001B202
0x18001b0e0  cmp     [rdi], r12b
0x18001b0e3  jz      loc_18001B1B9
0x18001b0e9  mov     rbx, [rbp+47h+arg_20]
0x18001b0ed  mov     rax, [rbp+47h+var_90]
0x18001b0f1  mov     [rbx], rax
0x18001b0f4  mov     rcx, [rbx+8]
0x18001b0f8  mov     rax, [rbp+47h+var_90+8]
0x18001b0fc  mov     [rbp+47h+var_90+8], r12
0x18001b100  mov     [rbx+8], rax
0x18001b104  test    rcx, rcx
0x18001b107  jz      short loc_18001B10F
0x18001b109  call    cs:__imp_SRCache_Free
0x18001b10f  mov     rax, [rbp+47h+var_80]
0x18001b113  mov     [rbx+10h], rax
0x18001b117  mov     eax, dword ptr [rbp+47h+var_78]
0x18001b11a  mov     [rbx+18h], eax
0x18001b11d  mov     eax, dword ptr [rbp+47h+var_78+4]
0x18001b120  mov     [rbx+1Ch], eax
0x18001b123  mov     eax, dword ptr [rbp+47h+var_70]
0x18001b126  mov     [rbx+20h], eax
0x18001b129  mov     eax, dword ptr [rbp+47h+var_70+4]
0x18001b12c  mov     [rbx+24h], eax
0x18001b12f  mov     rax, [rbp+47h+var_68]
0x18001b133  mov     [rbx+28h], rax
0x18001b137  mov     rax, [rbp+47h+var_60]
0x18001b13b  mov     [rbx+30h], rax
0x18001b13f  mov     rcx, [rbx+38h]
0x18001b143  mov     rax, [rbp+47h+var_58]
0x18001b147  mov     [rbp+47h+var_58], r12
0x18001b14b  mov     [rbx+38h], rax
0x18001b14f  test    rcx, rcx
0x18001b152  jz      short loc_18001B15A
0x18001b154  call    cs:__imp_SRCache_Free
0x18001b15a  mov     rcx, [rbx+40h]
0x18001b15e  mov     rax, qword ptr [rbp+47h+var_50]
0x18001b162  mov     qword ptr [rbp+47h+var_50], r12
0x18001b166  mov     [rbx+40h], rax
0x18001b16a  test    rcx, rcx
0x18001b16d  jz      short loc_18001B175
0x18001b16f  call    cs:__imp_SRCache_Free
0x18001b175  mov     rcx, [rbx+48h]
0x18001b179  mov     rax, qword ptr [rbp+47h+var_50+8]
0x18001b17d  mov     qword ptr [rbp+47h+var_50+8], r12
0x18001b181  mov     [rbx+48h], rax
0x18001b185  test    rcx, rcx
0x18001b188  jz      short loc_18001B190
0x18001b18a  call    cs:__imp_SRCache_Free
0x18001b190  mov     eax, [rbp+47h+var_40]
0x18001b193  mov     [rbx+50h], eax
0x18001b196  mov     rcx, [rbx+58h]
0x18001b19a  mov     rax, [rbp+47h+var_38]
0x18001b19e  mov     [rbp+47h+var_38], r12
0x18001b1a2  mov     [rbx+58h], rax
0x18001b1a6  test    rcx, rcx
0x18001b1a9  jz      short loc_18001B1B1
0x18001b1ab  call    cs:__imp_SRCache_Free
0x18001b1b1  mov     rax, [rbp+47h+var_30]
0x18001b1b5  mov     [rbx+60h], rax
0x18001b1b9  mov     ebx, r12d
0x18001b1bc  lea     rcx, [rbp+47h+var_90]; this
0x18001b1c0  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18001b1c5  lea     r11, [rsp+0B0h+var_20]
0x18001b1cd  mov     eax, ebx
0x18001b1cf  mov     rbx, [r11+30h]
0x18001b1d3  mov     rsi, [r11+38h]
0x18001b1d7  mov     rsp, r11
0x18001b1da  pop     r15
0x18001b1dc  pop     r14
0x18001b1de  pop     r12
0x18001b1e0  pop     rdi
0x18001b1e1  pop     rbp
0x18001b1e2  retn
0x18001b1e3  mov     rcx, [rbp+4Fh]; this
0x18001b1e7  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b1ee  mov     ebx, 80070057h
0x18001b1f3  mov     edx, 8DAh; void *
0x18001b1f8  mov     r9d, ebx; char *
0x18001b1fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b200  jmp     short loc_18001B1C5
0x18001b202  mov     r9d, eax; char *
0x18001b205  mov     edx, 8E0h; void *
0x18001b20a  mov     rcx, [rbp+4Fh]; this
0x18001b20e  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b215  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b21a  jmp     short loc_18001B1BC
0x18001b21c  mov     rcx, [rbp+4Fh]; this
0x18001b220  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b227  mov     r9d, eax; char *
0x18001b22a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b22f  mov     rcx, [rbp+47h+arg_18]
0x18001b233  mov     [rbp+47h+arg_18], r12
0x18001b237  test    rcx, rcx
0x18001b23a  jz      short loc_18001B242
0x18001b23c  call    cs:__imp_SRCacheContext_Close
0x18001b242  mov     edx, 490h; void *
0x18001b247  mov     rcx, [rbp+4Fh]; this
0x18001b24b  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b252  mov     r9d, ebx; char *
0x18001b255  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b25a  mov     r9d, ebx
0x18001b25d  mov     edx, 8DDh
0x18001b262  jmp     short loc_18001B20A
0x18001b264  mov     edx, 48Dh
0x18001b269  jmp     short loc_18001B247
0x18001b26b  mov     edx, 456h; void *
0x18001b270  jmp     short loc_18001B21C
0x18001b272  mov     edx, 45Bh
0x18001b277  jmp     short loc_18001B21C
```
