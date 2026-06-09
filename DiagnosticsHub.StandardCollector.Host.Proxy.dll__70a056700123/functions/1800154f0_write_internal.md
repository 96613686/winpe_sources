# _write_internal

- ea: `0x1800154f0`
- end: `0x18001560d`
- name: `_write_internal`
- size: `285`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f1a0`
- `0x180015458`
- `0x18005c78c`
- `0x18005c884`

## callees

- `0x1800073e8`
- `0x18001430c`
- `0x1800143f4`
- `0x1800154f0`
- `0x180015610`

## pseudocode

```c
__int64 __fastcall write_internal(int a1, _BYTE *a2, unsigned int a3, __int64 a4)
{
  BOOL v8; // eax
  __int64 v9; // r15
  unsigned int v10; // r14d

  if ( a1 == -2 )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    return 0xFFFFFFFFLL;
  }
  v8 = a1 >= 0 && a1 < (unsigned int)nhandle;
  if ( !v8 || (v9 = (__int64)a1 >> 6, (*(_BYTE *)(_pioinfo[v9] + 72LL * (a1 & 0x3F) + 56) & 1) == 0) )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)a4);
    return 0xFFFFFFFFLL;
  }
  _acrt_lowio_lock_fh((unsigned int)a1);
  v10 = -1;
  if ( (*(_BYTE *)(_pioinfo[v9] + 72LL * (a1 & 0x3F) + 56) & 1) != 0 )
  {
    v10 = write_nolock(a1, a2, a3, a4);
  }
  else
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
  }
  _acrt_lowio_unlock_fh((unsigned int)a1);
  return v10;
}

```

## disassembly

```asm
0x1800154f0  mov     [rsp+arg_10], rbx
0x1800154f5  mov     [rsp+arg_8], rdx
0x1800154fa  mov     [rsp+arg_0], ecx
0x1800154fe  push    rsi
0x1800154ff  push    r12
0x180015501  push    r13
0x180015503  push    r14
0x180015505  push    r15
0x180015507  sub     rsp, 30h
0x18001550b  mov     rbx, r9
0x18001550e  mov     r13d, r8d
0x180015511  movsxd  rsi, ecx
0x180015514  cmp     esi, 0FFFFFFFEh
0x180015517  jnz     short loc_180015546
0x180015519  mov     byte ptr [r9+38h], 1
0x18001551e  and     dword ptr [r9+34h], 0
0x180015523  mov     byte ptr [r9+30h], 1
0x180015528  mov     dword ptr [r9+2Ch], 9
0x180015530  or      eax, 0FFFFFFFFh
0x180015533  mov     rbx, [rsp+58h+arg_10]
0x180015538  add     rsp, 30h
0x18001553c  pop     r15
0x18001553e  pop     r14
0x180015540  pop     r13
0x180015542  pop     r12
0x180015544  pop     rsi
0x180015545  retn
0x180015546  test    ecx, ecx
0x180015548  js      short loc_180015559
0x18001554a  cmp     esi, cs:_nhandle
0x180015550  jnb     short loc_180015559
0x180015552  mov     eax, 1
0x180015557  jmp     short loc_18001555B
0x180015559  xor     eax, eax
0x18001555b  test    eax, eax
0x18001555d  jnz     short loc_180015592
0x18001555f  mov     byte ptr [r9+38h], 1
0x180015564  and     dword ptr [r9+34h], 0
0x180015569  mov     byte ptr [r9+30h], 1
0x18001556e  mov     dword ptr [r9+2Ch], 9
0x180015576  mov     [rsp+58h+var_30], rbx; __crt_cached_ptd_host *
0x18001557b  and     [rsp+58h+var_38], 0
0x180015581  xor     r9d, r9d; LineNo
0x180015584  xor     r8d, r8d; FileName
0x180015587  xor     edx, edx; FunctionName
0x180015589  xor     ecx, ecx; Expression
0x18001558b  call    _invalid_parameter_internal
0x180015590  jmp     short loc_180015530
0x180015592  mov     rax, rsi
0x180015595  mov     r15, rsi
0x180015598  sar     r15, 6
0x18001559c  lea     rcx, __pioinfo
0x1800155a3  and     eax, 3Fh
0x1800155a6  lea     r12, [rax+rax*8]
0x1800155aa  mov     rax, [rcx+r15*8]
0x1800155ae  test    byte ptr [rax+r12*8+38h], 1
0x1800155b4  jz      short loc_18001555F
0x1800155b6  mov     ecx, esi
0x1800155b8  call    __acrt_lowio_lock_fh
0x1800155bd  or      r14d, 0FFFFFFFFh
0x1800155c1  lea     rax, __pioinfo
0x1800155c8  mov     rax, [rax+r15*8]
0x1800155cc  test    byte ptr [rax+r12*8+38h], 1
0x1800155d2  jnz     short loc_1800155E9
0x1800155d4  mov     byte ptr [rbx+30h], 1
0x1800155d8  mov     dword ptr [rbx+2Ch], 9
0x1800155df  mov     byte ptr [rbx+38h], 1
0x1800155e3  and     dword ptr [rbx+34h], 0
0x1800155e7  jmp     short loc_1800155FE
0x1800155e9  mov     r9, rbx
0x1800155ec  mov     r8d, r13d
0x1800155ef  mov     rdx, [rsp+58h+arg_8]
0x1800155f4  mov     ecx, esi
0x1800155f6  call    _write_nolock
0x1800155fb  mov     r14d, eax
0x1800155fe  mov     ecx, esi
0x180015600  call    __acrt_lowio_unlock_fh
0x180015605  mov     eax, r14d
0x180015608  jmp     loc_180015533
0x1800612d3  push    rbp
0x1800612d5  sub     rsp, 30h
0x1800612d9  mov     rbp, rdx
0x1800612dc  mov     ecx, [rbp+60h]
0x1800612df  add     rsp, 30h
0x1800612e3  pop     rbp
0x1800612e4  jmp     __acrt_lowio_unlock_fh
```
