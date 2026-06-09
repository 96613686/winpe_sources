# _Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_dynamic_atexit_destructor_for__g_SystemSid__

- ea: `0x140029f90`
- end: `0x140029fca`
- name: `_Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_dynamic_atexit_destructor_for__g_SystemSid__`
- size: `58`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140029f90`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140029fb4`
- `ntdll!RtlFreeHeap` at `0x140029fb4`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_dynamic_atexit_destructor_for__g_SystemSid__()
{
  if ( qword_140050780 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, qword_140050780);
    qword_140050780 = 0;
  }
}

```

## disassembly

```asm
0x140029f90  sub     rsp, 28h
0x140029f94  cmp     cs:qword_140050780, 0
0x140029f9c  jz      short loc_140029FC5
0x140029f9e  mov     rcx, gs:60h
0x140029fa7  xor     edx, edx; Flags
0x140029fa9  mov     r8, cs:qword_140050780; P
0x140029fb0  mov     rcx, [rcx+30h]; HeapHandle
0x140029fb4  call    cs:__imp_RtlFreeHeap
0x140029fba  mov     cs:qword_140050780, 0
0x140029fc5  add     rsp, 28h
0x140029fc9  retn
```
