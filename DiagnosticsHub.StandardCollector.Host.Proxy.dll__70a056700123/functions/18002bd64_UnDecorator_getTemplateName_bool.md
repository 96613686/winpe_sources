# UnDecorator::getTemplateName(bool)

- ea: `0x18002bd64`
- end: `0x18002c07c`
- name: `?getTemplateName@UnDecorator@@AEAA?AVDName@@_N@Z`
- size: `792`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: ``

## callers

- `0x180028264`
- `0x18002baac`
- `0x18002d254`
- `0x18002d748`

## callees

- `0x180023ed8`
- `0x180024564`
- `0x180024c70`
- `0x1800262ac`
- `0x1800297b0`
- `0x180029938`
- `0x18002bafc`
- `0x18002bd64`
- `0x18002d254`
- `0x180060110`
- `0x180060270`

## pseudocode

```c
__int64 __fastcall UnDecorator::getTemplateName(__int64 a1, __int64 a2, char a3)
{
  _BYTE *v3; // rax
  _BYTE *v7; // rdi
  __int64 v8; // r12
  __int64 v9; // r13
  char v10; // r14
  __int64 v11; // r8
  bool v12; // zf
  __int64 OperatorName; // rax
  __int64 v14; // rdi
  int v15; // ecx
  _BYTE *MemoryWithBuffer; // rax
  __int64 TemplateArgumentList; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  BOOL v20; // r14d
  _BYTE *v21; // rax
  _BYTE *v22; // rax
  _BYTE *v23; // rax
  __int64 v24; // rax
  __int64 v26; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v27; // [rsp+28h] [rbp-D8h]
  int v28; // [rsp+30h] [rbp-D0h]
  _BYTE v29[24]; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v30[22]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+A8h] [rbp-58h]
  _DWORD v32[22]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v33; // [rsp+108h] [rbp+8h]
  _DWORD v34[22]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v35; // [rsp+168h] [rbp+68h]
  char v36; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v37; // [rsp+1C8h] [rbp+C8h]

  v3 = *(_BYTE **)(a1 + 256);
  if ( *v3 != 63 || v3[1] != 36 )
  {
    DName::DName(a2, a1, 2);
    return a2;
  }
  v7 = v3 + 2;
  *(_QWORD *)(a1 + 256) = v3 + 2;
  v8 = *(_QWORD *)(a1 + 96);
  v9 = *(_QWORD *)(a1 + 200);
  v37 = *(_QWORD *)(a1 + 208);
  memset(&v30[2], 0, 0x50u);
  v10 = 0;
  v31 = a1;
  v30[0] = -1;
  memset(&v32[2], 0, 0x50u);
  v33 = a1;
  v32[0] = -1;
  memset(&v34[2], 0, 0x50u);
  v34[0] = -1;
  *(_QWORD *)(a1 + 96) = v30;
  v35 = a1;
  *(_QWORD *)(a1 + 200) = v32;
  v27 = a1;
  *(_QWORD *)(a1 + 208) = v34;
  v12 = *v7 == 63;
  v36 = 0;
  if ( v12 )
  {
    LOBYTE(v11) = 1;
    *(_QWORD *)(a1 + 256) = v7 + 1;
    OperatorName = UnDecorator::getOperatorName(a1, v29, v11, &v36);
    v10 = v36;
  }
  else
  {
    OperatorName = UnDecorator::getZName(a1, (__int64)v29, 1, 1);
  }
  v14 = *(_QWORD *)OperatorName;
  v15 = *(_DWORD *)(OperatorName + 16);
  v28 = v15;
  v26 = v14;
  if ( !v14 )
    *(_BYTE *)(a1 + 276) = 1;
  if ( !v10 )
  {
    if ( (char)v15 <= 1 )
    {
      if ( v14 )
      {
        MemoryWithBuffer = _HeapManager::getMemoryWithBuffer((_HeapManager *)(a1 + 216), 0x10u);
        if ( MemoryWithBuffer )
        {
          *(_QWORD *)MemoryWithBuffer = &charNode::`vftable';
          MemoryWithBuffer[8] = 60;
        }
        DName::append<charNode>(&v26, MemoryWithBuffer);
      }
      else
      {
        v26 = 0;
        v28 = 0;
        DName::doPchar((DName *)&v26, 60);
      }
    }
    TemplateArgumentList = UnDecorator::getTemplateArgumentList(a1, v29);
    DName::operator+=(&v26, TemplateArgumentList, v18, v19);
    v14 = v26;
    v20 = v26 == 0;
    if ( v26 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26) == 62 )
    {
      if ( (char)v28 > 1 )
      {
LABEL_30:
        if ( a3 )
        {
          v23 = *(_BYTE **)(a1 + 256);
          if ( *v23 )
            *(_QWORD *)(a1 + 256) = v23 + 1;
        }
        v15 = v28;
        goto LABEL_34;
      }
      if ( v20 )
      {
        v26 = 0;
        v28 = 0;
        DName::doPchar((DName *)&v26, 32);
        v14 = v26;
      }
      else
      {
        v21 = _HeapManager::getMemoryWithBuffer((_HeapManager *)(v27 + 216), 0x10u);
        if ( v21 )
        {
          *(_QWORD *)v21 = &charNode::`vftable';
          v21[8] = 32;
        }
        DName::append<charNode>(&v26, v21);
        v14 = v26;
      }
    }
    if ( (char)v28 <= 1 )
    {
      if ( v14 )
      {
        v22 = _HeapManager::getMemoryWithBuffer((_HeapManager *)(v27 + 216), 0x10u);
        if ( v22 )
        {
          *(_QWORD *)v22 = &charNode::`vftable';
          v22[8] = 62;
        }
        DName::append<charNode>(&v26, v22);
      }
      else
      {
        v26 = 0;
        v28 = 0;
        DName::doPchar((DName *)&v26, 62);
      }
      v14 = v26;
    }
    goto LABEL_30;
  }
LABEL_34:
  *(_QWORD *)(a1 + 208) = v37;
  v24 = v27;
  *(_QWORD *)(a1 + 96) = v8;
  *(_QWORD *)(a1 + 200) = v9;
  *(_QWORD *)(a2 + 8) = v24;
  *(_QWORD *)a2 = v14;
  *(_DWORD *)(a2 + 16) = v15;
  return a2;
}

```

## disassembly

```asm
0x18002bd64  mov     [rsp-8+arg_8], rbx
0x18002bd69  push    rbp
0x18002bd6a  push    rsi
0x18002bd6b  push    rdi
0x18002bd6c  push    r12
0x18002bd6e  push    r13
0x18002bd70  push    r14
0x18002bd72  push    r15
0x18002bd74  lea     rbp, [rsp-70h]
0x18002bd79  sub     rsp, 170h
0x18002bd80  mov     rax, [rcx+100h]
0x18002bd87  mov     r15b, r8b
0x18002bd8a  mov     rsi, rdx
0x18002bd8d  mov     rbx, rcx
0x18002bd90  cmp     byte ptr [rax], 3Fh ; '?'
0x18002bd93  jnz     loc_18002C04D
0x18002bd99  cmp     byte ptr [rax+1], 24h ; '$'
0x18002bd9d  jnz     loc_18002C04D
0x18002bda3  lea     rdi, [rax+2]
0x18002bda7  xor     edx, edx; Val
0x18002bda9  mov     [rcx+100h], rdi
0x18002bdb0  mov     rax, [rcx+0D0h]
0x18002bdb7  mov     r12, [rcx+60h]
0x18002bdbb  mov     r13, [rcx+0C8h]
0x18002bdc2  lea     r8d, [rdx+50h]; Size
0x18002bdc6  lea     rcx, [rsp+1A0h+var_148]; void *
0x18002bdcb  mov     [rbp+0A0h+arg_18], rax
0x18002bdd2  call    memset
0x18002bdd7  or      r14d, 0FFFFFFFFh
0x18002bddb  mov     [rbp+0A0h+var_F8], rbx
0x18002bddf  xor     edx, edx; Val
0x18002bde1  mov     [rsp+1A0h+var_150], r14d
0x18002bde6  lea     rcx, [rbp+0A0h+var_E8]; void *
0x18002bdea  lea     r8d, [r14+51h]; Size
0x18002bdee  call    memset
0x18002bdf3  xor     edx, edx; Val
0x18002bdf5  mov     [rbp+0A0h+var_98], rbx
0x18002bdf9  lea     r8d, [r14+51h]; Size
0x18002bdfd  mov     [rbp+0A0h+var_F0], r14d
0x18002be01  lea     rcx, [rbp+0A0h+var_88]; void *
0x18002be05  call    memset
0x18002be0a  lea     rax, [rsp+1A0h+var_150]
0x18002be0f  mov     [rbp+0A0h+var_90], r14d
0x18002be13  mov     [rbx+60h], rax
0x18002be17  lea     rdx, [rsp+1A0h+var_168]
0x18002be1c  lea     rax, [rbp+0A0h+var_F0]
0x18002be20  mov     [rbp+0A0h+var_38], rbx
0x18002be24  mov     [rbx+0C8h], rax
0x18002be2b  xor     r14b, r14b
0x18002be2e  lea     rax, [rbp+0A0h+var_90]
0x18002be32  mov     [rsp+1A0h+var_178], rbx
0x18002be37  mov     [rbx+0D0h], rax
0x18002be3e  mov     rcx, rbx
0x18002be41  cmp     byte ptr [rdi], 3Fh ; '?'
0x18002be44  mov     [rbp+0A0h+arg_0], r14b
0x18002be4b  jnz     short loc_18002BE70
0x18002be4d  lea     rax, [rdi+1]
0x18002be51  mov     r8b, 1
0x18002be54  lea     r9, [rbp+0A0h+arg_0]
0x18002be5b  mov     [rbx+100h], rax
0x18002be62  call    ?getOperatorName@UnDecorator@@AEAA?AVDName@@_NPEA_N@Z; UnDecorator::getOperatorName(bool,bool *)
0x18002be67  mov     r14b, [rbp+0A0h+arg_0]
0x18002be6e  jmp     short loc_18002BE7B
0x18002be70  mov     r9b, 1
0x18002be73  mov     r8b, r9b
0x18002be76  call    ?getZName@UnDecorator@@AEAA?AVDName@@_N0@Z; UnDecorator::getZName(bool,bool)
0x18002be7b  mov     rdi, [rax]
0x18002be7e  mov     ecx, [rax+10h]
0x18002be81  mov     [rsp+1A0h+var_170], ecx
0x18002be85  mov     [rsp+1A0h+var_180], rdi
0x18002be8a  test    rdi, rdi
0x18002be8d  jnz     short loc_18002BE96
0x18002be8f  mov     byte ptr [rbx+114h], 1
0x18002be96  test    r14b, r14b
0x18002be99  jnz     loc_18002C023
0x18002be9f  lea     r14, ??_7charNode@@6B@; const charNode::`vftable'
0x18002bea6  cmp     cl, 1
0x18002bea9  jg      short loc_18002BEF1
0x18002beab  test    rdi, rdi
0x18002beae  jnz     short loc_18002BEC7
0x18002beb0  mov     dl, 3Ch ; '<'; char
0x18002beb2  mov     [rsp+1A0h+var_180], rdi
0x18002beb7  lea     rcx, [rsp+1A0h+var_180]; this
0x18002bebc  mov     [rsp+1A0h+var_170], edi
0x18002bec0  call    ?doPchar@DName@@AEAAXD@Z; DName::doPchar(char)
0x18002bec5  jmp     short loc_18002BEF1
0x18002bec7  lea     rcx, [rbx+0D8h]; this
0x18002bece  mov     edx, 10h; unsigned __int64
0x18002bed3  call    ?getMemoryWithBuffer@_HeapManager@@QEAAPEAX_K@Z; _HeapManager::getMemoryWithBuffer(unsigned __int64)
0x18002bed8  test    rax, rax
0x18002bedb  jz      short loc_18002BEE4
0x18002bedd  mov     [rax], r14
0x18002bee0  mov     byte ptr [rax+8], 3Ch ; '<'
0x18002bee4  mov     rdx, rax
0x18002bee7  lea     rcx, [rsp+1A0h+var_180]
0x18002beec  call    ??$append@VcharNode@@@DName@@AEAAXPEBVcharNode@@@Z; DName::append<charNode>(charNode const *)
0x18002bef1  lea     rdx, [rsp+1A0h+var_168]
0x18002bef6  mov     rcx, rbx
0x18002bef9  call    ?getTemplateArgumentList@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getTemplateArgumentList(void)
0x18002befe  mov     rdx, rax
0x18002bf01  lea     rcx, [rsp+1A0h+var_180]
0x18002bf06  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18002bf0b  mov     rdi, [rsp+1A0h+var_180]
0x18002bf10  xor     r14d, r14d
0x18002bf13  test    rdi, rdi
0x18002bf16  setz    r14b
0x18002bf1a  test    rdi, rdi
0x18002bf1d  jz      short loc_18002BF65
0x18002bf1f  mov     rax, [rdi]
0x18002bf22  mov     rcx, rdi
0x18002bf25  mov     rax, [rax+10h]
0x18002bf29  call    cs:__guard_dispatch_icall_fptr
0x18002bf2f  cmp     al, 3Eh ; '>'
0x18002bf31  jnz     short loc_18002BF65
0x18002bf33  cmp     byte ptr [rsp+1A0h+var_170], 1
0x18002bf38  jg      loc_18002C004
0x18002bf3e  test    r14d, r14d
0x18002bf41  jz      short loc_18002BF93
0x18002bf43  mov     dl, 20h ; ' '; char
0x18002bf45  mov     [rsp+1A0h+var_180], 0
0x18002bf4e  lea     rcx, [rsp+1A0h+var_180]; this
0x18002bf53  mov     [rsp+1A0h+var_170], 0
0x18002bf5b  call    ?doPchar@DName@@AEAAXD@Z; DName::doPchar(char)
0x18002bf60  mov     rdi, [rsp+1A0h+var_180]
0x18002bf65  lea     r14, ??_7charNode@@6B@; const charNode::`vftable'
0x18002bf6c  cmp     byte ptr [rsp+1A0h+var_170], 1
0x18002bf71  jg      loc_18002C004
0x18002bf77  test    rdi, rdi
0x18002bf7a  jnz     short loc_18002BFD0
0x18002bf7c  mov     dl, 3Eh ; '>'; char
0x18002bf7e  mov     [rsp+1A0h+var_180], rdi
0x18002bf83  lea     rcx, [rsp+1A0h+var_180]; this
0x18002bf88  mov     [rsp+1A0h+var_170], edi
0x18002bf8c  call    ?doPchar@DName@@AEAAXD@Z; DName::doPchar(char)
0x18002bf91  jmp     short loc_18002BFFF
0x18002bf93  mov     rcx, [rsp+1A0h+var_178]
0x18002bf98  mov     edx, 10h; unsigned __int64
0x18002bf9d  add     rcx, 0D8h; this
0x18002bfa4  call    ?getMemoryWithBuffer@_HeapManager@@QEAAPEAX_K@Z; _HeapManager::getMemoryWithBuffer(unsigned __int64)
0x18002bfa9  lea     r14, ??_7charNode@@6B@; const charNode::`vftable'
0x18002bfb0  test    rax, rax
0x18002bfb3  jz      short loc_18002BFBC
0x18002bfb5  mov     [rax], r14
0x18002bfb8  mov     byte ptr [rax+8], 20h ; ' '
0x18002bfbc  mov     rdx, rax
0x18002bfbf  lea     rcx, [rsp+1A0h+var_180]
0x18002bfc4  call    ??$append@VcharNode@@@DName@@AEAAXPEBVcharNode@@@Z; DName::append<charNode>(charNode const *)
0x18002bfc9  mov     rdi, [rsp+1A0h+var_180]
0x18002bfce  jmp     short loc_18002BF6C
0x18002bfd0  mov     rcx, [rsp+1A0h+var_178]
0x18002bfd5  mov     edx, 10h; unsigned __int64
0x18002bfda  add     rcx, 0D8h; this
0x18002bfe1  call    ?getMemoryWithBuffer@_HeapManager@@QEAAPEAX_K@Z; _HeapManager::getMemoryWithBuffer(unsigned __int64)
0x18002bfe6  test    rax, rax
0x18002bfe9  jz      short loc_18002BFF2
0x18002bfeb  mov     [rax], r14
0x18002bfee  mov     byte ptr [rax+8], 3Eh ; '>'
0x18002bff2  mov     rdx, rax
0x18002bff5  lea     rcx, [rsp+1A0h+var_180]
0x18002bffa  call    ??$append@VcharNode@@@DName@@AEAAXPEBVcharNode@@@Z; DName::append<charNode>(charNode const *)
0x18002bfff  mov     rdi, [rsp+1A0h+var_180]
0x18002c004  test    r15b, r15b
0x18002c007  jz      short loc_18002C01F
0x18002c009  mov     rax, [rbx+100h]
0x18002c010  cmp     byte ptr [rax], 0
0x18002c013  jz      short loc_18002C01F
0x18002c015  inc     rax
0x18002c018  mov     [rbx+100h], rax
0x18002c01f  mov     ecx, [rsp+1A0h+var_170]
0x18002c023  mov     rax, [rbp+0A0h+arg_18]
0x18002c02a  mov     [rbx+0D0h], rax
0x18002c031  mov     rax, [rsp+1A0h+var_178]
0x18002c036  mov     [rbx+60h], r12
0x18002c03a  mov     [rbx+0C8h], r13
0x18002c041  mov     [rsi+8], rax
0x18002c045  mov     [rsi], rdi
0x18002c048  mov     [rsi+10h], ecx
0x18002c04b  jmp     short loc_18002C05E
0x18002c04d  mov     r8d, 2
0x18002c053  mov     rdx, rbx
0x18002c056  mov     rcx, rsi
0x18002c059  call    ??0DName@@QEAA@PEAVUnDecorator@@W4DNameStatus@@@Z; DName::DName(UnDecorator *,DNameStatus)
0x18002c05e  mov     rbx, [rsp+1A0h+arg_8]
0x18002c066  mov     rax, rsi
0x18002c069  add     rsp, 170h
0x18002c070  pop     r15
0x18002c072  pop     r14
0x18002c074  pop     r13
0x18002c076  pop     r12
0x18002c078  pop     rdi
0x18002c079  pop     rsi
0x18002c07a  pop     rbp
0x18002c07b  retn
```
