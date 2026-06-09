# StartEncodeFaxPageMmrCompression

- ea: `0x18003a860`
- end: `0x18003a8ee`
- name: `StartEncodeFaxPageMmrCompression`
- size: `142`
- prototype: `__int64 __fastcall(_DWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180035d78`

## callees

- `0x18002bab8`
- `0x18002bb58`
- `0x18003a860`
- `0x18003d4ca`

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
0x18003a860  mov     [rsp+arg_0], rbx
0x18003a865  mov     [rsp+arg_8], rsi
0x18003a86a  push    rdi
0x18003a86b  sub     rsp, 20h
0x18003a86f  mov     eax, edx
0x18003a871  lea     rdi, [rcx+20h]
0x18003a875  mov     esi, edx
0x18003a877  mov     rbx, rcx
0x18003a87a  cdq
0x18003a87b  and     edx, 7
0x18003a87e  add     eax, edx
0x18003a880  sar     eax, 3
0x18003a883  cmp     [rcx+28h], eax
0x18003a886  jnb     short loc_18003A8B6
0x18003a888  mov     rcx, [rdi]; lpMem
0x18003a88b  call    pMemFree
0x18003a890  mov     eax, 6C0h
0x18003a895  cmp     esi, eax
0x18003a897  cmovle  esi, eax
0x18003a89a  mov     eax, esi
0x18003a89c  cdq
0x18003a89d  and     edx, 7
0x18003a8a0  lea     ecx, [rdx+rax]
0x18003a8a3  sar     ecx, 3; dwBytes
0x18003a8a6  mov     [rbx+28h], ecx
0x18003a8a9  call    pMemAlloc
0x18003a8ae  mov     [rdi], rax
0x18003a8b1  test    rax, rax
0x18003a8b4  jz      short loc_18003A8DD
0x18003a8b6  mov     r8d, [rbx+28h]; Size
0x18003a8ba  xor     edx, edx; Val
0x18003a8bc  mov     rcx, [rdi]; void *
0x18003a8bf  call    memset_0
0x18003a8c4  mov     eax, 1
0x18003a8c9  mov     dword ptr [rbx+350h], 0
0x18003a8d3  mov     dword ptr [rbx+358h], 0
0x18003a8dd  mov     rbx, [rsp+28h+arg_0]
0x18003a8e2  mov     rsi, [rsp+28h+arg_8]
0x18003a8e7  add     rsp, 20h
0x18003a8eb  pop     rdi
0x18003a8ec  retn
```
