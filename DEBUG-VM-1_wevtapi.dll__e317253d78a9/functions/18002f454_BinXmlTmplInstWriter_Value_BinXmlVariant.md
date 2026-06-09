# BinXmlTmplInstWriter::Value(BinXmlVariant &)

- ea: `0x18002f454`
- end: `0x18002f503`
- name: `?Value@BinXmlTmplInstWriter@@QEAAXAEAUBinXmlVariant@@@Z`
- size: `175`
- prototype: `void __fastcall(BinXmlTmplInstWriter *__hidden this, struct BinXmlVariant *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800243cc`
- `0x180026e30`

## callees

- `0x180023548`
- `0x18002e478`
- `0x18002f454`
- `0x18002f8d4`
- `0x180038fb4`

## pseudocode

```c
void __fastcall BinXmlTmplInstWriter::Value(BinXmlTmplInstWriter *this, struct BinXmlVariant *a2)
{
  WriteBuffer *v4; // rcx
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+30h] [rbp-28h]
  int v7; // [rsp+38h] [rbp-20h]
  int v8; // [rsp+3Ch] [rbp-1Ch]
  int v9; // [rsp+40h] [rbp-18h]

  if ( *((_DWORD *)this + 4) >= *((_DWORD *)this + 3) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids, 13);
    }
    v6 = 0;
    v7 = 13;
    v8 = -1;
    pExceptionObject = 0;
    v9 = 270;
    throw (EvtException *)&pExceptionObject;
  }
  v4 = *(WriteBuffer **)this;
  *((_DWORD *)this + 5) = *((_DWORD *)v4 + 4);
  WriteVariantValueData(v4, a2, 0);
  BinXmlTmplInstWriter::AdjustValueSpec(this, *((_DWORD *)a2 + 3));
}

```

## disassembly

```asm
0x18002f454  mov     [rsp+arg_0], rbx
0x18002f459  push    rdi
0x18002f45a  sub     rsp, 50h
0x18002f45e  mov     eax, [rcx+0Ch]
0x18002f461  mov     rdi, rdx
0x18002f464  mov     rbx, rcx
0x18002f467  cmp     [rcx+10h], eax
0x18002f46a  jb      short loc_18002F4DD
0x18002f46c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f473  lea     rax, WPP_GLOBAL_Control
0x18002f47a  mov     ebx, 0Dh
0x18002f47f  cmp     rcx, rax
0x18002f482  jz      short loc_18002F4A5
0x18002f484  test    byte ptr [rcx+1Ch], 2
0x18002f488  jz      short loc_18002F4A5
0x18002f48a  cmp     byte ptr [rcx+19h], 2
0x18002f48e  jb      short loc_18002F4A5
0x18002f490  mov     rcx, [rcx+10h]
0x18002f494  lea     r8, WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids
0x18002f49b  mov     edx, ebx
0x18002f49d  mov     r9d, ebx
0x18002f4a0  call    WPP_SF_D
0x18002f4a5  xorps   xmm0, xmm0
0x18002f4a8  mov     [rsp+58h+var_28], 0
0x18002f4b1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002f4b8  mov     [rsp+58h+var_20], ebx
0x18002f4bc  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002f4c1  mov     [rsp+58h+var_1C], 0FFFFFFFFh
0x18002f4c9  movdqu  [rsp+58h+pExceptionObject], xmm0
0x18002f4cf  mov     [rsp+58h+var_18], 10Eh
0x18002f4d7  call    _CxxThrowException_0
0x18002f4dd  mov     rcx, [rcx]; this
0x18002f4e0  xor     r8d, r8d
0x18002f4e3  mov     eax, [rcx+10h]
0x18002f4e6  mov     [rbx+14h], eax
0x18002f4e9  call    WriteVariantValueData
0x18002f4ee  mov     edx, [rdi+0Ch]; unsigned int
0x18002f4f1  mov     rcx, rbx; this
0x18002f4f4  mov     rbx, [rsp+58h+arg_0]
0x18002f4f9  add     rsp, 50h
0x18002f4fd  pop     rdi
0x18002f4fe  jmp     ?AdjustValueSpec@BinXmlTmplInstWriter@@AEAAXK@Z; BinXmlTmplInstWriter::AdjustValueSpec(ulong)
```
