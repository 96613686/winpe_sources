# McpGetCloudPrintServiceResult::McpGetCloudPrintServiceResult(void)

- ea: `0x1800221bc`
- end: `0x180022251`
- name: `??0McpGetCloudPrintServiceResult@@QEAA@XZ`
- size: `149`
- prototype: `McpGetCloudPrintServiceResult *__fastcall(McpGetCloudPrintServiceResult *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022084`

## callees

- `0x180006aec`
- `0x180021888`
- `0x180021b1c`
- `0x1800221bc`
- `0x18002b010`

## string_xrefs

- `0x180022228`: `McpGetCloudPrintServiceResult`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
McpGetCloudPrintServiceResult *__fastcall McpGetCloudPrintServiceResult::McpGetCloudPrintServiceResult(
        McpGetCloudPrintServiceResult *this)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>((__int64)this);
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMcpGetCloudPrintServiceResult,IFastRundown>::`vftable'{for `IMcpGetCloudPrintServiceResult'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMcpGetCloudPrintServiceResult,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &McpGetCloudPrintServiceResult::`vftable'{for `IMcpGetCloudPrintServiceResult'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMcpGetCloudPrintServiceResult,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'};
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  McpManagement::SvcHostServerReference::SvcHostServerReference(
    (McpGetCloudPrintServiceResult *)((char *)this + 64),
    L"McpGetCloudPrintServiceResult");
  McpManagement::SvcHostServerReference::AddRef((McpGetCloudPrintServiceResult *)((char *)this + 64));
  return this;
}

```

## disassembly

```asm
0x1800221bc  mov     [rsp+arg_8], rbx
0x1800221c1  mov     [rsp+arg_0], rcx
0x1800221c6  push    rdi
0x1800221c7  sub     rsp, 20h
0x1800221cb  mov     rdi, rcx
0x1800221ce  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMcpGetCloudPrintServiceResult@@UIFastRundown@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>(void)
0x1800221d3  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMcpGetCloudPrintServiceResult@@UIFastRundown@@@WRL@Microsoft@@6BIMcpGetCloudPrintServiceResult@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMcpGetCloudPrintServiceResult,IFastRundown>::`vftable'{for `IMcpGetCloudPrintServiceResult'}
0x1800221da  mov     [rdi], rcx
0x1800221dd  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMcpGetCloudPrintServiceResult@@UIFastRundown@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIFastRundown@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMcpGetCloudPrintServiceResult,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'}
0x1800221e4  mov     [rdi+8], rax
0x1800221e8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800221ef  xor     ebx, ebx
0x1800221f1  test    rcx, rcx
0x1800221f4  jz      short loc_180022203
0x1800221f6  mov     rax, [rcx]
0x1800221f9  mov     rax, [rax+8]
0x1800221fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022202  nop
0x180022203  lea     rax, ??_7McpGetCloudPrintServiceResult@@6BIMcpGetCloudPrintServiceResult@@@; const McpGetCloudPrintServiceResult::`vftable'{for `IMcpGetCloudPrintServiceResult'}
0x18002220a  mov     [rdi], rax
0x18002220d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMcpGetCloudPrintServiceResult@@UIFastRundown@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIFastRundown@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMcpGetCloudPrintServiceResult,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'}
0x180022214  mov     [rdi+8], rax
0x180022218  mov     [rdi+20h], rbx
0x18002221c  mov     [rdi+28h], rbx
0x180022220  mov     [rdi+30h], rbx
0x180022224  mov     [rdi+38h], rbx
0x180022228  lea     rdx, aMcpgetcloudpri_1; "McpGetCloudPrintServiceResult"
0x18002222f  lea     rcx, [rdi+40h]; this
0x180022233  call    ??0SvcHostServerReference@McpManagement@@QEAA@PEBG@Z; McpManagement::SvcHostServerReference::SvcHostServerReference(ushort const *)
0x180022238  nop
0x180022239  lea     rcx, [rdi+40h]; this
0x18002223d  call    ?AddRef@SvcHostServerReference@McpManagement@@QEAAXXZ; McpManagement::SvcHostServerReference::AddRef(void)
0x180022242  nop
0x180022243  mov     rax, rdi
0x180022246  mov     rbx, [rsp+28h+arg_8]
0x18002224b  add     rsp, 20h
0x18002224f  pop     rdi
0x180022250  retn
```
