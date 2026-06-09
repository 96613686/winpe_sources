# Database::Create(DbSession * *)

- ea: `0x180010220`
- end: `0x1800102d1`
- name: `?Create@Database@@EEAAJPEAPEAVDbSession@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(Database *__hidden this, struct DbSession **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180002ac8`
- `0x180006f78`
- `0x18000bf80`
- `0x180010024`
- `0x180010220`
- `0x18001490c`

## string_xrefs

- `0x180010294`: `Database::CreateSession for db=%s failed! hr=0x%x.`
- `0x18001029f`: `Database::Create`

## pseudocode

```c
__int64 __fastcall Database::Create(Database *this, struct DbSession **a2)
{
  struct DbSession *v4; // rax
  __int64 v5; // rcx
  struct DbSession *v6; // rbx
  int v7; // edi
  int *v8; // rax

  v4 = (struct DbSession *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v4;
  if ( v4 )
  {
    *((_QWORD *)v4 + 5) = -1;
    *((_QWORD *)v4 + 1) = (char *)v4 + 24;
    *((_QWORD *)v4 + 2) = (char *)v4 + 24;
    *((_DWORD *)v4 + 12) = -1;
    *((_WORD *)v4 + 12) = 0;
    v7 = DbSession::Initialize(v4, (const unsigned __int64 *)this + 6, *((const unsigned __int16 **)this + 9));
    if ( v7 >= 0 )
    {
      *a2 = v6;
      return (unsigned int)v7;
    }
  }
  else
  {
    v6 = 0;
    v7 = -2147467259;
  }
  v8 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v5);
  DSLogger::LogError(
    (DSLogger *)v8,
    L"Database::Create",
    398,
    L"Database::CreateSession for db=%s failed! hr=0x%x.",
    *((_QWORD *)this + 9),
    v7);
  if ( v6 )
    tlx::_delete<DbSession>(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180010220  push    rbx
0x180010222  push    rbp
0x180010223  push    rsi
0x180010224  push    rdi
0x180010225  sub     rsp, 38h
0x180010229  mov     rsi, rdx
0x18001022c  mov     rbp, rcx
0x18001022f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010236  mov     ecx, 38h ; '8'; unsigned __int64
0x18001023b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010240  mov     rbx, rax
0x180010243  test    rax, rax
0x180010246  jz      short loc_180010284
0x180010248  lea     r8, [rax+18h]
0x18001024c  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180010254  mov     [rax+8], r8
0x180010258  lea     rdx, [rbp+30h]; unsigned __int64 *
0x18001025c  mov     [rax+10h], r8
0x180010260  mov     rcx, rbx; this
0x180010263  xor     eax, eax
0x180010265  mov     dword ptr [rbx+30h], 0FFFFFFFFh
0x18001026c  mov     [r8], ax
0x180010270  mov     r8, [rbp+48h]; unsigned __int16 *
0x180010274  call    ?Initialize@DbSession@@AEAAJAEB_KPEBG@Z; DbSession::Initialize(unsigned __int64 const &,ushort const *)
0x180010279  mov     edi, eax
0x18001027b  test    eax, eax
0x18001027d  js      short loc_18001028B
0x18001027f  mov     [rsi], rbx
0x180010282  jmp     short loc_1800102C6
0x180010284  xor     ebx, ebx
0x180010286  mov     edi, 80004005h
0x18001028b  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010290  mov     rcx, [rbp+48h]
0x180010294  lea     r9, aDatabaseCreate_2; "Database::CreateSession for db=%s faile"...
0x18001029b  mov     [rsp+58h+var_30], edi
0x18001029f  lea     rdx, aDatabaseCreate_0; "Database::Create"
0x1800102a6  mov     [rsp+58h+var_38], rcx
0x1800102ab  mov     r8d, 18Eh; unsigned int
0x1800102b1  mov     rcx, rax; this
0x1800102b4  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800102b9  test    rbx, rbx
0x1800102bc  jz      short loc_1800102C6
0x1800102be  mov     rcx, rbx; P
0x1800102c1  call    ??$_delete@VDbSession@@@tlx@@YAXPEAVDbSession@@@Z; tlx::_delete<DbSession>(DbSession *)
0x1800102c6  mov     eax, edi
0x1800102c8  add     rsp, 38h
0x1800102cc  pop     rdi
0x1800102cd  pop     rsi
0x1800102ce  pop     rbp
0x1800102cf  pop     rbx
0x1800102d0  retn
```
