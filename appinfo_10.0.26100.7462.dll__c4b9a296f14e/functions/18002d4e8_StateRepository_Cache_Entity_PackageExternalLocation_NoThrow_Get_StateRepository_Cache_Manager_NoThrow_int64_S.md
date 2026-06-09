# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)

- ea: `0x18002d4e8`
- end: `0x18002d60f`
- name: `?Get@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002dbb8`

## callees

- `0x180007ae0`
- `0x180007c78`
- `0x18000edb0`
- `0x18002d4e8`
- `0x18003538c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d572`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d5ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d572`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d5ed`

## string_xrefs

- `0x18002d511`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002d555`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002d5be`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        bool *a5)
{
  int Field; // ebx
  bool *v9; // r14
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  _QWORD *v13; // [rsp+20h] [rbp-20h] BYREF
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
0x18002d4e8  mov     [rsp-18h+arg_0], rbx
0x18002d4ed  mov     [rsp-18h+arg_8], rsi
0x18002d4f2  mov     [rsp-18h+arg_10], r8
0x18002d4f7  push    rbp
0x18002d4f8  push    rdi
0x18002d4f9  push    r14
0x18002d4fb  mov     rbp, rsp
0x18002d4fe  sub     rsp, 40h
0x18002d502  mov     rsi, r9
0x18002d505  mov     rdi, rdx
0x18002d508  test    rdx, rdx
0x18002d50b  jnz     short loc_18002D531
0x18002d50d  mov     rcx, [rbp+18h]; this
0x18002d511  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d518  mov     ebx, 80070057h
0x18002d51d  mov     edx, 0A1h; void *
0x18002d522  mov     r9d, ebx; char *
0x18002d525  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d52a  mov     eax, ebx
0x18002d52c  jmp     loc_18002D5FB
0x18002d531  mov     r14, [rbp+arg_20]
0x18002d535  lea     r8, [rbp+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18002d539  and     [rbp+arg_10], 0
0x18002d53e  mov     r9, r14; bool *
0x18002d541  call    ?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18002d546  mov     ebx, eax
0x18002d548  test    eax, eax
0x18002d54a  jns     short loc_18002D580
0x18002d54c  mov     edx, 0A4h; void *
0x18002d551  mov     rcx, [rbp+18h]; this
0x18002d555  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d55c  mov     r9d, ebx; char *
0x18002d55f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d564  mov     rcx, [rbp+arg_10]
0x18002d568  and     [rbp+arg_10], 0
0x18002d56d  test    rcx, rcx
0x18002d570  jz      short loc_18002D52A
0x18002d572  call    cs:__imp_SRCacheContext_Close
0x18002d579  nop     dword ptr [rax+rax+00h]
0x18002d57e  jmp     short loc_18002D52A
0x18002d580  cmp     byte ptr [r14], 0
0x18002d584  jz      short loc_18002D5DF
0x18002d586  and     [rbp+var_18], 0
0x18002d58b  lea     rax, [rsi+18h]
0x18002d58f  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18002d593  mov     [rbp+var_20], rax
0x18002d597  lea     rdx, aPath_0; "Path"
0x18002d59e  mov     [rbp+var_10], 1
0x18002d5a2  lea     rcx, [rbp+arg_10]; this
0x18002d5a6  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18002d5ab  lea     rcx, [rbp+var_20]
0x18002d5af  mov     ebx, eax
0x18002d5b1  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18002d5b6  test    ebx, ebx
0x18002d5b8  jns     short loc_18002D5DC
0x18002d5ba  mov     rcx, [rbp+18h]; this
0x18002d5be  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d5c5  mov     r9d, ebx; char *
0x18002d5c8  mov     edx, 269h; void *
0x18002d5cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d5d2  mov     edx, 0A9h
0x18002d5d7  jmp     loc_18002D551
0x18002d5dc  mov     [rsi], rdi
0x18002d5df  mov     rcx, [rbp+arg_10]
0x18002d5e3  and     [rbp+arg_10], 0
0x18002d5e8  test    rcx, rcx
0x18002d5eb  jz      short loc_18002D5F9
0x18002d5ed  call    cs:__imp_SRCacheContext_Close
0x18002d5f4  nop     dword ptr [rax+rax+00h]
0x18002d5f9  xor     eax, eax
0x18002d5fb  mov     rbx, [rsp+40h+arg_0]
0x18002d600  mov     rsi, [rsp+40h+arg_8]
0x18002d605  add     rsp, 40h
0x18002d609  pop     r14
0x18002d60b  pop     rdi
0x18002d60c  pop     rbp
0x18002d60d  retn
```
