# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140005564`
- end: `0x1400056d4`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400056dc`

## callees

- `0x140002de4`
- `0x140003b1c`
- `0x1400052e0`
- `0x140005448`
- `0x140005468`
- `0x140005564`
- `0x140005ff8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000561a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000561a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000560c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000560c`

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
0x140005564  push    rbx
0x140005566  push    rbp
0x140005567  push    rsi
0x140005568  push    rdi
0x140005569  push    r12
0x14000556b  push    r13
0x14000556d  push    r14
0x14000556f  push    r15
0x140005571  sub     rsp, 28h
0x140005575  mov     [rcx+4], r8d
0x140005579  lea     rbx, [rcx+20h]
0x14000557d  mov     eax, [rdx+8]
0x140005580  lea     rsi, [rcx+38h]
0x140005584  mov     [rcx+8], eax
0x140005587  xor     r12d, r12d
0x14000558a  mov     [rcx+10h], r12
0x14000558e  mov     rbp, rcx
0x140005591  movzx   eax, word ptr [rdx+40h]
0x140005595  mov     r14, rdx
0x140005598  mov     [rcx+18h], ax
0x14000559c  mov     al, [rdx]
0x14000559e  mov     [rcx+1Ah], al
0x1400055a1  mov     [rbx], r12
0x1400055a4  mov     rax, [rdx+88h]
0x1400055ab  mov     [rcx+28h], rax
0x1400055af  mov     rax, [rdx+90h]
0x1400055b6  mov     [rcx+30h], rax
0x1400055ba  mov     [rsi], r12
0x1400055bd  mov     rcx, [rdx+18h]; this
0x1400055c1  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x1400055c6  mov     rcx, [r14+38h]; this
0x1400055ca  mov     r15, rax
0x1400055cd  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400055d2  mov     rcx, [r14+80h]; this
0x1400055d9  add     r15, rax
0x1400055dc  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400055e1  add     r15, rax
0x1400055e4  lea     rdi, [rbp+48h]
0x1400055e8  cmp     [rbp+40h], r12
0x1400055ec  jz      short loc_1400055F3
0x1400055ee  cmp     [rdi], r15
0x1400055f1  jnb     short loc_14000562E
0x1400055f3  mov     rdx, r15; dwBytes
0x1400055f6  mov     ecx, 8; dwFlags
0x1400055fb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005600  mov     r12, rax
0x140005603  test    rax, rax
0x140005606  jz      short loc_14000562B
0x140005608  mov     rbx, [rbp+40h]
0x14000560c  call    cs:__imp_GetProcessHeap
0x140005612  mov     r8, rbx; lpMem
0x140005615  xor     edx, edx; dwFlags
0x140005617  mov     rcx, rax; hHeap
0x14000561a  call    cs:__imp_HeapFree
0x140005620  mov     [rbp+40h], r12
0x140005624  lea     rbx, [rbp+20h]
0x140005628  mov     [rdi], r15
0x14000562b  xor     r12d, r12d
0x14000562e  mov     rcx, [rbp+40h]; Destination
0x140005632  test    rcx, rcx
0x140005635  jz      loc_1400056C3
0x14000563b  mov     rdi, [rdi]
0x14000563e  lea     r9, [rbp+10h]
0x140005642  mov     r8, [r14+38h]
0x140005646  add     rdi, rcx
0x140005649  mov     rdx, rdi
0x14000564c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140005651  mov     r8, [r14+80h]
0x140005658  mov     r9, rbx
0x14000565b  mov     rdx, rdi
0x14000565e  mov     rcx, rax; Destination
0x140005661  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140005666  mov     rbx, rax
0x140005669  cmp     rax, rdi
0x14000566c  jz      short loc_1400056AB
0x14000566e  mov     rcx, [r14+18h]; this
0x140005672  test    rcx, rcx
0x140005675  jz      short loc_1400056AB
0x140005677  cmp     [rcx], r12w
0x14000567b  jz      short loc_1400056AB
0x14000567d  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x140005682  mov     rdx, rdi
0x140005685  mov     r14, rax
0x140005688  sub     rdx, rbx; DestinationSize
0x14000568b  cmp     rdx, rax
0x14000568e  jb      short loc_1400056AB
0x140005690  mov     r8, rcx; Source
0x140005693  mov     r9, rax; SourceSize
0x140005696  mov     rcx, rbx; Destination
0x140005699  call    memcpy_s
0x14000569e  test    rsi, rsi
0x1400056a1  jz      short loc_1400056A6
0x1400056a3  mov     [rsi], rbx
0x1400056a6  add     rbx, r14
0x1400056a9  jmp     short loc_1400056B3
0x1400056ab  test    rsi, rsi
0x1400056ae  jz      short loc_1400056B3
0x1400056b0  mov     [rsi], r12
0x1400056b3  sub     rdi, rbx
0x1400056b6  xor     edx, edx; Val
0x1400056b8  mov     r8, rdi; Size
0x1400056bb  mov     rcx, rbx; void *
0x1400056be  call    memset_0
0x1400056c3  add     rsp, 28h
0x1400056c7  pop     r15
0x1400056c9  pop     r14
0x1400056cb  pop     r13
0x1400056cd  pop     r12
0x1400056cf  pop     rdi
0x1400056d0  pop     rsi
0x1400056d1  pop     rbp
0x1400056d2  pop     rbx
0x1400056d3  retn
```
