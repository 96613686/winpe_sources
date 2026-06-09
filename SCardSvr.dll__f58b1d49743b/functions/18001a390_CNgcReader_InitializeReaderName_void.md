# CNgcReader::InitializeReaderName(void)

- ea: `0x18001a390`
- end: `0x18001a535`
- name: `?InitializeReaderName@CNgcReader@@MEAAXXZ`
- size: `421`
- prototype: `void __fastcall(CNgcReader *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x1800044e0`
- `0x18000d7a0`
- `0x1800136a0`
- `0x18001a390`
- `0x18001a53c`
- `0x18001a634`
- `0x18001b304`
- `0x18001b380`
- `0x18001b3fc`
- `0x18001b5b0`
- `0x180023168`
- `0x1800326d0`

## string_xrefs

- `0x18001a3c3`: `CNgcReader::InitializeReaderName`

## pseudocode

```c
void __fastcall CNgcReader::InitializeReaderName(CNgcReader *this)
{
  unsigned __int8 *v2; // rbx
  const unsigned __int8 *v3; // rdx
  __int64 v4; // rdx
  unsigned int v5; // ebx
  const unsigned __int8 *v6; // rax
  int v7; // [rsp+20h] [rbp-69h] BYREF
  void **v8; // [rsp+28h] [rbp-61h] BYREF
  void *Block; // [rsp+30h] [rbp-59h]
  __int64 v10; // [rsp+38h] [rbp-51h]
  _BYTE v11[8]; // [rsp+40h] [rbp-49h] BYREF
  _QWORD *v12; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v13[2]; // [rsp+50h] [rbp-39h] BYREF
  void **v14; // [rsp+60h] [rbp-29h] BYREF
  int v15; // [rsp+68h] [rbp-21h]
  void **v16; // [rsp+70h] [rbp-19h]
  __int64 v17; // [rsp+78h] [rbp-11h]
  __int64 v18; // [rsp+80h] [rbp-9h]
  void **v19; // [rsp+88h] [rbp-1h]
  __int64 v20; // [rsp+90h] [rbp+7h]
  __int64 v21; // [rsp+98h] [rbp+Fh]
  char v22[40]; // [rsp+A0h] [rbp+17h] BYREF

  v7 = 0;
  strcpy(v22, "CNgcReader::InitializeReaderName");
  v13[0] = v22;
  v13[1] = &v7;
  lambda_f6aa99c3fba2956d003b5e0dd5f5b8fc_::operator()(v13);
  v7 = 1;
  v12 = v13;
  CLockWrite::CLockWrite((CLockWrite *)v11, (CNgcReader *)((char *)this + 56));
  v2 = (unsigned __int8 *)&Data;
  v3 = (const unsigned __int8 *)&Data;
  if ( *((_DWORD *)this + 211) )
    v3 = (const unsigned __int8 *)*((_QWORD *)this + 104);
  v8 = &CBuffer::`vftable';
  Block = 0;
  v10 = 0;
  CBuffer::Set((CBuffer *)&v8, v3, *((_DWORD *)this + 210));
  if ( HIDWORD(v10) )
    v2 = (unsigned __int8 *)Block;
  LODWORD(v4) = 0;
  if ( *(_WORD *)v2 )
  {
    do
    {
      if ( *(_WORD *)&v2[2 * (unsigned int)v4] == 92 )
        *(_WORD *)&v2[2 * (unsigned int)v4] = 95;
      v4 = (unsigned int)(v4 + 1);
    }
    while ( *(_WORD *)&v2[2 * v4] );
  }
  v14 = &CTextString::`vftable';
  v16 = &CBuffer::`vftable';
  v17 = 0;
  v18 = 0;
  v19 = &CBuffer::`vftable';
  v20 = 0;
  v21 = 0;
  v15 = 3;
  CTextString::operator+=((CTextString *)&v14, v2);
  v5 = 2 * CTextString::Length((CTextString *)&v14) + 2;
  v6 = (const unsigned __int8 *)CTextString::Unicode((CTextString *)&v14);
  CBuffer::Set((CNgcReader *)((char *)this + 8), v6, v5);
  CTextString::~CTextString((CTextString *)&v14);
  if ( Block )
    operator delete[](Block);
  CLockWrite::~CLockWrite((CLockWrite *)v11);
  WppTraceUnwinder__lambda_f6aa99c3fba2956d003b5e0dd5f5b8fc____::_WppTraceUnwinder__lambda_f6aa99c3fba2956d003b5e0dd5f5b8fc____(&v12);
}

```

## disassembly

```asm
0x18001a390  mov     [rsp-8+arg_8], rbx
0x18001a395  mov     [rsp-8+arg_10], rsi
0x18001a39a  push    rbp
0x18001a39b  push    r14
0x18001a39d  push    r15
0x18001a39f  lea     rbp, [rsp-47h]
0x18001a3a4  sub     rsp, 0D0h
0x18001a3ab  mov     rax, cs:__security_cookie
0x18001a3b2  xor     rax, rsp
0x18001a3b5  mov     [rbp+57h+var_18], rax
0x18001a3b9  mov     rsi, rcx
0x18001a3bc  xor     r14d, r14d
0x18001a3bf  mov     [rbp+57h+var_C0], r14d
0x18001a3c3  movups  xmm0, xmmword ptr cs:aCngcreaderInit; "CNgcReader::InitializeReaderName"
0x18001a3ca  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18001a3ce  movups  xmm1, xmmword ptr cs:aCngcreaderInit+10h; "ializeReaderName"
0x18001a3d5  movups  xmmword ptr [rbp+57h+var_40+10h], xmm1
0x18001a3d9  mov     al, byte ptr cs:aCngcreaderInit+20h; ""
0x18001a3df  mov     [rbp+57h+var_40+20h], al
0x18001a3e2  lea     rax, [rbp+57h+var_40]
0x18001a3e6  mov     [rbp+57h+var_90], rax
0x18001a3ea  lea     rax, [rbp+57h+var_C0]
0x18001a3ee  mov     [rbp+57h+var_88], rax
0x18001a3f2  lea     rcx, [rbp+57h+var_90]
0x18001a3f6  call    _lambda_f6aa99c3fba2956d003b5e0dd5f5b8fc___operator__
0x18001a3fb  mov     [rbp+57h+var_C0], 1
0x18001a402  lea     rax, [rbp+57h+var_90]
0x18001a406  mov     [rbp+57h+var_98], rax
0x18001a40a  lea     rdx, [rsi+38h]; struct CAccessLock *
0x18001a40e  lea     rcx, [rbp+57h+var_A0]; this
0x18001a412  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x18001a417  nop
0x18001a418  lea     rbx, Data
0x18001a41f  cmp     [rsi+34Ch], r14d
0x18001a426  mov     rdx, rbx
0x18001a429  jbe     short loc_18001A432
0x18001a42b  mov     rdx, [rsi+340h]; unsigned __int8 *
0x18001a432  lea     r15, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18001a439  mov     [rbp+57h+var_B8], r15
0x18001a43d  mov     [rbp+57h+Block], r14
0x18001a441  mov     [rbp+57h+var_A8], r14
0x18001a445  mov     r8d, [rsi+348h]; unsigned int
0x18001a44c  lea     rcx, [rbp+57h+var_B8]; this
0x18001a450  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x18001a455  nop
0x18001a456  cmp     dword ptr [rbp+57h+var_A8+4], r14d
0x18001a45a  cmova   rbx, [rbp+57h+Block]
0x18001a45f  mov     edx, r14d
0x18001a462  cmp     r14w, [rbx]
0x18001a466  jz      short loc_18001A484
0x18001a468  mov     eax, edx
0x18001a46a  mov     ecx, 5Ch ; '\'
0x18001a46f  cmp     cx, [rbx+rax*2]
0x18001a473  jnz     short loc_18001A47B
0x18001a475  mov     word ptr [rbx+rax*2], 5Fh ; '_'
0x18001a47b  inc     edx
0x18001a47d  cmp     r14w, [rbx+rdx*2]
0x18001a482  jnz     short loc_18001A468
0x18001a484  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x18001a48b  mov     [rbp+57h+var_80], rax
0x18001a48f  mov     [rbp+57h+var_70], r15
0x18001a493  mov     [rbp+57h+var_68], r14
0x18001a497  mov     [rbp+57h+var_60], r14
0x18001a49b  mov     [rbp+57h+var_58], r15
0x18001a49f  mov     [rbp+57h+var_50], r14
0x18001a4a3  mov     [rbp+57h+var_48], r14
0x18001a4a7  mov     [rbp+57h+var_78], 3
0x18001a4ae  mov     rdx, rbx; unsigned __int8 *
0x18001a4b1  lea     rcx, [rbp+57h+var_80]; this
0x18001a4b5  call    ??YCTextString@@QEAAPEBGPEBG@Z; CTextString::operator+=(ushort const *)
0x18001a4ba  lea     rcx, [rbp+57h+var_80]; this
0x18001a4be  call    ?Length@CTextString@@UEAAKXZ; CTextString::Length(void)
0x18001a4c3  lea     ebx, ds:2[rax*2]
0x18001a4ca  lea     rcx, [rbp+57h+var_80]; this
0x18001a4ce  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x18001a4d3  lea     rcx, [rsi+8]; this
0x18001a4d7  mov     r8d, ebx; unsigned int
0x18001a4da  mov     rdx, rax; unsigned __int8 *
0x18001a4dd  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x18001a4e2  nop
0x18001a4e3  lea     rcx, [rbp+57h+var_80]; this
0x18001a4e7  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x18001a4ec  nop
0x18001a4ed  cmp     [rbp+57h+Block], r14
0x18001a4f1  jz      short loc_18001A4FD
0x18001a4f3  mov     rcx, [rbp+57h+Block]; Block
0x18001a4f7  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18001a4fc  nop
0x18001a4fd  lea     rcx, [rbp+57h+var_A0]; this
0x18001a501  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x18001a506  nop
0x18001a507  lea     rcx, [rbp+57h+var_98]
0x18001a50b  call    WppTraceUnwinder__lambda_f6aa99c3fba2956d003b5e0dd5f5b8fc_______WppTraceUnwinder__lambda_f6aa99c3fba2956d003b5e0dd5f5b8fc____
0x18001a510  mov     rcx, [rbp+57h+var_18]
0x18001a514  xor     rcx, rsp; StackCookie
0x18001a517  call    __security_check_cookie
0x18001a51c  lea     r11, [rsp+0E0h+var_10]
0x18001a524  mov     rbx, [r11+28h]
0x18001a528  mov     rsi, [r11+30h]
0x18001a52c  mov     rsp, r11
0x18001a52f  pop     r15
0x18001a531  pop     r14
0x18001a533  pop     rbp
0x18001a534  retn
```
