# mtx_do_lock

- ea: `0x180307b9c`
- end: `0x180307d05`
- name: `mtx_do_lock`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180307e68`

## callees

- `0x180307b9c`
- `0x180309ce4`
- `0x180309de4`
- `0x18030c3f0`
- `0x180358070`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180307bc9`
- `KERNEL32!GetCurrentThreadId` at `0x180307be4`
- `KERNEL32!GetCurrentThreadId` at `0x180307bfa`
- `KERNEL32!GetCurrentThreadId` at `0x180307c51`
- `KERNEL32!GetCurrentThreadId` at `0x180307c86`
- `KERNEL32!GetCurrentThreadId` at `0x180307cdf`
- `KERNEL32!GetCurrentThreadId` at `0x180307bc9`
- `KERNEL32!GetCurrentThreadId` at `0x180307be4`
- `KERNEL32!GetCurrentThreadId` at `0x180307bfa`
- `KERNEL32!GetCurrentThreadId` at `0x180307c51`
- `KERNEL32!GetCurrentThreadId` at `0x180307c86`
- `KERNEL32!GetCurrentThreadId` at `0x180307cdf`

## pseudocode

```c
__int64 __fastcall mtx_do_lock(__int64 a1, const xtime *a2)
{
  unsigned __int8 (__fastcall *v4)(__int64, _QWORD); // rbx
  unsigned int v5; // eax
  int v6; // ecx
  xtime v8; // [rsp+20h] [rbp-38h] BYREF

  if ( (*(_DWORD *)a1 & 0xFFFFFEFF) == 1 )
  {
    if ( *(_DWORD *)(a1 + 72) != GetCurrentThreadId() )
    {
      (**(void (__fastcall ***)(__int64))(a1 + 8))(a1 + 8);
      *(_DWORD *)(a1 + 72) = GetCurrentThreadId();
    }
    ++*(_DWORD *)(a1 + 76);
    return 0;
  }
  if ( !a2 )
  {
    if ( *(_DWORD *)(a1 + 72) != GetCurrentThreadId() )
      (**(void (__fastcall ***)(__int64))(a1 + 8))(a1 + 8);
    goto LABEL_19;
  }
  if ( a2->sec >= 0 && (a2->sec || a2->nsec > 0) )
  {
    while ( 1 )
    {
      xtime_get(&v8, 1);
      if ( v8.sec >= a2->sec && (v8.sec != a2->sec || v8.nsec >= a2->nsec) )
        goto LABEL_22;
      if ( *(_DWORD *)(a1 + 72) != GetCurrentThreadId() )
      {
        v4 = *(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 8) + 16LL);
        v5 = Xtime_diff_to_millis2(a2, &v8);
        if ( !v4(a1 + 8, v5) )
          continue;
      }
      goto LABEL_19;
    }
  }
  if ( *(_DWORD *)(a1 + 72) == GetCurrentThreadId()
    || (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 8) + 8LL))(a1 + 8) )
  {
LABEL_19:
    v6 = *(_DWORD *)(a1 + 76);
    *(_DWORD *)(a1 + 76) = v6 + 1;
    if ( v6 + 1 <= 1 )
    {
      *(_DWORD *)(a1 + 72) = GetCurrentThreadId();
    }
    else if ( (*(_DWORD *)a1 & 0x100) == 0 )
    {
      *(_DWORD *)(a1 + 76) = v6;
      goto LABEL_22;
    }
    return 0;
  }
LABEL_22:
  if ( a2 && (a2->sec || a2->nsec) )
    return 2;
  else
    return 3;
}

```

## disassembly

```asm
0x180307b9c  mov     [rsp+arg_10], rbx
0x180307ba1  push    rsi
0x180307ba2  push    rdi
0x180307ba3  push    r14
0x180307ba5  sub     rsp, 40h
0x180307ba9  mov     rax, cs:__security_cookie
0x180307bb0  xor     rax, rsp
0x180307bb3  mov     [rsp+58h+var_28], rax
0x180307bb8  mov     eax, [rcx]
0x180307bba  mov     r14, rdx
0x180307bbd  btr     eax, 8
0x180307bc1  mov     rsi, rcx
0x180307bc4  cmp     eax, 1
0x180307bc7  jnz     short loc_180307BF5
0x180307bc9  call    cs:__imp_GetCurrentThreadId
0x180307bcf  cmp     [rsi+48h], eax
0x180307bd2  jz      short loc_180307BED
0x180307bd4  lea     rcx, [rsi+8]
0x180307bd8  mov     rax, [rcx]
0x180307bdb  mov     rax, [rax]
0x180307bde  call    cs:__guard_dispatch_icall_fptr
0x180307be4  call    cs:__imp_GetCurrentThreadId
0x180307bea  mov     [rsi+48h], eax
0x180307bed  inc     dword ptr [rsi+4Ch]
0x180307bf0  jmp     loc_180307CE8
0x180307bf5  test    r14, r14
0x180307bf8  jnz     short loc_180307C1E
0x180307bfa  call    cs:__imp_GetCurrentThreadId
0x180307c00  cmp     [rsi+48h], eax
0x180307c03  jz      loc_180307CA6
0x180307c09  lea     rcx, [rsi+8]
0x180307c0d  mov     rax, [rcx]
0x180307c10  mov     rax, [rax]
0x180307c13  call    cs:__guard_dispatch_icall_fptr
0x180307c19  jmp     loc_180307CA6
0x180307c1e  cmp     qword ptr [rdx], 0
0x180307c22  jl      short loc_180307C86
0x180307c24  jnz     short loc_180307C2C
0x180307c26  cmp     dword ptr [rdx+8], 0
0x180307c2a  jle     short loc_180307C86
0x180307c2c  mov     edx, 1; int
0x180307c31  lea     rcx, [rsp+58h+var_38]; xtime *
0x180307c36  call    xtime_get
0x180307c3b  mov     rax, [rsp+58h+var_38.sec]
0x180307c40  cmp     rax, [r14]
0x180307c43  jl      short loc_180307C51
0x180307c45  jnz     short loc_180307CBF
0x180307c47  mov     eax, [r14+8]
0x180307c4b  cmp     [rsp+58h+var_38.nsec], eax
0x180307c4f  jge     short loc_180307CBF
0x180307c51  call    cs:__imp_GetCurrentThreadId
0x180307c57  cmp     [rsi+48h], eax
0x180307c5a  jz      short loc_180307CA6
0x180307c5c  mov     rax, [rsi+8]
0x180307c60  lea     rdx, [rsp+58h+var_38]; xtime *
0x180307c65  mov     rcx, r14; xtime *
0x180307c68  mov     rbx, [rax+10h]
0x180307c6c  call    _Xtime_diff_to_millis2
0x180307c71  mov     edx, eax
0x180307c73  lea     rcx, [rsi+8]
0x180307c77  mov     rax, rbx
0x180307c7a  call    cs:__guard_dispatch_icall_fptr
0x180307c80  test    al, al
0x180307c82  jnz     short loc_180307CA6
0x180307c84  jmp     short loc_180307C2C
0x180307c86  call    cs:__imp_GetCurrentThreadId
0x180307c8c  cmp     [rsi+48h], eax
0x180307c8f  jz      short loc_180307CA6
0x180307c91  lea     rcx, [rsi+8]
0x180307c95  mov     rax, [rcx]
0x180307c98  mov     rax, [rax+8]
0x180307c9c  call    cs:__guard_dispatch_icall_fptr
0x180307ca2  test    al, al
0x180307ca4  jz      short loc_180307CBF
0x180307ca6  mov     ecx, [rsi+4Ch]
0x180307ca9  lea     eax, [rcx+1]
0x180307cac  mov     [rsi+4Ch], eax
0x180307caf  cmp     eax, 1
0x180307cb2  jle     short loc_180307CDF
0x180307cb4  test    dword ptr [rsi], 100h
0x180307cba  jnz     short loc_180307CE8
0x180307cbc  mov     [rsi+4Ch], ecx
0x180307cbf  test    r14, r14
0x180307cc2  jz      short loc_180307CD8
0x180307cc4  cmp     qword ptr [r14], 0
0x180307cc8  jnz     short loc_180307CD1
0x180307cca  cmp     dword ptr [r14+8], 0
0x180307ccf  jz      short loc_180307CD8
0x180307cd1  mov     eax, 2
0x180307cd6  jmp     short loc_180307CEA
0x180307cd8  mov     eax, 3
0x180307cdd  jmp     short loc_180307CEA
0x180307cdf  call    cs:__imp_GetCurrentThreadId
0x180307ce5  mov     [rsi+48h], eax
0x180307ce8  xor     eax, eax
0x180307cea  mov     rcx, [rsp+58h+var_28]
0x180307cef  xor     rcx, rsp; StackCookie
0x180307cf2  call    __security_check_cookie
0x180307cf7  mov     rbx, [rsp+58h+arg_10]
0x180307cfc  add     rsp, 40h
0x180307d00  pop     r14
0x180307d02  pop     rdi
0x180307d03  pop     rsi
0x180307d04  retn
```
