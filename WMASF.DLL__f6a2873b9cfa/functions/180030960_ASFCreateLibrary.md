# ASFCreateLibrary

- ea: `0x180030960`
- end: `0x1800309ec`
- name: `ASFCreateLibrary`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800318b0`

## callees

- `0x180001174`
- `0x180007734`
- `0x180030960`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall ASFCreateLibrary(_QWORD *a1)
{
  CASFLibrary *v3; // rax
  CASFLibrary *v4; // rdi
  int v5; // esi

  if ( !a1 )
    return 2147942487LL;
  v3 = (CASFLibrary *)operator new(0x220u);
  if ( v3 )
    v4 = CASFLibrary::CASFLibrary(v3);
  else
    v4 = 0;
  v5 = (**(__int64 (__fastcall ***)(CASFLibrary *, GUID *, _QWORD *))v4)(v4, &IID_IASFLibrary, a1);
  (*(void (__fastcall **)(CASFLibrary *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v5 >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 24LL))(*a1);
  else
    return (unsigned int)v5;
}

```

## disassembly

```asm
0x180030960  mov     [rsp+arg_0], rbx
0x180030965  mov     [rsp+arg_8], rsi
0x18003096a  push    rdi
0x18003096b  sub     rsp, 20h
0x18003096f  mov     rbx, rcx
0x180030972  test    rcx, rcx
0x180030975  jnz     short loc_18003097E
0x180030977  mov     eax, 80070057h
0x18003097c  jmp     short loc_1800309DC
0x18003097e  mov     ecx, 220h; Size
0x180030983  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030988  test    rax, rax
0x18003098b  jz      short loc_18003099A
0x18003098d  mov     rcx, rax; this
0x180030990  call    ??0CASFLibrary@@QEAA@XZ; CASFLibrary::CASFLibrary(void)
0x180030995  mov     rdi, rax
0x180030998  jmp     short loc_18003099C
0x18003099a  xor     edi, edi
0x18003099c  mov     rax, [rdi]
0x18003099f  lea     rdx, IID_IASFLibrary
0x1800309a6  mov     r8, rbx
0x1800309a9  mov     rcx, rdi
0x1800309ac  mov     rax, [rax]
0x1800309af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309b4  mov     rcx, [rdi]
0x1800309b7  mov     esi, eax
0x1800309b9  mov     rax, [rcx+10h]
0x1800309bd  mov     rcx, rdi
0x1800309c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309c5  test    esi, esi
0x1800309c7  jns     short loc_1800309CD
0x1800309c9  mov     eax, esi
0x1800309cb  jmp     short loc_1800309DC
0x1800309cd  mov     rcx, [rbx]
0x1800309d0  mov     rax, [rcx]
0x1800309d3  mov     rax, [rax+18h]
0x1800309d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309dc  mov     rbx, [rsp+28h+arg_0]
0x1800309e1  mov     rsi, [rsp+28h+arg_8]
0x1800309e6  add     rsp, 20h
0x1800309ea  pop     rdi
0x1800309eb  retn
```
