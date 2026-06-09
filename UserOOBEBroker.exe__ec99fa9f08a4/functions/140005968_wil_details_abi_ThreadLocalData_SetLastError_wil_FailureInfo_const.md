# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140005968`
- end: `0x140005bed`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400040f0`

## callees

- `0x14000295f`
- `0x1400034c8`
- `0x140005088`
- `0x140005968`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140005b28`
- `KERNEL32!HeapFree` at `0x140005b28`
- `KERNEL32!GetProcessHeap` at `0x140005b1a`
- `KERNEL32!GetProcessHeap` at `0x140005b1a`
- `msvcrt!memcpy_s` at `0x140005bb7`
- `msvcrt!memcpy_s` at `0x140005bb7`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v2; // esi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // edx
  __int64 v12; // rsi
  _QWORD *v13; // rbx
  __int64 v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned __int64 v23; // rbp
  LPVOID v24; // r12
  void *v25; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v27; // rcx
  char *v28; // rbp
  __int64 v29; // rax
  char *v30; // rax
  char *v31; // rbx
  _WORD *v32; // r8
  rsize_t v33; // r14

  v2 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v2 )
    {
      v5 = wil::details::ProcessHeapAlloc(8u, 0x190u);
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        *((_DWORD *)this + 8) = 5;
        v6 = v5 + 200;
        while ( v5 != v6 )
        {
          *v5 = 80;
          v5 += 40;
        }
      }
    }
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( !v2 || (v8 = *((_QWORD *)this + 3), v9 = v7 + 80LL * *((unsigned __int16 *)this + 16), v7 == v9) )
    {
LABEL_13:
      v10 = 1;
      v11 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
      *((_WORD *)this + 17) = v11;
      v12 = 80LL * (unsigned __int16)v11;
      *(_DWORD *)(v12 + v7 + 4) = _InterlockedIncrement(*((volatile signed __int32 **)this + 1));
      v13 = (_QWORD *)(v12 + v7 + 32);
      *(_DWORD *)(v12 + v7 + 8) = *((_DWORD *)a2 + 2);
      v14 = -1;
      *(_QWORD *)(v12 + v7 + 16) = 0;
      *(_WORD *)(v12 + v7 + 24) = *((_WORD *)a2 + 32);
      *(_BYTE *)(v12 + v7 + 26) = *(_BYTE *)a2;
      *v13 = 0;
      *(_QWORD *)(v12 + v7 + 40) = *((_QWORD *)a2 + 17);
      *(_QWORD *)(v12 + v7 + 48) = *((_QWORD *)a2 + 18);
      *(_QWORD *)(v12 + v7 + 56) = 0;
      v15 = *((_QWORD *)a2 + 7);
      if ( v15 )
      {
        v17 = -1;
        do
          ++v17;
        while ( *(_BYTE *)(v15 + v17) );
        v16 = v17 + 1;
      }
      else
      {
        v16 = 1;
      }
      v18 = *((_QWORD *)a2 + 16);
      if ( v18 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *(_BYTE *)(v18 + v19) );
        v10 = v19 + 1;
      }
      v20 = *((_QWORD *)a2 + 3);
      if ( v20 )
      {
        v22 = -1;
        do
          ++v22;
        while ( *(_WORD *)(v20 + 2 * v22) );
        v21 = 2 * v22 + 2;
      }
      else
      {
        v21 = 2;
      }
      v23 = v16 + v10 + v21;
      if ( !*(_QWORD *)(v12 + v7 + 64) || *(_QWORD *)(v12 + v7 + 72) < v23 )
      {
        v24 = wil::details::ProcessHeapAlloc(8u, v16 + v10 + v21);
        if ( v24 )
        {
          v25 = *(void **)(v12 + v7 + 64);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v25);
          *(_QWORD *)(v12 + v7 + 64) = v24;
          v13 = (_QWORD *)(v12 + v7 + 32);
          *(_QWORD *)(v12 + v7 + 72) = v23;
        }
      }
      v27 = *(_QWORD *)(v12 + v7 + 64);
      if ( v27 )
      {
        v28 = (char *)(v27 + *(_QWORD *)(v12 + v7 + 72));
        v29 = wil::details::WriteResultString<char const *>(v27, v28, *((_QWORD *)a2 + 7), v12 + v7 + 16);
        v30 = (char *)wil::details::WriteResultString<char const *>(v29, v28, *((_QWORD *)a2 + 16), v13);
        v31 = v30;
        if ( v30 == v28 )
          goto LABEL_38;
        v32 = (_WORD *)*((_QWORD *)a2 + 3);
        if ( !v32 || !*v32 )
          goto LABEL_38;
        do
          ++v14;
        while ( v32[v14] );
        v33 = 2 * v14 + 2;
        if ( v28 - v30 >= v33 )
        {
          memcpy_s(v30, v28 - v30, v32, v33);
          *(_QWORD *)(v12 + v7 + 56) = v31;
          v31 += v33;
        }
        else
        {
LABEL_38:
          *(_QWORD *)(v12 + v7 + 56) = 0;
        }
        memset_0(v31, 0, v28 - v31);
      }
    }
    else
    {
      while ( *(_DWORD *)(v8 + 4) <= *((_DWORD *)this + 4) || *(_DWORD *)(v8 + 8) != *((_DWORD *)a2 + 2) )
      {
        v8 += 80;
        if ( v8 == v9 )
          goto LABEL_13;
      }
    }
  }
}

```

## disassembly

```asm
0x140005968  push    rbx
0x14000596a  push    rbp
0x14000596b  push    rsi
0x14000596c  push    rdi
0x14000596d  push    r12
0x14000596f  push    r13
0x140005971  push    r14
0x140005973  push    r15
0x140005975  sub     rsp, 28h
0x140005979  mov     esi, [rcx+10h]
0x14000597c  xor     r12d, r12d
0x14000597f  mov     r15, rdx
0x140005982  mov     rbx, rcx
0x140005985  mov     ebp, 50h ; 'P'
0x14000598a  cmp     [rcx+18h], r12
0x14000598e  jnz     short loc_1400059C5
0x140005990  test    esi, esi
0x140005992  jz      short loc_1400059C5
0x140005994  mov     edx, 190h; dwBytes
0x140005999  lea     ecx, [rbp-48h]; dwFlags
0x14000599c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400059a1  mov     [rbx+18h], rax
0x1400059a5  test    rax, rax
0x1400059a8  jz      short loc_1400059C5
0x1400059aa  mov     dword ptr [rbx+20h], 5
0x1400059b1  lea     rcx, [rax+190h]
0x1400059b8  jmp     short loc_1400059C0
0x1400059ba  mov     [rax], bp
0x1400059bd  add     rax, rbp
0x1400059c0  cmp     rax, rcx
0x1400059c3  jnz     short loc_1400059BA
0x1400059c5  mov     rdi, [rbx+18h]
0x1400059c9  test    rdi, rdi
0x1400059cc  jz      loc_140005BDC
0x1400059d2  test    esi, esi
0x1400059d4  jz      short loc_140005A0C
0x1400059d6  movzx   eax, word ptr [rbx+20h]
0x1400059da  mov     rcx, rdi
0x1400059dd  lea     rdx, [rax+rax*4]
0x1400059e1  shl     rdx, 4
0x1400059e5  add     rdx, rdi
0x1400059e8  cmp     rdi, rdx
0x1400059eb  jz      short loc_140005A0C
0x1400059ed  mov     r8d, [rbx+10h]
0x1400059f1  cmp     [rcx+4], r8d
0x1400059f5  jbe     short loc_140005A04
0x1400059f7  mov     eax, [r15+8]
0x1400059fb  cmp     [rcx+8], eax
0x1400059fe  jz      loc_140005BDC
0x140005a04  add     rcx, rbp
0x140005a07  cmp     rcx, rdx
0x140005a0a  jnz     short loc_1400059F1
0x140005a0c  movzx   eax, word ptr [rbx+22h]
0x140005a10  mov     r8d, 1
0x140005a16  movzx   ecx, word ptr [rbx+20h]
0x140005a1a  add     eax, r8d
0x140005a1d  xor     edx, edx
0x140005a1f  div     ecx
0x140005a21  mov     ecx, r8d
0x140005a24  movzx   eax, dx
0x140005a27  mov     [rbx+22h], dx
0x140005a2b  lea     rsi, [rax+rax*4]
0x140005a2f  mov     rax, [rbx+8]
0x140005a33  shl     rsi, 4
0x140005a37  lock xadd [rax], ecx
0x140005a3b  add     ecx, r8d
0x140005a3e  lea     r13, [rsi+rdi]
0x140005a42  mov     [rsi+rdi+4], ecx
0x140005a46  lea     rbx, [rdi+20h]
0x140005a4a  mov     eax, [r15+8]
0x140005a4e  add     rbx, rsi
0x140005a51  mov     [rsi+rdi+8], eax
0x140005a55  or      r14, 0FFFFFFFFFFFFFFFFh
0x140005a59  mov     [r13+10h], r12
0x140005a5d  movzx   eax, word ptr [r15+40h]
0x140005a62  mov     [rsi+rdi+18h], ax
0x140005a67  mov     al, [r15]
0x140005a6a  mov     [rsi+rdi+1Ah], al
0x140005a6e  mov     [rbx], r12
0x140005a71  mov     rax, [r15+88h]
0x140005a78  mov     [rsi+rdi+28h], rax
0x140005a7d  mov     rax, [r15+90h]
0x140005a84  mov     [rsi+rdi+30h], rax
0x140005a89  mov     [rsi+rdi+38h], r12
0x140005a8e  mov     rcx, [r15+38h]
0x140005a92  test    rcx, rcx
0x140005a95  jnz     short loc_140005A9C
0x140005a97  mov     edx, r8d
0x140005a9a  jmp     short loc_140005AAC
0x140005a9c  mov     rax, r14
0x140005a9f  inc     rax
0x140005aa2  cmp     [rcx+rax], r12b
0x140005aa6  jnz     short loc_140005A9F
0x140005aa8  lea     rdx, [rax+1]
0x140005aac  mov     rcx, [r15+80h]
0x140005ab3  test    rcx, rcx
0x140005ab6  jz      short loc_140005AC8
0x140005ab8  mov     rax, r14
0x140005abb  inc     rax
0x140005abe  cmp     [rcx+rax], r12b
0x140005ac2  jnz     short loc_140005ABB
0x140005ac4  lea     r8, [rax+1]; unsigned __int64
0x140005ac8  mov     rcx, [r15+18h]
0x140005acc  test    rcx, rcx
0x140005acf  jnz     short loc_140005AD6
0x140005ad1  lea     eax, [rcx+2]
0x140005ad4  jmp     short loc_140005AEB
0x140005ad6  mov     rax, r14
0x140005ad9  inc     rax
0x140005adc  cmp     [rcx+rax*2], r12w
0x140005ae1  jnz     short loc_140005AD9
0x140005ae3  lea     rax, ds:2[rax*2]
0x140005aeb  lea     rbp, [r8+rax]
0x140005aef  add     rbp, rdx
0x140005af2  cmp     [rsi+rdi+40h], r12
0x140005af7  jz      short loc_140005B00
0x140005af9  cmp     [rsi+rdi+48h], rbp
0x140005afe  jnb     short loc_140005B42
0x140005b00  mov     rdx, rbp; dwBytes
0x140005b03  mov     ecx, 8; dwFlags
0x140005b08  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005b0d  mov     r12, rax
0x140005b10  test    rax, rax
0x140005b13  jz      short loc_140005B3F
0x140005b15  mov     rbx, [rsi+rdi+40h]
0x140005b1a  call    cs:__imp_GetProcessHeap
0x140005b20  mov     r8, rbx; lpMem
0x140005b23  xor     edx, edx; dwFlags
0x140005b25  mov     rcx, rax; hHeap
0x140005b28  call    cs:__imp_HeapFree
0x140005b2e  lea     rbx, [rdi+20h]
0x140005b32  mov     [rsi+rdi+40h], r12
0x140005b37  add     rbx, rsi
0x140005b3a  mov     [rsi+rdi+48h], rbp
0x140005b3f  xor     r12d, r12d
0x140005b42  mov     rcx, [rsi+rdi+40h]
0x140005b47  test    rcx, rcx
0x140005b4a  jz      loc_140005BDC
0x140005b50  mov     rbp, [rsi+rdi+48h]
0x140005b55  lea     r9, [r13+10h]
0x140005b59  mov     r8, [r15+38h]
0x140005b5d  add     rbp, rcx
0x140005b60  mov     rdx, rbp
0x140005b63  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140005b68  mov     r8, [r15+80h]
0x140005b6f  mov     r9, rbx
0x140005b72  mov     rdx, rbp
0x140005b75  mov     rcx, rax
0x140005b78  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140005b7d  mov     rbx, rax
0x140005b80  cmp     rax, rbp
0x140005b83  jz      short loc_140005BC7
0x140005b85  mov     r8, [r15+18h]; Source
0x140005b89  test    r8, r8
0x140005b8c  jz      short loc_140005BC7
0x140005b8e  cmp     [r8], r12w
0x140005b92  jz      short loc_140005BC7
0x140005b94  inc     r14
0x140005b97  cmp     [r8+r14*2], r12w
0x140005b9c  jnz     short loc_140005B94
0x140005b9e  mov     rdx, rbp
0x140005ba1  lea     r14, ds:2[r14*2]
0x140005ba9  sub     rdx, rbx; DestinationSize
0x140005bac  cmp     rdx, r14
0x140005baf  jb      short loc_140005BC7
0x140005bb1  mov     r9, r14; SourceSize
0x140005bb4  mov     rcx, rbx; Destination
0x140005bb7  call    cs:__imp_memcpy_s
0x140005bbd  mov     [rsi+rdi+38h], rbx
0x140005bc2  add     rbx, r14
0x140005bc5  jmp     short loc_140005BCC
0x140005bc7  mov     [rsi+rdi+38h], r12
0x140005bcc  sub     rbp, rbx
0x140005bcf  xor     edx, edx; Val
0x140005bd1  mov     r8, rbp; Size
0x140005bd4  mov     rcx, rbx; void *
0x140005bd7  call    memset_0
0x140005bdc  add     rsp, 28h
0x140005be0  pop     r15
0x140005be2  pop     r14
0x140005be4  pop     r13
0x140005be6  pop     r12
0x140005be8  pop     rdi
0x140005be9  pop     rsi
0x140005bea  pop     rbp
0x140005beb  pop     rbx
0x140005bec  retn
```
