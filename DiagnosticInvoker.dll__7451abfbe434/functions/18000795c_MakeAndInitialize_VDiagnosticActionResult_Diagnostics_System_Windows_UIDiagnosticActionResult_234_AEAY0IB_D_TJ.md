# ??$MakeAndInitialize@VDiagnosticActionResult@Diagnostics@System@Windows@@UIDiagnosticActionResult@234@AEAY0IB@D$$TJ@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIDiagnosticActionResult@Diagnostics@System@Windows@@@WRL@Microsoft@@@012@AEAY0IB@D$$QEA$$T$$QEAJ@Z

- ea: `0x18000795c`
- end: `0x180007a23`
- name: `??$MakeAndInitialize@VDiagnosticActionResult@Diagnostics@System@Windows@@UIDiagnosticActionResult@234@AEAY0IB@D$$TJ@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIDiagnosticActionResult@Diagnostics@System@Windows@@@WRL@Microsoft@@@012@AEAY0IB@D$$QEA$$T$$QEAJ@Z`
- size: `199`
- prototype: `__int64 __fastcall(__int64 *, char *, struct Windows::Foundation::Collections::IPropertySet **, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000881c`

## callees

- `0x1800022fc`
- `0x18000795c`
- `0x18000edf0`
- `0x18000f490`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Diagnostics::DiagnosticActionResult,Windows::System::Diagnostics::IDiagnosticActionResult,char (&)[129],std::nullptr_t,long>(
        __int64 *a1,
        char *a2,
        struct Windows::Foundation::Collections::IPropertySet **a3,
        int *a4)
{
  __int64 v8; // rcx
  Windows::System::Diagnostics::DiagnosticActionResult *v9; // rax
  int v10; // esi
  Windows::System::Diagnostics::DiagnosticActionResult *v11; // rdi

  v8 = *a1;
  if ( v8 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  *a1 = 0;
  v9 = (Windows::System::Diagnostics::DiagnosticActionResult *)operator new(
                                                                 0xD8u,
                                                                 (const struct std::nothrow_t *)&std::nothrow);
  if ( v9 )
  {
    v11 = (Windows::System::Diagnostics::DiagnosticActionResult *)Windows::System::Diagnostics::DiagnosticActionResult::DiagnosticActionResult(v9);
    v10 = Windows::System::Diagnostics::DiagnosticActionResult::RuntimeClassInitialize(v11, a2, *a3, *a4);
    if ( v10 >= 0 )
    {
      v10 = (**(__int64 (__fastcall ***)(Windows::System::Diagnostics::DiagnosticActionResult *, GUID *, __int64 *))v11)(
              v11,
              &GUID_c265a296_e73b_4097_b28f_3442f03dd831,
              a1);
      (*(void (__fastcall **)(Windows::System::Diagnostics::DiagnosticActionResult *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    else if ( v11 )
    {
      (*(void (__fastcall **)(Windows::System::Diagnostics::DiagnosticActionResult *))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000795c  push    rbx
0x18000795e  push    rbp
0x18000795f  push    rsi
0x180007960  push    rdi
0x180007961  push    r14
0x180007963  sub     rsp, 20h
0x180007967  mov     rsi, r9
0x18000796a  mov     r14, r8
0x18000796d  mov     rbp, rdx
0x180007970  mov     rbx, rcx
0x180007973  mov     rcx, [rcx]
0x180007976  test    rcx, rcx
0x180007979  jz      short loc_18000798F
0x18000797b  mov     qword ptr [rbx], 0
0x180007982  mov     rax, [rcx]
0x180007985  mov     rax, [rax+10h]
0x180007989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000798e  nop
0x18000798f  mov     qword ptr [rbx], 0
0x180007996  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000799d  mov     ecx, 0D8h; unsigned __int64
0x1800079a2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800079a7  test    rax, rax
0x1800079aa  jnz     short loc_1800079B3
0x1800079ac  mov     esi, 8007000Eh
0x1800079b1  jmp     short loc_180007A16
0x1800079b3  mov     rcx, rax; this
0x1800079b6  call    ??0DiagnosticActionResult@Diagnostics@System@Windows@@QEAA@XZ; Windows::System::Diagnostics::DiagnosticActionResult::DiagnosticActionResult(void)
0x1800079bb  mov     rdi, rax
0x1800079be  mov     r9d, [rsi]; int
0x1800079c1  mov     r8, [r14]; struct Windows::Foundation::Collections::IPropertySet *
0x1800079c4  mov     rdx, rbp; char *
0x1800079c7  mov     rcx, rax; this
0x1800079ca  call    ?RuntimeClassInitialize@DiagnosticActionResult@Diagnostics@System@Windows@@QEAAJPEADPEAUIPropertySet@Collections@Foundation@4@J@Z; Windows::System::Diagnostics::DiagnosticActionResult::RuntimeClassInitialize(char *,Windows::Foundation::Collections::IPropertySet *,long)
0x1800079cf  mov     esi, eax
0x1800079d1  test    eax, eax
0x1800079d3  jns     short loc_1800079EC
0x1800079d5  test    rdi, rdi
0x1800079d8  jz      short loc_1800079EA
0x1800079da  mov     rax, [rdi]
0x1800079dd  mov     rcx, rdi
0x1800079e0  mov     rax, [rax+10h]
0x1800079e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e9  nop
0x1800079ea  jmp     short loc_180007A16
0x1800079ec  mov     rax, [rdi]
0x1800079ef  mov     r8, rbx
0x1800079f2  lea     rdx, _GUID_c265a296_e73b_4097_b28f_3442f03dd831
0x1800079f9  mov     rcx, rdi
0x1800079fc  mov     rax, [rax]
0x1800079ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a04  mov     esi, eax
0x180007a06  mov     rcx, [rdi]
0x180007a09  mov     rax, [rcx+10h]
0x180007a0d  mov     rcx, rdi
0x180007a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a15  nop
0x180007a16  mov     eax, esi
0x180007a18  add     rsp, 20h
0x180007a1c  pop     r14
0x180007a1e  pop     rdi
0x180007a1f  pop     rsi
0x180007a20  pop     rbp
0x180007a21  pop     rbx
0x180007a22  retn
```
