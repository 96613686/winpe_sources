# UnDecorator::getTemplateName(bool)

- ea: `0x18002c4c4`
- end: `0x18002c7dc`
- name: `?getTemplateName@UnDecorator@@AEAA?AVDName@@_N@Z`
- size: `792`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: ``

## callers

- `0x1800289c4`
- `0x18002c20c`
- `0x18002d9b4`
- `0x18002dea8`

## callees

- `0x180024638`
- `0x180024cc4`
- `0x1800253d0`
- `0x180026a0c`
- `0x180029f10`
- `0x18002a098`
- `0x18002c25c`
- `0x18002c4c4`
- `0x18002d9b4`
- `0x1800603f0`
- `0x180060550`

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
0x18002c4c4  mov     [rsp-8+arg_8], rbx
0x18002c4c9  push    rbp
0x18002c4ca  push    rsi
0x18002c4cb  push    rdi
0x18002c4cc  push    r12
0x18002c4ce  push    r13
0x18002c4d0  push    r14
0x18002c4d2  push    r15
0x18002c4d4  lea     rbp, [rsp-70h]
0x18002c4d9  sub     rsp, 170h
0x18002c4e0  mov     rax, [rcx+100h]
0x18002c4e7  mov     r15b, r8b
0x18002c4ea  mov     rsi, rdx
0x18002c4ed  mov     rbx, rcx
0x18002c4f0  cmp     byte ptr [rax], 3Fh ; '?'
0x18002c4f3  jnz     loc_18002C7AD
0x18002c4f9  cmp     byte ptr [rax+1], 24h ; '$'
0x18002c4fd  jnz     loc_18002C7AD
0x18002c503  lea     rdi, [rax+2]
0x18002c507  xor     edx, edx; Val
0x18002c509  mov     [rcx+100h], rdi
0x18002c510  mov     rax, [rcx+0D0h]
0x18002c517  mov     r12, [rcx+60h]
0x18002c51b  mov     r13, [rcx+0C8h]
0x18002c522  lea     r8d, [rdx+50h]; Size
0x18002c526  lea     rcx, [rsp+1A0h+var_148]; void *
0x18002c52b  mov     [rbp+0A0h+arg_18], rax
0x18002c532  call    memset
0x18002c537  or      r14d, 0FFFFFFFFh
0x18002c53b  mov     [rbp+0A0h+var_F8], rbx
0x18002c53f  xor     edx, edx; Val
0x18002c541  mov     [rsp+1A0h+var_150], r14d
0x18002c546  lea     rcx, [rbp+0A0h+var_E8]; void *
0x18002c54a  lea     r8d, [r14+51h]; Size
0x18002c54e  call    memset
0x18002c553  xor     edx, edx; Val
0x18002c555  mov     [rbp+0A0h+var_98], rbx
0x18002c559  lea     r8d, [r14+51h]; Size
0x18002c55d  mov     [rbp+0A0h+var_F0], r14d
0x18002c561  lea     rcx, [rbp+0A0h+var_88]; void *
0x18002c565  call    memset
0x18002c56a  lea     rax, [rsp+1A0h+var_150]
0x18002c56f  mov     [rbp+0A0h+var_90], r14d
0x18002c573  mov     [rbx+60h], rax
0x18002c577  lea     rdx, [rsp+1A0h+var_168]
0x18002c57c  lea     rax, [rbp+0A0h+var_F0]
0x18002c580  mov     [rbp+0A0h+var_38], rbx
0x18002c584  mov     [rbx+0C8h], rax
0x18002c58b  xor     r14b, r14b
0x18002c58e  lea     rax, [rbp+0A0h+var_90]
0x18002c592  mov     [rsp+1A0h+var_178], rbx
0x18002c597  mov     [rbx+0D0h], rax
0x18002c59e  mov     rcx, rbx
0x18002c5a1  cmp     byte ptr [rdi], 3Fh ; '?'
0x18002c5a4  mov     [rbp+0A0h+arg_0], r14b
0x18002c5ab  jnz     short loc_18002C5D0
0x18002c5ad  lea     rax, [rdi+1]
0x18002c5b1  mov     r8b, 1
0x18002c5b4  lea     r9, [rbp+0A0h+arg_0]
0x18002c5bb  mov     [rbx+100h], rax
0x18002c5c2  call    ?getOperatorName@UnDecorator@@AEAA?AVDName@@_NPEA_N@Z; UnDecorator::getOperatorName(bool,bool *)
0x18002c5c7  mov     r14b, [rbp+0A0h+arg_0]
0x18002c5ce  jmp     short loc_18002C5DB
0x18002c5d0  mov     r9b, 1
0x18002c5d3  mov     r8b, r9b
0x18002c5d6  call    ?getZName@UnDecorator@@AEAA?AVDName@@_N0@Z; UnDecorator::getZName(bool,bool)
0x18002c5db  mov     rdi, [rax]
0x18002c5de  mov     ecx, [rax+10h]
0x18002c5e1  mov     [rsp+1A0h+var_170], ecx
0x18002c5e5  mov     [rsp+1A0h+var_180], rdi
0x18002c5ea  test    rdi, rdi
0x18002c5ed  jnz     short loc_18002C5F6
0x18002c5ef  mov     byte ptr [rbx+114h], 1
0x18002c5f6  test    r14b, r14b
0x18002c5f9  jnz     loc_18002C783
0x18002c5ff  lea     r14, ??_7charNode@@6B@; const charNode::`vftable'
0x18002c606  cmp     cl, 1
0x18002c609  jg      short loc_18002C651
0x18002c60b  test    rdi, rdi
0x18002c60e  jnz     short loc_18002C627
0x18002c610  mov     dl, 3Ch ; '<'; char
0x18002c612  mov     [rsp+1A0h+var_180], rdi
0x18002c617  lea     rcx, [rsp+1A0h+var_180]; this
0x18002c61c  mov     [rsp+1A0h+var_170], edi
0x18002c620  call    ?doPchar@DName@@AEAAXD@Z; DName::doPchar(char)
0x18002c625  jmp     short loc_18002C651
0x18002c627  lea     rcx, [rbx+0D8h]; this
0x18002c62e  mov     edx, 10h; unsigned __int64
0x18002c633  call    ?getMemoryWithBuffer@_HeapManager@@QEAAPEAX_K@Z; _HeapManager::getMemoryWithBuffer(unsigned __int64)
0x18002c638  test    rax, rax
0x18002c63b  jz      short loc_18002C644
0x18002c63d  mov     [rax], r14
0x18002c640  mov     byte ptr [rax+8], 3Ch ; '<'
0x18002c644  mov     rdx, rax
0x18002c647  lea     rcx, [rsp+1A0h+var_180]
0x18002c64c  call    ??$append@VcharNode@@@DName@@AEAAXPEBVcharNode@@@Z; DName::append<charNode>(charNode const *)
0x18002c651  lea     rdx, [rsp+1A0h+var_168]
0x18002c656  mov     rcx, rbx
0x18002c659  call    ?getTemplateArgumentList@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getTemplateArgumentList(void)
0x18002c65e  mov     rdx, rax
0x18002c661  lea     rcx, [rsp+1A0h+var_180]
0x18002c666  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18002c66b  mov     rdi, [rsp+1A0h+var_180]
0x18002c670  xor     r14d, r14d
0x18002c673  test    rdi, rdi
0x18002c676  setz    r14b
0x18002c67a  test    rdi, rdi
0x18002c67d  jz      short loc_18002C6C5
0x18002c67f  mov     rax, [rdi]
0x18002c682  mov     rcx, rdi
0x18002c685  mov     rax, [rax+10h]
0x18002c689  call    cs:__guard_dispatch_icall_fptr
0x18002c68f  cmp     al, 3Eh ; '>'
0x18002c691  jnz     short loc_18002C6C5
0x18002c693  cmp     byte ptr [rsp+1A0h+var_170], 1
0x18002c698  jg      loc_18002C764
0x18002c69e  test    r14d, r14d
0x18002c6a1  jz      short loc_18002C6F3
0x18002c6a3  mov     dl, 20h ; ' '; char
0x18002c6a5  mov     [rsp+1A0h+var_180], 0
0x18002c6ae  lea     rcx, [rsp+1A0h+var_180]; this
0x18002c6b3  mov     [rsp+1A0h+var_170], 0
0x18002c6bb  call    ?doPchar@DName@@AEAAXD@Z; DName::doPchar(char)
0x18002c6c0  mov     rdi, [rsp+1A0h+var_180]
0x18002c6c5  lea     r14, ??_7charNode@@6B@; const charNode::`vftable'
0x18002c6cc  cmp     byte ptr [rsp+1A0h+var_170], 1
0x18002c6d1  jg      loc_18002C764
0x18002c6d7  test    rdi, rdi
0x18002c6da  jnz     short loc_18002C730
0x18002c6dc  mov     dl, 3Eh ; '>'; char
0x18002c6de  mov     [rsp+1A0h+var_180], rdi
0x18002c6e3  lea     rcx, [rsp+1A0h+var_180]; this
0x18002c6e8  mov     [rsp+1A0h+var_170], edi
0x18002c6ec  call    ?doPchar@DName@@AEAAXD@Z; DName::doPchar(char)
0x18002c6f1  jmp     short loc_18002C75F
0x18002c6f3  mov     rcx, [rsp+1A0h+var_178]
0x18002c6f8  mov     edx, 10h; unsigned __int64
0x18002c6fd  add     rcx, 0D8h; this
0x18002c704  call    ?getMemoryWithBuffer@_HeapManager@@QEAAPEAX_K@Z; _HeapManager::getMemoryWithBuffer(unsigned __int64)
0x18002c709  lea     r14, ??_7charNode@@6B@; const charNode::`vftable'
0x18002c710  test    rax, rax
0x18002c713  jz      short loc_18002C71C
0x18002c715  mov     [rax], r14
0x18002c718  mov     byte ptr [rax+8], 20h ; ' '
0x18002c71c  mov     rdx, rax
0x18002c71f  lea     rcx, [rsp+1A0h+var_180]
0x18002c724  call    ??$append@VcharNode@@@DName@@AEAAXPEBVcharNode@@@Z; DName::append<charNode>(charNode const *)
0x18002c729  mov     rdi, [rsp+1A0h+var_180]
0x18002c72e  jmp     short loc_18002C6CC
0x18002c730  mov     rcx, [rsp+1A0h+var_178]
0x18002c735  mov     edx, 10h; unsigned __int64
0x18002c73a  add     rcx, 0D8h; this
0x18002c741  call    ?getMemoryWithBuffer@_HeapManager@@QEAAPEAX_K@Z; _HeapManager::getMemoryWithBuffer(unsigned __int64)
0x18002c746  test    rax, rax
0x18002c749  jz      short loc_18002C752
0x18002c74b  mov     [rax], r14
0x18002c74e  mov     byte ptr [rax+8], 3Eh ; '>'
0x18002c752  mov     rdx, rax
0x18002c755  lea     rcx, [rsp+1A0h+var_180]
0x18002c75a  call    ??$append@VcharNode@@@DName@@AEAAXPEBVcharNode@@@Z; DName::append<charNode>(charNode const *)
0x18002c75f  mov     rdi, [rsp+1A0h+var_180]
0x18002c764  test    r15b, r15b
0x18002c767  jz      short loc_18002C77F
0x18002c769  mov     rax, [rbx+100h]
0x18002c770  cmp     byte ptr [rax], 0
0x18002c773  jz      short loc_18002C77F
0x18002c775  inc     rax
0x18002c778  mov     [rbx+100h], rax
0x18002c77f  mov     ecx, [rsp+1A0h+var_170]
0x18002c783  mov     rax, [rbp+0A0h+arg_18]
0x18002c78a  mov     [rbx+0D0h], rax
0x18002c791  mov     rax, [rsp+1A0h+var_178]
0x18002c796  mov     [rbx+60h], r12
0x18002c79a  mov     [rbx+0C8h], r13
0x18002c7a1  mov     [rsi+8], rax
0x18002c7a5  mov     [rsi], rdi
0x18002c7a8  mov     [rsi+10h], ecx
0x18002c7ab  jmp     short loc_18002C7BE
0x18002c7ad  mov     r8d, 2
0x18002c7b3  mov     rdx, rbx
0x18002c7b6  mov     rcx, rsi
0x18002c7b9  call    ??0DName@@QEAA@PEAVUnDecorator@@W4DNameStatus@@@Z; DName::DName(UnDecorator *,DNameStatus)
0x18002c7be  mov     rbx, [rsp+1A0h+arg_8]
0x18002c7c6  mov     rax, rsi
0x18002c7c9  add     rsp, 170h
0x18002c7d0  pop     r15
0x18002c7d2  pop     r14
0x18002c7d4  pop     r13
0x18002c7d6  pop     r12
0x18002c7d8  pop     rdi
0x18002c7d9  pop     rsi
0x18002c7da  pop     rbp
0x18002c7db  retn
```
