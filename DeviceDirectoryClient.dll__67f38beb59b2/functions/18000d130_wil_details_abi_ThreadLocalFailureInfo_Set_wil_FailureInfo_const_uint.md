# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000d130`
- end: `0x18000d266`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d5b8`

## callees

- `0x180002fc0`
- `0x180008310`
- `0x180008388`
- `0x18000b32c`
- `0x18000cfa8`
- `0x18000cfc8`
- `0x18000d130`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d1ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d1ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d1df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d1df`

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
0x18000d130  push    rbx
0x18000d132  push    rbp
0x18000d133  push    rsi
0x18000d134  push    rdi
0x18000d135  push    r12
0x18000d137  push    r13
0x18000d139  push    r14
0x18000d13b  push    r15
0x18000d13d  sub     rsp, 28h
0x18000d141  mov     [rcx+4], r8d
0x18000d145  lea     r14, [rcx+38h]
0x18000d149  mov     eax, [rdx+8]
0x18000d14c  mov     rsi, rcx
0x18000d14f  mov     [rcx+8], eax
0x18000d152  mov     r15, rdx
0x18000d155  mov     qword ptr [rcx+10h], 0
0x18000d15d  movzx   eax, word ptr [rdx+40h]
0x18000d161  mov     [rcx+18h], ax
0x18000d165  mov     al, [rdx]
0x18000d167  mov     [rcx+1Ah], al
0x18000d16a  mov     qword ptr [rcx+20h], 0
0x18000d172  mov     rax, [rdx+88h]
0x18000d179  mov     [rcx+28h], rax
0x18000d17d  mov     rax, [rdx+90h]
0x18000d184  mov     [rcx+30h], rax
0x18000d188  mov     qword ptr [r14], 0
0x18000d18f  mov     rcx, [rdx+18h]; this
0x18000d193  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000d198  mov     rcx, [r15+38h]; this
0x18000d19c  mov     rbp, rax
0x18000d19f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000d1a4  mov     rcx, [r15+80h]; this
0x18000d1ab  add     rbp, rax
0x18000d1ae  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000d1b3  add     rbp, rax
0x18000d1b6  lea     rdi, [rsi+48h]
0x18000d1ba  cmp     qword ptr [rsi+40h], 0
0x18000d1bf  jz      short loc_18000D1C6
0x18000d1c1  cmp     [rdi], rbp
0x18000d1c4  jnb     short loc_18000D1FE
0x18000d1c6  mov     rdx, rbp; dwBytes
0x18000d1c9  mov     ecx, 8; dwFlags
0x18000d1ce  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d1d3  mov     r14, rax
0x18000d1d6  test    rax, rax
0x18000d1d9  jz      short loc_18000D1FA
0x18000d1db  mov     rbx, [rsi+40h]
0x18000d1df  call    cs:__imp_GetProcessHeap
0x18000d1e5  mov     r8, rbx; lpMem
0x18000d1e8  xor     edx, edx; dwFlags
0x18000d1ea  mov     rcx, rax; hHeap
0x18000d1ed  call    cs:__imp_HeapFree
0x18000d1f3  mov     [rsi+40h], r14
0x18000d1f7  mov     [rdi], rbp
0x18000d1fa  lea     r14, [rsi+38h]
0x18000d1fe  mov     rcx, [rsi+40h]; Destination
0x18000d202  test    rcx, rcx
0x18000d205  jz      short loc_18000D255
0x18000d207  mov     rbx, [rdi]
0x18000d20a  lea     r9, [rsi+10h]
0x18000d20e  mov     r8, [r15+38h]
0x18000d212  add     rbx, rcx
0x18000d215  mov     rdx, rbx
0x18000d218  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000d21d  mov     r8, [r15+80h]
0x18000d224  lea     r9, [rsi+20h]
0x18000d228  mov     rdx, rbx
0x18000d22b  mov     rcx, rax; Destination
0x18000d22e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000d233  mov     r8, [r15+18h]
0x18000d237  mov     r9, r14
0x18000d23a  mov     rdx, rbx
0x18000d23d  mov     rcx, rax; Destination
0x18000d240  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000d245  sub     rbx, rax
0x18000d248  xor     edx, edx; Val
0x18000d24a  mov     r8, rbx; Size
0x18000d24d  mov     rcx, rax; void *
0x18000d250  call    memset_0
0x18000d255  add     rsp, 28h
0x18000d259  pop     r15
0x18000d25b  pop     r14
0x18000d25d  pop     r13
0x18000d25f  pop     r12
0x18000d261  pop     rdi
0x18000d262  pop     rsi
0x18000d263  pop     rbp
0x18000d264  pop     rbx
0x18000d265  retn
```
