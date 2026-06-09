# ConfirmCannotResolveConflict(HWND__ *,long,ISyncMgrConflict *,ISyncMgrConflictResolveInfo *,ISyncMgrResolutionHandler *,bool *,bool *)

- ea: `0x18004833c`
- end: `0x1800484b2`
- name: `?ConfirmCannotResolveConflict@@YAJPEAUHWND__@@JPEAUISyncMgrConflict@@PEAUISyncMgrConflictResolveInfo@@PEAUISyncMgrResolutionHandler@@PEA_N4@Z`
- size: `374`
- prototype: `__int64 __fastcall(HWND, int, struct ISyncMgrConflict *, struct ISyncMgrConflictResolveInfo *, struct ISyncMgrResolutionHandler *, bool *, bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180037bf0`
- `0x18004863c`

## callees

- `0x1800133b0`
- `0x1800134dc`
- `0x18004833c`
- `0x1800484b8`
- `0x180048924`
- `0x180048a40`
- `0x180048bb8`
- `0x18005292a`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180048441`
- `SHELL32!__imp_ILFree` at `0x180048441`
- `SHLWAPI!__imp_SHInvokeCommand` at `0x180048436`
- `SHLWAPI!__imp_SHInvokeCommand` at `0x180048436`

## string_xrefs

- `0x180048428`: `delete`

## pseudocode

```c
__int64 __fastcall ConfirmCannotResolveConflict(
        HWND a1,
        int a2,
        struct ISyncMgrConflict *a3,
        struct ISyncMgrConflictResolveInfo *a4,
        struct ISyncMgrResolutionHandler *a5,
        bool *a6,
        bool *a7)
{
  __int64 v11; // rcx
  __int64 v12; // r8
  unsigned int v13; // esi
  int ConflictShellItem; // ebx
  int v15; // eax
  int v16; // ecx
  int v17; // r9d
  int v19; // [rsp+30h] [rbp-91h] BYREF
  int v20; // [rsp+34h] [rbp-8Dh] BYREF
  LPITEMIDLIST pidl; // [rsp+38h] [rbp-89h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-81h] BYREF
  _BYTE v23[12]; // [rsp+50h] [rbp-71h] BYREF
  __int128 v24; // [rsp+5Ch] [rbp-65h]
  __int64 v25; // [rsp+78h] [rbp-49h] BYREF
  int v26; // [rsp+88h] [rbp-39h]
  HWND v27; // [rsp+A0h] [rbp-21h]

  memset_0(v23, 0, 0x60u);
  v27 = a1;
  v26 = a2;
  v24 = STCONFIRM_CONFLICT_RESOLVE;
  v13 = 0;
  ConflictShellItem = GetConflictShellItem(v11, a3, v12, &v25);
  if ( ConflictShellItem < 0 )
    goto LABEL_13;
  v19 = 0;
  v20 = 0;
  ConflictShellItem = InvokeConfirmation(v23, &v19, &v20);
  if ( ConflictShellItem >= 0 )
  {
    v15 = v19;
    ConflictShellItem = 0;
    *a6 = 0;
    *a7 = 0;
    if ( v15 )
    {
      if ( v15 == 2 )
      {
        *a7 = 1;
      }
      else if ( v15 == 4 )
      {
        v13 = 2;
      }
    }
    else
    {
      ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(v22);
      pidl = 0;
      if ( (int)GetConflictIDListAndParent(v16, (_DWORD)a3, (unsigned int)&pidl, v17, (__int64)v22) >= 0 )
      {
        SHInvokeCommand(0, v22[0], pidl, "delete");
        ILFree(pidl);
      }
      ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(v22);
    }
    ((void (__fastcall *)(struct ISyncMgrConflictResolveInfo *, _QWORD))a4->lpVtbl->SetPresenterNextStep)(a4, v13);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( ConflictShellItem < 0 )
  {
LABEL_13:
    *a7 = 0;
    *a6 = 0;
    return (unsigned int)ConfirmConflictMissing(a1, ConflictShellItem, a3, a4);
  }
  return (unsigned int)ConflictShellItem;
}

```

## disassembly

```asm
0x18004833c  push    rbp
0x18004833e  push    rbx
0x18004833f  push    rsi
0x180048340  push    rdi
0x180048341  push    r12
0x180048343  push    r13
0x180048345  push    r14
0x180048347  push    r15
0x180048349  lea     rbp, [rsp-7]
0x18004834e  sub     rsp, 0C8h
0x180048355  mov     rax, cs:__security_cookie
0x18004835c  xor     rax, rsp
0x18004835f  mov     [rbp+3Fh+var_50], rax
0x180048363  mov     r15, [rbp+3Fh+arg_28]
0x180048367  mov     ebx, edx
0x180048369  mov     rdi, [rbp+3Fh+arg_30]
0x18004836d  xor     edx, edx; Val
0x18004836f  mov     r12, r8
0x180048372  mov     r13, rcx
0x180048375  lea     rcx, [rbp+3Fh+var_B0]; void *
0x180048379  mov     r14, r9
0x18004837c  lea     r8d, [rdx+60h]; Size
0x180048380  call    memset_0
0x180048385  movups  xmm0, cs:STCONFIRM_CONFLICT_RESOLVE
0x18004838c  lea     r9, [rbp+3Fh+var_88]
0x180048390  mov     [rbp+3Fh+var_60], r13
0x180048394  mov     rdx, r12
0x180048397  mov     [rbp+3Fh+var_78], ebx
0x18004839a  movdqu  [rbp+3Fh+var_A4], xmm0
0x18004839f  call    _GetConflictShellItem
0x1800483a4  xor     esi, esi
0x1800483a6  mov     ebx, eax
0x1800483a8  test    eax, eax
0x1800483aa  js      loc_180048478
0x1800483b0  lea     r8, [rsp+100h+var_CC]
0x1800483b5  mov     [rsp+100h+var_D0], esi
0x1800483b9  lea     rdx, [rsp+100h+var_D0]
0x1800483be  mov     [rsp+100h+var_CC], esi
0x1800483c2  lea     rcx, [rbp+3Fh+var_B0]
0x1800483c6  call    _InvokeConfirmation
0x1800483cb  mov     ebx, eax
0x1800483cd  test    eax, eax
0x1800483cf  js      loc_180048464
0x1800483d5  mov     eax, [rsp+100h+var_D0]
0x1800483d9  mov     ebx, esi
0x1800483db  mov     [r15], sil
0x1800483de  mov     [rdi], sil
0x1800483e1  test    eax, eax
0x1800483e3  jz      short loc_1800483F9
0x1800483e5  cmp     eax, 2
0x1800483e8  jz      short loc_1800483F4
0x1800483ea  cmp     eax, 4
0x1800483ed  jnz     short loc_180048451
0x1800483ef  lea     esi, [rax-2]
0x1800483f2  jmp     short loc_180048451
0x1800483f4  mov     byte ptr [rdi], 1
0x1800483f7  jmp     short loc_180048451
0x1800483f9  lea     rcx, [rsp+100h+var_C0]; void *
0x1800483fe  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x180048403  lea     rax, [rsp+100h+var_C0]
0x180048408  mov     [rsp+100h+pidl], rbx
0x18004840d  lea     r8, [rsp+100h+pidl]
0x180048412  mov     [rsp+100h+var_E0], rax
0x180048417  mov     rdx, r12
0x18004841a  call    _GetConflictIDListAndParent
0x18004841f  test    eax, eax
0x180048421  js      short loc_180048447
0x180048423  mov     r8, [rsp+100h+pidl]
0x180048428  lea     r9, aDelete_0; "delete"
0x18004842f  mov     rdx, [rsp+100h+var_C0]
0x180048434  xor     ecx, ecx
0x180048436  call    cs:__imp_SHInvokeCommand
0x18004843c  mov     rcx, [rsp+100h+pidl]; pidl
0x180048441  call    cs:__imp_ILFree
0x180048447  lea     rcx, [rsp+100h+var_C0]
0x18004844c  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x180048451  mov     rax, [r14]
0x180048454  mov     edx, esi
0x180048456  mov     rcx, r14
0x180048459  mov     rax, [rax+40h]
0x18004845d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048462  xor     esi, esi
0x180048464  mov     rcx, [rbp+3Fh+var_88]
0x180048468  mov     rax, [rcx]
0x18004846b  mov     rax, [rax+10h]
0x18004846f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048474  test    ebx, ebx
0x180048476  jns     short loc_180048490
0x180048478  mov     [rdi], sil
0x18004847b  mov     r9, r14; struct ISyncMgrConflictResolveInfo *
0x18004847e  mov     r8, r12; struct ISyncMgrConflict *
0x180048481  mov     [r15], sil
0x180048484  mov     edx, ebx; int
0x180048486  mov     rcx, r13; HWND
0x180048489  call    ?ConfirmConflictMissing@@YAJPEAUHWND__@@JPEAUISyncMgrConflict@@PEAUISyncMgrConflictResolveInfo@@@Z; ConfirmConflictMissing(HWND__ *,long,ISyncMgrConflict *,ISyncMgrConflictResolveInfo *)
0x18004848e  mov     ebx, eax
0x180048490  mov     eax, ebx
0x180048492  mov     rcx, [rbp+3Fh+var_50]
0x180048496  xor     rcx, rsp; StackCookie
0x180048499  call    __security_check_cookie
0x18004849e  add     rsp, 0C8h
0x1800484a5  pop     r15
0x1800484a7  pop     r14
0x1800484a9  pop     r13
0x1800484ab  pop     r12
0x1800484ad  pop     rdi
0x1800484ae  pop     rsi
0x1800484af  pop     rbx
0x1800484b0  pop     rbp
0x1800484b1  retn
```
