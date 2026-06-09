# StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,__int64)

- ea: `0x1800053d0`
- end: `0x1800058a5`
- name: `?ContextToObject@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `1237`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800089e0`

## callees

- `0x1800053d0`
- `0x180005ce0`
- `0x18000720c`
- `0x18000d930`
- `0x18000eed0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005565`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005565`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180005404`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800054a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x18000560d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180005404`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800054a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x18000560d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180005524`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180005524`

## string_xrefs

- `0x180005414`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800054b9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180005534`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000561d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000542c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180005476`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800054d1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180005573`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800055da`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180005635`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000569c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800056fa`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000575b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800057bc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000581d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000587b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180005735`: `CurrentDirectoryPath`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int Field_UInt32; // eax
  unsigned int v9; // edi
  int Field; // eax
  unsigned int v12; // edi
  int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // rcx
  int Field_String; // eax
  int v17; // edi
  unsigned __int16 *v18; // rcx
  int v19; // edi
  int v20; // eax
  unsigned int v21; // edi
  int v22; // edi
  int v23; // edi
  int v24; // edi
  int v25; // edi
  int v26; // edi
  int v27; // ebx
  unsigned __int16 **v28; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 *v29; // [rsp+28h] [rbp-20h] BYREF
  char v30; // [rsp+30h] [rbp-18h]
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
      (int)v28);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x487,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)v9,
      (int)v28);
    return v9;
  }
  if ( a3 )
  {
LABEL_6:
    if ( (a3 & 2) == 0 )
      goto LABEL_10;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Index", (unsigned int *)(a2 + 16));
  v12 = Field;
  if ( Field < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)Field,
      (int)v28);
    return v12;
  }
  if ( a3 )
  {
LABEL_10:
    if ( (a3 & 4) == 0 )
      goto LABEL_14;
  }
  v13 = SRCacheContext_GetField_UInt32(*(_QWORD *)a1, L"Flags", a2 + 20);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v13,
      (int)v28);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)v14,
      (int)v28);
    return v14;
  }
  if ( a3 )
  {
LABEL_14:
    if ( (a3 & 8) == 0 )
      goto LABEL_24;
  }
  v15 = *(_QWORD *)a1;
  v28 = (unsigned __int16 **)(a2 + 24);
  v29 = 0;
  v30 = 1;
  Field_String = SRCacheContext_GetField_String(v15, L"PackageRelativeApplicationId", &v29);
  v17 = Field_String;
  if ( Field_String >= 0 )
    v17 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v28);
  if ( v30 )
  {
    v18 = *v28;
    *v28 = v29;
    if ( v18 )
      SRCache_Free(v18);
  }
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x493,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v17,
      (int)v28);
    return (unsigned int)v17;
  }
  if ( a3 )
  {
LABEL_24:
    if ( (a3 & 0x10) == 0 )
      goto LABEL_28;
  }
  v29 = 0;
  v28 = (unsigned __int16 **)(a2 + 32);
  v30 = 1;
  v19 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"ApplicationUserModelId", &v29);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>((__int64 **)&v28);
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x497,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v19,
      (int)v28);
    return (unsigned int)v19;
  }
  if ( a3 )
  {
LABEL_28:
    if ( (a3 & 0x20) == 0 )
      goto LABEL_32;
  }
  v20 = SRCacheContext_GetField_UInt32(*(_QWORD *)a1, L"Activation", a2 + 40);
  v21 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v20,
      (int)v28);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)v21,
      (int)v28);
    return v21;
  }
  if ( a3 )
  {
LABEL_32:
    if ( (a3 & 0x40) == 0 )
      goto LABEL_36;
  }
  v29 = 0;
  v28 = (unsigned __int16 **)(a2 + 48);
  v30 = 1;
  v22 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"HostId", &v29);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>((__int64 **)&v28);
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v22,
      (int)v28);
    return (unsigned int)v22;
  }
  if ( a3 )
  {
LABEL_36:
    if ( (a3 & 0x80u) == 0LL )
      goto LABEL_40;
  }
  v29 = 0;
  v28 = (unsigned __int16 **)(a2 + 56);
  v30 = 1;
  v23 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Parameters", &v29);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>((__int64 **)&v28);
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A3,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v23,
      (int)v28);
    return (unsigned int)v23;
  }
  if ( a3 )
  {
LABEL_40:
    if ( (a3 & 0x100) == 0 )
      goto LABEL_44;
  }
  v29 = 0;
  v28 = (unsigned __int16 **)(a2 + 64);
  v30 = 1;
  v24 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"CurrentDirectoryPath", &v29);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>((__int64 **)&v28);
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v24,
      (int)v28);
    return (unsigned int)v24;
  }
  if ( a3 )
  {
LABEL_44:
    if ( (a3 & 0x200) == 0 )
      goto LABEL_48;
  }
  v29 = 0;
  v28 = (unsigned __int16 **)(a2 + 72);
  v30 = 1;
  v25 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Executable", &v29);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>((__int64 **)&v28);
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4AB,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v25,
      (int)v28);
    return (unsigned int)v25;
  }
  if ( a3 )
  {
LABEL_48:
    if ( (a3 & 0x400) == 0 )
      goto LABEL_52;
  }
  v29 = 0;
  v28 = (unsigned __int16 **)(a2 + 80);
  v30 = 1;
  v26 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Entrypoint", &v29);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>((__int64 **)&v28);
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4AF,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v26,
      (int)v28);
    return (unsigned int)v26;
  }
  if ( a3 )
  {
LABEL_52:
    if ( (a3 & 0x800) == 0 )
      goto LABEL_55;
  }
  v29 = 0;
  v28 = (unsigned __int16 **)(a2 + 88);
  v30 = 1;
  v27 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"StartPage", &v29);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>((__int64 **)&v28);
  if ( v27 >= 0 )
  {
LABEL_55:
    *(_QWORD *)a2 = a4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B3,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v27,
      (int)v28);
    return (unsigned int)v27;
  }
}

```

## disassembly

```asm
0x1800053d0  push    rbp
0x1800053d2  push    rbx
0x1800053d3  push    rsi
0x1800053d4  push    rdi
0x1800053d5  push    r14
0x1800053d7  push    r15
0x1800053d9  mov     rbp, rsp
0x1800053dc  sub     rsp, 48h
0x1800053e0  mov     r14, r9
0x1800053e3  mov     rbx, r8
0x1800053e6  mov     rsi, rdx
0x1800053e9  mov     r15, rcx
0x1800053ec  test    r8, r8
0x1800053ef  jz      short loc_1800053F6
0x1800053f1  test    bl, 1
0x1800053f4  jz      short loc_180005454
0x1800053f6  mov     rcx, [rcx]
0x1800053f9  lea     r8, [rdx+8]
0x1800053fd  lea     rdx, aPackage; "Package"
0x180005404  call    cs:__imp_SRCacheContext_GetField_UInt32
0x18000540a  mov     edi, eax
0x18000540c  test    eax, eax
0x18000540e  jns     short loc_18000544F
0x180005410  mov     rcx, [rbp+30h]; this
0x180005414  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000541b  mov     r9d, eax; char *
0x18000541e  mov     edx, 221h; void *
0x180005423  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005428  mov     rcx, [rbp+30h]; this
0x18000542c  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005433  mov     r9d, edi; char *
0x180005436  mov     edx, 487h; void *
0x18000543b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005440  mov     eax, edi
0x180005442  add     rsp, 48h
0x180005446  pop     r15
0x180005448  pop     r14
0x18000544a  pop     rdi
0x18000544b  pop     rsi
0x18000544c  pop     rbx
0x18000544d  pop     rbp
0x18000544e  retn
0x18000544f  test    rbx, rbx
0x180005452  jz      short loc_180005459
0x180005454  test    bl, 2
0x180005457  jz      short loc_180005496
0x180005459  lea     r8, [rsi+10h]; unsigned int *
0x18000545d  mov     rcx, r15; this
0x180005460  lea     rdx, aIndex; "Index"
0x180005467  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x18000546c  mov     edi, eax
0x18000546e  test    eax, eax
0x180005470  jns     short loc_180005491
0x180005472  mov     rcx, [rbp+30h]; this
0x180005476  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000547d  mov     r9d, eax; char *
0x180005480  mov     edx, 48Bh; void *
0x180005485  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000548a  mov     eax, edi
0x18000548c  jmp     loc_180005898
0x180005491  test    rbx, rbx
0x180005494  jz      short loc_18000549B
0x180005496  test    bl, 4
0x180005499  jz      short loc_1800054F9
0x18000549b  mov     rcx, [r15]
0x18000549e  lea     r8, [rsi+14h]
0x1800054a2  lea     rdx, aFlags; "Flags"
0x1800054a9  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800054af  mov     edi, eax
0x1800054b1  test    eax, eax
0x1800054b3  jns     short loc_1800054F4
0x1800054b5  mov     rcx, [rbp+30h]; this
0x1800054b9  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800054c0  mov     r9d, eax; char *
0x1800054c3  mov     edx, 221h; void *
0x1800054c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800054cd  mov     rcx, [rbp+30h]; this
0x1800054d1  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800054d8  mov     r9d, edi; char *
0x1800054db  mov     edx, 48Fh; void *
0x1800054e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800054e5  mov     eax, edi
0x1800054e7  add     rsp, 48h
0x1800054eb  pop     r15
0x1800054ed  pop     r14
0x1800054ef  pop     rdi
0x1800054f0  pop     rsi
0x1800054f1  pop     rbx
0x1800054f2  pop     rbp
0x1800054f3  retn
0x1800054f4  test    rbx, rbx
0x1800054f7  jz      short loc_180005502
0x1800054f9  test    bl, 8
0x1800054fc  jz      loc_18000559B
0x180005502  mov     rcx, [r15]
0x180005505  lea     rax, [rsi+18h]
0x180005509  lea     r8, [rbp+var_20]
0x18000550d  mov     [rbp+var_28], rax
0x180005511  lea     rdx, aPackagerelativ; "PackageRelativeApplicationId"
0x180005518  mov     [rbp+var_20], 0
0x180005520  mov     [rbp+var_18], 1
0x180005524  call    cs:__imp_SRCacheContext_GetField_String
0x18000552a  mov     edi, eax
0x18000552c  test    eax, eax
0x18000552e  jns     short loc_18000554A
0x180005530  mov     rcx, [rbp+30h]; this
0x180005534  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000553b  mov     r9d, eax; char *
0x18000553e  mov     edx, 246h; void *
0x180005543  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005548  jmp     short loc_18000554C
0x18000554a  xor     edi, edi
0x18000554c  cmp     [rbp+var_18], 0
0x180005550  jz      short loc_18000556B
0x180005552  mov     rdx, [rbp+var_28]
0x180005556  mov     rax, [rbp+var_20]
0x18000555a  mov     rcx, [rdx]
0x18000555d  mov     [rdx], rax
0x180005560  test    rcx, rcx
0x180005563  jz      short loc_18000556B
0x180005565  call    cs:__imp_SRCache_Free
0x18000556b  test    edi, edi
0x18000556d  jns     short loc_180005596
0x18000556f  mov     rcx, [rbp+30h]; this
0x180005573  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000557a  mov     r9d, edi; char *
0x18000557d  mov     edx, 493h; void *
0x180005582  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005587  mov     eax, edi
0x180005589  add     rsp, 48h
0x18000558d  pop     r15
0x18000558f  pop     r14
0x180005591  pop     rdi
0x180005592  pop     rsi
0x180005593  pop     rbx
0x180005594  pop     rbp
0x180005595  retn
0x180005596  test    rbx, rbx
0x180005599  jz      short loc_1800055A0
0x18000559b  test    bl, 10h
0x18000559e  jz      short loc_1800055FA
0x1800055a0  lea     rax, [rsi+20h]
0x1800055a4  mov     [rbp+var_20], 0
0x1800055ac  lea     r8, [rbp+var_20]; unsigned __int16 **
0x1800055b0  mov     [rbp+var_28], rax
0x1800055b4  lea     rdx, aApplicationuse_0; "ApplicationUserModelId"
0x1800055bb  mov     [rbp+var_18], 1
0x1800055bf  mov     rcx, r15; this
0x1800055c2  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800055c7  lea     rcx, [rbp+var_28]
0x1800055cb  mov     edi, eax
0x1800055cd  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800055d2  test    edi, edi
0x1800055d4  jns     short loc_1800055F5
0x1800055d6  mov     rcx, [rbp+30h]; this
0x1800055da  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800055e1  mov     r9d, edi; char *
0x1800055e4  mov     edx, 497h; void *
0x1800055e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800055ee  mov     eax, edi
0x1800055f0  jmp     loc_180005898
0x1800055f5  test    rbx, rbx
0x1800055f8  jz      short loc_1800055FF
0x1800055fa  test    bl, 20h
0x1800055fd  jz      short loc_18000565D
0x1800055ff  mov     rcx, [r15]
0x180005602  lea     r8, [rsi+28h]
0x180005606  lea     rdx, aActivation; "Activation"
0x18000560d  call    cs:__imp_SRCacheContext_GetField_UInt32
0x180005613  mov     edi, eax
0x180005615  test    eax, eax
0x180005617  jns     short loc_180005658
0x180005619  mov     rcx, [rbp+30h]; this
0x18000561d  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005624  mov     r9d, eax; char *
0x180005627  mov     edx, 221h; void *
0x18000562c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005631  mov     rcx, [rbp+30h]; this
0x180005635  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000563c  mov     r9d, edi; char *
0x18000563f  mov     edx, 49Bh; void *
0x180005644  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005649  mov     eax, edi
0x18000564b  add     rsp, 48h
0x18000564f  pop     r15
0x180005651  pop     r14
0x180005653  pop     rdi
0x180005654  pop     rsi
0x180005655  pop     rbx
0x180005656  pop     rbp
0x180005657  retn
0x180005658  test    rbx, rbx
0x18000565b  jz      short loc_180005662
0x18000565d  test    bl, 40h
0x180005660  jz      short loc_1800056BC
0x180005662  lea     rax, [rsi+30h]
0x180005666  mov     [rbp+var_20], 0
0x18000566e  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180005672  mov     [rbp+var_28], rax
0x180005676  lea     rdx, aHostid; "HostId"
0x18000567d  mov     [rbp+var_18], 1
0x180005681  mov     rcx, r15; this
0x180005684  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180005689  lea     rcx, [rbp+var_28]
0x18000568d  mov     edi, eax
0x18000568f  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180005694  test    edi, edi
0x180005696  jns     short loc_1800056B7
0x180005698  mov     rcx, [rbp+30h]; this
0x18000569c  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800056a3  mov     r9d, edi; char *
0x1800056a6  mov     edx, 49Fh; void *
0x1800056ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800056b0  mov     eax, edi
0x1800056b2  jmp     loc_180005898
0x1800056b7  test    rbx, rbx
0x1800056ba  jz      short loc_1800056C0
0x1800056bc  test    bl, bl
0x1800056be  jns     short loc_18000571A
0x1800056c0  lea     rax, [rsi+38h]
0x1800056c4  mov     [rbp+var_20], 0
0x1800056cc  lea     r8, [rbp+var_20]; unsigned __int16 **
0x1800056d0  mov     [rbp+var_28], rax
0x1800056d4  lea     rdx, aParameters; "Parameters"
0x1800056db  mov     [rbp+var_18], 1
0x1800056df  mov     rcx, r15; this
0x1800056e2  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800056e7  lea     rcx, [rbp+var_28]
0x1800056eb  mov     edi, eax
0x1800056ed  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800056f2  test    edi, edi
0x1800056f4  jns     short loc_180005715
0x1800056f6  mov     rcx, [rbp+30h]; this
0x1800056fa  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005701  mov     r9d, edi; char *
0x180005704  mov     edx, 4A3h; void *
0x180005709  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000570e  mov     eax, edi
0x180005710  jmp     loc_180005898
0x180005715  test    rbx, rbx
0x180005718  jz      short loc_180005721
0x18000571a  bt      rbx, 8
0x18000571f  jnb     short loc_18000577B
0x180005721  lea     rax, [rsi+40h]
0x180005725  mov     [rbp+var_20], 0
0x18000572d  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180005731  mov     [rbp+var_28], rax
0x180005735  lea     rdx, aCurrentdirecto; "CurrentDirectoryPath"
0x18000573c  mov     [rbp+var_18], 1
0x180005740  mov     rcx, r15; this
0x180005743  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180005748  lea     rcx, [rbp+var_28]
0x18000574c  mov     edi, eax
0x18000574e  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180005753  test    edi, edi
0x180005755  jns     short loc_180005776
0x180005757  mov     rcx, [rbp+30h]; this
0x18000575b  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005762  mov     r9d, edi; char *
0x180005765  mov     edx, 4A7h; void *
0x18000576a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000576f  mov     eax, edi
0x180005771  jmp     loc_180005898
0x180005776  test    rbx, rbx
0x180005779  jz      short loc_180005782
0x18000577b  bt      rbx, 9
0x180005780  jnb     short loc_1800057DC
0x180005782  lea     rax, [rsi+48h]
0x180005786  mov     [rbp+var_20], 0
0x18000578e  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180005792  mov     [rbp+var_28], rax
0x180005796  lea     rdx, aExecutable; "Executable"
0x18000579d  mov     [rbp+var_18], 1
0x1800057a1  mov     rcx, r15; this
0x1800057a4  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800057a9  lea     rcx, [rbp+var_28]
0x1800057ad  mov     edi, eax
0x1800057af  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800057b4  test    edi, edi
0x1800057b6  jns     short loc_1800057D7
0x1800057b8  mov     rcx, [rbp+30h]; this
0x1800057bc  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800057c3  mov     r9d, edi; char *
0x1800057c6  mov     edx, 4ABh; void *
0x1800057cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057d0  mov     eax, edi
0x1800057d2  jmp     loc_180005898
0x1800057d7  test    rbx, rbx
0x1800057da  jz      short loc_1800057E3
0x1800057dc  bt      rbx, 0Ah
0x1800057e1  jnb     short loc_18000583A
0x1800057e3  lea     rax, [rsi+50h]
0x1800057e7  mov     [rbp+var_20], 0
0x1800057ef  lea     r8, [rbp+var_20]; unsigned __int16 **
0x1800057f3  mov     [rbp+var_28], rax
0x1800057f7  lea     rdx, aEntrypoint; "Entrypoint"
0x1800057fe  mov     [rbp+var_18], 1
0x180005802  mov     rcx, r15; this
0x180005805  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000580a  lea     rcx, [rbp+var_28]
  ... truncated ...
```
