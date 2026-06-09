# CDlpManager::SetWorkingPath(ushort const *)

- ea: `0x14004f250`
- end: `0x14004f65a`
- name: `?SetWorkingPath@CDlpManager@@UEAAJPEBG@Z`
- size: `1034`
- prototype: `__int64 __fastcall(CDlpManager *__hidden this, LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callees

- `0x140005e4c`
- `0x1400076c8`
- `0x14000f4a4`
- `0x1400135b8`
- `0x14002d930`
- `0x14002f6e0`
- `0x140034ab4`
- `0x140041ad0`
- `0x14004f250`
- `0x140082010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14004f5f9`
- `KERNEL32!HeapFree` at `0x14004f5f9`
- `KERNEL32!GetProcessHeap` at `0x14004f5e4`
- `KERNEL32!GetProcessHeap` at `0x14004f5e4`
- `KERNEL32!GetFileAttributesW` at `0x14004f416`
- `KERNEL32!GetFileAttributesW` at `0x14004f416`
- `KERNEL32!LeaveCriticalSection` at `0x14004f62d`
- `KERNEL32!LeaveCriticalSection` at `0x14004f62d`
- `KERNEL32!EnterCriticalSection` at `0x14004f27f`
- `KERNEL32!EnterCriticalSection` at `0x14004f27f`

## string_xrefs

- `0x14004f2f5`: `CDlpManager::SetWorkingPath`
- `0x14004f3cf`: `CDlpManager::SetWorkingPath`
- `0x14004f4f1`: `CDlpManager::SetWorkingPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpManager::SetWorkingPath(CDlpManager *this, LPCWSTR lpFileName)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  enum WINDLP_STATE *v5; // rdx
  struct CDlpStateXml *v6; // rdi
  const unsigned __int16 *v7; // r14
  int FullPathNameW; // esi
  __int64 v9; // rax
  unsigned int v10; // ebx
  int v11; // eax
  __int64 v12; // rax
  unsigned int v13; // ebx
  int v14; // eax
  DWORD FileAttributesW; // ebx
  int v16; // ebx
  __int64 v17; // rax
  unsigned int v18; // ebx
  int v19; // eax
  _DWORD *v20; // rbx
  struct CDlpStateXml *v21; // rax
  __int64 v22; // rdx
  HANDLE ProcessHeap; // rax
  int v25; // [rsp+20h] [rbp-68h]
  int v26; // [rsp+28h] [rbp-60h]
  LPCWSTR lpFileNamea; // [rsp+90h] [rbp+8h] BYREF
  struct CDlpStateXml *v28; // [rsp+98h] [rbp+10h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 312);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  v6 = 0;
  v28 = 0;
  v7 = 0;
  lpFileNamea = 0;
  if ( !lpFileName )
  {
    FullPathNameW = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
      goto LABEL_42;
    v9 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
    v10 = 0;
    if ( !v9 )
      goto LABEL_7;
    v26 = -2147024809;
    v25 = 2177;
    goto LABEL_5;
  }
  FullPathNameW = CDlpManager::CheckInitialized(this, v5);
  if ( FullPathNameW >= 0 )
  {
    FullPathNameW = CMiscHelpersT<CEmptyType>::GetFullPathNameW(lpFileName, (LPWSTR *)&lpFileNamea, 0);
    if ( FullPathNameW < 0 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
      {
        v12 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
        v13 = 0;
        if ( v12 )
        {
          v14 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v12,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDlpManager::SetWorkingPath",
                  2185,
                  FullPathNameW,
                  -2);
          v13 = v14;
          if ( v14 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
      }
      v7 = lpFileNamea;
      goto LABEL_42;
    }
    v7 = lpFileNamea;
    FileAttributesW = GetFileAttributesW(lpFileNamea);
    if ( FileAttributesW == -1 )
      v16 = 0;
    else
      v16 = (FileAttributesW >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    FullPathNameW = 0;
    if ( !v16 )
    {
      FullPathNameW = -2147024893;
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_42;
      v9 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v10 = 0;
      if ( !v9 )
        goto LABEL_7;
      v26 = -2147024893;
      v25 = 2187;
      goto LABEL_5;
    }
    if ( *((_QWORD *)this + 83) )
    {
      FullPathNameW = CDlpStateXml::CreateInstance(&v28);
      if ( FullPathNameW < 0 )
      {
        if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        {
          v17 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
          v18 = 0;
          if ( v17 )
          {
            v19 = CDlpLogT<CEmptyType>::DlpLogFormat(
                    v17,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDlpManager::SetWorkingPath",
                    2195,
                    FullPathNameW,
                    -2);
            v18 = v19;
            if ( v19 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v19);
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v18);
        }
        v6 = v28;
        goto LABEL_42;
      }
      v6 = v28;
      FullPathNameW = CDlpStateXml::Initialize(v28, v7, 0);
      if ( FullPathNameW < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
          goto LABEL_42;
        v9 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
        v10 = 0;
        if ( !v9 )
          goto LABEL_7;
        v26 = FullPathNameW;
        v25 = 2199;
LABEL_5:
        v11 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v9,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpManager::SetWorkingPath",
                v25,
                v26,
                -2);
        v10 = v11;
        if ( v11 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
        goto LABEL_7;
      }
      v20 = (_DWORD *)*((_QWORD *)this + 83);
      if ( !v20 )
        v20 = 0;
      v21 = v6;
      v6 = 0;
      *((_QWORD *)this + 83) = v21;
      v20[37] = 1;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v22 = (__int64)v7;
    v7 = 0;
    SH<unsigned short *,SH_SSTRING>::Attach((__int64 *)this + 15, v22);
    goto LABEL_42;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
  {
    v9 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
    v10 = 0;
    if ( v9 )
    {
      v26 = FullPathNameW;
      v25 = 2181;
      goto LABEL_5;
    }
LABEL_7:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
  }
LABEL_42:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)FullPathNameW);
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v7 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v6 )
    (*(void (__fastcall **)(struct CDlpStateXml *))(*(_QWORD *)v6 + 16LL))(v6);
  LeaveCriticalSection(v4);
  return (unsigned int)FullPathNameW;
}

```

## disassembly

```asm
0x14004f250  mov     rax, rsp
0x14004f253  push    rsi
0x14004f254  push    rdi
0x14004f255  push    r12
0x14004f257  push    r14
0x14004f259  push    r15
0x14004f25b  sub     rsp, 60h
0x14004f25f  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x14004f267  mov     [rax+18h], rbx
0x14004f26b  mov     [rax+20h], rbp
0x14004f26f  mov     rbx, rdx
0x14004f272  mov     rbp, rcx
0x14004f275  lea     r15, [rcx+138h]
0x14004f27c  mov     rcx, r15; lpCriticalSection
0x14004f27f  call    cs:__imp_EnterCriticalSection
0x14004f286  nop     dword ptr [rax+rax+00h]
0x14004f28b  mov     [rsp+88h+var_40], 1
0x14004f293  xor     r12d, r12d
0x14004f296  mov     edi, r12d
0x14004f299  mov     [rsp+88h+arg_8], r12
0x14004f2a1  mov     r14d, r12d
0x14004f2a4  mov     [rsp+88h+lpFileName], r12
0x14004f2ac  test    rbx, rbx
0x14004f2af  jnz     short loc_14004F329
0x14004f2b1  mov     esi, 80070057h
0x14004f2b6  mov     rax, [rbp+50h]
0x14004f2ba  lea     rcx, [rbp+50h]
0x14004f2be  mov     rax, [rax+10h]
0x14004f2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f2c7  test    rax, rax
0x14004f2ca  jz      loc_14004F5D7
0x14004f2d0  mov     rax, [rbp+50h]
0x14004f2d4  lea     rcx, [rbp+50h]
0x14004f2d8  mov     rax, [rax+10h]
0x14004f2dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f2e1  mov     ebx, r12d
0x14004f2e4  test    rax, rax
0x14004f2e7  jz      short loc_14004F31D
0x14004f2e9  mov     [rsp+88h+var_60], esi
0x14004f2ed  mov     [rsp+88h+var_68], 881h
0x14004f2f5  lea     r9, aCdlpmanagerSet_4; "CDlpManager::SetWorkingPath"
0x14004f2fc  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14004f303  mov     edx, 4
0x14004f308  mov     rcx, rax
0x14004f30b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004f310  test    eax, eax
0x14004f312  mov     ebx, eax
0x14004f314  jns     short loc_14004F31D
0x14004f316  mov     ecx, eax
0x14004f318  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14004f31d  mov     ecx, ebx
0x14004f31f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004f324  jmp     loc_14004F5D7
0x14004f329  mov     rcx, rbp; this
0x14004f32c  call    ?CheckInitialized@CDlpManager@@AEAAJPEAW4WINDLP_STATE@@@Z; CDlpManager::CheckInitialized(WINDLP_STATE *)
0x14004f331  mov     esi, eax
0x14004f333  test    eax, eax
0x14004f335  jns     short loc_14004F37B
0x14004f337  mov     rdx, [rbp+50h]
0x14004f33b  lea     rcx, [rbp+50h]
0x14004f33f  mov     rax, [rdx+10h]
0x14004f343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f348  test    rax, rax
0x14004f34b  jz      loc_14004F5D7
0x14004f351  mov     rax, [rbp+50h]
0x14004f355  lea     rcx, [rbp+50h]
0x14004f359  mov     rax, [rax+10h]
0x14004f35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f362  mov     ebx, r12d
0x14004f365  test    rax, rax
0x14004f368  jz      short loc_14004F31D
0x14004f36a  mov     [rsp+88h+var_60], esi
0x14004f36e  mov     [rsp+88h+var_68], 885h
0x14004f376  jmp     loc_14004F2F5
0x14004f37b  xor     r8d, r8d
0x14004f37e  lea     rdx, [rsp+88h+lpFileName]
0x14004f386  mov     rcx, rbx; lpFileName
0x14004f389  call    ?GetFullPathNameW@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG1@Z; CMiscHelpersT<CEmptyType>::GetFullPathNameW(ushort const *,ushort * *,ushort * *)
0x14004f38e  mov     esi, eax
0x14004f390  test    eax, eax
0x14004f392  jns     short loc_14004F40B
0x14004f394  mov     rax, [rbp+50h]
0x14004f398  lea     rcx, [rbp+50h]
0x14004f39c  mov     rax, [rax+10h]
0x14004f3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f3a5  test    rax, rax
0x14004f3a8  jz      short loc_14004F3FE
0x14004f3aa  mov     rax, [rbp+50h]
0x14004f3ae  lea     rcx, [rbp+50h]
0x14004f3b2  mov     rax, [rax+10h]
0x14004f3b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f3bb  mov     ebx, r12d
0x14004f3be  test    rax, rax
0x14004f3c1  jz      short loc_14004F3F7
0x14004f3c3  mov     [rsp+88h+var_60], esi
0x14004f3c7  mov     [rsp+88h+var_68], 889h
0x14004f3cf  lea     r9, aCdlpmanagerSet_4; "CDlpManager::SetWorkingPath"
0x14004f3d6  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14004f3dd  mov     edx, 4
0x14004f3e2  mov     rcx, rax
0x14004f3e5  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004f3ea  mov     ebx, eax
0x14004f3ec  test    eax, eax
0x14004f3ee  jns     short loc_14004F3F7
0x14004f3f0  mov     ecx, eax
0x14004f3f2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14004f3f7  mov     ecx, ebx
0x14004f3f9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004f3fe  mov     r14, [rsp+88h+lpFileName]
0x14004f406  jmp     loc_14004F5D7
0x14004f40b  mov     r14, [rsp+88h+lpFileName]
0x14004f413  mov     rcx, r14; lpFileName
0x14004f416  call    cs:__imp_GetFileAttributesW
0x14004f41d  nop     dword ptr [rax+rax+00h]
0x14004f422  mov     ebx, eax
0x14004f424  cmp     eax, 0FFFFFFFFh
0x14004f427  jz      short loc_14004F431
0x14004f429  shr     ebx, 4
0x14004f42c  and     ebx, 1
0x14004f42f  jmp     short loc_14004F434
0x14004f431  mov     ebx, r12d
0x14004f434  xor     ecx, ecx
0x14004f436  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004f43b  xor     ecx, ecx
0x14004f43d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004f442  mov     esi, r12d
0x14004f445  test    ebx, ebx
0x14004f447  jnz     short loc_14004F496
0x14004f449  mov     esi, 80070003h
0x14004f44e  mov     rax, [rbp+50h]
0x14004f452  lea     rcx, [rbp+50h]
0x14004f456  mov     rax, [rax+10h]
0x14004f45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f45f  test    rax, rax
0x14004f462  jz      loc_14004F5D7
0x14004f468  mov     rax, [rbp+50h]
0x14004f46c  lea     rcx, [rbp+50h]
0x14004f470  mov     rax, [rax+10h]
0x14004f474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f479  mov     ebx, r12d
0x14004f47c  test    rax, rax
0x14004f47f  jz      loc_14004F31D
0x14004f485  mov     [rsp+88h+var_60], esi
0x14004f489  mov     [rsp+88h+var_68], 88Bh
0x14004f491  jmp     loc_14004F2F5
0x14004f496  cmp     [rbp+298h], r12
0x14004f49d  jz      loc_14004F5C8
0x14004f4a3  lea     rcx, [rsp+88h+arg_8]; struct CDlpStateXml **
0x14004f4ab  call    ?CreateInstance@CDlpStateXml@@SAJPEAPEAV1@@Z; CDlpStateXml::CreateInstance(CDlpStateXml * *)
0x14004f4b0  mov     esi, eax
0x14004f4b2  test    eax, eax
0x14004f4b4  jns     short loc_14004F52D
0x14004f4b6  mov     rax, [rbp+50h]
0x14004f4ba  lea     rcx, [rbp+50h]
0x14004f4be  mov     rax, [rax+10h]
0x14004f4c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f4c7  test    rax, rax
0x14004f4ca  jz      short loc_14004F520
0x14004f4cc  mov     rax, [rbp+50h]
0x14004f4d0  lea     rcx, [rbp+50h]
0x14004f4d4  mov     rax, [rax+10h]
0x14004f4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f4dd  mov     ebx, r12d
0x14004f4e0  test    rax, rax
0x14004f4e3  jz      short loc_14004F519
0x14004f4e5  mov     [rsp+88h+var_60], esi
0x14004f4e9  mov     [rsp+88h+var_68], 893h
0x14004f4f1  lea     r9, aCdlpmanagerSet_4; "CDlpManager::SetWorkingPath"
0x14004f4f8  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14004f4ff  mov     edx, 4
0x14004f504  mov     rcx, rax
0x14004f507  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004f50c  mov     ebx, eax
0x14004f50e  test    eax, eax
0x14004f510  jns     short loc_14004F519
0x14004f512  mov     ecx, eax
0x14004f514  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14004f519  mov     ecx, ebx
0x14004f51b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004f520  mov     rdi, [rsp+88h+arg_8]
0x14004f528  jmp     loc_14004F5D7
0x14004f52d  xor     r8d, r8d; int
0x14004f530  mov     rdx, r14; unsigned __int16 *
0x14004f533  mov     rdi, [rsp+88h+arg_8]
0x14004f53b  mov     rcx, rdi; this
0x14004f53e  call    ?Initialize@CDlpStateXml@@QEAAJPEBGH@Z; CDlpStateXml::Initialize(ushort const *,int)
0x14004f543  mov     esi, eax
0x14004f545  test    eax, eax
0x14004f547  jns     short loc_14004F58D
0x14004f549  mov     rax, [rbp+50h]
0x14004f54d  lea     rcx, [rbp+50h]
0x14004f551  mov     rax, [rax+10h]
0x14004f555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f55a  test    rax, rax
0x14004f55d  jz      short loc_14004F5D7
0x14004f55f  mov     rax, [rbp+50h]
0x14004f563  lea     rcx, [rbp+50h]
0x14004f567  mov     rax, [rax+10h]
0x14004f56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f570  mov     ebx, r12d
0x14004f573  test    rax, rax
0x14004f576  jz      loc_14004F31D
0x14004f57c  mov     [rsp+88h+var_60], esi
0x14004f580  mov     [rsp+88h+var_68], 897h
0x14004f588  jmp     loc_14004F2F5
0x14004f58d  mov     rbx, [rbp+298h]
0x14004f594  test    rbx, rbx
0x14004f597  cmovz   rbx, r12
0x14004f59b  mov     rax, rdi
0x14004f59e  mov     rdi, r12
0x14004f5a1  mov     [rbp+298h], rax
0x14004f5a8  mov     dword ptr [rbx+94h], 1
0x14004f5b2  xor     ecx, ecx
0x14004f5b4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004f5b9  mov     rax, [rbx]
0x14004f5bc  mov     rcx, rbx
0x14004f5bf  mov     rax, [rax+10h]
0x14004f5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f5c8  mov     rdx, r14
0x14004f5cb  mov     r14, r12
0x14004f5ce  lea     rcx, [rbp+78h]
0x14004f5d2  call    ?Attach@?$SH@PEAGVSH_SSTRING@@@@QEAAXPEAG@Z; SH<ushort *,SH_SSTRING>::Attach(ushort *)
0x14004f5d7  mov     ecx, esi
0x14004f5d9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004f5de  nop
0x14004f5df  test    r14, r14
0x14004f5e2  jz      short loc_14004F60D
0x14004f5e4  call    cs:__imp_GetProcessHeap
0x14004f5eb  nop     dword ptr [rax+rax+00h]
0x14004f5f0  mov     rcx, rax; hHeap
0x14004f5f3  lea     r8, [r14-4]; lpMem
0x14004f5f7  xor     edx, edx; dwFlags
0x14004f5f9  call    cs:__imp_HeapFree
0x14004f600  nop     dword ptr [rax+rax+00h]
0x14004f605  xor     ecx, ecx
0x14004f607  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004f60c  nop
0x14004f60d  test    rdi, rdi
0x14004f610  jz      short loc_14004F622
0x14004f612  mov     rax, [rdi]
0x14004f615  mov     rcx, rdi
0x14004f618  mov     rax, [rax+10h]
0x14004f61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f621  nop
0x14004f622  mov     eax, [rsp+88h+var_40]
0x14004f626  test    eax, eax
0x14004f628  jz      short loc_14004F63E
0x14004f62a  mov     rcx, r15; lpCriticalSection
0x14004f62d  call    cs:__imp_LeaveCriticalSection
0x14004f634  nop     dword ptr [rax+rax+00h]
0x14004f639  mov     [rsp+88h+var_40], r12d
0x14004f63e  mov     eax, esi
0x14004f640  lea     r11, [rsp+88h+var_28]
0x14004f645  mov     rbx, [r11+40h]
0x14004f649  mov     rbp, [r11+48h]
0x14004f64d  mov     rsp, r11
0x14004f650  pop     r15
0x14004f652  pop     r14
0x14004f654  pop     r12
0x14004f656  pop     rdi
0x14004f657  pop     rsi
0x14004f658  retn
```
