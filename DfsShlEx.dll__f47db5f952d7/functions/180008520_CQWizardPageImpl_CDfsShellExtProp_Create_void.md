# CQWizardPageImpl<CDfsShellExtProp>::Create(void)

- ea: `0x180008520`
- end: `0x18000853f`
- name: `?Create@?$CQWizardPageImpl@VCDfsShellExtProp@@@@UEAAPEAU_PSP@@XZ`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009ce0`

## pseudocode

```c
__int64 __fastcall CQWizardPageImpl<CDfsShellExtProp>::Create(__int64 a1)
{
  __int64 result; // rax

  result = IsolationAwareCreatePropertySheetPageW(a1 + 64);
  *(_QWORD *)(a1 + 168) = result;
  return result;
}

```

## disassembly

```asm
0x180008520  push    rbx
0x180008522  sub     rsp, 20h
0x180008526  mov     rbx, rcx
0x180008529  add     rcx, 40h ; '@'
0x18000852d  call    IsolationAwareCreatePropertySheetPageW
0x180008532  mov     [rbx+0A8h], rax
0x180008539  add     rsp, 20h
0x18000853d  pop     rbx
0x18000853e  retn
```
