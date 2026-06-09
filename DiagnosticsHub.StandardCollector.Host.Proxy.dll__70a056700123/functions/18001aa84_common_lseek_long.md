# common_lseek_long_

- ea: `0x18001aa84`
- end: `0x18001ab9f`
- name: `common_lseek_long_`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001af04`
- `0x18001af9c`

## callees

- `0x1800073e8`
- `0x18001430c`
- `0x1800143f4`
- `0x18001aa84`
- `0x18001acc0`

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
0x18001aa84  mov     [rsp+arg_10], rbx
0x18001aa89  mov     [rsp+arg_8], edx
0x18001aa8d  mov     [rsp+arg_0], ecx
0x18001aa91  push    rsi
0x18001aa92  push    r12
0x18001aa94  push    r13
0x18001aa96  push    r14
0x18001aa98  push    r15
0x18001aa9a  sub     rsp, 30h
0x18001aa9e  mov     rbx, r9
0x18001aaa1  mov     r13d, r8d
0x18001aaa4  movsxd  rsi, ecx
0x18001aaa7  cmp     esi, 0FFFFFFFEh
0x18001aaaa  jnz     short loc_18001AAD9
0x18001aaac  mov     byte ptr [r9+38h], 1
0x18001aab1  and     dword ptr [r9+34h], 0
0x18001aab6  mov     byte ptr [r9+30h], 1
0x18001aabb  mov     dword ptr [r9+2Ch], 9
0x18001aac3  or      eax, 0FFFFFFFFh
0x18001aac6  mov     rbx, [rsp+58h+arg_10]
0x18001aacb  add     rsp, 30h
0x18001aacf  pop     r15
0x18001aad1  pop     r14
0x18001aad3  pop     r13
0x18001aad5  pop     r12
0x18001aad7  pop     rsi
0x18001aad8  retn
0x18001aad9  test    ecx, ecx
0x18001aadb  js      short loc_18001AAEC
0x18001aadd  cmp     esi, cs:_nhandle
0x18001aae3  jnb     short loc_18001AAEC
0x18001aae5  mov     eax, 1
0x18001aaea  jmp     short loc_18001AAEE
0x18001aaec  xor     eax, eax
0x18001aaee  test    eax, eax
0x18001aaf0  jnz     short loc_18001AB25
0x18001aaf2  mov     byte ptr [r9+38h], 1
0x18001aaf7  and     dword ptr [r9+34h], 0
0x18001aafc  mov     byte ptr [r9+30h], 1
0x18001ab01  mov     dword ptr [r9+2Ch], 9
0x18001ab09  mov     [rsp+58h+var_30], rbx; __crt_cached_ptd_host *
0x18001ab0e  and     [rsp+58h+var_38], 0
0x18001ab14  xor     r9d, r9d; LineNo
0x18001ab17  xor     r8d, r8d; FileName
0x18001ab1a  xor     edx, edx; FunctionName
0x18001ab1c  xor     ecx, ecx; Expression
0x18001ab1e  call    _invalid_parameter_internal
0x18001ab23  jmp     short loc_18001AAC3
0x18001ab25  mov     rax, rsi
0x18001ab28  mov     r15, rsi
0x18001ab2b  sar     r15, 6
0x18001ab2f  lea     rcx, __pioinfo
0x18001ab36  and     eax, 3Fh
0x18001ab39  lea     r12, [rax+rax*8]
0x18001ab3d  mov     rax, [rcx+r15*8]
0x18001ab41  test    byte ptr [rax+r12*8+38h], 1
0x18001ab47  jz      short loc_18001AAF2
0x18001ab49  mov     ecx, esi
0x18001ab4b  call    __acrt_lowio_lock_fh
0x18001ab50  or      r14d, 0FFFFFFFFh
0x18001ab54  lea     rax, __pioinfo
0x18001ab5b  mov     rax, [rax+r15*8]
0x18001ab5f  test    byte ptr [rax+r12*8+38h], 1
0x18001ab65  jnz     short loc_18001AB7C
0x18001ab67  mov     byte ptr [rbx+30h], 1
0x18001ab6b  mov     dword ptr [rbx+2Ch], 9
0x18001ab72  mov     byte ptr [rbx+38h], 1
0x18001ab76  and     dword ptr [rbx+34h], 0
0x18001ab7a  jmp     short loc_18001AB90
0x18001ab7c  mov     r9, rbx
0x18001ab7f  mov     r8d, r13d
0x18001ab82  mov     edx, [rsp+58h+arg_8]
0x18001ab86  mov     ecx, esi
0x18001ab88  call    common_lseek_nolock_long_
0x18001ab8d  mov     r14d, eax
0x18001ab90  mov     ecx, esi
0x18001ab92  call    __acrt_lowio_unlock_fh
0x18001ab97  mov     eax, r14d
0x18001ab9a  jmp     loc_18001AAC6
```
