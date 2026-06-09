# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000e810`
- end: `0x18000ea95`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800089f0`

## callees

- `0x180005110`
- `0x18000c118`
- `0x18000e810`
- `0x1800142d2`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ea5f`
- `msvcrt!memcpy_s` at `0x18000ea5f`
- `KERNEL32!GetProcessHeap` at `0x18000e9c2`
- `KERNEL32!GetProcessHeap` at `0x18000e9c2`
- `KERNEL32!HeapFree` at `0x18000e9d0`
- `KERNEL32!HeapFree` at `0x18000e9d0`

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
0x18000e810  push    rbx
0x18000e812  push    rbp
0x18000e813  push    rsi
0x18000e814  push    rdi
0x18000e815  push    r12
0x18000e817  push    r13
0x18000e819  push    r14
0x18000e81b  push    r15
0x18000e81d  sub     rsp, 28h
0x18000e821  mov     esi, [rcx+10h]
0x18000e824  xor     r12d, r12d
0x18000e827  mov     r15, rdx
0x18000e82a  mov     rbx, rcx
0x18000e82d  mov     ebp, 50h ; 'P'
0x18000e832  cmp     [rcx+18h], r12
0x18000e836  jnz     short loc_18000E86D
0x18000e838  test    esi, esi
0x18000e83a  jz      short loc_18000E86D
0x18000e83c  mov     edx, 190h; dwBytes
0x18000e841  lea     ecx, [rbp-48h]; dwFlags
0x18000e844  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000e849  mov     [rbx+18h], rax
0x18000e84d  test    rax, rax
0x18000e850  jz      short loc_18000E86D
0x18000e852  mov     dword ptr [rbx+20h], 5
0x18000e859  lea     rcx, [rax+190h]
0x18000e860  jmp     short loc_18000E868
0x18000e862  mov     [rax], bp
0x18000e865  add     rax, rbp
0x18000e868  cmp     rax, rcx
0x18000e86b  jnz     short loc_18000E862
0x18000e86d  mov     rdi, [rbx+18h]
0x18000e871  test    rdi, rdi
0x18000e874  jz      loc_18000EA84
0x18000e87a  test    esi, esi
0x18000e87c  jz      short loc_18000E8B4
0x18000e87e  movzx   eax, word ptr [rbx+20h]
0x18000e882  mov     rcx, rdi
0x18000e885  lea     rdx, [rax+rax*4]
0x18000e889  shl     rdx, 4
0x18000e88d  add     rdx, rdi
0x18000e890  cmp     rdi, rdx
0x18000e893  jz      short loc_18000E8B4
0x18000e895  mov     r8d, [rbx+10h]
0x18000e899  cmp     [rcx+4], r8d
0x18000e89d  jbe     short loc_18000E8AC
0x18000e89f  mov     eax, [r15+8]
0x18000e8a3  cmp     [rcx+8], eax
0x18000e8a6  jz      loc_18000EA84
0x18000e8ac  add     rcx, rbp
0x18000e8af  cmp     rcx, rdx
0x18000e8b2  jnz     short loc_18000E899
0x18000e8b4  movzx   eax, word ptr [rbx+22h]
0x18000e8b8  mov     r8d, 1
0x18000e8be  movzx   ecx, word ptr [rbx+20h]
0x18000e8c2  add     eax, r8d
0x18000e8c5  xor     edx, edx
0x18000e8c7  div     ecx
0x18000e8c9  mov     ecx, r8d
0x18000e8cc  movzx   eax, dx
0x18000e8cf  mov     [rbx+22h], dx
0x18000e8d3  lea     rsi, [rax+rax*4]
0x18000e8d7  mov     rax, [rbx+8]
0x18000e8db  shl     rsi, 4
0x18000e8df  lock xadd [rax], ecx
0x18000e8e3  add     ecx, r8d
0x18000e8e6  lea     r13, [rsi+rdi]
0x18000e8ea  mov     [rsi+rdi+4], ecx
0x18000e8ee  lea     rbx, [rdi+20h]
0x18000e8f2  mov     eax, [r15+8]
0x18000e8f6  add     rbx, rsi
0x18000e8f9  mov     [rsi+rdi+8], eax
0x18000e8fd  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000e901  mov     [r13+10h], r12
0x18000e905  movzx   eax, word ptr [r15+40h]
0x18000e90a  mov     [rsi+rdi+18h], ax
0x18000e90f  mov     al, [r15]
0x18000e912  mov     [rsi+rdi+1Ah], al
0x18000e916  mov     [rbx], r12
0x18000e919  mov     rax, [r15+88h]
0x18000e920  mov     [rsi+rdi+28h], rax
0x18000e925  mov     rax, [r15+90h]
0x18000e92c  mov     [rsi+rdi+30h], rax
0x18000e931  mov     [rsi+rdi+38h], r12
0x18000e936  mov     rcx, [r15+38h]
0x18000e93a  test    rcx, rcx
0x18000e93d  jnz     short loc_18000E944
0x18000e93f  mov     edx, r8d
0x18000e942  jmp     short loc_18000E954
0x18000e944  mov     rax, r14
0x18000e947  inc     rax
0x18000e94a  cmp     [rcx+rax], r12b
0x18000e94e  jnz     short loc_18000E947
0x18000e950  lea     rdx, [rax+1]
0x18000e954  mov     rcx, [r15+80h]
0x18000e95b  test    rcx, rcx
0x18000e95e  jz      short loc_18000E970
0x18000e960  mov     rax, r14
0x18000e963  inc     rax
0x18000e966  cmp     [rcx+rax], r12b
0x18000e96a  jnz     short loc_18000E963
0x18000e96c  lea     r8, [rax+1]; unsigned __int64
0x18000e970  mov     rcx, [r15+18h]
0x18000e974  test    rcx, rcx
0x18000e977  jnz     short loc_18000E97E
0x18000e979  lea     eax, [rcx+2]
0x18000e97c  jmp     short loc_18000E993
0x18000e97e  mov     rax, r14
0x18000e981  inc     rax
0x18000e984  cmp     [rcx+rax*2], r12w
0x18000e989  jnz     short loc_18000E981
0x18000e98b  lea     rax, ds:2[rax*2]
0x18000e993  lea     rbp, [r8+rax]
0x18000e997  add     rbp, rdx
0x18000e99a  cmp     [rsi+rdi+40h], r12
0x18000e99f  jz      short loc_18000E9A8
0x18000e9a1  cmp     [rsi+rdi+48h], rbp
0x18000e9a6  jnb     short loc_18000E9EA
0x18000e9a8  mov     rdx, rbp; dwBytes
0x18000e9ab  mov     ecx, 8; dwFlags
0x18000e9b0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000e9b5  mov     r12, rax
0x18000e9b8  test    rax, rax
0x18000e9bb  jz      short loc_18000E9E7
0x18000e9bd  mov     rbx, [rsi+rdi+40h]
0x18000e9c2  call    cs:__imp_GetProcessHeap
0x18000e9c8  mov     r8, rbx; lpMem
0x18000e9cb  xor     edx, edx; dwFlags
0x18000e9cd  mov     rcx, rax; hHeap
0x18000e9d0  call    cs:__imp_HeapFree
0x18000e9d6  lea     rbx, [rdi+20h]
0x18000e9da  mov     [rsi+rdi+40h], r12
0x18000e9df  add     rbx, rsi
0x18000e9e2  mov     [rsi+rdi+48h], rbp
0x18000e9e7  xor     r12d, r12d
0x18000e9ea  mov     rcx, [rsi+rdi+40h]
0x18000e9ef  test    rcx, rcx
0x18000e9f2  jz      loc_18000EA84
0x18000e9f8  mov     rbp, [rsi+rdi+48h]
0x18000e9fd  lea     r9, [r13+10h]
0x18000ea01  mov     r8, [r15+38h]
0x18000ea05  add     rbp, rcx
0x18000ea08  mov     rdx, rbp
0x18000ea0b  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000ea10  mov     r8, [r15+80h]
0x18000ea17  mov     r9, rbx
0x18000ea1a  mov     rdx, rbp
0x18000ea1d  mov     rcx, rax
0x18000ea20  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000ea25  mov     rbx, rax
0x18000ea28  cmp     rax, rbp
0x18000ea2b  jz      short loc_18000EA6F
0x18000ea2d  mov     r8, [r15+18h]; Source
0x18000ea31  test    r8, r8
0x18000ea34  jz      short loc_18000EA6F
0x18000ea36  cmp     [r8], r12w
0x18000ea3a  jz      short loc_18000EA6F
0x18000ea3c  inc     r14
0x18000ea3f  cmp     [r8+r14*2], r12w
0x18000ea44  jnz     short loc_18000EA3C
0x18000ea46  mov     rdx, rbp
0x18000ea49  lea     r14, ds:2[r14*2]
0x18000ea51  sub     rdx, rbx; DestinationSize
0x18000ea54  cmp     rdx, r14
0x18000ea57  jb      short loc_18000EA6F
0x18000ea59  mov     r9, r14; SourceSize
0x18000ea5c  mov     rcx, rbx; Destination
0x18000ea5f  call    cs:__imp_memcpy_s
0x18000ea65  mov     [rsi+rdi+38h], rbx
0x18000ea6a  add     rbx, r14
0x18000ea6d  jmp     short loc_18000EA74
0x18000ea6f  mov     [rsi+rdi+38h], r12
0x18000ea74  sub     rbp, rbx
0x18000ea77  xor     edx, edx; Val
0x18000ea79  mov     r8, rbp; Size
0x18000ea7c  mov     rcx, rbx; void *
0x18000ea7f  call    memset_0
0x18000ea84  add     rsp, 28h
0x18000ea88  pop     r15
0x18000ea8a  pop     r14
0x18000ea8c  pop     r13
0x18000ea8e  pop     r12
0x18000ea90  pop     rdi
0x18000ea91  pop     rsi
0x18000ea92  pop     rbp
0x18000ea93  pop     rbx
0x18000ea94  retn
```
