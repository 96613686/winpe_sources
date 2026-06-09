# std::vector<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>>::~vector<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>>(void)

- ea: `0x1800088d0`
- end: `0x18000893e`
- name: `??1?$vector@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008944`

## callees

- `0x1800088d0`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008911`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008911`

## pseudocode

```c
void __fastcall std::vector<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>::~vector<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>(
        __int64 a1)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi

  v2 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(_QWORD **)(a1 + 8);
    while ( v2 != v3 )
    {
      if ( *v2 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
      ++v2;
    }
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x1800088d0  mov     [rsp+arg_0], rbx
0x1800088d5  mov     [rsp+arg_8], rsi
0x1800088da  push    rdi
0x1800088db  sub     rsp, 20h
0x1800088df  mov     rbx, rcx
0x1800088e2  mov     rdi, [rcx]
0x1800088e5  test    rdi, rdi
0x1800088e8  jz      short loc_18000892E
0x1800088ea  mov     rsi, [rcx+8]
0x1800088ee  jmp     short loc_180008909
0x1800088f0  mov     rcx, [rdi]
0x1800088f3  test    rcx, rcx
0x1800088f6  jz      short loc_180008905
0x1800088f8  mov     rax, [rcx]
0x1800088fb  mov     rax, [rax+10h]
0x1800088ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008904  nop
0x180008905  add     rdi, 8
0x180008909  cmp     rdi, rsi
0x18000890c  jnz     short loc_1800088F0
0x18000890e  mov     rcx, [rbx]
0x180008911  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008917  mov     qword ptr [rbx], 0
0x18000891e  mov     qword ptr [rbx+8], 0
0x180008926  mov     qword ptr [rbx+10h], 0
0x18000892e  mov     rbx, [rsp+28h+arg_0]
0x180008933  mov     rsi, [rsp+28h+arg_8]
0x180008938  add     rsp, 20h
0x18000893c  pop     rdi
0x18000893d  retn
```
