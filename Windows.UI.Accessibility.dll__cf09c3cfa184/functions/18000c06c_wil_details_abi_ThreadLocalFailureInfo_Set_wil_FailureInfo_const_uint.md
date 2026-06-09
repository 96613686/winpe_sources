# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000c06c`
- end: `0x18000c1a2`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c2a0`

## callees

- `0x180004344`
- `0x180005970`
- `0x1800059e8`
- `0x1800068ec`
- `0x18000690c`
- `0x18000af64`
- `0x18000c06c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c11b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c11b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c129`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c129`

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
0x18000c06c  push    rbx
0x18000c06e  push    rbp
0x18000c06f  push    rsi
0x18000c070  push    rdi
0x18000c071  push    r12
0x18000c073  push    r13
0x18000c075  push    r14
0x18000c077  push    r15
0x18000c079  sub     rsp, 28h
0x18000c07d  mov     [rcx+4], r8d
0x18000c081  lea     r14, [rcx+38h]
0x18000c085  mov     eax, [rdx+8]
0x18000c088  mov     rsi, rcx
0x18000c08b  mov     [rcx+8], eax
0x18000c08e  mov     r15, rdx
0x18000c091  mov     qword ptr [rcx+10h], 0
0x18000c099  movzx   eax, word ptr [rdx+40h]
0x18000c09d  mov     [rcx+18h], ax
0x18000c0a1  mov     al, [rdx]
0x18000c0a3  mov     [rcx+1Ah], al
0x18000c0a6  mov     qword ptr [rcx+20h], 0
0x18000c0ae  mov     rax, [rdx+88h]
0x18000c0b5  mov     [rcx+28h], rax
0x18000c0b9  mov     rax, [rdx+90h]
0x18000c0c0  mov     [rcx+30h], rax
0x18000c0c4  mov     qword ptr [r14], 0
0x18000c0cb  mov     rcx, [rdx+18h]; this
0x18000c0cf  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000c0d4  mov     rcx, [r15+38h]; this
0x18000c0d8  mov     rbp, rax
0x18000c0db  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000c0e0  mov     rcx, [r15+80h]; this
0x18000c0e7  add     rbp, rax
0x18000c0ea  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000c0ef  add     rbp, rax
0x18000c0f2  lea     rdi, [rsi+48h]
0x18000c0f6  cmp     qword ptr [rsi+40h], 0
0x18000c0fb  jz      short loc_18000C102
0x18000c0fd  cmp     [rdi], rbp
0x18000c100  jnb     short loc_18000C13A
0x18000c102  mov     rdx, rbp; dwBytes
0x18000c105  mov     ecx, 8; dwFlags
0x18000c10a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c10f  mov     r14, rax
0x18000c112  test    rax, rax
0x18000c115  jz      short loc_18000C136
0x18000c117  mov     rbx, [rsi+40h]
0x18000c11b  call    cs:__imp_GetProcessHeap
0x18000c121  mov     r8, rbx; lpMem
0x18000c124  xor     edx, edx; dwFlags
0x18000c126  mov     rcx, rax; hHeap
0x18000c129  call    cs:__imp_HeapFree
0x18000c12f  mov     [rsi+40h], r14
0x18000c133  mov     [rdi], rbp
0x18000c136  lea     r14, [rsi+38h]
0x18000c13a  mov     rcx, [rsi+40h]; Destination
0x18000c13e  test    rcx, rcx
0x18000c141  jz      short loc_18000C191
0x18000c143  mov     rbx, [rdi]
0x18000c146  lea     r9, [rsi+10h]
0x18000c14a  mov     r8, [r15+38h]
0x18000c14e  add     rbx, rcx
0x18000c151  mov     rdx, rbx
0x18000c154  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000c159  mov     r8, [r15+80h]
0x18000c160  lea     r9, [rsi+20h]
0x18000c164  mov     rdx, rbx
0x18000c167  mov     rcx, rax; Destination
0x18000c16a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000c16f  mov     r8, [r15+18h]
0x18000c173  mov     r9, r14
0x18000c176  mov     rdx, rbx
0x18000c179  mov     rcx, rax; Destination
0x18000c17c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000c181  sub     rbx, rax
0x18000c184  xor     edx, edx; Val
0x18000c186  mov     r8, rbx; Size
0x18000c189  mov     rcx, rax; void *
0x18000c18c  call    memset_0
0x18000c191  add     rsp, 28h
0x18000c195  pop     r15
0x18000c197  pop     r14
0x18000c199  pop     r13
0x18000c19b  pop     r12
0x18000c19d  pop     rdi
0x18000c19e  pop     rsi
0x18000c19f  pop     rbp
0x18000c1a0  pop     rbx
0x18000c1a1  retn
```
