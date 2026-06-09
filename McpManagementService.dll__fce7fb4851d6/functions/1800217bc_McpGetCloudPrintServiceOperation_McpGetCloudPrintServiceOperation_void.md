# McpGetCloudPrintServiceOperation::McpGetCloudPrintServiceOperation(void)

- ea: `0x1800217bc`
- end: `0x18002187f`
- name: `??0McpGetCloudPrintServiceOperation@@QEAA@XZ`
- size: `195`
- prototype: `McpGetCloudPrintServiceOperation *__fastcall(McpGetCloudPrintServiceOperation *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800215d8`

## callees

- `0x180006aec`
- `0x1800217bc`
- `0x180021888`
- `0x180021b1c`
- `0x18002b010`

## string_xrefs

- `0x180021858`: `McpGetCloudPrintServiceOperation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
McpGetCloudPrintServiceOperation *__fastcall McpGetCloudPrintServiceOperation::McpGetCloudPrintServiceOperation(
        McpGetCloudPrintServiceOperation *this)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>((__int64)this);
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMcpGetCloudPrintServiceOperation,IFastRundown>::`vftable'{for `IMcpGetCloudPrintServiceOperation'};
  *((_QWORD *)this + 1) = &McpGetCloudPrintServiceOperation::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &McpGetCloudPrintServiceOperation::`vftable'{for `IMcpGetCloudPrintServiceOperation'};
  *((_QWORD *)this + 1) = &McpGetCloudPrintServiceOperation::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'};
  *((_WORD *)this + 12) = 1;
  *((_BYTE *)this + 26) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = -2147019873;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  McpManagement::SvcHostServerReference::SvcHostServerReference(
    (McpGetCloudPrintServiceOperation *)((char *)this + 160),
    L"McpGetCloudPrintServiceOperation");
  McpManagement::SvcHostServerReference::AddRef((McpGetCloudPrintServiceOperation *)((char *)this + 160));
  return this;
}

```

## disassembly

```asm
0x1800217bc  mov     [rsp+arg_8], rbx
0x1800217c1  mov     [rsp+arg_0], rcx
0x1800217c6  push    rdi
0x1800217c7  sub     rsp, 20h
0x1800217cb  mov     rdi, rcx
0x1800217ce  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMcpGetCloudPrintServiceResult@@UIFastRundown@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>(void)
0x1800217d3  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMcpGetCloudPrintServiceOperation@@UIFastRundown@@@WRL@Microsoft@@6BIMcpGetCloudPrintServiceOperation@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMcpGetCloudPrintServiceOperation,IFastRundown>::`vftable'{for `IMcpGetCloudPrintServiceOperation'}
0x1800217da  mov     [rdi], rcx
0x1800217dd  lea     rax, ??_7McpGetCloudPrintServiceOperation@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIFastRundown@@@Details@WRL@Microsoft@@@; const McpGetCloudPrintServiceOperation::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'}
0x1800217e4  mov     [rdi+8], rax
0x1800217e8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800217ef  xor     ebx, ebx
0x1800217f1  test    rcx, rcx
0x1800217f4  jz      short loc_180021803
0x1800217f6  mov     rax, [rcx]
0x1800217f9  mov     rax, [rax+8]
0x1800217fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021802  nop
0x180021803  lea     rax, ??_7McpGetCloudPrintServiceOperation@@6BIMcpGetCloudPrintServiceOperation@@@; const McpGetCloudPrintServiceOperation::`vftable'{for `IMcpGetCloudPrintServiceOperation'}
0x18002180a  mov     [rdi], rax
0x18002180d  lea     rax, ??_7McpGetCloudPrintServiceOperation@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIFastRundown@@@Details@WRL@Microsoft@@@; const McpGetCloudPrintServiceOperation::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFastRundown>'}
0x180021814  mov     [rdi+8], rax
0x180021818  mov     word ptr [rdi+18h], 1
0x18002181e  mov     [rdi+1Ah], bl
0x180021821  mov     [rdi+20h], rbx
0x180021825  mov     [rdi+28h], rbx
0x180021829  mov     [rdi+30h], rbx
0x18002182d  mov     [rdi+38h], rbx
0x180021831  mov     [rdi+40h], rbx
0x180021835  mov     dword ptr [rdi+48h], 8007139Fh
0x18002183c  mov     [rdi+88h], rbx
0x180021843  mov     [rdi+90h], rbx
0x18002184a  mov     [rdi+98h], rbx
0x180021851  lea     rbx, [rdi+0A0h]
0x180021858  lea     rdx, aMcpgetcloudpri_0; "McpGetCloudPrintServiceOperation"
0x18002185f  mov     rcx, rbx; this
0x180021862  call    ??0SvcHostServerReference@McpManagement@@QEAA@PEBG@Z; McpManagement::SvcHostServerReference::SvcHostServerReference(ushort const *)
0x180021867  nop
0x180021868  mov     rcx, rbx; this
0x18002186b  call    ?AddRef@SvcHostServerReference@McpManagement@@QEAAXXZ; McpManagement::SvcHostServerReference::AddRef(void)
0x180021870  nop
0x180021871  mov     rax, rdi
0x180021874  mov     rbx, [rsp+28h+arg_8]
0x180021879  add     rsp, 20h
0x18002187d  pop     rdi
0x18002187e  retn
```
