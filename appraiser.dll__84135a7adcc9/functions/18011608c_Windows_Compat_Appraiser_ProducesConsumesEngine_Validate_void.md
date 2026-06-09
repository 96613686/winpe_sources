# Windows::Compat::Appraiser::ProducesConsumesEngine::Validate(void)

- ea: `0x18011608c`
- end: `0x18011669d`
- name: `?Validate@ProducesConsumesEngine@Appraiser@Compat@Windows@@QEAAJXZ`
- size: `1553`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::ProducesConsumesEngine *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18011562c`

## callees

- `0x18001a32c`
- `0x18002993c`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180115fdc`
- `0x18011608c`
- `0x180117f30`
- `0x180118184`
- `0x1801187c8`
- `0x180118ab8`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1801160c3`
- `KERNEL32!GetProcessHeap` at `0x1801160f4`
- `KERNEL32!GetProcessHeap` at `0x18011611b`
- `KERNEL32!GetProcessHeap` at `0x1801160c3`
- `KERNEL32!GetProcessHeap` at `0x1801160f4`
- `KERNEL32!GetProcessHeap` at `0x18011611b`
- `KERNEL32!HeapFree` at `0x180116590`
- `KERNEL32!HeapFree` at `0x1801165a6`
- `KERNEL32!HeapFree` at `0x1801165bc`
- `KERNEL32!HeapFree` at `0x180116590`
- `KERNEL32!HeapFree` at `0x1801165a6`
- `KERNEL32!HeapFree` at `0x1801165bc`

## string_xrefs

- `0x1801161bf`: `onecore\base\appcompat\appraiser\producesconsumes\producesconsumesengine.cpp`
- `0x18011624f`: `onecore\base\appcompat\appraiser\producesconsumes\producesconsumesengine.cpp`
- `0x18011628c`: `onecore\base\appcompat\appraiser\producesconsumes\producesconsumesengine.cpp`
- `0x1801162b2`: `onecore\base\appcompat\appraiser\producesconsumes\producesconsumesengine.cpp`
- `0x180116300`: `onecore\base\appcompat\appraiser\producesconsumes\producesconsumesengine.cpp`
- `0x18011638b`: `onecore\base\appcompat\appraiser\producesconsumes\producesconsumesengine.cpp`
- `0x1801163c8`: `onecore\base\appcompat\appraiser\producesconsumes\producesconsumesengine.cpp`
- `0x180116415`: `onecore\base\appcompat\appraiser\producesconsumes\producesconsumesengine.cpp`
- `0x18011655f`: `onecore\base\appcompat\appraiser\producesconsumes\producesconsumesengine.cpp`
- `0x18011668b`: `onecore\base\appcompat\appraiser\producesconsumes\producesconsumesengine.cpp`
- `0x1801161b8`: `Windows::Compat::Appraiser::ProducesConsumesEngine::Validate`
- `0x180116248`: `Windows::Compat::Appraiser::ProducesConsumesEngine::Validate`
- `0x180116285`: `Windows::Compat::Appraiser::ProducesConsumesEngine::Validate`
- `0x1801162ab`: `Windows::Compat::Appraiser::ProducesConsumesEngine::Validate`
- `0x1801162f9`: `Windows::Compat::Appraiser::ProducesConsumesEngine::Validate`
- `0x180116384`: `Windows::Compat::Appraiser::ProducesConsumesEngine::Validate`
- `0x1801163c1`: `Windows::Compat::Appraiser::ProducesConsumesEngine::Validate`
- `0x18011640e`: `Windows::Compat::Appraiser::ProducesConsumesEngine::Validate`
- `0x180116558`: `Windows::Compat::Appraiser::ProducesConsumesEngine::Validate`
- `0x180116684`: `Windows::Compat::Appraiser::ProducesConsumesEngine::Validate`
- `0x1801164cc`: `Failed ValidateComponentConsumes: [0x%x].`
- `0x1801165e9`: `Failed ValidateComponentConsumes: [0x%x].`
- `0x18011643c`: `Failed ValidateComponentProduces: [0x%x].`
- `0x18011650e`: `Failed ValidateComponentProduces: [0x%x].`
- `0x180116435`: `onecore\base\appcompat\appraiser\producesconsumes\layer.cpp`
- `0x1801164bc`: `Windows::Compat::Appraiser::Layer::Validate`
- `0x1801165f6`: `Windows::Compat::Appraiser::Layer::Validate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Appraiser::ProducesConsumesEngine::Validate(
        Windows::Compat::Appraiser::ProducesConsumesEngine *this)
{
  unsigned __int64 *v1; // rdi
  unsigned __int64 v2; // r12
  _QWORD *v3; // rax
  unsigned int v4; // esi
  __int64 v5; // rcx
  int v6; // eax
  int v7; // ebx
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // rsi
  __int64 *v10; // rax
  __int64 v11; // r14
  int v12; // eax
  int AllProduced; // eax
  unsigned __int64 i; // rsi
  unsigned __int64 v15; // rax
  __int64 *v16; // rdx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rcx
  __int64 v19; // r14
  int AllConsumed; // eax
  unsigned __int64 v21; // r15
  unsigned __int64 v22; // rax
  __int64 v23; // r14
  __int64 v24; // rcx
  int v25; // eax
  int v26; // esi
  int v28; // ecx
  int v29; // edx
  const char *v30; // rax
  char v31; // dl
  char *v32; // [rsp+20h] [rbp-A9h]
  char *v33; // [rsp+20h] [rbp-A9h]
  char *v34; // [rsp+30h] [rbp-99h]
  char *v35; // [rsp+30h] [rbp-99h]
  HANDLE hHeap[2]; // [rsp+40h] [rbp-89h] BYREF
  __int128 v37; // [rsp+50h] [rbp-79h]
  LPVOID lpMem[2]; // [rsp+60h] [rbp-69h]
  HANDLE v39[2]; // [rsp+70h] [rbp-59h] BYREF
  __int128 v40; // [rsp+80h] [rbp-49h]
  LPVOID v41[2]; // [rsp+90h] [rbp-39h]
  HANDLE v42[2]; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v43; // [rsp+B0h] [rbp-19h]
  LPVOID v44[2]; // [rsp+C0h] [rbp-9h]
  __int64 v45; // [rsp+D0h] [rbp+7h]
  Windows::Compat::Appraiser::ProducesConsumesEngine *v46; // [rsp+130h] [rbp+67h] BYREF
  const char *v47; // [rsp+138h] [rbp+6Fh] BYREF
  __int64 v48; // [rsp+140h] [rbp+77h]
  unsigned __int64 v49; // [rsp+148h] [rbp+7Fh]

  v46 = this;
  v45 = -2;
  v1 = (unsigned __int64 *)Windows::Compat::Appraiser::ProducesConsumesFactory::ValidationEngine;
  v39[0] = GetProcessHeap();
  v41[0] = (LPVOID)16;
  v40 = 0;
  v2 = 0;
  v41[1] = 0;
  v39[1] = (HANDLE)8;
  v42[0] = GetProcessHeap();
  v44[0] = (LPVOID)16;
  v43 = 0;
  v44[1] = 0;
  v42[1] = (HANDLE)8;
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v37 = 0;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)8;
  v3 = (_QWORD *)*v1;
  if ( *(_DWORD *)(*v1 + 64) )
  {
    v4 = 0;
    do
    {
      v5 = *(_QWORD *)(*v3 + 8LL * v4);
      v47 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
      v46 = 0;
      if ( !(unsigned __int8)Windows::Compat::Shared::Generics::OrderedArray<unsigned short const *,&public: static int Windows::Compat::Shared::Generics::Compare::String(unsigned short const * const &,unsigned short const * const &)>::Find(
                               v39,
                               &v46,
                               &v47) )
      {
        v6 = RtlArray<unsigned __int64>::Insert(v39, &v47, v46);
        v7 = v6;
        if ( v6 < 0 )
        {
          LODWORD(v32) = v6;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            92,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\producesconsumes\\producesconsumesengine.cpp",
            "Windows::Compat::Appraiser::ProducesConsumesEngine::Validate",
            v32,
            (int)"Failed Add Metadata",
            v34);
          goto LABEL_55;
        }
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x5Cu,
          "onecore\\base\\appcompat\\appraiser\\producesconsumes\\producesconsumesengine.cpp",
          "Windows::Compat::Appraiser::ProducesConsumesEngine::Validate",
          "Failed Add Metadata");
      ++v4;
      v3 = (_QWORD *)*v1;
    }
    while ( v4 < *(_DWORD *)(*v1 + 64) );
  }
  v8 = v1[3];
  v49 = v8;
  v9 = 0;
  if ( !v8 )
  {
LABEL_54:
    v7 = 0;
    goto LABEL_55;
  }
  do
  {
    v10 = 0;
    if ( v9 < v1[3] )
    {
      v46 = 0;
      if ( !is_mul_ok(v1[2], v9) || (v10 = (__int64 *)(v1[6] + v1[2] * v9), (unsigned __int64)v10 < v1[6]) )
        v10 = 0;
    }
    v11 = *v10;
    v12 = Windows::Compat::Shared::Generics::Set<unsigned short const *,&public: static int Windows::Compat::Shared::Generics::Compare::String(unsigned short const * const &,unsigned short const * const &)>::UnionWith(
            *v10 + 200,
            v39);
    v7 = v12;
    if ( v12 < 0 )
    {
      v30 = "Failed SetAllowedToConsume: [0x%x]";
      v31 = 106;
      goto LABEL_69;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x6Au,
        "onecore\\base\\appcompat\\appraiser\\producesconsumes\\producesconsumesengine.cpp",
        "Windows::Compat::Appraiser::ProducesConsumesEngine::Validate",
        "Failed SetAllowedToConsume: [0x%x]",
        v12);
    AllProduced = Windows::Compat::Appraiser::Layer::GetAllProduced(v11, hHeap);
    if ( AllProduced < 0 )
    {
      LODWORD(v34) = AllProduced;
      LODWORD(v32) = AllProduced;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        111,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\producesconsumes\\producesconsumesengine.cpp",
        "Windows::Compat::Appraiser::ProducesConsumesEngine::Validate",
        v32,
        (int)"Failed GetAllProduced: [0x%x].",
        v34);
      goto LABEL_22;
    }
    v7 = Windows::Compat::Shared::Generics::Set<unsigned short const *,&public: static int Windows::Compat::Shared::Generics::Compare::String(unsigned short const * const &,unsigned short const * const &)>::UnionWith(
           v39,
           hHeap);
    if ( v7 < 0 )
    {
      v30 = "Failed UnionWith: [0x%x]";
      v31 = 116;
LABEL_69:
      LODWORD(v34) = v7;
      LODWORD(v32) = v7;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v31,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\producesconsumes\\producesconsumesengine.cpp",
        "Windows::Compat::Appraiser::ProducesConsumesEngine::Validate",
        v32,
        (int)v30,
        v34);
      goto LABEL_55;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x74u,
        "onecore\\base\\appcompat\\appraiser\\producesconsumes\\producesconsumesengine.cpp",
        "Windows::Compat::Appraiser::ProducesConsumesEngine::Validate",
        "Failed UnionWith: [0x%x]",
        v7);
LABEL_22:
    ++v9;
  }
  while ( v9 < v8 );
  for ( i = 0; i < v8; ++i )
  {
    v15 = v8 - i - 1;
    v16 = 0;
    if ( v15 < v1[3] )
    {
      v46 = 0;
      v17 = v1[2] * v15;
      if ( !is_mul_ok(v1[2], v8 - i - 1) || (v18 = v1[6], v16 = (__int64 *)(v17 + v18), v17 + v18 < v18) )
        v16 = 0;
    }
    v19 = *v16;
    v7 = Windows::Compat::Shared::Generics::Set<unsigned short const *,&public: static int Windows::Compat::Shared::Generics::Compare::String(unsigned short const * const &,unsigned short const * const &)>::UnionWith(
           *v16 + 152,
           v42);
    if ( v7 < 0 )
    {
      v30 = "Failed SetAllowedToProduce: [0x%x]";
      v31 = 0x80;
      goto LABEL_69;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x80u,
        "onecore\\base\\appcompat\\appraiser\\producesconsumes\\producesconsumesengine.cpp",
        "Windows::Compat::Appraiser::ProducesConsumesEngine::Validate",
        "Failed SetAllowedToProduce: [0x%x]",
        v7);
    AllConsumed = Windows::Compat::Appraiser::Layer::GetAllConsumed(v19, hHeap);
    if ( AllConsumed >= 0 )
    {
      v7 = Windows::Compat::Shared::Generics::Set<unsigned short const *,&public: static int Windows::Compat::Shared::Generics::Compare::String(unsigned short const * const &,unsigned short const * const &)>::UnionWith(
             v42,
             hHeap);
      if ( v7 < 0 )
      {
        v30 = "Failed UnionWith: [0x%x]";
        v31 = -118;
        goto LABEL_69;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x8Au,
          "onecore\\base\\appcompat\\appraiser\\producesconsumes\\producesconsumesengine.cpp",
          "Windows::Compat::Appraiser::ProducesConsumesEngine::Validate",
          "Failed UnionWith: [0x%x]",
          v7);
    }
    else
    {
      LODWORD(v34) = AllConsumed;
      LODWORD(v32) = AllConsumed;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        133,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\producesconsumes\\producesconsumesengine.cpp",
        "Windows::Compat::Appraiser::ProducesConsumesEngine::Validate",
        v32,
        (int)"Failed GetAllConsumed: [0x%x].",
        v34);
    }
  }
  v21 = 0;
  v47 = "Failed ValidateComponentProduces: [0x%x].";
  LODWORD(v46) = 81;
  while ( 1 )
  {
    v22 = 0;
    if ( v21 < v1[3] )
    {
      v48 = 0;
      if ( !is_mul_ok(v1[2], v21) || (v22 = v1[6] + v1[2] * v21, v22 < v1[6]) )
        v22 = 0;
    }
    v23 = *(_QWORD *)v22;
    if ( *(_DWORD *)(*(_QWORD *)v22 + 16LL) )
      break;
LABEL_51:
    v2 = 0;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x96u,
        "onecore\\base\\appcompat\\appraiser\\producesconsumes\\producesconsumesengine.cpp",
        "Windows::Compat::Appraiser::ProducesConsumesEngine::Validate",
        "Failed Validate: [0x%x]",
        0);
    if ( ++v21 >= v49 )
      goto LABEL_54;
  }
  v24 = v23 + 200;
  while ( 1 )
  {
    v48 = *(_QWORD *)(*(_QWORD *)(v23 + 8) + 8 * v2);
    v25 = Windows::Compat::Appraiser::Layer::ValidateComponentConsumes(v23, v48, v24);
    v26 = v25;
    v7 = v25;
    if ( v25 < 0 )
      break;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x4Eu,
        "onecore\\base\\appcompat\\appraiser\\producesconsumes\\layer.cpp",
        "Windows::Compat::Appraiser::Layer::Validate",
        "Failed ValidateComponentConsumes: [0x%x].",
        v25);
    v26 = Windows::Compat::Appraiser::Layer::ValidateComponentProduces(v23, v48, v23 + 152);
    if ( v26 < 0 )
    {
      v7 = v26;
      v28 = v26;
      v29 = v26;
      goto LABEL_64;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x51u,
        "onecore\\base\\appcompat\\appraiser\\producesconsumes\\layer.cpp",
        "Windows::Compat::Appraiser::Layer::Validate",
        "Failed ValidateComponentProduces: [0x%x].",
        v26);
    ++v2;
    v24 = v23 + 200;
    if ( v2 >= *(unsigned int *)(v23 + 16) )
      goto LABEL_51;
  }
  LODWORD(v46) = 78;
  v28 = v25;
  v47 = "Failed ValidateComponentConsumes: [0x%x].";
  v29 = v25;
LABEL_64:
  LODWORD(v34) = v29;
  LODWORD(v32) = v28;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    (bool)v46,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\producesconsumes\\layer.cpp",
    "Windows::Compat::Appraiser::Layer::Validate",
    v32,
    (int)v47,
    v34);
  LODWORD(v35) = v26;
  LODWORD(v33) = v26;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    150,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\producesconsumes\\producesconsumesengine.cpp",
    "Windows::Compat::Appraiser::ProducesConsumesEngine::Validate",
    v33,
    (int)"Failed Validate: [0x%x]",
    v35);
LABEL_55:
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  if ( v44[1] )
    HeapFree(v42[0], 0, v44[1]);
  if ( v41[1] )
    HeapFree(v39[0], 0, v41[1]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18011608c  mov     [rsp-8+arg_0], rcx
0x180116091  push    rbp
0x180116092  push    rbx
0x180116093  push    rsi
0x180116094  push    rdi
0x180116095  push    r12
0x180116097  push    r13
0x180116099  push    r14
0x18011609b  push    r15
0x18011609d  lea     rbp, [rsp-1Fh]
0x1801160a2  sub     rsp, 0E8h
0x1801160a9  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x1801160b1  mov     rdi, cs:?ValidationEngine@ProducesConsumesFactory@Appraiser@Compat@Windows@@0PEAVProducesConsumesEngine@234@EA; Windows::Compat::Appraiser::ProducesConsumesEngine * Windows::Compat::Appraiser::ProducesConsumesFactory::ValidationEngine
0x1801160b8  xorps   xmm0, xmm0
0x1801160bb  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x1801160bf  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x1801160c3  call    cs:__imp_GetProcessHeap
0x1801160c9  mov     [rbp+57h+var_B0], rax
0x1801160cd  mov     esi, 10h
0x1801160d2  mov     [rbp+57h+var_90], rsi
0x1801160d6  xorps   xmm0, xmm0
0x1801160d9  movdqu  [rbp+57h+var_A0], xmm0
0x1801160de  xor     r12d, r12d
0x1801160e1  mov     [rbp+57h+var_90+8], r12
0x1801160e5  lea     ebx, [rsi-8]
0x1801160e8  mov     [rbp+57h+var_B0+8], rbx
0x1801160ec  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x1801160f0  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1801160f4  call    cs:__imp_GetProcessHeap
0x1801160fa  mov     [rbp+57h+var_80], rax
0x1801160fe  mov     [rbp+57h+var_60], rsi
0x180116102  xorps   xmm0, xmm0
0x180116105  movdqu  [rbp+57h+var_70], xmm0
0x18011610a  mov     [rbp+57h+var_60+8], r12
0x18011610e  mov     [rbp+57h+var_80+8], rbx
0x180116112  movups  xmmword ptr [rsp+120h+hHeap], xmm0
0x180116117  movups  xmmword ptr [rbp+57h+lpMem], xmm0
0x18011611b  call    cs:__imp_GetProcessHeap
0x180116121  mov     [rsp+120h+hHeap], rax
0x180116126  mov     [rbp+57h+lpMem], rsi
0x18011612a  xorps   xmm0, xmm0
0x18011612d  movdqu  [rbp+57h+var_D0], xmm0
0x180116132  mov     [rbp+57h+lpMem+8], r12
0x180116136  mov     [rsp+120h+hHeap+8], rbx
0x18011613b  mov     rax, [rdi]
0x18011613e  lea     r13d, [rsi-0Fh]
0x180116142  cmp     [rax+40h], r12d
0x180116146  jbe     loc_1801161D9
0x18011614c  mov     esi, r12d
0x18011614f  lea     r15, aFailedAddMetad; "Failed Add Metadata"
0x180116156  lea     r14d, [r12+5Ch]
0x18011615b  mov     ecx, esi
0x18011615d  mov     rax, [rax]
0x180116160  mov     rcx, [rax+rcx*8]
0x180116164  mov     rax, [rcx]
0x180116167  mov     rax, [rax+8]
0x18011616b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116170  mov     [rbp+57h+arg_8], rax
0x180116174  mov     [rbp+57h+arg_0], r12
0x180116178  lea     r8, [rbp+57h+arg_8]
0x18011617c  lea     rdx, [rbp+57h+arg_0]
0x180116180  lea     rcx, [rbp+57h+var_B0]
0x180116184  call    ?Find@?$OrderedArray@PEBG$1?String@Compare@Generics@Shared@Compat@Windows@@SAHAEBQEBG0@Z@Generics@Shared@Compat@Windows@@QEBA_NAEA_KAEBQEBG@Z; Windows::Compat::Shared::Generics::OrderedArray<ushort const *,&Windows::Compat::Shared::Generics::Compare::String(ushort const * const &,ushort const * const &)>::Find(unsigned __int64 &,ushort const * const &)
0x180116189  test    al, al
0x18011618b  jnz     short loc_1801161A8
0x18011618d  mov     r8, [rbp+57h+arg_0]
0x180116191  lea     rdx, [rbp+57h+arg_8]
0x180116195  lea     rcx, [rbp+57h+var_B0]
0x180116199  call    ?Insert@?$RtlArray@_K@@QEAAJAEB_K_K@Z; RtlArray<unsigned __int64>::Insert(unsigned __int64 const &,unsigned __int64)
0x18011619e  mov     ebx, eax
0x1801161a0  test    eax, eax
0x1801161a2  js      loc_1801162A2
0x1801161a8  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801161ae  and     eax, r13d
0x1801161b1  test    al, al
0x1801161b3  jz      short loc_1801161CE
0x1801161b5  mov     r9, r15; char *
0x1801161b8  lea     r8, aWindowsCompatA_161; "Windows::Compat::Appraiser::ProducesCon"...
0x1801161bf  lea     rdx, aOnecoreBaseApp_64; "onecore\\base\\appcompat\\appraiser\\pr"...
0x1801161c6  mov     ecx, r14d; unsigned int
0x1801161c9  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801161ce  add     esi, r13d
0x1801161d1  mov     rax, [rdi]
0x1801161d4  cmp     esi, [rax+40h]
0x1801161d7  jb      short loc_18011615B
0x1801161d9  mov     r15, [rdi+18h]
0x1801161dd  mov     [rbp+57h+arg_18], r15
0x1801161e1  mov     rsi, r12
0x1801161e4  test    r15, r15
0x1801161e7  jz      loc_18011657D
0x1801161ed  mov     rax, r12
0x1801161f0  cmp     rsi, [rdi+18h]
0x1801161f4  jnb     short loc_180116213
0x1801161f6  mov     [rbp+57h+arg_0], r12
0x1801161fa  mov     rax, rsi
0x1801161fd  mul     qword ptr [rdi+10h]
0x180116201  test    rdx, rdx
0x180116204  jnz     short loc_180116210
0x180116206  add     rax, [rdi+30h]
0x18011620a  cmp     rax, [rdi+30h]
0x18011620e  jnb     short loc_180116213
0x180116210  mov     rax, r12
0x180116213  mov     r14, [rax]
0x180116216  lea     rcx, [r14+0C8h]
0x18011621d  lea     rdx, [rbp+57h+var_B0]
0x180116221  call    ?UnionWith@?$Set@PEBG$1?String@Compare@Generics@Shared@Compat@Windows@@SAHAEBQEBG0@Z@Generics@Shared@Compat@Windows@@QEAAJAEBV12345@@Z; Windows::Compat::Shared::Generics::Set<ushort const *,&Windows::Compat::Shared::Generics::Compare::String(ushort const * const &,ushort const * const &)>::UnionWith(Windows::Compat::Shared::Generics::Set<ushort const *,&Windows::Compat::Shared::Generics::Compare::String(ushort const * const &,ushort const * const &)> const &)
0x180116226  mov     ebx, eax
0x180116228  test    eax, eax
0x18011622a  js      loc_180116668
0x180116230  mov     edx, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180116236  and     edx, r13d
0x180116239  test    dl, dl
0x18011623b  jz      short loc_180116260
0x18011623d  mov     dword ptr [rsp+120h+var_100], eax
0x180116241  lea     r9, aFailedSetallow_0; "Failed SetAllowedToConsume: [0x%x]"
0x180116248  lea     r8, aWindowsCompatA_161; "Windows::Compat::Appraiser::ProducesCon"...
0x18011624f  lea     rdx, aOnecoreBaseApp_64; "onecore\\base\\appcompat\\appraiser\\pr"...
0x180116256  mov     ecx, 6Ah ; 'j'; unsigned int
0x18011625b  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180116260  lea     rdx, [rsp+120h+hHeap]
0x180116265  mov     rcx, r14
0x180116268  call    ?GetAllProduced@Layer@Appraiser@Compat@Windows@@QEAAJAEAV?$Set@PEBG$1?String@Compare@Generics@Shared@Compat@Windows@@SAHAEBQEBG0@Z@Generics@Shared@34@@Z; Windows::Compat::Appraiser::Layer::GetAllProduced(Windows::Compat::Shared::Generics::Set<ushort const *,&Windows::Compat::Shared::Generics::Compare::String(ushort const * const &,ushort const * const &)> &)
0x18011626d  test    eax, eax
0x18011626f  jns     short loc_1801162C9
0x180116271  mov     dword ptr [rsp+120h+var_F0], eax; char *
0x180116275  lea     rcx, aFailedGetallpr; "Failed GetAllProduced: [0x%x]."
0x18011627c  mov     qword ptr [rsp+120h+var_F8], rcx; int
0x180116281  mov     dword ptr [rsp+120h+var_100], eax; char *
0x180116285  lea     r9, aWindowsCompatA_161; "Windows::Compat::Appraiser::ProducesCon"...
0x18011628c  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appcompat\\appraiser\\pr"...
0x180116293  mov     edx, 6Fh ; 'o'; bool
0x180116298  mov     ecx, r13d; this
0x18011629b  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801162a0  jmp     short loc_180116311
0x1801162a2  mov     qword ptr [rsp+120h+var_F8], r15; int
0x1801162a7  mov     dword ptr [rsp+120h+var_100], eax; char *
0x1801162ab  lea     r9, aWindowsCompatA_161; "Windows::Compat::Appraiser::ProducesCon"...
0x1801162b2  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appcompat\\appraiser\\pr"...
0x1801162b9  mov     edx, r14d; bool
0x1801162bc  mov     ecx, r13d; this
0x1801162bf  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801162c4  jmp     loc_180116580
0x1801162c9  lea     rdx, [rsp+120h+hHeap]
0x1801162ce  lea     rcx, [rbp+57h+var_B0]
0x1801162d2  call    ?UnionWith@?$Set@PEBG$1?String@Compare@Generics@Shared@Compat@Windows@@SAHAEBQEBG0@Z@Generics@Shared@Compat@Windows@@QEAAJAEBV12345@@Z; Windows::Compat::Shared::Generics::Set<ushort const *,&Windows::Compat::Shared::Generics::Compare::String(ushort const * const &,ushort const * const &)>::UnionWith(Windows::Compat::Shared::Generics::Set<ushort const *,&Windows::Compat::Shared::Generics::Compare::String(ushort const * const &,ushort const * const &)> const &)
0x1801162d7  mov     ebx, eax
0x1801162d9  test    eax, eax
0x1801162db  js      loc_18011665A
0x1801162e1  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801162e7  and     eax, r13d
0x1801162ea  test    al, al
0x1801162ec  jz      short loc_180116311
0x1801162ee  mov     dword ptr [rsp+120h+var_100], ebx
0x1801162f2  lea     r9, aFailedUnionwit; "Failed UnionWith: [0x%x]"
0x1801162f9  lea     r8, aWindowsCompatA_161; "Windows::Compat::Appraiser::ProducesCon"...
0x180116300  lea     rdx, aOnecoreBaseApp_64; "onecore\\base\\appcompat\\appraiser\\pr"...
0x180116307  mov     ecx, 74h ; 't'; unsigned int
0x18011630c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180116311  add     rsi, r13
0x180116314  cmp     rsi, r15
0x180116317  jb      loc_1801161ED
0x18011631d  mov     rsi, r12
0x180116320  mov     rax, r15
0x180116323  sub     rax, rsi
0x180116326  dec     rax
0x180116329  mov     rdx, r12
0x18011632c  cmp     rax, [rdi+18h]
0x180116330  jnb     short loc_18011634F
0x180116332  mov     [rbp+57h+arg_0], r12
0x180116336  mul     qword ptr [rdi+10h]
0x18011633a  test    rdx, rdx
0x18011633d  jnz     short loc_18011634C
0x18011633f  mov     rcx, [rdi+30h]
0x180116343  lea     rdx, [rax+rcx]
0x180116347  cmp     rdx, rcx
0x18011634a  jnb     short loc_18011634F
0x18011634c  mov     rdx, r12
0x18011634f  mov     r14, [rdx]
0x180116352  lea     rcx, [r14+98h]
0x180116359  lea     rdx, [rbp+57h+var_80]
0x18011635d  call    ?UnionWith@?$Set@PEBG$1?String@Compare@Generics@Shared@Compat@Windows@@SAHAEBQEBG0@Z@Generics@Shared@Compat@Windows@@QEAAJAEBV12345@@Z; Windows::Compat::Shared::Generics::Set<ushort const *,&Windows::Compat::Shared::Generics::Compare::String(ushort const * const &,ushort const * const &)>::UnionWith(Windows::Compat::Shared::Generics::Set<ushort const *,&Windows::Compat::Shared::Generics::Compare::String(ushort const * const &,ushort const * const &)> const &)
0x180116362  mov     ebx, eax
0x180116364  test    eax, eax
0x180116366  js      loc_18011664C
0x18011636c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180116372  and     eax, r13d
0x180116375  test    al, al
0x180116377  jz      short loc_18011639C
0x180116379  mov     dword ptr [rsp+120h+var_100], ebx
0x18011637d  lea     r9, aFailedSetallow; "Failed SetAllowedToProduce: [0x%x]"
0x180116384  lea     r8, aWindowsCompatA_161; "Windows::Compat::Appraiser::ProducesCon"...
0x18011638b  lea     rdx, aOnecoreBaseApp_64; "onecore\\base\\appcompat\\appraiser\\pr"...
0x180116392  mov     ecx, 80h; unsigned int
0x180116397  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18011639c  lea     rdx, [rsp+120h+hHeap]
0x1801163a1  mov     rcx, r14
0x1801163a4  call    ?GetAllConsumed@Layer@Appraiser@Compat@Windows@@QEAAJAEAV?$Set@PEBG$1?String@Compare@Generics@Shared@Compat@Windows@@SAHAEBQEBG0@Z@Generics@Shared@34@@Z; Windows::Compat::Appraiser::Layer::GetAllConsumed(Windows::Compat::Shared::Generics::Set<ushort const *,&Windows::Compat::Shared::Generics::Compare::String(ushort const * const &,ushort const * const &)> &)
0x1801163a9  test    eax, eax
0x1801163ab  jns     short loc_1801163DE
0x1801163ad  mov     dword ptr [rsp+120h+var_F0], eax; char *
0x1801163b1  lea     rcx, aFailedGetallco; "Failed GetAllConsumed: [0x%x]."
0x1801163b8  mov     qword ptr [rsp+120h+var_F8], rcx; int
0x1801163bd  mov     dword ptr [rsp+120h+var_100], eax; char *
0x1801163c1  lea     r9, aWindowsCompatA_161; "Windows::Compat::Appraiser::ProducesCon"...
0x1801163c8  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appcompat\\appraiser\\pr"...
0x1801163cf  mov     edx, 85h; bool
0x1801163d4  mov     ecx, r13d; this
0x1801163d7  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801163dc  jmp     short loc_180116426
0x1801163de  lea     rdx, [rsp+120h+hHeap]
0x1801163e3  lea     rcx, [rbp+57h+var_80]
0x1801163e7  call    ?UnionWith@?$Set@PEBG$1?String@Compare@Generics@Shared@Compat@Windows@@SAHAEBQEBG0@Z@Generics@Shared@Compat@Windows@@QEAAJAEBV12345@@Z; Windows::Compat::Shared::Generics::Set<ushort const *,&Windows::Compat::Shared::Generics::Compare::String(ushort const * const &,ushort const * const &)>::UnionWith(Windows::Compat::Shared::Generics::Set<ushort const *,&Windows::Compat::Shared::Generics::Compare::String(ushort const * const &,ushort const * const &)> const &)
0x1801163ec  mov     ebx, eax
0x1801163ee  test    eax, eax
0x1801163f0  js      loc_18011663E
0x1801163f6  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801163fc  and     eax, r13d
0x1801163ff  test    al, al
0x180116401  jz      short loc_180116426
0x180116403  mov     dword ptr [rsp+120h+var_100], ebx
0x180116407  lea     r9, aFailedUnionwit; "Failed UnionWith: [0x%x]"
0x18011640e  lea     r8, aWindowsCompatA_161; "Windows::Compat::Appraiser::ProducesCon"...
0x180116415  lea     rdx, aOnecoreBaseApp_64; "onecore\\base\\appcompat\\appraiser\\pr"...
0x18011641c  mov     ecx, 8Ah; unsigned int
0x180116421  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180116426  add     rsi, r13
0x180116429  cmp     rsi, r15
0x18011642c  jb      loc_180116320
0x180116432  mov     r15, r12
0x180116435  lea     r13, aOnecoreBaseApp_27; "onecore\\base\\appcompat\\appraiser\\pr"...
0x18011643c  lea     rax, aFailedValidate_0; "Failed ValidateComponentProduces: [0x%x"...
0x180116443  mov     [rbp+57h+arg_8], rax
0x180116447  mov     dword ptr [rbp+57h+arg_0], 51h ; 'Q'
0x18011644e  lea     r8, aFailedValidate_1; "Failed Validate: [0x%x]"
0x180116455  mov     rax, r12
0x180116458  cmp     r15, [rdi+18h]
0x18011645c  jnb     short loc_18011647B
0x18011645e  mov     [rbp+57h+arg_10], r12
0x180116462  mov     rax, r15
0x180116465  mul     qword ptr [rdi+10h]
0x180116469  test    rdx, rdx
0x18011646c  jnz     short loc_180116478
0x18011646e  add     rax, [rdi+30h]
0x180116472  cmp     rax, [rdi+30h]
0x180116476  jnb     short loc_18011647B
0x180116478  mov     rax, r12
0x18011647b  mov     r14, [rax]
0x18011647e  cmp     dword ptr [r14+10h], 0
0x180116483  jbe     loc_180116543
0x180116489  lea     rcx, [r14+0C8h]
0x180116490  mov     rax, [r14+8]
0x180116494  mov     rax, [rax+r12*8]
0x180116498  mov     [rbp+57h+arg_10], rax
0x18011649c  mov     r8, rcx
0x18011649f  mov     rdx, rax
0x1801164a2  mov     rcx, r14
0x1801164a5  call    ?ValidateComponentConsumes@Layer@Appraiser@Compat@Windows@@AEAAJPEAVIComponent@234@AEBV?$Set@PEBG$1?String@Compare@Generics@Shared@Compat@Windows@@SAHAEBQEBG0@Z@Generics@Shared@34@@Z; Windows::Compat::Appraiser::Layer::ValidateComponentConsumes(Windows::Compat::Appraiser::IComponent *,Windows::Compat::Shared::Generics::Set<ushort const *,&Windows::Compat::Shared::Generics::Compare::String(ushort const * const &,ushort const * const &)> const &)
0x1801164aa  mov     esi, eax
0x1801164ac  mov     ebx, eax
0x1801164ae  test    eax, eax
0x1801164b0  js      loc_1801165E0
0x1801164b6  mov     ecx, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801164bc  lea     rbx, aWindowsCompatA_816; "Windows::Compat::Appraiser::Layer::Vali"...
0x1801164c3  test    cl, 1
0x1801164c6  jz      short loc_1801164E3
0x1801164c8  mov     dword ptr [rsp+120h+var_100], eax
0x1801164cc  lea     r9, aFailedValidate; "Failed ValidateComponentConsumes: [0x%x"...
0x1801164d3  mov     r8, rbx; char *
0x1801164d6  mov     rdx, r13; char *
0x1801164d9  mov     ecx, 4Eh ; 'N'; unsigned int
0x1801164de  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801164e3  lea     r8, [r14+98h]
0x1801164ea  mov     rdx, [rbp+57h+arg_10]
0x1801164ee  mov     rcx, r14
0x1801164f1  call    ?ValidateComponentProduces@Layer@Appraiser@Compat@Windows@@AEAAJPEAVIComponent@234@AEBV?$Set@PEBG$1?String@Compare@Generics@Shared@Compat@Windows@@SAHAEBQEBG0@Z@Generics@Shared@34@@Z; Windows::Compat::Appraiser::Layer::ValidateComponentProduces(Windows::Compat::Appraiser::IComponent *,Windows::Compat::Shared::Generics::Set<ushort const *,&Windows::Compat::Shared::Generics::Compare::String(ushort const * const &,ushort const * const &)> const &)
0x1801164f6  mov     esi, eax
0x1801164f8  test    eax, eax
0x1801164fa  js      loc_1801165D8
0x180116500  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180116506  test    al, 1
0x180116508  jz      short loc_180116525
0x18011650a  mov     dword ptr [rsp+120h+var_100], esi
0x18011650e  lea     r9, aFailedValidate_0; "Failed ValidateComponentProduces: [0x%x"...
0x180116515  mov     r8, rbx; char *
0x180116518  mov     rdx, r13; char *
0x18011651b  mov     ecx, 51h ; 'Q'; unsigned int
0x180116520  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180116525  inc     r12
0x180116528  mov     eax, [r14+10h]
0x18011652c  cmp     r12, rax
0x18011652f  lea     rcx, [r14+0C8h]
0x180116536  jb      loc_180116490
0x18011653c  lea     r8, aFailedValidate_1; "Failed Validate: [0x%x]"
0x180116543  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180116549  xor     r12d, r12d
0x18011654c  test    al, 1
0x18011654e  jz      short loc_180116570
0x180116550  mov     dword ptr [rsp+120h+var_100], r12d
0x180116555  mov     r9, r8; char *
0x180116558  lea     r8, aWindowsCompatA_161; "Windows::Compat::Appraiser::ProducesCon"...
  ... truncated ...
```
