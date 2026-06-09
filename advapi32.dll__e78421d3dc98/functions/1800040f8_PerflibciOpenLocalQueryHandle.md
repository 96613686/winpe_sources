# PerflibciOpenLocalQueryHandle

- ea: `0x1800040f8`
- end: `0x180004283`
- name: `PerflibciOpenLocalQueryHandle`
- size: `395`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003e00`
- `0x1800160c0`

## callees

- `0x1800040f8`
- `0x18000428c`
- `0x180017554`
- `0x18003d048`
- `0x18006505a`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000420b`
- `KERNEL32!LocalFree` at `0x180004259`
- `KERNEL32!LocalFree` at `0x18000426f`
- `KERNEL32!LocalFree` at `0x18000420b`
- `KERNEL32!LocalFree` at `0x180004259`
- `KERNEL32!LocalFree` at `0x18000426f`
- `KERNEL32!GetLastError` at `0x180004264`
- `KERNEL32!GetLastError` at `0x180004264`
- `KERNEL32!GetComputerNameW` at `0x1800041a9`
- `KERNEL32!GetComputerNameW` at `0x1800041a9`
- `KERNEL32!CreateMutexW` at `0x1800041d9`
- `KERNEL32!CreateMutexW` at `0x1800041d9`

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
0x1800040f8  push    rbx
0x1800040fa  push    rbp
0x1800040fb  push    rsi
0x1800040fc  push    rdi
0x1800040fd  push    r12
0x1800040ff  push    r13
0x180004101  push    r14
0x180004103  push    r15
0x180004105  sub     rsp, 28h
0x180004109  xor     r13d, r13d
0x18000410c  mov     r14, r8
0x18000410f  mov     r12b, dl
0x180004112  mov     rsi, rcx
0x180004115  test    r8, r8
0x180004118  jz      loc_180004200
0x18000411e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180004122  mov     [r8], r13
0x180004125  mov     bpl, 1
0x180004128  test    rcx, rcx
0x18000412b  jnz     loc_180004213
0x180004131  mov     eax, 105h
0x180004136  add     eax, 7
0x180004139  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004140  and     eax, 0FFFFFFF8h
0x180004143  lea     eax, ds:60h[rax*2]
0x18000414a  mov     ecx, eax; unsigned __int64
0x18000414c  mov     r15d, eax
0x18000414f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004154  mov     rbx, rax
0x180004157  test    rax, rax
0x18000415a  jz      loc_18000427C
0x180004160  mov     r8d, r15d; Size
0x180004163  xor     edx, edx; Val
0x180004165  mov     rcx, rax; void *
0x180004168  call    memset_0
0x18000416d  mov     eax, r13d
0x180004170  test    r12b, r12b
0x180004173  setz    al
0x180004176  or      [rbx+20h], eax
0x180004179  call    ?PerflibciValidateCode@@YAKXZ; PerflibciValidateCode(void)
0x18000417e  mov     [rbx+24h], eax
0x180004181  lea     rcx, [rbx+60h]; unsigned __int16 *
0x180004185  mov     [rbx+8], rcx
0x180004189  mov     [rbx+10h], r13
0x18000418d  test    bpl, bpl
0x180004190  jz      loc_180004234
0x180004196  lea     rdx, [rsp+68h+nSize]; nSize
0x18000419e  mov     [rsp+68h+nSize], 104h
0x1800041a9  call    cs:__imp_GetComputerNameW
0x1800041af  mov     rax, [rbx+8]
0x1800041b3  inc     rdi
0x1800041b6  cmp     [rax+rdi*2], r13w
0x1800041bb  jnz     short loc_1800041B3
0x1800041bd  lea     eax, ds:9[rdi*2]
0x1800041c4  and     eax, 0FFFFFFF8h
0x1800041c7  add     eax, 10h
0x1800041ca  mov     [rbx+5Ch], eax
0x1800041cd  cmp     eax, 10h
0x1800041d0  jb      short loc_180004251
0x1800041d2  xor     r8d, r8d; lpName
0x1800041d5  xor     edx, edx; bInitialOwner
0x1800041d7  xor     ecx, ecx; lpMutexAttributes
0x1800041d9  call    cs:__imp_CreateMutexW
0x1800041df  mov     [rbx], rax
0x1800041e2  test    rax, rax
0x1800041e5  jz      short loc_180004264
0x1800041e7  mov     edi, r13d
0x1800041ea  mov     [r14], rbx
0x1800041ed  mov     eax, edi
0x1800041ef  add     rsp, 28h
0x1800041f3  pop     r15
0x1800041f5  pop     r14
0x1800041f7  pop     r13
0x1800041f9  pop     r12
0x1800041fb  pop     rdi
0x1800041fc  pop     rsi
0x1800041fd  pop     rbp
0x1800041fe  pop     rbx
0x1800041ff  retn
0x180004200  mov     rbx, r13
0x180004203  mov     edi, 57h ; 'W'
0x180004208  mov     rcx, rbx; hMem
0x18000420b  call    cs:__imp_LocalFree
0x180004211  jmp     short loc_1800041ED
0x180004213  cmp     [rcx], r13w
0x180004217  jz      loc_180004131
0x18000421d  mov     rax, rdi
0x180004220  inc     rax
0x180004223  cmp     [rcx+rax*2], r13w
0x180004228  jnz     short loc_180004220
0x18000422a  inc     eax
0x18000422c  mov     bpl, r13b
0x18000422f  jmp     loc_180004136
0x180004234  mov     rdx, rdi
0x180004237  inc     rdx
0x18000423a  cmp     [rsi+rdx*2], r13w
0x18000423f  jnz     short loc_180004237
0x180004241  inc     rdx; unsigned __int64
0x180004244  mov     r8, rsi; unsigned __int16 *
0x180004247  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000424c  jmp     loc_1800041AF
0x180004251  mov     rcx, rbx; hMem
0x180004254  mov     edi, 216h
0x180004259  call    cs:__imp_LocalFree
0x18000425f  mov     rbx, r13
0x180004262  jmp     short loc_180004208
0x180004264  call    cs:__imp_GetLastError
0x18000426a  mov     rcx, rbx; hMem
0x18000426d  mov     edi, eax
0x18000426f  call    cs:__imp_LocalFree
0x180004275  mov     rbx, r13
0x180004278  test    edi, edi
0x18000427a  jnz     short loc_180004208
0x18000427c  mov     edi, 0Eh
0x180004281  jmp     short loc_180004208
```
