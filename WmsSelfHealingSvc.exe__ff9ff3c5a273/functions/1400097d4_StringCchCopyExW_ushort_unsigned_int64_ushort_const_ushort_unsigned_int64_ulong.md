# StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x1400097d4`
- end: `0x140009883`
- name: `?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `175`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140008974`
- `0x140008e34`

## callees

- `0x1400097d4`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  __int64 result; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // r8
  unsigned __int16 *v12; // rax
  __int64 v13; // r9
  unsigned __int16 *v14; // rcx
  __int64 v15; // rdx
  unsigned __int64 v16; // r10

  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v10 = 2147483646;
    v11 = a2;
    v12 = a1;
    v13 = 0;
    do
    {
      if ( !v10 )
        break;
      if ( !*a3 )
        break;
      *v12++ = *a3++;
      --v10;
      ++v13;
      --v11;
    }
    while ( v11 );
    v14 = v12 - 1;
    v15 = v13 - 1;
    if ( v11 )
    {
      v14 = v12;
      v15 = v13;
    }
    v16 = a2 - v15;
    *v14 = 0;
    result = v11 == 0 ? 0x8007007A : 0;
    if ( a4 )
      *a4 = &a1[v15];
    if ( a5 )
      *a5 = v16;
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400097d4  push    rbx
0x1400097d6  push    rsi
0x1400097d7  push    rdi
0x1400097d8  xor     esi, esi
0x1400097da  mov     rdi, r9
0x1400097dd  mov     r11, r8
0x1400097e0  mov     r10, rdx
0x1400097e3  mov     rbx, rcx
0x1400097e6  test    rdx, rdx
0x1400097e9  jz      loc_140009872
0x1400097ef  cmp     rdx, 7FFFFFFFh
0x1400097f6  jbe     short loc_1400097FF
0x1400097f8  mov     eax, 80070057h
0x1400097fd  jmp     short loc_14000987C
0x1400097ff  mov     ecx, 7FFFFFFEh
0x140009804  mov     r8, r10
0x140009807  mov     rax, rbx
0x14000980a  mov     r9, rsi
0x14000980d  test    rcx, rcx
0x140009810  jz      short loc_140009832
0x140009812  movzx   edx, word ptr [r11]
0x140009816  test    dx, dx
0x140009819  jz      short loc_140009832
0x14000981b  mov     [rax], dx
0x14000981e  add     r11, 2
0x140009822  add     rax, 2
0x140009826  dec     rcx
0x140009829  inc     r9
0x14000982c  sub     r8, 1
0x140009830  jnz     short loc_14000980D
0x140009832  test    r8, r8
0x140009835  lea     rcx, [rax-2]
0x140009839  lea     rdx, [r9-1]
0x14000983d  cmovnz  rcx, rax
0x140009841  cmovnz  rdx, r9
0x140009845  neg     r8
0x140009848  sbb     eax, eax
0x14000984a  sub     r10, rdx
0x14000984d  not     eax
0x14000984f  mov     [rcx], si
0x140009852  and     eax, 8007007Ah
0x140009857  lea     rcx, [rbx+rdx*2]
0x14000985b  test    rdi, rdi
0x14000985e  jz      short loc_140009863
0x140009860  mov     [rdi], rcx
0x140009863  mov     rcx, [rsp+18h+arg_20]
0x140009868  test    rcx, rcx
0x14000986b  jz      short loc_14000987F
0x14000986d  mov     [rcx], r10
0x140009870  jmp     short loc_14000987F
0x140009872  mov     eax, 80070057h
0x140009877  test    r10, r10
0x14000987a  jz      short loc_14000987F
0x14000987c  mov     [rcx], si
0x14000987f  pop     rdi
0x140009880  pop     rsi
0x140009881  pop     rbx
0x140009882  retn
```
