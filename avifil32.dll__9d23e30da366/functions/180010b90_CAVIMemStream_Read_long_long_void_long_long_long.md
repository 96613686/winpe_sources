# CAVIMemStream::Read(long,long,void *,long,long *,long *)

- ea: `0x180010b90`
- end: `0x180010c99`
- name: `?Read@CAVIMemStream@@UEAAJJJPEAXJPEAJ1@Z`
- size: `265`
- prototype: `int(CAVIMemStream *__hidden this, int, int, void *, int, int *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180010b90`
- `0x180017365`

## pseudocode

```c
__int64 __fastcall CAVIMemStream::Read(CAVIMemStream *this, int a2, int a3, void *a4, int a5, int *a6, int *a7)
{
  unsigned int v8; // ecx
  int v9; // r11d
  __int64 result; // rax
  int v11; // eax

  if ( a2 + a3 > *((_DWORD *)this + 21) )
    a3 = *((_DWORD *)this + 21) - a2;
  if ( !a3 || a2 >= *((_DWORD *)this + 21) )
  {
    if ( a6 )
      *a6 = 0;
    if ( a7 )
      *a7 = 0;
  }
  v8 = *((_DWORD *)this + 25);
  if ( v8 )
  {
    if ( a3 <= 0 )
    {
      v9 = a5 / v8;
    }
    else
    {
      v9 = a5 / (int)v8;
      if ( a3 < a5 / (int)v8 )
        v9 = a3;
    }
    if ( a6 )
      *a6 = v9 * v8;
    if ( a7 )
      *a7 = v9;
    if ( a4 )
    {
      memmove_0(
        a4,
        (const void *)(*((_QWORD *)this + 5) + (unsigned int)(a2 * *((_DWORD *)this + 25))),
        (unsigned int)(v9 * *((_DWORD *)this + 25)));
      if ( a5 < *((_DWORD *)this + 25) )
        return 2147762292LL;
    }
    return 0;
  }
  if ( a6 )
    *a6 = *((_DWORD *)this + 12);
  if ( a7 )
    *a7 = 1;
  if ( !a4 )
    return 0;
  v11 = *((_DWORD *)this + 12);
  if ( a5 < v11 )
    v11 = a5;
  memmove_0(a4, *((const void **)this + 5), v11);
  result = 0;
  if ( a5 < *((_DWORD *)this + 12) )
    return 2147762292LL;
  return result;
}

```

## disassembly

```asm
0x180010b90  push    rbx
0x180010b92  push    rbp
0x180010b93  push    rsi
0x180010b94  push    rdi
0x180010b95  sub     rsp, 28h
0x180010b99  lea     eax, [rdx+r8]
0x180010b9d  mov     rsi, r9
0x180010ba0  mov     ebx, edx
0x180010ba2  mov     rdi, rcx
0x180010ba5  cmp     eax, [rcx+54h]
0x180010ba8  jle     short loc_180010BB1
0x180010baa  mov     r8d, [rcx+54h]
0x180010bae  sub     r8d, edx
0x180010bb1  mov     r9, [rsp+48h+arg_30]
0x180010bb9  mov     r10, [rsp+48h+arg_28]
0x180010bbe  test    r8d, r8d
0x180010bc1  jz      short loc_180010BC8
0x180010bc3  cmp     ebx, [rcx+54h]
0x180010bc6  jl      short loc_180010BE0
0x180010bc8  test    r10, r10
0x180010bcb  jz      short loc_180010BD4
0x180010bcd  mov     dword ptr [r10], 0
0x180010bd4  test    r9, r9
0x180010bd7  jz      short loc_180010BE0
0x180010bd9  mov     dword ptr [r9], 0
0x180010be0  mov     ecx, [rcx+64h]
0x180010be3  test    ecx, ecx
0x180010be5  jz      short loc_180010C48
0x180010be7  mov     ebp, [rsp+48h+arg_20]
0x180010beb  mov     eax, ebp
0x180010bed  test    r8d, r8d
0x180010bf0  jle     short loc_180010C01
0x180010bf2  cdq
0x180010bf3  idiv    ecx
0x180010bf5  cmp     r8d, eax
0x180010bf8  mov     r11d, eax
0x180010bfb  cmovl   r11d, r8d
0x180010bff  jmp     short loc_180010C08
0x180010c01  xor     edx, edx
0x180010c03  div     ecx
0x180010c05  mov     r11d, eax
0x180010c08  test    r10, r10
0x180010c0b  jz      short loc_180010C14
0x180010c0d  imul    ecx, r11d
0x180010c11  mov     [r10], ecx
0x180010c14  test    r9, r9
0x180010c17  jz      short loc_180010C1C
0x180010c19  mov     [r9], r11d
0x180010c1c  test    rsi, rsi
0x180010c1f  jz      short loc_180010C8E
0x180010c21  mov     ecx, [rdi+64h]
0x180010c24  mov     r8d, ecx
0x180010c27  imul    ecx, ebx
0x180010c2a  imul    r8d, r11d; Size
0x180010c2e  mov     edx, ecx
0x180010c30  mov     rcx, rsi; void *
0x180010c33  add     rdx, [rdi+28h]; Src
0x180010c37  call    memmove_0
0x180010c3c  cmp     ebp, [rdi+64h]
0x180010c3f  jge     short loc_180010C8E
0x180010c41  mov     eax, 80044074h
0x180010c46  jmp     short loc_180010C90
0x180010c48  test    r10, r10
0x180010c4b  jz      short loc_180010C53
0x180010c4d  mov     eax, [rdi+30h]
0x180010c50  mov     [r10], eax
0x180010c53  test    r9, r9
0x180010c56  jz      short loc_180010C5F
0x180010c58  mov     dword ptr [r9], 1
0x180010c5f  test    rsi, rsi
0x180010c62  jz      short loc_180010C8E
0x180010c64  mov     eax, [rdi+30h]
0x180010c67  mov     rcx, rsi; void *
0x180010c6a  mov     ebx, [rsp+48h+arg_20]
0x180010c6e  cmp     ebx, eax
0x180010c70  mov     rdx, [rdi+28h]; Src
0x180010c74  cmovl   eax, ebx
0x180010c77  movsxd  r8, eax; Size
0x180010c7a  call    memmove_0
0x180010c7f  xor     eax, eax
0x180010c81  mov     ecx, 80044074h
0x180010c86  cmp     ebx, [rdi+30h]
0x180010c89  cmovl   eax, ecx
0x180010c8c  jmp     short loc_180010C90
0x180010c8e  xor     eax, eax
0x180010c90  add     rsp, 28h
0x180010c94  pop     rdi
0x180010c95  pop     rsi
0x180010c96  pop     rbp
0x180010c97  pop     rbx
0x180010c98  retn
```
