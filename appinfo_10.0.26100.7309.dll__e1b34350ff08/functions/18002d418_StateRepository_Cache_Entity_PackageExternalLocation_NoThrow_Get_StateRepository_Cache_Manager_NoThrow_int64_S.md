# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)

- ea: `0x18002d418`
- end: `0x18002d53f`
- name: `?Get@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002dae8`

## callees

- `0x180007ae0`
- `0x180007c78`
- `0x18000edb0`
- `0x18002d418`
- `0x1800350cc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d4a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d51d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d4a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d51d`

## string_xrefs

- `0x18002d441`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002d485`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002d4ee`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

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
0x18002d418  mov     [rsp-18h+arg_0], rbx
0x18002d41d  mov     [rsp-18h+arg_8], rsi
0x18002d422  mov     [rsp-18h+arg_10], r8
0x18002d427  push    rbp
0x18002d428  push    rdi
0x18002d429  push    r14
0x18002d42b  mov     rbp, rsp
0x18002d42e  sub     rsp, 40h
0x18002d432  mov     rsi, r9
0x18002d435  mov     rdi, rdx
0x18002d438  test    rdx, rdx
0x18002d43b  jnz     short loc_18002D461
0x18002d43d  mov     rcx, [rbp+18h]; this
0x18002d441  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d448  mov     ebx, 80070057h
0x18002d44d  mov     edx, 0A1h; void *
0x18002d452  mov     r9d, ebx; char *
0x18002d455  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d45a  mov     eax, ebx
0x18002d45c  jmp     loc_18002D52B
0x18002d461  mov     r14, [rbp+arg_20]
0x18002d465  lea     r8, [rbp+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18002d469  and     [rbp+arg_10], 0
0x18002d46e  mov     r9, r14; bool *
0x18002d471  call    ?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18002d476  mov     ebx, eax
0x18002d478  test    eax, eax
0x18002d47a  jns     short loc_18002D4B0
0x18002d47c  mov     edx, 0A4h; void *
0x18002d481  mov     rcx, [rbp+18h]; this
0x18002d485  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d48c  mov     r9d, ebx; char *
0x18002d48f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d494  mov     rcx, [rbp+arg_10]
0x18002d498  and     [rbp+arg_10], 0
0x18002d49d  test    rcx, rcx
0x18002d4a0  jz      short loc_18002D45A
0x18002d4a2  call    cs:__imp_SRCacheContext_Close
0x18002d4a9  nop     dword ptr [rax+rax+00h]
0x18002d4ae  jmp     short loc_18002D45A
0x18002d4b0  cmp     byte ptr [r14], 0
0x18002d4b4  jz      short loc_18002D50F
0x18002d4b6  and     [rbp+var_18], 0
0x18002d4bb  lea     rax, [rsi+18h]
0x18002d4bf  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18002d4c3  mov     [rbp+var_20], rax
0x18002d4c7  lea     rdx, aPath_0; "Path"
0x18002d4ce  mov     [rbp+var_10], 1
0x18002d4d2  lea     rcx, [rbp+arg_10]; this
0x18002d4d6  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18002d4db  lea     rcx, [rbp+var_20]
0x18002d4df  mov     ebx, eax
0x18002d4e1  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18002d4e6  test    ebx, ebx
0x18002d4e8  jns     short loc_18002D50C
0x18002d4ea  mov     rcx, [rbp+18h]; this
0x18002d4ee  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d4f5  mov     r9d, ebx; char *
0x18002d4f8  mov     edx, 269h; void *
0x18002d4fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d502  mov     edx, 0A9h
0x18002d507  jmp     loc_18002D481
0x18002d50c  mov     [rsi], rdi
0x18002d50f  mov     rcx, [rbp+arg_10]
0x18002d513  and     [rbp+arg_10], 0
0x18002d518  test    rcx, rcx
0x18002d51b  jz      short loc_18002D529
0x18002d51d  call    cs:__imp_SRCacheContext_Close
0x18002d524  nop     dword ptr [rax+rax+00h]
0x18002d529  xor     eax, eax
0x18002d52b  mov     rbx, [rsp+40h+arg_0]
0x18002d530  mov     rsi, [rsp+40h+arg_8]
0x18002d535  add     rsp, 40h
0x18002d539  pop     r14
0x18002d53b  pop     rdi
0x18002d53c  pop     rbp
0x18002d53d  retn
```
