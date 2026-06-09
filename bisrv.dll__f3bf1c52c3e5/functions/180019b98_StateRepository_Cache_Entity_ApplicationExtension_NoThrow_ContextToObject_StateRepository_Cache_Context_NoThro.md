# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,__int64)

- ea: `0x180019b98`
- end: `0x180019f4a`
- name: `?ContextToObject@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `946`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180019430`

## callees

- `0x180019b98`
- `0x18001a1f0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019cc1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019d72`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019dcd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019e28`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019f3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019cc1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019d72`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019dcd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019e28`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019f3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180019bbd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180019bf6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180019c4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180019cdd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180019bbd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180019bf6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180019c4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180019cdd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180019c9a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180019d47`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180019da2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180019dfd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180019c9a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180019d47`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180019da2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180019dfd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x180019e5c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x180019e5c`

## string_xrefs

- `0x180019bcd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019c06`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019c5d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019ced`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019d0f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019ebb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019ed8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019ef5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019f12`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019c23`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180019dea`: `CurrentDirectoryPath`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  int Field_UInt32; // eax
  int v8; // ebx
  __int64 v9; // rdx
  int v10; // eax
  int v12; // eax
  __int64 v13; // rcx
  int Field_String; // eax
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  int Field_Binary; // eax
  __int64 v28; // rcx
  int v29; // [rsp+20h] [rbp-20h]
  __int64 *v30; // [rsp+20h] [rbp-20h]
  __int64 v31; // [rsp+28h] [rbp-18h] BYREF
  char v32; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  Field_UInt32 = SRCacheContext_GetField_UInt32(*a1, L"Application", a2 + 1);
  v8 = Field_UInt32;
  if ( Field_UInt32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt32,
      v29);
    v9 = 974;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v8,
      (int)v30);
    return (unsigned int)v8;
  }
  v10 = SRCacheContext_GetField_UInt32(*a1, L"Index", a2 + 2);
  v8 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v29);
    v9 = 978;
    goto LABEL_5;
  }
  v12 = SRCacheContext_GetField_UInt32(*a1, L"Flags", (char *)a2 + 20);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v12,
      v29);
    v9 = 982;
    goto LABEL_5;
  }
  v13 = *a1;
  v30 = a2 + 3;
  v31 = 0;
  v32 = 1;
  Field_String = SRCacheContext_GetField_String(v13, L"Category", &v31);
  v8 = Field_String;
  if ( Field_String < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v30);
  else
    v8 = 0;
  if ( v32 )
  {
    v15 = *v30;
    *v30 = v31;
    if ( v15 )
      SRCache_Free(v15);
  }
  if ( v8 < 0 )
  {
    v9 = 986;
    goto LABEL_5;
  }
  v16 = SRCacheContext_GetField_UInt32(*a1, L"Activation", a2 + 4);
  v8 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      (int)v30);
    v9 = 990;
    goto LABEL_5;
  }
  v17 = *a1;
  v30 = a2 + 5;
  v31 = 0;
  v32 = 1;
  v18 = SRCacheContext_GetField_String(v17, L"HostId", &v31);
  v8 = v18;
  if ( v18 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v18,
      (int)v30);
  else
    v8 = 0;
  if ( v32 )
  {
    v19 = *v30;
    *v30 = v31;
    if ( v19 )
      SRCache_Free(v19);
  }
  if ( v8 < 0 )
  {
    v9 = 994;
    goto LABEL_5;
  }
  v20 = *a1;
  v30 = a2 + 6;
  v31 = 0;
  v32 = 1;
  v21 = SRCacheContext_GetField_String(v20, L"Parameters", &v31);
  v8 = v21;
  if ( v21 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v21,
      (int)v30);
  else
    v8 = 0;
  if ( v32 )
  {
    v22 = *v30;
    *v30 = v31;
    if ( v22 )
      SRCache_Free(v22);
  }
  if ( v8 < 0 )
  {
    v9 = 998;
    goto LABEL_5;
  }
  v23 = *a1;
  v30 = a2 + 7;
  v31 = 0;
  v32 = 1;
  v24 = SRCacheContext_GetField_String(v23, L"CurrentDirectoryPath", &v31);
  v8 = v24;
  if ( v24 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v24,
      (int)v30);
  else
    v8 = 0;
  if ( v32 )
  {
    v25 = *v30;
    *v30 = v31;
    if ( v25 )
      SRCache_Free(v25);
  }
  if ( v8 < 0 )
  {
    v9 = 1002;
    goto LABEL_5;
  }
  v26 = *a1;
  v30 = a2 + 8;
  v31 = 0;
  v32 = 1;
  Field_Binary = SRCacheContext_GetField_Binary(v26, L"_Dictionary", a2 + 9, &v31);
  v8 = Field_Binary;
  if ( Field_Binary < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_Binary,
      (int)v30);
  else
    v8 = 0;
  if ( v32 )
  {
    v28 = *v30;
    *v30 = v31;
    if ( v28 )
      SRCache_Free(v28);
  }
  if ( v8 < 0 )
  {
    v9 = 1006;
    goto LABEL_5;
  }
  *a2 = a4;
  return 0;
}

```

## disassembly

```asm
0x180019b98  push    rbp
0x180019b9a  push    rbx
0x180019b9b  push    rsi
0x180019b9c  push    rdi
0x180019b9d  push    r14
0x180019b9f  mov     rbp, rsp
0x180019ba2  sub     rsp, 40h
0x180019ba6  mov     rdi, rdx
0x180019ba9  lea     r8, [rdx+8]
0x180019bad  mov     rsi, rcx
0x180019bb0  lea     rdx, aApplication; "Application"
0x180019bb7  mov     rcx, [rcx]
0x180019bba  mov     r14, r9
0x180019bbd  call    cs:__imp_SRCacheContext_GetField_UInt32
0x180019bc3  mov     ebx, eax
0x180019bc5  test    eax, eax
0x180019bc7  jns     short loc_180019BE8
0x180019bc9  mov     rcx, [rbp+28h]; this
0x180019bcd  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019bd4  mov     r9d, eax; char *
0x180019bd7  mov     edx, 221h; void *
0x180019bdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019be1  mov     edx, 3CEh
0x180019be6  jmp     short loc_180019C1F
0x180019be8  mov     rcx, [rsi]
0x180019beb  lea     r8, [rdi+10h]
0x180019bef  lea     rdx, aIndex; "Index"
0x180019bf6  call    cs:__imp_SRCacheContext_GetField_UInt32
0x180019bfc  mov     ebx, eax
0x180019bfe  test    eax, eax
0x180019c00  jns     short loc_180019C3F
0x180019c02  mov     rcx, [rbp+28h]; this
0x180019c06  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019c0d  mov     r9d, eax; char *
0x180019c10  mov     edx, 221h; void *
0x180019c15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c1a  mov     edx, 3D2h; void *
0x180019c1f  mov     rcx, [rbp+28h]; this
0x180019c23  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019c2a  mov     r9d, ebx; char *
0x180019c2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c32  mov     eax, ebx
0x180019c34  add     rsp, 40h
0x180019c38  pop     r14
0x180019c3a  pop     rdi
0x180019c3b  pop     rsi
0x180019c3c  pop     rbx
0x180019c3d  pop     rbp
0x180019c3e  retn
0x180019c3f  mov     rcx, [rsi]
0x180019c42  lea     r8, [rdi+14h]
0x180019c46  lea     rdx, aFlags; "Flags"
0x180019c4d  call    cs:__imp_SRCacheContext_GetField_UInt32
0x180019c53  mov     ebx, eax
0x180019c55  test    eax, eax
0x180019c57  jns     short loc_180019C78
0x180019c59  mov     rcx, [rbp+28h]; this
0x180019c5d  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019c64  mov     r9d, eax; char *
0x180019c67  mov     edx, 221h; void *
0x180019c6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c71  mov     edx, 3D6h
0x180019c76  jmp     short loc_180019C1F
0x180019c78  mov     rcx, [rsi]
0x180019c7b  lea     rax, [rdi+18h]
0x180019c7f  lea     r8, [rbp+var_18]
0x180019c83  mov     [rbp+var_20], rax
0x180019c87  lea     rdx, aCategory; "Category"
0x180019c8e  mov     [rbp+var_18], 0
0x180019c96  mov     [rbp+var_10], 1
0x180019c9a  call    cs:__imp_SRCacheContext_GetField_String
0x180019ca0  mov     ebx, eax
0x180019ca2  test    eax, eax
0x180019ca4  js      short loc_180019D0B
0x180019ca6  xor     ebx, ebx
0x180019ca8  cmp     [rbp+var_10], 0
0x180019cac  jz      short loc_180019CC7
0x180019cae  mov     rdx, [rbp+var_20]
0x180019cb2  mov     rax, [rbp+var_18]
0x180019cb6  mov     rcx, [rdx]
0x180019cb9  mov     [rdx], rax
0x180019cbc  test    rcx, rcx
0x180019cbf  jz      short loc_180019CC7
0x180019cc1  call    cs:__imp_SRCache_Free
0x180019cc7  test    ebx, ebx
0x180019cc9  js      loc_180019F2B
0x180019ccf  mov     rcx, [rsi]
0x180019cd2  lea     r8, [rdi+20h]
0x180019cd6  lea     rdx, aActivation; "Activation"
0x180019cdd  call    cs:__imp_SRCacheContext_GetField_UInt32
0x180019ce3  mov     ebx, eax
0x180019ce5  test    eax, eax
0x180019ce7  jns     short loc_180019D25
0x180019ce9  mov     rcx, [rbp+28h]; this
0x180019ced  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019cf4  mov     r9d, eax; char *
0x180019cf7  mov     edx, 221h; void *
0x180019cfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019d01  mov     edx, 3DEh
0x180019d06  jmp     loc_180019C1F
0x180019d0b  mov     rcx, [rbp+28h]; this
0x180019d0f  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019d16  mov     r9d, eax; char *
0x180019d19  mov     edx, 246h; void *
0x180019d1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019d23  jmp     short loc_180019CA8
0x180019d25  mov     rcx, [rsi]
0x180019d28  lea     rax, [rdi+28h]
0x180019d2c  lea     r8, [rbp+var_18]
0x180019d30  mov     [rbp+var_20], rax
0x180019d34  lea     rdx, aHostid; "HostId"
0x180019d3b  mov     [rbp+var_18], 0
0x180019d43  mov     [rbp+var_10], 1
0x180019d47  call    cs:__imp_SRCacheContext_GetField_String
0x180019d4d  mov     ebx, eax
0x180019d4f  test    eax, eax
0x180019d51  js      loc_180019EB7
0x180019d57  xor     ebx, ebx
0x180019d59  cmp     [rbp+var_10], 0
0x180019d5d  jz      short loc_180019D78
0x180019d5f  mov     rdx, [rbp+var_20]
0x180019d63  mov     rax, [rbp+var_18]
0x180019d67  mov     rcx, [rdx]
0x180019d6a  mov     [rdx], rax
0x180019d6d  test    rcx, rcx
0x180019d70  jz      short loc_180019D78
0x180019d72  call    cs:__imp_SRCache_Free
0x180019d78  test    ebx, ebx
0x180019d7a  js      loc_180019EA3
0x180019d80  mov     rcx, [rsi]
0x180019d83  lea     rax, [rdi+30h]
0x180019d87  lea     r8, [rbp+var_18]
0x180019d8b  mov     [rbp+var_20], rax
0x180019d8f  lea     rdx, aParameters; "Parameters"
0x180019d96  mov     [rbp+var_18], 0
0x180019d9e  mov     [rbp+var_10], 1
0x180019da2  call    cs:__imp_SRCacheContext_GetField_String
0x180019da8  mov     ebx, eax
0x180019daa  test    eax, eax
0x180019dac  js      loc_180019EF1
0x180019db2  xor     ebx, ebx
0x180019db4  cmp     [rbp+var_10], 0
0x180019db8  jz      short loc_180019DD3
0x180019dba  mov     rdx, [rbp+var_20]
0x180019dbe  mov     rax, [rbp+var_18]
0x180019dc2  mov     rcx, [rdx]
0x180019dc5  mov     [rdx], rax
0x180019dc8  test    rcx, rcx
0x180019dcb  jz      short loc_180019DD3
0x180019dcd  call    cs:__imp_SRCache_Free
0x180019dd3  test    ebx, ebx
0x180019dd5  js      loc_180019EAD
0x180019ddb  mov     rcx, [rsi]
0x180019dde  lea     rax, [rdi+38h]
0x180019de2  lea     r8, [rbp+var_18]
0x180019de6  mov     [rbp+var_20], rax
0x180019dea  lea     rdx, aCurrentdirecto; "CurrentDirectoryPath"
0x180019df1  mov     [rbp+var_18], 0
0x180019df9  mov     [rbp+var_10], 1
0x180019dfd  call    cs:__imp_SRCacheContext_GetField_String
0x180019e03  mov     ebx, eax
0x180019e05  test    eax, eax
0x180019e07  js      loc_180019ED4
0x180019e0d  xor     ebx, ebx
0x180019e0f  cmp     [rbp+var_10], 0
0x180019e13  jz      short loc_180019E2E
0x180019e15  mov     rdx, [rbp+var_20]
0x180019e19  mov     rax, [rbp+var_18]
0x180019e1d  mov     rcx, [rdx]
0x180019e20  mov     [rdx], rax
0x180019e23  test    rcx, rcx
0x180019e26  jz      short loc_180019E2E
0x180019e28  call    cs:__imp_SRCache_Free
0x180019e2e  test    ebx, ebx
0x180019e30  js      loc_180019F35
0x180019e36  mov     rcx, [rsi]
0x180019e39  lea     rax, [rdi+40h]
0x180019e3d  lea     r8, [rdi+48h]
0x180019e41  mov     [rbp+var_20], rax
0x180019e45  lea     r9, [rbp+var_18]
0x180019e49  mov     [rbp+var_18], 0
0x180019e51  lea     rdx, aDictionary; "_Dictionary"
0x180019e58  mov     [rbp+var_10], 1
0x180019e5c  call    cs:__imp_SRCacheContext_GetField_Binary
0x180019e62  mov     ebx, eax
0x180019e64  test    eax, eax
0x180019e66  js      loc_180019F0E
0x180019e6c  xor     ebx, ebx
0x180019e6e  cmp     [rbp+var_10], 0
0x180019e72  jz      short loc_180019E8B
0x180019e74  mov     rdx, [rbp+var_20]
0x180019e78  mov     rax, [rbp+var_18]
0x180019e7c  mov     rcx, [rdx]
0x180019e7f  mov     [rdx], rax
0x180019e82  test    rcx, rcx
0x180019e85  jnz     loc_180019F3F
0x180019e8b  test    ebx, ebx
0x180019e8d  js      short loc_180019E99
0x180019e8f  mov     [rdi], r14
0x180019e92  xor     eax, eax
0x180019e94  jmp     loc_180019C34
0x180019e99  mov     edx, 3EEh
0x180019e9e  jmp     loc_180019C1F
0x180019ea3  mov     edx, 3E2h
0x180019ea8  jmp     loc_180019C1F
0x180019ead  mov     edx, 3E6h
0x180019eb2  jmp     loc_180019C1F
0x180019eb7  mov     rcx, [rbp+28h]; this
0x180019ebb  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019ec2  mov     r9d, eax; char *
0x180019ec5  mov     edx, 246h; void *
0x180019eca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019ecf  jmp     loc_180019D59
0x180019ed4  mov     rcx, [rbp+28h]; this
0x180019ed8  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019edf  mov     r9d, eax; char *
0x180019ee2  mov     edx, 246h; void *
0x180019ee7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019eec  jmp     loc_180019E0F
0x180019ef1  mov     rcx, [rbp+28h]; this
0x180019ef5  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019efc  mov     r9d, eax; char *
0x180019eff  mov     edx, 246h; void *
0x180019f04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f09  jmp     loc_180019DB4
0x180019f0e  mov     rcx, [rbp+28h]; this
0x180019f12  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019f19  mov     r9d, eax; char *
0x180019f1c  mov     edx, 24Fh; void *
0x180019f21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f26  jmp     loc_180019E6E
0x180019f2b  mov     edx, 3DAh
0x180019f30  jmp     loc_180019C1F
0x180019f35  mov     edx, 3EAh
0x180019f3a  jmp     loc_180019C1F
0x180019f3f  call    cs:__imp_SRCache_Free
0x180019f45  jmp     loc_180019E8B
```
