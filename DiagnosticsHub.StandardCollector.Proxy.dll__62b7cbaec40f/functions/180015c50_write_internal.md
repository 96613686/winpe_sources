# _write_internal

- ea: `0x180015c50`
- end: `0x180015d6d`
- name: `_write_internal`
- size: `285`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f900`
- `0x180015bb8`
- `0x18005ca6c`
- `0x18005cb64`

## callees

- `0x180007b48`
- `0x180014a6c`
- `0x180014b54`
- `0x180015c50`
- `0x180015d70`

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
0x180015c50  mov     [rsp+arg_10], rbx
0x180015c55  mov     [rsp+arg_8], rdx
0x180015c5a  mov     [rsp+arg_0], ecx
0x180015c5e  push    rsi
0x180015c5f  push    r12
0x180015c61  push    r13
0x180015c63  push    r14
0x180015c65  push    r15
0x180015c67  sub     rsp, 30h
0x180015c6b  mov     rbx, r9
0x180015c6e  mov     r13d, r8d
0x180015c71  movsxd  rsi, ecx
0x180015c74  cmp     esi, 0FFFFFFFEh
0x180015c77  jnz     short loc_180015CA6
0x180015c79  mov     byte ptr [r9+38h], 1
0x180015c7e  and     dword ptr [r9+34h], 0
0x180015c83  mov     byte ptr [r9+30h], 1
0x180015c88  mov     dword ptr [r9+2Ch], 9
0x180015c90  or      eax, 0FFFFFFFFh
0x180015c93  mov     rbx, [rsp+58h+arg_10]
0x180015c98  add     rsp, 30h
0x180015c9c  pop     r15
0x180015c9e  pop     r14
0x180015ca0  pop     r13
0x180015ca2  pop     r12
0x180015ca4  pop     rsi
0x180015ca5  retn
0x180015ca6  test    ecx, ecx
0x180015ca8  js      short loc_180015CB9
0x180015caa  cmp     esi, cs:_nhandle
0x180015cb0  jnb     short loc_180015CB9
0x180015cb2  mov     eax, 1
0x180015cb7  jmp     short loc_180015CBB
0x180015cb9  xor     eax, eax
0x180015cbb  test    eax, eax
0x180015cbd  jnz     short loc_180015CF2
0x180015cbf  mov     byte ptr [r9+38h], 1
0x180015cc4  and     dword ptr [r9+34h], 0
0x180015cc9  mov     byte ptr [r9+30h], 1
0x180015cce  mov     dword ptr [r9+2Ch], 9
0x180015cd6  mov     [rsp+58h+var_30], rbx; __crt_cached_ptd_host *
0x180015cdb  and     [rsp+58h+var_38], 0
0x180015ce1  xor     r9d, r9d; LineNo
0x180015ce4  xor     r8d, r8d; FileName
0x180015ce7  xor     edx, edx; FunctionName
0x180015ce9  xor     ecx, ecx; Expression
0x180015ceb  call    _invalid_parameter_internal
0x180015cf0  jmp     short loc_180015C90
0x180015cf2  mov     rax, rsi
0x180015cf5  mov     r15, rsi
0x180015cf8  sar     r15, 6
0x180015cfc  lea     rcx, __pioinfo
0x180015d03  and     eax, 3Fh
0x180015d06  lea     r12, [rax+rax*8]
0x180015d0a  mov     rax, [rcx+r15*8]
0x180015d0e  test    byte ptr [rax+r12*8+38h], 1
0x180015d14  jz      short loc_180015CBF
0x180015d16  mov     ecx, esi
0x180015d18  call    __acrt_lowio_lock_fh
0x180015d1d  or      r14d, 0FFFFFFFFh
0x180015d21  lea     rax, __pioinfo
0x180015d28  mov     rax, [rax+r15*8]
0x180015d2c  test    byte ptr [rax+r12*8+38h], 1
0x180015d32  jnz     short loc_180015D49
0x180015d34  mov     byte ptr [rbx+30h], 1
0x180015d38  mov     dword ptr [rbx+2Ch], 9
0x180015d3f  mov     byte ptr [rbx+38h], 1
0x180015d43  and     dword ptr [rbx+34h], 0
0x180015d47  jmp     short loc_180015D5E
0x180015d49  mov     r9, rbx
0x180015d4c  mov     r8d, r13d
0x180015d4f  mov     rdx, [rsp+58h+arg_8]
0x180015d54  mov     ecx, esi
0x180015d56  call    _write_nolock
0x180015d5b  mov     r14d, eax
0x180015d5e  mov     ecx, esi
0x180015d60  call    __acrt_lowio_unlock_fh
0x180015d65  mov     eax, r14d
0x180015d68  jmp     loc_180015C93
0x1800615b3  push    rbp
0x1800615b5  sub     rsp, 30h
0x1800615b9  mov     rbp, rdx
0x1800615bc  mov     ecx, [rbp+60h]
0x1800615bf  add     rsp, 30h
0x1800615c3  pop     rbp
0x1800615c4  jmp     __acrt_lowio_unlock_fh
```
