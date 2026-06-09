# UpdateDstMBYVU9(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001d410`
- end: `0x18001d4a1`
- name: `?UpdateDstMBYVU9@@YAXPEAE00PEBE11JJJJ@Z`
- size: `145`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001dd20`

## callees

- `0x18001d410`

## pseudocode

```c
void __fastcall UpdateDstMBYVU9(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        const unsigned __int8 *a6,
        int a7,
        int a8,
        int a9,
        int a10)
{
  int v11; // eax
  __int128 v12; // xmm0
  __int64 v15; // r9
  int v16; // ebx
  unsigned __int8 v17; // al
  unsigned __int8 v18; // al

  v11 = 16;
  do
  {
    v12 = *(_OWORD *)a4;
    a4 += a7;
    *(_OWORD *)a1 = v12;
    a1 += a9;
    --v11;
  }
  while ( v11 );
  v15 = 2 * a8;
  v16 = 4;
  do
  {
    *a3 = *a6;
    a3[1] = a6[2];
    a3[2] = a6[4];
    v17 = a6[6];
    a6 += v15;
    a3[3] = v17;
    a3 += a10;
    *a2 = *a5;
    a2[1] = a5[2];
    a2[2] = a5[4];
    v18 = a5[6];
    a5 += v15;
    a2[3] = v18;
    a2 += a10;
    --v16;
  }
  while ( v16 );
}

```

## disassembly

```asm
0x18001d410  mov     [rsp+arg_0], rbx
0x18001d415  mov     eax, [rsp+arg_38]
0x18001d419  mov     r10, rdx
0x18001d41c  movsxd  rdx, [rsp+arg_30]
0x18001d421  movsxd  r11, [rsp+arg_40]
0x18001d426  lea     ebx, [rax+rax]
0x18001d429  mov     eax, 10h
0x18001d42e  movups  xmm0, xmmword ptr [r9]
0x18001d432  add     r9, rdx
0x18001d435  movdqu  xmmword ptr [rcx], xmm0
0x18001d439  add     rcx, r11
0x18001d43c  sub     eax, 1
0x18001d43f  jnz     short loc_18001D42E
0x18001d441  movsxd  r11, [rsp+arg_48]
0x18001d446  mov     rcx, [rsp+arg_28]
0x18001d44b  mov     rdx, [rsp+arg_20]
0x18001d450  movsxd  r9, ebx
0x18001d453  lea     ebx, [rax+4]
0x18001d456  mov     al, [rcx]
0x18001d458  mov     [r8], al
0x18001d45b  mov     al, [rcx+2]
0x18001d45e  mov     [r8+1], al
0x18001d462  mov     al, [rcx+4]
0x18001d465  mov     [r8+2], al
0x18001d469  mov     al, [rcx+6]
0x18001d46c  add     rcx, r9
0x18001d46f  mov     [r8+3], al
0x18001d473  add     r8, r11
0x18001d476  mov     al, [rdx]
0x18001d478  mov     [r10], al
0x18001d47b  mov     al, [rdx+2]
0x18001d47e  mov     [r10+1], al
0x18001d482  mov     al, [rdx+4]
0x18001d485  mov     [r10+2], al
0x18001d489  mov     al, [rdx+6]
0x18001d48c  add     rdx, r9
0x18001d48f  mov     [r10+3], al
0x18001d493  add     r10, r11
0x18001d496  sub     ebx, 1
0x18001d499  jnz     short loc_18001D456
0x18001d49b  mov     rbx, [rsp+arg_0]
0x18001d4a0  retn
```
