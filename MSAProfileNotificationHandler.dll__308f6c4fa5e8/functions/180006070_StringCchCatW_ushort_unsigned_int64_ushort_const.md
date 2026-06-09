# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006070`
- end: `0x180006119`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000439c`
- `0x180006460`

## callees

- `0x180006070`

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
0x180006070  mov     [rsp+arg_0], rbx
0x180006075  mov     [rsp+arg_8], rdi
0x18000607a  mov     r9d, 104h
0x180006080  mov     rbx, rcx
0x180006083  mov     r10d, r9d
0x180006086  mov     rax, rcx
0x180006089  xor     edi, edi
0x18000608b  cmp     [rax], di
0x18000608e  jz      short loc_18000609A
0x180006090  add     rax, 2
0x180006094  sub     r10, 1
0x180006098  jnz     short loc_18000608B
0x18000609a  mov     rax, r10
0x18000609d  mov     rcx, r9
0x1800060a0  neg     rax
0x1800060a3  mov     rax, r10
0x1800060a6  sbb     edx, edx
0x1800060a8  sub     rcx, r10
0x1800060ab  not     edx
0x1800060ad  and     edx, 80070057h
0x1800060b3  neg     rax
0x1800060b6  sbb     r11, r11
0x1800060b9  and     r11, rcx
0x1800060bc  test    r10, r10
0x1800060bf  jz      short loc_18000610C
0x1800060c1  lea     rax, [rbx+r11*2]
0x1800060c5  mov     ecx, 7FFFFFFEh
0x1800060ca  sub     r9, r11
0x1800060cd  jz      short loc_1800060F1
0x1800060cf  test    rcx, rcx
0x1800060d2  jz      short loc_1800060F1
0x1800060d4  movzx   edx, word ptr [r8]
0x1800060d8  test    dx, dx
0x1800060db  jz      short loc_1800060F1
0x1800060dd  mov     [rax], dx
0x1800060e0  add     r8, 2
0x1800060e4  add     rax, 2
0x1800060e8  dec     rcx
0x1800060eb  sub     r9, 1
0x1800060ef  jnz     short loc_1800060CF
0x1800060f1  test    r9, r9
0x1800060f4  lea     rcx, [rax-2]
0x1800060f8  cmovnz  rcx, rax
0x1800060fc  neg     r9
0x1800060ff  sbb     edx, edx
0x180006101  not     edx
0x180006103  and     edx, 8007007Ah
0x180006109  mov     [rcx], di
0x18000610c  mov     rbx, [rsp+arg_0]
0x180006111  mov     eax, edx
0x180006113  mov     rdi, [rsp+arg_8]
0x180006118  retn
```
