# BinXmlReader::InternalCopyInto(BinXmlWriter &)

- ea: `0x18002fd5c`
- end: `0x18002fe1e`
- name: `?InternalCopyInto@BinXmlReader@@AEAAXAEAVBinXmlWriter@@@Z`
- size: `194`
- prototype: `void __fastcall(BinXmlReader *__hidden this, struct BinXmlWriter *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002404c`
- `0x1800243cc`

## callees

- `0x180004070`
- `0x180013830`
- `0x1800243cc`
- `0x1800249f0`
- `0x18002e29c`
- `0x18002fd5c`

## pseudocode

```c
void __fastcall BinXmlReader::InternalCopyInto(BinXmlReader *this, struct BinXmlWriter *a2)
{
  __int64 v4; // [rsp+20h] [rbp-50h] BYREF
  int v5; // [rsp+28h] [rbp-48h]
  __int64 v6; // [rsp+2Ch] [rbp-44h]
  char v7; // [rsp+34h] [rbp-3Ch]
  _OWORD v8[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v9; // [rsp+58h] [rbp-18h]
  __int64 v10; // [rsp+60h] [rbp-10h]

  v4 = 0;
  v5 = -1;
  v6 = 0;
  v7 = 0;
  do
  {
    BinXmlReader::NextToken(this, (struct BinXmlToken *)&v4, 0);
    if ( HIDWORD(v6) == 12 )
    {
      v9 = *((_QWORD *)this + 11);
      v10 = *((_QWORD *)a2 + 1);
      memset(v8, 0, sizeof(v8));
      BinXmlReader::ReadTemplateDefinition(this, (struct BinXmlTemplate *)v8);
      BinXmlReader::CopyTemplateInstanceInto(this, (struct BinXmlTemplate *)v8, this, a2);
    }
    else
    {
      BinXmlWriter::AddToken(a2, (const struct BinXmlToken *)&v4);
    }
  }
  while ( HIDWORD(v6) );
}

```

## disassembly

```asm
0x18002fd5c  mov     [rsp-8+arg_10], rbx
0x18002fd61  mov     [rsp-8+arg_18], rdi
0x18002fd66  push    rbp
0x18002fd67  mov     rbp, rsp
0x18002fd6a  sub     rsp, 70h
0x18002fd6e  mov     rax, cs:__security_cookie
0x18002fd75  xor     rax, rsp
0x18002fd78  mov     [rbp+var_8], rax
0x18002fd7c  mov     rdi, rdx
0x18002fd7f  mov     [rbp+var_50], 0
0x18002fd87  mov     rbx, rcx
0x18002fd8a  mov     [rbp+var_48], 0FFFFFFFFh
0x18002fd91  mov     [rbp+var_44], 0
0x18002fd99  mov     [rbp+var_3C], 0
0x18002fd9d  xor     r8d, r8d; bool
0x18002fda0  lea     rdx, [rbp+var_50]; struct BinXmlToken *
0x18002fda4  mov     rcx, rbx; this
0x18002fda7  call    ?NextToken@BinXmlReader@@QEAAXAEAUBinXmlToken@@_N@Z; BinXmlReader::NextToken(BinXmlToken &,bool)
0x18002fdac  cmp     dword ptr [rbp+var_44+4], 0Ch
0x18002fdb0  jz      short loc_18002FDC0
0x18002fdb2  lea     rdx, [rbp+var_50]; struct BinXmlToken *
0x18002fdb6  mov     rcx, rdi; this
0x18002fdb9  call    ?AddToken@BinXmlWriter@@QEAAXAEBUBinXmlToken@@@Z; BinXmlWriter::AddToken(BinXmlToken const &)
0x18002fdbe  jmp     short loc_18002FDFA
0x18002fdc0  mov     rax, [rbx+58h]
0x18002fdc4  lea     rdx, [rbp+var_38]; struct BinXmlTemplate *
0x18002fdc8  xorps   xmm0, xmm0
0x18002fdcb  mov     [rbp+var_18], rax
0x18002fdcf  mov     rax, [rdi+8]
0x18002fdd3  mov     rcx, rbx; this
0x18002fdd6  mov     [rbp+var_10], rax
0x18002fdda  movdqu  [rbp+var_38], xmm0
0x18002fddf  movups  [rbp+var_28], xmm0
0x18002fde3  call    ?ReadTemplateDefinition@BinXmlReader@@QEAAXAEAVBinXmlTemplate@@@Z; BinXmlReader::ReadTemplateDefinition(BinXmlTemplate &)
0x18002fde8  mov     r9, rdi; struct BinXmlWriter *
0x18002fdeb  lea     rdx, [rbp+var_38]; struct BinXmlTemplate *
0x18002fdef  mov     r8, rbx; struct UserBuffer *
0x18002fdf2  mov     rcx, rbx; this
0x18002fdf5  call    ?CopyTemplateInstanceInto@BinXmlReader@@AEAAXAEAVBinXmlTemplate@@AEAVUserBuffer@@AEAVBinXmlWriter@@@Z; BinXmlReader::CopyTemplateInstanceInto(BinXmlTemplate &,UserBuffer &,BinXmlWriter &)
0x18002fdfa  cmp     dword ptr [rbp+var_44+4], 0
0x18002fdfe  jnz     short loc_18002FD9D
0x18002fe00  mov     rcx, [rbp+var_8]
0x18002fe04  xor     rcx, rsp; StackCookie
0x18002fe07  call    __security_check_cookie
0x18002fe0c  lea     r11, [rsp+70h+var_s0]
0x18002fe11  mov     rbx, [r11+20h]
0x18002fe15  mov     rdi, [r11+28h]
0x18002fe19  mov     rsp, r11
0x18002fe1c  pop     rbp
0x18002fe1d  retn
```
