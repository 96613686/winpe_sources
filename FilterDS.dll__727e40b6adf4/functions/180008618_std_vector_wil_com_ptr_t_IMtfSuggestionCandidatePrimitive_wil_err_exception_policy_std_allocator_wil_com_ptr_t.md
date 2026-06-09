# std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>>::~vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>>(void)

- ea: `0x180008618`
- end: `0x180008686`
- name: `??1?$vector@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180009890`
- `0x18002216c`

## callees

- `0x180008618`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008659`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008659`

## pseudocode

```c
void __fastcall std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>::~vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>(
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
0x180008618  mov     [rsp+arg_0], rbx
0x18000861d  mov     [rsp+arg_8], rsi
0x180008622  push    rdi
0x180008623  sub     rsp, 20h
0x180008627  mov     rbx, rcx
0x18000862a  mov     rdi, [rcx]
0x18000862d  test    rdi, rdi
0x180008630  jz      short loc_180008676
0x180008632  mov     rsi, [rcx+8]
0x180008636  jmp     short loc_180008651
0x180008638  mov     rcx, [rdi]
0x18000863b  test    rcx, rcx
0x18000863e  jz      short loc_18000864D
0x180008640  mov     rax, [rcx]
0x180008643  mov     rax, [rax+10h]
0x180008647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000864c  nop
0x18000864d  add     rdi, 8
0x180008651  cmp     rdi, rsi
0x180008654  jnz     short loc_180008638
0x180008656  mov     rcx, [rbx]
0x180008659  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000865f  mov     qword ptr [rbx], 0
0x180008666  mov     qword ptr [rbx+8], 0
0x18000866e  mov     qword ptr [rbx+10h], 0
0x180008676  mov     rbx, [rsp+28h+arg_0]
0x18000867b  mov     rsi, [rsp+28h+arg_8]
0x180008680  add     rsp, 20h
0x180008684  pop     rdi
0x180008685  retn
```
