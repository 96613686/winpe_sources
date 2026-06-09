# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005e64`
- end: `0x180005f0d`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ed8`
- `0x180005fcc`
- `0x18000881c`

## callees

- `0x180005e64`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  unsigned __int16 *v4; // rax
  unsigned int v5; // edx
  __int64 v6; // r11
  unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r9
  unsigned __int16 *v10; // rcx

  v3 = 260;
  v4 = a1;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0x80070057 : 0;
  v6 = (260 - v3) & -(__int64)(v3 != 0);
  if ( v3 )
  {
    v7 = &a1[v6];
    v8 = 2147483646;
    v9 = 260 - v6;
    if ( 260 != v6 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*a3 )
          break;
        *v7++ = *a3++;
        --v8;
        --v9;
      }
      while ( v9 );
    }
    v10 = v7 - 1;
    if ( v9 )
      v10 = v7;
    v5 = v9 == 0 ? 0x8007007A : 0;
    *v10 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180005e64  mov     [rsp+arg_0], rbx
0x180005e69  mov     [rsp+arg_8], rdi
0x180005e6e  mov     r9d, 104h
0x180005e74  mov     rbx, rcx
0x180005e77  mov     r10d, r9d
0x180005e7a  mov     rax, rcx
0x180005e7d  xor     edi, edi
0x180005e7f  cmp     [rax], di
0x180005e82  jz      short loc_180005E8E
0x180005e84  add     rax, 2
0x180005e88  sub     r10, 1
0x180005e8c  jnz     short loc_180005E7F
0x180005e8e  mov     rax, r10
0x180005e91  mov     rcx, r9
0x180005e94  neg     rax
0x180005e97  mov     rax, r10
0x180005e9a  sbb     edx, edx
0x180005e9c  sub     rcx, r10
0x180005e9f  not     edx
0x180005ea1  and     edx, 80070057h
0x180005ea7  neg     rax
0x180005eaa  sbb     r11, r11
0x180005ead  and     r11, rcx
0x180005eb0  test    r10, r10
0x180005eb3  jz      short loc_180005F00
0x180005eb5  lea     rax, [rbx+r11*2]
0x180005eb9  mov     ecx, 7FFFFFFEh
0x180005ebe  sub     r9, r11
0x180005ec1  jz      short loc_180005EE5
0x180005ec3  test    rcx, rcx
0x180005ec6  jz      short loc_180005EE5
0x180005ec8  movzx   edx, word ptr [r8]
0x180005ecc  test    dx, dx
0x180005ecf  jz      short loc_180005EE5
0x180005ed1  mov     [rax], dx
0x180005ed4  add     r8, 2
0x180005ed8  add     rax, 2
0x180005edc  dec     rcx
0x180005edf  sub     r9, 1
0x180005ee3  jnz     short loc_180005EC3
0x180005ee5  test    r9, r9
0x180005ee8  lea     rcx, [rax-2]
0x180005eec  cmovnz  rcx, rax
0x180005ef0  neg     r9
0x180005ef3  sbb     edx, edx
0x180005ef5  not     edx
0x180005ef7  and     edx, 8007007Ah
0x180005efd  mov     [rcx], di
0x180005f00  mov     rbx, [rsp+arg_0]
0x180005f05  mov     eax, edx
0x180005f07  mov     rdi, [rsp+arg_8]
0x180005f0c  retn
```
