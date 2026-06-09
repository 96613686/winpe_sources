# CSegmentHashListGen::OnSignaled(bool *,bool *)

- ea: `0x1800a14d0`
- end: `0x1800a16fd`
- name: `?OnSignaled@CSegmentHashListGen@@EEAAXPEA_N0@Z`
- size: `557`
- prototype: `void __fastcall(CSegmentHashListGen *__hidden this, bool *, bool *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800082d0`
- `0x18000e58c`
- `0x180018de0`
- `0x180018f48`
- `0x18001911c`
- `0x180020058`
- `0x1800a1134`
- `0x1800a14d0`
- `0x1800a1704`
- `0x18013937c`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a1561`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a16ea`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a1561`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a16ea`
- `KERNEL32!GetCurrentThread` at `0x1800a1553`
- `KERNEL32!GetCurrentThread` at `0x1800a16dc`
- `KERNEL32!GetCurrentThread` at `0x1800a1553`
- `KERNEL32!GetCurrentThread` at `0x1800a16dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CSegmentHashListGen::OnSignaled(CSegmentHashListGen *this, bool *a2, bool *a3)
{
  HANDLE CurrentThread; // rax
  __int64 (__fastcall ***v7)(_QWORD, __int64); // rbx
  __int64 v8; // r15
  HANDLE v9; // rax
  CSegmentGenWaiter *v10; // rbx
  int v11; // eax
  unsigned int v12; // [rsp+20h] [rbp-78h]
  Exception *v13; // [rsp+38h] [rbp-60h] BYREF
  _QWORD v14[2]; // [rsp+40h] [rbp-58h] BYREF
  void **v15; // [rsp+50h] [rbp-48h] BYREF
  int v16; // [rsp+58h] [rbp-40h]
  __int64 v17; // [rsp+60h] [rbp-38h]
  char v18; // [rsp+68h] [rbp-30h]
  int v20; // [rsp+A8h] [rbp+10h] BYREF
  unsigned int v21; // [rsp+B0h] [rbp+18h] BYREF
  __int64 (__fastcall ***v22)(_QWORD, __int64); // [rsp+B8h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, WPP_5dbf95b72c613eaf3e938ed4673986b6_Traceguids);
  }
  *a2 = 1;
  *a3 = 0;
  if ( !*((_BYTE *)this + 156) && *((_DWORD *)this + 75) )
  {
    if ( *((_BYTE *)this + 232) )
    {
      CurrentThread = GetCurrentThread();
      SetThreadPriority(CurrentThread, 0x10000);
    }
    try
    {
      Event::Event((Event *)v14, 0, 0);
      v21 = 0;
      CSegmentHashListGen::WriteHashesForSegment(
        (CSegmentHashListGen *)((char *)this - 32),
        *((_QWORD *)this + 17),
        *((_DWORD *)this + 75),
        *((unsigned __int8 **)this + 18),
        (int *)&v21,
        (void *)v14[1]);
      v7 = (__int64 (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 23) + 40LL))(
                                                        *((_QWORD *)this + 23),
                                                        0,
                                                        0);
      v22 = v7;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64), _QWORD, _QWORD))(*v7)[1])(
        v7,
        *((unsigned int *)this + 75),
        *((_QWORD *)this + 18));
      v20 = 0;
      v8 = (*v7)[2](v7, (__int64)&v20);
      v16 = 0;
      v17 = 0;
      v18 = 1;
      v15 = &TnoHash::`vftable';
      LODWORD(v7) = v20;
      TnoBaseHash::ReleaseHash((TnoBaseHash *)&v15);
      v17 = v8;
      v16 = (int)v7;
      v18 = 0;
      ObjectHandle::Wait((ObjectHandle *)v14, 0xFFFFFFFF);
      if ( (v21 & 0x80000000) != 0 )
        ApplicationError::Throw(L"CSegmentHashListGen::OnSignaled - writing hashes", v21);
      CSegmentHashListGen::CreateCacheSegment(
        (CSegmentHashListGen *)((char *)this - 32),
        *((_QWORD *)this + 17),
        *((_DWORD *)this + 74),
        (const struct TnoHash *)&v15,
        v12);
      v15 = &TnoHash::`vftable';
      TnoBaseHash::ReleaseHash((TnoBaseHash *)&v15);
      std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(&v22);
      v14[0] = &ObjectHandle::`vftable';
      ObjectHandle::CloseNoThrow((ObjectHandle *)v14);
    }
    catch ( Exception *v13 )
    {
      v10 = (CSegmentGenWaiter *)*((_QWORD *)this + 22);
      v11 = (*(__int64 (__fastcall **)(Exception *))(*(_QWORD *)v13 + 8LL))(v13);
      CSegmentGenWaiter::ReportFailure(v10, v11);
    }
    catch ( std::bad_alloc )
    {
      CSegmentGenWaiter::ReportFailure(*((CSegmentGenWaiter **)this + 22), -2147024882);
    }
    catch ( ... )
    {
      CSegmentGenWaiter::ReportFailure(*((CSegmentGenWaiter **)this + 22), -2147024122);
    }
    if ( *((_BYTE *)this + 232) )
    {
      v9 = GetCurrentThread();
      SetThreadPriority(v9, 0x20000);
    }
  }
}

```

## disassembly

```asm
0x1800a14d0  mov     [rsp+arg_0], rcx
0x1800a14d5  push    rbx
0x1800a14d6  push    rsi
0x1800a14d7  push    rdi
0x1800a14d8  push    r14
0x1800a14da  push    r15
0x1800a14dc  sub     rsp, 70h
0x1800a14e0  mov     rbx, r8
0x1800a14e3  mov     rdi, rdx
0x1800a14e6  mov     rsi, rcx
0x1800a14e9  lea     rax, WPP_GLOBAL_Control
0x1800a14f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a14f7  cmp     rcx, rax
0x1800a14fa  jz      short loc_1800A1521
0x1800a14fc  test    byte ptr [rcx+6Ch], 1
0x1800a1500  jz      short loc_1800A1521
0x1800a1502  cmp     byte ptr [rcx+69h], 4
0x1800a1506  jb      short loc_1800A1521
0x1800a1508  lea     r9, [rsi-20h]
0x1800a150c  mov     edx, 0Fh
0x1800a1511  lea     r8, WPP_5dbf95b72c613eaf3e938ed4673986b6_Traceguids
0x1800a1518  mov     rcx, [rcx+60h]
0x1800a151c  call    WPP_SF_q
0x1800a1521  mov     byte ptr [rdi], 1
0x1800a1524  xor     edi, edi
0x1800a1526  mov     [rbx], dil
0x1800a1529  cmp     [rsi+9Ch], dil
0x1800a1530  jnz     loc_1800A16F1
0x1800a1536  cmp     [rsi+12Ch], edi
0x1800a153c  jz      loc_1800A16F1
0x1800a1542  lea     rax, [rsi+0E8h]
0x1800a1549  mov     [rsp+98h+var_68], rax
0x1800a154e  cmp     [rax], dil
0x1800a1551  jz      short loc_1800A1568
0x1800a1553  call    cs:__imp_GetCurrentThread
0x1800a1559  mov     rcx, rax; hThread
0x1800a155c  mov     edx, 10000h; nPriority
0x1800a1561  call    cs:__imp_SetThreadPriority
0x1800a1567  nop
0x1800a1568  xor     r8d, r8d; bool
0x1800a156b  xor     edx, edx; bool
0x1800a156d  lea     rcx, [rsp+98h+var_58]; this
0x1800a1572  call    ??0Event@@QEAA@_N0@Z; Event::Event(bool,bool)
0x1800a1577  nop
0x1800a1578  mov     [rsp+98h+arg_10], edi
0x1800a157f  mov     rax, [rsp+98h+var_50]
0x1800a1584  mov     [rsp+98h+var_70], rax; void *
0x1800a1589  lea     rax, [rsp+98h+arg_10]
0x1800a1591  mov     [rsp+98h+var_78], rax; unsigned int
0x1800a1596  mov     r9, [rsi+90h]; unsigned __int8 *
0x1800a159d  mov     r8d, [rsi+12Ch]; unsigned int
0x1800a15a4  mov     rdx, [rsi+88h]; unsigned __int64
0x1800a15ab  lea     rcx, [rsi-20h]; this
0x1800a15af  call    ?WriteHashesForSegment@CSegmentHashListGen@@AEAAX_KKPEAEPEAJPEAX@Z; CSegmentHashListGen::WriteHashesForSegment(unsigned __int64,ulong,uchar *,long *,void *)
0x1800a15b4  mov     rcx, [rsi+0B8h]
0x1800a15bb  mov     rax, [rcx]
0x1800a15be  xor     r8d, r8d
0x1800a15c1  xor     edx, edx
0x1800a15c3  mov     rax, [rax+28h]
0x1800a15c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a15cc  mov     rbx, rax
0x1800a15cf  mov     [rsp+98h+arg_18], rax
0x1800a15d7  mov     rcx, [rax]
0x1800a15da  mov     rax, [rcx+8]
0x1800a15de  mov     r8, [rsi+90h]
0x1800a15e5  mov     edx, [rsi+12Ch]
0x1800a15eb  mov     rcx, rbx
0x1800a15ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a15f3  mov     [rsp+98h+arg_8], edi
0x1800a15fa  mov     rax, [rbx]
0x1800a15fd  lea     rdx, [rsp+98h+arg_8]
0x1800a1605  mov     rcx, rbx
0x1800a1608  mov     rax, [rax+10h]
0x1800a160c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1611  mov     r15, rax
0x1800a1614  mov     [rsp+98h+var_40], edi
0x1800a1618  mov     [rsp+98h+var_38], rdi
0x1800a161d  mov     [rsp+98h+var_30], 1
0x1800a1622  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x1800a1629  mov     [rsp+98h+var_48], rax
0x1800a162e  mov     ebx, [rsp+98h+arg_8]
0x1800a1635  lea     rcx, [rsp+98h+var_48]; this
0x1800a163a  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x1800a163f  mov     [rsp+98h+var_38], r15
0x1800a1644  mov     [rsp+98h+var_40], ebx
0x1800a1648  mov     [rsp+98h+var_30], dil
0x1800a164d  or      edx, 0FFFFFFFFh; unsigned int
0x1800a1650  lea     rcx, [rsp+98h+var_58]; this
0x1800a1655  call    ?Wait@ObjectHandle@@QEAA_NI@Z; ObjectHandle::Wait(uint)
0x1800a165a  mov     edx, [rsp+98h+arg_10]; int
0x1800a1661  test    edx, edx
0x1800a1663  jns     short loc_1800A1671
0x1800a1665  lea     rcx, aCsegmenthashli_1; "CSegmentHashListGen::OnSignaled - writi"...
0x1800a166c  call    ?Throw@ApplicationError@@SAXPEBGJ@Z; ApplicationError::Throw(ushort const *,long)
0x1800a1671  lea     r9, [rsp+98h+var_48]; struct TnoHash *
0x1800a1676  mov     r8d, [rsi+128h]; unsigned int
0x1800a167d  mov     rdx, [rsi+88h]; unsigned __int64
0x1800a1684  lea     rcx, [rsi-20h]; this
0x1800a1688  call    ?CreateCacheSegment@CSegmentHashListGen@@AEAAX_KKAEBVTnoHash@@K@Z; CSegmentHashListGen::CreateCacheSegment(unsigned __int64,ulong,TnoHash const &,ulong)
0x1800a168d  nop
0x1800a168e  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x1800a1695  mov     [rsp+98h+var_48], rax
0x1800a169a  lea     rcx, [rsp+98h+var_48]; this
0x1800a169f  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x1800a16a4  nop
0x1800a16a5  lea     rcx, [rsp+98h+arg_18]
0x1800a16ad  call    ??1?$auto_ptr@VCRepubCacheMigrateWorkItem@@@std@@QEAA@XZ; std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(void)
0x1800a16b2  nop
0x1800a16b3  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x1800a16ba  mov     [rsp+98h+var_58], rax
0x1800a16bf  lea     rcx, [rsp+98h+var_58]; this
0x1800a16c4  call    ?CloseNoThrow@ObjectHandle@@IEAAKXZ; ObjectHandle::CloseNoThrow(void)
0x1800a16c9  nop
0x1800a16ca  jmp     short loc_1800A16D2
0x1800a16cc  jmp     short loc_1800A16D0
0x1800a16ce  jmp     short $+2
0x1800a16d0  xor     edi, edi
0x1800a16d2  mov     rax, [rsp+98h+var_68]
0x1800a16d7  cmp     [rax], dil
0x1800a16da  jz      short loc_1800A16F1
0x1800a16dc  call    cs:__imp_GetCurrentThread
0x1800a16e2  mov     rcx, rax; hThread
0x1800a16e5  mov     edx, 20000h; nPriority
0x1800a16ea  call    cs:__imp_SetThreadPriority
0x1800a16f0  nop
0x1800a16f1  add     rsp, 70h
0x1800a16f5  pop     r15
0x1800a16f7  pop     r14
0x1800a16f9  pop     rdi
0x1800a16fa  pop     rsi
0x1800a16fb  pop     rbx
0x1800a16fc  retn
```
