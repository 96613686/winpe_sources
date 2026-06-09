# CxTemplateVector<CxNameAccessObject *>::RemoveTopNElementsAndShiftLeft0(unsigned __int64)

- ea: `0x183095be0`
- end: `0x183095cf0`
- name: `?RemoveTopNElementsAndShiftLeft0@?$CxTemplateVector@PEAVCxNameAccessObject@@@@UEAAX_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(CxVector *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1815b62b0`
- `0x182d41620`
- `0x182dc4440`
- `0x182dcc6d0`
- `0x183095be0`
- `0x1830bd2e0`
- `0x1830f54a0`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x183095c3f`
- `VCRUNTIME140!memmove` at `0x183095c3f`

## string_xrefs

- `0x183095c8b`: `Attempting to Resize/Reshape an object that is size locked.`

## pseudocode

```c
void __fastcall CxTemplateVector<CxNameAccessObject *>::RemoveTopNElementsAndShiftLeft0(
        void **this,
        unsigned __int64 a2)
{
  __int64 v3; // rbp
  unsigned __int64 v4; // rbx
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rbp
  _QWORD v8[5]; // [rsp+20h] [rbp-28h] BYREF

  v3 = a2;
  if ( a2 > (*((__int64 (__fastcall **)(void **))*this + 68))(this) )
    v3 = (*((__int64 (__fastcall **)(void **))*this + 68))(this);
  memmove(this[7], (char *)this[7] + 8 * v3, (_BYTE *)this[8] - ((_BYTE *)this[7] + 8 * v3));
  v4 = 1;
  v5 = (((_BYTE *)this[8] - (_BYTE *)this[7]) >> 3) - v3;
  v8[0] = 0;
  v6 = Mul_CheckDimSize(v5, 1u);
  v7 = v6;
  if ( v6 != ((_BYTE *)this[8] - (_BYTE *)this[7]) >> 3 )
  {
    if ( ((_DWORD)this[6] & 0x200000LL) != 0 )
    {
      CxReportError("Attempting to Resize/Reshape an object that is size locked.");
      return;
    }
    std::vector<CxNameAccessObject *>::resize(this + 7, v6, v8);
    this[10] = this[7];
    this[11] = this[7];
  }
  if ( !v7 )
  {
    v5 = 0;
    if ( (unsigned __int8)IsKindOfDataSet(*((unsigned int *)this + 8)) )
      v4 = 0;
  }
  CxVector::SetRowCol((CxVector *)this, v5, v4);
}

```

## disassembly

```asm
0x183095be0  mov     [rsp+arg_10], rbx
0x183095be5  mov     [rsp+arg_18], rbp
0x183095bea  push    rsi
0x183095beb  push    rdi
0x183095bec  push    r14
0x183095bee  sub     rsp, 30h
0x183095bf2  mov     rax, [rcx]
0x183095bf5  mov     rdi, rcx
0x183095bf8  mov     rbp, rdx
0x183095bfb  mov     rbx, [rax+220h]
0x183095c02  mov     rcx, rbx; this
0x183095c05  call    cs:__guard_check_icall_fptr; CxVector::SetPadForMissings(uint) ...
0x183095c0b  mov     rcx, rdi
0x183095c0e  call    rbx
0x183095c10  cmp     rbp, rax
0x183095c13  jbe     short loc_183095C30
0x183095c15  mov     rax, [rdi]
0x183095c18  mov     rbx, [rax+220h]
0x183095c1f  mov     rcx, rbx; this
0x183095c22  call    cs:__guard_check_icall_fptr; CxVector::SetPadForMissings(uint) ...
0x183095c28  mov     rcx, rdi
0x183095c2b  call    rbx
0x183095c2d  mov     rbp, rax
0x183095c30  mov     rcx, [rdi+38h]; void *
0x183095c34  mov     r8, [rdi+40h]
0x183095c38  lea     rdx, [rcx+rbp*8]; Src
0x183095c3c  sub     r8, rdx; Size
0x183095c3f  call    cs:__imp_memmove
0x183095c45  mov     rsi, [rdi+40h]
0x183095c49  mov     ebx, 1
0x183095c4e  sub     rsi, [rdi+38h]
0x183095c52  mov     edx, ebx; unsigned __int64
0x183095c54  sar     rsi, 3
0x183095c58  sub     rsi, rbp
0x183095c5b  mov     [rsp+48h+var_28], 0
0x183095c64  mov     rcx, rsi; unsigned __int64
0x183095c67  call    ?Mul_CheckDimSize@@YA_K_K0@Z; Mul_CheckDimSize(unsigned __int64,unsigned __int64)
0x183095c6c  mov     rcx, [rdi+40h]
0x183095c70  mov     rbp, rax
0x183095c73  sub     rcx, [rdi+38h]
0x183095c77  sar     rcx, 3
0x183095c7b  cmp     rax, rcx
0x183095c7e  jz      short loc_183095CBA
0x183095c80  mov     ecx, [rdi+30h]
0x183095c83  shr     rcx, 15h
0x183095c87  test    bl, cl
0x183095c89  jz      short loc_183095C99
0x183095c8b  lea     rcx, aAttemptingToRe; "Attempting to Resize/Reshape an object "...
0x183095c92  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x183095c97  jmp     short loc_183095CDD
0x183095c99  lea     r8, [rsp+48h+var_28]
0x183095c9e  mov     rdx, rbp
0x183095ca1  lea     rcx, [rdi+38h]
0x183095ca5  call    ?resize@?$vector@PEAVCxNameAccessObject@@V?$allocator@PEAVCxNameAccessObject@@@std@@@std@@QEAAX_KAEBQEAVCxNameAccessObject@@@Z; std::vector<CxNameAccessObject *>::resize(unsigned __int64,CxNameAccessObject * const &)
0x183095caa  mov     rax, [rdi+38h]
0x183095cae  mov     [rdi+50h], rax
0x183095cb2  mov     rax, [rdi+38h]
0x183095cb6  mov     [rdi+58h], rax
0x183095cba  test    rbp, rbp
0x183095cbd  jnz     short loc_183095CCF
0x183095cbf  mov     ecx, [rdi+20h]
0x183095cc2  call    ?IsKindOfDataSet@@YA_NW4CxVarType@@@Z; IsKindOfDataSet(CxVarType)
0x183095cc7  xor     esi, esi
0x183095cc9  test    al, al
0x183095ccb  jz      short loc_183095CCF
0x183095ccd  xor     ebx, ebx
0x183095ccf  mov     r8, rbx; unsigned __int64
0x183095cd2  mov     rdx, rsi; unsigned __int64
0x183095cd5  mov     rcx, rdi; this
0x183095cd8  call    ?SetRowCol@CxVector@@QEAAX_K0@Z; CxVector::SetRowCol(unsigned __int64,unsigned __int64)
0x183095cdd  mov     rbx, [rsp+48h+arg_10]
0x183095ce2  mov     rbp, [rsp+48h+arg_18]
0x183095ce7  add     rsp, 30h
0x183095ceb  pop     r14
0x183095ced  pop     rdi
0x183095cee  pop     rsi
0x183095cef  retn
```
