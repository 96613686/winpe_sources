# StartEncodeFaxPageMmrCompression

- ea: `0x180004344`
- end: `0x1800043d1`
- name: `StartEncodeFaxPageMmrCompression`
- size: `141`
- prototype: `__int64 __fastcall(_DWORD *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800044f0`
- `0x1800098c0`

## callees

- `0x180004344`
- `0x18000ea18`
- `0x18000eac0`
- `0x180017bce`

## pseudocode

```c
__int64 __fastcall StartEncodeFaxPageMmrCompression(_DWORD *a1, int a2)
{
  LPVOID *v2; // rdi
  int v3; // esi
  SIZE_T v5; // rcx
  __int64 result; // rax

  v2 = (LPVOID *)(a1 + 8);
  v3 = a2;
  if ( a1[10] >= (unsigned int)(a2 / 8) )
    goto LABEL_5;
  pMemFree(*v2);
  if ( v3 <= 1728 )
    v3 = 1728;
  v5 = (unsigned int)(v3 / 8);
  a1[10] = v5;
  result = pMemAlloc(v5);
  *v2 = (LPVOID)result;
  if ( result )
  {
LABEL_5:
    memset_0(*v2, 0, (unsigned int)a1[10]);
    result = 1;
    a1[212] = 0;
    a1[214] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004344  mov     [rsp+arg_0], rbx
0x180004349  mov     [rsp+arg_8], rsi
0x18000434e  push    rdi
0x18000434f  sub     rsp, 20h
0x180004353  mov     eax, edx
0x180004355  lea     rdi, [rcx+20h]
0x180004359  mov     esi, edx
0x18000435b  mov     rbx, rcx
0x18000435e  cdq
0x18000435f  and     edx, 7
0x180004362  add     eax, edx
0x180004364  sar     eax, 3
0x180004367  cmp     [rcx+28h], eax
0x18000436a  jnb     short loc_18000439A
0x18000436c  mov     rcx, [rdi]; lpMem
0x18000436f  call    pMemFree
0x180004374  mov     eax, 6C0h
0x180004379  cmp     esi, eax
0x18000437b  cmovle  esi, eax
0x18000437e  mov     eax, esi
0x180004380  cdq
0x180004381  and     edx, 7
0x180004384  lea     ecx, [rdx+rax]
0x180004387  sar     ecx, 3; dwBytes
0x18000438a  mov     [rbx+28h], ecx
0x18000438d  call    pMemAlloc
0x180004392  mov     [rdi], rax
0x180004395  test    rax, rax
0x180004398  jz      short loc_1800043C1
0x18000439a  mov     r8d, [rbx+28h]; Size
0x18000439e  xor     edx, edx; Val
0x1800043a0  mov     rcx, [rdi]; void *
0x1800043a3  call    memset_0
0x1800043a8  mov     eax, 1
0x1800043ad  mov     dword ptr [rbx+350h], 0
0x1800043b7  mov     dword ptr [rbx+358h], 0
0x1800043c1  mov     rbx, [rsp+28h+arg_0]
0x1800043c6  mov     rsi, [rsp+28h+arg_8]
0x1800043cb  add     rsp, 20h
0x1800043cf  pop     rdi
0x1800043d0  retn
```
