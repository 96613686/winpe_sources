# CreateHandle

- ea: `0x180010208`
- end: `0x1800102b9`
- name: `CreateHandle`
- size: `177`
- prototype: `_QWORD *__fastcall(int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000a1d0`

## callees

- `0x18000e2bc`
- `0x18000e308`
- `0x180010208`
- `0x1800102e8`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall CreateHandle(int a1, int a2, int a3)
{
  bool v4; // di
  _DWORD *v7; // rax
  _QWORD *v8; // rbx
  CMpgaDecoder *v9; // rax
  CMpgaDecoder *v10; // rax
  CMpgaDecoder *v11; // rcx
  bool v13; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
  v13 = 0;
  v7 = operator new(0x10u);
  v8 = v7;
  if ( v7 )
  {
    *v7 = 7498099;
    v9 = (CMpgaDecoder *)operator new(0x3F00u);
    if ( v9 )
    {
      v10 = CMpgaDecoder::CMpgaDecoder(v9, &v13, a1, a2, a3);
      v4 = v13;
      v11 = v10;
    }
    else
    {
      v11 = 0;
    }
    v8[1] = v11;
    if ( v11 )
    {
      if ( !v4 )
        return v8;
      (*(void (__fastcall **)(CMpgaDecoder *, __int64))(*(_QWORD *)v11 + 80LL))(v11, 1);
    }
    operator delete(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180010208  mov     [rsp+arg_0], rbx
0x18001020d  mov     [rsp+arg_8], rbp
0x180010212  push    rsi
0x180010213  push    rdi
0x180010214  push    r14
0x180010216  sub     rsp, 30h
0x18001021a  mov     r14d, ecx
0x18001021d  xor     dil, dil
0x180010220  mov     ecx, 10h; Size
0x180010225  mov     [rsp+48h+arg_18], dil
0x18001022a  mov     esi, r8d
0x18001022d  mov     ebp, edx
0x18001022f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010234  mov     rbx, rax
0x180010237  test    rax, rax
0x18001023a  jz      short loc_1800102A4
0x18001023c  mov     r9d, cs:dword_18001575C
0x180010243  mov     ecx, 3F00h; Size
0x180010248  mov     [rax], r9d
0x18001024b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010250  test    rax, rax
0x180010253  jz      short loc_180010276
0x180010255  mov     r9d, ebp; int
0x180010258  mov     [rsp+48h+var_28], esi; int
0x18001025c  mov     r8d, r14d; int
0x18001025f  lea     rdx, [rsp+48h+arg_18]; bool *
0x180010264  mov     rcx, rax; this
0x180010267  call    ??0CMpgaDecoder@@QEAA@PEA_NHHH@Z; CMpgaDecoder::CMpgaDecoder(bool *,int,int,int)
0x18001026c  mov     dil, [rsp+48h+arg_18]
0x180010271  mov     rcx, rax
0x180010274  jmp     short loc_180010278
0x180010276  xor     ecx, ecx
0x180010278  mov     [rbx+8], rcx
0x18001027c  test    rcx, rcx
0x18001027f  jz      short loc_18001029C
0x180010281  test    dil, dil
0x180010284  jnz     short loc_18001028B
0x180010286  mov     rax, rbx
0x180010289  jmp     short loc_1800102A6
0x18001028b  mov     rax, [rcx]
0x18001028e  mov     edx, 1
0x180010293  mov     rax, [rax+50h]
0x180010297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001029c  mov     rcx, rbx; Block
0x18001029f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800102a4  xor     eax, eax
0x1800102a6  mov     rbx, [rsp+48h+arg_0]
0x1800102ab  mov     rbp, [rsp+48h+arg_8]
0x1800102b0  add     rsp, 30h
0x1800102b4  pop     r14
0x1800102b6  pop     rdi
0x1800102b7  pop     rsi
0x1800102b8  retn
```
