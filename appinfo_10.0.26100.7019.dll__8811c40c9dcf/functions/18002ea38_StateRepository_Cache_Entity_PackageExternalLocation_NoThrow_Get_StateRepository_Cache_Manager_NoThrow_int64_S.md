# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)

- ea: `0x18002ea38`
- end: `0x18002eb5f`
- name: `?Get@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002f108`

## callees

- `0x180007ae0`
- `0x180007c78`
- `0x18000ee70`
- `0x18002ea38`
- `0x18003501c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002eac2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002eb3d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002eac2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002eb3d`

## string_xrefs

- `0x18002ea61`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002eaa5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18002eb0e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

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
0x18002ea38  mov     [rsp-18h+arg_0], rbx
0x18002ea3d  mov     [rsp-18h+arg_8], rsi
0x18002ea42  mov     [rsp-18h+arg_10], r8
0x18002ea47  push    rbp
0x18002ea48  push    rdi
0x18002ea49  push    r14
0x18002ea4b  mov     rbp, rsp
0x18002ea4e  sub     rsp, 40h
0x18002ea52  mov     rsi, r9
0x18002ea55  mov     rdi, rdx
0x18002ea58  test    rdx, rdx
0x18002ea5b  jnz     short loc_18002EA81
0x18002ea5d  mov     rcx, [rbp+18h]; this
0x18002ea61  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ea68  mov     ebx, 80070057h
0x18002ea6d  mov     edx, 0A1h; void *
0x18002ea72  mov     r9d, ebx; char *
0x18002ea75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ea7a  mov     eax, ebx
0x18002ea7c  jmp     loc_18002EB4B
0x18002ea81  mov     r14, [rbp+arg_20]
0x18002ea85  lea     r8, [rbp+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18002ea89  and     [rbp+arg_10], 0
0x18002ea8e  mov     r9, r14; bool *
0x18002ea91  call    ?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18002ea96  mov     ebx, eax
0x18002ea98  test    eax, eax
0x18002ea9a  jns     short loc_18002EAD0
0x18002ea9c  mov     edx, 0A4h; void *
0x18002eaa1  mov     rcx, [rbp+18h]; this
0x18002eaa5  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002eaac  mov     r9d, ebx; char *
0x18002eaaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002eab4  mov     rcx, [rbp+arg_10]
0x18002eab8  and     [rbp+arg_10], 0
0x18002eabd  test    rcx, rcx
0x18002eac0  jz      short loc_18002EA7A
0x18002eac2  call    cs:__imp_SRCacheContext_Close
0x18002eac9  nop     dword ptr [rax+rax+00h]
0x18002eace  jmp     short loc_18002EA7A
0x18002ead0  cmp     byte ptr [r14], 0
0x18002ead4  jz      short loc_18002EB2F
0x18002ead6  and     [rbp+var_18], 0
0x18002eadb  lea     rax, [rsi+18h]
0x18002eadf  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18002eae3  mov     [rbp+var_20], rax
0x18002eae7  lea     rdx, aPath_0; "Path"
0x18002eaee  mov     [rbp+var_10], 1
0x18002eaf2  lea     rcx, [rbp+arg_10]; this
0x18002eaf6  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18002eafb  lea     rcx, [rbp+var_20]
0x18002eaff  mov     ebx, eax
0x18002eb01  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18002eb06  test    ebx, ebx
0x18002eb08  jns     short loc_18002EB2C
0x18002eb0a  mov     rcx, [rbp+18h]; this
0x18002eb0e  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002eb15  mov     r9d, ebx; char *
0x18002eb18  mov     edx, 269h; void *
0x18002eb1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002eb22  mov     edx, 0A9h
0x18002eb27  jmp     loc_18002EAA1
0x18002eb2c  mov     [rsi], rdi
0x18002eb2f  mov     rcx, [rbp+arg_10]
0x18002eb33  and     [rbp+arg_10], 0
0x18002eb38  test    rcx, rcx
0x18002eb3b  jz      short loc_18002EB49
0x18002eb3d  call    cs:__imp_SRCacheContext_Close
0x18002eb44  nop     dword ptr [rax+rax+00h]
0x18002eb49  xor     eax, eax
0x18002eb4b  mov     rbx, [rsp+40h+arg_0]
0x18002eb50  mov     rsi, [rsp+40h+arg_8]
0x18002eb55  add     rsp, 40h
0x18002eb59  pop     r14
0x18002eb5b  pop     rdi
0x18002eb5c  pop     rbp
0x18002eb5d  retn
```
