# CDumpWriter::WriteHeader(void)

- ea: `0x180002954`
- end: `0x1800029f9`
- name: `?WriteHeader@CDumpWriter@@AEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(CDumpWriter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002440`

## callees

- `0x180001400`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CDumpWriter::WriteHeader(CDumpWriter *this)
{
  __int64 v1; // rax
  __int64 v2; // rcx
  __int64 result; // rax
  _DWORD v4[4]; // [rsp+30h] [rbp-9h] BYREF
  _OWORD v5[2]; // [rsp+40h] [rbp+7h] BYREF
  int v6; // [rsp+60h] [rbp+27h]
  int v7; // [rsp+64h] [rbp+2Bh]
  __int64 v8; // [rsp+68h] [rbp+2Fh]
  int v9; // [rsp+70h] [rbp+37h]
  int v10; // [rsp+74h] [rbp+3Bh]
  __int64 v11; // [rsp+78h] [rbp+3Fh]

  v10 = *((_DWORD *)this + 26);
  v1 = *((_QWORD *)this + 2);
  v2 = *((_QWORD *)this + 1);
  v8 = v1;
  v5[0] = xmmword_1800047F0;
  v6 = 2;
  v5[1] = xmmword_180004800;
  v7 = 64;
  v9 = 539;
  v11 = 32;
  v4[0] = 0;
  result = (*(__int64 (__fastcall **)(__int64, _OWORD *, __int64, _DWORD *))(*(_QWORD *)v2 + 32LL))(v2, v5, 64, v4);
  if ( v4[0] != 64 )
    return 2147549183LL;
  return result;
}

```

## disassembly

```asm
0x180002954  push    rbp
0x180002956  lea     rbp, [rsp-57h]
0x18000295b  sub     rsp, 90h
0x180002962  mov     rax, cs:__security_cookie
0x180002969  xor     rax, rsp
0x18000296c  mov     [rbp+57h+var_10], rax
0x180002970  mov     eax, [rcx+68h]
0x180002973  lea     r9, [rbp+57h+var_60]
0x180002977  movups  xmm0, cs:xmmword_1800047F0
0x18000297e  mov     [rbp+57h+var_1C], eax
0x180002981  mov     r8d, 40h ; '@'
0x180002987  mov     rax, [rcx+10h]
0x18000298b  lea     rdx, [rbp+57h+var_50]
0x18000298f  mov     rcx, [rcx+8]
0x180002993  movups  xmm1, cs:xmmword_180004800
0x18000299a  mov     [rbp+57h+var_28], rax
0x18000299e  movdqu  [rbp+57h+var_50], xmm0
0x1800029a3  mov     [rbp+57h+var_30], 2
0x1800029aa  movdqu  [rbp+57h+var_40], xmm1
0x1800029af  mov     [rbp+57h+var_2C], 40h ; '@'
0x1800029b6  mov     [rbp+57h+var_20], 21Bh
0x1800029bd  mov     [rbp+57h+var_18], 20h ; ' '
0x1800029c5  mov     [rbp+57h+var_60], 0
0x1800029cc  mov     rax, [rcx]
0x1800029cf  mov     rax, [rax+20h]
0x1800029d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d8  cmp     [rbp+57h+var_60], 40h ; '@'
0x1800029dc  mov     ecx, 8000FFFFh
0x1800029e1  cmovnz  eax, ecx
0x1800029e4  mov     rcx, [rbp+57h+var_10]
0x1800029e8  xor     rcx, rsp; StackCookie
0x1800029eb  call    __security_check_cookie
0x1800029f0  add     rsp, 90h
0x1800029f7  pop     rbp
0x1800029f8  retn
```
