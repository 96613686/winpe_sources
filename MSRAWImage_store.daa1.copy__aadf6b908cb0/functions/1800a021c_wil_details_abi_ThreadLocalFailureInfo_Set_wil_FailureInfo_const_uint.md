# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800a021c`
- end: `0x1800a0372`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `342`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800a05fc`

## callees

- `0x18009eb7c`
- `0x18009ebf4`
- `0x18009fde0`
- `0x1800a0108`
- `0x1800a012c`
- `0x1800a021c`
- `0x1800b0b00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a02e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a02e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a02cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a02cf`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int64 v5; // rsi
  const char *v6; // rdx
  unsigned __int64 v7; // rsi
  const char *v8; // rdx
  SIZE_T v9; // rsi
  SIZE_T *v10; // rbx
  LPVOID v11; // rbp
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
      v10 = (SIZE_T *)((char *)this + 72);
      *((_QWORD *)this + 9) = v9;
    }
  }
  v14 = (char *)*((_QWORD *)this + 8);
  if ( v14 )
  {
    v15 = &v14[*v10];
    v16 = (void *)wil::details::WriteResultString<char const *>(v14);
    v17 = (void *)wil::details::WriteResultString<char const *>(v16);
    v18 = (void *)wil::details::WriteResultString<unsigned short const *>(v17);
    memset(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x1800a021c  mov     [rsp+arg_0], rbx
0x1800a0221  mov     [rsp+arg_8], rbp
0x1800a0226  mov     [rsp+arg_10], rsi
0x1800a022b  push    rdi
0x1800a022c  push    r12
0x1800a022e  push    r13
0x1800a0230  push    r14
0x1800a0232  push    r15
0x1800a0234  sub     rsp, 20h
0x1800a0238  mov     rdi, rcx
0x1800a023b  mov     [rcx+4], r8d
0x1800a023f  mov     eax, [rdx+8]
0x1800a0242  mov     r15, rdx
0x1800a0245  mov     [rcx+8], eax
0x1800a0248  xor     ecx, ecx
0x1800a024a  mov     [rdi+10h], rcx
0x1800a024e  lea     r14, [rdi+38h]
0x1800a0252  movzx   eax, word ptr [rdx+40h]
0x1800a0256  mov     [rdi+18h], ax
0x1800a025a  mov     al, [rdx]
0x1800a025c  mov     [rdi+1Ah], al
0x1800a025f  mov     [rdi+20h], rcx
0x1800a0263  mov     rax, [rdx+88h]
0x1800a026a  mov     [rdi+28h], rax
0x1800a026e  mov     rax, [rdx+90h]
0x1800a0275  mov     [rdi+30h], rax
0x1800a0279  mov     [r14], rcx
0x1800a027c  mov     rcx, [rdx+18h]; this
0x1800a0280  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800a0285  mov     rcx, [r15+38h]; this
0x1800a0289  mov     rsi, rax
0x1800a028c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800a0291  mov     rcx, [r15+80h]; this
0x1800a0298  add     rsi, rax
0x1800a029b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800a02a0  add     rsi, rax
0x1800a02a3  lea     rbx, [rdi+48h]
0x1800a02a7  cmp     qword ptr [rdi+40h], 0
0x1800a02ac  jz      short loc_1800A02B3
0x1800a02ae  cmp     [rbx], rsi
0x1800a02b1  jnb     short loc_1800A02FD
0x1800a02b3  mov     rdx, rsi; dwBytes
0x1800a02b6  mov     ecx, 8; dwFlags
0x1800a02bb  mov     r14, rbx
0x1800a02be  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800a02c3  mov     rbp, rax
0x1800a02c6  test    rax, rax
0x1800a02c9  jz      short loc_1800A02F9
0x1800a02cb  mov     rbx, [rdi+40h]
0x1800a02cf  call    cs:__imp_GetProcessHeap
0x1800a02d6  nop     dword ptr [rax+rax+00h]
0x1800a02db  mov     r8, rbx; lpMem
0x1800a02de  xor     edx, edx; dwFlags
0x1800a02e0  mov     rcx, rax; hHeap
0x1800a02e3  call    cs:__imp_HeapFree
0x1800a02ea  nop     dword ptr [rax+rax+00h]
0x1800a02ef  mov     [rdi+40h], rbp
0x1800a02f3  mov     rbx, r14
0x1800a02f6  mov     [r14], rsi
0x1800a02f9  lea     r14, [rdi+38h]
0x1800a02fd  mov     rcx, [rdi+40h]; Destination
0x1800a0301  test    rcx, rcx
0x1800a0304  jz      short loc_1800A0354
0x1800a0306  mov     rbx, [rbx]
0x1800a0309  lea     r9, [rdi+10h]
0x1800a030d  mov     r8, [r15+38h]
0x1800a0311  add     rbx, rcx
0x1800a0314  mov     rdx, rbx
0x1800a0317  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800a031c  mov     r8, [r15+80h]
0x1800a0323  lea     r9, [rdi+20h]
0x1800a0327  mov     rdx, rbx
0x1800a032a  mov     rcx, rax; Destination
0x1800a032d  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800a0332  mov     r8, [r15+18h]
0x1800a0336  mov     r9, r14
0x1800a0339  mov     rdx, rbx
0x1800a033c  mov     rcx, rax; Destination
0x1800a033f  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800a0344  sub     rbx, rax
0x1800a0347  xor     edx, edx; Val
0x1800a0349  mov     r8, rbx; Size
0x1800a034c  mov     rcx, rax; void *
0x1800a034f  call    memset
0x1800a0354  mov     rbx, [rsp+48h+arg_0]
0x1800a0359  mov     rbp, [rsp+48h+arg_8]
0x1800a035e  mov     rsi, [rsp+48h+arg_10]
0x1800a0363  add     rsp, 20h
0x1800a0367  pop     r15
0x1800a0369  pop     r14
0x1800a036b  pop     r13
0x1800a036d  pop     r12
0x1800a036f  pop     rdi
0x1800a0370  retn
```
