# WriterStringTable::WriteString(WriteBuffer &,BinXmlString const &)

- ea: `0x180035c70`
- end: `0x180035eed`
- name: `?WriteString@WriterStringTable@@UEAAXAEAVWriteBuffer@@AEBVBinXmlString@@@Z`
- size: `637`
- prototype: `void(WriterStringTable *__hidden this, struct WriteBuffer *, const struct BinXmlString *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x180003780`
- `0x180013180`
- `0x180013650`
- `0x18001ab4c`
- `0x180023548`
- `0x18002fec0`
- `0x180034d80`
- `0x180035c70`
- `0x180038fb4`
- `0x180038fc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WriterStringTable::WriteString(
        WriterStringTable *this,
        struct WriteBuffer *a2,
        const struct BinXmlString *a3)
{
  __int64 v6; // r14
  unsigned int v7; // r10d
  __int64 v8; // rdx
  unsigned int v9; // r8d
  unsigned int v10; // r10d
  __int64 v11; // r8
  unsigned int *v12; // r15
  void *Buf2; // [rsp+20h] [rbp-50h] BYREF
  int v14; // [rsp+28h] [rbp-48h]
  char v15; // [rsp+2Ch] [rbp-44h]
  __int64 v16; // [rsp+30h] [rbp-40h] BYREF
  int v17; // [rsp+38h] [rbp-38h]
  int v18; // [rsp+3Ch] [rbp-34h]
  __int128 pExceptionObject; // [rsp+40h] [rbp-30h] BYREF
  __int64 v20; // [rsp+50h] [rbp-20h]
  int v21; // [rsp+58h] [rbp-18h]
  __int64 v22; // [rsp+5Ch] [rbp-14h]
  char v23; // [rsp+64h] [rbp-Ch]
  unsigned int v24; // [rsp+A0h] [rbp+30h] BYREF
  int v25; // [rsp+B0h] [rbp+40h] BYREF

  v6 = *((_WORD *)a3 + 4) & 0x3F;
  v7 = *(_DWORD *)(*((_QWORD *)this + 1) + 4 * v6);
  v24 = v7;
  v8 = *((_QWORD *)this + 34);
  v9 = *(_DWORD *)(v8 + 32) - *(_DWORD *)(v8 + 24);
  if ( v7 >= v9 - 4 || LoopExists(v7, *(const unsigned __int8 **)(v8 + 24), v9) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_40f2f4b7590833bbffda41ed85cfa29f_Traceguids, 13);
    }
    pExceptionObject = 0;
    v20 = 0;
    v21 = 13;
    v22 = 0x2FFFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  while ( 1 )
  {
    v11 = *((_QWORD *)this + 34);
    if ( !v10 )
      break;
    v12 = (unsigned int *)(*(_QWORD *)(v11 + 24) + v10);
    v16 = *(_QWORD *)(v11 + 24);
    v17 = 0;
    v18 = *(_DWORD *)(v11 + 32) - *(_DWORD *)(v11 + 24);
    UserBuffer::Advance((UserBuffer *)&v16, (_DWORD)v12 - *(_DWORD *)(v11 + 24) + 4);
    Buf2 = &unk_180040824;
    v14 = 0;
    v15 = 1;
    BinXmlString::Deserialize((BinXmlString *)&Buf2, (struct UserBuffer *)&v16);
    if ( v14 == *((_DWORD *)a3 + 2) && !memcmp_0(*(const void **)a3, Buf2, 2LL * *((unsigned __int16 *)a3 + 5)) )
    {
      WriteBuffer::Write(a2, &v24, 4u);
      BinXmlString::~BinXmlString((BinXmlString *)&Buf2);
      return;
    }
    v24 = *v12;
    BinXmlString::~BinXmlString((BinXmlString *)&Buf2);
    v10 = v24;
  }
  if ( *(_QWORD *)(v11 + 56) + 2 * ((unsigned __int64)*((unsigned __int16 *)a3 + 5) + 6) >= *(_QWORD *)(v11 + 32) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_40f2f4b7590833bbffda41ed85cfa29f_Traceguids, 111);
    }
    *(_QWORD *)&pExceptionObject = &word_18004024A;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v20 = 0;
    v21 = 111;
    v22 = -1;
    v23 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v25 = *((_DWORD *)a2 + 4) + 4;
  WriteBuffer::Write(a2, &v25, 4u);
  WriteBuffer::Write(a2, (const void *)(*((_QWORD *)this + 1) + 4 * v6), 4u);
  *(_DWORD *)(*((_QWORD *)this + 1) + 4 * v6) = v25;
  BinXmlString::Serialize(a3, a2);
}

```

## disassembly

```asm
0x180035c70  mov     [rsp-28h+arg_8], rbx
0x180035c75  push    rbp
0x180035c76  push    rsi
0x180035c77  push    rdi
0x180035c78  push    r14
0x180035c7a  push    r15
0x180035c7c  mov     rbp, rsp
0x180035c7f  sub     rsp, 70h
0x180035c83  mov     rbx, r8
0x180035c86  mov     rdi, rdx
0x180035c89  mov     rsi, rcx
0x180035c8c  movzx   r14d, word ptr [r8+8]
0x180035c91  and     r14d, 3Fh
0x180035c95  mov     rax, [rcx+8]
0x180035c99  mov     r10d, [rax+r14*4]
0x180035c9d  mov     [rbp+arg_0], r10d
0x180035ca1  mov     rdx, [rcx+110h]
0x180035ca8  mov     eax, [rdx+20h]
0x180035cab  sub     eax, [rdx+18h]
0x180035cae  mov     r8d, eax; unsigned int
0x180035cb1  add     eax, 0FFFFFFFCh
0x180035cb4  cmp     r10d, eax
0x180035cb7  jnb     loc_180035E7E
0x180035cbd  mov     rdx, [rdx+18h]; unsigned __int8 *
0x180035cc1  mov     ecx, r10d; unsigned int
0x180035cc4  call    ?LoopExists@@YA_NKPEBEK@Z; LoopExists(ulong,uchar const *,ulong)
0x180035cc9  test    al, al
0x180035ccb  jnz     loc_180035E7E
0x180035cd1  mov     r8, [rsi+110h]
0x180035cd8  test    r10d, r10d
0x180035cdb  jz      loc_180035DA7
0x180035ce1  mov     rax, [r8+18h]
0x180035ce5  mov     r15d, r10d
0x180035ce8  add     r15, rax
0x180035ceb  mov     [rbp+var_40], rax
0x180035cef  mov     [rbp+var_38], 0
0x180035cf6  mov     eax, [r8+20h]
0x180035cfa  sub     eax, [r8+18h]
0x180035cfe  mov     [rbp+var_34], eax
0x180035d01  mov     edx, r15d
0x180035d04  sub     edx, [r8+18h]
0x180035d08  add     edx, 4; unsigned int
0x180035d0b  lea     rcx, [rbp+var_40]; this
0x180035d0f  call    ?Advance@UserBuffer@@QEAAXK@Z; UserBuffer::Advance(ulong)
0x180035d14  lea     rax, unk_180040824
0x180035d1b  mov     [rbp+Buf2], rax
0x180035d1f  xor     eax, eax
0x180035d21  mov     [rbp+var_48], eax
0x180035d24  mov     [rbp+var_44], 1
0x180035d28  lea     rdx, [rbp+var_40]; struct UserBuffer *
0x180035d2c  lea     rcx, [rbp+Buf2]; this
0x180035d30  call    ?Deserialize@BinXmlString@@QEAAXAEAVUserBuffer@@@Z; BinXmlString::Deserialize(UserBuffer &)
0x180035d35  movzx   eax, word ptr [rbx+8]
0x180035d39  cmp     word ptr [rbp+var_48], ax
0x180035d3d  jnz     short loc_180035D5F
0x180035d3f  movzx   eax, word ptr [rbx+0Ah]
0x180035d43  cmp     word ptr [rbp+var_48+2], ax
0x180035d47  jnz     short loc_180035D5F
0x180035d49  mov     r8d, eax
0x180035d4c  add     r8, r8; Size
0x180035d4f  mov     rdx, [rbp+Buf2]; Buf2
0x180035d53  mov     rcx, [rbx]; Buf1
0x180035d56  call    memcmp_0
0x180035d5b  test    eax, eax
0x180035d5d  jz      short loc_180035D77
0x180035d5f  mov     eax, [r15]
0x180035d62  mov     [rbp+arg_0], eax
0x180035d65  lea     rcx, [rbp+Buf2]; this
0x180035d69  call    ??1BinXmlString@@QEAA@XZ; BinXmlString::~BinXmlString(void)
0x180035d6e  mov     r10d, [rbp+arg_0]
0x180035d72  jmp     loc_180035CD1
0x180035d77  mov     r8d, 4; unsigned int
0x180035d7d  lea     rdx, [rbp+arg_0]; void *
0x180035d81  mov     rcx, rdi; this
0x180035d84  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180035d89  nop
0x180035d8a  lea     rcx, [rbp+Buf2]; this
0x180035d8e  call    ??1BinXmlString@@QEAA@XZ; BinXmlString::~BinXmlString(void)
0x180035d93  mov     rbx, [rsp+70h+arg_8]
0x180035d9b  add     rsp, 70h
0x180035d9f  pop     r15
0x180035da1  pop     r14
0x180035da3  pop     rdi
0x180035da4  pop     rsi
0x180035da5  pop     rbp
0x180035da6  retn
0x180035da7  movzx   ecx, word ptr [rbx+0Ah]
0x180035dab  mov     rax, [r8+38h]
0x180035daf  add     rcx, 6
0x180035db3  lea     rcx, [rax+rcx*2]
0x180035db7  cmp     rcx, [r8+20h]
0x180035dbb  jnb     short loc_180035E06
0x180035dbd  mov     eax, [rdi+10h]
0x180035dc0  add     eax, 4
0x180035dc3  mov     [rbp+arg_10], eax
0x180035dc6  mov     r8d, 4; unsigned int
0x180035dcc  lea     rdx, [rbp+arg_10]; void *
0x180035dd0  mov     rcx, rdi; this
0x180035dd3  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180035dd8  mov     rax, [rsi+8]
0x180035ddc  lea     rdx, [rax+r14*4]; void *
0x180035de0  mov     r8d, 4; unsigned int
0x180035de6  mov     rcx, rdi; this
0x180035de9  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180035dee  mov     rcx, [rsi+8]
0x180035df2  mov     eax, [rbp+arg_10]
0x180035df5  mov     [rcx+r14*4], eax
0x180035df9  mov     rdx, rdi; struct WriteBuffer *
0x180035dfc  mov     rcx, rbx; this
0x180035dff  call    ?Serialize@BinXmlString@@QEBAXAEAVWriteBuffer@@@Z; BinXmlString::Serialize(WriteBuffer &)
0x180035e04  jmp     short loc_180035D93
0x180035e06  lea     rax, WPP_GLOBAL_Control
0x180035e0d  mov     ebx, 6Fh ; 'o'
0x180035e12  mov     rcx, cs:WPP_GLOBAL_Control
0x180035e19  cmp     rcx, rax
0x180035e1c  jz      short loc_180035E43
0x180035e1e  test    dword ptr [rcx+1Ch], 200h
0x180035e25  jz      short loc_180035E43
0x180035e27  cmp     byte ptr [rcx+19h], 2
0x180035e2b  jb      short loc_180035E43
0x180035e2d  lea     edx, [rbx-63h]
0x180035e30  mov     r9d, ebx
0x180035e33  lea     r8, WPP_40f2f4b7590833bbffda41ed85cfa29f_Traceguids
0x180035e3a  mov     rcx, [rcx+10h]
0x180035e3e  call    WPP_SF_D
0x180035e43  lea     rax, word_18004024A
0x180035e4a  mov     qword ptr [rbp+pExceptionObject], rax
0x180035e4e  mov     qword ptr [rbp+pExceptionObject+8], 0
0x180035e56  mov     [rbp+var_20], 0
0x180035e5e  mov     [rbp+var_18], ebx
0x180035e61  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x180035e69  mov     [rbp+var_C], 0
0x180035e6d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180035e74  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035e78  call    _CxxThrowException_0
0x180035e7e  lea     rax, WPP_GLOBAL_Control
0x180035e85  mov     ebx, 0Dh
0x180035e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180035e91  cmp     rcx, rax
0x180035e94  jz      short loc_180035EBB
0x180035e96  test    dword ptr [rcx+1Ch], 200h
0x180035e9d  jz      short loc_180035EBB
0x180035e9f  cmp     byte ptr [rcx+19h], 2
0x180035ea3  jb      short loc_180035EBB
0x180035ea5  lea     edx, [rbx-2]
0x180035ea8  mov     r9d, ebx
0x180035eab  lea     r8, WPP_40f2f4b7590833bbffda41ed85cfa29f_Traceguids
0x180035eb2  mov     rcx, [rcx+10h]
0x180035eb6  call    WPP_SF_D
0x180035ebb  xorps   xmm0, xmm0
0x180035ebe  movdqu  [rbp+pExceptionObject], xmm0
0x180035ec3  mov     [rbp+var_20], 0
0x180035ecb  mov     [rbp+var_18], ebx
0x180035ece  mov     dword ptr [rbp+var_14], 0FFFFFFFFh
0x180035ed5  mov     dword ptr [rbp+var_14+4], 2Fh ; '/'
0x180035edc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180035ee3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035ee7  call    _CxxThrowException_0
```
