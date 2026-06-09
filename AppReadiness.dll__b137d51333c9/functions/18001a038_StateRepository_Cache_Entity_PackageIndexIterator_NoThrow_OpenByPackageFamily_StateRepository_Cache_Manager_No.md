# StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x18001a038`
- end: `0x18001a59c`
- name: `?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `1380`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180019ff0`

## callees

- `0x18001a038`
- `0x180030914`
- `0x18003e210`
- `0x18003eca8`
- `0x180075b58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18001a14d`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18001a14d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18001a4dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18001a4dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001a298`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001a298`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001a0c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001a0c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a088`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a0e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a2bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a322`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a448`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a088`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a0e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a2bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a322`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001a448`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a51b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a53d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a591`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a51b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a53d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a591`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001a369`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001a369`

## string_xrefs

- `0x18001a3a3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18001a4f5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18001a2f1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001a3ed`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001a408`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001a2d1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001a380`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001a3cd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(
        StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned __int64 v11; // r15
  _WORD *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // r14
  char *v17; // rdi
  __int64 v18; // r9
  unsigned __int64 v19; // r8
  _WORD *v20; // rax
  unsigned __int64 v21; // rax
  _WORD *v22; // rcx
  char *v23; // r8
  unsigned __int64 j; // rdx
  char *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  char *v28; // rcx
  __int64 v29; // rcx
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rdx
  char *v34; // rcx
  __int64 v35; // rcx
  char *v36; // rcx
  char *v37; // rax
  char *v38; // rcx
  unsigned __int64 v39; // r8
  _WORD *i; // rdx
  int v41[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v42; // [rsp+28h] [rbp-D8h]
  __int64 v43; // [rsp+30h] [rbp-D0h] BYREF
  char v44; // [rsp+38h] [rbp-C8h]
  char *v45; // [rsp+40h] [rbp-C0h]
  _BYTE v46[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v47; // [rsp+248h] [rbp+148h]
  unsigned __int64 v48; // [rsp+250h] [rbp+150h]
  void *Src; // [rsp+258h] [rbp+158h]
  _BYTE v50[40]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  if ( !a3 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x792,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)0x80070057LL,
      v41[0]);
    return v8;
  }
  v6 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v6 )
    SRCacheContext_Close(v6);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  v42 = v41;
  *(_QWORD *)v41 = 0;
  v43 = 0;
  v44 = 1;
  v8 = SRCacheContext_Open(v7, L"Package\\Index\\PackageFamily", 0, &v43);
  if ( v44 )
  {
    v9 = *(_QWORD *)v42;
    *(_QWORD *)v42 = v43;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v8,
      v41[0]);
    v33 = 1944;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v8,
      v41[0]);
LABEL_40:
    v29 = *(_QWORD *)v41;
    *(_QWORD *)v41 = 0;
    if ( v29 )
      SRCacheContext_Close(v29);
    return v8;
  }
  if ( !*(_QWORD *)v41 )
  {
    v8 = -2140733422;
    v33 = 1945;
    goto LABEL_50;
  }
  v45 = 0;
  memset_0(v46, 0, sizeof(v46));
  v47 = 0;
  v48 = 256;
  Src = v46;
  if ( (unsigned int)_o__ui64tow_s(a3, v50, 17) )
  {
    v8 = -2147418113;
    v32 = 358;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)v8,
      v41[0]);
    v27 = 1948;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v8,
      v41[0]);
    v28 = v45;
    v45 = 0;
    if ( v28 )
      SRCache_Free();
    goto LABEL_40;
  }
  v11 = 0;
  v12 = v50;
  v13 = 0;
  while ( *v12 )
  {
    if ( ++v11 >= 0x7FFFFFFF )
    {
      v8 = -2147024809;
      v32 = 309;
      goto LABEL_48;
    }
    if ( *v12 == 94 )
      ++v13;
    ++v12;
  }
  v14 = v47;
  v15 = v48;
  v16 = v11 + v13 + v47 + 1;
  if ( v16 > v48 )
  {
    v37 = (char *)SRCache_AllocStringBuffer((unsigned int)v16, v48, v10, 94);
    v17 = v37;
    if ( !v37 )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x8007000ELL,
        v41[0]);
      v32 = 310;
      goto LABEL_48;
    }
    memcpy_0(v37, Src, 2 * v48);
    v36 = v45;
    v45 = v17;
    if ( v36 )
    {
      SRCache_Free();
      v17 = v45;
    }
    v14 = v47;
    v15 = v16;
    v48 = v16;
    Src = v17;
  }
  else
  {
    v17 = (char *)Src;
  }
  if ( v13 )
  {
    v38 = &v17[2 * v14];
    v39 = 0;
    for ( i = v50; v39 < v11; v38 += 2 )
    {
      if ( *i == 94 )
      {
        *(_WORD *)v38 = 94;
        v38 += 2;
      }
      ++v39;
      *(_WORD *)v38 = *i++;
    }
    *(_WORD *)v38 = 0;
    goto LABEL_33;
  }
  v18 = 2147483646;
  if ( v15 - 1 > 0x7FFFFFFE )
  {
    v8 = -2147024809;
LABEL_47:
    v32 = 313;
    goto LABEL_48;
  }
  v19 = v15;
  v20 = v17;
  do
  {
    if ( !*v20 )
      break;
    ++v20;
    --v19;
  }
  while ( v19 );
  v8 = v19 == 0 ? 0x80070057 : 0;
  if ( v19 )
    v21 = v15 - v19;
  else
    v21 = 0;
  if ( !v19 )
    goto LABEL_47;
  v22 = v50;
  v23 = &v17[2 * v21];
  for ( j = v15 - v21; j; --j )
  {
    if ( !v18 )
      break;
    if ( !*v22 )
      break;
    *(_WORD *)v23 = *v22++;
    v23 += 2;
    --v18;
  }
  v25 = v23 - 2;
  v8 = j == 0 ? 0x8007007A : 0;
  if ( j )
    v25 = v23;
  *(_WORD *)v25 = 0;
  if ( !j )
    goto LABEL_47;
LABEL_33:
  v47 += v11;
  v42 = (int *)this;
  v43 = 0;
  v44 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v41, Src, 0, &v43);
  if ( v44 )
  {
    v26 = *(_QWORD *)v42;
    *(_QWORD *)v42 = v43;
    if ( v26 )
      SRCacheContext_Close(v26);
  }
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v8,
      v41[0]);
    v27 = 1951;
    goto LABEL_38;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v31 = SRCacheContext_AddToCache(*(_QWORD *)v41, L"Package\\Index\\PackageFamily");
  v8 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v31,
      v41[0]);
    v27 = 1957;
    goto LABEL_38;
  }
  v34 = v45;
  v45 = 0;
  if ( v34 )
    SRCache_Free();
  v35 = *(_QWORD *)v41;
  *(_QWORD *)v41 = 0;
  if ( v35 )
    SRCacheContext_Close(v35);
  return 0;
}

```

## disassembly

```asm
0x18001a038  mov     [rsp-8+arg_18], rbx
0x18001a03d  push    rbp
0x18001a03e  push    rsi
0x18001a03f  push    rdi
0x18001a040  push    r12
0x18001a042  push    r13
0x18001a044  push    r14
0x18001a046  push    r15
0x18001a048  lea     rbp, [rsp-190h]
0x18001a050  sub     rsp, 290h
0x18001a057  mov     rax, cs:__security_cookie
0x18001a05e  xor     rax, rsp
0x18001a061  mov     [rbp+1C0h+var_38], rax
0x18001a068  xor     r13d, r13d
0x18001a06b  mov     rdi, r8
0x18001a06e  mov     r12, rdx
0x18001a071  mov     rsi, rcx
0x18001a074  test    r8, r8
0x18001a077  jz      loc_18001A401
0x18001a07d  mov     rcx, [rcx]
0x18001a080  mov     [rsi], r13
0x18001a083  test    rcx, rcx
0x18001a086  jz      short loc_18001A08E
0x18001a088  call    cs:__imp_SRCacheContext_Close
0x18001a08e  mov     [rsi+8], r13d
0x18001a092  lea     rax, [rsp+2C0h+var_2A0]
0x18001a097  mov     [rsi+10h], r13
0x18001a09b  lea     r9, [rsp+2C0h+var_290]
0x18001a0a0  mov     rcx, [r12]
0x18001a0a4  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x18001a0ab  xor     r8d, r8d
0x18001a0ae  mov     [rsp+2C0h+var_298], rax
0x18001a0b3  mov     qword ptr [rsp+2C0h+var_2A0], r13; int
0x18001a0b8  mov     [rsp+2C0h+var_290], r13
0x18001a0bd  mov     [rsp+2C0h+var_288], 1
0x18001a0c2  call    cs:__imp_SRCacheContext_Open
0x18001a0c8  mov     ebx, eax
0x18001a0ca  cmp     [rsp+2C0h+var_288], r13b
0x18001a0cf  jz      short loc_18001A0EC
0x18001a0d1  mov     r8, [rsp+2C0h+var_298]
0x18001a0d6  mov     rdx, [rsp+2C0h+var_290]
0x18001a0db  mov     rcx, [r8]
0x18001a0de  mov     [r8], rdx
0x18001a0e1  test    rcx, rcx
0x18001a0e4  jz      short loc_18001A0EC
0x18001a0e6  call    cs:__imp_SRCacheContext_Close
0x18001a0ec  test    ebx, ebx
0x18001a0ee  js      loc_18001A3C6
0x18001a0f4  cmp     qword ptr [rsp+2C0h+var_2A0], r13
0x18001a0f9  setnz   al
0x18001a0fc  test    al, al
0x18001a0fe  jz      loc_18001A4A4
0x18001a104  xor     edx, edx; Val
0x18001a106  mov     [rsp+2C0h+var_280], r13
0x18001a10b  mov     r8d, 200h; Size
0x18001a111  lea     rcx, [rsp+2C0h+var_278]; void *
0x18001a116  call    memset_0
0x18001a11b  mov     r9d, 10h
0x18001a121  mov     [rbp+1C0h+var_78], r13
0x18001a128  lea     rax, [rsp+2C0h+var_278]
0x18001a12d  mov     [rbp+1C0h+var_70], 100h
0x18001a138  lea     rdx, [rbp+1C0h+var_60]
0x18001a13f  mov     [rbp+1C0h+Src], rax
0x18001a146  mov     rcx, rdi
0x18001a149  lea     r8d, [r9+1]
0x18001a14d  call    cs:__imp__o__ui64tow_s
0x18001a153  test    eax, eax
0x18001a155  jnz     loc_18001A4B3
0x18001a15b  mov     r15, r13
0x18001a15e  lea     rax, [rbp+1C0h+var_60]
0x18001a165  mov     rbx, r13
0x18001a168  mov     r9d, 5Eh ; '^'
0x18001a16e  cmp     [rax], r13w
0x18001a172  jz      short loc_18001A194
0x18001a174  inc     r15
0x18001a177  cmp     r15, 7FFFFFFFh
0x18001a17e  jnb     loc_18001A4CA
0x18001a184  cmp     [rax], r9w
0x18001a188  jz      loc_18001A4C2
0x18001a18e  add     rax, 2
0x18001a192  jmp     short loc_18001A16E
0x18001a194  mov     rcx, [rbp+1C0h+var_78]
0x18001a19b  mov     rdx, [rbp+1C0h+var_70]
0x18001a1a2  lea     r14, [rcx+1]
0x18001a1a6  add     r14, rbx
0x18001a1a9  add     r14, r15
0x18001a1ac  cmp     r14, rdx
0x18001a1af  ja      loc_18001A4D9
0x18001a1b5  mov     rdi, [rbp+1C0h+Src]
0x18001a1bc  test    rbx, rbx
0x18001a1bf  jnz     loc_18001A548
0x18001a1c5  lea     rax, [rdx-1]
0x18001a1c9  mov     r9d, 7FFFFFFEh
0x18001a1cf  cmp     rax, r9
0x18001a1d2  ja      loc_18001A533
0x18001a1d8  mov     r8, rdx
0x18001a1db  mov     rax, rdi
0x18001a1de  cmp     [rax], r13w
0x18001a1e2  jz      short loc_18001A1EE
0x18001a1e4  add     rax, 2
0x18001a1e8  sub     r8, 1
0x18001a1ec  jnz     short loc_18001A1DE
0x18001a1ee  mov     rax, r8
0x18001a1f1  mov     ebx, 80070057h
0x18001a1f6  neg     rax
0x18001a1f9  sbb     ecx, ecx
0x18001a1fb  not     ecx
0x18001a1fd  and     ebx, ecx
0x18001a1ff  test    r8, r8
0x18001a202  jz      loc_18001A52B
0x18001a208  mov     rax, rdx
0x18001a20b  sub     rax, r8
0x18001a20e  test    r8, r8
0x18001a211  jz      loc_18001A39E
0x18001a217  lea     rcx, [rbp+1C0h+var_60]
0x18001a21e  lea     r8, [rdi+rax*2]
0x18001a222  sub     rdx, rax
0x18001a225  jz      short loc_18001A249
0x18001a227  test    r9, r9
0x18001a22a  jz      short loc_18001A249
0x18001a22c  movzx   eax, word ptr [rcx]
0x18001a22f  test    ax, ax
0x18001a232  jz      short loc_18001A249
0x18001a234  mov     [r8], ax
0x18001a238  add     rcx, 2
0x18001a23c  add     r8, 2
0x18001a240  dec     r9
0x18001a243  sub     rdx, 1
0x18001a247  jnz     short loc_18001A227
0x18001a249  mov     rax, rdx
0x18001a24c  lea     rcx, [r8-2]
0x18001a250  neg     rax
0x18001a253  sbb     ebx, ebx
0x18001a255  not     ebx
0x18001a257  and     ebx, 8007007Ah
0x18001a25d  test    rdx, rdx
0x18001a260  cmovnz  rcx, r8
0x18001a264  mov     [rcx], r13w
0x18001a268  jz      loc_18001A39E
0x18001a26e  mov     rdx, [rbp+1C0h+Src]
0x18001a275  lea     r9, [rsp+2C0h+var_290]
0x18001a27a  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x18001a27f  xor     r8d, r8d
0x18001a282  add     [rbp+1C0h+var_78], r15
0x18001a289  mov     [rsp+2C0h+var_298], rsi
0x18001a28e  mov     [rsp+2C0h+var_290], r13
0x18001a293  mov     [rsp+2C0h+var_288], 1
0x18001a298  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001a29e  mov     ebx, eax
0x18001a2a0  cmp     [rsp+2C0h+var_288], r13b
0x18001a2a5  jz      short loc_18001A2C2
0x18001a2a7  mov     r8, [rsp+2C0h+var_298]
0x18001a2ac  mov     rdx, [rsp+2C0h+var_290]
0x18001a2b1  mov     rcx, [r8]
0x18001a2b4  mov     [r8], rdx
0x18001a2b7  test    rcx, rcx
0x18001a2ba  jz      short loc_18001A2C2
0x18001a2bc  call    cs:__imp_SRCacheContext_Close
0x18001a2c2  test    ebx, ebx
0x18001a2c4  jns     loc_18001A354
0x18001a2ca  mov     rcx, [rbp+1C8h]; this
0x18001a2d1  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a2d8  mov     r9d, ebx; char *
0x18001a2db  mov     edx, 1B0h; void *
0x18001a2e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a2e5  mov     edx, 79Fh; void *
0x18001a2ea  mov     rcx, [rbp+1C8h]; this
0x18001a2f1  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a2f8  mov     r9d, ebx; char *
0x18001a2fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a300  mov     rcx, [rsp+2C0h+var_280]
0x18001a305  mov     [rsp+2C0h+var_280], r13
0x18001a30a  test    rcx, rcx
0x18001a30d  jnz     loc_18001A53D
0x18001a313  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x18001a318  mov     qword ptr [rsp+2C0h+var_2A0], r13
0x18001a31d  test    rcx, rcx
0x18001a320  jz      short loc_18001A328
0x18001a322  call    cs:__imp_SRCacheContext_Close
0x18001a328  mov     eax, ebx
0x18001a32a  mov     rcx, [rbp+1C0h+var_38]
0x18001a331  xor     rcx, rsp; StackCookie
0x18001a334  call    __security_check_cookie
0x18001a339  mov     rbx, [rsp+2C0h+arg_18]
0x18001a341  add     rsp, 290h
0x18001a348  pop     r15
0x18001a34a  pop     r14
0x18001a34c  pop     r13
0x18001a34e  pop     r12
0x18001a350  pop     rdi
0x18001a351  pop     rsi
0x18001a352  pop     rbp
0x18001a353  retn
0x18001a354  cmp     [rsi], r13
0x18001a357  jnz     loc_18001A588
0x18001a35d  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x18001a362  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x18001a369  call    cs:__imp_SRCacheContext_AddToCache
0x18001a36f  mov     ebx, eax
0x18001a371  test    eax, eax
0x18001a373  jns     loc_18001A426
0x18001a379  mov     rcx, [rbp+1C8h]; this
0x18001a380  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a387  mov     r9d, eax; char *
0x18001a38a  mov     edx, 1A6h; void *
0x18001a38f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a394  mov     edx, 7A5h
0x18001a399  jmp     loc_18001A2EA
0x18001a39e  mov     edx, 139h; void *
0x18001a3a3  lea     rdi, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a3aa  mov     rcx, [rbp+1C8h]; this
0x18001a3b1  mov     r9d, ebx; char *
0x18001a3b4  mov     r8, rdi; unsigned int
0x18001a3b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a3bc  mov     edx, 79Ch
0x18001a3c1  jmp     loc_18001A2EA
0x18001a3c6  mov     rcx, [rbp+1C8h]; this
0x18001a3cd  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a3d4  mov     r9d, ebx; char *
0x18001a3d7  mov     edx, 18Ch; void *
0x18001a3dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a3e1  mov     edx, 798h; void *
0x18001a3e6  mov     rcx, [rbp+1C8h]; this
0x18001a3ed  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a3f4  mov     r9d, ebx; char *
0x18001a3f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a3fc  jmp     loc_18001A313
0x18001a401  mov     rcx, [rbp+1C8h]; this
0x18001a408  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a40f  mov     ebx, 80070057h
0x18001a414  mov     edx, 792h; void *
0x18001a419  mov     r9d, ebx; char *
0x18001a41c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a421  jmp     loc_18001A328
0x18001a426  mov     rcx, [rsp+2C0h+var_280]
0x18001a42b  mov     [rsp+2C0h+var_280], r13
0x18001a430  test    rcx, rcx
0x18001a433  jnz     loc_18001A591
0x18001a439  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x18001a43e  mov     qword ptr [rsp+2C0h+var_2A0], r13
0x18001a443  test    rcx, rcx
0x18001a446  jz      short loc_18001A44E
0x18001a448  call    cs:__imp_SRCacheContext_Close
0x18001a44e  xor     eax, eax
0x18001a450  jmp     loc_18001A32A
0x18001a455  mov     r8, [rbp+1C0h+var_70]
0x18001a45c  mov     rcx, rdi; void *
0x18001a45f  mov     rdx, [rbp+1C0h+Src]; Src
0x18001a466  add     r8, r8; Size
0x18001a469  call    memcpy_0
0x18001a46e  mov     rcx, [rsp+2C0h+var_280]
0x18001a473  mov     [rsp+2C0h+var_280], rdi
0x18001a478  test    rcx, rcx
0x18001a47b  jnz     loc_18001A51B
0x18001a481  mov     rcx, [rbp+1C0h+var_78]
0x18001a488  mov     rdx, r14
0x18001a48b  mov     [rbp+1C0h+var_70], rdx
0x18001a492  mov     r9d, 5Eh ; '^'
0x18001a498  mov     [rbp+1C0h+Src], rdi
0x18001a49f  jmp     loc_18001A1BC
0x18001a4a4  mov     ebx, 80670012h
0x18001a4a9  mov     edx, 799h
0x18001a4ae  jmp     loc_18001A3E6
0x18001a4b3  mov     ebx, 8000FFFFh
0x18001a4b8  mov     edx, 166h
0x18001a4bd  jmp     loc_18001A3A3
0x18001a4c2  inc     rbx
0x18001a4c5  jmp     loc_18001A18E
0x18001a4ca  mov     ebx, 80070057h
0x18001a4cf  mov     edx, 135h
0x18001a4d4  jmp     loc_18001A3A3
0x18001a4d9  mov     ecx, r14d
0x18001a4dc  call    cs:__imp_SRCache_AllocStringBuffer
0x18001a4e2  mov     rdi, rax
0x18001a4e5  test    rax, rax
0x18001a4e8  jnz     loc_18001A455
0x18001a4ee  mov     rcx, [rbp+1C8h]; this
0x18001a4f5  lea     rdi, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001a4fc  mov     ebx, 8007000Eh
0x18001a501  mov     r8, rdi; unsigned int
0x18001a504  mov     r9d, ebx; char *
0x18001a507  mov     edx, 193h; void *
0x18001a50c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a511  mov     edx, 136h
0x18001a516  jmp     loc_18001A3AA
0x18001a51b  call    cs:__imp_SRCache_Free
0x18001a521  mov     rdi, [rsp+2C0h+var_280]
0x18001a526  jmp     loc_18001A481
0x18001a52b  mov     rax, r13
0x18001a52e  jmp     loc_18001A20E
0x18001a533  mov     ebx, 80070057h
0x18001a538  jmp     loc_18001A39E
0x18001a53d  call    cs:__imp_SRCache_Free
0x18001a543  jmp     loc_18001A313
0x18001a548  lea     rcx, [rdi+rcx*2]
0x18001a54c  mov     r8, r13
0x18001a54f  lea     rdx, [rbp+1C0h+var_60]
0x18001a556  test    r15, r15
0x18001a559  jz      short loc_18001A57F
0x18001a55b  cmp     [rdx], r9w
  ... truncated ...
```
