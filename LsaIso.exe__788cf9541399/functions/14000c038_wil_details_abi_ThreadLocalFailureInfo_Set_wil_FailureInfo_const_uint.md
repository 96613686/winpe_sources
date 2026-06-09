# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000c038`
- end: `0x14000c16e`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000c4ac`

## callees

- `0x140007394`
- `0x14000740c`
- `0x14000b3b4`
- `0x14000bdec`
- `0x14000be0c`
- `0x14000c038`
- `0x140038cd2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c0f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c0f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c0e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c0e7`

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
0x14000c038  push    rbx
0x14000c03a  push    rbp
0x14000c03b  push    rsi
0x14000c03c  push    rdi
0x14000c03d  push    r12
0x14000c03f  push    r13
0x14000c041  push    r14
0x14000c043  push    r15
0x14000c045  sub     rsp, 28h
0x14000c049  mov     [rcx+4], r8d
0x14000c04d  lea     r14, [rcx+38h]
0x14000c051  mov     eax, [rdx+8]
0x14000c054  mov     rsi, rcx
0x14000c057  mov     [rcx+8], eax
0x14000c05a  mov     r15, rdx
0x14000c05d  mov     qword ptr [rcx+10h], 0
0x14000c065  movzx   eax, word ptr [rdx+40h]
0x14000c069  mov     [rcx+18h], ax
0x14000c06d  mov     al, [rdx]
0x14000c06f  mov     [rcx+1Ah], al
0x14000c072  mov     qword ptr [rcx+20h], 0
0x14000c07a  mov     rax, [rdx+88h]
0x14000c081  mov     [rcx+28h], rax
0x14000c085  mov     rax, [rdx+90h]
0x14000c08c  mov     [rcx+30h], rax
0x14000c090  mov     qword ptr [r14], 0
0x14000c097  mov     rcx, [rdx+18h]; this
0x14000c09b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x14000c0a0  mov     rcx, [r15+38h]; this
0x14000c0a4  mov     rbp, rax
0x14000c0a7  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14000c0ac  mov     rcx, [r15+80h]; this
0x14000c0b3  add     rbp, rax
0x14000c0b6  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14000c0bb  add     rbp, rax
0x14000c0be  lea     rdi, [rsi+48h]
0x14000c0c2  cmp     qword ptr [rsi+40h], 0
0x14000c0c7  jz      short loc_14000C0CE
0x14000c0c9  cmp     [rdi], rbp
0x14000c0cc  jnb     short loc_14000C106
0x14000c0ce  mov     rdx, rbp; dwBytes
0x14000c0d1  mov     ecx, 8; dwFlags
0x14000c0d6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000c0db  mov     r14, rax
0x14000c0de  test    rax, rax
0x14000c0e1  jz      short loc_14000C102
0x14000c0e3  mov     rbx, [rsi+40h]
0x14000c0e7  call    cs:__imp_GetProcessHeap
0x14000c0ed  mov     r8, rbx; lpMem
0x14000c0f0  xor     edx, edx; dwFlags
0x14000c0f2  mov     rcx, rax; hHeap
0x14000c0f5  call    cs:__imp_HeapFree
0x14000c0fb  mov     [rsi+40h], r14
0x14000c0ff  mov     [rdi], rbp
0x14000c102  lea     r14, [rsi+38h]
0x14000c106  mov     rcx, [rsi+40h]; Destination
0x14000c10a  test    rcx, rcx
0x14000c10d  jz      short loc_14000C15D
0x14000c10f  mov     rbx, [rdi]
0x14000c112  lea     r9, [rsi+10h]
0x14000c116  mov     r8, [r15+38h]
0x14000c11a  add     rbx, rcx
0x14000c11d  mov     rdx, rbx
0x14000c120  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000c125  mov     r8, [r15+80h]
0x14000c12c  lea     r9, [rsi+20h]
0x14000c130  mov     rdx, rbx
0x14000c133  mov     rcx, rax; Destination
0x14000c136  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000c13b  mov     r8, [r15+18h]
0x14000c13f  mov     r9, r14
0x14000c142  mov     rdx, rbx
0x14000c145  mov     rcx, rax; Destination
0x14000c148  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x14000c14d  sub     rbx, rax
0x14000c150  xor     edx, edx; Val
0x14000c152  mov     r8, rbx; Size
0x14000c155  mov     rcx, rax; void *
0x14000c158  call    memset_0
0x14000c15d  add     rsp, 28h
0x14000c161  pop     r15
0x14000c163  pop     r14
0x14000c165  pop     r13
0x14000c167  pop     r12
0x14000c169  pop     rdi
0x14000c16a  pop     rsi
0x14000c16b  pop     rbp
0x14000c16c  pop     rbx
0x14000c16d  retn
```
