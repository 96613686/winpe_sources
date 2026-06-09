# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140005a98`
- end: `0x140005b41`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004760`
- `0x140005bc0`

## callees

- `0x140005a98`

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

  v3 = 512;
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
  v6 = (512 - v3) & -(__int64)(v3 != 0);
  if ( v3 )
  {
    v7 = &a1[v6];
    v8 = 2147483646;
    v9 = 512 - v6;
    if ( 512 != v6 )
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
0x140005a98  mov     [rsp+arg_0], rbx
0x140005a9d  mov     [rsp+arg_8], rdi
0x140005aa2  mov     r9d, 200h
0x140005aa8  mov     rbx, rcx
0x140005aab  mov     r10d, r9d
0x140005aae  mov     rax, rcx
0x140005ab1  xor     edi, edi
0x140005ab3  cmp     [rax], di
0x140005ab6  jz      short loc_140005AC2
0x140005ab8  add     rax, 2
0x140005abc  sub     r10, 1
0x140005ac0  jnz     short loc_140005AB3
0x140005ac2  mov     rax, r10
0x140005ac5  mov     rcx, r9
0x140005ac8  neg     rax
0x140005acb  mov     rax, r10
0x140005ace  sbb     edx, edx
0x140005ad0  sub     rcx, r10
0x140005ad3  not     edx
0x140005ad5  and     edx, 80070057h
0x140005adb  neg     rax
0x140005ade  sbb     r11, r11
0x140005ae1  and     r11, rcx
0x140005ae4  test    r10, r10
0x140005ae7  jz      short loc_140005B34
0x140005ae9  lea     rax, [rbx+r11*2]
0x140005aed  mov     ecx, 7FFFFFFEh
0x140005af2  sub     r9, r11
0x140005af5  jz      short loc_140005B19
0x140005af7  test    rcx, rcx
0x140005afa  jz      short loc_140005B19
0x140005afc  movzx   edx, word ptr [r8]
0x140005b00  test    dx, dx
0x140005b03  jz      short loc_140005B19
0x140005b05  mov     [rax], dx
0x140005b08  add     r8, 2
0x140005b0c  add     rax, 2
0x140005b10  dec     rcx
0x140005b13  sub     r9, 1
0x140005b17  jnz     short loc_140005AF7
0x140005b19  test    r9, r9
0x140005b1c  lea     rcx, [rax-2]
0x140005b20  cmovnz  rcx, rax
0x140005b24  neg     r9
0x140005b27  sbb     edx, edx
0x140005b29  not     edx
0x140005b2b  and     edx, 8007007Ah
0x140005b31  mov     [rcx], di
0x140005b34  mov     rbx, [rsp+arg_0]
0x140005b39  mov     eax, edx
0x140005b3b  mov     rdi, [rsp+arg_8]
0x140005b40  retn
```
