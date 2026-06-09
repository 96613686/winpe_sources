# BinXmlWriter::OpenStartElementTag(BinXmlString const &)

- ea: `0x18002e944`
- end: `0x18002eaae`
- name: `?OpenStartElementTag@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z`
- size: `362`
- prototype: `void __fastcall(BinXmlWriter *__hidden this, const struct BinXmlString *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002e29c`
- `0x18002eb48`

## callees

- `0x180003780`
- `0x180008b20`
- `0x180021478`
- `0x180023548`
- `0x18002e944`
- `0x18002f6fc`
- `0x18002f7c0`
- `0x180038fb4`

## pseudocode

```c
void __fastcall BinXmlWriter::OpenStartElementTag(BinXmlWriter *this, const struct BinXmlString *a2)
{
  __int64 v4; // rcx
  __int64 *v5; // rbx
  __int64 v6; // rax
  Write *v7; // rcx
  _QWORD *v8; // rcx
  __int64 v9; // rdi
  __int64 *v10; // rdx
  __int64 v11; // [rsp+20h] [rbp-38h] BYREF
  __int128 pExceptionObject; // [rsp+28h] [rbp-30h] BYREF
  __int64 v13; // [rsp+38h] [rbp-20h]
  int v14; // [rsp+40h] [rbp-18h]
  int v15; // [rsp+44h] [rbp-14h]
  int v16; // [rsp+48h] [rbp-10h]
  __int16 v17; // [rsp+80h] [rbp+28h] BYREF

  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_BYTE *)this + 104) = 1;
  BinXmlWriter::WriteHeaderTokenIfNecessary(this);
  v4 = *(_QWORD *)this;
  v5 = (__int64 *)((char *)this + 48);
  v11 = 0;
  LODWORD(v11) = *(_DWORD *)(v4 + 16);
  if ( *((_QWORD *)this + 6) == *((_QWORD *)this + 7)
    || (v6 = *((_QWORD *)this + 7), BYTE4(v11) = 1, !*(_BYTE *)(v6 - 4)) )
  {
    BYTE4(v11) = 0;
  }
  WriteBuffer::Write((Write *)v4, &unk_180042C38, 1u);
  if ( *((_BYTE *)this + 105) )
  {
    v7 = *(Write **)this;
    v17 = -1;
    WriteBuffer::Write(v7, &v17, 2u);
  }
  WriteBuffer::SetCurrentIndex(*(WriteBuffer **)this, *(_DWORD *)(*(_QWORD *)this + 16LL) + 4);
  BinXmlWriter::WriteName(this, a2);
  v8 = (_QWORD *)*((_QWORD *)this + 7);
  if ( v8 == *((_QWORD **)this + 8) )
  {
    v9 = *v5;
    if ( !(unsigned __int8)utl::vector<BinXmlWriter::ElementInfo,utl::allocator<BinXmlWriter::ElementInfo>>::_Grow(v5) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids, 14);
      }
      v13 = 0;
      v14 = 14;
      v15 = -1;
      pExceptionObject = 0;
      v16 = 614;
      throw (EvtException *)&pExceptionObject;
    }
    v10 = &v11;
    if ( (unsigned __int64)&v11 - v9 < v5[1] - *v5 )
      v10 = (__int64 *)((char *)&v11 + *v5 - v9);
    *(_QWORD *)v5[1] = *v10;
  }
  else
  {
    *v8 = v11;
  }
  v5[1] += 8;
}

```

## disassembly

```asm
0x18002e944  push    rbp
0x18002e946  push    rbx
0x18002e947  push    rsi
0x18002e948  push    rdi
0x18002e949  mov     rbp, rsp
0x18002e94c  sub     rsp, 58h
0x18002e950  mov     rsi, rdx
0x18002e953  mov     qword ptr [rcx+50h], 0
0x18002e95b  mov     rdi, rcx
0x18002e95e  mov     qword ptr [rcx+48h], 0
0x18002e966  mov     byte ptr [rcx+68h], 1
0x18002e96a  call    ?WriteHeaderTokenIfNecessary@BinXmlWriter@@AEAAXXZ; BinXmlWriter::WriteHeaderTokenIfNecessary(void)
0x18002e96f  mov     rcx, [rdi]; this
0x18002e972  lea     rbx, [rdi+30h]
0x18002e976  mov     [rbp+var_38], 0
0x18002e97e  mov     eax, [rcx+10h]
0x18002e981  mov     dword ptr [rbp+var_38], eax
0x18002e984  mov     rax, [rbx+8]
0x18002e988  cmp     [rbx], rax
0x18002e98b  jz      short loc_18002E99B
0x18002e98d  mov     rax, [rdi+38h]
0x18002e991  mov     byte ptr [rbp+var_38+4], 1
0x18002e995  cmp     byte ptr [rax-4], 0
0x18002e999  jnz     short loc_18002E99F
0x18002e99b  mov     byte ptr [rbp+var_38+4], 0
0x18002e99f  mov     r8d, 1; unsigned int
0x18002e9a5  lea     rdx, unk_180042C38; void *
0x18002e9ac  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002e9b1  cmp     byte ptr [rdi+69h], 0
0x18002e9b5  jz      short loc_18002E9D2
0x18002e9b7  mov     rcx, [rdi]; this
0x18002e9ba  lea     rdx, [rbp+arg_0]; void *
0x18002e9be  mov     eax, 0FFFFh
0x18002e9c3  mov     r8d, 2; unsigned int
0x18002e9c9  mov     [rbp+arg_0], ax
0x18002e9cd  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002e9d2  mov     rcx, [rdi]; this
0x18002e9d5  mov     edx, [rcx+10h]
0x18002e9d8  add     edx, 4; unsigned int
0x18002e9db  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x18002e9e0  mov     rdx, rsi; struct BinXmlString *
0x18002e9e3  mov     rcx, rdi; this
0x18002e9e6  call    ?WriteName@BinXmlWriter@@AEAAXAEBVBinXmlString@@@Z; BinXmlWriter::WriteName(BinXmlString const &)
0x18002e9eb  mov     rcx, [rbx+8]
0x18002e9ef  cmp     rcx, [rbx+10h]
0x18002e9f3  jz      short loc_18002EA0A
0x18002e9f5  mov     rax, [rbp+var_38]
0x18002e9f9  mov     [rcx], rax
0x18002e9fc  add     qword ptr [rbx+8], 8
0x18002ea01  add     rsp, 58h
0x18002ea05  pop     rdi
0x18002ea06  pop     rsi
0x18002ea07  pop     rbx
0x18002ea08  pop     rbp
0x18002ea09  retn
0x18002ea0a  mov     rdi, [rbx]
0x18002ea0d  mov     rcx, rbx
0x18002ea10  call    ?_Grow@?$vector@UElementInfo@BinXmlWriter@@V?$allocator@UElementInfo@BinXmlWriter@@@utl@@@utl@@AEAA_NXZ; utl::vector<BinXmlWriter::ElementInfo,utl::allocator<BinXmlWriter::ElementInfo>>::_Grow(void)
0x18002ea15  test    al, al
0x18002ea17  jz      short loc_18002EA42
0x18002ea19  mov     r9, [rbx+8]
0x18002ea1d  lea     rcx, [rbp+var_38]
0x18002ea21  mov     r8, [rbx]
0x18002ea24  lea     rdx, [rbp+var_38]
0x18002ea28  mov     rax, r9
0x18002ea2b  sub     rcx, rdi
0x18002ea2e  sub     rax, r8
0x18002ea31  cmp     rcx, rax
0x18002ea34  jnb     short loc_18002EA3A
0x18002ea36  lea     rdx, [rcx+r8]
0x18002ea3a  mov     rax, [rdx]
0x18002ea3d  mov     [r9], rax
0x18002ea40  jmp     short loc_18002E9FC
0x18002ea42  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea49  lea     rax, WPP_GLOBAL_Control
0x18002ea50  mov     ebx, 0Eh
0x18002ea55  cmp     rcx, rax
0x18002ea58  jz      short loc_18002EA7C
0x18002ea5a  test    byte ptr [rcx+1Ch], 2
0x18002ea5e  jz      short loc_18002EA7C
0x18002ea60  cmp     byte ptr [rcx+19h], 2
0x18002ea64  jb      short loc_18002EA7C
0x18002ea66  mov     rcx, [rcx+10h]
0x18002ea6a  lea     edx, [rbx+6]
0x18002ea6d  mov     r9d, ebx
0x18002ea70  lea     r8, WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids
0x18002ea77  call    WPP_SF_D
0x18002ea7c  xorps   xmm0, xmm0
0x18002ea7f  mov     [rbp+var_20], 0
0x18002ea87  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002ea8e  mov     [rbp+var_18], ebx
0x18002ea91  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002ea95  mov     [rbp+var_14], 0FFFFFFFFh
0x18002ea9c  movdqu  [rbp+pExceptionObject], xmm0
0x18002eaa1  mov     [rbp+var_10], 266h
0x18002eaa8  call    _CxxThrowException_0
```
