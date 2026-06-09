# MakeQualifiedIdentityName(ushort const *,ushort const *,_UNICODE_STRING *)

- ea: `0x18001719c`
- end: `0x1800172ce`
- name: `?MakeQualifiedIdentityName@@YAJPEBG0PEAU_UNICODE_STRING@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800014fc`
- `0x180016060`

## callees

- `0x18001719c`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180017252`
- `msvcrt!wcscpy_s` at `0x180017287`
- `msvcrt!wcscpy_s` at `0x180017252`
- `msvcrt!wcscpy_s` at `0x180017287`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800172a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800172a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001722d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001722d`

## pseudocode

```c
__int64 __fastcall MakeQualifiedIdentityName(wchar_t *Source, wchar_t *a2, struct _UNICODE_STRING *a3)
{
  unsigned int v3; // ebx
  __int64 v7; // rbp
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // edx
  unsigned __int64 v11; // rdi
  WCHAR *v12; // rax
  WCHAR *v13; // r14
  PWSTR Buffer; // rcx

  v3 = 0;
  if ( Source && a2 && a3 )
  {
    if ( !*Source )
      goto LABEL_18;
    if ( !*a2 )
      goto LABEL_18;
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    v9 = -1;
    do
      ++v9;
    while ( Source[v9] );
    v10 = v8 + v9 + 2;
    if ( v10 >= (unsigned int)v9 && (v11 = 2LL * v10, v11 <= 0xFFFFFFFF) && (unsigned int)(v11 - 3) <= 0x7FFC )
    {
      v12 = (WCHAR *)CoTaskMemAlloc((unsigned int)v11);
      a3->Buffer = v12;
      v13 = v12;
      if ( v12 )
      {
        wcscpy_s(v12, (unsigned __int64)(unsigned int)v11 >> 1, Source);
        do
          ++v7;
        while ( v13[v7] );
        v13[v7] = 92;
        wcscpy_s(&v13[v7 + 1], (__int64)(2 * ((unsigned __int64)(unsigned int)v11 >> 1) - (2 * v7 + 2)) >> 1, a2);
        a3->MaximumLength = v11;
        a3->Length = v11 - 2;
        return v3;
      }
      v3 = -2147024882;
    }
    else
    {
LABEL_18:
      v3 = -2147024809;
    }
    Buffer = a3->Buffer;
    if ( Buffer )
      CoTaskMemFree(Buffer);
    *a3 = 0;
    return v3;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18001719c  push    rbx
0x18001719e  push    rbp
0x18001719f  push    rsi
0x1800171a0  push    rdi
0x1800171a1  push    r12
0x1800171a3  push    r13
0x1800171a5  push    r14
0x1800171a7  push    r15
0x1800171a9  sub     rsp, 28h
0x1800171ad  xor     ebx, ebx
0x1800171af  mov     rsi, r8
0x1800171b2  mov     r12, rdx
0x1800171b5  mov     r15, rcx
0x1800171b8  test    rcx, rcx
0x1800171bb  jz      loc_1800172B8
0x1800171c1  test    rdx, rdx
0x1800171c4  jz      loc_1800172B8
0x1800171ca  test    r8, r8
0x1800171cd  jz      loc_1800172B8
0x1800171d3  cmp     [rcx], bx
0x1800171d6  jz      loc_18001729A
0x1800171dc  cmp     [rdx], bx
0x1800171df  jz      loc_18001729A
0x1800171e5  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800171e9  mov     rcx, rbp
0x1800171ec  inc     rcx
0x1800171ef  cmp     [rdx+rcx*2], bx
0x1800171f3  jnz     short loc_1800171EC
0x1800171f5  mov     rax, rbp
0x1800171f8  inc     rax
0x1800171fb  cmp     [r15+rax*2], bx
0x180017200  jnz     short loc_1800171F8
0x180017202  lea     edx, [rax+2]
0x180017205  add     edx, ecx
0x180017207  cmp     edx, eax
0x180017209  jb      loc_18001729A
0x18001720f  mov     edi, edx
0x180017211  mov     eax, 0FFFFFFFFh
0x180017216  add     rdi, rdi
0x180017219  cmp     rdi, rax
0x18001721c  ja      short loc_18001729A
0x18001721e  lea     eax, [rdi-3]
0x180017221  cmp     eax, 7FFCh
0x180017226  ja      short loc_18001729A
0x180017228  mov     ecx, edi; cb
0x18001722a  mov     r13d, edi
0x18001722d  call    cs:__imp_CoTaskMemAlloc
0x180017233  mov     [rsi+8], rax
0x180017237  mov     r14, rax
0x18001723a  test    rax, rax
0x18001723d  jnz     short loc_180017246
0x18001723f  mov     ebx, 8007000Eh
0x180017244  jmp     short loc_18001729F
0x180017246  shr     r13, 1
0x180017249  mov     r8, r15; Source
0x18001724c  mov     rdx, r13; SizeInWords
0x18001724f  mov     rcx, r14; Destination
0x180017252  call    cs:__imp_wcscpy_s
0x180017258  xor     eax, eax
0x18001725a  inc     rbp
0x18001725d  cmp     [r14+rbp*2], ax
0x180017262  jnz     short loc_18001725A
0x180017264  lea     rcx, [r14+2]
0x180017268  mov     word ptr [r14+rbp*2], 5Ch ; '\'
0x18001726f  lea     rcx, [rcx+rbp*2]; Destination
0x180017273  mov     r8, r12; Source
0x180017276  lea     rdx, ds:0[r13*2]
0x18001727e  sub     rdx, rcx
0x180017281  add     rdx, r14
0x180017284  sar     rdx, 1; SizeInWords
0x180017287  call    cs:__imp_wcscpy_s
0x18001728d  mov     [rsi+2], di
0x180017291  sub     di, 2
0x180017295  mov     [rsi], di
0x180017298  jmp     short loc_1800172B4
0x18001729a  mov     ebx, 80070057h
0x18001729f  mov     rcx, [rsi+8]; pv
0x1800172a3  test    rcx, rcx
0x1800172a6  jz      short loc_1800172AE
0x1800172a8  call    cs:__imp_CoTaskMemFree
0x1800172ae  xorps   xmm0, xmm0
0x1800172b1  movups  xmmword ptr [rsi], xmm0
0x1800172b4  mov     eax, ebx
0x1800172b6  jmp     short loc_1800172BD
0x1800172b8  mov     eax, 80004003h
0x1800172bd  add     rsp, 28h
0x1800172c1  pop     r15
0x1800172c3  pop     r14
0x1800172c5  pop     r13
0x1800172c7  pop     r12
0x1800172c9  pop     rdi
0x1800172ca  pop     rsi
0x1800172cb  pop     rbp
0x1800172cc  pop     rbx
0x1800172cd  retn
```
