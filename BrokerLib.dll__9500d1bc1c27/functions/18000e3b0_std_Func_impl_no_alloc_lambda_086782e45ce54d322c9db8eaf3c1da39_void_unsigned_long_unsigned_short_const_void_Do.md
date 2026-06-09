# std::_Func_impl_no_alloc__lambda_086782e45ce54d322c9db8eaf3c1da39__void_unsigned_long_unsigned_short_const___void___::_Do_call

- ea: `0x18000e3b0`
- end: `0x18000e447`
- name: `std::_Func_impl_no_alloc__lambda_086782e45ce54d322c9db8eaf3c1da39__void_unsigned_long_unsigned_short_const___void___::_Do_call`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000e3b0`
- `0x18000e4f0`
- `0x18001e010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e3cd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e3cd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e417`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e417`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e3d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e3d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 (__fastcall *__fastcall std::_Func_impl_no_alloc__lambda_086782e45ce54d322c9db8eaf3c1da39__void_unsigned_long_unsigned_short_const___void___::_Do_call(
        __int64 a1,
        unsigned int *a2,
        __int64 a3,
        __int64 *a4))(_QWORD, _QWORD, __int64)
{
  __int64 v5; // rbp
  unsigned int v6; // esi
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 (__fastcall *result)(_QWORD, _QWORD, __int64); // rax

  v5 = *a4;
  v6 = *a2;
  v7 = *(_QWORD *)(a1 + 8);
  RtlAcquireSRWLockExclusive(v7);
  GetCurrentThreadId();
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL),
      v6);
  RtlReleaseSRWLockExclusive(v7);
  v8 = *(_QWORD *)(a1 + 8);
  result = *(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(v8 + 32);
  if ( result )
    return (__int64 (__fastcall *)(_QWORD, _QWORD, __int64))result(*(_QWORD *)(v8 + 8), v6, v5);
  return result;
}

```

## disassembly

```asm
0x18000e3b0  push    rbx
0x18000e3b2  push    rbp
0x18000e3b3  push    rsi
0x18000e3b4  push    rdi
0x18000e3b5  sub     rsp, 48h
0x18000e3b9  mov     rbx, rcx
0x18000e3bc  mov     rbp, [r9]
0x18000e3bf  mov     esi, [rdx]
0x18000e3c1  mov     rdi, [rcx+8]
0x18000e3c5  mov     [rsp+68h+var_38], rdi
0x18000e3ca  mov     rcx, rdi
0x18000e3cd  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e3d3  call    cs:__imp_GetCurrentThreadId
0x18000e3d9  mov     [rsp+68h+var_2C], eax
0x18000e3dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3e4  test    dword ptr [rcx+1Ch], 800h
0x18000e3eb  jz      short loc_18000E414
0x18000e3ed  cmp     byte ptr [rcx+19h], 5
0x18000e3f1  jb      short loc_18000E414
0x18000e3f3  mov     rax, [rbx+8]
0x18000e3f7  mov     edx, 36h ; '6'
0x18000e3fc  mov     [rsp+68h+var_48], esi
0x18000e400  mov     r9, [rax+8]
0x18000e404  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x18000e40b  mov     rcx, [rcx+10h]
0x18000e40f  call    WPP_SF__guid_d
0x18000e414  mov     rcx, rdi
0x18000e417  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e41d  mov     [rsp+68h+var_30], 0
0x18000e422  mov     rcx, [rbx+8]
0x18000e426  mov     rax, [rcx+20h]
0x18000e42a  test    rax, rax
0x18000e42d  jz      short loc_18000E43E
0x18000e42f  mov     r8, rbp
0x18000e432  mov     edx, esi
0x18000e434  mov     rcx, [rcx+8]
0x18000e438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e43d  nop
0x18000e43e  add     rsp, 48h
0x18000e442  pop     rdi
0x18000e443  pop     rsi
0x18000e444  pop     rbp
0x18000e445  pop     rbx
0x18000e446  retn
```
