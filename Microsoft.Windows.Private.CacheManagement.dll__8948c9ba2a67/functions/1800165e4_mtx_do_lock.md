# mtx_do_lock

- ea: `0x1800165e4`
- end: `0x180016715`
- name: `mtx_do_lock`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800165b8`

## callees

- `0x1800165e4`
- `0x180017f8c`
- `0x1800181b0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001660d`
- `KERNEL32!GetCurrentThreadId` at `0x18001660d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001662c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001664e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001662c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001664e`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x18001668f`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x1800166a7`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x18001668f`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x1800166a7`

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
0x1800165e4  mov     [rsp+arg_8], rbx
0x1800165e9  mov     [rsp+arg_10], rbp
0x1800165ee  mov     [rsp+arg_18], rsi
0x1800165f3  push    rdi
0x1800165f4  sub     rsp, 40h
0x1800165f8  mov     rax, cs:__security_cookie
0x1800165ff  xor     rax, rsp
0x180016602  mov     [rsp+48h+var_18], rax
0x180016607  mov     rdi, rdx
0x18001660a  mov     rbx, rcx
0x18001660d  call    cs:__imp_GetCurrentThreadId
0x180016613  mov     r8d, [rbx]
0x180016616  mov     ebp, eax
0x180016618  btr     r8d, 8
0x18001661d  cmp     r8d, 1
0x180016621  jnz     short loc_18001663D
0x180016623  cmp     [rbx+48h], eax
0x180016626  jz      short loc_180016635
0x180016628  lea     rcx, [rbx+10h]; SRWLock
0x18001662c  call    cs:__imp_AcquireSRWLockExclusive
0x180016632  mov     [rbx+48h], ebp
0x180016635  inc     dword ptr [rbx+4Ch]
0x180016638  jmp     loc_1800166F1
0x18001663d  test    rdi, rdi
0x180016640  jnz     short loc_180016656
0x180016642  lea     rsi, [rbx+48h]
0x180016646  cmp     [rsi], ebp
0x180016648  jz      short loc_1800166B1
0x18001664a  lea     rcx, [rbx+10h]; SRWLock
0x18001664e  call    cs:__imp_AcquireSRWLockExclusive
0x180016654  jmp     short loc_1800166B1
0x180016656  cmp     qword ptr [rdi], 0
0x18001665a  jl      short loc_18001669B
0x18001665c  jnz     short loc_180016664
0x18001665e  cmp     dword ptr [rdi+8], 0
0x180016662  jle     short loc_18001669B
0x180016664  lea     rcx, [rsp+48h+var_28]
0x180016669  call    _Timespec64_get_sys
0x18001666e  mov     rax, [rsp+48h+var_28]
0x180016673  cmp     rax, [rdi]
0x180016676  jl      short loc_180016683
0x180016678  jnz     short loc_1800166CF
0x18001667a  mov     eax, [rdi+8]
0x18001667d  cmp     [rsp+48h+var_20], eax
0x180016681  jge     short loc_1800166CF
0x180016683  lea     rsi, [rbx+48h]
0x180016687  cmp     [rsi], ebp
0x180016689  jz      short loc_1800166B1
0x18001668b  lea     rcx, [rbx+10h]; SRWLock
0x18001668f  call    cs:__imp_TryAcquireSRWLockExclusive
0x180016695  test    al, al
0x180016697  jnz     short loc_1800166B1
0x180016699  jmp     short loc_180016664
0x18001669b  lea     rsi, [rbx+48h]
0x18001669f  cmp     [rsi], ebp
0x1800166a1  jz      short loc_1800166B1
0x1800166a3  lea     rcx, [rbx+10h]; SRWLock
0x1800166a7  call    cs:__imp_TryAcquireSRWLockExclusive
0x1800166ad  test    al, al
0x1800166af  jz      short loc_1800166CF
0x1800166b1  mov     ecx, [rbx+4Ch]
0x1800166b4  lea     eax, [rcx+1]
0x1800166b7  mov     [rbx+4Ch], eax
0x1800166ba  cmp     eax, 1
0x1800166bd  jle     short loc_1800166EF
0x1800166bf  test    dword ptr [rbx], 100h
0x1800166c5  jnz     short loc_1800166F1
0x1800166c7  mov     [rbx+4Ch], ecx
0x1800166ca  test    rdi, rdi
0x1800166cd  jz      short loc_1800166E8
0x1800166cf  cmp     qword ptr [rdi], 0
0x1800166d3  jnz     short loc_1800166E1
0x1800166d5  mov     eax, [rdi+8]
0x1800166d8  neg     eax
0x1800166da  sbb     eax, eax
0x1800166dc  add     eax, 3
0x1800166df  jmp     short loc_1800166F3
0x1800166e1  mov     eax, 2
0x1800166e6  jmp     short loc_1800166F3
0x1800166e8  mov     eax, 3
0x1800166ed  jmp     short loc_1800166F3
0x1800166ef  mov     [rsi], ebp
0x1800166f1  xor     eax, eax
0x1800166f3  mov     rcx, [rsp+48h+var_18]
0x1800166f8  xor     rcx, rsp; StackCookie
0x1800166fb  call    __security_check_cookie
0x180016700  mov     rbx, [rsp+48h+arg_8]
0x180016705  mov     rbp, [rsp+48h+arg_10]
0x18001670a  mov     rsi, [rsp+48h+arg_18]
0x18001670f  add     rsp, 40h
0x180016713  pop     rdi
0x180016714  retn
```
