# common_lseek_long_

- ea: `0x18001b1e4`
- end: `0x18001b2ff`
- name: `common_lseek_long_`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001b664`
- `0x18001b6fc`

## callees

- `0x180007b48`
- `0x180014a6c`
- `0x180014b54`
- `0x18001b1e4`
- `0x18001b420`

## pseudocode

```c
__int64 __fastcall common_lseek_long_(unsigned int a1, unsigned int a2, unsigned int a3, __int64 a4)
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
  v8 = (a1 & 0x80000000) == 0 && a1 < nhandle;
  if ( !v8 || (v9 = (__int64)(int)a1 >> 6, (*(_BYTE *)(_pioinfo[v9] + 72LL * (a1 & 0x3F) + 56) & 1) == 0) )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)a4);
    return 0xFFFFFFFFLL;
  }
  _acrt_lowio_lock_fh(a1);
  v10 = -1;
  if ( (*(_BYTE *)(_pioinfo[v9] + 72LL * (a1 & 0x3F) + 56) & 1) != 0 )
  {
    v10 = common_lseek_nolock_long_(a1, a2, a3, a4);
  }
  else
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
  }
  _acrt_lowio_unlock_fh(a1);
  return v10;
}

```

## disassembly

```asm
0x18001b1e4  mov     [rsp+arg_10], rbx
0x18001b1e9  mov     [rsp+arg_8], edx
0x18001b1ed  mov     [rsp+arg_0], ecx
0x18001b1f1  push    rsi
0x18001b1f2  push    r12
0x18001b1f4  push    r13
0x18001b1f6  push    r14
0x18001b1f8  push    r15
0x18001b1fa  sub     rsp, 30h
0x18001b1fe  mov     rbx, r9
0x18001b201  mov     r13d, r8d
0x18001b204  movsxd  rsi, ecx
0x18001b207  cmp     esi, 0FFFFFFFEh
0x18001b20a  jnz     short loc_18001B239
0x18001b20c  mov     byte ptr [r9+38h], 1
0x18001b211  and     dword ptr [r9+34h], 0
0x18001b216  mov     byte ptr [r9+30h], 1
0x18001b21b  mov     dword ptr [r9+2Ch], 9
0x18001b223  or      eax, 0FFFFFFFFh
0x18001b226  mov     rbx, [rsp+58h+arg_10]
0x18001b22b  add     rsp, 30h
0x18001b22f  pop     r15
0x18001b231  pop     r14
0x18001b233  pop     r13
0x18001b235  pop     r12
0x18001b237  pop     rsi
0x18001b238  retn
0x18001b239  test    ecx, ecx
0x18001b23b  js      short loc_18001B24C
0x18001b23d  cmp     esi, cs:_nhandle
0x18001b243  jnb     short loc_18001B24C
0x18001b245  mov     eax, 1
0x18001b24a  jmp     short loc_18001B24E
0x18001b24c  xor     eax, eax
0x18001b24e  test    eax, eax
0x18001b250  jnz     short loc_18001B285
0x18001b252  mov     byte ptr [r9+38h], 1
0x18001b257  and     dword ptr [r9+34h], 0
0x18001b25c  mov     byte ptr [r9+30h], 1
0x18001b261  mov     dword ptr [r9+2Ch], 9
0x18001b269  mov     [rsp+58h+var_30], rbx; __crt_cached_ptd_host *
0x18001b26e  and     [rsp+58h+var_38], 0
0x18001b274  xor     r9d, r9d; LineNo
0x18001b277  xor     r8d, r8d; FileName
0x18001b27a  xor     edx, edx; FunctionName
0x18001b27c  xor     ecx, ecx; Expression
0x18001b27e  call    _invalid_parameter_internal
0x18001b283  jmp     short loc_18001B223
0x18001b285  mov     rax, rsi
0x18001b288  mov     r15, rsi
0x18001b28b  sar     r15, 6
0x18001b28f  lea     rcx, __pioinfo
0x18001b296  and     eax, 3Fh
0x18001b299  lea     r12, [rax+rax*8]
0x18001b29d  mov     rax, [rcx+r15*8]
0x18001b2a1  test    byte ptr [rax+r12*8+38h], 1
0x18001b2a7  jz      short loc_18001B252
0x18001b2a9  mov     ecx, esi
0x18001b2ab  call    __acrt_lowio_lock_fh
0x18001b2b0  or      r14d, 0FFFFFFFFh
0x18001b2b4  lea     rax, __pioinfo
0x18001b2bb  mov     rax, [rax+r15*8]
0x18001b2bf  test    byte ptr [rax+r12*8+38h], 1
0x18001b2c5  jnz     short loc_18001B2DC
0x18001b2c7  mov     byte ptr [rbx+30h], 1
0x18001b2cb  mov     dword ptr [rbx+2Ch], 9
0x18001b2d2  mov     byte ptr [rbx+38h], 1
0x18001b2d6  and     dword ptr [rbx+34h], 0
0x18001b2da  jmp     short loc_18001B2F0
0x18001b2dc  mov     r9, rbx
0x18001b2df  mov     r8d, r13d
0x18001b2e2  mov     edx, [rsp+58h+arg_8]
0x18001b2e6  mov     ecx, esi
0x18001b2e8  call    common_lseek_nolock_long_
0x18001b2ed  mov     r14d, eax
0x18001b2f0  mov     ecx, esi
0x18001b2f2  call    __acrt_lowio_unlock_fh
0x18001b2f7  mov     eax, r14d
0x18001b2fa  jmp     loc_18001B226
```
