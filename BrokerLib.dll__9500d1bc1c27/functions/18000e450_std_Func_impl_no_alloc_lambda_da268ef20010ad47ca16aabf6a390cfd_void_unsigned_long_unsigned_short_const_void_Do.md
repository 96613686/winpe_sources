# std::_Func_impl_no_alloc__lambda_da268ef20010ad47ca16aabf6a390cfd__void_unsigned_long_unsigned_short_const___void___::_Do_call

- ea: `0x18000e450`
- end: `0x18000e4e7`
- name: `std::_Func_impl_no_alloc__lambda_da268ef20010ad47ca16aabf6a390cfd__void_unsigned_long_unsigned_short_const___void___::_Do_call`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000e450`
- `0x18000e4f0`
- `0x18001e010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e46d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e46d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e4b7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e4b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e473`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e473`

## pseudocode

```c
__int64 (__fastcall *__fastcall std::_Func_impl_no_alloc__lambda_da268ef20010ad47ca16aabf6a390cfd__void_unsigned_long_unsigned_short_const___void___::_Do_call(
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
      55,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL),
      v6);
  RtlReleaseSRWLockExclusive(v7);
  v8 = *(_QWORD *)(a1 + 8);
  result = *(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(v8 + 40);
  if ( result )
    return (__int64 (__fastcall *)(_QWORD, _QWORD, __int64))result(*(_QWORD *)(v8 + 8), v6, v5);
  return result;
}

```

## disassembly

```asm
0x18000e450  push    rbx
0x18000e452  push    rbp
0x18000e453  push    rsi
0x18000e454  push    rdi
0x18000e455  sub     rsp, 48h
0x18000e459  mov     rbx, rcx
0x18000e45c  mov     rbp, [r9]
0x18000e45f  mov     esi, [rdx]
0x18000e461  mov     rdi, [rcx+8]
0x18000e465  mov     [rsp+68h+var_38], rdi
0x18000e46a  mov     rcx, rdi
0x18000e46d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e473  call    cs:__imp_GetCurrentThreadId
0x18000e479  mov     [rsp+68h+var_2C], eax
0x18000e47d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e484  test    dword ptr [rcx+1Ch], 800h
0x18000e48b  jz      short loc_18000E4B4
0x18000e48d  cmp     byte ptr [rcx+19h], 5
0x18000e491  jb      short loc_18000E4B4
0x18000e493  mov     rax, [rbx+8]
0x18000e497  mov     edx, 37h ; '7'
0x18000e49c  mov     [rsp+68h+var_48], esi
0x18000e4a0  mov     r9, [rax+8]
0x18000e4a4  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x18000e4ab  mov     rcx, [rcx+10h]
0x18000e4af  call    WPP_SF__guid_d
0x18000e4b4  mov     rcx, rdi
0x18000e4b7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e4bd  mov     [rsp+68h+var_30], 0
0x18000e4c2  mov     rcx, [rbx+8]
0x18000e4c6  mov     rax, [rcx+28h]
0x18000e4ca  test    rax, rax
0x18000e4cd  jz      short loc_18000E4DE
0x18000e4cf  mov     r8, rbp
0x18000e4d2  mov     edx, esi
0x18000e4d4  mov     rcx, [rcx+8]
0x18000e4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4dd  nop
0x18000e4de  add     rsp, 48h
0x18000e4e2  pop     rdi
0x18000e4e3  pop     rsi
0x18000e4e4  pop     rbp
0x18000e4e5  pop     rbx
0x18000e4e6  retn
```
