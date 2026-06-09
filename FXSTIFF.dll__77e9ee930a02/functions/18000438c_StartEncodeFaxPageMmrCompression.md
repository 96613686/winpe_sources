# StartEncodeFaxPageMmrCompression

- ea: `0x18000438c`
- end: `0x18000441a`
- name: `StartEncodeFaxPageMmrCompression`
- size: `142`
- prototype: `__int64 __fastcall(_DWORD *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004540`
- `0x180009d40`

## callees

- `0x18000438c`
- `0x18000f128`
- `0x18000f1c8`
- `0x18001899e`

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
0x18000438c  mov     [rsp+arg_0], rbx
0x180004391  mov     [rsp+arg_8], rsi
0x180004396  push    rdi
0x180004397  sub     rsp, 20h
0x18000439b  mov     eax, edx
0x18000439d  lea     rdi, [rcx+20h]
0x1800043a1  mov     esi, edx
0x1800043a3  mov     rbx, rcx
0x1800043a6  cdq
0x1800043a7  and     edx, 7
0x1800043aa  add     eax, edx
0x1800043ac  sar     eax, 3
0x1800043af  cmp     [rcx+28h], eax
0x1800043b2  jnb     short loc_1800043E2
0x1800043b4  mov     rcx, [rdi]; lpMem
0x1800043b7  call    pMemFree
0x1800043bc  mov     eax, 6C0h
0x1800043c1  cmp     esi, eax
0x1800043c3  cmovle  esi, eax
0x1800043c6  mov     eax, esi
0x1800043c8  cdq
0x1800043c9  and     edx, 7
0x1800043cc  lea     ecx, [rdx+rax]
0x1800043cf  sar     ecx, 3; dwBytes
0x1800043d2  mov     [rbx+28h], ecx
0x1800043d5  call    pMemAlloc
0x1800043da  mov     [rdi], rax
0x1800043dd  test    rax, rax
0x1800043e0  jz      short loc_180004409
0x1800043e2  mov     r8d, [rbx+28h]; Size
0x1800043e6  xor     edx, edx; Val
0x1800043e8  mov     rcx, [rdi]; void *
0x1800043eb  call    memset_0
0x1800043f0  mov     eax, 1
0x1800043f5  mov     dword ptr [rbx+350h], 0
0x1800043ff  mov     dword ptr [rbx+358h], 0
0x180004409  mov     rbx, [rsp+28h+arg_0]
0x18000440e  mov     rsi, [rsp+28h+arg_8]
0x180004413  add     rsp, 20h
0x180004417  pop     rdi
0x180004418  retn
```
