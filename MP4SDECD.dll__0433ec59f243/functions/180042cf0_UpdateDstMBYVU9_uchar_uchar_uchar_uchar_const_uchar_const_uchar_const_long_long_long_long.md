# UpdateDstMBYVU9(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x180042cf0`
- end: `0x180042d81`
- name: `?UpdateDstMBYVU9@@YAXPEAE00PEBE11JJJJ@Z`
- size: `145`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180043790`

## callees

- `0x180042cf0`

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
0x180042cf0  mov     [rsp+arg_0], rbx
0x180042cf5  mov     eax, [rsp+arg_38]
0x180042cf9  mov     r10, rdx
0x180042cfc  movsxd  rdx, [rsp+arg_30]
0x180042d01  movsxd  r11, [rsp+arg_40]
0x180042d06  lea     ebx, [rax+rax]
0x180042d09  mov     eax, 10h
0x180042d0e  movups  xmm0, xmmword ptr [r9]
0x180042d12  add     r9, rdx
0x180042d15  movdqu  xmmword ptr [rcx], xmm0
0x180042d19  add     rcx, r11
0x180042d1c  sub     eax, 1
0x180042d1f  jnz     short loc_180042D0E
0x180042d21  movsxd  r11, [rsp+arg_48]
0x180042d26  mov     rcx, [rsp+arg_28]
0x180042d2b  mov     rdx, [rsp+arg_20]
0x180042d30  movsxd  r9, ebx
0x180042d33  lea     ebx, [rax+4]
0x180042d36  mov     al, [rcx]
0x180042d38  mov     [r8], al
0x180042d3b  mov     al, [rcx+2]
0x180042d3e  mov     [r8+1], al
0x180042d42  mov     al, [rcx+4]
0x180042d45  mov     [r8+2], al
0x180042d49  mov     al, [rcx+6]
0x180042d4c  add     rcx, r9
0x180042d4f  mov     [r8+3], al
0x180042d53  add     r8, r11
0x180042d56  mov     al, [rdx]
0x180042d58  mov     [r10], al
0x180042d5b  mov     al, [rdx+2]
0x180042d5e  mov     [r10+1], al
0x180042d62  mov     al, [rdx+4]
0x180042d65  mov     [r10+2], al
0x180042d69  mov     al, [rdx+6]
0x180042d6c  add     rdx, r9
0x180042d6f  mov     [r10+3], al
0x180042d73  add     r10, r11
0x180042d76  sub     ebx, 1
0x180042d79  jnz     short loc_180042D36
0x180042d7b  mov     rbx, [rsp+arg_0]
0x180042d80  retn
```
