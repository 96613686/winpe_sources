# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)

- ea: `0x180009fa4`
- end: `0x18000a0ca`
- name: `?Get@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `294`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a914`

## callees

- `0x1800075e4`
- `0x180009444`
- `0x180009fa4`
- `0x18000b130`
- `0x18000b454`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a034`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a0af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a034`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a0af`

## string_xrefs

- `0x180009fcd`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18000a014`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18000a07d`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExternalLocation.hpp`

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
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExternalLocation.hpp",
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
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExternalLocation.hpp",
        (const char *)(unsigned int)Field,
        (int)v13);
      v10 = 169;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExternalLocation.hpp",
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
0x180009fa4  mov     [rsp-18h+arg_0], rbx
0x180009fa9  mov     [rsp-18h+arg_8], rsi
0x180009fae  mov     [rsp-18h+arg_10], r8
0x180009fb3  push    rbp
0x180009fb4  push    rdi
0x180009fb5  push    r14
0x180009fb7  mov     rbp, rsp
0x180009fba  sub     rsp, 40h
0x180009fbe  mov     rsi, r9
0x180009fc1  mov     rdi, rdx
0x180009fc4  test    rdx, rdx
0x180009fc7  jnz     short loc_180009FED
0x180009fc9  mov     rcx, [rbp+18h]; this
0x180009fcd  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\StateRepositor"...
0x180009fd4  mov     ebx, 80070057h
0x180009fd9  mov     edx, 0A1h; void *
0x180009fde  mov     r9d, ebx; char *
0x180009fe1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009fe6  mov     eax, ebx
0x180009fe8  jmp     loc_18000A0B7
0x180009fed  mov     r14, [rbp+arg_20]
0x180009ff1  lea     r8, [rbp+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x180009ff5  mov     r9, r14; bool *
0x180009ff8  mov     [rbp+arg_10], 0
0x18000a000  call    ?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18000a005  mov     ebx, eax
0x18000a007  test    eax, eax
0x18000a009  jns     short loc_18000A03C
0x18000a00b  mov     edx, 0A4h; void *
0x18000a010  mov     rcx, [rbp+18h]; this
0x18000a014  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a01b  mov     r9d, ebx; char *
0x18000a01e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a023  mov     rcx, [rbp+arg_10]
0x18000a027  mov     [rbp+arg_10], 0
0x18000a02f  test    rcx, rcx
0x18000a032  jz      short loc_180009FE6
0x18000a034  call    cs:__imp_SRCacheContext_Close
0x18000a03a  jmp     short loc_180009FE6
0x18000a03c  cmp     byte ptr [r14], 0
0x18000a040  jz      short loc_18000A09E
0x18000a042  lea     rax, [rsi+18h]
0x18000a046  mov     [rbp+var_18], 0
0x18000a04e  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18000a052  mov     [rbp+var_20], rax
0x18000a056  lea     rdx, aPath; "Path"
0x18000a05d  mov     [rbp+var_10], 1
0x18000a061  lea     rcx, [rbp+arg_10]; this
0x18000a065  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000a06a  lea     rcx, [rbp+var_20]
0x18000a06e  mov     ebx, eax
0x18000a070  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18000a075  test    ebx, ebx
0x18000a077  jns     short loc_18000A09B
0x18000a079  mov     rcx, [rbp+18h]; this
0x18000a07d  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a084  mov     r9d, ebx; char *
0x18000a087  mov     edx, 269h; void *
0x18000a08c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a091  mov     edx, 0A9h
0x18000a096  jmp     loc_18000A010
0x18000a09b  mov     [rsi], rdi
0x18000a09e  mov     rcx, [rbp+arg_10]
0x18000a0a2  mov     [rbp+arg_10], 0
0x18000a0aa  test    rcx, rcx
0x18000a0ad  jz      short loc_18000A0B5
0x18000a0af  call    cs:__imp_SRCacheContext_Close
0x18000a0b5  xor     eax, eax
0x18000a0b7  mov     rbx, [rsp+40h+arg_0]
0x18000a0bc  mov     rsi, [rsp+40h+arg_8]
0x18000a0c1  add     rsp, 40h
0x18000a0c5  pop     r14
0x18000a0c7  pop     rdi
0x18000a0c8  pop     rbp
0x18000a0c9  retn
```
