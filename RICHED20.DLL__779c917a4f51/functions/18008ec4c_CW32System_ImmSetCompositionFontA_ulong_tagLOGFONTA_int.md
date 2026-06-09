# CW32System::ImmSetCompositionFontA(ulong,tagLOGFONTA *,int)

- ea: `0x18008ec4c`
- end: `0x18008ecbf`
- name: `?ImmSetCompositionFontA@CW32System@@SAHKPEAUtagLOGFONTA@@H@Z`
- size: `115`
- prototype: `__int64 __fastcall(unsigned int, struct tagLOGFONTA *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180065b6c`

## callees

- `0x18008ec4c`
- `0x1800905e8`
- `0x180092010`

## string_xrefs

- `0x18008ec8e`: `ImmSetCompositionFontA`

## pseudocode

```c
__int64 __fastcall CW32System::ImmSetCompositionFontA(unsigned int a1, struct tagLOGFONTA *a2, int a3)
{
  __int64 (__fastcall *v6)(_QWORD, struct tagLOGFONTA *); // rax

  if ( a3 )
    return (*(int (__fastcall **)(__int64, _QWORD, struct tagLOGFONTA *))(*(_QWORD *)qword_1800A44B8 + 392LL))(
             qword_1800A44B8,
             a1,
             a2) >= 0;
  v6 = (__int64 (__fastcall *)(_QWORD, struct tagLOGFONTA *))qword_1800A4108;
  if ( !qword_1800A4108 )
  {
    SetIMEProcAddr(&qword_1800A4108, 0, "ImmSetCompositionFontA");
    v6 = (__int64 (__fastcall *)(_QWORD, struct tagLOGFONTA *))qword_1800A4108;
  }
  return v6(a1, a2);
}

```

## disassembly

```asm
0x18008ec4c  mov     [rsp+arg_0], rbx
0x18008ec51  push    rdi
0x18008ec52  sub     rsp, 20h
0x18008ec56  mov     rbx, rdx
0x18008ec59  mov     edi, ecx
0x18008ec5b  test    r8d, r8d
0x18008ec5e  jz      short loc_18008EC82
0x18008ec60  mov     rcx, cs:qword_1800A44B8
0x18008ec67  mov     r8, rdx
0x18008ec6a  mov     edx, edi
0x18008ec6c  mov     rax, [rcx]
0x18008ec6f  mov     rax, [rax+188h]
0x18008ec76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ec7b  not     eax
0x18008ec7d  shr     eax, 1Fh
0x18008ec80  jmp     short loc_18008ECB4
0x18008ec82  mov     rax, cs:qword_1800A4108
0x18008ec89  test    rax, rax
0x18008ec8c  jnz     short loc_18008ECAA
0x18008ec8e  lea     r8, aImmsetcomposit_0; "ImmSetCompositionFontA"
0x18008ec95  xor     edx, edx
0x18008ec97  lea     rcx, qword_1800A4108
0x18008ec9e  call    SetIMEProcAddr
0x18008eca3  mov     rax, cs:qword_1800A4108
0x18008ecaa  mov     rdx, rbx
0x18008ecad  mov     ecx, edi
0x18008ecaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ecb4  mov     rbx, [rsp+28h+arg_0]
0x18008ecb9  add     rsp, 20h
0x18008ecbd  pop     rdi
0x18008ecbe  retn
```
