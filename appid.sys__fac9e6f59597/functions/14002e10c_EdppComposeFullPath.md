# EdppComposeFullPath

- ea: `0x14002e10c`
- end: `0x14002e222`
- name: `EdppComposeFullPath`
- size: `278`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, _QWORD *, _WORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002e7ec`
- `0x14002e9d8`

## callees

- `0x140001b3c`
- `0x140006c40`
- `0x140006f40`
- `0x14002e10c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002e1fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e1fe`
- `ntoskrnl!ExAllocatePool2` at `0x14002e18a`
- `ntoskrnl!ExAllocatePool2` at `0x14002e18a`
- `ntoskrnl!RtlGetNtSystemRoot` at `0x14002e13b`
- `ntoskrnl!RtlGetNtSystemRoot` at `0x14002e13b`

## pseudocode

```c
__int64 __fastcall EdppComposeFullPath(const wchar_t *a1, unsigned int a2, _QWORD *a3, _WORD *a4)
{
  __int64 NtSystemRoot; // rax
  __int64 v8; // rdi
  const void *v9; // r12
  __int64 v10; // r10
  unsigned __int16 v11; // r10
  __int64 v12; // rax
  size_t v13; // r13
  size_t v14; // rbp
  char *Pool2; // rax
  char *v16; // rsi
  NTSTATUS v17; // ebx

  *a3 = 0;
  *a4 = 0;
  NtSystemRoot = RtlGetNtSystemRoot();
  v8 = -1;
  v9 = (const void *)NtSystemRoot;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(NtSystemRoot + 2 * v10) );
  v11 = 2 * v10;
  v12 = -1;
  v13 = v11;
  do
    ++v12;
  while ( a1[v12] );
  v14 = (unsigned __int16)(v11 + 2 * (v12 + 4));
  Pool2 = (char *)ExAllocatePool2(256, v14, 1097884741);
  v16 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, v14);
    memmove(v16, v9, v13);
    v17 = RtlStringCbPrintfW((NTSTRSAFE_PWSTR)&v16[v13], v14 - v13, a1, a2);
    if ( v17 < 0 )
    {
      ExFreePoolWithTag(v16, 0);
    }
    else
    {
      *a3 = v16;
      do
        ++v8;
      while ( *(_WORD *)&v16[2 * v8] );
      *a4 = 2 * (v8 + 1);
    }
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14002e10c  mov     [rsp+arg_10], rbx
0x14002e111  mov     [rsp+arg_8], edx
0x14002e115  mov     [rsp+pszFormat], rcx
0x14002e11a  push    rbp
0x14002e11b  push    rsi
0x14002e11c  push    rdi
0x14002e11d  push    r12
0x14002e11f  push    r13
0x14002e121  push    r14
0x14002e123  push    r15
0x14002e125  sub     rsp, 20h
0x14002e129  xor     esi, esi
0x14002e12b  mov     r15, r9
0x14002e12e  mov     [r8], rsi
0x14002e131  mov     r14, r8
0x14002e134  mov     [r9], si
0x14002e138  mov     rbx, rcx
0x14002e13b  call    cs:__imp_RtlGetNtSystemRoot
0x14002e142  nop     dword ptr [rax+rax+00h]
0x14002e147  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14002e14b  mov     r12, rax
0x14002e14e  mov     r10, rdi
0x14002e151  inc     r10
0x14002e154  cmp     [rax+r10*2], si
0x14002e159  jnz     short loc_14002E151
0x14002e15b  add     r10w, r10w
0x14002e15f  mov     rax, rdi
0x14002e162  movzx   r13d, r10w
0x14002e166  inc     rax
0x14002e169  cmp     [rbx+rax*2], si
0x14002e16d  jnz     short loc_14002E166
0x14002e16f  add     ax, 4
0x14002e173  mov     r8d, 41706445h
0x14002e179  add     ax, ax
0x14002e17c  mov     ecx, 100h
0x14002e181  add     ax, r13w
0x14002e185  movzx   ebp, ax
0x14002e188  mov     edx, ebp
0x14002e18a  call    cs:__imp_ExAllocatePool2
0x14002e191  nop     dword ptr [rax+rax+00h]
0x14002e196  mov     rsi, rax
0x14002e199  test    rax, rax
0x14002e19c  jnz     short loc_14002E1A5
0x14002e19e  mov     ebx, 0C0000017h
0x14002e1a3  jmp     short loc_14002E20A
0x14002e1a5  mov     r8, rbp; Size
0x14002e1a8  xor     edx, edx; Val
0x14002e1aa  mov     rcx, rsi; void *
0x14002e1ad  call    memset
0x14002e1b2  mov     r8, r13; Size
0x14002e1b5  mov     rdx, r12; Src
0x14002e1b8  mov     rcx, rsi; void *
0x14002e1bb  call    memmove
0x14002e1c0  mov     r9d, [rsp+58h+arg_8]
0x14002e1c5  lea     rcx, [rsi+r13]; pszDest
0x14002e1c9  mov     r8, [rsp+58h+pszFormat]; pszFormat
0x14002e1ce  sub     rbp, r13
0x14002e1d1  mov     rdx, rbp; cbDest
0x14002e1d4  call    RtlStringCbPrintfW
0x14002e1d9  mov     ebx, eax
0x14002e1db  xor     eax, eax
0x14002e1dd  test    ebx, ebx
0x14002e1df  js      short loc_14002E1F9
0x14002e1e1  mov     [r14], rsi
0x14002e1e4  inc     rdi
0x14002e1e7  cmp     [rsi+rdi*2], ax
0x14002e1eb  jnz     short loc_14002E1E4
0x14002e1ed  inc     di
0x14002e1f0  add     di, di
0x14002e1f3  mov     [r15], di
0x14002e1f7  jmp     short loc_14002E20A
0x14002e1f9  xor     edx, edx; Tag
0x14002e1fb  mov     rcx, rsi; P
0x14002e1fe  call    cs:__imp_ExFreePoolWithTag
0x14002e205  nop     dword ptr [rax+rax+00h]
0x14002e20a  mov     eax, ebx
0x14002e20c  mov     rbx, [rsp+58h+arg_10]
0x14002e211  add     rsp, 20h
0x14002e215  pop     r15
0x14002e217  pop     r14
0x14002e219  pop     r13
0x14002e21b  pop     r12
0x14002e21d  pop     rdi
0x14002e21e  pop     rsi
0x14002e21f  pop     rbp
0x14002e220  retn
```
