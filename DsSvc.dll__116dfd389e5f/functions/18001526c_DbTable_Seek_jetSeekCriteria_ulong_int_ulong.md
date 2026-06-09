# DbTable::Seek(_jetSeekCriteria *,ulong,int,ulong)

- ea: `0x18001526c`
- end: `0x1800153ed`
- name: `?Seek@DbTable@@AEAAJPEAU_jetSeekCriteria@@KHK@Z`
- size: `385`
- prototype: `__int64 __fastcall(DbTable *__hidden this, struct _jetSeekCriteria *, unsigned int, int, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180014770`
- `0x180014dd0`
- `0x180015468`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x1800114e4`
- `0x18001526c`

## import_xrefs

- `ESENT!JetMove` at `0x18001538f`
- `ESENT!JetMove` at `0x18001538f`
- `ESENT!JetSeek` at `0x180015376`
- `ESENT!JetSeek` at `0x180015376`
- `ESENT!JetMakeKey` at `0x180015325`
- `ESENT!JetMakeKey` at `0x180015325`
- `ESENT!JetSetCurrentIndexW` at `0x1800152a9`
- `ESENT!JetSetCurrentIndexW` at `0x1800152a9`

## pseudocode

```c
__int64 __fastcall DbTable::Seek(DbTable *this, const void **a2, int a3, int a4, unsigned int a5)
{
  int v8; // ebx
  __int64 v9; // rcx
  JET_ERR v10; // esi
  int *v11; // rax
  int i; // esi
  JET_TABLEID v13; // rdx
  JET_SESID v14; // rcx
  __int64 v15; // rcx
  JET_ERR Key; // r15d
  int *v17; // rax
  JET_ERR v18; // eax
  __int64 v19; // rcx
  int v20; // edi
  int *v21; // rax
  __int64 grbit; // [rsp+20h] [rbp-48h]

  if ( a4 >= *((_DWORD *)this + 8) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    v8 = 0;
    v10 = JetSetCurrentIndexW(
            *((_QWORD *)this + 5),
            *((_QWORD *)this + 9),
            *(JET_PCWSTR *)(*((_QWORD *)this + 3) + 80LL * a4 + 8));
    if ( v10 >= 0
      || (v11 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v9),
          DSLogger::LogError((DSLogger *)v11, L"DbTable::Seek", 812, L"JET_ERR : %d", v10),
          v8 = JetToHResult(v10),
          v8 >= 0) )
    {
      if ( a2 && a3 )
      {
        for ( i = 0; ; ++i )
        {
          v13 = *((_QWORD *)this + 9);
          v14 = *((_QWORD *)this + 5);
          if ( i >= a3 )
            break;
          Key = JetMakeKey(v14, v13, a2[2 * i], (unsigned int)a2[2 * i + 1], HIDWORD(a2[2 * i + 1]));
          if ( Key < 0 )
          {
            v17 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v15);
            LODWORD(grbit) = Key;
            DSLogger::LogError((DSLogger *)v17, L"DbTable::Seek", 821, L"JET_ERR : %d", grbit);
            v8 = JetToHResult(Key);
            if ( v8 < 0 )
              return (unsigned int)v8;
          }
        }
        v18 = JetSeek(v14, v13, a5 | 0x20);
      }
      else
      {
        v18 = JetMove(*((_QWORD *)this + 5), *((_QWORD *)this + 9), 0x80000000, 0);
      }
      v20 = v18;
      if ( v18 == -1601 )
      {
        return 1;
      }
      else if ( v18 < 0 )
      {
        v21 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v19);
        LODWORD(grbit) = v20;
        DSLogger::LogError((DSLogger *)v21, L"DbTable::Seek", 841, L"JET_ERR : %d", grbit);
        return (unsigned int)JetToHResult(v20);
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001526c  push    rbx
0x18001526e  push    rbp
0x18001526f  push    rsi
0x180015270  push    rdi
0x180015271  push    r14
0x180015273  push    r15
0x180015275  sub     rsp, 38h
0x180015279  mov     r14d, r8d
0x18001527c  mov     rbp, rdx
0x18001527f  mov     rdi, rcx
0x180015282  cmp     r9d, [rcx+20h]
0x180015286  jge     loc_1800153D9
0x18001528c  mov     r8, [rcx+18h]
0x180015290  xor     ebx, ebx
0x180015292  mov     rdx, [rcx+48h]; tableid
0x180015296  mov     rcx, [rcx+28h]; sesid
0x18001529a  movsxd  rax, r9d
0x18001529d  lea     r9, [rax+rax*4]
0x1800152a1  add     r9, r9
0x1800152a4  mov     r8, [r8+r9*8+8]; szIndexName
0x1800152a9  call    cs:__imp_JetSetCurrentIndexW
0x1800152af  mov     esi, eax
0x1800152b1  test    eax, eax
0x1800152b3  jns     short loc_1800152EB
0x1800152b5  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800152ba  lea     r9, aJetErrD; "JET_ERR : %d"
0x1800152c1  mov     dword ptr [rsp+68h+grbit], esi
0x1800152c5  mov     r8d, 32Ch; unsigned int
0x1800152cb  lea     rdx, aDbtableSeek; "DbTable::Seek"
0x1800152d2  mov     rcx, rax; this
0x1800152d5  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800152da  mov     ecx, esi; int
0x1800152dc  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x1800152e1  mov     ebx, eax
0x1800152e3  test    eax, eax
0x1800152e5  js      loc_1800153DE
0x1800152eb  test    rbp, rbp
0x1800152ee  jz      loc_18001537E
0x1800152f4  test    r14d, r14d
0x1800152f7  jz      loc_18001537E
0x1800152fd  xor     esi, esi
0x1800152ff  mov     rdx, [rdi+48h]; tableid
0x180015303  mov     rcx, [rdi+28h]; sesid
0x180015307  cmp     esi, r14d
0x18001530a  jge     short loc_18001536A
0x18001530c  movsxd  r8, esi
0x18001530f  add     r8, r8
0x180015312  mov     eax, [rbp+r8*8+0Ch]
0x180015317  mov     r9d, [rbp+r8*8+8]; cbData
0x18001531c  mov     r8, [rbp+r8*8+0]; pvData
0x180015321  mov     dword ptr [rsp+68h+grbit], eax; grbit
0x180015325  call    cs:__imp_JetMakeKey
0x18001532b  mov     r15d, eax
0x18001532e  test    eax, eax
0x180015330  jns     short loc_180015366
0x180015332  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180015337  lea     r9, aJetErrD; "JET_ERR : %d"
0x18001533e  mov     dword ptr [rsp+68h+grbit], r15d
0x180015343  mov     r8d, 335h; unsigned int
0x180015349  lea     rdx, aDbtableSeek; "DbTable::Seek"
0x180015350  mov     rcx, rax; this
0x180015353  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180015358  mov     ecx, r15d; int
0x18001535b  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x180015360  mov     ebx, eax
0x180015362  test    eax, eax
0x180015364  js      short loc_1800153DE
0x180015366  inc     esi
0x180015368  jmp     short loc_1800152FF
0x18001536a  mov     r8d, [rsp+68h+arg_20]
0x180015372  or      r8d, 20h; grbit
0x180015376  call    cs:__imp_JetSeek
0x18001537c  jmp     short loc_180015395
0x18001537e  mov     rdx, [rdi+48h]; tableid
0x180015382  xor     r9d, r9d; grbit
0x180015385  mov     rcx, [rdi+28h]; sesid
0x180015389  mov     r8d, 80000000h; cRow
0x18001538f  call    cs:__imp_JetMove
0x180015395  mov     edi, eax
0x180015397  cmp     eax, 0FFFFF9BFh
0x18001539c  jnz     short loc_1800153A5
0x18001539e  mov     ebx, 1
0x1800153a3  jmp     short loc_1800153DE
0x1800153a5  test    edi, edi
0x1800153a7  jns     short loc_1800153DE
0x1800153a9  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800153ae  lea     r9, aJetErrD; "JET_ERR : %d"
0x1800153b5  mov     dword ptr [rsp+68h+grbit], edi
0x1800153b9  mov     r8d, 349h; unsigned int
0x1800153bf  lea     rdx, aDbtableSeek; "DbTable::Seek"
0x1800153c6  mov     rcx, rax; this
0x1800153c9  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800153ce  mov     ecx, edi; int
0x1800153d0  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x1800153d5  mov     ebx, eax
0x1800153d7  jmp     short loc_1800153DE
0x1800153d9  mov     ebx, 80004005h
0x1800153de  mov     eax, ebx
0x1800153e0  add     rsp, 38h
0x1800153e4  pop     r15
0x1800153e6  pop     r14
0x1800153e8  pop     rdi
0x1800153e9  pop     rsi
0x1800153ea  pop     rbp
0x1800153eb  pop     rbx
0x1800153ec  retn
```
