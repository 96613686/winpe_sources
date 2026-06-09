# DbTableAccess<SharingTargetTableAdapter>::Initialize(tlx::smart_ptr<DbSession,&tlx::_delete<DbSession>(DbSession *),utl::allocator<int>> const &)

- ea: `0x1800177b0`
- end: `0x1800178b3`
- name: `?Initialize@?$DbTableAccess@VSharingTargetTableAdapter@@@@UEAAJAEBV?$smart_ptr@VDbSession@@$1??$_delete@VDbSession@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002ac8`
- `0x18000f120`
- `0x180014a18`
- `0x180015a9c`
- `0x1800177b0`
- `0x180017ea0`

## pseudocode

```c
__int64 __fastcall DbTableAccess<SharingTargetTableAdapter>::Initialize(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 v4; // rcx
  utl::_RefCountBase *v6; // rcx
  int TableDefinition; // edx
  _QWORD *v8; // rax
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v2 = a2[1];
  v4 = *a2;
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  *(_QWORD *)(a1 + 24) = v4;
  v6 = *(utl::_RefCountBase **)(a1 + 32);
  *(_QWORD *)(a1 + 32) = v2;
  if ( v6 )
    utl::_RefCountBase::_DecStrong(v6);
  if ( !*(_QWORD *)(a1 + 24) )
    return (unsigned int)-2147024882;
  v8 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v8 )
  {
    *v8 = 0;
    v8[1] = 0;
    *((_DWORD *)v8 + 4) = 0;
    v8[3] = 0;
    *((_DWORD *)v8 + 8) = 0;
    v8[7] = 0;
    v8[8] = 0;
    v8[10] = 0;
  }
  if ( (unsigned __int8)tlx::smart_xxx<DbTable *,void (*)(DbTable *),&void tlx::_delete<DbTable>(DbTable *),0,utl::allocator<int>>::reset(
                          a1 + 8,
                          v8) )
  {
    v10 = 0;
    TableDefinition = DbTableDescription<SharingTargetTableAdapter>::GetTableDefinition(&v10);
    if ( TableDefinition >= 0 )
    {
      TableDefinition = DbTable::Initialize(
                          *(DbTable **)(a1 + 8),
                          v10,
                          a2,
                          _InterlockedCompareExchange(
                            &DbTableAccess<SharingTargetTableAdapter>::s_fIndexCorrupted,
                            0,
                            0));
      if ( TableDefinition >= 0 )
        _InterlockedCompareExchange(&DbTableAccess<SharingTargetTableAdapter>::s_fIndexCorrupted, 0, 1);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)TableDefinition;
}

```

## disassembly

```asm
0x1800177b0  mov     [rsp+arg_8], rbx
0x1800177b5  push    rdi
0x1800177b6  sub     rsp, 20h
0x1800177ba  mov     rax, [rdx+8]
0x1800177be  mov     rbx, rcx
0x1800177c1  mov     rcx, [rdx]
0x1800177c4  mov     rdi, rdx
0x1800177c7  test    rax, rax
0x1800177ca  jz      short loc_1800177D0
0x1800177cc  lock inc dword ptr [rax+8]
0x1800177d0  mov     [rbx+18h], rcx
0x1800177d4  mov     rcx, [rbx+20h]; this
0x1800177d8  mov     [rbx+20h], rax
0x1800177dc  test    rcx, rcx
0x1800177df  jz      short loc_1800177E6
0x1800177e1  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800177e6  cmp     qword ptr [rbx+18h], 0
0x1800177eb  jnz     short loc_1800177F7
0x1800177ed  mov     edx, 8007000Eh
0x1800177f2  jmp     loc_1800178A6
0x1800177f7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800177fe  mov     ecx, 58h ; 'X'; unsigned __int64
0x180017803  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017808  test    rax, rax
0x18001780b  jz      short loc_18001784A
0x18001780d  mov     qword ptr [rax], 0
0x180017814  mov     qword ptr [rax+8], 0
0x18001781c  mov     dword ptr [rax+10h], 0
0x180017823  mov     qword ptr [rax+18h], 0
0x18001782b  mov     dword ptr [rax+20h], 0
0x180017832  mov     qword ptr [rax+38h], 0
0x18001783a  mov     qword ptr [rax+40h], 0
0x180017842  mov     qword ptr [rax+50h], 0
0x18001784a  mov     rdx, rax
0x18001784d  lea     rcx, [rbx+8]
0x180017851  call    ?reset@?$smart_xxx@PEAVDbTable@@P6AXPEAV1@@Z$1??$_delete@VDbTable@@@tlx@@YAX0@Z$0A@V?$allocator@H@utl@@@tlx@@QEAA_NPEAVDbTable@@@Z; tlx::smart_xxx<DbTable *,void (*)(DbTable *),&tlx::_delete<DbTable>(DbTable *),0,utl::allocator<int>>::reset(DbTable *)
0x180017856  test    al, al
0x180017858  jz      short loc_1800177ED
0x18001785a  lea     rcx, [rsp+28h+arg_0]
0x18001785f  mov     [rsp+28h+arg_0], 0
0x180017868  call    ?GetTableDefinition@?$DbTableDescription@VSharingTargetTableAdapter@@@@SAJPEAPEAUtagJET_TABLECREATE_W@@@Z; DbTableDescription<SharingTargetTableAdapter>::GetTableDefinition(tagJET_TABLECREATE_W * *)
0x18001786d  mov     edx, eax
0x18001786f  test    eax, eax
0x180017871  js      short loc_1800178A6
0x180017873  xor     edx, edx
0x180017875  xor     eax, eax
0x180017877  lock cmpxchg cs:?s_fIndexCorrupted@?$DbTableAccess@VSharingTargetTableAdapter@@@@0JA, edx; long DbTableAccess<SharingTargetTableAdapter>::s_fIndexCorrupted
0x18001787f  mov     rdx, [rsp+28h+arg_0]
0x180017884  mov     r9d, eax
0x180017887  mov     rcx, [rbx+8]; this
0x18001788b  mov     r8, rdi
0x18001788e  call    ?Initialize@DbTable@@QEAAJPEAUtagJET_TABLECREATE_W@@AEBV?$smart_ptr@VDbSession@@$1??$_delete@VDbSession@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@H@Z; DbTable::Initialize(tagJET_TABLECREATE_W *,tlx::smart_ptr<DbSession,&tlx::_delete<DbSession>(DbSession *),utl::allocator<int>> const &,int)
0x180017893  mov     edx, eax
0x180017895  test    eax, eax
0x180017897  js      short loc_1800178A6
0x180017899  xor     ecx, ecx
0x18001789b  lea     eax, [rcx+1]
0x18001789e  lock cmpxchg cs:?s_fIndexCorrupted@?$DbTableAccess@VSharingTargetTableAdapter@@@@0JA, ecx; long DbTableAccess<SharingTargetTableAdapter>::s_fIndexCorrupted
0x1800178a6  mov     rbx, [rsp+28h+arg_8]
0x1800178ab  mov     eax, edx
0x1800178ad  add     rsp, 20h
0x1800178b1  pop     rdi
0x1800178b2  retn
```
