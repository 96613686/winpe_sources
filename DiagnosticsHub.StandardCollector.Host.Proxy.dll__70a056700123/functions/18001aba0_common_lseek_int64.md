# common_lseek___int64_

- ea: `0x18001aba0`
- end: `0x18001acbe`
- name: `common_lseek___int64_`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001b044`
- `0x18001b0e0`

## callees

- `0x1800073e8`
- `0x18001430c`
- `0x1800143f4`
- `0x18001aba0`
- `0x18001ad4c`

## pseudocode

```c
__int64 __fastcall common_lseek___int64_(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
{
  BOOL v8; // eax
  __int64 v9; // r15
  LARGE_INTEGER v10; // r14

  if ( a1 == -2 )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    return -1;
  }
  v8 = a1 >= 0 && a1 < (unsigned int)nhandle;
  if ( !v8 || (v9 = (__int64)a1 >> 6, (*(_BYTE *)(_pioinfo[v9] + 72LL * (a1 & 0x3F) + 56) & 1) == 0) )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)a4);
    return -1;
  }
  _acrt_lowio_lock_fh((unsigned int)a1);
  v10.QuadPart = -1;
  if ( (*(_BYTE *)(_pioinfo[v9] + 72LL * (a1 & 0x3F) + 56) & 1) != 0 )
  {
    v10 = common_lseek_nolock___int64_(a1, a2, a3, a4);
  }
  else
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
  }
  _acrt_lowio_unlock_fh((unsigned int)a1);
  return v10.QuadPart;
}

```

## disassembly

```asm
0x18001aba0  mov     [rsp+arg_10], rbx
0x18001aba5  mov     [rsp+arg_8], rdx
0x18001abaa  mov     [rsp+arg_0], ecx
0x18001abae  push    rsi
0x18001abaf  push    r12
0x18001abb1  push    r13
0x18001abb3  push    r14
0x18001abb5  push    r15
0x18001abb7  sub     rsp, 30h
0x18001abbb  mov     rbx, r9
0x18001abbe  mov     r13d, r8d
0x18001abc1  movsxd  rsi, ecx
0x18001abc4  cmp     esi, 0FFFFFFFEh
0x18001abc7  jnz     short loc_18001ABF7
0x18001abc9  mov     byte ptr [r9+38h], 1
0x18001abce  and     dword ptr [r9+34h], 0
0x18001abd3  mov     byte ptr [r9+30h], 1
0x18001abd8  mov     dword ptr [r9+2Ch], 9
0x18001abe0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001abe4  mov     rbx, [rsp+58h+arg_10]
0x18001abe9  add     rsp, 30h
0x18001abed  pop     r15
0x18001abef  pop     r14
0x18001abf1  pop     r13
0x18001abf3  pop     r12
0x18001abf5  pop     rsi
0x18001abf6  retn
0x18001abf7  test    ecx, ecx
0x18001abf9  js      short loc_18001AC0A
0x18001abfb  cmp     esi, cs:_nhandle
0x18001ac01  jnb     short loc_18001AC0A
0x18001ac03  mov     eax, 1
0x18001ac08  jmp     short loc_18001AC0C
0x18001ac0a  xor     eax, eax
0x18001ac0c  test    eax, eax
0x18001ac0e  jnz     short loc_18001AC43
0x18001ac10  mov     byte ptr [r9+38h], 1
0x18001ac15  and     dword ptr [r9+34h], 0
0x18001ac1a  mov     byte ptr [r9+30h], 1
0x18001ac1f  mov     dword ptr [r9+2Ch], 9
0x18001ac27  mov     [rsp+58h+var_30], rbx; __crt_cached_ptd_host *
0x18001ac2c  and     [rsp+58h+var_38], 0
0x18001ac32  xor     r9d, r9d; LineNo
0x18001ac35  xor     r8d, r8d; FileName
0x18001ac38  xor     edx, edx; FunctionName
0x18001ac3a  xor     ecx, ecx; Expression
0x18001ac3c  call    _invalid_parameter_internal
0x18001ac41  jmp     short loc_18001ABE0
0x18001ac43  mov     rax, rsi
0x18001ac46  mov     r15, rsi
0x18001ac49  sar     r15, 6
0x18001ac4d  lea     rcx, __pioinfo
0x18001ac54  and     eax, 3Fh
0x18001ac57  lea     r12, [rax+rax*8]
0x18001ac5b  mov     rax, [rcx+r15*8]
0x18001ac5f  test    byte ptr [rax+r12*8+38h], 1
0x18001ac65  jz      short loc_18001AC10
0x18001ac67  mov     ecx, esi
0x18001ac69  call    __acrt_lowio_lock_fh
0x18001ac6e  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001ac72  lea     rax, __pioinfo
0x18001ac79  mov     rax, [rax+r15*8]
0x18001ac7d  test    byte ptr [rax+r12*8+38h], 1
0x18001ac83  jnz     short loc_18001AC9A
0x18001ac85  mov     byte ptr [rbx+30h], 1
0x18001ac89  mov     dword ptr [rbx+2Ch], 9
0x18001ac90  mov     byte ptr [rbx+38h], 1
0x18001ac94  and     dword ptr [rbx+34h], 0
0x18001ac98  jmp     short loc_18001ACAF
0x18001ac9a  mov     r9, rbx
0x18001ac9d  mov     r8d, r13d
0x18001aca0  mov     rdx, [rsp+58h+arg_8]
0x18001aca5  mov     ecx, esi
0x18001aca7  call    common_lseek_nolock___int64_
0x18001acac  mov     r14, rax
0x18001acaf  mov     ecx, esi
0x18001acb1  call    __acrt_lowio_unlock_fh
0x18001acb6  mov     rax, r14
0x18001acb9  jmp     loc_18001ABE4
```
