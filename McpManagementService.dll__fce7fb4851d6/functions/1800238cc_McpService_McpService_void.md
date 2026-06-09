# McpService::McpService(void)

- ea: `0x1800238cc`
- end: `0x180023961`
- name: `??0McpService@@QEAA@XZ`
- size: `149`
- prototype: `McpService *__fastcall(McpService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800237f0`

## callees

- `0x180006aec`
- `0x180021888`
- `0x180021b1c`
- `0x1800238cc`
- `0x18002b010`

## string_xrefs

- `0x180023938`: `McpService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
McpService *__fastcall McpService::McpService(McpService *this)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>((__int64)this);
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMcpService,IFastRundown>::`vftable'{for `IMcpService'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMcpService,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &McpService::`vftable'{for `IMcpService'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMcpService,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'};
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  McpManagement::SvcHostServerReference::SvcHostServerReference((McpService *)((char *)this + 56), L"McpService");
  McpManagement::SvcHostServerReference::AddRef((McpService *)((char *)this + 56));
  return this;
}

```

## disassembly

```asm
0x1800238cc  mov     [rsp+arg_8], rbx
0x1800238d1  mov     [rsp+arg_0], rcx
0x1800238d6  push    rdi
0x1800238d7  sub     rsp, 20h
0x1800238db  mov     rdi, rcx
0x1800238de  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMcpGetCloudPrintServiceResult@@UIFastRundown@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>(void)
0x1800238e3  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMcpService@@UIFastRundown@@@WRL@Microsoft@@6BIMcpService@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMcpService,IFastRundown>::`vftable'{for `IMcpService'}
0x1800238ea  mov     [rdi], rcx
0x1800238ed  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMcpService@@UIFastRundown@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIFastRundown@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMcpService,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'}
0x1800238f4  mov     [rdi+8], rax
0x1800238f8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800238ff  xor     ebx, ebx
0x180023901  test    rcx, rcx
0x180023904  jz      short loc_180023913
0x180023906  mov     rax, [rcx]
0x180023909  mov     rax, [rax+8]
0x18002390d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023912  nop
0x180023913  lea     rax, ??_7McpService@@6BIMcpService@@@; const McpService::`vftable'{for `IMcpService'}
0x18002391a  mov     [rdi], rax
0x18002391d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMcpService@@UIFastRundown@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIFastRundown@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMcpService,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'}
0x180023924  mov     [rdi+8], rax
0x180023928  mov     [rdi+18h], rbx
0x18002392c  mov     [rdi+20h], rbx
0x180023930  mov     [rdi+28h], rbx
0x180023934  mov     [rdi+30h], rbx
0x180023938  lea     rdx, aMcpservice; "McpService"
0x18002393f  lea     rcx, [rdi+38h]; this
0x180023943  call    ??0SvcHostServerReference@McpManagement@@QEAA@PEBG@Z; McpManagement::SvcHostServerReference::SvcHostServerReference(ushort const *)
0x180023948  nop
0x180023949  lea     rcx, [rdi+38h]; this
0x18002394d  call    ?AddRef@SvcHostServerReference@McpManagement@@QEAAXXZ; McpManagement::SvcHostServerReference::AddRef(void)
0x180023952  nop
0x180023953  mov     rax, rdi
0x180023956  mov     rbx, [rsp+28h+arg_8]
0x18002395b  add     rsp, 20h
0x18002395f  pop     rdi
0x180023960  retn
```
