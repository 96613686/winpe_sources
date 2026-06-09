# SHBeginLabelEdit

- ea: `0x1801ff588`
- end: `0x1801ff852`
- name: `SHBeginLabelEdit`
- size: `714`
- prototype: `__int64 __fastcall(IShellFolder *psfParent, LPCITEMIDLIST pidl, HWND hWnd)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1801b8330`

## callees

- `0x1801ff588`
- `0x180210010`

## import_xrefs

- `SHELL32!SHCreateItemWithParent` at `0x1801ff5d6`
- `SHELL32!SHCreateItemWithParent` at `0x1801ff5d6`
- `SHELL32!__imp_SHLimitInputEdit` at `0x1801ff79d`
- `SHELL32!__imp_SHLimitInputEdit` at `0x1801ff79d`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ff688`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ff6f2`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ff688`
- `SHLWAPI!__imp_StrCmpICW` at `0x1801ff6f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ff705`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ff7df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ff7e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ff705`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ff7df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ff7e9`
- `USER32!SendMessageW` at `0x1801ff719`
- `USER32!SendMessageW` at `0x1801ff80a`
- `USER32!SendMessageW` at `0x1801ff821`
- `USER32!SendMessageW` at `0x1801ff719`
- `USER32!SendMessageW` at `0x1801ff80a`
- `USER32!SendMessageW` at `0x1801ff821`
- `USER32!SetWindowTextW` at `0x1801ff667`
- `USER32!SetWindowTextW` at `0x1801ff667`

## pseudocode

```c
__int64 __fastcall SHBeginLabelEdit(IShellFolder *psfParent, LPCITEMIDLIST pidl, HWND hWnd, int a4)
{
  unsigned int v6; // r12d
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rdi
  WCHAR *v9; // rdx
  int v10; // eax
  struct IShellFolderVtbl *lpVtbl; // rax
  int v12; // ecx
  int v14; // [rsp+40h] [rbp-30h] BYREF
  void *ppvItem; // [rsp+48h] [rbp-28h] BYREF
  __int64 v16; // [rsp+50h] [rbp-20h] BYREF
  LPCWSTR pszStr1; // [rsp+58h] [rbp-18h] BYREF
  LPCWSTR lpString; // [rsp+60h] [rbp-10h] BYREF
  LPCWSTR pszStr2; // [rsp+68h] [rbp-8h] BYREF
  LPCITEMIDLIST v20; // [rsp+B8h] [rbp+48h] BYREF
  int v21; // [rsp+C8h] [rbp+58h] BYREF

  v21 = a4;
  v20 = pidl;
  v14 = 0;
  ppvItem = 0;
  v6 = 1;
  if ( SHCreateItemWithParent(0, psfParent, pidl, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppvItem) >= 0 )
  {
    v21 = 0;
    if ( (*(int (__fastcall **)(void *, __int64, int *))(*(_QWORD *)ppvItem + 48LL))(ppvItem, 541065232, &v21) >= 0
      && (v21 & 0x10) != 0 )
    {
      lpString = 0;
      v6 = 0;
      if ( (*(int (__fastcall **)(void *, __int64, LPCWSTR *))(*(_QWORD *)ppvItem + 40LL))(
             ppvItem,
             2147684353LL,
             &lpString) >= 0 )
      {
        pszStr1 = 0;
        if ( (*(int (__fastcall **)(void *, __int64, LPCWSTR *))(*(_QWORD *)ppvItem + 40LL))(
               ppvItem,
               2147581953LL,
               &pszStr1) >= 0 )
        {
          SetWindowTextW(hWnd, lpString);
          if ( (v21 & 0x20400000) != 0x20000000 && !StrCmpICW(pszStr1, lpString) )
          {
            v7 = -1;
            v8 = -1;
            do
              ++v8;
            while ( lpString[v8] );
            pszStr2 = 0;
            if ( (*(int (__fastcall **)(void *, const PROPERTYKEY *, LPCWSTR *))(*(_QWORD *)ppvItem + 136LL))(
                   ppvItem,
                   &PKEY_FileExtension,
                   &pszStr2) >= 0 )
            {
              v9 = (WCHAR *)pszStr2;
              do
                ++v7;
              while ( pszStr2[v7] );
              if ( v7 < v8 )
              {
                v10 = StrCmpICW(&pszStr1[v8 - v7], pszStr2);
                v9 = (WCHAR *)pszStr2;
                if ( !v10 )
                  v8 -= v7;
              }
              CoTaskMemFree(v9);
            }
            SendMessageW(hWnd, 0xB1u, 0, v8);
          }
          lpVtbl = psfParent->lpVtbl;
          v16 = 0;
          if ( ((int (__fastcall *)(IShellFolder *, _QWORD, __int64, LPCITEMIDLIST *, GUID *, _QWORD, __int64 *))lpVtbl->GetUIObjectOf)(
                 psfParent,
                 0,
                 1,
                 &v20,
                 &GUID_1df0d7f1_b267_4d28_8b10_12e23202a5c4,
                 0,
                 &v16) < 0 )
            ((void (__fastcall *)(IShellFolder *, GUID *, __int64 *))psfParent->lpVtbl->QueryInterface)(
              psfParent,
              &GUID_1df0d7f1_b267_4d28_8b10_12e23202a5c4,
              &v16);
          if ( v16 )
          {
            pszStr2 = 0;
            if ( (**(int (__fastcall ***)(__int64, GUID *, LPCWSTR *))v16)(
                   v16,
                   &GUID_000214e6_0000_0000_c000_000000000046,
                   &pszStr2) >= 0 )
            {
              SHLimitInputEdit(hWnd, (IShellFolder *)pszStr2);
              (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)pszStr2 + 16LL))(pszStr2);
            }
            (*(void (__fastcall **)(__int64, LPCWSTR, int *))(*(_QWORD *)v16 + 32LL))(v16, pszStr1, &v14);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
          CoTaskMemFree((LPVOID)pszStr1);
        }
        CoTaskMemFree((LPVOID)lpString);
      }
      v12 = 128;
      if ( v14 )
        v12 = v14;
      SendMessageW(hWnd, 0xC5u, v12, 0);
      SendMessageW(hWnd, 0x150Au, 8u, 8);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvItem + 16LL))(ppvItem);
  }
  return v6;
}

```

## disassembly

```asm
0x1801ff588  mov     [rsp-38h+arg_0], rbx
0x1801ff58d  mov     [rsp-38h+arg_18], r9d
0x1801ff592  mov     [rsp-38h+arg_8], rdx
0x1801ff597  push    rbp
0x1801ff598  push    rsi
0x1801ff599  push    rdi
0x1801ff59a  push    r12
0x1801ff59c  push    r13
0x1801ff59e  push    r14
0x1801ff5a0  push    r15
0x1801ff5a2  mov     rbp, rsp
0x1801ff5a5  sub     rsp, 70h
0x1801ff5a9  xor     r13d, r13d
0x1801ff5ac  lea     rax, [rbp+var_28]
0x1801ff5b0  mov     r14, r8
0x1801ff5b3  mov     [rbp+var_30], r13d
0x1801ff5b7  mov     r8, rdx; pidl
0x1801ff5ba  mov     [rbp+var_28], r13
0x1801ff5be  mov     r15, rcx
0x1801ff5c1  mov     [rsp+70h+ppvItem], rax; ppvItem
0x1801ff5c6  mov     rdx, rcx; psfParent
0x1801ff5c9  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1801ff5d0  xor     ecx, ecx; pidlParent
0x1801ff5d2  lea     r12d, [r13+1]
0x1801ff5d6  call    cs:__imp_SHCreateItemWithParent
0x1801ff5dc  test    eax, eax
0x1801ff5de  js      loc_1801FF837
0x1801ff5e4  mov     rcx, [rbp+var_28]
0x1801ff5e8  lea     r8, [rbp+arg_18]
0x1801ff5ec  mov     [rbp+arg_18], r13d
0x1801ff5f0  mov     edx, 20400010h
0x1801ff5f5  mov     rax, [rcx]
0x1801ff5f8  mov     rax, [rax+30h]
0x1801ff5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff601  test    eax, eax
0x1801ff603  js      loc_1801FF827
0x1801ff609  test    byte ptr [rbp+arg_18], 10h
0x1801ff60d  jz      loc_1801FF827
0x1801ff613  mov     rcx, [rbp+var_28]
0x1801ff617  lea     r8, [rbp+lpString]
0x1801ff61b  mov     [rbp+lpString], r13
0x1801ff61f  mov     edx, 80031001h
0x1801ff624  mov     r12d, r13d
0x1801ff627  mov     rax, [rcx]
0x1801ff62a  mov     rax, [rax+28h]
0x1801ff62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff633  test    eax, eax
0x1801ff635  js      loc_1801FF7EF
0x1801ff63b  mov     rcx, [rbp+var_28]
0x1801ff63f  lea     r8, [rbp+pszStr1]
0x1801ff643  mov     [rbp+pszStr1], r13
0x1801ff647  mov     edx, 80018001h
0x1801ff64c  mov     rax, [rcx]
0x1801ff64f  mov     rax, [rax+28h]
0x1801ff653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff658  test    eax, eax
0x1801ff65a  js      loc_1801FF7E5
0x1801ff660  mov     rdx, [rbp+lpString]; lpString
0x1801ff664  mov     rcx, r14; hWnd
0x1801ff667  call    cs:__imp_SetWindowTextW
0x1801ff66d  mov     eax, [rbp+arg_18]
0x1801ff670  and     eax, 20400000h
0x1801ff675  cmp     eax, 20000000h
0x1801ff67a  jz      loc_1801FF71F
0x1801ff680  mov     rdx, [rbp+lpString]; pszStr2
0x1801ff684  mov     rcx, [rbp+pszStr1]; pszStr1
0x1801ff688  call    cs:__imp_StrCmpICW
0x1801ff68e  test    eax, eax
0x1801ff690  jnz     loc_1801FF71F
0x1801ff696  mov     rax, [rbp+lpString]
0x1801ff69a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801ff69e  mov     rdi, rsi
0x1801ff6a1  inc     rdi
0x1801ff6a4  cmp     [rax+rdi*2], r13w
0x1801ff6a9  jnz     short loc_1801FF6A1
0x1801ff6ab  mov     rcx, [rbp+var_28]
0x1801ff6af  lea     r8, [rbp+pszStr2]
0x1801ff6b3  mov     [rbp+pszStr2], r13
0x1801ff6b7  lea     rdx, PKEY_FileExtension
0x1801ff6be  mov     rax, [rcx]
0x1801ff6c1  mov     rax, [rax+88h]
0x1801ff6c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff6cd  test    eax, eax
0x1801ff6cf  js      short loc_1801FF70B
0x1801ff6d1  mov     rdx, [rbp+pszStr2]; pszStr2
0x1801ff6d5  inc     rsi
0x1801ff6d8  cmp     [rdx+rsi*2], r13w
0x1801ff6dd  jnz     short loc_1801FF6D5
0x1801ff6df  cmp     rsi, rdi
0x1801ff6e2  jnb     short loc_1801FF702
0x1801ff6e4  mov     rax, [rbp+pszStr1]
0x1801ff6e8  mov     rbx, rdi
0x1801ff6eb  sub     rbx, rsi
0x1801ff6ee  lea     rcx, [rax+rbx*2]; pszStr1
0x1801ff6f2  call    cs:__imp_StrCmpICW
0x1801ff6f8  mov     rdx, [rbp+pszStr2]
0x1801ff6fc  test    eax, eax
0x1801ff6fe  cmovz   rdi, rbx
0x1801ff702  mov     rcx, rdx; pv
0x1801ff705  call    cs:__imp_CoTaskMemFree
0x1801ff70b  mov     r9, rdi; lParam
0x1801ff70e  xor     r8d, r8d; wParam
0x1801ff711  mov     edx, 0B1h; Msg
0x1801ff716  mov     rcx, r14; hWnd
0x1801ff719  call    cs:__imp_SendMessageW
0x1801ff71f  mov     rax, [r15]
0x1801ff722  lea     rcx, [rbp+var_20]
0x1801ff726  mov     [rsp+70h+var_40], rcx
0x1801ff72b  lea     rbx, _GUID_1df0d7f1_b267_4d28_8b10_12e23202a5c4
0x1801ff732  xor     edx, edx
0x1801ff734  mov     [rsp+70h+var_48], r13
0x1801ff739  lea     r9, [rbp+arg_8]
0x1801ff73d  mov     [rbp+var_20], r13
0x1801ff741  mov     rax, [rax+50h]
0x1801ff745  mov     rcx, r15
0x1801ff748  mov     [rsp+70h+ppvItem], rbx
0x1801ff74d  lea     r8d, [rdx+1]
0x1801ff751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff756  test    eax, eax
0x1801ff758  jns     short loc_1801FF76F
0x1801ff75a  mov     rax, [r15]
0x1801ff75d  lea     r8, [rbp+var_20]
0x1801ff761  mov     rdx, rbx
0x1801ff764  mov     rcx, r15
0x1801ff767  mov     rax, [rax]
0x1801ff76a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff76f  mov     rcx, [rbp+var_20]
0x1801ff773  test    rcx, rcx
0x1801ff776  jz      short loc_1801FF7DB
0x1801ff778  mov     [rbp+pszStr2], r13
0x1801ff77c  lea     r8, [rbp+pszStr2]
0x1801ff780  mov     rax, [rcx]
0x1801ff783  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x1801ff78a  mov     rax, [rax]
0x1801ff78d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff792  test    eax, eax
0x1801ff794  js      short loc_1801FF7B3
0x1801ff796  mov     rdx, [rbp+pszStr2]; psf
0x1801ff79a  mov     rcx, r14; hwndEdit
0x1801ff79d  call    cs:__imp_SHLimitInputEdit
0x1801ff7a3  mov     rcx, [rbp+pszStr2]
0x1801ff7a7  mov     rax, [rcx]
0x1801ff7aa  mov     rax, [rax+10h]
0x1801ff7ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff7b3  mov     rcx, [rbp+var_20]
0x1801ff7b7  lea     r8, [rbp+var_30]
0x1801ff7bb  mov     rdx, [rbp+pszStr1]
0x1801ff7bf  mov     rax, [rcx]
0x1801ff7c2  mov     rax, [rax+20h]
0x1801ff7c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff7cb  mov     rcx, [rbp+var_20]
0x1801ff7cf  mov     rax, [rcx]
0x1801ff7d2  mov     rax, [rax+10h]
0x1801ff7d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff7db  mov     rcx, [rbp+pszStr1]; pv
0x1801ff7df  call    cs:__imp_CoTaskMemFree
0x1801ff7e5  mov     rcx, [rbp+lpString]; pv
0x1801ff7e9  call    cs:__imp_CoTaskMemFree
0x1801ff7ef  mov     eax, [rbp+var_30]
0x1801ff7f2  mov     ecx, 80h
0x1801ff7f7  test    eax, eax
0x1801ff7f9  mov     edx, 0C5h; Msg
0x1801ff7fe  cmovnz  ecx, eax
0x1801ff801  xor     r9d, r9d; lParam
0x1801ff804  movsxd  r8, ecx; wParam
0x1801ff807  mov     rcx, r14; hWnd
0x1801ff80a  call    cs:__imp_SendMessageW
0x1801ff810  mov     r8d, 8; wParam
0x1801ff816  mov     edx, 150Ah; Msg
0x1801ff81b  mov     r9d, r8d; lParam
0x1801ff81e  mov     rcx, r14; hWnd
0x1801ff821  call    cs:__imp_SendMessageW
0x1801ff827  mov     rcx, [rbp+var_28]
0x1801ff82b  mov     rdx, [rcx]
0x1801ff82e  mov     rax, [rdx+10h]
0x1801ff832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff837  mov     rbx, [rsp+70h+arg_0]
0x1801ff83f  mov     eax, r12d
0x1801ff842  add     rsp, 70h
0x1801ff846  pop     r15
0x1801ff848  pop     r14
0x1801ff84a  pop     r13
0x1801ff84c  pop     r12
0x1801ff84e  pop     rdi
0x1801ff84f  pop     rsi
0x1801ff850  pop     rbp
0x1801ff851  retn
```
