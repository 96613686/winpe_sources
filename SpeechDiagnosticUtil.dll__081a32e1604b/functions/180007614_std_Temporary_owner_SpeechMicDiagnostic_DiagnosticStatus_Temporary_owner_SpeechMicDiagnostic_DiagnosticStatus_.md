# std::_Temporary_owner<SpeechMicDiagnostic::DiagnosticStatus>::~_Temporary_owner<SpeechMicDiagnostic::DiagnosticStatus>(void)

- ea: `0x180007614`
- end: `0x18000764d`
- name: `??1?$_Temporary_owner@VDiagnosticStatus@SpeechMicDiagnostic@@@std@@QEAA@XZ`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800107c2`

## callees

- `0x180002ce0`
- `0x180007614`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000762b`
- `KERNEL32!CloseHandle` at `0x18000762b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Temporary_owner<SpeechMicDiagnostic::DiagnosticStatus>::~_Temporary_owner<SpeechMicDiagnostic::DiagnosticStatus>(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  void *v2; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v2 = (void *)v1[2];
    if ( v2 )
      CloseHandle(v2);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x180007614  push    rbx
0x180007616  sub     rsp, 20h
0x18000761a  mov     rbx, [rcx]
0x18000761d  test    rbx, rbx
0x180007620  jz      short loc_180007646
0x180007622  mov     rcx, [rbx+10h]; hObject
0x180007626  test    rcx, rcx
0x180007629  jz      short loc_180007638
0x18000762b  call    cs:__imp_CloseHandle
0x180007632  nop     dword ptr [rax+rax+00h]
0x180007637  nop
0x180007638  mov     edx, 20h ; ' '; unsigned __int64
0x18000763d  mov     rcx, rbx; void *
0x180007640  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007645  nop
0x180007646  add     rsp, 20h
0x18000764a  pop     rbx
0x18000764b  retn
```
