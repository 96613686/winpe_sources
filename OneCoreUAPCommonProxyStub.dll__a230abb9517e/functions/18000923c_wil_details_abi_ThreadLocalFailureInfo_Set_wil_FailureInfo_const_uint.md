# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000923c`
- end: `0x180009372`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800095d4`

## callees

- `0x1800045ba`
- `0x1800068a4`
- `0x18000691c`
- `0x180008acc`
- `0x180009138`
- `0x180009158`
- `0x18000923c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800092f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800092f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800092eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800092eb`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int64 v5; // rbp
  const char *v6; // rdx
  unsigned __int64 v7; // rbp
  const char *v8; // rdx
  SIZE_T v9; // rbp
  SIZE_T *v10; // rdi
  LPVOID v11; // r14
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  char *v14; // rcx
  char *v15; // rbx
  void *v16; // rax
  void *v17; // rax
  void *v18; // rax

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v6) + v5;
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v8) + v7;
  v10 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v10 < v9 )
  {
    v11 = wil::details::ProcessHeapAlloc(8u, v9);
    if ( v11 )
    {
      v12 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
      *((_QWORD *)this + 8) = v11;
      *v10 = v9;
    }
  }
  v14 = (char *)*((_QWORD *)this + 8);
  if ( v14 )
  {
    v15 = &v14[*v10];
    v16 = (void *)wil::details::WriteResultString<char const *>(v14);
    v17 = (void *)wil::details::WriteResultString<char const *>(v16);
    v18 = (void *)wil::details::WriteResultString<unsigned short const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x18000923c  push    rbx
0x18000923e  push    rbp
0x18000923f  push    rsi
0x180009240  push    rdi
0x180009241  push    r12
0x180009243  push    r13
0x180009245  push    r14
0x180009247  push    r15
0x180009249  sub     rsp, 28h
0x18000924d  mov     [rcx+4], r8d
0x180009251  lea     r14, [rcx+38h]
0x180009255  mov     eax, [rdx+8]
0x180009258  mov     rsi, rcx
0x18000925b  mov     [rcx+8], eax
0x18000925e  mov     r15, rdx
0x180009261  mov     qword ptr [rcx+10h], 0
0x180009269  movzx   eax, word ptr [rdx+40h]
0x18000926d  mov     [rcx+18h], ax
0x180009271  mov     al, [rdx]
0x180009273  mov     [rcx+1Ah], al
0x180009276  mov     qword ptr [rcx+20h], 0
0x18000927e  mov     rax, [rdx+88h]
0x180009285  mov     [rcx+28h], rax
0x180009289  mov     rax, [rdx+90h]
0x180009290  mov     [rcx+30h], rax
0x180009294  mov     qword ptr [r14], 0
0x18000929b  mov     rcx, [rdx+18h]; this
0x18000929f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800092a4  mov     rcx, [r15+38h]; this
0x1800092a8  mov     rbp, rax
0x1800092ab  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800092b0  mov     rcx, [r15+80h]; this
0x1800092b7  add     rbp, rax
0x1800092ba  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800092bf  add     rbp, rax
0x1800092c2  lea     rdi, [rsi+48h]
0x1800092c6  cmp     qword ptr [rsi+40h], 0
0x1800092cb  jz      short loc_1800092D2
0x1800092cd  cmp     [rdi], rbp
0x1800092d0  jnb     short loc_18000930A
0x1800092d2  mov     rdx, rbp; dwBytes
0x1800092d5  mov     ecx, 8; dwFlags
0x1800092da  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800092df  mov     r14, rax
0x1800092e2  test    rax, rax
0x1800092e5  jz      short loc_180009306
0x1800092e7  mov     rbx, [rsi+40h]
0x1800092eb  call    cs:__imp_GetProcessHeap
0x1800092f1  mov     r8, rbx; lpMem
0x1800092f4  xor     edx, edx; dwFlags
0x1800092f6  mov     rcx, rax; hHeap
0x1800092f9  call    cs:__imp_HeapFree
0x1800092ff  mov     [rsi+40h], r14
0x180009303  mov     [rdi], rbp
0x180009306  lea     r14, [rsi+38h]
0x18000930a  mov     rcx, [rsi+40h]; Destination
0x18000930e  test    rcx, rcx
0x180009311  jz      short loc_180009361
0x180009313  mov     rbx, [rdi]
0x180009316  lea     r9, [rsi+10h]
0x18000931a  mov     r8, [r15+38h]
0x18000931e  add     rbx, rcx
0x180009321  mov     rdx, rbx
0x180009324  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009329  mov     r8, [r15+80h]
0x180009330  lea     r9, [rsi+20h]
0x180009334  mov     rdx, rbx
0x180009337  mov     rcx, rax; Destination
0x18000933a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000933f  mov     r8, [r15+18h]
0x180009343  mov     r9, r14
0x180009346  mov     rdx, rbx
0x180009349  mov     rcx, rax; Destination
0x18000934c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180009351  sub     rbx, rax
0x180009354  xor     edx, edx; Val
0x180009356  mov     r8, rbx; Size
0x180009359  mov     rcx, rax; void *
0x18000935c  call    memset_0
0x180009361  add     rsp, 28h
0x180009365  pop     r15
0x180009367  pop     r14
0x180009369  pop     r13
0x18000936b  pop     r12
0x18000936d  pop     rdi
0x18000936e  pop     rsi
0x18000936f  pop     rbp
0x180009370  pop     rbx
0x180009371  retn
```
