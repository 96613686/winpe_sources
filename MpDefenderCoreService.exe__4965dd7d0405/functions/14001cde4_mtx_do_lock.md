# mtx_do_lock

- ea: `0x14001cde4`
- end: `0x14001cf15`
- name: `mtx_do_lock`
- size: `305`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14001cd94`
- `0x14001cd9c`

## callees

- `0x14001cde4`
- `0x14001ef6c`
- `0x14003a5c0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14001ce0d`
- `KERNEL32!GetCurrentThreadId` at `0x14001ce0d`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x14001ce8f`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x14001cea7`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x14001ce8f`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x14001cea7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001ce2c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001ce4e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001ce2c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001ce4e`

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
0x14001cde4  mov     [rsp+arg_8], rbx
0x14001cde9  mov     [rsp+arg_10], rbp
0x14001cdee  mov     [rsp+arg_18], rsi
0x14001cdf3  push    rdi
0x14001cdf4  sub     rsp, 40h
0x14001cdf8  mov     rax, cs:__security_cookie
0x14001cdff  xor     rax, rsp
0x14001ce02  mov     [rsp+48h+var_18], rax
0x14001ce07  mov     rdi, rdx
0x14001ce0a  mov     rbx, rcx
0x14001ce0d  call    cs:__imp_GetCurrentThreadId
0x14001ce13  mov     r8d, [rbx]
0x14001ce16  mov     ebp, eax
0x14001ce18  btr     r8d, 8
0x14001ce1d  cmp     r8d, 1
0x14001ce21  jnz     short loc_14001CE3D
0x14001ce23  cmp     [rbx+48h], eax
0x14001ce26  jz      short loc_14001CE35
0x14001ce28  lea     rcx, [rbx+10h]; SRWLock
0x14001ce2c  call    cs:__imp_AcquireSRWLockExclusive
0x14001ce32  mov     [rbx+48h], ebp
0x14001ce35  inc     dword ptr [rbx+4Ch]
0x14001ce38  jmp     loc_14001CEF1
0x14001ce3d  test    rdi, rdi
0x14001ce40  jnz     short loc_14001CE56
0x14001ce42  lea     rsi, [rbx+48h]
0x14001ce46  cmp     [rsi], ebp
0x14001ce48  jz      short loc_14001CEB1
0x14001ce4a  lea     rcx, [rbx+10h]; SRWLock
0x14001ce4e  call    cs:__imp_AcquireSRWLockExclusive
0x14001ce54  jmp     short loc_14001CEB1
0x14001ce56  cmp     qword ptr [rdi], 0
0x14001ce5a  jl      short loc_14001CE9B
0x14001ce5c  jnz     short loc_14001CE64
0x14001ce5e  cmp     dword ptr [rdi+8], 0
0x14001ce62  jle     short loc_14001CE9B
0x14001ce64  lea     rcx, [rsp+48h+var_28]
0x14001ce69  call    _Timespec64_get_sys
0x14001ce6e  mov     rax, [rsp+48h+var_28]
0x14001ce73  cmp     rax, [rdi]
0x14001ce76  jl      short loc_14001CE83
0x14001ce78  jnz     short loc_14001CECF
0x14001ce7a  mov     eax, [rdi+8]
0x14001ce7d  cmp     [rsp+48h+var_20], eax
0x14001ce81  jge     short loc_14001CECF
0x14001ce83  lea     rsi, [rbx+48h]
0x14001ce87  cmp     [rsi], ebp
0x14001ce89  jz      short loc_14001CEB1
0x14001ce8b  lea     rcx, [rbx+10h]; SRWLock
0x14001ce8f  call    cs:__imp_TryAcquireSRWLockExclusive
0x14001ce95  test    al, al
0x14001ce97  jnz     short loc_14001CEB1
0x14001ce99  jmp     short loc_14001CE64
0x14001ce9b  lea     rsi, [rbx+48h]
0x14001ce9f  cmp     [rsi], ebp
0x14001cea1  jz      short loc_14001CEB1
0x14001cea3  lea     rcx, [rbx+10h]; SRWLock
0x14001cea7  call    cs:__imp_TryAcquireSRWLockExclusive
0x14001cead  test    al, al
0x14001ceaf  jz      short loc_14001CECF
0x14001ceb1  mov     ecx, [rbx+4Ch]
0x14001ceb4  lea     eax, [rcx+1]
0x14001ceb7  mov     [rbx+4Ch], eax
0x14001ceba  cmp     eax, 1
0x14001cebd  jle     short loc_14001CEEF
0x14001cebf  test    dword ptr [rbx], 100h
0x14001cec5  jnz     short loc_14001CEF1
0x14001cec7  mov     [rbx+4Ch], ecx
0x14001ceca  test    rdi, rdi
0x14001cecd  jz      short loc_14001CEE8
0x14001cecf  cmp     qword ptr [rdi], 0
0x14001ced3  jnz     short loc_14001CEE1
0x14001ced5  mov     eax, [rdi+8]
0x14001ced8  neg     eax
0x14001ceda  sbb     eax, eax
0x14001cedc  add     eax, 3
0x14001cedf  jmp     short loc_14001CEF3
0x14001cee1  mov     eax, 2
0x14001cee6  jmp     short loc_14001CEF3
0x14001cee8  mov     eax, 3
0x14001ceed  jmp     short loc_14001CEF3
0x14001ceef  mov     [rsi], ebp
0x14001cef1  xor     eax, eax
0x14001cef3  mov     rcx, [rsp+48h+var_18]
0x14001cef8  xor     rcx, rsp; StackCookie
0x14001cefb  call    __security_check_cookie
0x14001cf00  mov     rbx, [rsp+48h+arg_8]
0x14001cf05  mov     rbp, [rsp+48h+arg_10]
0x14001cf0a  mov     rsi, [rsp+48h+arg_18]
0x14001cf0f  add     rsp, 40h
0x14001cf13  pop     rdi
0x14001cf14  retn
```
