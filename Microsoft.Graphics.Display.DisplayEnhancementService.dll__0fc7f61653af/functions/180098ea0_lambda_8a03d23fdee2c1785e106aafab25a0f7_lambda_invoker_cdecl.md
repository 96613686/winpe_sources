# _lambda_8a03d23fdee2c1785e106aafab25a0f7_::_lambda_invoker_cdecl_

- ea: `0x180098ea0`
- end: `0x180098eea`
- name: `_lambda_8a03d23fdee2c1785e106aafab25a0f7_::_lambda_invoker_cdecl_`
- size: `74`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180098ea0`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x180098ecd`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x180098ecd`
- `ntdll!LdrAddRefDll` at `0x180098eb9`
- `ntdll!LdrAddRefDll` at `0x180098eb9`

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
0x180098ea0  mov     [rsp+arg_0], rbx
0x180098ea5  push    rdi
0x180098ea6  sub     rsp, 20h
0x180098eaa  mov     rbx, rdx
0x180098ead  mov     rdi, rcx
0x180098eb0  lea     rdx, __ImageBase; BaseAddress
0x180098eb7  xor     ecx, ecx; Flags
0x180098eb9  call    cs:__imp_LdrAddRefDll
0x180098ebf  test    eax, eax
0x180098ec1  js      short loc_180098ED3
0x180098ec3  lea     rdx, __ImageBase; mod
0x180098eca  mov     rcx, rdi; pci
0x180098ecd  call    cs:__imp_FreeLibraryWhenCallbackReturns
0x180098ed3  mov     rcx, [rbx+10h]
0x180098ed7  mov     rax, [rbx+8]
0x180098edb  mov     rbx, [rsp+28h+arg_0]
0x180098ee0  add     rsp, 20h
0x180098ee4  pop     rdi
0x180098ee5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
