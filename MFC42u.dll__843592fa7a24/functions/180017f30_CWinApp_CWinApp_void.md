# CWinApp::~CWinApp(void)

- ea: `0x180017f30`
- end: `0x18001810b`
- name: `??1CWinApp@@UEAA@XZ`
- size: `475`
- prototype: `void __fastcall(CWinApp *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800018f0`
- `0x180070f10`

## callees

- `0x180013330`
- `0x180017f30`
- `0x180018120`
- `0x18005f520`
- `0x1800d7010`

## import_xrefs

- `msvcrt!free` at `0x180017ff3`
- `msvcrt!free` at `0x180018000`
- `msvcrt!free` at `0x18001800d`
- `msvcrt!free` at `0x18001801a`
- `msvcrt!free` at `0x180018027`
- `msvcrt!free` at `0x180017ff3`
- `msvcrt!free` at `0x180018000`
- `msvcrt!free` at `0x18001800d`
- `msvcrt!free` at `0x18001801a`
- `msvcrt!free` at `0x180018027`
- `KERNEL32!GlobalDeleteAtom` at `0x1800180d4`
- `KERNEL32!GlobalDeleteAtom` at `0x1800180df`
- `KERNEL32!GlobalDeleteAtom` at `0x1800180d4`
- `KERNEL32!GlobalDeleteAtom` at `0x1800180df`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWinApp::~CWinApp(CWinApp *this)
{
  CWinApp *v1; // rbx
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  ATOM v6; // cx
  ATOM v7; // cx
  __int64 v8; // rcx
  __int64 v9; // rcx
  CException *v10; // [rsp+20h] [rbp-18h] BYREF

  try
  {
    v1 = this;
    *(_QWORD *)this = &CWinApp::`vftable';
    v2 = *((_QWORD *)this + 31);
    if ( v2 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 8LL))(v2, 1);
    v3 = *((_QWORD *)v1 + 40);
    if ( v3 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 40LL))(v3, 1);
    if ( !*((_BYTE *)AfxGetModuleState() + 40) )
    {
      if ( CDocManager::pStaticList )
      {
        (*(void (__fastcall **)(CObList *, __int64))(*(_QWORD *)CDocManager::pStaticList + 8LL))(
          CDocManager::pStaticList,
          1);
        CDocManager::pStaticList = 0;
      }
      if ( CDocManager::pStaticDocManager )
      {
        (*(void (__fastcall **)(struct CDocManager *, __int64))(*(_QWORD *)CDocManager::pStaticDocManager + 8LL))(
          CDocManager::pStaticDocManager,
          1);
        CDocManager::pStaticDocManager = 0;
      }
    }
    v4 = (void *)*((_QWORD *)v1 + 36);
    if ( v4 )
      AfxGlobalFree(v4);
    v5 = (void *)*((_QWORD *)v1 + 37);
    if ( v5 )
      AfxGlobalFree(v5);
    v6 = *((_WORD *)v1 + 168);
    if ( v6 )
      GlobalDeleteAtom(v6);
    v7 = *((_WORD *)v1 + 169);
    if ( v7 )
      GlobalDeleteAtom(v7);
    v8 = *((_QWORD *)v1 + 41);
    if ( v8 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 8LL))(v8, 1);
    v9 = *((_QWORD *)v1 + 7);
    if ( *(_QWORD *)(v9 + 32) == *((_QWORD *)v1 + 29) )
      *(_QWORD *)(v9 + 32) = 0;
    if ( *(CWinApp **)(v9 + 8) == v1 )
      *(_QWORD *)(v9 + 8) = 0;
    free(*((void **)v1 + 29));
    free(*((void **)v1 + 30));
    free(*((void **)v1 + 33));
    free(*((void **)v1 + 34));
    free(*((void **)v1 + 35));
    *((_QWORD *)v1 + 11) = 0;
  }
  catch ( CException *v10 )
  {
    if ( v10 )
      CException::Delete(v10);
    v1 = this;
  }
  CWinThread::~CWinThread(v1);
}

```

## disassembly

```asm
0x180017f30  mov     [rsp+arg_8], rbx
0x180017f35  mov     [rsp+arg_0], rcx
0x180017f3a  push    rsi
0x180017f3b  sub     rsp, 30h
0x180017f3f  mov     rbx, rcx
0x180017f42  lea     rax, ??_7CWinApp@@6B@; const CWinApp::`vftable'
0x180017f49  mov     [rcx], rax
0x180017f4c  mov     rcx, [rcx+0F8h]
0x180017f53  xor     esi, esi
0x180017f55  test    rcx, rcx
0x180017f58  jnz     loc_180018043
0x180017f5e  mov     rcx, [rbx+140h]
0x180017f65  test    rcx, rcx
0x180017f68  jnz     loc_180018059
0x180017f6e  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x180017f73  cmp     [rax+28h], sil
0x180017f77  jz      loc_18001806F
0x180017f7d  mov     rcx, [rbx+120h]; hMem
0x180017f84  test    rcx, rcx
0x180017f87  jnz     loc_1800180C0
0x180017f8d  mov     rcx, [rbx+128h]; hMem
0x180017f94  test    rcx, rcx
0x180017f97  jnz     loc_1800180CA
0x180017f9d  movzx   ecx, word ptr [rbx+150h]; nAtom
0x180017fa4  test    cx, cx
0x180017fa7  jnz     loc_1800180D4
0x180017fad  movzx   ecx, word ptr [rbx+152h]; nAtom
0x180017fb4  test    cx, cx
0x180017fb7  jnz     loc_1800180DF
0x180017fbd  mov     rcx, [rbx+148h]
0x180017fc4  test    rcx, rcx
0x180017fc7  jnz     loc_1800180EA
0x180017fcd  mov     rcx, [rbx+38h]
0x180017fd1  mov     rax, [rbx+0E8h]
0x180017fd8  cmp     [rcx+20h], rax
0x180017fdc  jnz     short loc_180017FE2
0x180017fde  mov     [rcx+20h], rsi
0x180017fe2  cmp     [rcx+8], rbx
0x180017fe6  jnz     short loc_180017FEC
0x180017fe8  mov     [rcx+8], rsi
0x180017fec  mov     rcx, [rbx+0E8h]; Block
0x180017ff3  call    cs:__imp_free
0x180017ff9  mov     rcx, [rbx+0F0h]; Block
0x180018000  call    cs:__imp_free
0x180018006  mov     rcx, [rbx+108h]; Block
0x18001800d  call    cs:__imp_free
0x180018013  mov     rcx, [rbx+110h]; Block
0x18001801a  call    cs:__imp_free
0x180018020  mov     rcx, [rbx+118h]; Block
0x180018027  call    cs:__imp_free
0x18001802d  mov     [rbx+58h], rsi
0x180018031  mov     rcx, rbx; this
0x180018034  mov     rbx, [rsp+38h+arg_8]
0x180018039  add     rsp, 30h
0x18001803d  pop     rsi
0x18001803e  jmp     ??1CWinThread@@UEAA@XZ; CWinThread::~CWinThread(void)
0x180018043  mov     rax, [rcx]
0x180018046  mov     edx, 1
0x18001804b  mov     rax, [rax+8]
0x18001804f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018054  jmp     loc_180017F5E
0x180018059  mov     rax, [rcx]
0x18001805c  mov     edx, 1
0x180018061  mov     rax, [rax+28h]
0x180018065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001806a  jmp     loc_180017F6E
0x18001806f  mov     rcx, cs:?pStaticList@CDocManager@@2PEAVCPtrList@@EA; CPtrList * CDocManager::pStaticList
0x180018076  test    rcx, rcx
0x180018079  jz      short loc_180018093
0x18001807b  mov     rax, [rcx]
0x18001807e  mov     edx, 1
0x180018083  mov     rax, [rax+8]
0x180018087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001808c  mov     cs:?pStaticList@CDocManager@@2PEAVCPtrList@@EA, rsi; CPtrList * CDocManager::pStaticList
0x180018093  mov     rcx, cs:?pStaticDocManager@CDocManager@@2PEAV1@EA; CDocManager * CDocManager::pStaticDocManager
0x18001809a  test    rcx, rcx
0x18001809d  jz      loc_180017F7D
0x1800180a3  mov     rax, [rcx]
0x1800180a6  mov     edx, 1
0x1800180ab  mov     rax, [rax+8]
0x1800180af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180b4  mov     cs:?pStaticDocManager@CDocManager@@2PEAV1@EA, rsi; CDocManager * CDocManager::pStaticDocManager
0x1800180bb  jmp     loc_180017F7D
0x1800180c0  call    ?AfxGlobalFree@@YAXPEAX@Z; AfxGlobalFree(void *)
0x1800180c5  jmp     loc_180017F8D
0x1800180ca  call    ?AfxGlobalFree@@YAXPEAX@Z; AfxGlobalFree(void *)
0x1800180cf  jmp     loc_180017F9D
0x1800180d4  call    cs:__imp_GlobalDeleteAtom
0x1800180da  jmp     loc_180017FAD
0x1800180df  call    cs:__imp_GlobalDeleteAtom
0x1800180e5  jmp     loc_180017FBD
0x1800180ea  mov     rax, [rcx]
0x1800180ed  mov     edx, 1
0x1800180f2  mov     rax, [rax+8]
0x1800180f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180fb  jmp     loc_180017FCD
0x180018100  mov     rbx, [rsp+38h+arg_0]
0x180018105  jmp     loc_180018031
```
