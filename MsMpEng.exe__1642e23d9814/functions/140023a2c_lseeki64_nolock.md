# _lseeki64_nolock

- ea: `0x140023a2c`
- end: `0x140023ac6`
- name: `_lseeki64_nolock`
- size: `154`
- prototype: `union _LARGE_INTEGER __fastcall(int, LARGE_INTEGER, DWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002213c`
- `0x1400225d0`
- `0x140023ad0`
- `0x140023ccc`
- `0x14002411c`
- `0x140024654`

## callees

- `0x140011f80`
- `0x14002397c`
- `0x140023a2c`

## pseudocode

```c
union _LARGE_INTEGER __fastcall lseeki64_nolock(int a1, LARGE_INTEGER a2, DWORD a3)
{
  union _LARGE_INTEGER v3; // rdi
  int v4; // ebx
  int v5; // ebx
  _QWORD v7[2]; // [rsp+20h] [rbp-40h] BYREF
  char v8; // [rsp+30h] [rbp-30h]
  __int128 v9; // [rsp+38h] [rbp-28h]
  char v10; // [rsp+48h] [rbp-18h]
  int v11; // [rsp+4Ch] [rbp-14h]
  char v12; // [rsp+50h] [rbp-10h]
  int v13; // [rsp+54h] [rbp-Ch]
  char v14; // [rsp+58h] [rbp-8h]

  v7[0] = 0;
  v8 = 0;
  v10 = 0;
  v12 = 0;
  v14 = 0;
  if ( !dword_14003E558 )
  {
    v10 = 1;
    v9 = *(_OWORD *)&off_14003C8F8;
  }
  v3 = common_lseek_nolock<__int64>(a1, a2, a3, (__int64)v7);
  if ( v10 == 2 )
    *(_DWORD *)(v7[0] + 936LL) &= ~2u;
  if ( v12 )
  {
    v4 = v11;
    *(_DWORD *)(unknown_libname_33(v7) + 32) = v4;
  }
  if ( v14 )
  {
    v5 = v13;
    *(_DWORD *)(unknown_libname_33(v7) + 36) = v5;
  }
  return v3;
}

```

## disassembly

```asm
0x140023a2c  mov     [rsp-8+arg_0], rbx
0x140023a31  mov     [rsp-8+arg_8], rdi
0x140023a36  push    rbp
0x140023a37  mov     rbp, rsp
0x140023a3a  sub     rsp, 60h
0x140023a3e  and     [rbp+var_40], 0
0x140023a43  cmp     cs:dword_14003E558, 0
0x140023a4a  mov     [rbp+var_30], 0
0x140023a4e  mov     [rbp+var_18], 0
0x140023a52  mov     [rbp+var_10], 0
0x140023a56  mov     [rbp+var_8], 0
0x140023a5a  jnz     short loc_140023A6C
0x140023a5c  movups  xmm0, xmmword ptr cs:off_14003C8F8
0x140023a63  mov     [rbp+var_18], 1
0x140023a67  movdqu  [rbp+var_28], xmm0
0x140023a6c  lea     r9, [rbp+var_40]
0x140023a70  call    ??$common_lseek_nolock@_J@@YA_JH_JHAEAV__crt_cached_ptd_host@@@Z
0x140023a75  cmp     [rbp+var_18], 2
0x140023a79  mov     rdi, rax
0x140023a7c  jnz     short loc_140023A89
0x140023a7e  mov     rcx, [rbp+var_40]
0x140023a82  and     dword ptr [rcx+3A8h], 0FFFFFFFDh
0x140023a89  cmp     [rbp+var_10], 0
0x140023a8d  jz      short loc_140023A9E
0x140023a8f  mov     ebx, [rbp+var_14]
0x140023a92  lea     rcx, [rbp+var_40]
0x140023a96  call    unknown_libname_33; Microsoft VisualC 64bit universal runtime
0x140023a9b  mov     [rax+20h], ebx
0x140023a9e  cmp     [rbp+var_8], 0
0x140023aa2  jz      short loc_140023AB3
0x140023aa4  mov     ebx, [rbp+var_C]
0x140023aa7  lea     rcx, [rbp+var_40]
0x140023aab  call    unknown_libname_33; Microsoft VisualC 64bit universal runtime
0x140023ab0  mov     [rax+24h], ebx
0x140023ab3  mov     rbx, [rsp+60h+arg_0]
0x140023ab8  mov     rax, rdi
0x140023abb  mov     rdi, [rsp+60h+arg_8]
0x140023ac0  add     rsp, 60h
0x140023ac4  pop     rbp
0x140023ac5  retn
```
