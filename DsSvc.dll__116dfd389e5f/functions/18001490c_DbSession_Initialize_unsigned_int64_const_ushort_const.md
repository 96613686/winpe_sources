# DbSession::Initialize(unsigned __int64 const &,ushort const *)

- ea: `0x18001490c`
- end: `0x180014a12`
- name: `?Initialize@DbSession@@AEAAJAEB_KPEBG@Z`
- size: `262`
- prototype: `__int64 __fastcall(DbSession *__hidden this, const unsigned __int64 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180010220`

## callees

- `0x180006e2c`
- `0x180006f78`
- `0x18000bf80`
- `0x1800114e4`
- `0x18001490c`

## import_xrefs

- `ESENT!JetBeginSessionW` at `0x180014970`
- `ESENT!JetBeginSessionW` at `0x180014970`
- `ESENT!JetOpenDatabaseW` at `0x1800149c2`
- `ESENT!JetOpenDatabaseW` at `0x1800149c2`

## pseudocode

```c
__int64 __fastcall DbSession::Initialize(DbSession *this, const unsigned __int64 *a2, const unsigned __int16 *a3)
{
  int v4; // ebx
  __int64 v5; // rcx
  JET_ERR v6; // ebp
  int *v7; // rax
  __int64 v8; // rcx
  JET_ERR v9; // edi
  int *v10; // rax
  JET_GRBIT grbita; // [rsp+20h] [rbp-48h]
  __int64 grbit; // [rsp+20h] [rbp-48h]

  if ( *a2 != -1 && a3 && *a3 )
  {
    *(_QWORD *)this = *a2;
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            (char *)this + 8,
                            a3) )
    {
      v4 = 0;
      v6 = JetBeginSessionW(*(_QWORD *)this, (JET_SESID *)this + 5, &szUserName, &szUserName);
      if ( v6 >= 0
        || (v7 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v5),
            grbita = v6,
            DSLogger::LogError((DSLogger *)v7, L"DbSession::Initialize", 141, L"JET_ERR : %d", grbita),
            v4 = JetToHResult(v6),
            v4 >= 0) )
      {
        v9 = JetOpenDatabaseW(*((_QWORD *)this + 5), *((JET_PCWSTR *)this + 1), 0, (JET_DBID *)this + 12, 0);
        if ( v9 < 0 )
        {
          v10 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v8);
          LODWORD(grbit) = v9;
          DSLogger::LogError((DSLogger *)v10, L"DbSession::Initialize", 142, L"JET_ERR : %d", grbit);
          return (unsigned int)JetToHResult(v9);
        }
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001490c  push    rbx
0x18001490e  push    rbp
0x18001490f  push    rsi
0x180014910  push    rdi
0x180014911  push    r14
0x180014913  push    r15
0x180014915  sub     rsp, 38h
0x180014919  mov     rax, [rdx]
0x18001491c  mov     rdi, rcx
0x18001491f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014923  jz      loc_1800149FE
0x180014929  xor     r15d, r15d
0x18001492c  test    r8, r8
0x18001492f  jz      loc_1800149FE
0x180014935  cmp     [r8], r15w
0x180014939  jz      loc_1800149FE
0x18001493f  mov     [rcx], rax
0x180014942  mov     rdx, r8
0x180014945  add     rcx, 8
0x180014949  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18001494e  test    al, al
0x180014950  jnz     short loc_18001495C
0x180014952  mov     ebx, 8007000Eh
0x180014957  jmp     loc_180014A03
0x18001495c  mov     rcx, [rdi]; instance
0x18001495f  lea     r8, szUserName; szUserName
0x180014966  mov     r9, r8; szPassword
0x180014969  lea     rdx, [rdi+28h]; psesid
0x18001496d  mov     ebx, r15d
0x180014970  call    cs:__imp_JetBeginSessionW
0x180014976  mov     ebp, eax
0x180014978  test    eax, eax
0x18001497a  jns     short loc_1800149AE
0x18001497c  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180014981  lea     r9, aJetErrD; "JET_ERR : %d"
0x180014988  mov     dword ptr [rsp+68h+grbit], ebp
0x18001498c  mov     r8d, 8Dh; unsigned int
0x180014992  lea     rdx, aDbsessionIniti; "DbSession::Initialize"
0x180014999  mov     rcx, rax; this
0x18001499c  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800149a1  mov     ecx, ebp; int
0x1800149a3  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x1800149a8  mov     ebx, eax
0x1800149aa  test    eax, eax
0x1800149ac  js      short loc_180014A03
0x1800149ae  mov     rdx, [rdi+8]; szFilename
0x1800149b2  lea     r9, [rdi+30h]; pdbid
0x1800149b6  mov     rcx, [rdi+28h]; sesid
0x1800149ba  xor     r8d, r8d; szConnect
0x1800149bd  mov     dword ptr [rsp+68h+grbit], r15d; grbit
0x1800149c2  call    cs:__imp_JetOpenDatabaseW
0x1800149c8  mov     edi, eax
0x1800149ca  test    eax, eax
0x1800149cc  jns     short loc_180014A03
0x1800149ce  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800149d3  lea     r9, aJetErrD; "JET_ERR : %d"
0x1800149da  mov     dword ptr [rsp+68h+grbit], edi
0x1800149de  mov     r8d, 8Eh; unsigned int
0x1800149e4  lea     rdx, aDbsessionIniti; "DbSession::Initialize"
0x1800149eb  mov     rcx, rax; this
0x1800149ee  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800149f3  mov     ecx, edi; int
0x1800149f5  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x1800149fa  mov     ebx, eax
0x1800149fc  jmp     short loc_180014A03
0x1800149fe  mov     ebx, 80070057h
0x180014a03  mov     eax, ebx
0x180014a05  add     rsp, 38h
0x180014a09  pop     r15
0x180014a0b  pop     r14
0x180014a0d  pop     rdi
0x180014a0e  pop     rsi
0x180014a0f  pop     rbp
0x180014a10  pop     rbx
0x180014a11  retn
```
