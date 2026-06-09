# StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)

- ea: `0x1800075b0`
- end: `0x180007acc`
- name: `?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `1308`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180006510`
- `0x180007000`

## callees

- `0x1800075b0`
- `0x180007ae0`
- `0x180007c30`
- `0x180007c78`
- `0x18000edb0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000788f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180007937`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000788f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180007937`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800078d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000797e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800078d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000797e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800076cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180007730`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800076cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180007730`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt64` at `0x180007814`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt64` at `0x180007814`

## string_xrefs

- `0x180007924`: `MutableLink`
- `0x180007618`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18000765a`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18000769c`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800076fd`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18000775e`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800077a0`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800077e2`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180007842`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800078ea`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180007992`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800079f3`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180007a37`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180007a95`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800076e5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180007746`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000782a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800078a5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000794d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000787c`: `InstalledLocation`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int Field; // edi
  int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  unsigned int v13; // edi
  int Field_UInt32; // eax
  unsigned int v15; // edi
  int v16; // eax
  unsigned int v17; // edi
  int v18; // eax
  unsigned int v19; // edi
  int v20; // eax
  unsigned int v21; // edi
  int Field_UInt64; // eax
  unsigned int v23; // edi
  __int64 v24; // rcx
  int Field_String; // eax
  int v26; // edi
  unsigned __int16 *v27; // rcx
  __int64 v28; // rcx
  int v29; // eax
  int v30; // edi
  unsigned __int16 *v31; // rcx
  int v32; // edi
  int v33; // eax
  unsigned int v34; // edi
  int v35; // ebx
  unsigned __int16 **v36; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v37; // [rsp+28h] [rbp-18h] BYREF
  char v38; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]

  if ( a3 && (a3 & 1) == 0 )
    goto LABEL_6;
  v37 = 0;
  v36 = (unsigned __int16 **)(a2 + 8);
  v38 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageFullName", &v37);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v36);
  if ( Field < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x820,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)Field,
      (int)v36);
    return (unsigned int)Field;
  }
  if ( a3 )
  {
LABEL_6:
    if ( (a3 & 2) == 0 )
      goto LABEL_10;
  }
  v10 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageFamily", (unsigned int *)(a2 + 16));
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x824,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v10,
      (int)v36);
    return v11;
  }
  if ( a3 )
  {
LABEL_10:
    if ( (a3 & 4) == 0 )
      goto LABEL_14;
  }
  v12 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageType", (unsigned int *)(a2 + 24));
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x828,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v12,
      (int)v36);
    return v13;
  }
  if ( a3 )
  {
LABEL_14:
    if ( (a3 & 8) == 0 )
      goto LABEL_18;
  }
  Field_UInt32 = SRCacheContext_GetField_UInt32(*(_QWORD *)a1, L"Flags", a2 + 28);
  v15 = Field_UInt32;
  if ( Field_UInt32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt32,
      (int)v36);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)v15,
      (int)v36);
    return v15;
  }
  if ( a3 )
  {
LABEL_18:
    if ( (a3 & 0x10) == 0 )
      goto LABEL_22;
  }
  v16 = SRCacheContext_GetField_UInt32(*(_QWORD *)a1, L"Flags2", a2 + 32);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      (int)v36);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x830,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)v17,
      (int)v36);
    return v17;
  }
  if ( a3 )
  {
LABEL_22:
    if ( (a3 & 0x20) == 0 )
      goto LABEL_26;
  }
  v18 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageOrigin", (unsigned int *)(a2 + 36));
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x834,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v18,
      (int)v36);
    return v19;
  }
  if ( a3 )
  {
LABEL_26:
    if ( (a3 & 0x40) == 0 )
      goto LABEL_30;
  }
  v20 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Volume", (unsigned int *)(a2 + 40));
  v21 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x838,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v20,
      (int)v36);
    return v21;
  }
  if ( a3 )
  {
LABEL_30:
    if ( (a3 & 0x80u) == 0LL )
      goto LABEL_34;
  }
  Field_UInt64 = SRCacheContext_GetField_UInt64(*(_QWORD *)a1, L"OSMaxVersionTested", a2 + 48);
  v23 = Field_UInt64;
  if ( Field_UInt64 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x230,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt64,
      (int)v36);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)v23,
      (int)v36);
    return v23;
  }
  if ( a3 )
  {
LABEL_34:
    if ( (a3 & 0x100) == 0 )
      goto LABEL_44;
  }
  v24 = *(_QWORD *)a1;
  v36 = (unsigned __int16 **)(a2 + 56);
  v37 = 0;
  v38 = 1;
  Field_String = SRCacheContext_GetField_String(v24, L"InstalledLocation", &v37);
  v26 = Field_String;
  if ( Field_String >= 0 )
    v26 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v36);
  if ( v38 )
  {
    v27 = *v36;
    *v36 = v37;
    if ( v27 )
      SRCache_Free();
  }
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x840,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v26,
      (int)v36);
    return (unsigned int)v26;
  }
  if ( a3 )
  {
LABEL_44:
    if ( (a3 & 0x200) == 0 )
      goto LABEL_54;
  }
  v28 = *(_QWORD *)a1;
  v36 = (unsigned __int16 **)(a2 + 64);
  v37 = 0;
  v38 = 1;
  v29 = SRCacheContext_GetField_String(v28, L"MutableLink", &v37);
  v30 = v29;
  if ( v29 >= 0 )
    v30 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v29,
      (int)v36);
  if ( v38 )
  {
    v31 = *v36;
    *v36 = v37;
    if ( v31 )
      SRCache_Free();
  }
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x844,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v30,
      (int)v36);
    return (unsigned int)v30;
  }
  if ( a3 )
  {
LABEL_54:
    if ( (a3 & 0x400) == 0 )
      goto LABEL_58;
  }
  v37 = 0;
  v36 = (unsigned __int16 **)(a2 + 72);
  v38 = 1;
  v32 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"MutableLocation", &v37);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v36);
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x848,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v32,
      (int)v36);
    return (unsigned int)v32;
  }
  if ( a3 )
  {
LABEL_58:
    if ( (a3 & 0x800) == 0 )
      goto LABEL_62;
  }
  v33 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"TargetDeviceFamilyName", (unsigned int *)(a2 + 80));
  v34 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v33,
      (int)v36);
    return v34;
  }
  if ( a3 )
  {
LABEL_62:
    if ( (a3 & 0x1000) == 0 )
      goto LABEL_65;
  }
  v37 = 0;
  v36 = (unsigned __int16 **)(a2 + 88);
  v38 = 1;
  v35 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"DisplayName", &v37);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v36);
  if ( v35 >= 0 )
  {
LABEL_65:
    *(_QWORD *)a2 = a4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x850,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v35,
      (int)v36);
    return (unsigned int)v35;
  }
}

```

## disassembly

```asm
0x1800075b0  mov     [rsp-18h+arg_0], rbx
0x1800075b5  mov     [rsp-18h+arg_8], rsi
0x1800075ba  mov     [rsp-18h+arg_10], rdi
0x1800075bf  push    rbp
0x1800075c0  push    r14
0x1800075c2  push    r15
0x1800075c4  mov     rbp, rsp
0x1800075c7  sub     rsp, 40h
0x1800075cb  mov     r15, r9
0x1800075ce  mov     rbx, r8
0x1800075d1  mov     rsi, rdx
0x1800075d4  mov     r14, rcx
0x1800075d7  test    r8, r8
0x1800075da  jz      short loc_1800075E1
0x1800075dc  test    bl, 1
0x1800075df  jz      short loc_180007638
0x1800075e1  lea     rax, [rdx+8]
0x1800075e5  mov     [rbp+var_18], 0
0x1800075ed  lea     rdx, aPackagefullnam; "PackageFullName"
0x1800075f4  mov     [rbp+var_20], rax
0x1800075f8  lea     r8, [rbp+var_18]; unsigned __int16 **
0x1800075fc  mov     [rbp+var_10], 1
0x180007600  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180007605  lea     rcx, [rbp+var_20]
0x180007609  mov     edi, eax
0x18000760b  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180007610  test    edi, edi
0x180007612  jns     short loc_180007633
0x180007614  mov     rcx, [rbp+18h]; this
0x180007618  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000761f  mov     r9d, edi; char *
0x180007622  mov     edx, 820h; void *
0x180007627  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000762c  mov     eax, edi
0x18000762e  jmp     loc_180007AB2
0x180007633  test    rbx, rbx
0x180007636  jz      short loc_18000763D
0x180007638  test    bl, 2
0x18000763b  jz      short loc_18000767A
0x18000763d  lea     r8, [rsi+10h]; unsigned int *
0x180007641  mov     rcx, r14; this
0x180007644  lea     rdx, aPackagefamily; "PackageFamily"
0x18000764b  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180007650  mov     edi, eax
0x180007652  test    eax, eax
0x180007654  jns     short loc_180007675
0x180007656  mov     rcx, [rbp+18h]; this
0x18000765a  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007661  mov     r9d, eax; char *
0x180007664  mov     edx, 824h; void *
0x180007669  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000766e  mov     eax, edi
0x180007670  jmp     loc_180007AB2
0x180007675  test    rbx, rbx
0x180007678  jz      short loc_18000767F
0x18000767a  test    bl, 4
0x18000767d  jz      short loc_1800076BC
0x18000767f  lea     r8, [rsi+18h]; unsigned int *
0x180007683  mov     rcx, r14; this
0x180007686  lea     rdx, aPackagetype; "PackageType"
0x18000768d  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180007692  mov     edi, eax
0x180007694  test    eax, eax
0x180007696  jns     short loc_1800076B7
0x180007698  mov     rcx, [rbp+18h]; this
0x18000769c  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800076a3  mov     r9d, eax; char *
0x1800076a6  mov     edx, 828h; void *
0x1800076ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076b0  mov     eax, edi
0x1800076b2  jmp     loc_180007AB2
0x1800076b7  test    rbx, rbx
0x1800076ba  jz      short loc_1800076C1
0x1800076bc  test    bl, 8
0x1800076bf  jz      short loc_18000771D
0x1800076c1  mov     rcx, [r14]
0x1800076c4  lea     r8, [rsi+1Ch]
0x1800076c8  lea     rdx, aFlags; "Flags"
0x1800076cf  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800076d6  nop     dword ptr [rax+rax+00h]
0x1800076db  mov     edi, eax
0x1800076dd  test    eax, eax
0x1800076df  jns     short loc_180007718
0x1800076e1  mov     rcx, [rbp+18h]; this
0x1800076e5  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800076ec  mov     r9d, eax; char *
0x1800076ef  mov     edx, 221h; void *
0x1800076f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076f9  mov     rcx, [rbp+18h]; this
0x1800076fd  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007704  mov     r9d, edi; char *
0x180007707  mov     edx, 82Ch; void *
0x18000770c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007711  mov     eax, edi
0x180007713  jmp     loc_180007AB2
0x180007718  test    rbx, rbx
0x18000771b  jz      short loc_180007722
0x18000771d  test    bl, 10h
0x180007720  jz      short loc_18000777E
0x180007722  mov     rcx, [r14]
0x180007725  lea     r8, [rsi+20h]
0x180007729  lea     rdx, aFlags2; "Flags2"
0x180007730  call    cs:__imp_SRCacheContext_GetField_UInt32
0x180007737  nop     dword ptr [rax+rax+00h]
0x18000773c  mov     edi, eax
0x18000773e  test    eax, eax
0x180007740  jns     short loc_180007779
0x180007742  mov     rcx, [rbp+18h]; this
0x180007746  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000774d  mov     r9d, eax; char *
0x180007750  mov     edx, 221h; void *
0x180007755  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000775a  mov     rcx, [rbp+18h]; this
0x18000775e  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007765  mov     r9d, edi; char *
0x180007768  mov     edx, 830h; void *
0x18000776d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007772  mov     eax, edi
0x180007774  jmp     loc_180007AB2
0x180007779  test    rbx, rbx
0x18000777c  jz      short loc_180007783
0x18000777e  test    bl, 20h
0x180007781  jz      short loc_1800077C0
0x180007783  lea     r8, [rsi+24h]; unsigned int *
0x180007787  mov     rcx, r14; this
0x18000778a  lea     rdx, aPackageorigin; "PackageOrigin"
0x180007791  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180007796  mov     edi, eax
0x180007798  test    eax, eax
0x18000779a  jns     short loc_1800077BB
0x18000779c  mov     rcx, [rbp+18h]; this
0x1800077a0  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800077a7  mov     r9d, eax; char *
0x1800077aa  mov     edx, 834h; void *
0x1800077af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077b4  mov     eax, edi
0x1800077b6  jmp     loc_180007AB2
0x1800077bb  test    rbx, rbx
0x1800077be  jz      short loc_1800077C5
0x1800077c0  test    bl, 40h
0x1800077c3  jz      short loc_180007802
0x1800077c5  lea     r8, [rsi+28h]; unsigned int *
0x1800077c9  mov     rcx, r14; this
0x1800077cc  lea     rdx, aVolume; "Volume"
0x1800077d3  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x1800077d8  mov     edi, eax
0x1800077da  test    eax, eax
0x1800077dc  jns     short loc_1800077FD
0x1800077de  mov     rcx, [rbp+18h]; this
0x1800077e2  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800077e9  mov     r9d, eax; char *
0x1800077ec  mov     edx, 838h; void *
0x1800077f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077f6  mov     eax, edi
0x1800077f8  jmp     loc_180007AB2
0x1800077fd  test    rbx, rbx
0x180007800  jz      short loc_180007806
0x180007802  test    bl, bl
0x180007804  jns     short loc_180007862
0x180007806  mov     rcx, [r14]
0x180007809  lea     r8, [rsi+30h]
0x18000780d  lea     rdx, aOsmaxversionte; "OSMaxVersionTested"
0x180007814  call    cs:__imp_SRCacheContext_GetField_UInt64
0x18000781b  nop     dword ptr [rax+rax+00h]
0x180007820  mov     edi, eax
0x180007822  test    eax, eax
0x180007824  jns     short loc_18000785D
0x180007826  mov     rcx, [rbp+18h]; this
0x18000782a  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007831  mov     r9d, eax; char *
0x180007834  mov     edx, 230h; void *
0x180007839  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000783e  mov     rcx, [rbp+18h]; this
0x180007842  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007849  mov     r9d, edi; char *
0x18000784c  mov     edx, 83Ch; void *
0x180007851  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007856  mov     eax, edi
0x180007858  jmp     loc_180007AB2
0x18000785d  test    rbx, rbx
0x180007860  jz      short loc_18000786D
0x180007862  bt      rbx, 8
0x180007867  jnb     loc_18000790A
0x18000786d  mov     rcx, [r14]
0x180007870  lea     rax, [rsi+38h]
0x180007874  lea     r8, [rbp+var_18]
0x180007878  mov     [rbp+var_20], rax
0x18000787c  lea     rdx, aInstalledlocat; "InstalledLocation"
0x180007883  mov     [rbp+var_18], 0
0x18000788b  mov     [rbp+var_10], 1
0x18000788f  call    cs:__imp_SRCacheContext_GetField_String
0x180007896  nop     dword ptr [rax+rax+00h]
0x18000789b  mov     edi, eax
0x18000789d  test    eax, eax
0x18000789f  jns     short loc_1800078BB
0x1800078a1  mov     rcx, [rbp+18h]; this
0x1800078a5  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800078ac  mov     r9d, eax; char *
0x1800078af  mov     edx, 246h; void *
0x1800078b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800078b9  jmp     short loc_1800078BD
0x1800078bb  xor     edi, edi
0x1800078bd  cmp     [rbp+var_10], 0
0x1800078c1  jz      short loc_1800078E2
0x1800078c3  mov     rdx, [rbp+var_20]
0x1800078c7  mov     rax, [rbp+var_18]
0x1800078cb  mov     rcx, [rdx]
0x1800078ce  mov     [rdx], rax
0x1800078d1  test    rcx, rcx
0x1800078d4  jz      short loc_1800078E2
0x1800078d6  call    cs:__imp_SRCache_Free
0x1800078dd  nop     dword ptr [rax+rax+00h]
0x1800078e2  test    edi, edi
0x1800078e4  jns     short loc_180007905
0x1800078e6  mov     rcx, [rbp+18h]; this
0x1800078ea  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800078f1  mov     r9d, edi; char *
0x1800078f4  mov     edx, 840h; void *
0x1800078f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800078fe  mov     eax, edi
0x180007900  jmp     loc_180007AB2
0x180007905  test    rbx, rbx
0x180007908  jz      short loc_180007915
0x18000790a  bt      rbx, 9
0x18000790f  jnb     loc_1800079B2
0x180007915  mov     rcx, [r14]
0x180007918  lea     rax, [rsi+40h]
0x18000791c  lea     r8, [rbp+var_18]
0x180007920  mov     [rbp+var_20], rax
0x180007924  lea     rdx, aMutablelink; "MutableLink"
0x18000792b  mov     [rbp+var_18], 0
0x180007933  mov     [rbp+var_10], 1
0x180007937  call    cs:__imp_SRCacheContext_GetField_String
0x18000793e  nop     dword ptr [rax+rax+00h]
0x180007943  mov     edi, eax
0x180007945  test    eax, eax
0x180007947  jns     short loc_180007963
0x180007949  mov     rcx, [rbp+18h]; this
0x18000794d  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007954  mov     r9d, eax; char *
0x180007957  mov     edx, 246h; void *
0x18000795c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007961  jmp     short loc_180007965
0x180007963  xor     edi, edi
0x180007965  cmp     [rbp+var_10], 0
0x180007969  jz      short loc_18000798A
0x18000796b  mov     rdx, [rbp+var_20]
0x18000796f  mov     rax, [rbp+var_18]
0x180007973  mov     rcx, [rdx]
0x180007976  mov     [rdx], rax
0x180007979  test    rcx, rcx
0x18000797c  jz      short loc_18000798A
0x18000797e  call    cs:__imp_SRCache_Free
0x180007985  nop     dword ptr [rax+rax+00h]
0x18000798a  test    edi, edi
0x18000798c  jns     short loc_1800079AD
0x18000798e  mov     rcx, [rbp+18h]; this
0x180007992  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007999  mov     r9d, edi; char *
0x18000799c  mov     edx, 844h; void *
0x1800079a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800079a6  mov     eax, edi
0x1800079a8  jmp     loc_180007AB2
0x1800079ad  test    rbx, rbx
0x1800079b0  jz      short loc_1800079B9
0x1800079b2  bt      rbx, 0Ah
0x1800079b7  jnb     short loc_180007A13
0x1800079b9  lea     rax, [rsi+48h]
0x1800079bd  mov     [rbp+var_18], 0
0x1800079c5  lea     r8, [rbp+var_18]; unsigned __int16 **
0x1800079c9  mov     [rbp+var_20], rax
0x1800079cd  lea     rdx, aMutablelocatio; "MutableLocation"
0x1800079d4  mov     [rbp+var_10], 1
0x1800079d8  mov     rcx, r14; this
0x1800079db  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800079e0  lea     rcx, [rbp+var_20]
0x1800079e4  mov     edi, eax
0x1800079e6  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800079eb  test    edi, edi
0x1800079ed  jns     short loc_180007A0E
0x1800079ef  mov     rcx, [rbp+18h]; this
0x1800079f3  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800079fa  mov     r9d, edi; char *
0x1800079fd  mov     edx, 848h; void *
0x180007a02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a07  mov     eax, edi
0x180007a09  jmp     loc_180007AB2
0x180007a0e  test    rbx, rbx
0x180007a11  jz      short loc_180007A1A
0x180007a13  bt      rbx, 0Bh
0x180007a18  jnb     short loc_180007A54
0x180007a1a  lea     r8, [rsi+50h]; unsigned int *
0x180007a1e  mov     rcx, r14; this
0x180007a21  lea     rdx, aTargetdevicefa; "TargetDeviceFamilyName"
0x180007a28  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180007a2d  mov     edi, eax
0x180007a2f  test    eax, eax
0x180007a31  jns     short loc_180007A4F
0x180007a33  mov     rcx, [rbp+18h]; this
0x180007a37  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
  ... truncated ...
```
