# DllCanUnloadNow

- ea: `0x18000cec0`
- end: `0x18000cf2d`
- name: `DllCanUnloadNow`
- size: `109`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003e3b`
- `0x180006214`
- `0x18000842c`
- `0x180008c34`
- `0x18000904c`
- `0x18000cec0`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000cf1b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  Microsoft::WRL::Details *v0; // rax
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx
  bool v2; // r9
  PSLIST_ENTRY v3; // rax
  struct _SLIST_ENTRY *Next; // rbx

  v0 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  if ( !Microsoft::WRL::Details::TerminateMap(v0, v1, 0, v2)
    || (unsigned int)std::_Atomic_storage<int,4>::load(&`winrt::get_module_lock'::`2'::s_lock) )
  {
    return 1;
  }
  v3 = WINRT_IMPL_InterlockedFlushSList(&`winrt::impl::get_factory_cache'::`2'::cache);
  if ( v3 )
  {
    do
    {
      Next = v3->Next;
      winrt::impl::factory_cache_entry_base::clear((winrt::impl::factory_cache_entry_base *)&v3[-1]);
      v3 = Next;
    }
    while ( Next );
  }
  return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x18000cec0  push    rbx
0x18000cec2  sub     rsp, 20h
0x18000cec6  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18000cecb  xor     r8d, r8d; unsigned __int16 *
0x18000cece  mov     rcx, rax; this
0x18000ced1  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000ced6  test    al, al
0x18000ced8  jz      short loc_18000CF22
0x18000ceda  lea     rcx, ?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000cee1  call    ?load@?$_Atomic_storage@H$03@std@@QEBAHW4memory_order@2@@Z; std::_Atomic_storage<int,4>::load(std::memory_order)
0x18000cee6  test    eax, eax
0x18000cee8  jnz     short loc_18000CF22
0x18000ceea  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000cef1  call    WINRT_IMPL_InterlockedFlushSList
0x18000cef6  test    rax, rax
0x18000cef9  jz      short loc_18000CF0F
0x18000cefb  mov     rbx, [rax]
0x18000cefe  lea     rcx, [rax-10h]; this
0x18000cf02  call    ?clear@factory_cache_entry_base@impl@winrt@@QEAAXXZ; winrt::impl::factory_cache_entry_base::clear(void)
0x18000cf07  mov     rax, rbx
0x18000cf0a  test    rbx, rbx
0x18000cf0d  jnz     short loc_18000CEFB
0x18000cf0f  lea     rcx, gPFactory
0x18000cf16  add     rsp, 20h
0x18000cf1a  pop     rbx
0x18000cf1b  jmp     cs:__imp_NdrDllCanUnloadNow
0x18000cf22  mov     eax, 1
0x18000cf27  add     rsp, 20h
0x18000cf2b  pop     rbx
0x18000cf2c  retn
```
