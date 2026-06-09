# mtx_do_lock

- ea: `0x1801d2b44`
- end: `0x1801d2c75`
- name: `mtx_do_lock`
- size: `305`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1801d2ae0`
- `0x1801d2af0`

## callees

- `0x1801d2050`
- `0x1801d2b44`
- `0x1801f7110`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1801d2b6d`
- `KERNEL32!GetCurrentThreadId` at `0x1801d2b6d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1801d2b8c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1801d2bae`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1801d2b8c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1801d2bae`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x1801d2bef`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x1801d2c07`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x1801d2bef`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x1801d2c07`

## pseudocode

```c
__int64 __fastcall mtx_do_lock(__int64 a1, __int64 a2)
{
  DWORD CurrentThreadId; // eax
  DWORD v5; // ebp
  DWORD *v6; // rsi
  int v7; // ecx
  __int64 v9; // [rsp+20h] [rbp-28h] BYREF
  int v10; // [rsp+28h] [rbp-20h]

  CurrentThreadId = GetCurrentThreadId();
  v5 = CurrentThreadId;
  if ( (*(_DWORD *)a1 & 0xFFFFFEFF) == 1 )
  {
    if ( *(_DWORD *)(a1 + 72) != CurrentThreadId )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
      *(_DWORD *)(a1 + 72) = v5;
    }
    ++*(_DWORD *)(a1 + 76);
    return 0;
  }
  if ( !a2 )
  {
    v6 = (DWORD *)(a1 + 72);
    if ( *(_DWORD *)(a1 + 72) != CurrentThreadId )
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
LABEL_19:
    v7 = *(_DWORD *)(a1 + 76);
    *(_DWORD *)(a1 + 76) = v7 + 1;
    if ( v7 + 1 <= 1 )
    {
      *v6 = v5;
    }
    else if ( (*(_DWORD *)a1 & 0x100) == 0 )
    {
      *(_DWORD *)(a1 + 76) = v7;
      if ( !a2 )
        return 3;
      goto LABEL_22;
    }
    return 0;
  }
  if ( *(__int64 *)a2 >= 0 && (*(_QWORD *)a2 || *(int *)(a2 + 8) > 0) )
  {
    while ( 1 )
    {
      Timespec64_get_sys(&v9);
      if ( v9 >= *(_QWORD *)a2 && (v9 != *(_QWORD *)a2 || v10 >= *(_DWORD *)(a2 + 8)) )
        break;
      v6 = (DWORD *)(a1 + 72);
      if ( *(_DWORD *)(a1 + 72) == v5 || TryAcquireSRWLockExclusive((PSRWLOCK)(a1 + 16)) )
        goto LABEL_19;
    }
  }
  else
  {
    v6 = (DWORD *)(a1 + 72);
    if ( *(_DWORD *)(a1 + 72) == CurrentThreadId || TryAcquireSRWLockExclusive((PSRWLOCK)(a1 + 16)) )
      goto LABEL_19;
  }
LABEL_22:
  if ( *(_QWORD *)a2 )
    return 2;
  else
    return 3 - (unsigned int)(*(_DWORD *)(a2 + 8) != 0);
}

```

## disassembly

```asm
0x1801d2b44  mov     [rsp+arg_8], rbx
0x1801d2b49  mov     [rsp+arg_10], rbp
0x1801d2b4e  mov     [rsp+arg_18], rsi
0x1801d2b53  push    rdi
0x1801d2b54  sub     rsp, 40h
0x1801d2b58  mov     rax, cs:__security_cookie
0x1801d2b5f  xor     rax, rsp
0x1801d2b62  mov     [rsp+48h+var_18], rax
0x1801d2b67  mov     rdi, rdx
0x1801d2b6a  mov     rbx, rcx
0x1801d2b6d  call    cs:__imp_GetCurrentThreadId
0x1801d2b73  mov     r8d, [rbx]
0x1801d2b76  mov     ebp, eax
0x1801d2b78  btr     r8d, 8
0x1801d2b7d  cmp     r8d, 1
0x1801d2b81  jnz     short loc_1801D2B9D
0x1801d2b83  cmp     [rbx+48h], eax
0x1801d2b86  jz      short loc_1801D2B95
0x1801d2b88  lea     rcx, [rbx+10h]; SRWLock
0x1801d2b8c  call    cs:__imp_AcquireSRWLockExclusive
0x1801d2b92  mov     [rbx+48h], ebp
0x1801d2b95  inc     dword ptr [rbx+4Ch]
0x1801d2b98  jmp     loc_1801D2C51
0x1801d2b9d  test    rdi, rdi
0x1801d2ba0  jnz     short loc_1801D2BB6
0x1801d2ba2  lea     rsi, [rbx+48h]
0x1801d2ba6  cmp     [rsi], ebp
0x1801d2ba8  jz      short loc_1801D2C11
0x1801d2baa  lea     rcx, [rbx+10h]; SRWLock
0x1801d2bae  call    cs:__imp_AcquireSRWLockExclusive
0x1801d2bb4  jmp     short loc_1801D2C11
0x1801d2bb6  cmp     qword ptr [rdi], 0
0x1801d2bba  jl      short loc_1801D2BFB
0x1801d2bbc  jnz     short loc_1801D2BC4
0x1801d2bbe  cmp     dword ptr [rdi+8], 0
0x1801d2bc2  jle     short loc_1801D2BFB
0x1801d2bc4  lea     rcx, [rsp+48h+var_28]
0x1801d2bc9  call    _Timespec64_get_sys
0x1801d2bce  mov     rax, [rsp+48h+var_28]
0x1801d2bd3  cmp     rax, [rdi]
0x1801d2bd6  jl      short loc_1801D2BE3
0x1801d2bd8  jnz     short loc_1801D2C2F
0x1801d2bda  mov     eax, [rdi+8]
0x1801d2bdd  cmp     [rsp+48h+var_20], eax
0x1801d2be1  jge     short loc_1801D2C2F
0x1801d2be3  lea     rsi, [rbx+48h]
0x1801d2be7  cmp     [rsi], ebp
0x1801d2be9  jz      short loc_1801D2C11
0x1801d2beb  lea     rcx, [rbx+10h]; SRWLock
0x1801d2bef  call    cs:__imp_TryAcquireSRWLockExclusive
0x1801d2bf5  test    al, al
0x1801d2bf7  jnz     short loc_1801D2C11
0x1801d2bf9  jmp     short loc_1801D2BC4
0x1801d2bfb  lea     rsi, [rbx+48h]
0x1801d2bff  cmp     [rsi], ebp
0x1801d2c01  jz      short loc_1801D2C11
0x1801d2c03  lea     rcx, [rbx+10h]; SRWLock
0x1801d2c07  call    cs:__imp_TryAcquireSRWLockExclusive
0x1801d2c0d  test    al, al
0x1801d2c0f  jz      short loc_1801D2C2F
0x1801d2c11  mov     ecx, [rbx+4Ch]
0x1801d2c14  lea     eax, [rcx+1]
0x1801d2c17  mov     [rbx+4Ch], eax
0x1801d2c1a  cmp     eax, 1
0x1801d2c1d  jle     short loc_1801D2C4F
0x1801d2c1f  test    dword ptr [rbx], 100h
0x1801d2c25  jnz     short loc_1801D2C51
0x1801d2c27  mov     [rbx+4Ch], ecx
0x1801d2c2a  test    rdi, rdi
0x1801d2c2d  jz      short loc_1801D2C48
0x1801d2c2f  cmp     qword ptr [rdi], 0
0x1801d2c33  jnz     short loc_1801D2C41
0x1801d2c35  mov     eax, [rdi+8]
0x1801d2c38  neg     eax
0x1801d2c3a  sbb     eax, eax
0x1801d2c3c  add     eax, 3
0x1801d2c3f  jmp     short loc_1801D2C53
0x1801d2c41  mov     eax, 2
0x1801d2c46  jmp     short loc_1801D2C53
0x1801d2c48  mov     eax, 3
0x1801d2c4d  jmp     short loc_1801D2C53
0x1801d2c4f  mov     [rsi], ebp
0x1801d2c51  xor     eax, eax
0x1801d2c53  mov     rcx, [rsp+48h+var_18]
0x1801d2c58  xor     rcx, rsp; StackCookie
0x1801d2c5b  call    __security_check_cookie
0x1801d2c60  mov     rbx, [rsp+48h+arg_8]
0x1801d2c65  mov     rbp, [rsp+48h+arg_10]
0x1801d2c6a  mov     rsi, [rsp+48h+arg_18]
0x1801d2c6f  add     rsp, 40h
0x1801d2c73  pop     rdi
0x1801d2c74  retn
```
