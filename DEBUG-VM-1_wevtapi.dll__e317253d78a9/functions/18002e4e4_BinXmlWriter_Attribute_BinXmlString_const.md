# BinXmlWriter::Attribute(BinXmlString const &)

- ea: `0x18002e4e4`
- end: `0x18002e5e8`
- name: `?Attribute@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z`
- size: `260`
- prototype: `void __fastcall(BinXmlWriter *__hidden this, const struct BinXmlString *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002e29c`
- `0x18002eb48`

## callees

- `0x180003780`
- `0x180008b20`
- `0x180023548`
- `0x18002e4e4`
- `0x18002f7c0`
- `0x180038fb4`

## pseudocode

```c
void __fastcall BinXmlWriter::Attribute(BinXmlWriter *this, const struct BinXmlString *a2)
{
  bool v2; // zf
  __int64 v5; // rax
  WriteBuffer *v6; // rcx
  Write *v7; // rcx
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v9; // [rsp+30h] [rbp-28h]
  int v10; // [rsp+38h] [rbp-20h]
  int v11; // [rsp+3Ch] [rbp-1Ch]
  int v12; // [rsp+40h] [rbp-18h]
  char v13; // [rsp+60h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 19) == 0;
  *((_QWORD *)this + 10) = 0;
  if ( v2 )
  {
    v5 = *((_QWORD *)this + 7);
    if ( *((_QWORD *)this + 6) == v5 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids, 13);
      }
      v9 = 0;
      v10 = 13;
      v11 = -1;
      pExceptionObject = 0;
      v12 = 638;
      throw (EvtException *)&pExceptionObject;
    }
    *(_BYTE *)(*(unsigned int *)(v5 - 8) + *(_QWORD *)(*(_QWORD *)this + 8LL)) |= 0x40u;
    v6 = *(WriteBuffer **)this;
    *((_DWORD *)this + 18) = *(_DWORD *)(*(_QWORD *)this + 16LL);
    WriteBuffer::SetCurrentIndex(v6, *((_DWORD *)v6 + 4) + 4);
  }
  else
  {
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + *((unsigned int *)this + 19)) |= 0x40u;
  }
  v7 = *(Write **)this;
  *((_DWORD *)this + 19) = *(_DWORD *)(*(_QWORD *)this + 16LL);
  v13 = 6;
  WriteBuffer::Write(v7, &v13, 1u);
  BinXmlWriter::WriteName(this, a2);
}

```

## disassembly

```asm
0x18002e4e4  mov     [rsp+arg_8], rbx
0x18002e4e9  push    rdi
0x18002e4ea  sub     rsp, 50h
0x18002e4ee  cmp     dword ptr [rcx+4Ch], 0
0x18002e4f2  mov     rdi, rdx
0x18002e4f5  mov     rbx, rcx
0x18002e4f8  mov     qword ptr [rcx+50h], 0
0x18002e500  jnz     loc_18002E5A6
0x18002e506  mov     rax, [rcx+38h]
0x18002e50a  cmp     [rcx+30h], rax
0x18002e50e  jnz     short loc_18002E582
0x18002e510  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e517  lea     rax, WPP_GLOBAL_Control
0x18002e51e  mov     ebx, 0Dh
0x18002e523  cmp     rcx, rax
0x18002e526  jz      short loc_18002E54A
0x18002e528  test    byte ptr [rcx+1Ch], 2
0x18002e52c  jz      short loc_18002E54A
0x18002e52e  cmp     byte ptr [rcx+19h], 2
0x18002e532  jb      short loc_18002E54A
0x18002e534  mov     rcx, [rcx+10h]
0x18002e538  lea     edx, [rbx+8]
0x18002e53b  mov     r9d, ebx
0x18002e53e  lea     r8, WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids
0x18002e545  call    WPP_SF_D
0x18002e54a  xorps   xmm0, xmm0
0x18002e54d  mov     [rsp+58h+var_28], 0
0x18002e556  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002e55d  mov     [rsp+58h+var_20], ebx
0x18002e561  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002e566  mov     [rsp+58h+var_1C], 0FFFFFFFFh
0x18002e56e  movdqu  [rsp+58h+pExceptionObject], xmm0
0x18002e574  mov     [rsp+58h+var_18], 27Eh
0x18002e57c  call    _CxxThrowException_0
0x18002e582  mov     edx, [rax-8]
0x18002e585  mov     rax, [rcx]
0x18002e588  mov     rcx, [rax+8]
0x18002e58c  or      byte ptr [rdx+rcx], 40h
0x18002e590  mov     rcx, [rbx]; this
0x18002e593  mov     eax, [rcx+10h]
0x18002e596  mov     [rbx+48h], eax
0x18002e599  mov     edx, [rcx+10h]
0x18002e59c  add     edx, 4; unsigned int
0x18002e59f  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x18002e5a4  jmp     short loc_18002E5B4
0x18002e5a6  mov     rax, [rcx]
0x18002e5a9  mov     edx, [rcx+4Ch]
0x18002e5ac  mov     rcx, [rax+8]
0x18002e5b0  or      byte ptr [rcx+rdx], 40h
0x18002e5b4  mov     rcx, [rbx]; this
0x18002e5b7  lea     rdx, [rsp+58h+arg_0]; void *
0x18002e5bc  mov     r8d, 1; unsigned int
0x18002e5c2  mov     eax, [rcx+10h]
0x18002e5c5  mov     [rbx+4Ch], eax
0x18002e5c8  mov     [rsp+58h+arg_0], 6
0x18002e5cd  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002e5d2  mov     rdx, rdi; struct BinXmlString *
0x18002e5d5  mov     rcx, rbx; this
0x18002e5d8  call    ?WriteName@BinXmlWriter@@AEAAXAEBVBinXmlString@@@Z; BinXmlWriter::WriteName(BinXmlString const &)
0x18002e5dd  mov     rbx, [rsp+58h+arg_8]
0x18002e5e2  add     rsp, 50h
0x18002e5e6  pop     rdi
0x18002e5e7  retn
```
