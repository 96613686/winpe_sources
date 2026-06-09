# CComTypeLibraryRegistrationT<CEmptyType>::Register(int)

- ea: `0x180016078`
- end: `0x1800161a7`
- name: `?Register@?$CComTypeLibraryRegistrationT@VCEmptyType@@@@QEAAJH@Z`
- size: `303`
- prototype: `__int64 __fastcall(GUID *libID, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800178d8`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x1800142f8`
- `0x180016078`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016129`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016129`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001611a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001611a`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1800160c4`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1800160c4`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x1800160de`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x1800160de`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x18001617c`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x18001617c`

## pseudocode

```c
__int64 __fastcall CComTypeLibraryRegistrationT<CEmptyType>::Register(GUID *libID, int a2)
{
  int CurrentModuleFileName; // eax
  const OLECHAR *v5; // rbx
  HRESULT v6; // edi
  int v7; // ecx
  HANDLE ProcessHeap; // rax
  LPCOLESTR szFile[2]; // [rsp+30h] [rbp-10h] BYREF
  ITypeLib *pptlib; // [rsp+70h] [rbp+30h] BYREF
  __int64 v12; // [rsp+78h] [rbp+38h] BYREF

  szFile[0] = 0;
  pptlib = 0;
  v12 = 0;
  CurrentModuleFileName = CComHelpersT<CEmptyType>::GetCurrentModuleFileName(szFile);
  v5 = szFile[0];
  v6 = CurrentModuleFileName;
  if ( CurrentModuleFileName < 0 )
    goto LABEL_5;
  CurrentModuleFileName = LoadTypeLib(szFile[0], &pptlib);
  v6 = CurrentModuleFileName;
  if ( CurrentModuleFileName < 0 )
    goto LABEL_5;
  if ( a2 )
  {
    CurrentModuleFileName = RegisterTypeLib(pptlib, v5, 0);
    v6 = CurrentModuleFileName;
    if ( CurrentModuleFileName >= 0 )
      goto LABEL_7;
    goto LABEL_5;
  }
  CurrentModuleFileName = ((__int64 (__fastcall *)(ITypeLib *, __int64 *))pptlib->lpVtbl->GetLibAttr)(pptlib, &v12);
  v6 = CurrentModuleFileName;
  if ( CurrentModuleFileName < 0 )
  {
LABEL_5:
    v7 = CurrentModuleFileName;
LABEL_6:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_7;
  }
  v6 = UnRegisterTypeLib(
         libID,
         *(_WORD *)(v12 + 24),
         *(_WORD *)(v12 + 26),
         *(_DWORD *)(v12 + 16),
         *(SYSKIND *)(v12 + 20));
  ((void (__fastcall *)(ITypeLib *, __int64))pptlib->lpVtbl->ReleaseTLibAttr)(pptlib, v12);
  if ( v6 < 0 )
  {
    v7 = v6;
    goto LABEL_6;
  }
LABEL_7:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( pptlib )
  {
    ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
    pptlib = 0;
  }
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v5 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016078  mov     [rsp-18h+arg_0], rbx
0x18001607d  mov     [rsp-18h+arg_8], rsi
0x180016082  push    rbp
0x180016083  push    rdi
0x180016084  push    r14
0x180016086  mov     rbp, rsp
0x180016089  sub     rsp, 40h
0x18001608d  mov     r14, rcx
0x180016090  mov     [rbp+szFile], 0
0x180016098  lea     rcx, [rbp+szFile]
0x18001609c  mov     [rbp+pptlib], 0
0x1800160a4  mov     esi, edx
0x1800160a6  mov     [rbp+arg_18], 0
0x1800160ae  call    ?GetCurrentModuleFileName@?$CComHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CComHelpersT<CEmptyType>::GetCurrentModuleFileName(ushort * *)
0x1800160b3  mov     rbx, [rbp+szFile]
0x1800160b7  mov     edi, eax
0x1800160b9  test    eax, eax
0x1800160bb  js      short loc_1800160EA
0x1800160bd  lea     rdx, [rbp+pptlib]; pptlib
0x1800160c1  mov     rcx, rbx; szFile
0x1800160c4  call    cs:__imp_LoadTypeLib
0x1800160ca  mov     edi, eax
0x1800160cc  test    eax, eax
0x1800160ce  js      short loc_1800160EA
0x1800160d0  mov     rcx, [rbp+pptlib]; ptlib
0x1800160d4  test    esi, esi
0x1800160d6  jz      short loc_18001614B
0x1800160d8  xor     r8d, r8d; szHelpDir
0x1800160db  mov     rdx, rbx; szFullPath
0x1800160de  call    cs:__imp_RegisterTypeLib
0x1800160e4  mov     edi, eax
0x1800160e6  test    eax, eax
0x1800160e8  jns     short loc_1800160F1
0x1800160ea  mov     ecx, eax
0x1800160ec  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800160f1  mov     ecx, edi
0x1800160f3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800160f8  mov     rcx, [rbp+pptlib]
0x1800160fc  test    rcx, rcx
0x1800160ff  jz      short loc_180016115
0x180016101  mov     rax, [rcx]
0x180016104  mov     rax, [rax+10h]
0x180016108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001610d  mov     [rbp+pptlib], 0
0x180016115  test    rbx, rbx
0x180016118  jz      short loc_180016136
0x18001611a  call    cs:__imp_GetProcessHeap
0x180016120  lea     r8, [rbx-4]; lpMem
0x180016124  xor     edx, edx; dwFlags
0x180016126  mov     rcx, rax; hHeap
0x180016129  call    cs:__imp_HeapFree
0x18001612f  xor     ecx, ecx
0x180016131  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016136  mov     rbx, [rsp+40h+arg_0]
0x18001613b  mov     eax, edi
0x18001613d  mov     rsi, [rsp+40h+arg_8]
0x180016142  add     rsp, 40h
0x180016146  pop     r14
0x180016148  pop     rdi
0x180016149  pop     rbp
0x18001614a  retn
0x18001614b  mov     rax, [rcx]
0x18001614e  lea     rdx, [rbp+arg_18]
0x180016152  mov     rax, [rax+38h]
0x180016156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001615b  mov     edi, eax
0x18001615d  test    eax, eax
0x18001615f  js      short loc_1800160EA
0x180016161  mov     rdx, [rbp+arg_18]
0x180016165  mov     rcx, r14; libID
0x180016168  mov     eax, [rdx+14h]
0x18001616b  mov     r9d, [rdx+10h]; lcid
0x18001616f  movzx   r8d, word ptr [rdx+1Ah]; wVerMinor
0x180016174  movzx   edx, word ptr [rdx+18h]; wVerMajor
0x180016178  mov     [rsp+40h+syskind], eax; syskind
0x18001617c  call    cs:__imp_UnRegisterTypeLib
0x180016182  mov     rcx, [rbp+pptlib]
0x180016186  mov     edi, eax
0x180016188  mov     rdx, [rbp+arg_18]
0x18001618c  mov     rax, [rcx]
0x18001618f  mov     rax, [rax+60h]
0x180016193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016198  test    edi, edi
0x18001619a  jns     loc_1800160F1
0x1800161a0  mov     ecx, edi
0x1800161a2  jmp     loc_1800160EC
```
