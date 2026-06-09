# LocalePublisherTable::_PublisherRecord::Deserialize(Buffer &)

- ea: `0x180036dc0`
- end: `0x180037335`
- name: `?Deserialize@_PublisherRecord@LocalePublisherTable@@QEAAXAEAVBuffer@@@Z`
- size: `1397`
- prototype: `void(LocalePublisherTable::_PublisherRecord *__hidden this, struct Buffer *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180037510`
- `0x180038364`

## callees

- `0x180009e80`
- `0x180013790`
- `0x18001ec1c`
- `0x180023548`
- `0x18003072c`
- `0x180036508`
- `0x180036dc0`
- `0x180038fb4`

## pseudocode

```c
void __fastcall LocalePublisherTable::_PublisherRecord::Deserialize(
        LocalePublisherTable::_PublisherRecord *this,
        struct Buffer *a2)
{
  unsigned int i; // edi
  unsigned int j; // edi
  unsigned int k; // edi
  unsigned int m; // edi
  UserBuffer *v8; // rcx
  __int64 v9; // [rsp+20h] [rbp-40h] BYREF
  unsigned __int64 v10; // [rsp+28h] [rbp-38h]
  __int128 pExceptionObject; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+40h] [rbp-20h]
  int v13; // [rsp+48h] [rbp-18h]
  int v14; // [rsp+4Ch] [rbp-14h]
  int v15; // [rsp+50h] [rbp-10h]
  unsigned int v16; // [rsp+A0h] [rbp+40h] BYREF
  int v17; // [rsp+A8h] [rbp+48h] BYREF
  int v18; // [rsp+B0h] [rbp+50h] BYREF

  v16 = 0;
  v18 = 0;
  v17 = 0;
  utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::clear((char *)this + 32);
  UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v16, 4u);
  for ( i = 0; i < v16; ++i )
  {
    UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v18, 4u);
    UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v17, 4u);
    utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::emplace<unsigned long &,unsigned long &,0>(
      (char *)this + 32,
      &v9,
      &v18,
      &v17);
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
      }
      v12 = 0;
      v13 = 14;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 867;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !(_BYTE)v10 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 13);
      }
      v12 = 0;
      v13 = 13;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 872;
      throw (EvtException *)&pExceptionObject;
    }
  }
  utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::clear((char *)this + 64);
  UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v16, 4u);
  for ( j = 0; j < v16; ++j )
  {
    UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v18, 4u);
    UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v17, 4u);
    utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::emplace<unsigned long &,unsigned long &,0>(
      (char *)this + 64,
      &v9,
      &v18,
      &v17);
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
      }
      v12 = 0;
      v13 = 14;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 886;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !(_BYTE)v10 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 13);
      }
      v12 = 0;
      v13 = 13;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 891;
      throw (EvtException *)&pExceptionObject;
    }
  }
  utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::clear((char *)this + 96);
  UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v16, 4u);
  for ( k = 0; k < v16; ++k )
  {
    UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v18, 4u);
    UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v17, 4u);
    utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::emplace<unsigned long &,unsigned long &,0>(
      (char *)this + 96,
      &v9,
      &v18,
      &v17);
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
      }
      v12 = 0;
      v13 = 14;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 905;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !(_BYTE)v10 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 13);
      }
      v12 = 0;
      v13 = 13;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 910;
      throw (EvtException *)&pExceptionObject;
    }
  }
  utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::clear((char *)this + 128);
  UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v16, 4u);
  for ( m = 0; ; ++m )
  {
    v8 = (struct Buffer *)((char *)a2 + 8);
    if ( m >= v16 )
      break;
    UserBuffer::Read(v8, &v18, 4u);
    UserBuffer::Read((struct Buffer *)((char *)a2 + 8), &v17, 4u);
    utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned long>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned long>>,0>::emplace<unsigned long &,unsigned long &,0>(
      (char *)this + 128,
      &v9,
      &v18,
      &v17);
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
      }
      v12 = 0;
      v13 = 14;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 924;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !(_BYTE)v10 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 13);
      }
      v12 = 0;
      v13 = 13;
      v14 = -1;
      pExceptionObject = 0;
      v15 = 929;
      throw (EvtException *)&pExceptionObject;
    }
  }
  v16 = 0;
  UserBuffer::Read(v8, &v16, 4u);
  v9 = *((_QWORD *)a2 + 1) + *((unsigned int *)a2 + 4);
  v10 = (unsigned __int64)v16 >> 1;
  AssignOrThrowOOM(this, &v9);
  Buffer::Advance(a2, v16);
}

```

## disassembly

```asm
0x180036dc0  push    rbp
0x180036dc2  push    rbx
0x180036dc3  push    rsi
0x180036dc4  push    rdi
0x180036dc5  push    r12
0x180036dc7  push    r14
0x180036dc9  push    r15
0x180036dcb  mov     rbp, rsp
0x180036dce  sub     rsp, 60h
0x180036dd2  xor     r12d, r12d
0x180036dd5  mov     rsi, rcx
0x180036dd8  add     rcx, 20h ; ' '
0x180036ddc  mov     [rbp+arg_0], r12d
0x180036de0  mov     [rbp+arg_10], r12d
0x180036de4  mov     r15, rdx
0x180036de7  mov     [rbp+arg_8], r12d
0x180036deb  call    ?clear@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::clear(void)
0x180036df0  lea     rbx, [r15+8]
0x180036df4  mov     rcx, rbx; this
0x180036df7  lea     r8d, [r12+4]; unsigned int
0x180036dfc  lea     rdx, [rbp+arg_0]; void *
0x180036e00  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180036e05  mov     edi, r12d
0x180036e08  cmp     edi, [rbp+arg_0]
0x180036e0b  jnb     loc_180036F2A
0x180036e11  mov     r8d, 4; unsigned int
0x180036e17  lea     rdx, [rbp+arg_10]; void *
0x180036e1b  mov     rcx, rbx; this
0x180036e1e  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180036e23  mov     r8d, 4; unsigned int
0x180036e29  lea     rdx, [rbp+arg_8]; void *
0x180036e2d  mov     rcx, rbx; this
0x180036e30  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180036e35  lea     r9, [rbp+arg_8]
0x180036e39  lea     r8, [rbp+arg_10]
0x180036e3d  lea     rdx, [rbp+var_40]
0x180036e41  lea     rcx, [rsi+20h]
0x180036e45  call    ??$emplace@AEAKAEAK$0A@@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBKK@utl@@@utl@@_N@1@AEAK0@Z; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::emplace<ulong &,ulong &,0>(ulong &,ulong &)
0x180036e4a  cmp     [rbp+var_40], r12
0x180036e4e  jz      short loc_180036EC2
0x180036e50  cmp     byte ptr [rbp+var_38], r12b
0x180036e54  jz      short loc_180036E5A
0x180036e56  inc     edi
0x180036e58  jmp     short loc_180036E08
0x180036e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e61  lea     rax, WPP_GLOBAL_Control
0x180036e68  mov     ebx, 0Dh
0x180036e6d  cmp     rcx, rax
0x180036e70  jz      short loc_180036E94
0x180036e72  test    byte ptr [rcx+1Ch], 1
0x180036e76  jz      short loc_180036E94
0x180036e78  cmp     byte ptr [rcx+19h], 2
0x180036e7c  jb      short loc_180036E94
0x180036e7e  mov     rcx, [rcx+10h]
0x180036e82  lea     edx, [rbx+19h]
0x180036e85  mov     r9d, ebx
0x180036e88  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180036e8f  call    WPP_SF_D
0x180036e94  xorps   xmm0, xmm0
0x180036e97  mov     [rbp+var_20], r12
0x180036e9b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180036ea2  mov     [rbp+var_18], ebx
0x180036ea5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180036ea9  mov     [rbp+var_14], 0FFFFFFFFh
0x180036eb0  movdqu  [rbp+pExceptionObject], xmm0
0x180036eb5  mov     [rbp+var_10], 368h
0x180036ebc  call    _CxxThrowException_0
0x180036ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ec9  lea     rax, WPP_GLOBAL_Control
0x180036ed0  mov     ebx, 0Eh
0x180036ed5  cmp     rcx, rax
0x180036ed8  jz      short loc_180036EFC
0x180036eda  test    byte ptr [rcx+1Ch], 1
0x180036ede  jz      short loc_180036EFC
0x180036ee0  cmp     byte ptr [rcx+19h], 2
0x180036ee4  jb      short loc_180036EFC
0x180036ee6  mov     rcx, [rcx+10h]
0x180036eea  lea     edx, [rbx+17h]
0x180036eed  mov     r9d, ebx
0x180036ef0  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180036ef7  call    WPP_SF_D
0x180036efc  xorps   xmm0, xmm0
0x180036eff  mov     [rbp+var_20], r12
0x180036f03  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180036f0a  mov     [rbp+var_18], ebx
0x180036f0d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180036f11  mov     [rbp+var_14], 0FFFFFFFFh
0x180036f18  movdqu  [rbp+pExceptionObject], xmm0
0x180036f1d  mov     [rbp+var_10], 363h
0x180036f24  call    _CxxThrowException_0
0x180036f2a  lea     rcx, [rsi+40h]
0x180036f2e  call    ?clear@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::clear(void)
0x180036f33  mov     r8d, 4; unsigned int
0x180036f39  lea     rdx, [rbp+arg_0]; void *
0x180036f3d  mov     rcx, rbx; this
0x180036f40  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180036f45  mov     edi, r12d
0x180036f48  cmp     edi, [rbp+arg_0]
0x180036f4b  jnb     loc_18003706A
0x180036f51  mov     r8d, 4; unsigned int
0x180036f57  lea     rdx, [rbp+arg_10]; void *
0x180036f5b  mov     rcx, rbx; this
0x180036f5e  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180036f63  mov     r8d, 4; unsigned int
0x180036f69  lea     rdx, [rbp+arg_8]; void *
0x180036f6d  mov     rcx, rbx; this
0x180036f70  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180036f75  lea     r9, [rbp+arg_8]
0x180036f79  lea     r8, [rbp+arg_10]
0x180036f7d  lea     rdx, [rbp+var_40]
0x180036f81  lea     rcx, [rsi+40h]
0x180036f85  call    ??$emplace@AEAKAEAK$0A@@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBKK@utl@@@utl@@_N@1@AEAK0@Z; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::emplace<ulong &,ulong &,0>(ulong &,ulong &)
0x180036f8a  cmp     [rbp+var_40], r12
0x180036f8e  jz      short loc_180037002
0x180036f90  cmp     byte ptr [rbp+var_38], r12b
0x180036f94  jz      short loc_180036F9A
0x180036f96  inc     edi
0x180036f98  jmp     short loc_180036F48
0x180036f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036fa1  lea     rax, WPP_GLOBAL_Control
0x180036fa8  mov     ebx, 0Dh
0x180036fad  cmp     rcx, rax
0x180036fb0  jz      short loc_180036FD4
0x180036fb2  test    byte ptr [rcx+1Ch], 1
0x180036fb6  jz      short loc_180036FD4
0x180036fb8  cmp     byte ptr [rcx+19h], 2
0x180036fbc  jb      short loc_180036FD4
0x180036fbe  mov     rcx, [rcx+10h]
0x180036fc2  lea     edx, [rbx+1Bh]
0x180036fc5  mov     r9d, ebx
0x180036fc8  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180036fcf  call    WPP_SF_D
0x180036fd4  xorps   xmm0, xmm0
0x180036fd7  mov     [rbp+var_20], r12
0x180036fdb  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180036fe2  mov     [rbp+var_18], ebx
0x180036fe5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180036fe9  mov     [rbp+var_14], 0FFFFFFFFh
0x180036ff0  movdqu  [rbp+pExceptionObject], xmm0
0x180036ff5  mov     [rbp+var_10], 37Bh
0x180036ffc  call    _CxxThrowException_0
0x180037002  mov     rcx, cs:WPP_GLOBAL_Control
0x180037009  lea     rax, WPP_GLOBAL_Control
0x180037010  mov     ebx, 0Eh
0x180037015  cmp     rcx, rax
0x180037018  jz      short loc_18003703C
0x18003701a  test    byte ptr [rcx+1Ch], 1
0x18003701e  jz      short loc_18003703C
0x180037020  cmp     byte ptr [rcx+19h], 2
0x180037024  jb      short loc_18003703C
0x180037026  mov     rcx, [rcx+10h]
0x18003702a  lea     edx, [rbx+19h]
0x18003702d  mov     r9d, ebx
0x180037030  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037037  call    WPP_SF_D
0x18003703c  xorps   xmm0, xmm0
0x18003703f  mov     [rbp+var_20], r12
0x180037043  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003704a  mov     [rbp+var_18], ebx
0x18003704d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180037051  mov     [rbp+var_14], 0FFFFFFFFh
0x180037058  movdqu  [rbp+pExceptionObject], xmm0
0x18003705d  mov     [rbp+var_10], 376h
0x180037064  call    _CxxThrowException_0
0x18003706a  lea     rcx, [rsi+60h]
0x18003706e  call    ?clear@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::clear(void)
0x180037073  mov     r8d, 4; unsigned int
0x180037079  lea     rdx, [rbp+arg_0]; void *
0x18003707d  mov     rcx, rbx; this
0x180037080  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x180037085  mov     edi, r12d
0x180037088  cmp     edi, [rbp+arg_0]
0x18003708b  jnb     loc_1800371AA
0x180037091  mov     r8d, 4; unsigned int
0x180037097  lea     rdx, [rbp+arg_10]; void *
0x18003709b  mov     rcx, rbx; this
0x18003709e  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x1800370a3  mov     r8d, 4; unsigned int
0x1800370a9  lea     rdx, [rbp+arg_8]; void *
0x1800370ad  mov     rcx, rbx; this
0x1800370b0  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x1800370b5  lea     r9, [rbp+arg_8]
0x1800370b9  lea     r8, [rbp+arg_10]
0x1800370bd  lea     rdx, [rbp+var_40]
0x1800370c1  lea     rcx, [rsi+60h]
0x1800370c5  call    ??$emplace@AEAKAEAK$0A@@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBKK@utl@@@utl@@_N@1@AEAK0@Z; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::emplace<ulong &,ulong &,0>(ulong &,ulong &)
0x1800370ca  cmp     [rbp+var_40], r12
0x1800370ce  jz      short loc_180037142
0x1800370d0  cmp     byte ptr [rbp+var_38], r12b
0x1800370d4  jz      short loc_1800370DA
0x1800370d6  inc     edi
0x1800370d8  jmp     short loc_180037088
0x1800370da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370e1  lea     rax, WPP_GLOBAL_Control
0x1800370e8  mov     ebx, 0Dh
0x1800370ed  cmp     rcx, rax
0x1800370f0  jz      short loc_180037114
0x1800370f2  test    byte ptr [rcx+1Ch], 1
0x1800370f6  jz      short loc_180037114
0x1800370f8  cmp     byte ptr [rcx+19h], 2
0x1800370fc  jb      short loc_180037114
0x1800370fe  mov     rcx, [rcx+10h]
0x180037102  lea     edx, [rbx+1Dh]
0x180037105  mov     r9d, ebx
0x180037108  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x18003710f  call    WPP_SF_D
0x180037114  xorps   xmm0, xmm0
0x180037117  mov     [rbp+var_20], r12
0x18003711b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037122  mov     [rbp+var_18], ebx
0x180037125  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180037129  mov     [rbp+var_14], 0FFFFFFFFh
0x180037130  movdqu  [rbp+pExceptionObject], xmm0
0x180037135  mov     [rbp+var_10], 38Eh
0x18003713c  call    _CxxThrowException_0
0x180037142  mov     rcx, cs:WPP_GLOBAL_Control
0x180037149  lea     rax, WPP_GLOBAL_Control
0x180037150  mov     ebx, 0Eh
0x180037155  cmp     rcx, rax
0x180037158  jz      short loc_18003717C
0x18003715a  test    byte ptr [rcx+1Ch], 1
0x18003715e  jz      short loc_18003717C
0x180037160  cmp     byte ptr [rcx+19h], 2
0x180037164  jb      short loc_18003717C
0x180037166  mov     rcx, [rcx+10h]
0x18003716a  lea     edx, [rbx+1Bh]
0x18003716d  mov     r9d, ebx
0x180037170  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037177  call    WPP_SF_D
0x18003717c  xorps   xmm0, xmm0
0x18003717f  mov     [rbp+var_20], r12
0x180037183  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003718a  mov     [rbp+var_18], ebx
0x18003718d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180037191  mov     [rbp+var_14], 0FFFFFFFFh
0x180037198  movdqu  [rbp+pExceptionObject], xmm0
0x18003719d  mov     [rbp+var_10], 389h
0x1800371a4  call    _CxxThrowException_0
0x1800371aa  lea     r14, [rsi+80h]
0x1800371b1  mov     rcx, r14
0x1800371b4  call    ?clear@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::clear(void)
0x1800371b9  mov     r8d, 4; unsigned int
0x1800371bf  lea     rdx, [rbp+arg_0]; void *
0x1800371c3  mov     rcx, rbx; this
0x1800371c6  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x1800371cb  mov     edi, r12d
0x1800371ce  mov     r8d, 4; unsigned int
0x1800371d4  mov     rcx, rbx; this
0x1800371d7  cmp     edi, [rbp+arg_0]
0x1800371da  jnb     loc_1800372EF
0x1800371e0  lea     rdx, [rbp+arg_10]; void *
0x1800371e4  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x1800371e9  mov     r8d, 4; unsigned int
0x1800371ef  lea     rdx, [rbp+arg_8]; void *
0x1800371f3  mov     rcx, rbx; this
0x1800371f6  call    ?Read@UserBuffer@@QEAAXPEAXK@Z; UserBuffer::Read(void *,ulong)
0x1800371fb  lea     r9, [rbp+arg_8]
0x1800371ff  mov     rcx, r14
0x180037202  lea     r8, [rbp+arg_10]
0x180037206  lea     rdx, [rbp+var_40]
0x18003720a  call    ??$emplace@AEAKAEAK$0A@@?$_Tree@KU?$pair@$$CBKK@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKK@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBKK@utl@@@utl@@_N@1@AEAK0@Z; utl::_Tree<ulong,utl::pair<ulong const,ulong>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,ulong>>,0>::emplace<ulong &,ulong &,0>(ulong &,ulong &)
0x18003720f  cmp     [rbp+var_40], r12
0x180037213  jz      short loc_180037287
0x180037215  cmp     byte ptr [rbp+var_38], r12b
0x180037219  jz      short loc_18003721F
0x18003721b  inc     edi
0x18003721d  jmp     short loc_1800371CE
0x18003721f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037226  lea     rax, WPP_GLOBAL_Control
0x18003722d  mov     ebx, 0Dh
0x180037232  cmp     rcx, rax
0x180037235  jz      short loc_180037259
0x180037237  test    byte ptr [rcx+1Ch], 1
0x18003723b  jz      short loc_180037259
0x18003723d  cmp     byte ptr [rcx+19h], 2
0x180037241  jb      short loc_180037259
0x180037243  mov     rcx, [rcx+10h]
0x180037247  lea     edx, [rbx+1Fh]
0x18003724a  mov     r9d, ebx
0x18003724d  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037254  call    WPP_SF_D
0x180037259  xorps   xmm0, xmm0
0x18003725c  mov     [rbp+var_20], r12
0x180037260  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037267  mov     [rbp+var_18], ebx
0x18003726a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003726e  mov     [rbp+var_14], 0FFFFFFFFh
0x180037275  movdqu  [rbp+pExceptionObject], xmm0
0x18003727a  mov     [rbp+var_10], 3A1h
0x180037281  call    _CxxThrowException_0
0x180037287  mov     rcx, cs:WPP_GLOBAL_Control
0x18003728e  lea     rax, WPP_GLOBAL_Control
0x180037295  mov     ebx, 0Eh
0x18003729a  cmp     rcx, rax
0x18003729d  jz      short loc_1800372C1
0x18003729f  test    byte ptr [rcx+1Ch], 1
0x1800372a3  jz      short loc_1800372C1
0x1800372a5  cmp     byte ptr [rcx+19h], 2
0x1800372a9  jb      short loc_1800372C1
0x1800372ab  mov     rcx, [rcx+10h]
  ... truncated ...
```
