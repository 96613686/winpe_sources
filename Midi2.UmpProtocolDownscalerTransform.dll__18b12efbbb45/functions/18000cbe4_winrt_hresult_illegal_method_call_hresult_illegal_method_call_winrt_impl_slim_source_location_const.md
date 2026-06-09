# winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::impl::slim_source_location const &)

- ea: `0x18000cbe4`
- end: `0x18000cc1f`
- name: `??0hresult_illegal_method_call@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z`
- size: `59`
- prototype: `__int64 __fastcall(winrt::hresult_illegal_method_call *__hidden this, const struct winrt::impl::slim_source_location *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000df90`
- `0x18000e350`
- `0x18000f930`
- `0x180011290`
- `0x180011400`

## callees

- `0x1800115e4`

## pseudocode

```c
winrt::hresult_illegal_method_call *__fastcall winrt::hresult_illegal_method_call::hresult_illegal_method_call(
        winrt::hresult_illegal_method_call *this,
        const struct winrt::impl::slim_source_location *a2)
{
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = -1430532899;
  *((_DWORD *)this + 3) = -2147483634;
  *((_QWORD *)this + 2) = 0;
  winrt::hresult_error::originate((__int64)this, 0x8000000E, 0, (unsigned int *)a2);
  return this;
}

```

## disassembly

```asm
0x18000cbe4  push    rbx
0x18000cbe6  sub     rsp, 20h
0x18000cbea  mov     qword ptr [rcx], 0
0x18000cbf1  mov     r9, rdx
0x18000cbf4  mov     dword ptr [rcx+8], 0AABBCCDDh
0x18000cbfb  mov     edx, 8000000Eh
0x18000cc00  mov     [rcx+0Ch], edx
0x18000cc03  xor     r8d, r8d
0x18000cc06  mov     qword ptr [rcx+10h], 0
0x18000cc0e  mov     rbx, rcx
0x18000cc11  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x18000cc16  mov     rax, rbx
0x18000cc19  add     rsp, 20h
0x18000cc1d  pop     rbx
0x18000cc1e  retn
```
