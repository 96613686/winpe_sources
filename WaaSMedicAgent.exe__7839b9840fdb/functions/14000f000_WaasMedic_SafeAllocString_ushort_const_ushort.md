# WaasMedic::SafeAllocString(ushort const *,ushort * *)

- ea: `0x14000f000`
- end: `0x14000f159`
- name: `?SafeAllocString@WaasMedic@@YAJPEBGPEAPEAG@Z`
- size: `345`
- prototype: `__int64 __fastcall(WaasMedic *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x140009580`
- `0x14000a8f0`

## callees

- `0x14000b470`
- `0x14000efd4`
- `0x14000f000`

## string_xrefs

- `0x14000f11c`: `Failed to copy client scenario param! hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::SafeAllocString(WaasMedic *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  WaasMedic *v4; // rdi
  WaasMedic *v5; // rax
  __int64 v6; // r8
  unsigned int v7; // ebx
  __int64 v8; // rbp
  _WORD *v9; // rax
  _WORD *v10; // r9
  unsigned __int64 v11; // rdx
  __int64 v12; // rax
  _WORD *v13; // rcx
  signed int v14; // r8d

  v4 = this;
  if ( !this || !a2 )
    return (unsigned int)-2147467261;
  v5 = this;
  v6 = 0x7FFFFFFF;
  do
  {
    if ( !*(_WORD *)v5 )
      break;
    v5 = (WaasMedic *)((char *)v5 + 2);
    --v6;
  }
  while ( v6 );
  v7 = v6 == 0 ? 0x80070057 : 0;
  v8 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
  if ( v6 )
  {
    v9 = WaasMedic::SafeAlloc((WaasMedic *)(2 * v8 + 2));
    *(_QWORD *)a2 = v9;
    v10 = v9;
    if ( !v9 )
    {
      v7 = -2147024882;
      LogLevelW(2u, L"Failed to allocate memory for client scenario param!");
      return v7;
    }
    v11 = v8 + 1;
    if ( v8 == -1 )
    {
      v14 = -2147024809;
    }
    else
    {
      if ( v11 > 0x7FFFFFFF )
      {
        *v9 = 0;
        v7 = -2147024809;
        goto LABEL_20;
      }
      v12 = 2147483646;
      do
      {
        if ( !v12 )
          break;
        if ( !*(_WORD *)v4 )
          break;
        *v10 = *(_WORD *)v4;
        v4 = (WaasMedic *)((char *)v4 + 2);
        ++v10;
        --v12;
        --v11;
      }
      while ( v11 );
      v13 = v10 - 1;
      if ( v11 )
        v13 = v10;
      v14 = v11 == 0 ? 0x8007007A : 0;
      *v13 = 0;
    }
    v7 = v14;
    if ( v14 >= 0 )
      return v7;
LABEL_20:
    LogLevelW(2u, L"Failed to copy client scenario param! hr = 0x%08x");
    return v7;
  }
  LogLevelW(2u, L"Failed to calculate string length for %s! hr = 0x%08x", this, v7);
  return v7;
}

```

## disassembly

```asm
0x14000f000  push    rbx
0x14000f002  push    rbp
0x14000f003  push    rsi
0x14000f004  push    rdi
0x14000f005  push    r13
0x14000f007  push    r14
0x14000f009  sub     rsp, 28h
0x14000f00d  xor     r14d, r14d
0x14000f010  mov     rsi, rdx
0x14000f013  mov     rdi, rcx
0x14000f016  test    rcx, rcx
0x14000f019  jz      loc_14000F145
0x14000f01f  test    rdx, rdx
0x14000f022  jz      loc_14000F145
0x14000f028  mov     r13d, 7FFFFFFFh
0x14000f02e  mov     rax, rcx
0x14000f031  mov     r8d, r13d
0x14000f034  cmp     [rax], r14w
0x14000f038  jz      short loc_14000F044
0x14000f03a  add     rax, 2
0x14000f03e  sub     r8, 1; bool
0x14000f042  jnz     short loc_14000F034
0x14000f044  mov     rax, r8
0x14000f047  mov     rdx, r13
0x14000f04a  neg     rax
0x14000f04d  mov     rax, r8
0x14000f050  sbb     ebx, ebx
0x14000f052  sub     rdx, r8; unsigned __int64
0x14000f055  not     ebx
0x14000f057  and     ebx, 80070057h
0x14000f05d  neg     rax
0x14000f060  sbb     rbp, rbp
0x14000f063  and     rbp, rdx
0x14000f066  test    r8, r8
0x14000f069  jnz     short loc_14000F087
0x14000f06b  mov     r8, rcx
0x14000f06e  lea     rdx, aFailedToCalcul; "Failed to calculate string length for %"...
0x14000f075  mov     ecx, 2; unsigned __int8
0x14000f07a  mov     r9d, ebx
0x14000f07d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000f082  jmp     loc_14000F14A
0x14000f087  lea     rcx, ds:2[rbp*2]; this
0x14000f08f  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x14000f094  mov     [rsi], rax
0x14000f097  mov     r9, rax
0x14000f09a  test    rax, rax
0x14000f09d  jnz     short loc_14000F0B8
0x14000f09f  lea     rdx, aFailedToAlloca_0; "Failed to allocate memory for client sc"...
0x14000f0a6  mov     ebx, 8007000Eh
0x14000f0ab  lea     ecx, [rax+2]; unsigned __int8
0x14000f0ae  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000f0b3  jmp     loc_14000F14A
0x14000f0b8  lea     rdx, [rbp+1]
0x14000f0bc  test    rdx, rdx
0x14000f0bf  jz      short loc_14000F12F
0x14000f0c1  cmp     rdx, r13
0x14000f0c4  jbe     short loc_14000F0CE
0x14000f0c6  mov     r8d, 80070057h
0x14000f0cc  jmp     short loc_14000F13A
0x14000f0ce  mov     eax, 7FFFFFFEh
0x14000f0d3  test    rax, rax
0x14000f0d6  jz      short loc_14000F0F5
0x14000f0d8  movzx   ecx, word ptr [rdi]
0x14000f0db  test    cx, cx
0x14000f0de  jz      short loc_14000F0F5
0x14000f0e0  mov     [r9], cx
0x14000f0e4  add     rdi, 2
0x14000f0e8  add     r9, 2
0x14000f0ec  dec     rax
0x14000f0ef  sub     rdx, 1
0x14000f0f3  jnz     short loc_14000F0D3
0x14000f0f5  test    rdx, rdx
0x14000f0f8  lea     rcx, [r9-2]
0x14000f0fc  cmovnz  rcx, r9
0x14000f100  neg     rdx
0x14000f103  sbb     r8d, r8d
0x14000f106  not     r8d
0x14000f109  and     r8d, 8007007Ah
0x14000f110  mov     [rcx], r14w
0x14000f114  mov     ebx, r8d
0x14000f117  test    r8d, r8d
0x14000f11a  jns     short loc_14000F14A
0x14000f11c  lea     rdx, aFailedToCopyCl; "Failed to copy client scenario param! h"...
0x14000f123  mov     ecx, 2; unsigned __int8
0x14000f128  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000f12d  jmp     short loc_14000F14A
0x14000f12f  mov     r8d, 80070057h
0x14000f135  test    rdx, rdx
0x14000f138  jz      short loc_14000F114
0x14000f13a  mov     [rax], r14w
0x14000f13e  mov     ebx, 80070057h
0x14000f143  jmp     short loc_14000F11C
0x14000f145  mov     ebx, 80004003h
0x14000f14a  mov     eax, ebx
0x14000f14c  add     rsp, 28h
0x14000f150  pop     r14
0x14000f152  pop     r13
0x14000f154  pop     rdi
0x14000f155  pop     rsi
0x14000f156  pop     rbp
0x14000f157  pop     rbx
0x14000f158  retn
```
