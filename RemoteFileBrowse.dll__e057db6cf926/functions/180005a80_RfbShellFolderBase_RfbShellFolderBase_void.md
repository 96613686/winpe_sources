# RfbShellFolderBase::~RfbShellFolderBase(void)

- ea: `0x180005a80`
- end: `0x180005b0f`
- name: `??1RfbShellFolderBase@@UEAA@XZ`
- size: `143`
- prototype: `void __fastcall(RfbShellFolderBase *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005a04`
- `0x180005c10`
- `0x180007864`
- `0x1800164b4`
- `0x180018b45`

## callees

- `0x180005a80`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005afe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005afe`

## pseudocode

```c
void __fastcall RfbShellFolderBase::~RfbShellFolderBase(RfbShellFolderBase *this)
{
  volatile signed __int32 *v2; // rbx
  void *v3; // rcx

  *(_QWORD *)this = &RfbShellFolderBase::`vftable';
  *((_QWORD *)this + 1) = &RfbShellFolderBase::`vftable'{for `Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *((_QWORD *)this + 2) = &RfbShellFolderBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IPersistIDList>'};
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 11);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  v3 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v3 )
    CoTaskMemFree(v3);
}

```

## disassembly

```asm
0x180005a80  mov     [rsp+arg_0], rbx
0x180005a85  push    rdi
0x180005a86  sub     rsp, 20h
0x180005a8a  lea     rax, ??_7RfbShellFolderBase@@6B@; const RfbShellFolderBase::`vftable'
0x180005a91  mov     rdi, rcx
0x180005a94  mov     [rcx], rax
0x180005a97  lea     rax, ??_7RfbShellFolderBase@@6B?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@WRL@Microsoft@@@; const RfbShellFolderBase::`vftable'{for `Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180005a9e  mov     [rcx+8], rax
0x180005aa2  lea     rax, ??_7RfbShellFolderBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIPersistIDList@@@Details@WRL@Microsoft@@@; const RfbShellFolderBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IPersistIDList>'}
0x180005aa9  mov     [rcx+10h], rax
0x180005aad  mov     rbx, [rcx+58h]
0x180005ab1  test    rbx, rbx
0x180005ab4  jz      short loc_180005AED
0x180005ab6  or      eax, 0FFFFFFFFh
0x180005ab9  lock xadd [rbx+8], eax
0x180005abe  cmp     eax, 1
0x180005ac1  jnz     short loc_180005AED
0x180005ac3  mov     rax, [rbx]
0x180005ac6  mov     rcx, rbx
0x180005ac9  mov     rax, [rax]
0x180005acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad1  or      eax, 0FFFFFFFFh
0x180005ad4  lock xadd [rbx+0Ch], eax
0x180005ad9  cmp     eax, 1
0x180005adc  jnz     short loc_180005AED
0x180005ade  mov     rax, [rbx]
0x180005ae1  mov     rcx, rbx
0x180005ae4  mov     rax, [rax+8]
0x180005ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aed  mov     rcx, [rdi+38h]; pv
0x180005af1  mov     qword ptr [rdi+38h], 0
0x180005af9  test    rcx, rcx
0x180005afc  jz      short loc_180005B04
0x180005afe  call    cs:__imp_CoTaskMemFree
0x180005b04  mov     rbx, [rsp+28h+arg_0]
0x180005b09  add     rsp, 20h
0x180005b0d  pop     rdi
0x180005b0e  retn
```
