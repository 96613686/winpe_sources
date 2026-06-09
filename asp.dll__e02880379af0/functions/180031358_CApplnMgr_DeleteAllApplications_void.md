# CApplnMgr::DeleteAllApplications(void)

- ea: `0x180031358`
- end: `0x180031481`
- name: `?DeleteAllApplications@CApplnMgr@@QEAAXXZ`
- size: `297`
- prototype: `void __fastcall(CApplnMgr *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18003f760`

## callees

- `0x18000a160`
- `0x180031358`
- `0x1800328b4`
- `0x180045ccc`
- `0x180045dc0`
- `0x180045f00`
- `0x180047b9c`
- `0x180047d98`
- `0x180064010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18003147a`
- `KERNEL32!EnterCriticalSection` at `0x18003136e`
- `KERNEL32!EnterCriticalSection` at `0x18003136e`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800313f6`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800313f6`

## pseudocode

```c
void __fastcall CApplnMgr::DeleteAllApplications(CApplnMgr *this)
{
  __int64 v1; // rsi
  __int64 v2; // rdi
  int v3; // eax
  bool v4; // zf
  CPtrArray *v5; // rbx
  CHitObj *v6; // rax
  CHitObj *v7; // rax
  CHitObj *v8; // rbx

  EnterCriticalSection(&stru_180079B28);
  v1 = xmmword_180079A30;
  CHashTable::ReInit((CHashTable *)&g_ApplnMgr);
  while ( v1 )
  {
    v2 = v1 - 32;
    v1 = *(_QWORD *)(v1 + 32);
    v3 = *(_DWORD *)(v2 + 72);
    if ( (v3 & 8) == 0 )
    {
      v4 = *(_DWORD *)(v2 + 304) == 0;
      *(_DWORD *)(v2 + 72) = v3 | 8;
      if ( v4 )
      {
        v5 = (CPtrArray *)(v2 + 288);
      }
      else
      {
        do
        {
          (*(void (__fastcall **)(_QWORD))(***(_QWORD ***)(v2 + 296) + 16LL))(**(_QWORD **)(v2 + 296));
          v5 = (CPtrArray *)(v2 + 288);
          CPtrArray::Remove((CPtrArray *)(v2 + 288), 0);
        }
        while ( *(_DWORD *)(v2 + 304) );
      }
      CPtrArray::Clear(v5);
      v6 = (CHitObj *)ALLOC_CACHE_HANDLER::Alloc(CHitObj::sm_pach);
      if ( v6 )
      {
        v7 = CHitObj::CHitObj(v6);
        v8 = v7;
        if ( !v7 )
          goto LABEL_12;
        CHitObj::ApplicationCleanupInit(v7, (struct CAppln *)v2);
        if ( (int)CHitObj::PostViperAsyncCall(v8) < 0 )
          goto LABEL_12;
      }
      else
      {
        v8 = 0;
LABEL_12:
        CAppln::UnInit((CScriptManager *)v2);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
        if ( v8 )
          (**(void (__fastcall ***)(CHitObj *, __int64))v8)(v8, 1);
      }
    }
  }
  LeaveCriticalSection(&stru_180079B28);
}

```

## disassembly

```asm
0x180031358  mov     [rsp+arg_0], rbx
0x18003135d  mov     [rsp+arg_8], rsi
0x180031362  push    rdi
0x180031363  sub     rsp, 20h
0x180031367  lea     rcx, stru_180079B28; lpCriticalSection
0x18003136e  call    cs:__imp_EnterCriticalSection
0x180031374  mov     rsi, qword ptr cs:xmmword_180079A30
0x18003137b  lea     rcx, ?g_ApplnMgr@@3VCApplnMgr@@A; this
0x180031382  call    ?ReInit@CHashTable@@QEAAXXZ; CHashTable::ReInit(void)
0x180031387  jmp     loc_18003145B
0x18003138c  lea     rdi, [rsi-20h]
0x180031390  mov     rsi, [rsi+20h]
0x180031394  mov     eax, [rdi+48h]
0x180031397  test    al, 8
0x180031399  jnz     loc_18003145B
0x18003139f  or      eax, 8
0x1800313a2  cmp     dword ptr [rdi+130h], 0
0x1800313a9  mov     [rdi+48h], eax
0x1800313ac  jz      short loc_1800313E0
0x1800313ae  mov     rax, [rdi+128h]
0x1800313b5  mov     rcx, [rax]
0x1800313b8  mov     rax, [rcx]
0x1800313bb  mov     rax, [rax+10h]
0x1800313bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313c4  lea     rbx, [rdi+120h]
0x1800313cb  xor     edx, edx; int
0x1800313cd  mov     rcx, rbx; this
0x1800313d0  call    ?Remove@CPtrArray@@QEAAJH@Z; CPtrArray::Remove(int)
0x1800313d5  cmp     dword ptr [rdi+130h], 0
0x1800313dc  jnz     short loc_1800313AE
0x1800313de  jmp     short loc_1800313E7
0x1800313e0  lea     rbx, [rdi+120h]
0x1800313e7  mov     rcx, rbx; this
0x1800313ea  call    ?Clear@CPtrArray@@QEAAJXZ; CPtrArray::Clear(void)
0x1800313ef  mov     rcx, cs:?sm_pach@CHitObj@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CHitObj::sm_pach
0x1800313f6  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x1800313fc  test    rax, rax
0x1800313ff  jz      short loc_18003142A
0x180031401  mov     rcx, rax; this
0x180031404  call    ??0CHitObj@@QEAA@XZ; CHitObj::CHitObj(void)
0x180031409  mov     rbx, rax
0x18003140c  test    rax, rax
0x18003140f  jz      short loc_18003142C
0x180031411  mov     rdx, rdi; struct CAppln *
0x180031414  mov     rcx, rax; this
0x180031417  call    ?ApplicationCleanupInit@CHitObj@@QEAAXPEAVCAppln@@@Z; CHitObj::ApplicationCleanupInit(CAppln *)
0x18003141c  mov     rcx, rbx; this
0x18003141f  call    ?PostViperAsyncCall@CHitObj@@QEAAJXZ; CHitObj::PostViperAsyncCall(void)
0x180031424  test    eax, eax
0x180031426  jns     short loc_18003145B
0x180031428  jmp     short loc_18003142C
0x18003142a  xor     ebx, ebx
0x18003142c  mov     rcx, rdi; pUnk
0x18003142f  call    ?UnInit@CAppln@@QEAAJXZ; CAppln::UnInit(void)
0x180031434  mov     rax, [rdi]
0x180031437  mov     rcx, rdi
0x18003143a  mov     rax, [rax+10h]
0x18003143e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031443  test    rbx, rbx
0x180031446  jz      short loc_18003145B
0x180031448  mov     rax, [rbx]
0x18003144b  mov     edx, 1
0x180031450  mov     rcx, rbx
0x180031453  mov     rax, [rax]
0x180031456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003145b  test    rsi, rsi
0x18003145e  jnz     loc_18003138C
0x180031464  lea     rcx, stru_180079B28
0x18003146b  mov     rbx, [rsp+28h+arg_0]
0x180031470  mov     rsi, [rsp+28h+arg_8]
0x180031475  add     rsp, 20h
0x180031479  pop     rdi
0x18003147a  jmp     cs:__imp_LeaveCriticalSection
```
