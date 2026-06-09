# BinXmlWriter::EndCurrentElement(void)

- ea: `0x18002e704`
- end: `0x18002e895`
- name: `?EndCurrentElement@BinXmlWriter@@AEAAXXZ`
- size: `401`
- prototype: `void __fastcall(BinXmlWriter *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002e660`
- `0x18002e89c`

## callees

- `0x18000314c`
- `0x180003780`
- `0x180008b20`
- `0x180023548`
- `0x18002e704`
- `0x180038fb4`

## pseudocode

```c
void __fastcall BinXmlWriter::EndCurrentElement(BinXmlWriter *this)
{
  __int64 v2; // r8
  unsigned int v3; // esi
  _QWORD *v4; // rdx
  WriteBuffer *v5; // rcx
  unsigned int v6; // ebx
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+38h] [rbp-20h]
  int v10; // [rsp+3Ch] [rbp-1Ch]
  int v11; // [rsp+40h] [rbp-18h]
  int v12; // [rsp+80h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 7);
  if ( *((_QWORD *)this + 6) == v2 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids, 13);
    }
    v9 = 13;
    v10 = -1;
    v8 = 0;
    v11 = 512;
    pExceptionObject = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v3 = *(_DWORD *)(v2 - 8) + (*((_BYTE *)this + 105) != 0 ? 3 : 1);
  utl::vector<BinXmlWriter::ElementInfo,utl::allocator<BinXmlWriter::ElementInfo>>::pop_back((char *)this + 48);
  if ( v3 > 0x7FFFFFFF )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids, 13);
    }
    v9 = 13;
    v10 = -1;
    v8 = 0;
    v11 = 526;
    pExceptionObject = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *((_DWORD *)this + 20) && *((_DWORD *)this + 21) && (*v4 == v4[1] || !*(_BYTE *)(*((_QWORD *)this + 7) - 4LL)) )
  {
    WriteBuffer::SetCurrentIndex(*(WriteBuffer **)this, *((_DWORD *)this + 20));
    if ( *((_DWORD *)this + 21) != -1 )
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + *((unsigned int *)this + 21)) &= ~0x40u;
  }
  v5 = *(WriteBuffer **)this;
  *((_QWORD *)this + 10) = 0;
  v12 = *((_DWORD *)v5 + 4) - v3 - 3;
  v6 = *((_DWORD *)v5 + 4);
  WriteBuffer::SetCurrentIndex(v5, v3);
  WriteBuffer::Write(*(Write **)this, &v12, 4u);
  WriteBuffer::SetCurrentIndex(*(WriteBuffer **)this, v6);
}

```

## disassembly

```asm
0x18002e704  push    rbp
0x18002e706  push    rbx
0x18002e707  push    rsi
0x18002e708  push    rdi
0x18002e709  mov     rbp, rsp
0x18002e70c  sub     rsp, 58h
0x18002e710  lea     rdx, [rcx+30h]
0x18002e714  mov     rdi, rcx
0x18002e717  mov     r8, [rdx+8]
0x18002e71b  cmp     [rdx], r8
0x18002e71e  jnz     short loc_18002E78A
0x18002e720  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e727  lea     rax, WPP_GLOBAL_Control
0x18002e72e  mov     edi, 0Dh
0x18002e733  cmp     rcx, rax
0x18002e736  jz      short loc_18002E75A
0x18002e738  test    byte ptr [rcx+1Ch], 2
0x18002e73c  jz      short loc_18002E75A
0x18002e73e  cmp     byte ptr [rcx+19h], 2
0x18002e742  jb      short loc_18002E75A
0x18002e744  mov     rcx, [rcx+10h]
0x18002e748  lea     edx, [rdi+5]
0x18002e74b  mov     r9d, edi
0x18002e74e  lea     r8, WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids
0x18002e755  call    WPP_SF_D
0x18002e75a  xorps   xmm0, xmm0
0x18002e75d  mov     [rbp+var_20], edi
0x18002e760  xor     ebx, ebx
0x18002e762  mov     [rbp+var_1C], 0FFFFFFFFh
0x18002e769  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002e770  mov     [rbp+var_28], rbx
0x18002e774  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002e778  mov     [rbp+var_18], 200h
0x18002e77f  movdqu  [rbp+pExceptionObject], xmm0
0x18002e784  call    _CxxThrowException_0
0x18002e78a  mov     al, [rcx+69h]
0x18002e78d  neg     al
0x18002e78f  sbb     ecx, ecx
0x18002e791  and     ecx, 2
0x18002e794  lea     esi, [rcx+1]
0x18002e797  mov     rcx, rdx
0x18002e79a  add     esi, [r8-8]
0x18002e79e  call    ?pop_back@?$vector@UElementInfo@BinXmlWriter@@V?$allocator@UElementInfo@BinXmlWriter@@@utl@@@utl@@QEAAXXZ; utl::vector<BinXmlWriter::ElementInfo,utl::allocator<BinXmlWriter::ElementInfo>>::pop_back(void)
0x18002e7a3  cmp     esi, 7FFFFFFFh
0x18002e7a9  jbe     short loc_18002E815
0x18002e7ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7b2  lea     rax, WPP_GLOBAL_Control
0x18002e7b9  mov     edi, 0Dh
0x18002e7be  cmp     rcx, rax
0x18002e7c1  jz      short loc_18002E7E5
0x18002e7c3  test    byte ptr [rcx+1Ch], 2
0x18002e7c7  jz      short loc_18002E7E5
0x18002e7c9  cmp     byte ptr [rcx+19h], 2
0x18002e7cd  jb      short loc_18002E7E5
0x18002e7cf  mov     rcx, [rcx+10h]
0x18002e7d3  lea     edx, [rdi+6]
0x18002e7d6  mov     r9d, edi
0x18002e7d9  lea     r8, WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids
0x18002e7e0  call    WPP_SF_D
0x18002e7e5  xorps   xmm0, xmm0
0x18002e7e8  mov     [rbp+var_20], edi
0x18002e7eb  xor     ebx, ebx
0x18002e7ed  mov     [rbp+var_1C], 0FFFFFFFFh
0x18002e7f4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002e7fb  mov     [rbp+var_28], rbx
0x18002e7ff  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002e803  mov     [rbp+var_18], 20Eh
0x18002e80a  movdqu  [rbp+pExceptionObject], xmm0
0x18002e80f  call    _CxxThrowException_0
0x18002e815  xor     ebx, ebx
0x18002e817  cmp     [rdi+50h], ebx
0x18002e81a  jz      short loc_18002E854
0x18002e81c  cmp     [rdi+54h], ebx
0x18002e81f  jz      short loc_18002E854
0x18002e821  mov     rax, [rdx+8]
0x18002e825  cmp     [rdx], rax
0x18002e828  jz      short loc_18002E833
0x18002e82a  mov     rax, [rdi+38h]
0x18002e82e  cmp     [rax-4], bl
0x18002e831  jnz     short loc_18002E854
0x18002e833  mov     edx, [rdi+50h]; unsigned int
0x18002e836  mov     rcx, [rdi]; this
0x18002e839  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x18002e83e  cmp     dword ptr [rdi+54h], 0FFFFFFFFh
0x18002e842  jz      short loc_18002E854
0x18002e844  mov     rax, [rdi]
0x18002e847  mov     r8d, [rdi+54h]
0x18002e84b  mov     rcx, [rax+8]
0x18002e84f  and     byte ptr [rcx+r8], 0BFh
0x18002e854  mov     rcx, [rdi]; this
0x18002e857  mov     edx, esi; unsigned int
0x18002e859  mov     [rdi+50h], rbx
0x18002e85d  mov     eax, [rcx+10h]
0x18002e860  sub     eax, esi
0x18002e862  sub     eax, 3
0x18002e865  mov     [rbp+arg_0], eax
0x18002e868  mov     ebx, [rcx+10h]
0x18002e86b  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x18002e870  mov     rcx, [rdi]; this
0x18002e873  lea     rdx, [rbp+arg_0]; void *
0x18002e877  mov     r8d, 4; unsigned int
0x18002e87d  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18002e882  mov     rcx, [rdi]; this
0x18002e885  mov     edx, ebx; unsigned int
0x18002e887  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x18002e88c  add     rsp, 58h
0x18002e890  pop     rdi
0x18002e891  pop     rsi
0x18002e892  pop     rbx
0x18002e893  pop     rbp
0x18002e894  retn
```
