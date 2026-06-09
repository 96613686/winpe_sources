# UnDecorator::getTemplateTypeArgument(void)

- ea: `0x18002c524`
- end: `0x18002c6a0`
- name: `?getTemplateTypeArgument@UnDecorator@@AEAA?AVDName@@XZ`
- size: `380`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: ``

## callers

- `0x1800267c8`
- `0x18002bafc`
- `0x18002c07c`
- `0x18002cc20`
- `0x18002cdc8`

## callees

- `0x180020450`
- `0x180023d20`
- `0x180024474`
- `0x180024b10`
- `0x180024b44`
- `0x18002a630`
- `0x18002b5ac`
- `0x18002c524`
- `0x180032370`
- `0x180060110`

## string_xrefs

- `0x18002c619`: ``template-parameter`

## pseudocode

```c
DName *__fastcall UnDecorator::getTemplateTypeArgument(__int64 a1, DName *a2)
{
  _BYTE *v2; // rax
  __int64 (__fastcall *v5)(_QWORD); // rbx
  unsigned int v6; // eax
  __int64 v7; // rax
  DName *v8; // rax
  __int64 v9; // r8
  __int128 v11; // [rsp+20h] [rbp-39h] BYREF
  __int64 v12; // [rsp+30h] [rbp-29h] BYREF
  struct UnDecorator *v13; // [rsp+38h] [rbp-21h]
  int v14; // [rsp+40h] [rbp-19h]
  _BYTE v15[24]; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v16[32]; // [rsp+60h] [rbp+7h] BYREF
  char String[16]; // [rsp+80h] [rbp+27h] BYREF

  v2 = *(_BYTE **)(a1 + 256);
  if ( *v2 == 88 )
  {
    *(_DWORD *)&String[8] = 4;
    *(_QWORD *)(a1 + 256) = v2 + 1;
    *(_QWORD *)String = "void";
    v11 = *(_OWORD *)String;
    DName::DName(a2, (struct UnDecorator *)a1, (const struct StringLiteral *)&v11);
  }
  else if ( *v2 == 63 )
  {
    UnDecorator::getSignedDimension(a1, &v12);
    if ( (*(_DWORD *)(a1 + 272) & 0x4000) == 0 || !*(_QWORD *)(a1 + 280) )
      goto LABEL_10;
    *(_OWORD *)String = 0;
    if ( v12 )
      *(_BYTE *)(*(__int64 (__fastcall **)(__int64, char *, char *))(*(_QWORD *)v12 + 24LL))(v12, String, &String[15]) = 0;
    v5 = *(__int64 (__fastcall **)(_QWORD))(a1 + 280);
    v6 = atol(String);
    v7 = v5(v6);
    if ( v7 )
    {
      DName::DName(a2, a1, v7, 0);
    }
    else
    {
LABEL_10:
      *(_QWORD *)&v11 = "`template-parameter";
      DWORD2(v11) = 19;
      v8 = DName::DName((DName *)v16, v13, (const struct StringLiteral *)&v11);
      DName::operator+(v8, v15, &v12);
      LOBYTE(v9) = 39;
      DName::operator+(v15, a2, v9);
    }
  }
  else
  {
    v13 = (struct UnDecorator *)a1;
    v12 = 0;
    v14 = 0;
    UnDecorator::getPrimaryDataType(a1, a2, &v12);
  }
  return a2;
}

```

## disassembly

```asm
0x18002c524  mov     [rsp-8+arg_10], rbx
0x18002c529  push    rbp
0x18002c52a  push    rsi
0x18002c52b  push    rdi
0x18002c52c  lea     rbp, [rsp-47h]
0x18002c531  sub     rsp, 0A0h
0x18002c538  mov     rax, cs:__security_cookie
0x18002c53f  xor     rax, rsp
0x18002c542  mov     [rbp+57h+var_20], rax
0x18002c546  mov     rax, [rcx+100h]
0x18002c54d  mov     rsi, rdx
0x18002c550  mov     rdi, rcx
0x18002c553  cmp     byte ptr [rax], 58h ; 'X'
0x18002c556  jnz     short loc_18002C592
0x18002c558  lea     rcx, [rax+1]
0x18002c55c  mov     dword ptr [rbp+57h+String+8], 4
0x18002c563  lea     rax, aVoid_0; "void"
0x18002c56a  mov     [rdi+100h], rcx
0x18002c571  mov     qword ptr [rbp+57h+String], rax
0x18002c575  lea     r8, [rbp+57h+var_90]; struct StringLiteral *
0x18002c579  movaps  xmm0, xmmword ptr [rbp+57h+String]
0x18002c57d  mov     rdx, rdi; struct UnDecorator *
0x18002c580  mov     rcx, rsi; this
0x18002c583  movdqa  [rbp+57h+var_90], xmm0
0x18002c588  call    ??0DName@@QEAA@PEAVUnDecorator@@AEBUStringLiteral@@@Z; DName::DName(UnDecorator *,StringLiteral const &)
0x18002c58d  jmp     loc_18002C67E
0x18002c592  cmp     byte ptr [rax], 3Fh ; '?'
0x18002c595  jnz     loc_18002C662
0x18002c59b  lea     rdx, [rbp+57h+var_80]
0x18002c59f  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18002c5a4  test    dword ptr [rdi+110h], 4000h
0x18002c5ae  jz      short loc_18002C615
0x18002c5b0  cmp     qword ptr [rdi+118h], 0
0x18002c5b8  jz      short loc_18002C615
0x18002c5ba  mov     rcx, [rbp+57h+var_80]
0x18002c5be  xorps   xmm0, xmm0
0x18002c5c1  movups  xmmword ptr [rbp+57h+String], xmm0
0x18002c5c5  test    rcx, rcx
0x18002c5c8  jz      short loc_18002C5E2
0x18002c5ca  mov     rax, [rcx]
0x18002c5cd  lea     r8, [rbp+57h+String+0Fh]
0x18002c5d1  lea     rdx, [rbp+57h+String]
0x18002c5d5  mov     rax, [rax+18h]
0x18002c5d9  call    cs:__guard_dispatch_icall_fptr
0x18002c5df  mov     byte ptr [rax], 0
0x18002c5e2  mov     rbx, [rdi+118h]
0x18002c5e9  lea     rcx, [rbp+57h+String]; String
0x18002c5ed  call    atol
0x18002c5f2  mov     ecx, eax
0x18002c5f4  mov     rax, rbx
0x18002c5f7  call    cs:__guard_dispatch_icall_fptr
0x18002c5fd  test    rax, rax
0x18002c600  jz      short loc_18002C615
0x18002c602  xor     r9d, r9d
0x18002c605  mov     r8, rax
0x18002c608  mov     rdx, rdi
0x18002c60b  mov     rcx, rsi
0x18002c60e  call    ??$?0$0A@@DName@@QEAA@PEAVUnDecorator@@PEBDU?$StringLifeSelector@$0A@@@@Z; DName::DName(UnDecorator *,char const *,StringLifeSelector<0>)
0x18002c613  jmp     short loc_18002C67E
0x18002c615  mov     rdx, [rbp+57h+var_78]; struct UnDecorator *
0x18002c619  lea     rax, aTemplateParame; "`template-parameter"
0x18002c620  mov     qword ptr [rbp+57h+var_90], rax
0x18002c624  lea     r8, [rbp+57h+var_90]; struct StringLiteral *
0x18002c628  mov     dword ptr [rbp+57h+var_90+8], 13h
0x18002c62f  lea     rcx, [rbp+57h+var_50]; this
0x18002c633  movaps  xmm0, [rbp+57h+var_90]
0x18002c637  movdqa  [rbp+57h+var_90], xmm0
0x18002c63c  call    ??0DName@@QEAA@PEAVUnDecorator@@AEBUStringLiteral@@@Z; DName::DName(UnDecorator *,StringLiteral const &)
0x18002c641  lea     r8, [rbp+57h+var_80]
0x18002c645  mov     rcx, rax
0x18002c648  lea     rdx, [rbp+57h+var_68]
0x18002c64c  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x18002c651  mov     r8b, 27h ; '''
0x18002c654  lea     rcx, [rbp+57h+var_68]
0x18002c658  mov     rdx, rsi
0x18002c65b  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x18002c660  jmp     short loc_18002C67E
0x18002c662  lea     r8, [rbp+57h+var_80]
0x18002c666  mov     [rbp+57h+var_78], rdi
0x18002c66a  mov     [rbp+57h+var_80], 0
0x18002c672  mov     [rbp+57h+var_70], 0
0x18002c679  call    ?getPrimaryDataType@UnDecorator@@AEAA?AVDName@@AEBV2@@Z; UnDecorator::getPrimaryDataType(DName const &)
0x18002c67e  mov     rax, rsi
0x18002c681  mov     rcx, [rbp+57h+var_20]
0x18002c685  xor     rcx, rsp; StackCookie
0x18002c688  call    __security_check_cookie
0x18002c68d  mov     rbx, [rsp+0B0h+arg_10]
0x18002c695  add     rsp, 0A0h
0x18002c69c  pop     rdi
0x18002c69d  pop     rsi
0x18002c69e  pop     rbp
0x18002c69f  retn
```
