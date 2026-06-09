# StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,__int64)

- ea: `0x180008b20`
- end: `0x18000900b`
- name: `?ContextToObject@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `1259`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008590`

## callees

- `0x180007ae0`
- `0x180007c30`
- `0x180007c78`
- `0x180008b20`
- `0x18000ee70`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008cc2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008cc2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180008c7b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180008c7b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180008b5f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180008c02`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180008d68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180008b5f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180008c02`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180008d68`

## string_xrefs

- `0x180008b75`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180008c18`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180008c91`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180008d7e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180008b8d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008bcf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008c30`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008cd6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008d35`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008d96`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008df5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008e53`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008eb4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008f15`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008f76`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008fd4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008e8e`: `CurrentDirectoryPath`

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
  unsigned __int16 **v18; // rdx
  unsigned __int16 *v19; // rcx
  int v20; // edi
  int v21; // eax
  unsigned int v22; // edi
  int v23; // edi
  int v24; // edi
  int v25; // edi
  int v26; // edi
  int v27; // edi
  int v28; // ebx
  unsigned __int16 **v29; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v30; // [rsp+28h] [rbp-18h] BYREF
  char v31; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]

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
      (int)v29);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x487,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)v9,
      (int)v29);
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
      (int)v29);
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
      (int)v29);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)v14,
      (int)v29);
    return v14;
  }
  if ( a3 )
  {
LABEL_14:
    if ( (a3 & 8) == 0 )
      goto LABEL_24;
  }
  v15 = *(_QWORD *)a1;
  v29 = (unsigned __int16 **)(a2 + 24);
  v30 = 0;
  v31 = 1;
  Field_String = SRCacheContext_GetField_String(v15, L"PackageRelativeApplicationId", &v30);
  v17 = Field_String;
  if ( Field_String >= 0 )
    v17 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v29);
  if ( v31 )
  {
    v18 = v29;
    v19 = *v29;
    *v29 = v30;
    if ( v19 )
      SRCache_Free(v19, v18);
  }
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x493,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v17,
      (int)v29);
    return (unsigned int)v17;
  }
  if ( a3 )
  {
LABEL_24:
    if ( (a3 & 0x10) == 0 )
      goto LABEL_28;
  }
  v30 = 0;
  v29 = (unsigned __int16 **)(a2 + 32);
  v31 = 1;
  v20 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"ApplicationUserModelId", &v30);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v29);
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x497,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v20,
      (int)v29);
    return (unsigned int)v20;
  }
  if ( a3 )
  {
LABEL_28:
    if ( (a3 & 0x20) == 0 )
      goto LABEL_32;
  }
  v21 = SRCacheContext_GetField_UInt32(*(_QWORD *)a1, L"Activation", a2 + 40);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v21,
      (int)v29);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)v22,
      (int)v29);
    return v22;
  }
  if ( a3 )
  {
LABEL_32:
    if ( (a3 & 0x40) == 0 )
      goto LABEL_36;
  }
  v30 = 0;
  v29 = (unsigned __int16 **)(a2 + 48);
  v31 = 1;
  v23 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"HostId", &v30);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v29);
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v23,
      (int)v29);
    return (unsigned int)v23;
  }
  if ( a3 )
  {
LABEL_36:
    if ( (a3 & 0x80u) == 0LL )
      goto LABEL_40;
  }
  v30 = 0;
  v29 = (unsigned __int16 **)(a2 + 56);
  v31 = 1;
  v24 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Parameters", &v30);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v29);
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A3,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v24,
      (int)v29);
    return (unsigned int)v24;
  }
  if ( a3 )
  {
LABEL_40:
    if ( (a3 & 0x100) == 0 )
      goto LABEL_44;
  }
  v30 = 0;
  v29 = (unsigned __int16 **)(a2 + 64);
  v31 = 1;
  v25 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"CurrentDirectoryPath", &v30);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v29);
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v25,
      (int)v29);
    return (unsigned int)v25;
  }
  if ( a3 )
  {
LABEL_44:
    if ( (a3 & 0x200) == 0 )
      goto LABEL_48;
  }
  v30 = 0;
  v29 = (unsigned __int16 **)(a2 + 72);
  v31 = 1;
  v26 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Executable", &v30);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v29);
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4AB,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v26,
      (int)v29);
    return (unsigned int)v26;
  }
  if ( a3 )
  {
LABEL_48:
    if ( (a3 & 0x400) == 0 )
      goto LABEL_52;
  }
  v30 = 0;
  v29 = (unsigned __int16 **)(a2 + 80);
  v31 = 1;
  v27 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Entrypoint", &v30);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v29);
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4AF,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v27,
      (int)v29);
    return (unsigned int)v27;
  }
  if ( a3 )
  {
LABEL_52:
    if ( (a3 & 0x800) == 0 )
      goto LABEL_55;
  }
  v30 = 0;
  v29 = (unsigned __int16 **)(a2 + 88);
  v31 = 1;
  v28 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"StartPage", &v30);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v29);
  if ( v28 >= 0 )
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
      (const char *)(unsigned int)v28,
      (int)v29);
    return (unsigned int)v28;
  }
}

```

## disassembly

```asm
0x180008b20  mov     [rsp-18h+arg_0], rbx
0x180008b25  mov     [rsp-18h+arg_8], rsi
0x180008b2a  mov     [rsp-18h+arg_10], rdi
0x180008b2f  push    rbp
0x180008b30  push    r14
0x180008b32  push    r15
0x180008b34  mov     rbp, rsp
0x180008b37  sub     rsp, 40h
0x180008b3b  mov     r14, r9
0x180008b3e  mov     rbx, r8
0x180008b41  mov     rsi, rdx
0x180008b44  mov     r15, rcx
0x180008b47  test    r8, r8
0x180008b4a  jz      short loc_180008B51
0x180008b4c  test    bl, 1
0x180008b4f  jz      short loc_180008BAD
0x180008b51  mov     rcx, [rcx]
0x180008b54  lea     r8, [rdx+8]
0x180008b58  lea     rdx, aPackage; "Package"
0x180008b5f  call    cs:__imp_SRCacheContext_GetField_UInt32
0x180008b66  nop     dword ptr [rax+rax+00h]
0x180008b6b  mov     edi, eax
0x180008b6d  test    eax, eax
0x180008b6f  jns     short loc_180008BA8
0x180008b71  mov     rcx, [rbp+18h]; this
0x180008b75  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008b7c  mov     r9d, eax; char *
0x180008b7f  mov     edx, 221h; void *
0x180008b84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b89  mov     rcx, [rbp+18h]; this
0x180008b8d  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008b94  mov     r9d, edi; char *
0x180008b97  mov     edx, 487h; void *
0x180008b9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ba1  mov     eax, edi
0x180008ba3  jmp     loc_180008FF1
0x180008ba8  test    rbx, rbx
0x180008bab  jz      short loc_180008BB2
0x180008bad  test    bl, 2
0x180008bb0  jz      short loc_180008BEF
0x180008bb2  lea     r8, [rsi+10h]; unsigned int *
0x180008bb6  mov     rcx, r15; this
0x180008bb9  lea     rdx, aIndex; "Index"
0x180008bc0  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180008bc5  mov     edi, eax
0x180008bc7  test    eax, eax
0x180008bc9  jns     short loc_180008BEA
0x180008bcb  mov     rcx, [rbp+18h]; this
0x180008bcf  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008bd6  mov     r9d, eax; char *
0x180008bd9  mov     edx, 48Bh; void *
0x180008bde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008be3  mov     eax, edi
0x180008be5  jmp     loc_180008FF1
0x180008bea  test    rbx, rbx
0x180008bed  jz      short loc_180008BF4
0x180008bef  test    bl, 4
0x180008bf2  jz      short loc_180008C50
0x180008bf4  mov     rcx, [r15]
0x180008bf7  lea     r8, [rsi+14h]
0x180008bfb  lea     rdx, aFlags; "Flags"
0x180008c02  call    cs:__imp_SRCacheContext_GetField_UInt32
0x180008c09  nop     dword ptr [rax+rax+00h]
0x180008c0e  mov     edi, eax
0x180008c10  test    eax, eax
0x180008c12  jns     short loc_180008C4B
0x180008c14  mov     rcx, [rbp+18h]; this
0x180008c18  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008c1f  mov     r9d, eax; char *
0x180008c22  mov     edx, 221h; void *
0x180008c27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c2c  mov     rcx, [rbp+18h]; this
0x180008c30  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008c37  mov     r9d, edi; char *
0x180008c3a  mov     edx, 48Fh; void *
0x180008c3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c44  mov     eax, edi
0x180008c46  jmp     loc_180008FF1
0x180008c4b  test    rbx, rbx
0x180008c4e  jz      short loc_180008C59
0x180008c50  test    bl, 8
0x180008c53  jz      loc_180008CF6
0x180008c59  mov     rcx, [r15]
0x180008c5c  lea     rax, [rsi+18h]
0x180008c60  lea     r8, [rbp+var_18]
0x180008c64  mov     [rbp+var_20], rax
0x180008c68  lea     rdx, aPackagerelativ; "PackageRelativeApplicationId"
0x180008c6f  mov     [rbp+var_18], 0
0x180008c77  mov     [rbp+var_10], 1
0x180008c7b  call    cs:__imp_SRCacheContext_GetField_String
0x180008c82  nop     dword ptr [rax+rax+00h]
0x180008c87  mov     edi, eax
0x180008c89  test    eax, eax
0x180008c8b  jns     short loc_180008CA7
0x180008c8d  mov     rcx, [rbp+18h]; this
0x180008c91  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008c98  mov     r9d, eax; char *
0x180008c9b  mov     edx, 246h; void *
0x180008ca0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ca5  jmp     short loc_180008CA9
0x180008ca7  xor     edi, edi
0x180008ca9  cmp     [rbp+var_10], 0
0x180008cad  jz      short loc_180008CCE
0x180008caf  mov     rdx, [rbp+var_20]
0x180008cb3  mov     rax, [rbp+var_18]
0x180008cb7  mov     rcx, [rdx]
0x180008cba  mov     [rdx], rax
0x180008cbd  test    rcx, rcx
0x180008cc0  jz      short loc_180008CCE
0x180008cc2  call    cs:__imp_SRCache_Free
0x180008cc9  nop     dword ptr [rax+rax+00h]
0x180008cce  test    edi, edi
0x180008cd0  jns     short loc_180008CF1
0x180008cd2  mov     rcx, [rbp+18h]; this
0x180008cd6  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008cdd  mov     r9d, edi; char *
0x180008ce0  mov     edx, 493h; void *
0x180008ce5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008cea  mov     eax, edi
0x180008cec  jmp     loc_180008FF1
0x180008cf1  test    rbx, rbx
0x180008cf4  jz      short loc_180008CFB
0x180008cf6  test    bl, 10h
0x180008cf9  jz      short loc_180008D55
0x180008cfb  lea     rax, [rsi+20h]
0x180008cff  mov     [rbp+var_18], 0
0x180008d07  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180008d0b  mov     [rbp+var_20], rax
0x180008d0f  lea     rdx, aApplicationuse_0; "ApplicationUserModelId"
0x180008d16  mov     [rbp+var_10], 1
0x180008d1a  mov     rcx, r15; this
0x180008d1d  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180008d22  lea     rcx, [rbp+var_20]
0x180008d26  mov     edi, eax
0x180008d28  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180008d2d  test    edi, edi
0x180008d2f  jns     short loc_180008D50
0x180008d31  mov     rcx, [rbp+18h]; this
0x180008d35  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008d3c  mov     r9d, edi; char *
0x180008d3f  mov     edx, 497h; void *
0x180008d44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d49  mov     eax, edi
0x180008d4b  jmp     loc_180008FF1
0x180008d50  test    rbx, rbx
0x180008d53  jz      short loc_180008D5A
0x180008d55  test    bl, 20h
0x180008d58  jz      short loc_180008DB6
0x180008d5a  mov     rcx, [r15]
0x180008d5d  lea     r8, [rsi+28h]
0x180008d61  lea     rdx, aActivation; "Activation"
0x180008d68  call    cs:__imp_SRCacheContext_GetField_UInt32
0x180008d6f  nop     dword ptr [rax+rax+00h]
0x180008d74  mov     edi, eax
0x180008d76  test    eax, eax
0x180008d78  jns     short loc_180008DB1
0x180008d7a  mov     rcx, [rbp+18h]; this
0x180008d7e  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008d85  mov     r9d, eax; char *
0x180008d88  mov     edx, 221h; void *
0x180008d8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d92  mov     rcx, [rbp+18h]; this
0x180008d96  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008d9d  mov     r9d, edi; char *
0x180008da0  mov     edx, 49Bh; void *
0x180008da5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008daa  mov     eax, edi
0x180008dac  jmp     loc_180008FF1
0x180008db1  test    rbx, rbx
0x180008db4  jz      short loc_180008DBB
0x180008db6  test    bl, 40h
0x180008db9  jz      short loc_180008E15
0x180008dbb  lea     rax, [rsi+30h]
0x180008dbf  mov     [rbp+var_18], 0
0x180008dc7  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180008dcb  mov     [rbp+var_20], rax
0x180008dcf  lea     rdx, aHostid; "HostId"
0x180008dd6  mov     [rbp+var_10], 1
0x180008dda  mov     rcx, r15; this
0x180008ddd  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180008de2  lea     rcx, [rbp+var_20]
0x180008de6  mov     edi, eax
0x180008de8  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180008ded  test    edi, edi
0x180008def  jns     short loc_180008E10
0x180008df1  mov     rcx, [rbp+18h]; this
0x180008df5  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008dfc  mov     r9d, edi; char *
0x180008dff  mov     edx, 49Fh; void *
0x180008e04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e09  mov     eax, edi
0x180008e0b  jmp     loc_180008FF1
0x180008e10  test    rbx, rbx
0x180008e13  jz      short loc_180008E19
0x180008e15  test    bl, bl
0x180008e17  jns     short loc_180008E73
0x180008e19  lea     rax, [rsi+38h]
0x180008e1d  mov     [rbp+var_18], 0
0x180008e25  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180008e29  mov     [rbp+var_20], rax
0x180008e2d  lea     rdx, aParameters; "Parameters"
0x180008e34  mov     [rbp+var_10], 1
0x180008e38  mov     rcx, r15; this
0x180008e3b  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180008e40  lea     rcx, [rbp+var_20]
0x180008e44  mov     edi, eax
0x180008e46  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180008e4b  test    edi, edi
0x180008e4d  jns     short loc_180008E6E
0x180008e4f  mov     rcx, [rbp+18h]; this
0x180008e53  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008e5a  mov     r9d, edi; char *
0x180008e5d  mov     edx, 4A3h; void *
0x180008e62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e67  mov     eax, edi
0x180008e69  jmp     loc_180008FF1
0x180008e6e  test    rbx, rbx
0x180008e71  jz      short loc_180008E7A
0x180008e73  bt      rbx, 8
0x180008e78  jnb     short loc_180008ED4
0x180008e7a  lea     rax, [rsi+40h]
0x180008e7e  mov     [rbp+var_18], 0
0x180008e86  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180008e8a  mov     [rbp+var_20], rax
0x180008e8e  lea     rdx, aCurrentdirecto; "CurrentDirectoryPath"
0x180008e95  mov     [rbp+var_10], 1
0x180008e99  mov     rcx, r15; this
0x180008e9c  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180008ea1  lea     rcx, [rbp+var_20]
0x180008ea5  mov     edi, eax
0x180008ea7  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180008eac  test    edi, edi
0x180008eae  jns     short loc_180008ECF
0x180008eb0  mov     rcx, [rbp+18h]; this
0x180008eb4  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008ebb  mov     r9d, edi; char *
0x180008ebe  mov     edx, 4A7h; void *
0x180008ec3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ec8  mov     eax, edi
0x180008eca  jmp     loc_180008FF1
0x180008ecf  test    rbx, rbx
0x180008ed2  jz      short loc_180008EDB
0x180008ed4  bt      rbx, 9
0x180008ed9  jnb     short loc_180008F35
0x180008edb  lea     rax, [rsi+48h]
0x180008edf  mov     [rbp+var_18], 0
0x180008ee7  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180008eeb  mov     [rbp+var_20], rax
0x180008eef  lea     rdx, aExecutable; "Executable"
0x180008ef6  mov     [rbp+var_10], 1
0x180008efa  mov     rcx, r15; this
0x180008efd  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180008f02  lea     rcx, [rbp+var_20]
0x180008f06  mov     edi, eax
0x180008f08  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180008f0d  test    edi, edi
0x180008f0f  jns     short loc_180008F30
0x180008f11  mov     rcx, [rbp+18h]; this
0x180008f15  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008f1c  mov     r9d, edi; char *
0x180008f1f  mov     edx, 4ABh; void *
0x180008f24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f29  mov     eax, edi
0x180008f2b  jmp     loc_180008FF1
0x180008f30  test    rbx, rbx
0x180008f33  jz      short loc_180008F3C
0x180008f35  bt      rbx, 0Ah
0x180008f3a  jnb     short loc_180008F93
0x180008f3c  lea     rax, [rsi+50h]
0x180008f40  mov     [rbp+var_18], 0
0x180008f48  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180008f4c  mov     [rbp+var_20], rax
0x180008f50  lea     rdx, aEntrypoint; "Entrypoint"
0x180008f57  mov     [rbp+var_10], 1
0x180008f5b  mov     rcx, r15; this
0x180008f5e  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180008f63  lea     rcx, [rbp+var_20]
0x180008f67  mov     edi, eax
0x180008f69  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180008f6e  test    edi, edi
0x180008f70  jns     short loc_180008F8E
0x180008f72  mov     rcx, [rbp+18h]; this
0x180008f76  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008f7d  mov     r9d, edi; char *
0x180008f80  mov     edx, 4AFh; void *
0x180008f85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f8a  mov     eax, edi
0x180008f8c  jmp     short loc_180008FF1
0x180008f8e  test    rbx, rbx
0x180008f91  jz      short loc_180008F9A
0x180008f93  bt      rbx, 0Bh
0x180008f98  jnb     short loc_180008FEC
0x180008f9a  lea     rax, [rsi+58h]
0x180008f9e  mov     [rbp+var_18], 0
0x180008fa6  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180008faa  mov     [rbp+var_20], rax
0x180008fae  lea     rdx, aStartpage; "StartPage"
0x180008fb5  mov     [rbp+var_10], 1
0x180008fb9  mov     rcx, r15; this
0x180008fbc  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
  ... truncated ...
```
