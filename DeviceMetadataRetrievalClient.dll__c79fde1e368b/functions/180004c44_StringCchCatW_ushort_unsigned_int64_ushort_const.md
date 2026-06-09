# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180004c44`
- end: `0x180004cff`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004714`
- `0x1800047c4`
- `0x18000490c`
- `0x1800049bc`
- `0x18000ede8`

## callees

- `0x180004c44`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  __int64 v5; // r11
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  __int64 v9; // r9
  unsigned __int16 *i; // rax
  unsigned __int16 *v11; // rcx

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = a2;
    v6 = a1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (a2 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v9 = a2 - v8;
      for ( i = &a1[v8]; v9; --v9 )
      {
        if ( !v3 )
          break;
        if ( !*a3 )
          break;
        *i++ = *a3++;
        --v3;
      }
      v11 = i - 1;
      if ( v9 )
        v11 = i;
      v7 = v9 == 0 ? 0x8007007A : 0;
      *v11 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180004c44  mov     [rsp+arg_0], rbx
0x180004c49  mov     [rsp+arg_8], rdi
0x180004c4e  lea     rax, [rdx-1]
0x180004c52  mov     r10d, 7FFFFFFEh
0x180004c58  mov     r9, rdx
0x180004c5b  mov     rbx, rcx
0x180004c5e  cmp     rax, r10
0x180004c61  ja      loc_180004CED
0x180004c67  mov     r11, rdx
0x180004c6a  mov     rax, rcx
0x180004c6d  xor     edi, edi
0x180004c6f  cmp     [rax], di
0x180004c72  jz      short loc_180004C7E
0x180004c74  add     rax, 2
0x180004c78  sub     r11, 1
0x180004c7c  jnz     short loc_180004C6F
0x180004c7e  mov     rax, r11
0x180004c81  mov     rcx, r9
0x180004c84  neg     rax
0x180004c87  mov     rax, r11
0x180004c8a  sbb     edx, edx
0x180004c8c  sub     rcx, r11
0x180004c8f  not     edx
0x180004c91  and     edx, 80070057h
0x180004c97  neg     rax
0x180004c9a  sbb     rax, rax
0x180004c9d  and     rax, rcx
0x180004ca0  test    r11, r11
0x180004ca3  jz      short loc_180004CF2
0x180004ca5  sub     r9, rax
0x180004ca8  lea     rax, [rbx+rax*2]
0x180004cac  jz      short loc_180004CD0
0x180004cae  test    r10, r10
0x180004cb1  jz      short loc_180004CD0
0x180004cb3  movzx   ecx, word ptr [r8]
0x180004cb7  test    cx, cx
0x180004cba  jz      short loc_180004CD0
0x180004cbc  mov     [rax], cx
0x180004cbf  add     r8, 2
0x180004cc3  add     rax, 2
0x180004cc7  dec     r10
0x180004cca  sub     r9, 1
0x180004cce  jnz     short loc_180004CAE
0x180004cd0  test    r9, r9
0x180004cd3  lea     rcx, [rax-2]
0x180004cd7  cmovnz  rcx, rax
0x180004cdb  neg     r9
0x180004cde  sbb     edx, edx
0x180004ce0  not     edx
0x180004ce2  and     edx, 8007007Ah
0x180004ce8  mov     [rcx], di
0x180004ceb  jmp     short loc_180004CF2
0x180004ced  mov     edx, 80070057h
0x180004cf2  mov     rbx, [rsp+arg_0]
0x180004cf7  mov     eax, edx
0x180004cf9  mov     rdi, [rsp+arg_8]
0x180004cfe  retn
```
