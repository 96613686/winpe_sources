# DllCanUnloadNow

- ea: `0x180010580`
- end: `0x1800105ec`
- name: `DllCanUnloadNow`
- size: `108`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009778`
- `0x180010580`
- `0x180010984`
- `0x180042010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x1800105b3`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1800105b3`

## string_xrefs

- `0x1800105c4`: `PrxDllCanUnloadNow`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> *v0; // rax
  int CanUnloadNow; // ebx
  void *retaddr; // [rsp+38h] [rbp+0h]

  v0 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  if ( (*(unsigned int (__fastcall **)(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> *))(*(_QWORD *)v0->data_ + 24LL))(v0) )
    return 1;
  CanUnloadNow = NdrDllCanUnloadNow(&gPFactory);
  if ( CanUnloadNow >= 0 )
    return 0;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    0x83u,
    "onecoreuap\\base\\appmodel\\statemanager\\winrt\\srv\\abiservermodule.cpp",
    CanUnloadNow,
    "PrxDllCanUnloadNow");
  return CanUnloadNow;
}

```

## disassembly

```asm
0x180010580  push    rbx
0x180010582  sub     rsp, 30h
0x180010586  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18001058b  mov     rdx, rax
0x18001058e  mov     rcx, [rax]
0x180010591  mov     rax, [rcx+18h]
0x180010595  mov     rcx, rdx
0x180010598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001059d  test    eax, eax
0x18001059f  jz      short loc_1800105AC
0x1800105a1  mov     eax, 1
0x1800105a6  add     rsp, 30h
0x1800105aa  pop     rbx
0x1800105ab  retn
0x1800105ac  lea     rcx, gPFactory; pPSFactoryBuffer
0x1800105b3  call    cs:__imp_NdrDllCanUnloadNow
0x1800105b9  mov     ebx, eax
0x1800105bb  test    eax, eax
0x1800105bd  jns     short loc_1800105E8
0x1800105bf  mov     rcx, [rsp+38h]; callerReturnAddress
0x1800105c4  lea     rax, aPrxdllcanunloa; "PrxDllCanUnloadNow"
0x1800105cb  mov     r9d, ebx; hr
0x1800105ce  mov     [rsp+38h+formatString], rax; formatString
0x1800105d3  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800105da  mov     edx, 83h; lineNumber
0x1800105df  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800105e4  mov     eax, ebx
0x1800105e6  jmp     short loc_1800105A6
0x1800105e8  xor     eax, eax
0x1800105ea  jmp     short loc_1800105A6
```
