# CxTemplateVector<CxNameAccessObject *>::RemoveElementAndShiftLeft0(unsigned __int64)

- ea: `0x183095b00`
- end: `0x183095bda`
- name: `?RemoveElementAndShiftLeft0@?$CxTemplateVector@PEAVCxNameAccessObject@@@@QEAAX_K@Z`
- size: `218`
- prototype: `__int64 __fastcall(CxVector *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x183095a30`

## callees

- `0x1815b62b0`
- `0x182d41620`
- `0x182dcc6d0`
- `0x183095b00`
- `0x1830bd2e0`
- `0x1830f54a0`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x183095b28`
- `VCRUNTIME140!memmove` at `0x183095b28`

## string_xrefs

- `0x183095b75`: `Attempting to Resize/Reshape an object that is size locked.`

## pseudocode

```c
void __fastcall CxTemplateVector<CxNameAccessObject *>::RemoveElementAndShiftLeft0(CxVector *this, __int64 a2)
{
  unsigned __int64 v3; // rdi
  unsigned __int64 v4; // rsi
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rbp
  _QWORD v7[5]; // [rsp+20h] [rbp-28h] BYREF

  memmove(
    (void *)(*((_QWORD *)this + 7) + 8 * a2),
    (const void *)(*((_QWORD *)this + 7) + 8 * a2 + 8),
    *((_QWORD *)this + 8) - (*((_QWORD *)this + 7) + 8 * a2 + 8));
  v3 = 1;
  v4 = ((__int64)(*((_QWORD *)this + 8) - *((_QWORD *)this + 7)) >> 3) - 1;
  v7[0] = 0;
  v5 = Mul_CheckDimSize(v4, 1u);
  v6 = v5;
  if ( v5 != (__int64)(*((_QWORD *)this + 8) - *((_QWORD *)this + 7)) >> 3 )
  {
    if ( (*((_DWORD *)this + 12) & 0x200000LL) != 0 )
    {
      CxReportError("Attempting to Resize/Reshape an object that is size locked.");
      return;
    }
    std::vector<CxNameAccessObject *>::resize((char *)this + 56, v5, v7);
    *((_QWORD *)this + 10) = *((_QWORD *)this + 7);
    *((_QWORD *)this + 11) = *((_QWORD *)this + 7);
  }
  if ( !v6 )
  {
    v4 = 0;
    if ( (unsigned __int8)IsKindOfDataSet(*((unsigned int *)this + 8)) )
      v3 = 0;
  }
  CxVector::SetRowCol(this, v4, v3);
}

```

## disassembly

```asm
0x183095b00  mov     [rsp+arg_8], rbx
0x183095b05  mov     [rsp+arg_10], rbp
0x183095b0a  push    rsi
0x183095b0b  push    rdi
0x183095b0c  push    r14
0x183095b0e  sub     rsp, 30h
0x183095b12  mov     rax, [rcx+38h]
0x183095b16  mov     rbx, rcx
0x183095b19  mov     r8, [rbx+40h]
0x183095b1d  lea     rcx, [rax+rdx*8]; void *
0x183095b21  lea     rdx, [rcx+8]; Src
0x183095b25  sub     r8, rdx; Size
0x183095b28  call    cs:__imp_memmove
0x183095b2e  mov     rsi, [rbx+40h]
0x183095b32  mov     edi, 1
0x183095b37  sub     rsi, [rbx+38h]
0x183095b3b  mov     edx, edi; unsigned __int64
0x183095b3d  sar     rsi, 3
0x183095b41  dec     rsi
0x183095b44  mov     [rsp+48h+var_28], 0
0x183095b4d  mov     rcx, rsi; unsigned __int64
0x183095b50  call    ?Mul_CheckDimSize@@YA_K_K0@Z; Mul_CheckDimSize(unsigned __int64,unsigned __int64)
0x183095b55  mov     rcx, [rbx+40h]
0x183095b59  mov     rbp, rax
0x183095b5c  sub     rcx, [rbx+38h]
0x183095b60  sar     rcx, 3
0x183095b64  cmp     rax, rcx
0x183095b67  jz      short loc_183095BA4
0x183095b69  mov     ecx, [rbx+30h]
0x183095b6c  shr     rcx, 15h
0x183095b70  test    dil, cl
0x183095b73  jz      short loc_183095B83
0x183095b75  lea     rcx, aAttemptingToRe; "Attempting to Resize/Reshape an object "...
0x183095b7c  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x183095b81  jmp     short loc_183095BC7
0x183095b83  lea     r8, [rsp+48h+var_28]
0x183095b88  mov     rdx, rbp
0x183095b8b  lea     rcx, [rbx+38h]
0x183095b8f  call    ?resize@?$vector@PEAVCxNameAccessObject@@V?$allocator@PEAVCxNameAccessObject@@@std@@@std@@QEAAX_KAEBQEAVCxNameAccessObject@@@Z; std::vector<CxNameAccessObject *>::resize(unsigned __int64,CxNameAccessObject * const &)
0x183095b94  mov     rax, [rbx+38h]
0x183095b98  mov     [rbx+50h], rax
0x183095b9c  mov     rax, [rbx+38h]
0x183095ba0  mov     [rbx+58h], rax
0x183095ba4  test    rbp, rbp
0x183095ba7  jnz     short loc_183095BB9
0x183095ba9  mov     ecx, [rbx+20h]
0x183095bac  call    ?IsKindOfDataSet@@YA_NW4CxVarType@@@Z; IsKindOfDataSet(CxVarType)
0x183095bb1  xor     esi, esi
0x183095bb3  test    al, al
0x183095bb5  jz      short loc_183095BB9
0x183095bb7  xor     edi, edi
0x183095bb9  mov     r8, rdi; unsigned __int64
0x183095bbc  mov     rdx, rsi; unsigned __int64
0x183095bbf  mov     rcx, rbx; this
0x183095bc2  call    ?SetRowCol@CxVector@@QEAAX_K0@Z; CxVector::SetRowCol(unsigned __int64,unsigned __int64)
0x183095bc7  mov     rbx, [rsp+48h+arg_8]
0x183095bcc  mov     rbp, [rsp+48h+arg_10]
0x183095bd1  add     rsp, 30h
0x183095bd5  pop     r14
0x183095bd7  pop     rdi
0x183095bd8  pop     rsi
0x183095bd9  retn
```
