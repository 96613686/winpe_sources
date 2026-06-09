# _lambda_8a03d23fdee2c1785e106aafab25a0f7_::_lambda_invoker_cdecl_

- ea: `0x180032970`
- end: `0x1800329ba`
- name: `_lambda_8a03d23fdee2c1785e106aafab25a0f7_::_lambda_invoker_cdecl_`
- size: `74`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180032970`
- `0x180037010`

## import_xrefs

- `ntdll!LdrAddRefDll` at `0x180032989`
- `ntdll!LdrAddRefDll` at `0x180032989`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x18003299d`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x18003299d`

## pseudocode

```c
void __fastcall lambda_8a03d23fdee2c1785e106aafab25a0f7_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        void (__fastcall **Context)(_QWORD),
        PTP_WORK Work)
{
  if ( LdrAddRefDll(0, &_ImageBase) >= 0 )
    FreeLibraryWhenCallbackReturns(Instance, &_ImageBase);
  Context[1](Context[2]);
}

```

## disassembly

```asm
0x180032970  mov     [rsp+arg_0], rbx
0x180032975  push    rdi
0x180032976  sub     rsp, 20h
0x18003297a  mov     rbx, rdx
0x18003297d  mov     rdi, rcx
0x180032980  lea     rdx, __ImageBase; BaseAddress
0x180032987  xor     ecx, ecx; Flags
0x180032989  call    cs:__imp_LdrAddRefDll
0x18003298f  test    eax, eax
0x180032991  js      short loc_1800329A3
0x180032993  lea     rdx, __ImageBase; mod
0x18003299a  mov     rcx, rdi; pci
0x18003299d  call    cs:__imp_FreeLibraryWhenCallbackReturns
0x1800329a3  mov     rcx, [rbx+10h]
0x1800329a7  mov     rax, [rbx+8]
0x1800329ab  mov     rbx, [rsp+28h+arg_0]
0x1800329b0  add     rsp, 20h
0x1800329b4  pop     rdi
0x1800329b5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
