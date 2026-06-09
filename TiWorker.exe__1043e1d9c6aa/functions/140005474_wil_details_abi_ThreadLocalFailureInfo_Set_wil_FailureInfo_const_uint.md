# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140005474`
- end: `0x1400055e4`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400055ec`

## callees

- `0x140002cf8`
- `0x140003a2c`
- `0x1400051f0`
- `0x140005358`
- `0x140005378`
- `0x140005474`
- `0x140005ef8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000551c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000551c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000552a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000552a`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  char **v3; // rbx
  char **v4; // rsi
  unsigned __int64 v7; // r15
  const char *v8; // rdx
  unsigned __int64 v9; // r15
  const char *v10; // rdx
  SIZE_T v11; // r15
  SIZE_T *v12; // rdi
  LPVOID v13; // r12
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  char *v16; // rcx
  const char *v17; // rdi
  char *v18; // rax
  const wchar_t *v19; // rdx
  char *v20; // rbx
  wil::details *v21; // rcx
  rsize_t v22; // rax
  const void *v23; // rcx
  rsize_t v24; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (char **)((char *)this + 32);
  v4 = (char **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const wchar_t *)a2);
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v8) + v7;
  v11 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v10) + v9;
  v12 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v12 < v11 )
  {
    v13 = wil::details::ProcessHeapAlloc(8u, v11);
    if ( v13 )
    {
      v14 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
      *((_QWORD *)this + 8) = v13;
      v3 = (char **)((char *)this + 32);
      *v12 = v11;
    }
  }
  v16 = (char *)*((_QWORD *)this + 8);
  if ( v16 )
  {
    v17 = &v16[*v12];
    v18 = wil::details::WriteResultString<char const *>(v16, v17, *((wil::details **)a2 + 7), (char **)this + 2);
    v20 = wil::details::WriteResultString<char const *>(v18, v17, *((wil::details **)a2 + 16), v3);
    if ( v20 != v17
      && (v21 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v21
      && (v22 = wil::details::ResultStringSize(v21, v19), v24 = v22, v17 - v20 >= v22) )
    {
      memcpy_s(v20, v17 - v20, v23, v22);
      if ( v4 )
        *v4 = v20;
      v20 += v24;
    }
    else if ( v4 )
    {
      *v4 = 0;
    }
    memset_0(v20, 0, v17 - v20);
  }
}

```

## disassembly

```asm
0x140005474  push    rbx
0x140005476  push    rbp
0x140005477  push    rsi
0x140005478  push    rdi
0x140005479  push    r12
0x14000547b  push    r13
0x14000547d  push    r14
0x14000547f  push    r15
0x140005481  sub     rsp, 28h
0x140005485  mov     [rcx+4], r8d
0x140005489  lea     rbx, [rcx+20h]
0x14000548d  mov     eax, [rdx+8]
0x140005490  lea     rsi, [rcx+38h]
0x140005494  mov     [rcx+8], eax
0x140005497  xor     r12d, r12d
0x14000549a  mov     [rcx+10h], r12
0x14000549e  mov     rbp, rcx
0x1400054a1  movzx   eax, word ptr [rdx+40h]
0x1400054a5  mov     r14, rdx
0x1400054a8  mov     [rcx+18h], ax
0x1400054ac  mov     al, [rdx]
0x1400054ae  mov     [rcx+1Ah], al
0x1400054b1  mov     [rbx], r12
0x1400054b4  mov     rax, [rdx+88h]
0x1400054bb  mov     [rcx+28h], rax
0x1400054bf  mov     rax, [rdx+90h]
0x1400054c6  mov     [rcx+30h], rax
0x1400054ca  mov     [rsi], r12
0x1400054cd  mov     rcx, [rdx+18h]; this
0x1400054d1  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x1400054d6  mov     rcx, [r14+38h]; this
0x1400054da  mov     r15, rax
0x1400054dd  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400054e2  mov     rcx, [r14+80h]; this
0x1400054e9  add     r15, rax
0x1400054ec  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400054f1  add     r15, rax
0x1400054f4  lea     rdi, [rbp+48h]
0x1400054f8  cmp     [rbp+40h], r12
0x1400054fc  jz      short loc_140005503
0x1400054fe  cmp     [rdi], r15
0x140005501  jnb     short loc_14000553E
0x140005503  mov     rdx, r15; dwBytes
0x140005506  mov     ecx, 8; dwFlags
0x14000550b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005510  mov     r12, rax
0x140005513  test    rax, rax
0x140005516  jz      short loc_14000553B
0x140005518  mov     rbx, [rbp+40h]
0x14000551c  call    cs:__imp_GetProcessHeap
0x140005522  mov     r8, rbx; lpMem
0x140005525  xor     edx, edx; dwFlags
0x140005527  mov     rcx, rax; hHeap
0x14000552a  call    cs:__imp_HeapFree
0x140005530  mov     [rbp+40h], r12
0x140005534  lea     rbx, [rbp+20h]
0x140005538  mov     [rdi], r15
0x14000553b  xor     r12d, r12d
0x14000553e  mov     rcx, [rbp+40h]; Destination
0x140005542  test    rcx, rcx
0x140005545  jz      loc_1400055D3
0x14000554b  mov     rdi, [rdi]
0x14000554e  lea     r9, [rbp+10h]
0x140005552  mov     r8, [r14+38h]
0x140005556  add     rdi, rcx
0x140005559  mov     rdx, rdi
0x14000555c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140005561  mov     r8, [r14+80h]
0x140005568  mov     r9, rbx
0x14000556b  mov     rdx, rdi
0x14000556e  mov     rcx, rax; Destination
0x140005571  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140005576  mov     rbx, rax
0x140005579  cmp     rax, rdi
0x14000557c  jz      short loc_1400055BB
0x14000557e  mov     rcx, [r14+18h]; this
0x140005582  test    rcx, rcx
0x140005585  jz      short loc_1400055BB
0x140005587  cmp     [rcx], r12w
0x14000558b  jz      short loc_1400055BB
0x14000558d  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x140005592  mov     rdx, rdi
0x140005595  mov     r14, rax
0x140005598  sub     rdx, rbx; DestinationSize
0x14000559b  cmp     rdx, rax
0x14000559e  jb      short loc_1400055BB
0x1400055a0  mov     r8, rcx; Source
0x1400055a3  mov     r9, rax; SourceSize
0x1400055a6  mov     rcx, rbx; Destination
0x1400055a9  call    memcpy_s
0x1400055ae  test    rsi, rsi
0x1400055b1  jz      short loc_1400055B6
0x1400055b3  mov     [rsi], rbx
0x1400055b6  add     rbx, r14
0x1400055b9  jmp     short loc_1400055C3
0x1400055bb  test    rsi, rsi
0x1400055be  jz      short loc_1400055C3
0x1400055c0  mov     [rsi], r12
0x1400055c3  sub     rdi, rbx
0x1400055c6  xor     edx, edx; Val
0x1400055c8  mov     r8, rdi; Size
0x1400055cb  mov     rcx, rbx; void *
0x1400055ce  call    memset_0
0x1400055d3  add     rsp, 28h
0x1400055d7  pop     r15
0x1400055d9  pop     r14
0x1400055db  pop     r13
0x1400055dd  pop     r12
0x1400055df  pop     rdi
0x1400055e0  pop     rsi
0x1400055e1  pop     rbp
0x1400055e2  pop     rbx
0x1400055e3  retn
```
