# COleSafeArray::COleSafeArray(tagSAFEARRAY const *,ushort)

- ea: `0x18008ba40`
- end: `0x18008baa8`
- name: `??0COleSafeArray@@QEAA@PEBUtagSAFEARRAY@@G@Z`
- size: `104`
- prototype: `COleSafeArray *(COleSafeArray *__hidden this, const struct tagSAFEARRAY *, unsigned __int16)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180024fc0`
- `0x18008d4a0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008ba80`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008ba80`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18008ba8c`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18008ba8c`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008ba70`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18008ba70`

## pseudocode

```c
COleSafeArray *__fastcall COleSafeArray::COleSafeArray(COleSafeArray *this, struct tagSAFEARRAY *a2, __int16 a3)
{
  HRESULT v6; // eax
  UINT Dim; // eax
  SAFEARRAY *v8; // rcx

  AfxSafeArrayInit(this);
  *(_WORD *)this = a3 | 0x2000;
  v6 = SafeArrayCopy(a2, (SAFEARRAY **)this + 1);
  AfxCheckError(v6);
  Dim = SafeArrayGetDim(*((SAFEARRAY **)this + 1));
  v8 = (SAFEARRAY *)*((_QWORD *)this + 1);
  *((_DWORD *)this + 7) = Dim;
  *((_DWORD *)this + 6) = SafeArrayGetElemsize(v8);
  return this;
}

```

## disassembly

```asm
0x18008ba40  mov     [rsp+arg_0], rbx
0x18008ba45  mov     [rsp+arg_8], rsi
0x18008ba4a  push    rdi
0x18008ba4b  sub     rsp, 20h
0x18008ba4f  movzx   ebx, r8w
0x18008ba53  mov     rdi, rdx
0x18008ba56  mov     rsi, rcx
0x18008ba59  call    ?AfxSafeArrayInit@@YAXPEAVCOleSafeArray@@@Z; AfxSafeArrayInit(COleSafeArray *)
0x18008ba5e  or      bx, 2000h
0x18008ba63  mov     rcx, rdi; psa
0x18008ba66  mov     [rsi], bx
0x18008ba69  lea     rbx, [rsi+8]
0x18008ba6d  mov     rdx, rbx; ppsaOut
0x18008ba70  call    cs:__imp_SafeArrayCopy
0x18008ba76  mov     ecx, eax; int
0x18008ba78  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008ba7d  mov     rcx, [rbx]; psa
0x18008ba80  call    cs:__imp_SafeArrayGetDim
0x18008ba86  mov     rcx, [rbx]; psa
0x18008ba89  mov     [rsi+1Ch], eax
0x18008ba8c  call    cs:__imp_SafeArrayGetElemsize
0x18008ba92  mov     rbx, [rsp+28h+arg_0]
0x18008ba97  mov     [rsi+18h], eax
0x18008ba9a  mov     rax, rsi
0x18008ba9d  mov     rsi, [rsp+28h+arg_8]
0x18008baa2  add     rsp, 20h
0x18008baa6  pop     rdi
0x18008baa7  retn
```
