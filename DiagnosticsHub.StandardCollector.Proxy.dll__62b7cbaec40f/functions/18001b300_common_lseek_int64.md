# common_lseek___int64_

- ea: `0x18001b300`
- end: `0x18001b41e`
- name: `common_lseek___int64_`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001b7a4`
- `0x18001b840`

## callees

- `0x180007b48`
- `0x180014a6c`
- `0x180014b54`
- `0x18001b300`
- `0x18001b4ac`

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
0x18001b300  mov     [rsp+arg_10], rbx
0x18001b305  mov     [rsp+arg_8], rdx
0x18001b30a  mov     [rsp+arg_0], ecx
0x18001b30e  push    rsi
0x18001b30f  push    r12
0x18001b311  push    r13
0x18001b313  push    r14
0x18001b315  push    r15
0x18001b317  sub     rsp, 30h
0x18001b31b  mov     rbx, r9
0x18001b31e  mov     r13d, r8d
0x18001b321  movsxd  rsi, ecx
0x18001b324  cmp     esi, 0FFFFFFFEh
0x18001b327  jnz     short loc_18001B357
0x18001b329  mov     byte ptr [r9+38h], 1
0x18001b32e  and     dword ptr [r9+34h], 0
0x18001b333  mov     byte ptr [r9+30h], 1
0x18001b338  mov     dword ptr [r9+2Ch], 9
0x18001b340  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b344  mov     rbx, [rsp+58h+arg_10]
0x18001b349  add     rsp, 30h
0x18001b34d  pop     r15
0x18001b34f  pop     r14
0x18001b351  pop     r13
0x18001b353  pop     r12
0x18001b355  pop     rsi
0x18001b356  retn
0x18001b357  test    ecx, ecx
0x18001b359  js      short loc_18001B36A
0x18001b35b  cmp     esi, cs:_nhandle
0x18001b361  jnb     short loc_18001B36A
0x18001b363  mov     eax, 1
0x18001b368  jmp     short loc_18001B36C
0x18001b36a  xor     eax, eax
0x18001b36c  test    eax, eax
0x18001b36e  jnz     short loc_18001B3A3
0x18001b370  mov     byte ptr [r9+38h], 1
0x18001b375  and     dword ptr [r9+34h], 0
0x18001b37a  mov     byte ptr [r9+30h], 1
0x18001b37f  mov     dword ptr [r9+2Ch], 9
0x18001b387  mov     [rsp+58h+var_30], rbx; __crt_cached_ptd_host *
0x18001b38c  and     [rsp+58h+var_38], 0
0x18001b392  xor     r9d, r9d; LineNo
0x18001b395  xor     r8d, r8d; FileName
0x18001b398  xor     edx, edx; FunctionName
0x18001b39a  xor     ecx, ecx; Expression
0x18001b39c  call    _invalid_parameter_internal
0x18001b3a1  jmp     short loc_18001B340
0x18001b3a3  mov     rax, rsi
0x18001b3a6  mov     r15, rsi
0x18001b3a9  sar     r15, 6
0x18001b3ad  lea     rcx, __pioinfo
0x18001b3b4  and     eax, 3Fh
0x18001b3b7  lea     r12, [rax+rax*8]
0x18001b3bb  mov     rax, [rcx+r15*8]
0x18001b3bf  test    byte ptr [rax+r12*8+38h], 1
0x18001b3c5  jz      short loc_18001B370
0x18001b3c7  mov     ecx, esi
0x18001b3c9  call    __acrt_lowio_lock_fh
0x18001b3ce  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001b3d2  lea     rax, __pioinfo
0x18001b3d9  mov     rax, [rax+r15*8]
0x18001b3dd  test    byte ptr [rax+r12*8+38h], 1
0x18001b3e3  jnz     short loc_18001B3FA
0x18001b3e5  mov     byte ptr [rbx+30h], 1
0x18001b3e9  mov     dword ptr [rbx+2Ch], 9
0x18001b3f0  mov     byte ptr [rbx+38h], 1
0x18001b3f4  and     dword ptr [rbx+34h], 0
0x18001b3f8  jmp     short loc_18001B40F
0x18001b3fa  mov     r9, rbx
0x18001b3fd  mov     r8d, r13d
0x18001b400  mov     rdx, [rsp+58h+arg_8]
0x18001b405  mov     ecx, esi
0x18001b407  call    common_lseek_nolock___int64_
0x18001b40c  mov     r14, rax
0x18001b40f  mov     ecx, esi
0x18001b411  call    __acrt_lowio_unlock_fh
0x18001b416  mov     rax, r14
0x18001b419  jmp     loc_18001B344
```
