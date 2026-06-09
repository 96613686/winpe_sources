# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18004c10c`
- end: `0x18004c242`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18004c2d8`

## callees

- `0x18003f080`
- `0x18003f0f8`
- `0x18003fa84`
- `0x18003faa4`
- `0x18004afd4`
- `0x18004c10c`
- `0x18009e2c2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c1bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c1bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c1c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c1c9`

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
0x18004c10c  push    rbx
0x18004c10e  push    rbp
0x18004c10f  push    rsi
0x18004c110  push    rdi
0x18004c111  push    r12
0x18004c113  push    r13
0x18004c115  push    r14
0x18004c117  push    r15
0x18004c119  sub     rsp, 28h
0x18004c11d  mov     [rcx+4], r8d
0x18004c121  lea     r14, [rcx+38h]
0x18004c125  mov     eax, [rdx+8]
0x18004c128  mov     rsi, rcx
0x18004c12b  mov     [rcx+8], eax
0x18004c12e  mov     r15, rdx
0x18004c131  mov     qword ptr [rcx+10h], 0
0x18004c139  movzx   eax, word ptr [rdx+40h]
0x18004c13d  mov     [rcx+18h], ax
0x18004c141  mov     al, [rdx]
0x18004c143  mov     [rcx+1Ah], al
0x18004c146  mov     qword ptr [rcx+20h], 0
0x18004c14e  mov     rax, [rdx+88h]
0x18004c155  mov     [rcx+28h], rax
0x18004c159  mov     rax, [rdx+90h]
0x18004c160  mov     [rcx+30h], rax
0x18004c164  mov     qword ptr [r14], 0
0x18004c16b  mov     rcx, [rdx+18h]; this
0x18004c16f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18004c174  mov     rcx, [r15+38h]; this
0x18004c178  mov     rbp, rax
0x18004c17b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18004c180  mov     rcx, [r15+80h]; this
0x18004c187  add     rbp, rax
0x18004c18a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18004c18f  add     rbp, rax
0x18004c192  lea     rdi, [rsi+48h]
0x18004c196  cmp     qword ptr [rsi+40h], 0
0x18004c19b  jz      short loc_18004C1A2
0x18004c19d  cmp     [rdi], rbp
0x18004c1a0  jnb     short loc_18004C1DA
0x18004c1a2  mov     rdx, rbp; dwBytes
0x18004c1a5  mov     ecx, 8; dwFlags
0x18004c1aa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18004c1af  mov     r14, rax
0x18004c1b2  test    rax, rax
0x18004c1b5  jz      short loc_18004C1D6
0x18004c1b7  mov     rbx, [rsi+40h]
0x18004c1bb  call    cs:__imp_GetProcessHeap
0x18004c1c1  mov     r8, rbx; lpMem
0x18004c1c4  xor     edx, edx; dwFlags
0x18004c1c6  mov     rcx, rax; hHeap
0x18004c1c9  call    cs:__imp_HeapFree
0x18004c1cf  mov     [rsi+40h], r14
0x18004c1d3  mov     [rdi], rbp
0x18004c1d6  lea     r14, [rsi+38h]
0x18004c1da  mov     rcx, [rsi+40h]; Destination
0x18004c1de  test    rcx, rcx
0x18004c1e1  jz      short loc_18004C231
0x18004c1e3  mov     rbx, [rdi]
0x18004c1e6  lea     r9, [rsi+10h]
0x18004c1ea  mov     r8, [r15+38h]
0x18004c1ee  add     rbx, rcx
0x18004c1f1  mov     rdx, rbx
0x18004c1f4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18004c1f9  mov     r8, [r15+80h]
0x18004c200  lea     r9, [rsi+20h]
0x18004c204  mov     rdx, rbx
0x18004c207  mov     rcx, rax; Destination
0x18004c20a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18004c20f  mov     r8, [r15+18h]
0x18004c213  mov     r9, r14
0x18004c216  mov     rdx, rbx
0x18004c219  mov     rcx, rax; Destination
0x18004c21c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18004c221  sub     rbx, rax
0x18004c224  xor     edx, edx; Val
0x18004c226  mov     r8, rbx; Size
0x18004c229  mov     rcx, rax; void *
0x18004c22c  call    memset_0
0x18004c231  add     rsp, 28h
0x18004c235  pop     r15
0x18004c237  pop     r14
0x18004c239  pop     r13
0x18004c23b  pop     r12
0x18004c23d  pop     rdi
0x18004c23e  pop     rsi
0x18004c23f  pop     rbp
0x18004c240  pop     rbx
0x18004c241  retn
```
