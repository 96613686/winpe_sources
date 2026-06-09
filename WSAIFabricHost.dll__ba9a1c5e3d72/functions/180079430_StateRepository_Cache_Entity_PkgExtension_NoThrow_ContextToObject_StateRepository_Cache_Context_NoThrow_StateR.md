# StateRepository::Cache::Entity::PkgExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PkgExtension_NoThrow &,StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,__int64)

- ea: `0x180079430`
- end: `0x1800797c1`
- name: `?ContextToObject@PkgExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `913`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180079f04`

## callees

- `0x18000b064`
- `0x180079430`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800796ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800796ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800794c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079553`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800795cd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079647`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800796c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079785`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800794c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079553`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800795cd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079647`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800796c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079785`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180079486`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180079515`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18007958f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180079609`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180079683`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180079486`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180079515`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18007958f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180079609`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180079683`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x180079747`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x180079747`

## string_xrefs

- `0x180079447`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800794d7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x180079793`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x1800796e6`: `Extension`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PkgExtension_NoThrow::ContextToObject(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rcx
  int Field_String; // eax
  int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  int Field_UInt32; // eax
  __int64 v27; // rcx
  int Field_Binary; // eax
  int v29; // ebx
  __int64 v30; // rcx
  __int64 *v31; // [rsp+20h] [rbp-28h]
  __int64 *v32; // [rsp+20h] [rbp-28h]
  __int64 v33; // [rsp+28h] [rbp-20h] BYREF
  char v34; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]

  if ( a3 && (a3 & 1) == 0 )
    goto LABEL_13;
  v8 = *a1;
  v31 = a2 + 1;
  v33 = 0;
  v34 = 1;
  Field_String = SRCacheContext_GetField_String(v8, L"Name", &v33);
  v10 = Field_String;
  if ( Field_String >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v31);
  if ( v34 )
  {
    v11 = *v31;
    *v31 = v33;
    if ( v11 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 718;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v10,
      (int)v31);
    return (unsigned int)v10;
  }
  if ( a3 )
  {
LABEL_13:
    if ( (a3 & 2) == 0 )
      goto LABEL_23;
  }
  v14 = *a1;
  v31 = a2 + 2;
  v33 = 0;
  v34 = 1;
  v15 = SRCacheContext_GetField_String(v14, L"Id", &v33);
  v10 = v15;
  if ( v15 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v15,
      (int)v31);
  if ( v34 )
  {
    v16 = *v31;
    *v31 = v33;
    if ( v16 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 722;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_23:
    if ( (a3 & 4) == 0 )
      goto LABEL_33;
  }
  v17 = *a1;
  v31 = a2 + 3;
  v33 = 0;
  v34 = 1;
  v18 = SRCacheContext_GetField_String(v17, L"PublicFolder", &v33);
  v10 = v18;
  if ( v18 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v18,
      (int)v31);
  if ( v34 )
  {
    v19 = *v31;
    *v31 = v33;
    if ( v19 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 726;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_33:
    if ( (a3 & 8) == 0 )
      goto LABEL_43;
  }
  v20 = *a1;
  v31 = a2 + 4;
  v33 = 0;
  v34 = 1;
  v21 = SRCacheContext_GetField_String(v20, L"DisplayName", &v33);
  v10 = v21;
  if ( v21 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v21,
      (int)v31);
  if ( v34 )
  {
    v22 = *v31;
    *v31 = v33;
    if ( v22 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 730;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_43:
    if ( (a3 & 0x10) == 0 )
      goto LABEL_53;
  }
  v23 = *a1;
  v31 = a2 + 5;
  v33 = 0;
  v34 = 1;
  v24 = SRCacheContext_GetField_String(v23, L"Description", &v33);
  v10 = v24;
  if ( v24 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v24,
      (int)v31);
  if ( v34 )
  {
    v25 = *v31;
    *v31 = v33;
    if ( v25 )
      SRCache_Free();
  }
  if ( v10 < 0 )
  {
    v12 = 734;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_53:
    if ( (a3 & 0x20) == 0 )
      goto LABEL_57;
  }
  Field_UInt32 = SRCacheContext_GetField_UInt32(*a1, L"Extension", a2 + 6);
  v10 = Field_UInt32;
  if ( Field_UInt32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt32,
      (int)v31);
    v12 = 738;
    goto LABEL_11;
  }
  if ( a3 )
  {
LABEL_57:
    if ( (a3 & 0x40) == 0 )
      goto LABEL_66;
  }
  v27 = *a1;
  v32 = a2 + 7;
  v33 = 0;
  v34 = 1;
  Field_Binary = SRCacheContext_GetField_Binary(v27, L"_Dictionary", a2 + 8, &v33);
  v29 = Field_Binary;
  if ( Field_Binary >= 0 )
    v29 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_Binary,
      (int)v32);
  if ( v34 )
  {
    v30 = *v32;
    *v32 = v33;
    if ( v30 )
      SRCache_Free();
  }
  if ( v29 >= 0 )
  {
LABEL_66:
    *a2 = a4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v29,
      (int)v32);
    return (unsigned int)v29;
  }
}

```

## disassembly

```asm
0x180079430  push    rbp
0x180079432  push    rbx
0x180079433  push    rsi
0x180079434  push    rdi
0x180079435  push    r12
0x180079437  push    r13
0x180079439  push    r14
0x18007943b  push    r15
0x18007943d  mov     rbp, rsp
0x180079440  sub     rsp, 48h
0x180079444  xor     r12d, r12d
0x180079447  lea     r13, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007944e  mov     r15, r9
0x180079451  mov     rbx, r8
0x180079454  mov     rsi, rdx
0x180079457  mov     r14, rcx
0x18007945a  test    r8, r8
0x18007945d  jz      short loc_180079468
0x18007945f  test    bl, 1
0x180079462  jz      loc_1800794F2
0x180079468  mov     rcx, [rcx]
0x18007946b  lea     rax, [rdx+8]
0x18007946f  lea     rdx, aName; "Name"
0x180079476  mov     [rbp+var_28], rax
0x18007947a  lea     r8, [rbp+var_20]
0x18007947e  mov     [rbp+var_20], r12
0x180079482  mov     [rbp+var_18], 1
0x180079486  call    cs:__imp_SRCacheContext_GetField_String
0x18007948c  mov     edi, eax
0x18007948e  test    eax, eax
0x180079490  jns     short loc_1800794A8
0x180079492  mov     rcx, [rbp+40h]; this
0x180079496  mov     r9d, eax; char *
0x180079499  mov     r8, r13; unsigned int
0x18007949c  mov     edx, 246h; void *
0x1800794a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800794a6  jmp     short loc_1800794AB
0x1800794a8  mov     edi, r12d
0x1800794ab  cmp     [rbp+var_18], r12b
0x1800794af  jz      short loc_1800794CA
0x1800794b1  mov     rdx, [rbp+var_28]
0x1800794b5  mov     rax, [rbp+var_20]
0x1800794b9  mov     rcx, [rdx]
0x1800794bc  mov     [rdx], rax
0x1800794bf  test    rcx, rcx
0x1800794c2  jz      short loc_1800794CA
0x1800794c4  call    cs:__imp_SRCache_Free
0x1800794ca  test    edi, edi
0x1800794cc  jns     short loc_1800794ED
0x1800794ce  mov     edx, 2CEh; void *
0x1800794d3  mov     rcx, [rbp+40h]; this
0x1800794d7  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800794de  mov     r9d, edi; char *
0x1800794e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800794e6  mov     eax, edi
0x1800794e8  jmp     loc_1800797B0
0x1800794ed  test    rbx, rbx
0x1800794f0  jz      short loc_1800794F7
0x1800794f2  test    bl, 2
0x1800794f5  jz      short loc_18007956C
0x1800794f7  mov     rcx, [r14]
0x1800794fa  lea     rax, [rsi+10h]
0x1800794fe  lea     r8, [rbp+var_20]
0x180079502  mov     [rbp+var_28], rax
0x180079506  lea     rdx, aId; "Id"
0x18007950d  mov     [rbp+var_20], r12
0x180079511  mov     [rbp+var_18], 1
0x180079515  call    cs:__imp_SRCacheContext_GetField_String
0x18007951b  mov     edi, eax
0x18007951d  test    eax, eax
0x18007951f  jns     short loc_180079537
0x180079521  mov     rcx, [rbp+40h]; this
0x180079525  mov     r9d, eax; char *
0x180079528  mov     r8, r13; unsigned int
0x18007952b  mov     edx, 246h; void *
0x180079530  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079535  jmp     short loc_18007953A
0x180079537  mov     edi, r12d
0x18007953a  cmp     [rbp+var_18], r12b
0x18007953e  jz      short loc_180079559
0x180079540  mov     rdx, [rbp+var_28]
0x180079544  mov     rax, [rbp+var_20]
0x180079548  mov     rcx, [rdx]
0x18007954b  mov     [rdx], rax
0x18007954e  test    rcx, rcx
0x180079551  jz      short loc_180079559
0x180079553  call    cs:__imp_SRCache_Free
0x180079559  test    edi, edi
0x18007955b  jns     short loc_180079567
0x18007955d  mov     edx, 2D2h
0x180079562  jmp     loc_1800794D3
0x180079567  test    rbx, rbx
0x18007956a  jz      short loc_180079571
0x18007956c  test    bl, 4
0x18007956f  jz      short loc_1800795E6
0x180079571  mov     rcx, [r14]
0x180079574  lea     rax, [rsi+18h]
0x180079578  lea     r8, [rbp+var_20]
0x18007957c  mov     [rbp+var_28], rax
0x180079580  lea     rdx, aPublicfolder; "PublicFolder"
0x180079587  mov     [rbp+var_20], r12
0x18007958b  mov     [rbp+var_18], 1
0x18007958f  call    cs:__imp_SRCacheContext_GetField_String
0x180079595  mov     edi, eax
0x180079597  test    eax, eax
0x180079599  jns     short loc_1800795B1
0x18007959b  mov     rcx, [rbp+40h]; this
0x18007959f  mov     r9d, eax; char *
0x1800795a2  mov     r8, r13; unsigned int
0x1800795a5  mov     edx, 246h; void *
0x1800795aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800795af  jmp     short loc_1800795B4
0x1800795b1  mov     edi, r12d
0x1800795b4  cmp     [rbp+var_18], r12b
0x1800795b8  jz      short loc_1800795D3
0x1800795ba  mov     rdx, [rbp+var_28]
0x1800795be  mov     rax, [rbp+var_20]
0x1800795c2  mov     rcx, [rdx]
0x1800795c5  mov     [rdx], rax
0x1800795c8  test    rcx, rcx
0x1800795cb  jz      short loc_1800795D3
0x1800795cd  call    cs:__imp_SRCache_Free
0x1800795d3  test    edi, edi
0x1800795d5  jns     short loc_1800795E1
0x1800795d7  mov     edx, 2D6h
0x1800795dc  jmp     loc_1800794D3
0x1800795e1  test    rbx, rbx
0x1800795e4  jz      short loc_1800795EB
0x1800795e6  test    bl, 8
0x1800795e9  jz      short loc_180079660
0x1800795eb  mov     rcx, [r14]
0x1800795ee  lea     rax, [rsi+20h]
0x1800795f2  lea     r8, [rbp+var_20]
0x1800795f6  mov     [rbp+var_28], rax
0x1800795fa  lea     rdx, aDisplayname; "DisplayName"
0x180079601  mov     [rbp+var_20], r12
0x180079605  mov     [rbp+var_18], 1
0x180079609  call    cs:__imp_SRCacheContext_GetField_String
0x18007960f  mov     edi, eax
0x180079611  test    eax, eax
0x180079613  jns     short loc_18007962B
0x180079615  mov     rcx, [rbp+40h]; this
0x180079619  mov     r9d, eax; char *
0x18007961c  mov     r8, r13; unsigned int
0x18007961f  mov     edx, 246h; void *
0x180079624  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079629  jmp     short loc_18007962E
0x18007962b  mov     edi, r12d
0x18007962e  cmp     [rbp+var_18], r12b
0x180079632  jz      short loc_18007964D
0x180079634  mov     rdx, [rbp+var_28]
0x180079638  mov     rax, [rbp+var_20]
0x18007963c  mov     rcx, [rdx]
0x18007963f  mov     [rdx], rax
0x180079642  test    rcx, rcx
0x180079645  jz      short loc_18007964D
0x180079647  call    cs:__imp_SRCache_Free
0x18007964d  test    edi, edi
0x18007964f  jns     short loc_18007965B
0x180079651  mov     edx, 2DAh
0x180079656  jmp     loc_1800794D3
0x18007965b  test    rbx, rbx
0x18007965e  jz      short loc_180079665
0x180079660  test    bl, 10h
0x180079663  jz      short loc_1800796DA
0x180079665  mov     rcx, [r14]
0x180079668  lea     rax, [rsi+28h]
0x18007966c  lea     r8, [rbp+var_20]
0x180079670  mov     [rbp+var_28], rax
0x180079674  lea     rdx, aDescription; "Description"
0x18007967b  mov     [rbp+var_20], r12
0x18007967f  mov     [rbp+var_18], 1
0x180079683  call    cs:__imp_SRCacheContext_GetField_String
0x180079689  mov     edi, eax
0x18007968b  test    eax, eax
0x18007968d  jns     short loc_1800796A5
0x18007968f  mov     rcx, [rbp+40h]; this
0x180079693  mov     r9d, eax; char *
0x180079696  mov     r8, r13; unsigned int
0x180079699  mov     edx, 246h; void *
0x18007969e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800796a3  jmp     short loc_1800796A8
0x1800796a5  mov     edi, r12d
0x1800796a8  cmp     [rbp+var_18], r12b
0x1800796ac  jz      short loc_1800796C7
0x1800796ae  mov     rdx, [rbp+var_28]
0x1800796b2  mov     rax, [rbp+var_20]
0x1800796b6  mov     rcx, [rdx]
0x1800796b9  mov     [rdx], rax
0x1800796bc  test    rcx, rcx
0x1800796bf  jz      short loc_1800796C7
0x1800796c1  call    cs:__imp_SRCache_Free
0x1800796c7  test    edi, edi
0x1800796c9  jns     short loc_1800796D5
0x1800796cb  mov     edx, 2DEh
0x1800796d0  jmp     loc_1800794D3
0x1800796d5  test    rbx, rbx
0x1800796d8  jz      short loc_1800796DF
0x1800796da  test    bl, 20h
0x1800796dd  jz      short loc_18007971C
0x1800796df  mov     rcx, [r14]
0x1800796e2  lea     r8, [rsi+30h]
0x1800796e6  lea     rdx, aExtension; "Extension"
0x1800796ed  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800796f3  mov     edi, eax
0x1800796f5  test    eax, eax
0x1800796f7  jns     short loc_180079717
0x1800796f9  mov     rcx, [rbp+40h]; this
0x1800796fd  mov     r9d, eax; char *
0x180079700  mov     r8, r13; unsigned int
0x180079703  mov     edx, 221h; void *
0x180079708  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007970d  mov     edx, 2E2h
0x180079712  jmp     loc_1800794D3
0x180079717  test    rbx, rbx
0x18007971a  jz      short loc_180079725
0x18007971c  test    bl, 40h
0x18007971f  jz      loc_1800797AB
0x180079725  mov     rcx, [r14]
0x180079728  lea     rax, [rsi+38h]
0x18007972c  lea     r8, [rsi+40h]
0x180079730  mov     [rbp+var_28], rax
0x180079734  lea     r9, [rbp+var_20]
0x180079738  mov     [rbp+var_20], r12
0x18007973c  lea     rdx, aDictionary; "_Dictionary"
0x180079743  mov     [rbp+var_18], 1
0x180079747  call    cs:__imp_SRCacheContext_GetField_Binary
0x18007974d  mov     ebx, eax
0x18007974f  test    eax, eax
0x180079751  jns     short loc_180079769
0x180079753  mov     rcx, [rbp+40h]; this
0x180079757  mov     r9d, eax; char *
0x18007975a  mov     r8, r13; unsigned int
0x18007975d  mov     edx, 24Fh; void *
0x180079762  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079767  jmp     short loc_18007976C
0x180079769  mov     ebx, r12d
0x18007976c  cmp     [rbp+var_18], r12b
0x180079770  jz      short loc_18007978B
0x180079772  mov     rdx, [rbp+var_28]
0x180079776  mov     rax, [rbp+var_20]
0x18007977a  mov     rcx, [rdx]
0x18007977d  mov     [rdx], rax
0x180079780  test    rcx, rcx
0x180079783  jz      short loc_18007978B
0x180079785  call    cs:__imp_SRCache_Free
0x18007978b  test    ebx, ebx
0x18007978d  jns     short loc_1800797AB
0x18007978f  mov     rcx, [rbp+40h]; this
0x180079793  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007979a  mov     r9d, ebx; char *
0x18007979d  mov     edx, 2E6h; void *
0x1800797a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800797a7  mov     eax, ebx
0x1800797a9  jmp     short loc_1800797B0
0x1800797ab  mov     [rsi], r15
0x1800797ae  xor     eax, eax
0x1800797b0  add     rsp, 48h
0x1800797b4  pop     r15
0x1800797b6  pop     r14
0x1800797b8  pop     r13
0x1800797ba  pop     r12
0x1800797bc  pop     rdi
0x1800797bd  pop     rsi
0x1800797be  pop     rbx
0x1800797bf  pop     rbp
0x1800797c0  retn
```
