# PathCombineExt(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180024220`
- end: `0x18002432e`
- name: `?PathCombineExt@@YAKPEBG00PEAPEAG@Z`
- size: `270`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *, wchar_t *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180023c90`
- `0x180040f30`

## callees

- `0x180024220`
- `0x18003aef8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800242be`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800242be`

## pseudocode

```c
__int64 __fastcall PathCombineExt(wchar_t *Source, wchar_t *a2, wchar_t *a3, unsigned __int16 **a4)
{
  __int64 v4; // rdi
  __int64 v6; // rbx
  __int64 v10; // rsi
  unsigned int v12; // eax
  unsigned int v14; // ecx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // r12
  wchar_t *v17; // rbx

  v4 = -1;
  v6 = -1;
  do
    ++v6;
  while ( Source[v6] );
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  while ( a3[++v4] != 0 )
    ;
  v12 = v6 + 2;
  if ( (unsigned int)v6 >= 0xFFFFFFFE )
    return 534;
  v14 = v12 + v10;
  if ( v12 + (unsigned int)v10 < v12 || v14 + (unsigned int)v4 < v14 )
    return 534;
  v15 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (v14 + (unsigned int)v4));
  v16 = v15;
  if ( !v15 )
    return 14;
  *a4 = v15;
  wcscpy_s(v15, (unsigned int)(v6 + 1), Source);
  v17 = &v16[(unsigned int)v6];
  wcscpy_s(v17++, 2u, L"\\");
  wcscpy_s(v17, (unsigned int)(v10 + 1), a2);
  wcscpy_s(&v17[(unsigned int)v10], (unsigned int)(v4 + 1), a3);
  return 0;
}

```

## disassembly

```asm
0x180024220  mov     [rsp+arg_8], rbx
0x180024225  mov     [rsp+arg_10], rbp
0x18002422a  push    rsi
0x18002422b  push    rdi
0x18002422c  push    r13
0x18002422e  push    r14
0x180024230  push    r15
0x180024232  sub     rsp, 20h
0x180024236  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18002423d  mov     r13, r9
0x180024240  mov     rbx, rdi
0x180024243  mov     r14, r8
0x180024246  mov     r15, rdx
0x180024249  mov     rbp, rcx
0x18002424c  nop     dword ptr [rax+00h]
0x180024250  inc     rbx
0x180024253  cmp     word ptr [rcx+rbx*2], 0
0x180024258  jnz     short loc_180024250
0x18002425a  mov     rsi, rdi
0x18002425d  nop     dword ptr [rax]
0x180024260  inc     rsi
0x180024263  cmp     word ptr [rdx+rsi*2], 0
0x180024268  jnz     short loc_180024260
0x18002426a  nop     word ptr [rax+rax+00h]
0x180024270  cmp     word ptr [r8+rdi*2+2], 0
0x180024277  lea     rdi, [rdi+1]
0x18002427b  jnz     short loc_180024270
0x18002427d  lea     eax, [rbx+2]
0x180024280  cmp     eax, 2
0x180024283  jnb     short loc_1800242A1
0x180024285  mov     eax, 216h
0x18002428a  mov     rbx, [rsp+48h+arg_8]
0x18002428f  mov     rbp, [rsp+48h+arg_10]
0x180024294  add     rsp, 20h
0x180024298  pop     r15
0x18002429a  pop     r14
0x18002429c  pop     r13
0x18002429e  pop     rdi
0x18002429f  pop     rsi
0x1800242a0  retn
0x1800242a1  lea     ecx, [rax+rsi]
0x1800242a4  cmp     ecx, eax
0x1800242a6  jb      short loc_180024285
0x1800242a8  lea     eax, [rcx+rdi]
0x1800242ab  cmp     eax, ecx
0x1800242ad  jb      short loc_180024285
0x1800242af  mov     edx, eax
0x1800242b1  mov     ecx, 40h ; '@'; uFlags
0x1800242b6  add     rdx, rdx; uBytes
0x1800242b9  mov     [rsp+48h+arg_0], r12
0x1800242be  call    cs:__imp_LocalAlloc
0x1800242c4  mov     r12, rax
0x1800242c7  test    rax, rax
0x1800242ca  jz      short loc_180024327
0x1800242cc  lea     edx, [rbx+1]; SizeInWords
0x1800242cf  mov     [r13+0], rax
0x1800242d3  mov     r8, rbp; Source
0x1800242d6  mov     rcx, rax; Destination
0x1800242d9  call    wcscpy_s
0x1800242de  mov     eax, ebx
0x1800242e0  lea     r8, Source; "\\"
0x1800242e7  mov     edx, 2; SizeInWords
0x1800242ec  lea     rbx, [r12+rax*2]
0x1800242f0  mov     rcx, rbx; Destination
0x1800242f3  call    wcscpy_s
0x1800242f8  add     rbx, 2
0x1800242fc  lea     edx, [rsi+1]; SizeInWords
0x1800242ff  mov     rcx, rbx; Destination
0x180024302  mov     r8, r15; Source
0x180024305  call    wcscpy_s
0x18002430a  mov     eax, esi
0x18002430c  lea     edx, [rdi+1]; SizeInWords
0x18002430f  mov     r8, r14; Source
0x180024312  lea     rcx, [rbx+rax*2]; Destination
0x180024316  call    wcscpy_s
0x18002431b  xor     eax, eax
0x18002431d  mov     r12, [rsp+48h+arg_0]
0x180024322  jmp     loc_18002428A
0x180024327  mov     eax, 0Eh
0x18002432c  jmp     short loc_18002431D
```
