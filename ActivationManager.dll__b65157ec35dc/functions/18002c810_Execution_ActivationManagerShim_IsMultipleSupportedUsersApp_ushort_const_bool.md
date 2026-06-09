# Execution::ActivationManagerShim::IsMultipleSupportedUsersApp(ushort const *,bool &)

- ea: `0x18002c810`
- end: `0x18002c8f8`
- name: `?IsMultipleSupportedUsersApp@ActivationManagerShim@Execution@@AEAAJPEBGAEA_N@Z`
- size: `232`
- prototype: `int(Execution::ActivationManagerShim *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180011ad0`
- `0x18006b040`

## callees

- `0x18000b5c0`
- `0x18002c810`
- `0x18002c900`
- `0x18006e9a4`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x18002c82a`
- `ntdll!RtlIsMultiSessionSku` at `0x18002c82a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18002c85a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18002c85a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002c8b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002c8e7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002c8b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002c8e7`

## string_xrefs

- `0x18002c873`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall Execution::ActivationManagerShim::IsMultipleSupportedUsersApp(
        Execution::ActivationManagerShim *this,
        const unsigned __int16 *a2,
        bool *a3)
{
  int IsEffectiveSupportedUsersMultiple; // ebx
  __int64 v6; // rdx
  Execution::ActivationManagerShim *v7; // rcx
  Execution::ActivationManagerShim *v9; // rcx
  Execution::ActivationManagerShim **v10; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+28h] [rbp-20h] BYREF
  char v12; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  Execution::ActivationManagerShim *v14; // [rsp+70h] [rbp+28h] BYREF

  v14 = this;
  *a3 = 0;
  if ( (unsigned __int8)RtlIsMultiSessionSku() )
    return 0;
  v14 = 0;
  v10 = &v14;
  v11 = 0;
  v12 = 1;
  IsEffectiveSupportedUsersMultiple = SRCacheManager_Open(0, &v11);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v10);
  if ( IsEffectiveSupportedUsersMultiple >= 0 )
  {
    IsEffectiveSupportedUsersMultiple = StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(
                                          (struct StateRepository::Cache::Manager_NoThrow *)&v14,
                                          a2,
                                          a3);
    if ( IsEffectiveSupportedUsersMultiple < 0 )
    {
      v6 = 1761;
      goto LABEL_4;
    }
    v9 = v14;
    v14 = 0;
    if ( v9 )
      SRCacheManager_Close(v9);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA5,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
    (const char *)(unsigned int)IsEffectiveSupportedUsersMultiple,
    (int)v10);
  v6 = 1760;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
    (const char *)(unsigned int)IsEffectiveSupportedUsersMultiple,
    (int)v10);
  v7 = v14;
  v14 = 0;
  if ( v7 )
    SRCacheManager_Close(v7);
  return (unsigned int)IsEffectiveSupportedUsersMultiple;
}

```

## disassembly

```asm
0x18002c810  mov     [rsp-20h+arg_0], rcx
0x18002c815  push    rbp
0x18002c816  push    rbx
0x18002c817  push    rsi
0x18002c818  push    rdi
0x18002c819  mov     rbp, rsp
0x18002c81c  sub     rsp, 48h
0x18002c820  mov     rdi, r8
0x18002c823  mov     byte ptr [r8], 0
0x18002c827  mov     rsi, rdx
0x18002c82a  call    cs:__imp_RtlIsMultiSessionSku
0x18002c830  test    al, al
0x18002c832  jnz     loc_18002C8ED
0x18002c838  lea     rax, [rbp+arg_0]
0x18002c83c  mov     [rbp+arg_0], 0
0x18002c844  lea     rdx, [rbp+var_20]
0x18002c848  mov     [rbp+var_28], rax
0x18002c84c  xor     ecx, ecx
0x18002c84e  mov     [rbp+var_20], 0
0x18002c856  mov     [rbp+var_18], 1
0x18002c85a  call    cs:__imp_SRCacheManager_Open
0x18002c860  lea     rcx, [rbp+var_28]
0x18002c864  mov     ebx, eax
0x18002c866  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18002c86b  test    ebx, ebx
0x18002c86d  jns     short loc_18002C8BA
0x18002c86f  mov     rcx, [rbp+20h]; this
0x18002c873  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c87a  mov     r9d, ebx; char *
0x18002c87d  mov     edx, 0A5h; void *
0x18002c882  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c887  mov     edx, 6E0h; void *
0x18002c88c  mov     rcx, [rbp+20h]; this
0x18002c890  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002c897  mov     r9d, ebx; char *
0x18002c89a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c89f  mov     rcx, [rbp+arg_0]
0x18002c8a3  mov     [rbp+arg_0], 0
0x18002c8ab  test    rcx, rcx
0x18002c8ae  jz      short loc_18002C8B6
0x18002c8b0  call    cs:__imp_SRCacheManager_Close
0x18002c8b6  mov     eax, ebx
0x18002c8b8  jmp     short loc_18002C8EF
0x18002c8ba  mov     r8, rdi; bool *
0x18002c8bd  lea     rcx, [rbp+arg_0]; struct StateRepository::Cache::Manager_NoThrow *
0x18002c8c1  mov     rdx, rsi; unsigned __int16 *
0x18002c8c4  call    ?GetIsEffectiveSupportedUsersMultiple@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18002c8c9  mov     ebx, eax
0x18002c8cb  test    eax, eax
0x18002c8cd  jns     short loc_18002C8D6
0x18002c8cf  mov     edx, 6E1h
0x18002c8d4  jmp     short loc_18002C88C
0x18002c8d6  mov     rcx, [rbp+arg_0]
0x18002c8da  mov     [rbp+arg_0], 0
0x18002c8e2  test    rcx, rcx
0x18002c8e5  jz      short loc_18002C8ED
0x18002c8e7  call    cs:__imp_SRCacheManager_Close
0x18002c8ed  xor     eax, eax
0x18002c8ef  add     rsp, 48h
0x18002c8f3  pop     rdi
0x18002c8f4  pop     rsi
0x18002c8f5  pop     rbx
0x18002c8f6  pop     rbp
0x18002c8f7  retn
```
