# XC_WriteHFlex

- ea: `0x1800527b8`
- end: `0x180052892`
- name: `XC_WriteHFlex`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18005017c`

## callees

- `0x18004e048`
- `0x18004f464`
- `0x180050770`
- `0x1800527b8`

## pseudocode

```c
__int64 __fastcall XC_WriteHFlex(__int64 a1, unsigned int a2)
{
  if ( *(_WORD *)(a1 + 22736) != 7 )
    XCF_FatalErrorHandler(a1, 14);
  PSVSubtract(a1, *(_QWORD *)(a1 + 26064), *(_QWORD *)(a1 + 26048), *(_QWORD *)(a1 + 21984));
  return WriteExpandedFlexCurveTo(
           a1,
           *(_QWORD *)(a1 + 21968),
           *(_QWORD *)(a1 + 26048),
           *(_QWORD *)(a1 + 21976),
           *(_QWORD *)(a1 + 21984),
           *(_QWORD *)(a1 + 21992),
           *(_QWORD *)(a1 + 26048),
           *(_QWORD *)(a1 + 22000),
           *(_QWORD *)(a1 + 26048),
           *(_QWORD *)(a1 + 22008),
           *(_QWORD *)(a1 + 26064),
           *(_QWORD *)(a1 + 22016),
           *(_QWORD *)(a1 + 26048),
           *(_QWORD *)(a1 + 26056),
           a2);
}

```

## disassembly

```asm
0x1800527b8  mov     [rsp+arg_0], rbx
0x1800527bd  push    rdi
0x1800527be  sub     rsp, 80h
0x1800527c5  cmp     word ptr [rcx+58D0h], 7
0x1800527cd  mov     edi, edx
0x1800527cf  mov     rbx, rcx
0x1800527d2  jnz     loc_180052887
0x1800527d8  mov     r9, [rcx+55E0h]
0x1800527df  mov     r8, [rcx+65C0h]
0x1800527e6  mov     rdx, [rcx+65D0h]
0x1800527ed  call    PSVSubtract
0x1800527f2  mov     r8, [rbx+65C0h]
0x1800527f9  mov     rcx, rbx
0x1800527fc  mov     rax, [rbx+65C8h]
0x180052803  mov     r9, [rbx+55D8h]
0x18005280a  mov     rdx, [rbx+55D0h]
0x180052811  mov     [rsp+88h+var_18], edi
0x180052815  mov     [rsp+88h+var_20], rax
0x18005281a  mov     rax, [rbx+5600h]
0x180052821  mov     [rsp+88h+var_28], r8
0x180052826  mov     [rsp+88h+var_30], rax
0x18005282b  mov     rax, [rbx+65D0h]
0x180052832  mov     [rsp+88h+var_38], rax
0x180052837  mov     rax, [rbx+55F8h]
0x18005283e  mov     [rsp+88h+var_40], rax
0x180052843  mov     rax, [rbx+55F0h]
0x18005284a  mov     [rsp+88h+var_48], r8
0x18005284f  mov     [rsp+88h+var_50], rax
0x180052854  mov     rax, [rbx+55E8h]
0x18005285b  mov     [rsp+88h+var_58], r8
0x180052860  mov     [rsp+88h+var_60], rax
0x180052865  mov     rax, [rbx+55E0h]
0x18005286c  mov     [rsp+88h+var_68], rax
0x180052871  call    WriteExpandedFlexCurveTo
0x180052876  mov     rbx, [rsp+88h+arg_0]
0x18005287e  add     rsp, 80h
0x180052885  pop     rdi
0x180052886  retn
0x180052887  mov     edx, 0Eh
0x18005288c  call    XCF_FatalErrorHandler
```
