# CScriptManager::UnInit(void)

- ea: `0x180057034`
- end: `0x180057134`
- name: `?UnInit@CScriptManager@@QEAAJXZ`
- size: `256`
- prototype: `__int64 __fastcall(CScriptManager *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180004a64`
- `0x18003db14`

## callees

- `0x18000f614`
- `0x18004197c`
- `0x180057034`
- `0x18005713c`
- `0x1800571f8`
- `0x180064010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180057105`
- `KERNEL32!DeleteCriticalSection` at `0x180057112`
- `KERNEL32!DeleteCriticalSection` at `0x18005711f`
- `KERNEL32!DeleteCriticalSection` at `0x180057105`
- `KERNEL32!DeleteCriticalSection` at `0x180057112`
- `KERNEL32!DeleteCriticalSection` at `0x18005711f`
- `iisutil!RemoveWorkItem` at `0x180057056`
- `iisutil!RemoveWorkItem` at `0x180057056`

## pseudocode

```c
__int64 __fastcall CScriptManager::UnInit(CScriptManager *this)
{
  int inited; // ebx
  CScriptManager *v2; // rcx
  CScriptManager *v3; // rcx
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax

  inited = 0;
  if ( byte_18007CC48 )
  {
    v2 = (CScriptManager *)(unsigned int)dword_18007CFF8;
    if ( dword_18007CFF8 )
    {
      RemoveWorkItem(dword_18007CFF8);
      dword_18007CFF8 = 0;
    }
    inited = CScriptManager::UnInitASEElems(v2);
    v4 = CScriptManager::UnInitPLL(v3);
    if ( inited >= 0 )
      inited = v4;
    v5 = CHashTable::UnInit((CHashTable *)&qword_18007CED0);
    if ( inited >= 0 )
      inited = v5;
    v6 = CHashTable::UnInit((CHashTable *)&qword_18007CC50);
    if ( inited >= 0 )
      inited = v6;
    v7 = CHashTable::UnInit((CHashTable *)&qword_18007CD90);
    if ( inited >= 0 )
      inited = v7;
    if ( g_pWrapTypelibs )
    {
      (*(void (__fastcall **)(struct IWrapTypeLibs *))(*(_QWORD *)g_pWrapTypelibs + 16LL))(g_pWrapTypelibs);
      g_pWrapTypelibs = 0;
    }
    DeleteCriticalSection(&CriticalSection);
    DeleteCriticalSection(&stru_18007CD68);
    DeleteCriticalSection(&stru_18007CEA8);
    byte_18007CC48 = 0;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180057034  mov     [rsp+arg_0], rcx
0x180057039  push    rbx
0x18005703a  sub     rsp, 30h
0x18005703e  xor     ebx, ebx
0x180057040  cmp     cs:byte_18007CC48, bl
0x180057046  jz      loc_18005712C
0x18005704c  mov     ecx, cs:dword_18007CFF8
0x180057052  test    ecx, ecx
0x180057054  jz      short loc_180057062
0x180057056  call    cs:__imp_?RemoveWorkItem@@YAHK@Z; RemoveWorkItem(ulong)
0x18005705c  mov     cs:dword_18007CFF8, ebx
0x180057062  call    ?UnInitASEElems@CScriptManager@@AEAAJXZ; CScriptManager::UnInitASEElems(void)
0x180057067  mov     ebx, eax
0x180057069  call    ?UnInitPLL@CScriptManager@@AEAAJXZ; CScriptManager::UnInitPLL(void)
0x18005706e  test    ebx, ebx
0x180057070  cmovns  ebx, eax
0x180057073  lea     rcx, qword_18007CED0; this
0x18005707a  call    ?UnInit@CHashTable@@QEAAJXZ; CHashTable::UnInit(void)
0x18005707f  test    ebx, ebx
0x180057081  cmovns  ebx, eax
0x180057084  lea     rcx, qword_18007CC50; this
0x18005708b  call    ?UnInit@CHashTable@@QEAAJXZ; CHashTable::UnInit(void)
0x180057090  test    ebx, ebx
0x180057092  cmovns  ebx, eax
0x180057095  lea     rcx, qword_18007CD90; this
0x18005709c  call    ?UnInit@CHashTable@@QEAAJXZ; CHashTable::UnInit(void)
0x1800570a1  test    ebx, ebx
0x1800570a3  cmovns  ebx, eax
0x1800570a6  mov     dword ptr [rsp+38h+arg_0], ebx
0x1800570aa  mov     rcx, cs:?g_pWrapTypelibs@@3PEAUIWrapTypeLibs@@EA; IWrapTypeLibs * g_pWrapTypelibs
0x1800570b1  test    rcx, rcx
0x1800570b4  jz      short loc_1800570FE
0x1800570b6  mov     rax, [rcx]
0x1800570b9  mov     rax, [rax+10h]
0x1800570bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570c2  jmp     short loc_1800570F3
0x1800570c4  mov     r9d, eax
0x1800570c7  lea     rax, aCscriptmanager_1; "CScriptManager::UnInit()"
0x1800570ce  mov     [rsp+38h+var_10], rax
0x1800570d3  lea     rax, aIwraptypelibsR; "IWrapTypeLibs::Release()"
0x1800570da  mov     [rsp+38h+var_18], rax
0x1800570df  xor     edx, edx; struct CHitObj *
0x1800570e1  lea     r8d, [rdx+1]; int
0x1800570e5  mov     ecx, 3F4h; unsigned int
0x1800570ea  call    ?HandleErrorMissingFilename@@YAXIPEAVCHitObj@@HZZ; HandleErrorMissingFilename(uint,CHitObj *,int,...)
0x1800570ef  mov     ebx, dword ptr [rsp+38h+arg_0]
0x1800570f3  mov     cs:?g_pWrapTypelibs@@3PEAUIWrapTypeLibs@@EA, 0; IWrapTypeLibs * g_pWrapTypelibs
0x1800570fe  lea     rcx, CriticalSection; lpCriticalSection
0x180057105  call    cs:__imp_DeleteCriticalSection
0x18005710b  lea     rcx, stru_18007CD68; lpCriticalSection
0x180057112  call    cs:__imp_DeleteCriticalSection
0x180057118  lea     rcx, stru_18007CEA8; lpCriticalSection
0x18005711f  call    cs:__imp_DeleteCriticalSection
0x180057125  mov     cs:byte_18007CC48, 0
0x18005712c  mov     eax, ebx
0x18005712e  add     rsp, 30h
0x180057132  pop     rbx
0x180057133  retn
```
