# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800206b0`
- end: `0x1800208ea`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `570`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180020aa0`

## callees

- `0x1800206b0`
- `0x180024d30`
- `0x180024dec`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800206f9`
- `KERNEL32!HeapAlloc` at `0x18002085b`
- `KERNEL32!HeapAlloc` at `0x1800206f9`
- `KERNEL32!HeapAlloc` at `0x18002085b`
- `KERNEL32!GetProcessHeap` at `0x1800206e7`
- `KERNEL32!GetProcessHeap` at `0x18002084a`
- `KERNEL32!GetProcessHeap` at `0x180020869`
- `KERNEL32!GetProcessHeap` at `0x1800206e7`
- `KERNEL32!GetProcessHeap` at `0x18002084a`
- `KERNEL32!GetProcessHeap` at `0x180020869`
- `KERNEL32!HeapFree` at `0x180020878`
- `KERNEL32!HeapFree` at `0x180020878`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v2; // edi
  HANDLE ProcessHeap; // rax
  _WORD *v6; // rax
  _WORD *v7; // rcx
  _DWORD *v8; // rcx
  _DWORD *v9; // rdx
  _DWORD *v10; // rcx
  __int64 v11; // r8
  volatile signed __int32 *v12; // rax
  signed __int32 v13; // ecx
  __int64 v14; // rdx
  __int64 v15; // rdi
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rdx
  SIZE_T v23; // rbx
  HANDLE v24; // rax
  LPVOID v25; // rbp
  HANDLE v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rbx
  __int64 v29; // rax
  void *v30; // rax

  v2 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v2 )
    {
      ProcessHeap = GetProcessHeap();
      v6 = HeapAlloc(ProcessHeap, 8u, 0x1B8u);
      *((_QWORD *)this + 3) = v6;
      if ( v6 )
      {
        v7 = v6 + 220;
        *((_DWORD *)this + 8) = 5;
        while ( v6 != v7 )
        {
          *v6 = 88;
          v6 += 44;
        }
      }
    }
  }
  v8 = (_DWORD *)*((_QWORD *)this + 3);
  if ( v8 )
  {
    if ( !v2 || (v9 = &v8[22 * *((unsigned __int16 *)this + 16)], v8 == v9) )
    {
LABEL_14:
      v11 = 1;
      v12 = (volatile signed __int32 *)*((_QWORD *)this + 1);
      *((_WORD *)this + 17) = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
      v13 = _InterlockedExchangeAdd(v12, 1u);
      v14 = -1;
      v15 = *((_QWORD *)this + 3) + 88LL * *((unsigned __int16 *)this + 17);
      *(_DWORD *)(v15 + 4) = v13 + 1;
      *(_DWORD *)(v15 + 8) = *((_DWORD *)a2 + 1);
      *(_QWORD *)(v15 + 16) = 0;
      *(_WORD *)(v15 + 24) = *((_WORD *)a2 + 28);
      *(_DWORD *)(v15 + 28) = *(_DWORD *)a2;
      *(_QWORD *)(v15 + 40) = 0;
      *(_QWORD *)(v15 + 48) = *((_QWORD *)a2 + 16);
      *(_QWORD *)(v15 + 56) = *((_QWORD *)a2 + 17);
      *(_QWORD *)(v15 + 64) = 0;
      v16 = *((_QWORD *)a2 + 6);
      if ( v16 )
      {
        v18 = -1;
        do
          ++v18;
        while ( *(_BYTE *)(v16 + v18) );
        v17 = v18 + 1;
      }
      else
      {
        v17 = 1;
      }
      v19 = *((_QWORD *)a2 + 15);
      if ( v19 )
      {
        v20 = -1;
        do
          ++v20;
        while ( *(_BYTE *)(v19 + v20) );
        v11 = v20 + 1;
      }
      v21 = *((_QWORD *)a2 + 2);
      if ( v21 )
      {
        do
          ++v14;
        while ( *(_WORD *)(v21 + 2 * v14) );
        v22 = 2 * v14 + 2;
      }
      else
      {
        v22 = 2;
      }
      v23 = v17 + v22 + v11;
      if ( !*(_QWORD *)(v15 + 72) || *(_QWORD *)(v15 + 80) < v23 )
      {
        v24 = GetProcessHeap();
        v25 = HeapAlloc(v24, 8u, v23);
        if ( v25 )
        {
          v26 = GetProcessHeap();
          HeapFree(v26, 0, *(LPVOID *)(v15 + 72));
          *(_QWORD *)(v15 + 72) = v25;
          *(_QWORD *)(v15 + 80) = v23;
        }
      }
      v27 = *(_QWORD *)(v15 + 72);
      if ( v27 )
      {
        v28 = v27 + *(_QWORD *)(v15 + 80);
        v29 = wil::details::WriteResultString<char const *>(v27, v28, *((_QWORD *)a2 + 6), v15 + 16);
        v30 = (void *)wil::details::WriteResultString<char const *>(v29, v28, *((_QWORD *)a2 + 15), v15 + 40);
        wil::details::WriteResultString<unsigned short const *>(v30);
      }
    }
    else
    {
      v10 = v8 + 2;
      while ( *(v10 - 1) <= *((_DWORD *)this + 4) || *v10 != *((_DWORD *)a2 + 1) )
      {
        v10 += 22;
        if ( v10 - 2 == v9 )
          goto LABEL_14;
      }
    }
  }
}

```

## disassembly

```asm
0x1800206b0  mov     [rsp+arg_0], rbx
0x1800206b5  mov     [rsp+arg_8], rbp
0x1800206ba  mov     [rsp+arg_10], rsi
0x1800206bf  push    rdi
0x1800206c0  push    r12
0x1800206c2  push    r13
0x1800206c4  push    r14
0x1800206c6  push    r15
0x1800206c8  sub     rsp, 40h
0x1800206cc  mov     edi, [rcx+10h]
0x1800206cf  xor     r13d, r13d
0x1800206d2  mov     rsi, rdx
0x1800206d5  mov     rbx, rcx
0x1800206d8  mov     ebp, 58h ; 'X'
0x1800206dd  cmp     [rcx+18h], r13
0x1800206e1  jnz     short loc_180020728
0x1800206e3  test    edi, edi
0x1800206e5  jz      short loc_180020728
0x1800206e7  call    cs:__imp_GetProcessHeap
0x1800206ed  lea     edx, [rbp-50h]; dwFlags
0x1800206f0  mov     r8d, 1B8h; dwBytes
0x1800206f6  mov     rcx, rax; hHeap
0x1800206f9  call    cs:__imp_HeapAlloc
0x1800206ff  mov     [rbx+18h], rax
0x180020703  test    rax, rax
0x180020706  jz      short loc_180020728
0x180020708  lea     rcx, [rax+1B8h]
0x18002070f  mov     dword ptr [rbx+20h], 5
0x180020716  mov     [rsp+68h+var_40], rcx
0x18002071b  jmp     short loc_180020723
0x18002071d  mov     [rax], bp
0x180020720  add     rax, rbp
0x180020723  cmp     rax, rcx
0x180020726  jnz     short loc_18002071D
0x180020728  mov     rcx, [rbx+18h]
0x18002072c  test    rcx, rcx
0x18002072f  jz      loc_1800208CC
0x180020735  test    edi, edi
0x180020737  jz      short loc_180020773
0x180020739  movzx   eax, word ptr [rbx+20h]
0x18002073d  imul    rdx, rax, 58h ; 'X'
0x180020741  add     rdx, rcx
0x180020744  mov     [rsp+68h+var_30], rdx
0x180020749  cmp     rcx, rdx
0x18002074c  jz      short loc_180020773
0x18002074e  mov     r8d, [rbx+10h]
0x180020752  add     rcx, 8
0x180020756  cmp     [rcx-4], r8d
0x18002075a  jbe     short loc_180020767
0x18002075c  mov     eax, [rsi+4]
0x18002075f  cmp     [rcx], eax
0x180020761  jz      loc_1800208CC
0x180020767  add     rcx, rbp
0x18002076a  lea     rax, [rcx-8]
0x18002076e  cmp     rax, rdx
0x180020771  jnz     short loc_180020756
0x180020773  movzx   eax, word ptr [rbx+22h]
0x180020777  mov     r8d, 1
0x18002077d  movzx   ecx, word ptr [rbx+20h]
0x180020781  add     eax, r8d
0x180020784  xor     edx, edx
0x180020786  div     ecx
0x180020788  mov     rax, [rbx+8]
0x18002078c  mov     ecx, r8d
0x18002078f  mov     [rbx+22h], dx
0x180020793  lock xadd [rax], ecx
0x180020797  movzx   eax, word ptr [rbx+22h]
0x18002079b  add     ecx, r8d
0x18002079e  imul    rdi, rax, 58h ; 'X'
0x1800207a2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800207a6  add     rdi, [rbx+18h]
0x1800207aa  mov     [rdi+4], ecx
0x1800207ad  mov     eax, [rsi+4]
0x1800207b0  mov     [rdi+8], eax
0x1800207b3  mov     [rdi+10h], r13
0x1800207b7  movzx   eax, word ptr [rsi+38h]
0x1800207bb  mov     [rdi+18h], ax
0x1800207bf  mov     eax, [rsi]
0x1800207c1  mov     [rdi+1Ch], eax
0x1800207c4  mov     [rdi+28h], r13
0x1800207c8  mov     rax, [rsi+80h]
0x1800207cf  mov     [rdi+30h], rax
0x1800207d3  mov     rax, [rsi+88h]
0x1800207da  mov     [rdi+38h], rax
0x1800207de  mov     [rdi+40h], r13
0x1800207e2  mov     rcx, [rsi+30h]
0x1800207e6  test    rcx, rcx
0x1800207e9  jnz     short loc_1800207F0
0x1800207eb  mov     eax, r8d
0x1800207ee  jmp     short loc_1800207FF
0x1800207f0  mov     rax, rdx
0x1800207f3  inc     rax
0x1800207f6  cmp     [rcx+rax], r13b
0x1800207fa  jnz     short loc_1800207F3
0x1800207fc  add     rax, r8
0x1800207ff  mov     r9, [rsi+78h]
0x180020803  test    r9, r9
0x180020806  jz      short loc_180020817
0x180020808  mov     rcx, rdx
0x18002080b  inc     rcx
0x18002080e  cmp     [r9+rcx], r13b
0x180020812  jnz     short loc_18002080B
0x180020814  add     r8, rcx
0x180020817  mov     rcx, [rsi+10h]
0x18002081b  test    rcx, rcx
0x18002081e  jnz     short loc_180020825
0x180020820  lea     edx, [rcx+2]
0x180020823  jmp     short loc_180020837
0x180020825  inc     rdx
0x180020828  cmp     [rcx+rdx*2], r13w
0x18002082d  jnz     short loc_180020825
0x18002082f  lea     rdx, ds:2[rdx*2]
0x180020837  lea     rbx, [rdx+r8]
0x18002083b  add     rbx, rax
0x18002083e  cmp     [rdi+48h], r13
0x180020842  jz      short loc_18002084A
0x180020844  cmp     [rdi+50h], rbx
0x180020848  jnb     short loc_180020886
0x18002084a  call    cs:__imp_GetProcessHeap
0x180020850  mov     r8, rbx; dwBytes
0x180020853  mov     edx, 8; dwFlags
0x180020858  mov     rcx, rax; hHeap
0x18002085b  call    cs:__imp_HeapAlloc
0x180020861  mov     rbp, rax
0x180020864  test    rax, rax
0x180020867  jz      short loc_180020886
0x180020869  call    cs:__imp_GetProcessHeap
0x18002086f  mov     r8, [rdi+48h]; lpMem
0x180020873  xor     edx, edx; dwFlags
0x180020875  mov     rcx, rax; hHeap
0x180020878  call    cs:__imp_HeapFree
0x18002087e  mov     [rdi+48h], rbp
0x180020882  mov     [rdi+50h], rbx
0x180020886  mov     rcx, [rdi+48h]
0x18002088a  test    rcx, rcx
0x18002088d  jz      short loc_1800208CC
0x18002088f  mov     rbx, [rdi+50h]
0x180020893  lea     r9, [rdi+10h]
0x180020897  mov     r8, [rsi+30h]
0x18002089b  add     rbx, rcx
0x18002089e  mov     rdx, rbx
0x1800208a1  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800208a6  mov     r8, [rsi+78h]
0x1800208aa  lea     r9, [rdi+28h]
0x1800208ae  mov     rdx, rbx
0x1800208b1  mov     rcx, rax
0x1800208b4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800208b9  mov     r8, [rsi+10h]
0x1800208bd  lea     r9, [rdi+40h]
0x1800208c1  mov     rdx, rbx
0x1800208c4  mov     rcx, rax; Destination
0x1800208c7  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800208cc  lea     r11, [rsp+68h+var_28]
0x1800208d1  mov     rbx, [r11+30h]
0x1800208d5  mov     rbp, [r11+38h]
0x1800208d9  mov     rsi, [r11+40h]
0x1800208dd  mov     rsp, r11
0x1800208e0  pop     r15
0x1800208e2  pop     r14
0x1800208e4  pop     r13
0x1800208e6  pop     r12
0x1800208e8  pop     rdi
0x1800208e9  retn
```
