# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)

- ea: `0x180031ba0`
- end: `0x180031cc6`
- name: `?Get@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `294`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180031f90`

## callees

- `0x18000720c`
- `0x18000d930`
- `0x18000eed0`
- `0x18001d56c`
- `0x180031ba0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180031c30`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180031cab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180031c30`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180031cab`

## string_xrefs

- `0x180031bc9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x180031c10`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x180031c79`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        bool *a5)
{
  int Field; // ebx
  bool *v9; // r14
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 *v13; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v14; // [rsp+28h] [rbp-18h] BYREF
  char v15; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v17; // [rsp+70h] [rbp+30h] BYREF

  v17 = a3;
  if ( !a2 )
  {
    Field = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)0x80070057LL,
      (int)v13);
    return (unsigned int)Field;
  }
  v9 = a5;
  v17 = 0;
  Field = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
            a1,
            a2,
            (struct StateRepository::Cache::Context_NoThrow *)&v17,
            a5);
  if ( Field < 0 )
  {
    v10 = 164;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    v14 = 0;
    v13 = a4 + 3;
    v15 = 1;
    Field = StateRepository::Cache::Context_NoThrow::GetField(
              (StateRepository::Cache::Context_NoThrow *)&v17,
              L"Path",
              &v14);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v13);
    if ( Field < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x269,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
        (const char *)(unsigned int)Field,
        (int)v13);
      v10 = 169;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
        (const char *)(unsigned int)Field,
        (int)v13);
      v11 = v17;
      v17 = 0;
      if ( v11 )
        SRCacheContext_Close(v11);
      return (unsigned int)Field;
    }
    *a4 = a2;
  }
  v12 = v17;
  v17 = 0;
  if ( v12 )
    SRCacheContext_Close(v12);
  return 0;
}

```

## disassembly

```asm
0x180031ba0  mov     [rsp-18h+arg_0], rbx
0x180031ba5  mov     [rsp-18h+arg_8], rsi
0x180031baa  mov     [rsp-18h+arg_10], r8
0x180031baf  push    rbp
0x180031bb0  push    rdi
0x180031bb1  push    r14
0x180031bb3  mov     rbp, rsp
0x180031bb6  sub     rsp, 40h
0x180031bba  mov     rsi, r9
0x180031bbd  mov     rdi, rdx
0x180031bc0  test    rdx, rdx
0x180031bc3  jnz     short loc_180031BE9
0x180031bc5  mov     rcx, [rbp+18h]; this
0x180031bc9  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180031bd0  mov     ebx, 80070057h
0x180031bd5  mov     edx, 0A1h; void *
0x180031bda  mov     r9d, ebx; char *
0x180031bdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031be2  mov     eax, ebx
0x180031be4  jmp     loc_180031CB3
0x180031be9  mov     r14, [rbp+arg_20]
0x180031bed  lea     r8, [rbp+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x180031bf1  mov     r9, r14; bool *
0x180031bf4  mov     [rbp+arg_10], 0
0x180031bfc  call    ?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180031c01  mov     ebx, eax
0x180031c03  test    eax, eax
0x180031c05  jns     short loc_180031C38
0x180031c07  mov     edx, 0A4h; void *
0x180031c0c  mov     rcx, [rbp+18h]; this
0x180031c10  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180031c17  mov     r9d, ebx; char *
0x180031c1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031c1f  mov     rcx, [rbp+arg_10]
0x180031c23  mov     [rbp+arg_10], 0
0x180031c2b  test    rcx, rcx
0x180031c2e  jz      short loc_180031BE2
0x180031c30  call    cs:__imp_SRCacheContext_Close
0x180031c36  jmp     short loc_180031BE2
0x180031c38  cmp     byte ptr [r14], 0
0x180031c3c  jz      short loc_180031C9A
0x180031c3e  lea     rax, [rsi+18h]
0x180031c42  mov     [rbp+var_18], 0
0x180031c4a  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180031c4e  mov     [rbp+var_20], rax
0x180031c52  lea     rdx, aPath_0; "Path"
0x180031c59  mov     [rbp+var_10], 1
0x180031c5d  lea     rcx, [rbp+arg_10]; this
0x180031c61  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180031c66  lea     rcx, [rbp+var_20]
0x180031c6a  mov     ebx, eax
0x180031c6c  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180031c71  test    ebx, ebx
0x180031c73  jns     short loc_180031C97
0x180031c75  mov     rcx, [rbp+18h]; this
0x180031c79  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180031c80  mov     r9d, ebx; char *
0x180031c83  mov     edx, 269h; void *
0x180031c88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031c8d  mov     edx, 0A9h
0x180031c92  jmp     loc_180031C0C
0x180031c97  mov     [rsi], rdi
0x180031c9a  mov     rcx, [rbp+arg_10]
0x180031c9e  mov     [rbp+arg_10], 0
0x180031ca6  test    rcx, rcx
0x180031ca9  jz      short loc_180031CB1
0x180031cab  call    cs:__imp_SRCacheContext_Close
0x180031cb1  xor     eax, eax
0x180031cb3  mov     rbx, [rsp+40h+arg_0]
0x180031cb8  mov     rsi, [rsp+40h+arg_8]
0x180031cbd  add     rsp, 40h
0x180031cc1  pop     r14
0x180031cc3  pop     rdi
0x180031cc4  pop     rbp
0x180031cc5  retn
```
