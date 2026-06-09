# HrFillRasCombo

- ea: `0x18000d220`
- end: `0x18000d3e4`
- name: `HrFillRasCombo`
- size: `452`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001740`
- `0x18000d220`
- `0x180014010`

## import_xrefs

- `USER32!SendMessageA` at `0x18000d267`
- `USER32!SendMessageA` at `0x18000d39b`
- `USER32!SendMessageA` at `0x18000d267`
- `USER32!SendMessageA` at `0x18000d39b`
- `USER32!SendMessageW` at `0x18000d354`
- `USER32!SendMessageW` at `0x18000d36d`
- `USER32!SendMessageW` at `0x18000d387`
- `USER32!SendMessageW` at `0x18000d354`
- `USER32!SendMessageW` at `0x18000d36d`
- `USER32!SendMessageW` at `0x18000d387`
- `RASAPI32!RasEnumEntriesW` at `0x18000d2af`
- `RASAPI32!RasEnumEntriesW` at `0x18000d312`
- `RASAPI32!RasEnumEntriesW` at `0x18000d2af`
- `RASAPI32!RasEnumEntriesW` at `0x18000d312`

## pseudocode

```c
__int64 __fastcall HrFillRasCombo(HWND hWnd, int a2, DWORD *a3)
{
  int v6; // esi
  struct tagRASENTRYNAMEW *v7; // rbx
  struct tagRASENTRYNAMEW *v8; // r8
  DWORD v9; // eax
  struct tagRASENTRYNAMEW *v10; // r8
  DWORD i; // edi
  __int64 v12; // rcx
  struct tagRASENTRYNAMEW *v13; // r12
  int v14; // eax
  struct tagRASENTRYNAMEW *v16[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD v17; // [rsp+78h] [rbp+38h] BYREF
  DWORD v18; // [rsp+88h] [rbp+48h] BYREF

  v16[0] = 0;
  v18 = 0;
  v17 = 0;
  if ( !a2 )
    SendMessageA(hWnd, 0x14Bu, 0, 0);
  v18 = 1048;
  v6 = HrAlloc((void **)v16, 0x418u);
  if ( v6 < 0 )
    goto LABEL_18;
  v7 = v16[0];
  v8 = v16[0];
  v16[0]->dwSize = 1048;
  v17 = 0;
  v9 = RasEnumEntriesW(0, 0, v8, &v18, &v17);
  if ( v9 != 603 )
    goto LABEL_7;
  ((void (__fastcall *)(LPMALLOC, struct tagRASENTRYNAMEW *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v7);
  v16[0] = 0;
  v6 = HrAlloc((void **)v16, v18);
  if ( v6 < 0 )
  {
LABEL_18:
    v7 = v16[0];
    goto LABEL_19;
  }
  v7 = v16[0];
  v10 = v16[0];
  v16[0]->dwSize = 1048;
  v17 = 0;
  v9 = RasEnumEntriesW(0, 0, v10, &v18, &v17);
LABEL_7:
  if ( v9 )
  {
    if ( a3 )
      *a3 = v9;
    v6 = -2146644796;
  }
  else
  {
    for ( i = 0; i < v17; ++i )
    {
      v12 = i;
      if ( a2 )
      {
        v13 = &v7[v12];
        if ( (int)SendMessageW(hWnd, 0x158u, 0, (LPARAM)v7[v12].szEntryName) < 0 )
        {
          v14 = SendMessageW(hWnd, 0x143u, 0, (LPARAM)v13->szEntryName);
          SendMessageA(hWnd, 0x14Eu, v14, 0);
        }
      }
      else
      {
        SendMessageW(hWnd, 0x143u, 0, (LPARAM)v7[v12].szEntryName);
      }
    }
  }
LABEL_19:
  if ( v7 )
    ((void (__fastcall *)(LPMALLOC, struct tagRASENTRYNAMEW *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000d220  mov     [rsp-28h+arg_0], rbx
0x18000d225  mov     [rsp-28h+arg_10], rsi
0x18000d22a  push    rbp
0x18000d22b  push    rdi
0x18000d22c  push    r12
0x18000d22e  push    r14
0x18000d230  push    r15
0x18000d232  mov     rbp, rsp
0x18000d235  sub     rsp, 40h
0x18000d239  mov     [rbp+var_10], 0
0x18000d241  mov     rdi, r8
0x18000d244  mov     [rbp+arg_18], 0
0x18000d24b  mov     r15d, edx
0x18000d24e  mov     [rbp+arg_8], 0
0x18000d255  mov     r14, rcx
0x18000d258  test    edx, edx
0x18000d25a  jnz     short loc_18000D26D
0x18000d25c  xor     r9d, r9d; lParam
0x18000d25f  xor     r8d, r8d; wParam
0x18000d262  mov     edx, 14Bh; Msg
0x18000d267  call    cs:__imp_SendMessageA
0x18000d26d  mov     r12d, 418h
0x18000d273  lea     rcx, [rbp+var_10]; void **
0x18000d277  mov     edx, r12d; unsigned int
0x18000d27a  mov     [rbp+arg_18], r12d
0x18000d27e  call    ?HrAlloc@@YAJPEAPEAXK@Z; HrAlloc(void * *,ulong)
0x18000d283  mov     esi, eax
0x18000d285  test    eax, eax
0x18000d287  js      loc_18000D3AA
0x18000d28d  mov     rbx, [rbp+var_10]
0x18000d291  lea     rax, [rbp+arg_8]
0x18000d295  lea     r9, [rbp+arg_18]; LPDWORD
0x18000d299  mov     [rsp+40h+var_20], rax; LPDWORD
0x18000d29e  mov     r8, rbx; struct tagRASENTRYNAMEW *
0x18000d2a1  xor     edx, edx; LPCWSTR
0x18000d2a3  xor     ecx, ecx; LPCWSTR
0x18000d2a5  mov     [rbx], r12d
0x18000d2a8  mov     [rbp+arg_8], 0
0x18000d2af  call    cs:__imp_RasEnumEntriesW
0x18000d2b5  cmp     eax, 25Bh
0x18000d2ba  jnz     short loc_18000D318
0x18000d2bc  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000d2c3  mov     rdx, rbx
0x18000d2c6  mov     rax, [rcx]
0x18000d2c9  mov     rax, [rax+28h]
0x18000d2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2d2  mov     edx, [rbp+arg_18]; unsigned int
0x18000d2d5  lea     rcx, [rbp+var_10]; void **
0x18000d2d9  mov     [rbp+var_10], 0
0x18000d2e1  call    ?HrAlloc@@YAJPEAPEAXK@Z; HrAlloc(void * *,ulong)
0x18000d2e6  mov     esi, eax
0x18000d2e8  test    eax, eax
0x18000d2ea  js      loc_18000D3AA
0x18000d2f0  mov     rbx, [rbp+var_10]
0x18000d2f4  lea     rax, [rbp+arg_8]
0x18000d2f8  lea     r9, [rbp+arg_18]; LPDWORD
0x18000d2fc  mov     [rsp+40h+var_20], rax; LPDWORD
0x18000d301  mov     r8, rbx; struct tagRASENTRYNAMEW *
0x18000d304  xor     edx, edx; LPCWSTR
0x18000d306  xor     ecx, ecx; LPCWSTR
0x18000d308  mov     [rbx], r12d
0x18000d30b  mov     [rbp+arg_8], 0
0x18000d312  call    cs:__imp_RasEnumEntriesW
0x18000d318  test    eax, eax
0x18000d31a  jz      short loc_18000D32D
0x18000d31c  test    rdi, rdi
0x18000d31f  jz      short loc_18000D323
0x18000d321  mov     [rdi], eax
0x18000d323  mov     esi, 800CCCC4h
0x18000d328  jmp     loc_18000D3AE
0x18000d32d  xor     edi, edi
0x18000d32f  cmp     [rbp+arg_8], edi
0x18000d332  jbe     short loc_18000D3AE
0x18000d334  mov     eax, edi
0x18000d336  xor     r8d, r8d; wParam
0x18000d339  imul    rcx, rax, 418h
0x18000d340  test    r15d, r15d
0x18000d343  jnz     short loc_18000D35C
0x18000d345  lea     r9, [rcx+4]
0x18000d349  mov     edx, 143h; Msg
0x18000d34e  add     r9, rbx; lParam
0x18000d351  mov     rcx, r14; hWnd
0x18000d354  call    cs:__imp_SendMessageW
0x18000d35a  jmp     short loc_18000D3A1
0x18000d35c  lea     r12, [rcx+rbx]
0x18000d360  mov     edx, 158h; Msg
0x18000d365  lea     r9, [r12+4]; lParam
0x18000d36a  mov     rcx, r14; hWnd
0x18000d36d  call    cs:__imp_SendMessageW
0x18000d373  test    eax, eax
0x18000d375  jns     short loc_18000D3A1
0x18000d377  lea     r9, [r12+4]; lParam
0x18000d37c  xor     r8d, r8d; wParam
0x18000d37f  mov     edx, 143h; Msg
0x18000d384  mov     rcx, r14; hWnd
0x18000d387  call    cs:__imp_SendMessageW
0x18000d38d  movsxd  r8, eax; wParam
0x18000d390  xor     r9d, r9d; lParam
0x18000d393  mov     edx, 14Eh; Msg
0x18000d398  mov     rcx, r14; hWnd
0x18000d39b  call    cs:__imp_SendMessageA
0x18000d3a1  inc     edi
0x18000d3a3  cmp     edi, [rbp+arg_8]
0x18000d3a6  jb      short loc_18000D334
0x18000d3a8  jmp     short loc_18000D3AE
0x18000d3aa  mov     rbx, [rbp+var_10]
0x18000d3ae  test    rbx, rbx
0x18000d3b1  jz      short loc_18000D3C9
0x18000d3b3  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000d3ba  mov     rdx, rbx
0x18000d3bd  mov     rax, [rcx]
0x18000d3c0  mov     rax, [rax+28h]
0x18000d3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3c9  lea     r11, [rsp+40h+var_s0]
0x18000d3ce  mov     eax, esi
0x18000d3d0  mov     rbx, [r11+30h]
0x18000d3d4  mov     rsi, [r11+40h]
0x18000d3d8  mov     rsp, r11
0x18000d3db  pop     r15
0x18000d3dd  pop     r14
0x18000d3df  pop     r12
0x18000d3e1  pop     rdi
0x18000d3e2  pop     rbp
0x18000d3e3  retn
```
