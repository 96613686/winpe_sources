# PerflibciOpenLocalQueryHandle

- ea: `0x1800045d0`
- end: `0x18000478f`
- name: `PerflibciOpenLocalQueryHandle`
- size: `447`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004290`
- `0x18000c6f0`

## callees

- `0x180002e84`
- `0x1800045d0`
- `0x180004798`
- `0x18004165c`
- `0x18007205a`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800046f8`
- `KERNEL32!LocalFree` at `0x18000474c`
- `KERNEL32!LocalFree` at `0x18000476e`
- `KERNEL32!LocalFree` at `0x1800046f8`
- `KERNEL32!LocalFree` at `0x18000474c`
- `KERNEL32!LocalFree` at `0x18000476e`
- `KERNEL32!GetLastError` at `0x18000475d`
- `KERNEL32!GetLastError` at `0x18000475d`
- `KERNEL32!GetComputerNameW` at `0x180004681`
- `KERNEL32!GetComputerNameW` at `0x180004681`
- `KERNEL32!CreateMutexW` at `0x1800046bb`
- `KERNEL32!CreateMutexW` at `0x1800046bb`

## pseudocode

```c
__int64 __fastcall PerflibciOpenLocalQueryHandle(unsigned __int16 *a1, char a2, _QWORD *a3)
{
  __int64 v6; // rdi
  char v7; // bp
  int v8; // eax
  unsigned __int64 v9; // r15
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  WCHAR *v12; // rcx
  HANDLE MutexW; // rax
  DWORD LastError; // edi
  __int64 v16; // rax
  __int64 v17; // rdx
  DWORD nSize; // [rsp+80h] [rbp+18h] BYREF

  if ( !a3 )
  {
    v11 = 0;
    LastError = 87;
    goto LABEL_13;
  }
  v6 = -1;
  *a3 = 0;
  v7 = 1;
  if ( a1 && *a1 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a1[v16] );
    v8 = v16 + 1;
    v7 = 0;
  }
  else
  {
    v8 = 261;
  }
  v9 = 2 * ((v8 + 7) & 0xFFFFFFF8) + 96;
  v10 = operator new(v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( !v10 )
    goto LABEL_23;
  memset_0(v10, 0, (unsigned int)v9);
  *((_DWORD *)v11 + 8) |= a2 == 0;
  *((_DWORD *)v11 + 9) = PerflibciValidateCode();
  v12 = (WCHAR *)(v11 + 12);
  v11[1] = v11 + 12;
  v11[2] = 0;
  if ( v7 )
  {
    nSize = 260;
    GetComputerNameW(v12, &nSize);
  }
  else
  {
    v17 = -1;
    do
      ++v17;
    while ( a1[v17] );
    StringCchCopyW(v12, v17 + 1, a1);
  }
  do
    ++v6;
  while ( *(_WORD *)(v11[1] + 2 * v6) );
  *((_DWORD *)v11 + 23) = ((2 * v6 + 9) & 0xFFFFFFF8) + 16;
  if ( ((2 * (_DWORD)v6 + 9) & 0xFFFFFFF8) >= 0xFFFFFFF0 )
  {
    LastError = 534;
    LocalFree(v11);
    v11 = 0;
    goto LABEL_13;
  }
  MutexW = CreateMutexW(0, 0, 0);
  *v11 = MutexW;
  if ( !MutexW )
  {
    LastError = GetLastError();
    LocalFree(v11);
    v11 = 0;
    if ( !LastError )
LABEL_23:
      LastError = 14;
LABEL_13:
    LocalFree(v11);
    return LastError;
  }
  LastError = 0;
  *a3 = v11;
  return LastError;
}

```

## disassembly

```asm
0x1800045d0  push    rbx
0x1800045d2  push    rbp
0x1800045d3  push    rsi
0x1800045d4  push    rdi
0x1800045d5  push    r12
0x1800045d7  push    r13
0x1800045d9  push    r14
0x1800045db  push    r15
0x1800045dd  sub     rsp, 28h
0x1800045e1  xor     r13d, r13d
0x1800045e4  mov     r14, r8
0x1800045e7  mov     r12b, dl
0x1800045ea  mov     rsi, rcx
0x1800045ed  test    r8, r8
0x1800045f0  jz      loc_1800046ED
0x1800045f6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800045fa  mov     [r8], r13
0x1800045fd  mov     bpl, 1
0x180004600  test    rcx, rcx
0x180004603  jnz     loc_180004706
0x180004609  mov     eax, 105h
0x18000460e  add     eax, 7
0x180004611  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004618  and     eax, 0FFFFFFF8h
0x18000461b  lea     eax, ds:60h[rax*2]
0x180004622  mov     ecx, eax; unsigned __int64
0x180004624  mov     r15d, eax
0x180004627  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000462c  mov     rbx, rax
0x18000462f  test    rax, rax
0x180004632  jz      loc_180004785
0x180004638  mov     r8d, r15d; Size
0x18000463b  xor     edx, edx; Val
0x18000463d  mov     rcx, rax; void *
0x180004640  call    memset_0
0x180004645  mov     eax, r13d
0x180004648  test    r12b, r12b
0x18000464b  setz    al
0x18000464e  or      [rbx+20h], eax
0x180004651  call    ?PerflibciValidateCode@@YAKXZ; PerflibciValidateCode(void)
0x180004656  mov     [rbx+24h], eax
0x180004659  lea     rcx, [rbx+60h]; unsigned __int16 *
0x18000465d  mov     [rbx+8], rcx
0x180004661  mov     [rbx+10h], r13
0x180004665  test    bpl, bpl
0x180004668  jz      loc_180004727
0x18000466e  lea     rdx, [rsp+68h+nSize]; nSize
0x180004676  mov     [rsp+68h+nSize], 104h
0x180004681  call    cs:__imp_GetComputerNameW
0x180004688  nop     dword ptr [rax+rax+00h]
0x18000468d  mov     rax, [rbx+8]
0x180004691  inc     rdi
0x180004694  cmp     [rax+rdi*2], r13w
0x180004699  jnz     short loc_180004691
0x18000469b  lea     eax, ds:9[rdi*2]
0x1800046a2  and     eax, 0FFFFFFF8h
0x1800046a5  add     eax, 10h
0x1800046a8  mov     [rbx+5Ch], eax
0x1800046ab  cmp     eax, 10h
0x1800046ae  jb      loc_180004744
0x1800046b4  xor     r8d, r8d; lpName
0x1800046b7  xor     edx, edx; bInitialOwner
0x1800046b9  xor     ecx, ecx; lpMutexAttributes
0x1800046bb  call    cs:__imp_CreateMutexW
0x1800046c2  nop     dword ptr [rax+rax+00h]
0x1800046c7  mov     [rbx], rax
0x1800046ca  test    rax, rax
0x1800046cd  jz      loc_18000475D
0x1800046d3  mov     edi, r13d
0x1800046d6  mov     [r14], rbx
0x1800046d9  mov     eax, edi
0x1800046db  add     rsp, 28h
0x1800046df  pop     r15
0x1800046e1  pop     r14
0x1800046e3  pop     r13
0x1800046e5  pop     r12
0x1800046e7  pop     rdi
0x1800046e8  pop     rsi
0x1800046e9  pop     rbp
0x1800046ea  pop     rbx
0x1800046eb  retn
0x1800046ed  mov     rbx, r13
0x1800046f0  mov     edi, 57h ; 'W'
0x1800046f5  mov     rcx, rbx; hMem
0x1800046f8  call    cs:__imp_LocalFree
0x1800046ff  nop     dword ptr [rax+rax+00h]
0x180004704  jmp     short loc_1800046D9
0x180004706  cmp     [rcx], r13w
0x18000470a  jz      loc_180004609
0x180004710  mov     rax, rdi
0x180004713  inc     rax
0x180004716  cmp     [rcx+rax*2], r13w
0x18000471b  jnz     short loc_180004713
0x18000471d  inc     eax
0x18000471f  mov     bpl, r13b
0x180004722  jmp     loc_18000460E
0x180004727  mov     rdx, rdi
0x18000472a  inc     rdx
0x18000472d  cmp     [rsi+rdx*2], r13w
0x180004732  jnz     short loc_18000472A
0x180004734  inc     rdx; unsigned __int64
0x180004737  mov     r8, rsi; unsigned __int16 *
0x18000473a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000473f  jmp     loc_18000468D
0x180004744  mov     rcx, rbx; hMem
0x180004747  mov     edi, 216h
0x18000474c  call    cs:__imp_LocalFree
0x180004753  nop     dword ptr [rax+rax+00h]
0x180004758  mov     rbx, r13
0x18000475b  jmp     short loc_1800046F5
0x18000475d  call    cs:__imp_GetLastError
0x180004764  nop     dword ptr [rax+rax+00h]
0x180004769  mov     rcx, rbx; hMem
0x18000476c  mov     edi, eax
0x18000476e  call    cs:__imp_LocalFree
0x180004775  nop     dword ptr [rax+rax+00h]
0x18000477a  mov     rbx, r13
0x18000477d  test    edi, edi
0x18000477f  jnz     loc_1800046F5
0x180004785  mov     edi, 0Eh
0x18000478a  jmp     loc_1800046F5
```
