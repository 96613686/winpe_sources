# StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,__int64)

- ea: `0x180005ff0`
- end: `0x18000652a`
- name: `?ContextToObject@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `1338`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180006530`
- `0x180007120`

## callees

- `0x180005ff0`
- `0x18000b580`
- `0x18000b5c0`
- `0x18002f980`
- `0x180030470`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800061ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800062e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800063ea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800061ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800062e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800063ea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180006024`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180006087`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180006024`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180006087`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800061ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006326`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000642b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800061ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006326`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000642b`

## string_xrefs

- `0x18000604c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800060af`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800060f9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180006160`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800061fa`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000623c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000629b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180006334`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000639d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180006439`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800064a2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180006500`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180006034`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180006097`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800061bb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800062f5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800063fa`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180006377`: `CurrentDirectoryPath`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int Field_UInt32; // eax
  unsigned int v9; // esi
  int v11; // eax
  unsigned int v12; // esi
  int Field; // eax
  unsigned int v14; // esi
  int v15; // esi
  __int64 v16; // rcx
  int Field_String; // eax
  int v18; // esi
  unsigned __int16 *v19; // rcx
  int v20; // eax
  unsigned int v21; // esi
  int v22; // esi
  __int64 v23; // rcx
  int v24; // eax
  int v25; // esi
  unsigned __int16 *v26; // rcx
  int v27; // esi
  __int64 v28; // rcx
  int v29; // eax
  int v30; // esi
  unsigned __int16 *v31; // rcx
  int v32; // esi
  int v33; // ebx
  unsigned __int16 **v34; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 *v35; // [rsp+28h] [rbp-20h] BYREF
  char v36; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  if ( a3 && (a3 & 1) == 0 )
    goto LABEL_6;
  Field_UInt32 = SRCacheContext_GetField_UInt32(*(_QWORD *)a1, L"Package", a2 + 8);
  v9 = Field_UInt32;
  if ( Field_UInt32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt32,
      (int)v34);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x487,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)v9,
      (int)v34);
    return v9;
  }
  if ( a3 )
  {
LABEL_6:
    if ( (a3 & 2) == 0 )
      goto LABEL_10;
  }
  v11 = SRCacheContext_GetField_UInt32(*(_QWORD *)a1, L"Index", a2 + 16);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v11,
      (int)v34);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)v12,
      (int)v34);
    return v12;
  }
  if ( a3 )
  {
LABEL_10:
    if ( (a3 & 4) == 0 )
      goto LABEL_14;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Flags", (unsigned int *)(a2 + 20));
  v14 = Field;
  if ( Field < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)Field,
      (int)v34);
    return v14;
  }
  if ( a3 )
  {
LABEL_14:
    if ( (a3 & 8) == 0 )
      goto LABEL_18;
  }
  v35 = 0;
  v34 = (unsigned __int16 **)(a2 + 24);
  v36 = 1;
  v15 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageRelativeApplicationId", &v35);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v34);
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x493,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v15,
      (int)v34);
    return (unsigned int)v15;
  }
  if ( a3 )
  {
LABEL_18:
    if ( (a3 & 0x10) == 0 )
      goto LABEL_28;
  }
  v16 = *(_QWORD *)a1;
  v34 = (unsigned __int16 **)(a2 + 32);
  v35 = 0;
  v36 = 1;
  Field_String = SRCacheContext_GetField_String(v16, L"ApplicationUserModelId", &v35);
  v18 = Field_String;
  if ( Field_String >= 0 )
    v18 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v34);
  if ( v36 )
  {
    v19 = *v34;
    *v34 = v35;
    if ( v19 )
      SRCache_Free();
  }
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x497,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v18,
      (int)v34);
    return (unsigned int)v18;
  }
  if ( a3 )
  {
LABEL_28:
    if ( (a3 & 0x20) == 0 )
      goto LABEL_32;
  }
  v20 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Activation", (unsigned int *)(a2 + 40));
  v21 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v20,
      (int)v34);
    return v21;
  }
  if ( a3 )
  {
LABEL_32:
    if ( (a3 & 0x40) == 0 )
      goto LABEL_36;
  }
  v35 = 0;
  v34 = (unsigned __int16 **)(a2 + 48);
  v36 = 1;
  v22 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"HostId", &v35);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v34);
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v22,
      (int)v34);
    return (unsigned int)v22;
  }
  if ( a3 )
  {
LABEL_36:
    if ( (a3 & 0x80u) == 0LL )
      goto LABEL_46;
  }
  v23 = *(_QWORD *)a1;
  v34 = (unsigned __int16 **)(a2 + 56);
  v35 = 0;
  v36 = 1;
  v24 = SRCacheContext_GetField_String(v23, L"Parameters", &v35);
  v25 = v24;
  if ( v24 >= 0 )
    v25 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v24,
      (int)v34);
  if ( v36 )
  {
    v26 = *v34;
    *v34 = v35;
    if ( v26 )
      SRCache_Free();
  }
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A3,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v25,
      (int)v34);
    return (unsigned int)v25;
  }
  if ( a3 )
  {
LABEL_46:
    if ( (a3 & 0x100) == 0 )
      goto LABEL_50;
  }
  v35 = 0;
  v34 = (unsigned __int16 **)(a2 + 64);
  v36 = 1;
  v27 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"CurrentDirectoryPath", &v35);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v34);
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v27,
      (int)v34);
    return (unsigned int)v27;
  }
  if ( a3 )
  {
LABEL_50:
    if ( (a3 & 0x200) == 0 )
      goto LABEL_60;
  }
  v28 = *(_QWORD *)a1;
  v34 = (unsigned __int16 **)(a2 + 72);
  v35 = 0;
  v36 = 1;
  v29 = SRCacheContext_GetField_String(v28, L"Executable", &v35);
  v30 = v29;
  if ( v29 >= 0 )
    v30 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v29,
      (int)v34);
  if ( v36 )
  {
    v31 = *v34;
    *v34 = v35;
    if ( v31 )
      SRCache_Free();
  }
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4AB,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v30,
      (int)v34);
    return (unsigned int)v30;
  }
  if ( a3 )
  {
LABEL_60:
    if ( (a3 & 0x400) == 0 )
      goto LABEL_64;
  }
  v35 = 0;
  v34 = (unsigned __int16 **)(a2 + 80);
  v36 = 1;
  v32 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Entrypoint", &v35);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v34);
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4AF,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v32,
      (int)v34);
    return (unsigned int)v32;
  }
  if ( a3 )
  {
LABEL_64:
    if ( (a3 & 0x800) == 0 )
      goto LABEL_67;
  }
  v35 = 0;
  v34 = (unsigned __int16 **)(a2 + 88);
  v36 = 1;
  v33 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"StartPage", &v35);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v34);
  if ( v33 >= 0 )
  {
LABEL_67:
    *(_QWORD *)a2 = a4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B3,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v33,
      (int)v34);
    return (unsigned int)v33;
  }
}

```

## disassembly

```asm
0x180005ff0  push    rbp
0x180005ff2  push    rbx
0x180005ff3  push    rsi
0x180005ff4  push    rdi
0x180005ff5  push    r14
0x180005ff7  push    r15
0x180005ff9  mov     rbp, rsp
0x180005ffc  sub     rsp, 48h
0x180006000  mov     r14, r9
0x180006003  mov     rbx, r8
0x180006006  mov     rdi, rdx
0x180006009  mov     r15, rcx
0x18000600c  test    r8, r8
0x18000600f  jz      short loc_180006016
0x180006011  test    bl, 1
0x180006014  jz      short loc_180006074
0x180006016  mov     rcx, [rcx]
0x180006019  lea     r8, [rdx+8]
0x18000601d  lea     rdx, aPackage; "Package"
0x180006024  call    cs:__imp_SRCacheContext_GetField_UInt32
0x18000602a  mov     esi, eax
0x18000602c  test    eax, eax
0x18000602e  jns     short loc_18000606F
0x180006030  mov     rcx, [rbp+30h]; this
0x180006034  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000603b  mov     r9d, eax; char *
0x18000603e  mov     edx, 221h; void *
0x180006043  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006048  mov     rcx, [rbp+30h]; this
0x18000604c  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006053  mov     r9d, esi; char *
0x180006056  mov     edx, 487h; void *
0x18000605b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006060  mov     eax, esi
0x180006062  add     rsp, 48h
0x180006066  pop     r15
0x180006068  pop     r14
0x18000606a  pop     rdi
0x18000606b  pop     rsi
0x18000606c  pop     rbx
0x18000606d  pop     rbp
0x18000606e  retn
0x18000606f  test    rbx, rbx
0x180006072  jz      short loc_180006079
0x180006074  test    bl, 2
0x180006077  jz      short loc_1800060D7
0x180006079  mov     rcx, [r15]
0x18000607c  lea     r8, [rdi+10h]
0x180006080  lea     rdx, aIndex; "Index"
0x180006087  call    cs:__imp_SRCacheContext_GetField_UInt32
0x18000608d  mov     esi, eax
0x18000608f  test    eax, eax
0x180006091  jns     short loc_1800060D2
0x180006093  mov     rcx, [rbp+30h]; this
0x180006097  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000609e  mov     r9d, eax; char *
0x1800060a1  mov     edx, 221h; void *
0x1800060a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060ab  mov     rcx, [rbp+30h]; this
0x1800060af  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800060b6  mov     r9d, esi; char *
0x1800060b9  mov     edx, 48Bh; void *
0x1800060be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060c3  mov     eax, esi
0x1800060c5  add     rsp, 48h
0x1800060c9  pop     r15
0x1800060cb  pop     r14
0x1800060cd  pop     rdi
0x1800060ce  pop     rsi
0x1800060cf  pop     rbx
0x1800060d0  pop     rbp
0x1800060d1  retn
0x1800060d2  test    rbx, rbx
0x1800060d5  jz      short loc_1800060DC
0x1800060d7  test    bl, 4
0x1800060da  jz      short loc_180006121
0x1800060dc  lea     r8, [rdi+14h]; unsigned int *
0x1800060e0  mov     rcx, r15; this
0x1800060e3  lea     rdx, aFlags; "Flags"
0x1800060ea  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x1800060ef  mov     esi, eax
0x1800060f1  test    eax, eax
0x1800060f3  jns     short loc_18000611C
0x1800060f5  mov     rcx, [rbp+30h]; this
0x1800060f9  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006100  mov     r9d, eax; char *
0x180006103  mov     edx, 48Fh; void *
0x180006108  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000610d  mov     eax, esi
0x18000610f  add     rsp, 48h
0x180006113  pop     r15
0x180006115  pop     r14
0x180006117  pop     rdi
0x180006118  pop     rsi
0x180006119  pop     rbx
0x18000611a  pop     rbp
0x18000611b  retn
0x18000611c  test    rbx, rbx
0x18000611f  jz      short loc_180006126
0x180006121  test    bl, 8
0x180006124  jz      short loc_180006180
0x180006126  lea     rax, [rdi+18h]
0x18000612a  mov     [rbp+var_20], 0
0x180006132  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180006136  mov     [rbp+var_28], rax
0x18000613a  lea     rdx, aPackagerelativ; "PackageRelativeApplicationId"
0x180006141  mov     [rbp+var_18], 1
0x180006145  mov     rcx, r15; this
0x180006148  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000614d  lea     rcx, [rbp+var_28]
0x180006151  mov     esi, eax
0x180006153  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180006158  test    esi, esi
0x18000615a  jns     short loc_18000617B
0x18000615c  mov     rcx, [rbp+30h]; this
0x180006160  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006167  mov     r9d, esi; char *
0x18000616a  mov     edx, 493h; void *
0x18000616f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006174  mov     eax, esi
0x180006176  jmp     loc_18000651D
0x18000617b  test    rbx, rbx
0x18000617e  jz      short loc_180006189
0x180006180  test    bl, 10h
0x180006183  jz      loc_18000621A
0x180006189  mov     rcx, [r15]
0x18000618c  lea     rax, [rdi+20h]
0x180006190  lea     r8, [rbp+var_20]
0x180006194  mov     [rbp+var_28], rax
0x180006198  lea     rdx, aApplicationuse_0; "ApplicationUserModelId"
0x18000619f  mov     [rbp+var_20], 0
0x1800061a7  mov     [rbp+var_18], 1
0x1800061ab  call    cs:__imp_SRCacheContext_GetField_String
0x1800061b1  mov     esi, eax
0x1800061b3  test    eax, eax
0x1800061b5  jns     short loc_1800061D1
0x1800061b7  mov     rcx, [rbp+30h]; this
0x1800061bb  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800061c2  mov     r9d, eax; char *
0x1800061c5  mov     edx, 246h; void *
0x1800061ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061cf  jmp     short loc_1800061D3
0x1800061d1  xor     esi, esi
0x1800061d3  cmp     [rbp+var_18], 0
0x1800061d7  jz      short loc_1800061F2
0x1800061d9  mov     rdx, [rbp+var_28]
0x1800061dd  mov     rax, [rbp+var_20]
0x1800061e1  mov     rcx, [rdx]
0x1800061e4  mov     [rdx], rax
0x1800061e7  test    rcx, rcx
0x1800061ea  jz      short loc_1800061F2
0x1800061ec  call    cs:__imp_SRCache_Free
0x1800061f2  test    esi, esi
0x1800061f4  jns     short loc_180006215
0x1800061f6  mov     rcx, [rbp+30h]; this
0x1800061fa  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006201  mov     r9d, esi; char *
0x180006204  mov     edx, 497h; void *
0x180006209  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000620e  mov     eax, esi
0x180006210  jmp     loc_18000651D
0x180006215  test    rbx, rbx
0x180006218  jz      short loc_18000621F
0x18000621a  test    bl, 20h
0x18000621d  jz      short loc_18000625C
0x18000621f  lea     r8, [rdi+28h]; unsigned int *
0x180006223  mov     rcx, r15; this
0x180006226  lea     rdx, aActivation; "Activation"
0x18000622d  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180006232  mov     esi, eax
0x180006234  test    eax, eax
0x180006236  jns     short loc_180006257
0x180006238  mov     rcx, [rbp+30h]; this
0x18000623c  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006243  mov     r9d, eax; char *
0x180006246  mov     edx, 49Bh; void *
0x18000624b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006250  mov     eax, esi
0x180006252  jmp     loc_18000651D
0x180006257  test    rbx, rbx
0x18000625a  jz      short loc_180006261
0x18000625c  test    bl, 40h
0x18000625f  jz      short loc_1800062BB
0x180006261  lea     rax, [rdi+30h]
0x180006265  mov     [rbp+var_20], 0
0x18000626d  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180006271  mov     [rbp+var_28], rax
0x180006275  lea     rdx, aHostid; "HostId"
0x18000627c  mov     [rbp+var_18], 1
0x180006280  mov     rcx, r15; this
0x180006283  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180006288  lea     rcx, [rbp+var_28]
0x18000628c  mov     esi, eax
0x18000628e  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180006293  test    esi, esi
0x180006295  jns     short loc_1800062B6
0x180006297  mov     rcx, [rbp+30h]; this
0x18000629b  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800062a2  mov     r9d, esi; char *
0x1800062a5  mov     edx, 49Fh; void *
0x1800062aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062af  mov     eax, esi
0x1800062b1  jmp     loc_18000651D
0x1800062b6  test    rbx, rbx
0x1800062b9  jz      short loc_1800062C3
0x1800062bb  test    bl, bl
0x1800062bd  jns     loc_18000635C
0x1800062c3  mov     rcx, [r15]
0x1800062c6  lea     rax, [rdi+38h]
0x1800062ca  lea     r8, [rbp+var_20]
0x1800062ce  mov     [rbp+var_28], rax
0x1800062d2  lea     rdx, aParameters; "Parameters"
0x1800062d9  mov     [rbp+var_20], 0
0x1800062e1  mov     [rbp+var_18], 1
0x1800062e5  call    cs:__imp_SRCacheContext_GetField_String
0x1800062eb  mov     esi, eax
0x1800062ed  test    eax, eax
0x1800062ef  jns     short loc_18000630B
0x1800062f1  mov     rcx, [rbp+30h]; this
0x1800062f5  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800062fc  mov     r9d, eax; char *
0x1800062ff  mov     edx, 246h; void *
0x180006304  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006309  jmp     short loc_18000630D
0x18000630b  xor     esi, esi
0x18000630d  cmp     [rbp+var_18], 0
0x180006311  jz      short loc_18000632C
0x180006313  mov     rdx, [rbp+var_28]
0x180006317  mov     rax, [rbp+var_20]
0x18000631b  mov     rcx, [rdx]
0x18000631e  mov     [rdx], rax
0x180006321  test    rcx, rcx
0x180006324  jz      short loc_18000632C
0x180006326  call    cs:__imp_SRCache_Free
0x18000632c  test    esi, esi
0x18000632e  jns     short loc_180006357
0x180006330  mov     rcx, [rbp+30h]; this
0x180006334  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000633b  mov     r9d, esi; char *
0x18000633e  mov     edx, 4A3h; void *
0x180006343  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006348  mov     eax, esi
0x18000634a  add     rsp, 48h
0x18000634e  pop     r15
0x180006350  pop     r14
0x180006352  pop     rdi
0x180006353  pop     rsi
0x180006354  pop     rbx
0x180006355  pop     rbp
0x180006356  retn
0x180006357  test    rbx, rbx
0x18000635a  jz      short loc_180006363
0x18000635c  bt      rbx, 8
0x180006361  jnb     short loc_1800063BD
0x180006363  lea     rax, [rdi+40h]
0x180006367  mov     [rbp+var_20], 0
0x18000636f  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180006373  mov     [rbp+var_28], rax
0x180006377  lea     rdx, aCurrentdirecto; "CurrentDirectoryPath"
0x18000637e  mov     [rbp+var_18], 1
0x180006382  mov     rcx, r15; this
0x180006385  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000638a  lea     rcx, [rbp+var_28]
0x18000638e  mov     esi, eax
0x180006390  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180006395  test    esi, esi
0x180006397  jns     short loc_1800063B8
0x180006399  mov     rcx, [rbp+30h]; this
0x18000639d  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800063a4  mov     r9d, esi; char *
0x1800063a7  mov     edx, 4A7h; void *
0x1800063ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800063b1  mov     eax, esi
0x1800063b3  jmp     loc_18000651D
0x1800063b8  test    rbx, rbx
0x1800063bb  jz      short loc_1800063C8
0x1800063bd  bt      rbx, 9
0x1800063c2  jnb     loc_180006461
0x1800063c8  mov     rcx, [r15]
0x1800063cb  lea     rax, [rdi+48h]
0x1800063cf  lea     r8, [rbp+var_20]
0x1800063d3  mov     [rbp+var_28], rax
0x1800063d7  lea     rdx, aExecutable; "Executable"
0x1800063de  mov     [rbp+var_20], 0
0x1800063e6  mov     [rbp+var_18], 1
0x1800063ea  call    cs:__imp_SRCacheContext_GetField_String
0x1800063f0  mov     esi, eax
0x1800063f2  test    eax, eax
0x1800063f4  jns     short loc_180006410
0x1800063f6  mov     rcx, [rbp+30h]; this
0x1800063fa  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006401  mov     r9d, eax; char *
0x180006404  mov     edx, 246h; void *
0x180006409  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000640e  jmp     short loc_180006412
0x180006410  xor     esi, esi
0x180006412  cmp     [rbp+var_18], 0
0x180006416  jz      short loc_180006431
0x180006418  mov     rdx, [rbp+var_28]
0x18000641c  mov     rax, [rbp+var_20]
  ... truncated ...
```
