# CAudioTimeCompression::allocTemps(int,int)

- ea: `0x18004fd30`
- end: `0x18004feff`
- name: `?allocTemps@CAudioTimeCompression@@IEAAJHH@Z`
- size: `463`
- prototype: `__int64 __fastcall(CAudioTimeCompression *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004f270`

## callees

- `0x18004fd30`
- `0x180050f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fdb5`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fdd0`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fdf2`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fe0d`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fe28`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fe6c`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fe96`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fdb5`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fdd0`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fdf2`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fe0d`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fe28`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fe6c`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fe96`

## pseudocode

```c
__int64 __fastcall CAudioTimeCompression::allocTemps(CAudioTimeCompression *this, int a2, int a3)
{
  __int64 v3; // rsi
  int v6; // ecx
  int v7; // ebx
  int v8; // eax
  size_t v9; // rbp
  void *v10; // rax
  size_t v11; // rdx
  void *v12; // rax
  void *v13; // rax
  void *v14; // rax
  __int64 result; // rax

  v3 = a3;
  CAudioTimeCompression::freeTemps(this);
  if ( a2 <= 0 || (int)v3 <= 0 )
    return 2147942487LL;
  v6 = a2 + v3;
  if ( a2 > a2 + (int)v3 || (int)v3 > v6 )
    return 2147942414LL;
  v7 = 1;
  if ( v6 > 2048 )
    v6 = 2048;
  v8 = 0;
  while ( v7 < v6 )
  {
    v7 *= 2;
    if ( ++v8 >= 32 )
    {
      v7 = 0;
      break;
    }
  }
  if ( *((_BYTE *)this + 120) == 1 )
  {
    if ( v7 >= 2147483613 )
      return 2147942414LL;
    v9 = 4LL * v7;
    *((_QWORD *)this + 20) = _aligned_malloc(v9, 0x20u);
    v10 = _aligned_malloc(v9, 0x20u);
    v11 = 32;
  }
  else
  {
    v9 = 4LL * v7;
    *((_QWORD *)this + 20) = _aligned_malloc(v9, 0x10u);
    v10 = _aligned_malloc(v9, 0x10u);
    v11 = 16;
  }
  *((_QWORD *)this + 21) = v10;
  v12 = _aligned_malloc(v9, v11);
  *((_QWORD *)this + 22) = v12;
  if ( !*((_QWORD *)this + 20) )
    return 2147942414LL;
  if ( !*((_QWORD *)this + 21) )
    return 2147942414LL;
  if ( !v12 )
    return 2147942414LL;
  *((_DWORD *)this + 50) = v7;
  *((_DWORD *)this + 51) = v7;
  v13 = _aligned_malloc(v9, 0x10u);
  *((_QWORD *)this + 23) = v13;
  if ( !v13 )
    return 2147942414LL;
  *((_DWORD *)this + 52) = v3;
  v14 = _aligned_malloc(4 * v3, 0x10u);
  *((_QWORD *)this + 24) = v14;
  if ( !v14 )
    return 2147942414LL;
  result = 0;
  *((_DWORD *)this + 38) = v7;
  return result;
}

```

## disassembly

```asm
0x18004fd30  mov     [rsp+arg_8], rbx
0x18004fd35  mov     [rsp+arg_10], rsi
0x18004fd3a  push    rdi
0x18004fd3b  sub     rsp, 20h
0x18004fd3f  movsxd  rsi, r8d
0x18004fd42  mov     ebx, edx
0x18004fd44  mov     rdi, rcx
0x18004fd47  call    ?freeTemps@CAudioTimeCompression@@IEAAJXZ; CAudioTimeCompression::freeTemps(void)
0x18004fd4c  test    ebx, ebx
0x18004fd4e  jle     loc_18004FEE9
0x18004fd54  test    esi, esi
0x18004fd56  jle     loc_18004FEE9
0x18004fd5c  lea     ecx, [rbx+rsi]
0x18004fd5f  cmp     ebx, ecx
0x18004fd61  jg      loc_18004FED3
0x18004fd67  cmp     esi, ecx
0x18004fd69  jg      loc_18004FED3
0x18004fd6f  mov     eax, 800h
0x18004fd74  mov     ebx, 1
0x18004fd79  cmp     ecx, eax
0x18004fd7b  cmovg   ecx, eax
0x18004fd7e  xor     eax, eax
0x18004fd80  cmp     ebx, ecx
0x18004fd82  jge     short loc_18004FD8F
0x18004fd84  add     ebx, ebx
0x18004fd86  inc     eax
0x18004fd88  cmp     eax, 20h ; ' '
0x18004fd8b  jl      short loc_18004FD80
0x18004fd8d  xor     ebx, ebx
0x18004fd8f  cmp     byte ptr [rdi+78h], 1
0x18004fd93  mov     [rsp+28h+arg_0], rbp
0x18004fd98  jnz     short loc_18004FDE3
0x18004fd9a  cmp     ebx, 7FFFFFDDh
0x18004fda0  jge     loc_18004FECC
0x18004fda6  movsxd  rbp, ebx
0x18004fda9  mov     edx, 20h ; ' '; Alignment
0x18004fdae  shl     rbp, 2
0x18004fdb2  mov     rcx, rbp; Size
0x18004fdb5  call    cs:__imp__aligned_malloc
0x18004fdbc  nop     dword ptr [rax+rax+00h]
0x18004fdc1  mov     edx, 20h ; ' '; Alignment
0x18004fdc6  mov     rcx, rbp; Size
0x18004fdc9  mov     [rdi+0A0h], rax
0x18004fdd0  call    cs:__imp__aligned_malloc
0x18004fdd7  nop     dword ptr [rax+rax+00h]
0x18004fddc  mov     edx, 20h ; ' '
0x18004fde1  jmp     short loc_18004FE1E
0x18004fde3  movsxd  rbp, ebx
0x18004fde6  mov     edx, 10h; Alignment
0x18004fdeb  shl     rbp, 2
0x18004fdef  mov     rcx, rbp; Size
0x18004fdf2  call    cs:__imp__aligned_malloc
0x18004fdf9  nop     dword ptr [rax+rax+00h]
0x18004fdfe  mov     edx, 10h; Alignment
0x18004fe03  mov     rcx, rbp; Size
0x18004fe06  mov     [rdi+0A0h], rax
0x18004fe0d  call    cs:__imp__aligned_malloc
0x18004fe14  nop     dword ptr [rax+rax+00h]
0x18004fe19  mov     edx, 10h; Alignment
0x18004fe1e  mov     rcx, rbp; Size
0x18004fe21  mov     [rdi+0A8h], rax
0x18004fe28  call    cs:__imp__aligned_malloc
0x18004fe2f  nop     dword ptr [rax+rax+00h]
0x18004fe34  mov     [rdi+0B0h], rax
0x18004fe3b  cmp     qword ptr [rdi+0A0h], 0
0x18004fe43  jz      loc_18004FECC
0x18004fe49  cmp     qword ptr [rdi+0A8h], 0
0x18004fe51  jz      short loc_18004FECC
0x18004fe53  test    rax, rax
0x18004fe56  jz      short loc_18004FECC
0x18004fe58  mov     edx, 10h; Alignment
0x18004fe5d  mov     [rdi+0C8h], ebx
0x18004fe63  mov     rcx, rbp; Size
0x18004fe66  mov     [rdi+0CCh], ebx
0x18004fe6c  call    cs:__imp__aligned_malloc
0x18004fe73  nop     dword ptr [rax+rax+00h]
0x18004fe78  mov     [rdi+0B8h], rax
0x18004fe7f  test    rax, rax
0x18004fe82  jz      short loc_18004FECC
0x18004fe84  mov     rcx, rsi
0x18004fe87  mov     [rdi+0D0h], esi
0x18004fe8d  shl     rcx, 2; Size
0x18004fe91  mov     edx, 10h; Alignment
0x18004fe96  call    cs:__imp__aligned_malloc
0x18004fe9d  nop     dword ptr [rax+rax+00h]
0x18004fea2  mov     [rdi+0C0h], rax
0x18004fea9  test    rax, rax
0x18004feac  jz      short loc_18004FECC
0x18004feae  xor     eax, eax
0x18004feb0  mov     [rdi+98h], ebx
0x18004feb6  mov     rbp, [rsp+28h+arg_0]
0x18004febb  mov     rbx, [rsp+28h+arg_8]
0x18004fec0  mov     rsi, [rsp+28h+arg_10]
0x18004fec5  add     rsp, 20h
0x18004fec9  pop     rdi
0x18004feca  retn
0x18004fecc  mov     eax, 8007000Eh
0x18004fed1  jmp     short loc_18004FEB6
0x18004fed3  mov     eax, 8007000Eh
0x18004fed8  mov     rbx, [rsp+28h+arg_8]
0x18004fedd  mov     rsi, [rsp+28h+arg_10]
0x18004fee2  add     rsp, 20h
0x18004fee6  pop     rdi
0x18004fee7  retn
0x18004fee9  mov     rbx, [rsp+28h+arg_8]
0x18004feee  mov     eax, 80070057h
0x18004fef3  mov     rsi, [rsp+28h+arg_10]
0x18004fef8  add     rsp, 20h
0x18004fefc  pop     rdi
0x18004fefd  retn
```
