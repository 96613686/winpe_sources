# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800091a0`
- end: `0x1800092d6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180009538`

## callees

- `0x1800056e0`
- `0x180006c50`
- `0x180006cc8`
- `0x180008bc0`
- `0x180009078`
- `0x180009098`
- `0x1800091a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000925d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000925d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000924f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000924f`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int16 **v3; // r14
  unsigned __int64 v6; // rbp
  const char *v7; // rdx
  unsigned __int64 v8; // rbp
  const char *v9; // rdx
  SIZE_T v10; // rbp
  SIZE_T *v11; // rdi
  LPVOID v12; // r14
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  const char *v16; // rbx
  char *v17; // rax
  unsigned __int16 *v18; // rax
  char *v19; // rax

  *((_DWORD *)this + 1) = a3;
  v3 = (unsigned __int16 **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v8 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v7) + v6;
  v10 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v9) + v8;
  v11 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v11 < v10 )
  {
    v12 = wil::details::ProcessHeapAlloc(8u, v10);
    if ( v12 )
    {
      v13 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
      *((_QWORD *)this + 8) = v12;
      *v11 = v10;
    }
    v3 = (unsigned __int16 **)((char *)this + 56);
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = wil::details::WriteResultString<char const *>(v15, v16, *((wil::details **)a2 + 7), (char **)this + 2);
    v18 = (unsigned __int16 *)wil::details::WriteResultString<char const *>(
                                v17,
                                v16,
                                *((wil::details **)a2 + 16),
                                (char **)this + 4);
    v19 = wil::details::WriteResultString<unsigned short const *>(
            v18,
            (const unsigned __int16 *)v16,
            *((wil::details **)a2 + 3),
            v3);
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x1800091a0  push    rbx
0x1800091a2  push    rbp
0x1800091a3  push    rsi
0x1800091a4  push    rdi
0x1800091a5  push    r12
0x1800091a7  push    r13
0x1800091a9  push    r14
0x1800091ab  push    r15
0x1800091ad  sub     rsp, 28h
0x1800091b1  mov     [rcx+4], r8d
0x1800091b5  lea     r14, [rcx+38h]
0x1800091b9  mov     eax, [rdx+8]
0x1800091bc  mov     rsi, rcx
0x1800091bf  mov     [rcx+8], eax
0x1800091c2  mov     r15, rdx
0x1800091c5  mov     qword ptr [rcx+10h], 0
0x1800091cd  movzx   eax, word ptr [rdx+40h]
0x1800091d1  mov     [rcx+18h], ax
0x1800091d5  mov     al, [rdx]
0x1800091d7  mov     [rcx+1Ah], al
0x1800091da  mov     qword ptr [rcx+20h], 0
0x1800091e2  mov     rax, [rdx+88h]
0x1800091e9  mov     [rcx+28h], rax
0x1800091ed  mov     rax, [rdx+90h]
0x1800091f4  mov     [rcx+30h], rax
0x1800091f8  mov     qword ptr [r14], 0
0x1800091ff  mov     rcx, [rdx+18h]; this
0x180009203  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180009208  mov     rcx, [r15+38h]; this
0x18000920c  mov     rbp, rax
0x18000920f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180009214  mov     rcx, [r15+80h]; this
0x18000921b  add     rbp, rax
0x18000921e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180009223  add     rbp, rax
0x180009226  lea     rdi, [rsi+48h]
0x18000922a  cmp     qword ptr [rsi+40h], 0
0x18000922f  jz      short loc_180009236
0x180009231  cmp     [rdi], rbp
0x180009234  jnb     short loc_18000926E
0x180009236  mov     rdx, rbp; dwBytes
0x180009239  mov     ecx, 8; dwFlags
0x18000923e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009243  mov     r14, rax
0x180009246  test    rax, rax
0x180009249  jz      short loc_18000926A
0x18000924b  mov     rbx, [rsi+40h]
0x18000924f  call    cs:__imp_GetProcessHeap
0x180009255  mov     r8, rbx; lpMem
0x180009258  xor     edx, edx; dwFlags
0x18000925a  mov     rcx, rax; hHeap
0x18000925d  call    cs:__imp_HeapFree
0x180009263  mov     [rsi+40h], r14
0x180009267  mov     [rdi], rbp
0x18000926a  lea     r14, [rsi+38h]
0x18000926e  mov     rcx, [rsi+40h]; Destination
0x180009272  test    rcx, rcx
0x180009275  jz      short loc_1800092C5
0x180009277  mov     rbx, [rdi]
0x18000927a  lea     r9, [rsi+10h]
0x18000927e  mov     r8, [r15+38h]
0x180009282  add     rbx, rcx
0x180009285  mov     rdx, rbx
0x180009288  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000928d  mov     r8, [r15+80h]
0x180009294  lea     r9, [rsi+20h]
0x180009298  mov     rdx, rbx
0x18000929b  mov     rcx, rax; Destination
0x18000929e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800092a3  mov     r8, [r15+18h]
0x1800092a7  mov     r9, r14
0x1800092aa  mov     rdx, rbx
0x1800092ad  mov     rcx, rax; Destination
0x1800092b0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800092b5  sub     rbx, rax
0x1800092b8  xor     edx, edx; Val
0x1800092ba  mov     r8, rbx; Size
0x1800092bd  mov     rcx, rax; void *
0x1800092c0  call    memset_0
0x1800092c5  add     rsp, 28h
0x1800092c9  pop     r15
0x1800092cb  pop     r14
0x1800092cd  pop     r13
0x1800092cf  pop     r12
0x1800092d1  pop     rdi
0x1800092d2  pop     rsi
0x1800092d3  pop     rbp
0x1800092d4  pop     rbx
0x1800092d5  retn
```
