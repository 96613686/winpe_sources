# StateRepository::Cache::Entity::Package_NoThrow::GetEffectiveLocationByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)

- ea: `0x18002ea40`
- end: `0x18002eefa`
- name: `?GetEffectiveLocationByUserAndPackage@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z`
- size: `1210`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009df60`

## callees

- `0x18002ddc0`
- `0x18002ea40`
- `0x18002efa8`
- `0x18002f708`
- `0x18002f738`
- `0x18002f994`
- `0x18004c240`
- `0x180058768`
- `0x1800cac68`
- `0x1800caea0`
- `0x18012d119`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18002ebf1`
- `ntdll!RtlAllocateHeap` at `0x18002ebf1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ed45`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002edb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ee23`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ee67`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ed45`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002edb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ee23`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ee67`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002ec5d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002ecb9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002eeac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002eeea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002ec5d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002ecb9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002eeac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002eeea`

## string_xrefs

- `0x18002ec9d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002ee82`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002eebd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002ec79`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002ecc4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002edce`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002ede5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002edff`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002ee43`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetEffectiveLocationByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        void **a4)
{
  __int64 v8; // r12
  _WORD *v9; // rdi
  bool v10; // si
  ReservedForLocalUse *v11; // rcx
  int v12; // r14d
  bool v13; // si
  int v14; // eax
  unsigned int v15; // ebx
  unsigned __int64 v16; // rbx
  _WORD *i; // rax
  unsigned __int64 v18; // rbx
  SIZE_T v19; // rsi
  void *Heap; // rax
  _WORD *v21; // rax
  _WORD *v22; // r14
  _WORD *v23; // rcx
  unsigned __int64 v24; // rdx
  void *v25; // rcx
  __int64 v26; // rcx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rdx
  int v32; // eax
  __int64 v33; // r8
  int v34; // eax
  __int64 v35; // r8
  __int64 v36; // rdx
  ReservedForLocalUse *v37; // rcx
  __int64 v38; // rdx
  ReservedForLocalUse *v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  int v42; // [rsp+20h] [rbp-99h]
  int v43; // [rsp+20h] [rbp-99h]
  ReservedForLocalUse *v44; // [rsp+30h] [rbp-89h] BYREF
  __int64 v45; // [rsp+38h] [rbp-81h] BYREF
  __int128 v46; // [rsp+40h] [rbp-79h] BYREF
  __int128 v47; // [rsp+50h] [rbp-69h]
  __int128 v48; // [rsp+60h] [rbp-59h] BYREF
  __int64 v49; // [rsp+70h] [rbp-49h]
  __int64 v50; // [rsp+78h] [rbp-41h]
  __int64 v51; // [rsp+80h] [rbp-39h]
  __int64 v52; // [rsp+88h] [rbp-31h]
  __int64 v53; // [rsp+90h] [rbp-29h]
  _WORD *v54; // [rsp+98h] [rbp-21h]
  __int128 v55; // [rsp+A0h] [rbp-19h]
  int v56; // [rsp+B0h] [rbp-9h]
  __int64 v57; // [rsp+B8h] [rbp-1h]
  __int64 v58; // [rsp+C0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  bool v60; // [rsp+128h] [rbp+6Fh] BYREF

  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(a4);
  v8 = 0;
  v9 = 0;
  v46 = 0;
  v47 = 0;
  if ( !a2 )
    goto LABEL_7;
  v10 = 0;
  v60 = 0;
  if ( !a3 )
  {
    v12 = -2147024809;
    v28 = 225;
    goto LABEL_31;
  }
  v45 = 0;
  v12 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(a1, a2, a3, &v45);
  if ( v12 < 0 )
  {
    v28 = 228;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v12,
      v42);
    v29 = 2297;
    goto LABEL_32;
  }
  v8 = v45;
  if ( !v45 )
    goto LABEL_5;
  v44 = 0;
  v32 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
          a1,
          v45,
          (struct StateRepository::Cache::Context_NoThrow *)&v44,
          &v60);
  v12 = v32;
  if ( v32 < 0 )
  {
    v36 = 164;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v32,
      v42);
    v37 = v44;
    v8 = 0;
    v44 = 0;
    if ( v37 )
      SRCacheContext_Close(v37);
    v28 = 231;
    goto LABEL_31;
  }
  v10 = v60;
  if ( v60 )
  {
    v32 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::ContextToObject(&v44, &v46, v33, v8);
    v12 = v32;
    if ( v32 < 0 )
    {
      v36 = 169;
      goto LABEL_50;
    }
  }
  v11 = v44;
  v8 = 0;
  v44 = 0;
  if ( v11 )
    SRCacheContext_Close(v11);
LABEL_5:
  if ( !v10 || (v9 = (_WORD *)*((_QWORD *)&v47 + 1)) == 0 )
  {
LABEL_7:
    v13 = 0;
    v60 = 0;
    if ( a3 )
    {
      v45 = v8;
      v12 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(a1, 0, a3, &v45);
      if ( v12 < 0 )
      {
        v31 = 228;
      }
      else
      {
        v8 = v45;
        if ( !v45 )
        {
LABEL_10:
          if ( v13 )
            v9 = (_WORD *)*((_QWORD *)&v47 + 1);
          goto LABEL_12;
        }
        v44 = 0;
        v34 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
                a1,
                v45,
                (struct StateRepository::Cache::Context_NoThrow *)&v44,
                &v60);
        v12 = v34;
        if ( v34 < 0 )
        {
          v38 = 164;
        }
        else
        {
          v13 = v60;
          if ( !v60
            || (v34 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::ContextToObject(
                        &v44,
                        &v46,
                        v35,
                        v8),
                v12 = v34,
                v34 >= 0) )
          {
            v11 = v44;
            v8 = 0;
            v44 = 0;
            if ( v11 )
              SRCacheContext_Close(v11);
            goto LABEL_10;
          }
          v38 = 169;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v38,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v34,
          v42);
        v39 = v44;
        v8 = 0;
        v44 = 0;
        if ( v39 )
          SRCacheContext_Close(v39);
        v31 = 231;
      }
    }
    else
    {
      v12 = -2147024809;
      v31 = 225;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v12,
      v42);
    v29 = 2310;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v12,
      v43);
    v30 = *((_QWORD *)&v47 + 1);
    *((_QWORD *)&v47 + 1) = v8;
    if ( v30 )
      SRCache_Free(v30);
    return (unsigned int)v12;
  }
LABEL_12:
  v49 = v8;
  v48 = 0;
  v55 = 0;
  v50 = 0;
  v51 = 0;
  v52 = v8;
  v53 = v8;
  v54 = (_WORD *)v8;
  v56 = v8;
  v57 = v8;
  v58 = v8;
  if ( !v9 )
  {
    v60 = 0;
    v14 = StateRepository::Cache::Entity::Package_NoThrow::Get((__int64 *)a1, a3, 768, (__int64 *)&v48, &v60);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x914,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        (const char *)(unsigned int)v14,
        v42);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v48);
      v40 = *((_QWORD *)&v47 + 1);
      *((_QWORD *)&v47 + 1) = v8;
      if ( v40 )
        SRCache_Free(v40);
      return v15;
    }
    if ( !v60 || (v9 = (_WORD *)v55) == 0 && (v9 = v54) == 0 )
    {
LABEL_27:
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v48);
      v26 = *((_QWORD *)&v47 + 1);
      *((_QWORD *)&v47 + 1) = v8;
      if ( v26 )
        SRCache_Free(v26);
      return 0;
    }
  }
  v16 = v8;
  for ( i = v9; *i; ++v16 )
  {
    if ( v16 >= 0x7FFFFFFF )
      break;
    ++i;
  }
  v18 = v16 + 1;
  v19 = 2 * v18;
  if ( !is_mul_ok(v18, 2u) )
    v19 = -1;
  Heap = ReservedForLocalUse::GetHeap(v11);
  v21 = RtlAllocateHeap(Heap, 0, v19);
  v22 = v21;
  if ( v21 )
  {
    memset_0(v21, 0, v19);
    v23 = v22;
    v24 = v8;
    if ( v18 )
    {
      do
      {
        ++v24;
        *v23++ = *v9++;
      }
      while ( v24 < v18 );
    }
    v25 = *a4;
    *a4 = v22;
    if ( v25 )
      Common::GlobalHeap::Free(v25);
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x929,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
    (const char *)0x8007000ELL,
    v42);
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v48);
  v41 = *((_QWORD *)&v47 + 1);
  *((_QWORD *)&v47 + 1) = v8;
  if ( v41 )
    SRCache_Free(v41);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18002ea40  push    rbp
0x18002ea42  push    rbx
0x18002ea43  push    rsi
0x18002ea44  push    rdi
0x18002ea45  push    r12
0x18002ea47  push    r13
0x18002ea49  push    r14
0x18002ea4b  push    r15
0x18002ea4d  lea     rbp, [rsp-1Fh]
0x18002ea52  sub     rsp, 0D8h
0x18002ea59  mov     r15, rcx
0x18002ea5c  mov     r13, r9
0x18002ea5f  mov     rcx, r9
0x18002ea62  mov     rbx, r8
0x18002ea65  mov     r14, rdx
0x18002ea68  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18002ea6d  xor     r12d, r12d
0x18002ea70  xorps   xmm0, xmm0
0x18002ea73  xorps   xmm1, xmm1
0x18002ea76  mov     edi, r12d
0x18002ea79  movdqu  [rbp+57h+var_D0], xmm0
0x18002ea7e  movdqu  [rbp+57h+var_C0], xmm1
0x18002ea83  test    r14, r14
0x18002ea86  jz      short loc_18002EAD7
0x18002ea88  xor     sil, sil
0x18002ea8b  mov     [rbp+57h+arg_8], sil
0x18002ea8f  test    rbx, rbx
0x18002ea92  jz      loc_18002EDC8
0x18002ea98  lea     r9, [rsp+110h+var_D8]; __int64 *
0x18002ea9d  mov     [rsp+110h+var_D8], r12
0x18002eaa2  mov     r8, rbx; __int64
0x18002eaa5  mov     rdx, r14; __int64
0x18002eaa8  mov     rcx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x18002eaab  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)
0x18002eab0  mov     r14d, eax
0x18002eab3  test    eax, eax
0x18002eab5  js      loc_18002EC79
0x18002eabb  mov     r12, [rsp+110h+var_D8]
0x18002eac0  test    r12, r12
0x18002eac3  jnz     loc_18002ECE6
0x18002eac9  test    sil, sil
0x18002eacc  jz      short loc_18002EAD7
0x18002eace  mov     rdi, qword ptr [rbp+57h+var_C0+8]
0x18002ead2  test    rdi, rdi
0x18002ead5  jnz     short loc_18002EB1F
0x18002ead7  xor     sil, sil
0x18002eada  mov     [rbp+57h+arg_8], sil
0x18002eade  test    rbx, rbx
0x18002eae1  jz      loc_18002EDDF
0x18002eae7  lea     r9, [rsp+110h+var_D8]; __int64 *
0x18002eaec  mov     [rsp+110h+var_D8], r12
0x18002eaf1  mov     r8, rbx; __int64
0x18002eaf4  xor     edx, edx; __int64
0x18002eaf6  mov     rcx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x18002eaf9  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)
0x18002eafe  mov     r14d, eax
0x18002eb01  test    eax, eax
0x18002eb03  js      loc_18002ECC4
0x18002eb09  mov     r12, [rsp+110h+var_D8]
0x18002eb0e  test    r12, r12
0x18002eb11  jnz     loc_18002ED50
0x18002eb17  test    sil, sil
0x18002eb1a  cmovnz  rdi, qword ptr [rbp+57h+var_C0+8]
0x18002eb1f  mov     [rbp+57h+var_A0], r12
0x18002eb23  xorps   xmm0, xmm0
0x18002eb26  movdqa  [rbp+57h+var_B0], xmm0
0x18002eb2b  movdqa  [rbp+57h+var_70], xmm0
0x18002eb30  mov     [rbp+57h+var_98], 0
0x18002eb38  mov     [rbp+57h+var_90], 0
0x18002eb40  mov     [rbp+57h+var_88], r12
0x18002eb44  mov     [rbp+57h+var_80], r12
0x18002eb48  mov     [rbp+57h+var_78], r12
0x18002eb4c  mov     [rbp+57h+var_60], r12d
0x18002eb50  mov     [rbp+57h+var_58], r12
0x18002eb54  mov     [rbp+57h+var_50], r12
0x18002eb58  test    rdi, rdi
0x18002eb5b  jnz     short loc_18002EBA9
0x18002eb5d  lea     rax, [rbp+57h+arg_8]
0x18002eb61  mov     [rbp+57h+arg_8], dil
0x18002eb65  lea     r9, [rbp+57h+var_B0]
0x18002eb69  mov     qword ptr [rsp+110h+var_F0], rax; int
0x18002eb6e  mov     r8d, 300h
0x18002eb74  mov     rdx, rbx
0x18002eb77  mov     rcx, r15
0x18002eb7a  call    ?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18002eb7f  mov     ebx, eax
0x18002eb81  test    eax, eax
0x18002eb83  js      loc_18002EE7E
0x18002eb89  cmp     [rbp+57h+arg_8], dil
0x18002eb8d  jz      loc_18002EC47
0x18002eb93  mov     rdi, qword ptr [rbp+57h+var_70]
0x18002eb97  test    rdi, rdi
0x18002eb9a  jnz     short loc_18002EBA9
0x18002eb9c  mov     rdi, [rbp+57h+var_78]
0x18002eba0  test    rdi, rdi
0x18002eba3  jz      loc_18002EC47
0x18002eba9  cmp     word ptr [rdi], 0
0x18002ebad  mov     rbx, r12
0x18002ebb0  mov     rax, rdi
0x18002ebb3  jz      short loc_18002EBCB
0x18002ebb5  cmp     rbx, 7FFFFFFFh
0x18002ebbc  jnb     short loc_18002EBCB
0x18002ebbe  add     rax, 2
0x18002ebc2  inc     rbx
0x18002ebc5  cmp     word ptr [rax], 0
0x18002ebc9  jnz     short loc_18002EBB5
0x18002ebcb  inc     rbx
0x18002ebce  mov     eax, 2
0x18002ebd3  mul     rbx
0x18002ebd6  mov     rsi, rax
0x18002ebd9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002ebe0  cmovb   rsi, rax
0x18002ebe4  call    ?GetHeap@ReservedForLocalUse@@YAPEAXXZ; ReservedForLocalUse::GetHeap(void)
0x18002ebe9  mov     rcx, rax; HeapHandle
0x18002ebec  mov     r8, rsi; Size
0x18002ebef  xor     edx, edx; Flags
0x18002ebf1  call    cs:__imp_RtlAllocateHeap
0x18002ebf7  mov     r14, rax
0x18002ebfa  test    rax, rax
0x18002ebfd  jz      loc_18002EEB9
0x18002ec03  mov     r8, rsi; Size
0x18002ec06  xor     edx, edx; Val
0x18002ec08  mov     rcx, rax; void *
0x18002ec0b  call    memset_0
0x18002ec10  mov     rcx, r14
0x18002ec13  mov     rdx, r12
0x18002ec16  test    rbx, rbx
0x18002ec19  jz      short loc_18002EC36
0x18002ec1b  nop     dword ptr [rax+rax+00h]
0x18002ec20  movzx   eax, word ptr [rdi]
0x18002ec23  inc     rdx
0x18002ec26  mov     [rcx], ax
0x18002ec29  lea     rcx, [rcx+2]
0x18002ec2d  lea     rdi, [rdi+2]
0x18002ec31  cmp     rdx, rbx
0x18002ec34  jb      short loc_18002EC20
0x18002ec36  mov     rcx, [r13+0]; void *
0x18002ec3a  mov     [r13+0], r14
0x18002ec3e  test    rcx, rcx
0x18002ec41  jnz     loc_18002EDBE
0x18002ec47  lea     rcx, [rbp+57h+var_B0]; this
0x18002ec4b  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002ec50  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x18002ec54  mov     qword ptr [rbp+57h+var_C0+8], r12
0x18002ec58  test    rcx, rcx
0x18002ec5b  jz      short loc_18002EC63
0x18002ec5d  call    cs:__imp_SRCache_Free
0x18002ec63  xor     eax, eax
0x18002ec65  add     rsp, 0D8h
0x18002ec6c  pop     r15
0x18002ec6e  pop     r14
0x18002ec70  pop     r13
0x18002ec72  pop     r12
0x18002ec74  pop     rdi
0x18002ec75  pop     rsi
0x18002ec76  pop     rbx
0x18002ec77  pop     rbp
0x18002ec78  retn
0x18002ec79  lea     rbx, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ec80  mov     edx, 0E4h; void *
0x18002ec85  mov     rcx, [rbp+5Fh]; this
0x18002ec89  mov     r9d, r14d; char *
0x18002ec8c  mov     r8, rbx; unsigned int
0x18002ec8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ec94  mov     edx, 8F9h; void *
0x18002ec99  mov     rcx, [rbp+5Fh]; this
0x18002ec9d  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002eca4  mov     r9d, r14d; char *
0x18002eca7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ecac  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x18002ecb0  mov     qword ptr [rbp+57h+var_C0+8], r12
0x18002ecb4  test    rcx, rcx
0x18002ecb7  jz      short loc_18002ECBF
0x18002ecb9  call    cs:__imp_SRCache_Free
0x18002ecbf  mov     eax, r14d
0x18002ecc2  jmp     short loc_18002EC65
0x18002ecc4  lea     rbx, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002eccb  mov     edx, 0E4h; void *
0x18002ecd0  mov     rcx, [rbp+5Fh]; this
0x18002ecd4  mov     r9d, r14d; char *
0x18002ecd7  mov     r8, rbx; unsigned int
0x18002ecda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ecdf  mov     edx, 906h
0x18002ece4  jmp     short loc_18002EC99
0x18002ece6  lea     r9, [rbp+57h+arg_8]; bool *
0x18002ecea  mov     [rsp+110h+var_E0], rdi
0x18002ecef  lea     r8, [rsp+110h+var_E0]; struct StateRepository::Cache::Context_NoThrow *
0x18002ecf4  mov     rdx, r12; __int64
0x18002ecf7  mov     rcx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x18002ecfa  call    ?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18002ecff  mov     r14d, eax
0x18002ed02  test    eax, eax
0x18002ed04  js      loc_18002EDF6
0x18002ed0a  movzx   esi, [rbp+57h+arg_8]
0x18002ed0e  test    sil, sil
0x18002ed11  jz      short loc_18002ED2F
0x18002ed13  mov     r9, r12
0x18002ed16  lea     rdx, [rbp+57h+var_D0]
0x18002ed1a  lea     rcx, [rsp+110h+var_E0]
0x18002ed1f  call    ?ContextToObject@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,__int64)
0x18002ed24  mov     r14d, eax
0x18002ed27  test    eax, eax
0x18002ed29  js      loc_18002EE33
0x18002ed2f  mov     rcx, [rsp+110h+var_E0]
0x18002ed34  xor     r12d, r12d
0x18002ed37  mov     [rsp+110h+var_E0], r12
0x18002ed3c  test    rcx, rcx
0x18002ed3f  jz      loc_18002EAC9
0x18002ed45  call    cs:__imp_SRCacheContext_Close
0x18002ed4b  jmp     loc_18002EAC9
0x18002ed50  lea     r9, [rbp+57h+arg_8]; bool *
0x18002ed54  mov     [rsp+110h+var_E0], 0
0x18002ed5d  lea     r8, [rsp+110h+var_E0]; struct StateRepository::Cache::Context_NoThrow *
0x18002ed62  mov     rdx, r12; __int64
0x18002ed65  mov     rcx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x18002ed68  call    ?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18002ed6d  mov     r14d, eax
0x18002ed70  test    eax, eax
0x18002ed72  js      loc_18002EE3A
0x18002ed78  movzx   esi, [rbp+57h+arg_8]
0x18002ed7c  test    sil, sil
0x18002ed7f  jz      short loc_18002ED9D
0x18002ed81  mov     r9, r12
0x18002ed84  lea     rdx, [rbp+57h+var_D0]
0x18002ed88  lea     rcx, [rsp+110h+var_E0]
0x18002ed8d  call    ?ContextToObject@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,__int64)
0x18002ed92  mov     r14d, eax
0x18002ed95  test    eax, eax
0x18002ed97  js      loc_18002EE77
0x18002ed9d  mov     rcx, [rsp+110h+var_E0]
0x18002eda2  xor     r12d, r12d
0x18002eda5  mov     [rsp+110h+var_E0], r12
0x18002edaa  test    rcx, rcx
0x18002edad  jz      loc_18002EB17
0x18002edb3  call    cs:__imp_SRCacheContext_Close
0x18002edb9  jmp     loc_18002EB17
0x18002edbe  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18002edc3  jmp     loc_18002EC47
0x18002edc8  mov     r14d, 80070057h
0x18002edce  lea     rbx, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002edd5  mov     edx, 0E1h
0x18002edda  jmp     loc_18002EC85
0x18002eddf  mov     r14d, 80070057h
0x18002ede5  lea     rbx, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002edec  mov     edx, 0E1h
0x18002edf1  jmp     loc_18002ECD0
0x18002edf6  mov     edx, 0A4h; void *
0x18002edfb  mov     rcx, [rbp+5Fh]; this
0x18002edff  lea     rbx, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ee06  mov     r8, rbx; unsigned int
0x18002ee09  mov     r9d, eax; char *
0x18002ee0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ee11  mov     rcx, [rsp+110h+var_E0]
0x18002ee16  xor     r12d, r12d
0x18002ee19  mov     [rsp+110h+var_E0], r12
0x18002ee1e  test    rcx, rcx
0x18002ee21  jz      short loc_18002EE29
0x18002ee23  call    cs:__imp_SRCacheContext_Close
0x18002ee29  mov     edx, 0E7h
0x18002ee2e  jmp     loc_18002EC85
0x18002ee33  mov     edx, 0A9h
0x18002ee38  jmp     short loc_18002EDFB
0x18002ee3a  mov     edx, 0A4h; void *
0x18002ee3f  mov     rcx, [rbp+5Fh]; this
0x18002ee43  lea     rbx, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ee4a  mov     r8, rbx; unsigned int
0x18002ee4d  mov     r9d, eax; char *
0x18002ee50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ee55  mov     rcx, [rsp+110h+var_E0]
0x18002ee5a  xor     r12d, r12d
0x18002ee5d  mov     [rsp+110h+var_E0], r12
0x18002ee62  test    rcx, rcx
0x18002ee65  jz      short loc_18002EE6D
0x18002ee67  call    cs:__imp_SRCacheContext_Close
0x18002ee6d  mov     edx, 0E7h
0x18002ee72  jmp     loc_18002ECD0
0x18002ee77  mov     edx, 0A9h
0x18002ee7c  jmp     short loc_18002EE3F
0x18002ee7e  mov     rcx, [rbp+5Fh]; this
0x18002ee82  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ee89  mov     r9d, ebx; char *
0x18002ee8c  mov     edx, 914h; void *
0x18002ee91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ee96  lea     rcx, [rbp+57h+var_B0]; this
0x18002ee9a  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002ee9f  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x18002eea3  mov     qword ptr [rbp+57h+var_C0+8], r12
0x18002eea7  test    rcx, rcx
0x18002eeaa  jz      short loc_18002EEB2
0x18002eeac  call    cs:__imp_SRCache_Free
0x18002eeb2  mov     eax, ebx
0x18002eeb4  jmp     loc_18002EC65
0x18002eeb9  mov     rcx, [rbp+5Fh]; this
0x18002eebd  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002eec4  mov     r9d, 8007000Eh; char *
0x18002eeca  mov     edx, 929h; void *
0x18002eecf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002eed4  lea     rcx, [rbp+57h+var_B0]; this
0x18002eed8  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002eedd  mov     rcx, qword ptr [rbp+57h+var_C0+8]
  ... truncated ...
```
