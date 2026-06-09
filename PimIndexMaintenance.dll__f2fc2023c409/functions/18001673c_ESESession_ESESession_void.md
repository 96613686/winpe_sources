# ESESession::~ESESession(void)

- ea: `0x18001673c`
- end: `0x1800167f3`
- name: `??1ESESession@@UEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ESESession *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800168b0`

## callees

- `0x180002858`
- `0x18001673c`
- `0x180016828`
- `0x1800195cc`
- `0x18001963c`
- `0x18001968c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800167c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800167c8`
- `ESENT!JetDetachDatabaseA` at `0x18001679d`
- `ESENT!JetDetachDatabaseA` at `0x18001679d`

## pseudocode

```c
void __fastcall ESESession::~ESESession(ESESession *this)
{
  char *v2; // r14
  __int64 i; // rbx

  *(_QWORD *)this = &ESESession::`vftable';
  v2 = (char *)this + 104;
  for ( i = 0; i != 5; ++i )
    auto_JET_TABLEID::close((auto_JET_TABLEID *)&v2[48 * i]);
  *((_QWORD *)this + 43) = 0;
  auto_JET_TABLEID::close((ESESession *)((char *)this + 32));
  auto_JET_DBID::close((ESESession *)((char *)this + 16));
  if ( *((_DWORD *)this + 90) )
    JetDetachDatabaseA(*((_QWORD *)this + 7), 0);
  auto_JET_SESID::close((ESESession *)((char *)this + 48));
  `vector destructor iterator'(v2, 0x30u, 5u, (void (*)(void *))ESESession::TableInfo::~TableInfo);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  auto_JET_SESID::close((ESESession *)((char *)this + 48));
  auto_JET_TABLEID::~auto_JET_TABLEID((ESESession *)((char *)this + 32));
  auto_JET_DBID::close((ESESession *)((char *)this + 16));
}

```

## disassembly

```asm
0x18001673c  push    rbx
0x18001673e  push    rbp
0x18001673f  push    rsi
0x180016740  push    rdi
0x180016741  push    r14
0x180016743  sub     rsp, 20h
0x180016747  lea     rax, ??_7ESESession@@6B@; const ESESession::`vftable'
0x18001674e  mov     rdi, rcx
0x180016751  mov     [rcx], rax
0x180016754  lea     r14, [rcx+68h]
0x180016758  xor     ebx, ebx
0x18001675a  lea     rcx, [rbx+rbx*2]
0x18001675e  shl     rcx, 4
0x180016762  add     rcx, r14; this
0x180016765  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x18001676a  inc     rbx
0x18001676d  cmp     rbx, 5
0x180016771  jnz     short loc_18001675A
0x180016773  xor     eax, eax
0x180016775  lea     rcx, [rdi+20h]; this
0x180016779  mov     [rdi+158h], rax
0x180016780  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x180016785  lea     rcx, [rdi+10h]; this
0x180016789  call    ?close@auto_JET_DBID@@QEAAXXZ; auto_JET_DBID::close(void)
0x18001678e  cmp     dword ptr [rdi+168h], 0
0x180016795  jz      short loc_1800167A3
0x180016797  mov     rcx, [rdi+38h]; sesid
0x18001679b  xor     edx, edx; szFilename
0x18001679d  call    cs:__imp_JetDetachDatabaseA
0x1800167a3  lea     rcx, [rdi+30h]; this
0x1800167a7  call    ?close@auto_JET_SESID@@QEAAXXZ; auto_JET_SESID::close(void)
0x1800167ac  mov     edx, 30h ; '0'; unsigned __int64
0x1800167b1  lea     r9, ??1TableInfo@ESESession@@QEAA@XZ; void (*)(void *)
0x1800167b8  mov     rcx, r14; void *
0x1800167bb  lea     r8d, [rdx-2Bh]; unsigned __int64
0x1800167bf  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800167c4  lea     rcx, [rdi+40h]; lpCriticalSection
0x1800167c8  call    cs:__imp_DeleteCriticalSection
0x1800167ce  lea     rcx, [rdi+30h]; this
0x1800167d2  call    ?close@auto_JET_SESID@@QEAAXXZ; auto_JET_SESID::close(void)
0x1800167d7  lea     rcx, [rdi+20h]; this
0x1800167db  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x1800167e0  lea     rcx, [rdi+10h]; this
0x1800167e4  add     rsp, 20h
0x1800167e8  pop     r14
0x1800167ea  pop     rdi
0x1800167eb  pop     rsi
0x1800167ec  pop     rbp
0x1800167ed  pop     rbx
0x1800167ee  jmp     ?close@auto_JET_DBID@@QEAAXXZ; auto_JET_DBID::close(void)
```
