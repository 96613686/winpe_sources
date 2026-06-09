# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140006cd4`
- end: `0x140006e17`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140007088`

## callees

- `0x14000353c`
- `0x140004308`
- `0x140004380`
- `0x140006798`
- `0x140006b48`
- `0x140006b6c`
- `0x140006cd4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006d83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006d83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006d97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006d97`

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
0x140006cd4  push    rbx
0x140006cd6  push    rbp
0x140006cd7  push    rsi
0x140006cd8  push    rdi
0x140006cd9  push    r12
0x140006cdb  push    r13
0x140006cdd  push    r14
0x140006cdf  push    r15
0x140006ce1  sub     rsp, 28h
0x140006ce5  mov     [rcx+4], r8d
0x140006ce9  lea     r14, [rcx+38h]
0x140006ced  mov     eax, [rdx+8]
0x140006cf0  mov     rsi, rcx
0x140006cf3  mov     [rcx+8], eax
0x140006cf6  mov     r15, rdx
0x140006cf9  mov     qword ptr [rcx+10h], 0
0x140006d01  movzx   eax, word ptr [rdx+40h]
0x140006d05  mov     [rcx+18h], ax
0x140006d09  mov     al, [rdx]
0x140006d0b  mov     [rcx+1Ah], al
0x140006d0e  mov     qword ptr [rcx+20h], 0
0x140006d16  mov     rax, [rdx+88h]
0x140006d1d  mov     [rcx+28h], rax
0x140006d21  mov     rax, [rdx+90h]
0x140006d28  mov     [rcx+30h], rax
0x140006d2c  mov     qword ptr [r14], 0
0x140006d33  mov     rcx, [rdx+18h]; this
0x140006d37  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140006d3c  mov     rcx, [r15+38h]; this
0x140006d40  mov     rbp, rax
0x140006d43  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140006d48  mov     rcx, [r15+80h]; this
0x140006d4f  add     rbp, rax
0x140006d52  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140006d57  add     rbp, rax
0x140006d5a  lea     rdi, [rsi+48h]
0x140006d5e  cmp     qword ptr [rsi+40h], 0
0x140006d63  jz      short loc_140006D6A
0x140006d65  cmp     [rdi], rbp
0x140006d68  jnb     short loc_140006DAE
0x140006d6a  mov     rdx, rbp; dwBytes
0x140006d6d  mov     ecx, 8; dwFlags
0x140006d72  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006d77  mov     r14, rax
0x140006d7a  test    rax, rax
0x140006d7d  jz      short loc_140006DAA
0x140006d7f  mov     rbx, [rsi+40h]
0x140006d83  call    cs:__imp_GetProcessHeap
0x140006d8a  nop     dword ptr [rax+rax+00h]
0x140006d8f  mov     r8, rbx; lpMem
0x140006d92  xor     edx, edx; dwFlags
0x140006d94  mov     rcx, rax; hHeap
0x140006d97  call    cs:__imp_HeapFree
0x140006d9e  nop     dword ptr [rax+rax+00h]
0x140006da3  mov     [rsi+40h], r14
0x140006da7  mov     [rdi], rbp
0x140006daa  lea     r14, [rsi+38h]
0x140006dae  mov     rcx, [rsi+40h]; Destination
0x140006db2  test    rcx, rcx
0x140006db5  jz      short loc_140006E05
0x140006db7  mov     rbx, [rdi]
0x140006dba  lea     r9, [rsi+10h]
0x140006dbe  mov     r8, [r15+38h]
0x140006dc2  add     rbx, rcx
0x140006dc5  mov     rdx, rbx
0x140006dc8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006dcd  mov     r8, [r15+80h]
0x140006dd4  lea     r9, [rsi+20h]
0x140006dd8  mov     rdx, rbx
0x140006ddb  mov     rcx, rax; Destination
0x140006dde  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006de3  mov     r8, [r15+18h]
0x140006de7  mov     r9, r14
0x140006dea  mov     rdx, rbx
0x140006ded  mov     rcx, rax; Destination
0x140006df0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x140006df5  sub     rbx, rax
0x140006df8  xor     edx, edx; Val
0x140006dfa  mov     r8, rbx; Size
0x140006dfd  mov     rcx, rax; void *
0x140006e00  call    memset_0
0x140006e05  add     rsp, 28h
0x140006e09  pop     r15
0x140006e0b  pop     r14
0x140006e0d  pop     r13
0x140006e0f  pop     r12
0x140006e11  pop     rdi
0x140006e12  pop     rsi
0x140006e13  pop     rbp
0x140006e14  pop     rbx
0x140006e15  retn
```
