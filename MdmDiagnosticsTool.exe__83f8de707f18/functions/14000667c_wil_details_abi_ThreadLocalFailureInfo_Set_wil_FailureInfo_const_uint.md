# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000667c`
- end: `0x1400067bf`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140006a30`

## callees

- `0x140002cd8`
- `0x140002d58`
- `0x140005bb8`
- `0x140006558`
- `0x14000657c`
- `0x14000667c`
- `0x140009cc6`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000673f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000673f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000672b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000672b`

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
0x14000667c  push    rbx
0x14000667e  push    rbp
0x14000667f  push    rsi
0x140006680  push    rdi
0x140006681  push    r12
0x140006683  push    r13
0x140006685  push    r14
0x140006687  push    r15
0x140006689  sub     rsp, 28h
0x14000668d  mov     [rcx+4], r8d
0x140006691  lea     r14, [rcx+38h]
0x140006695  mov     eax, [rdx+8]
0x140006698  mov     rsi, rcx
0x14000669b  mov     [rcx+8], eax
0x14000669e  mov     r15, rdx
0x1400066a1  mov     qword ptr [rcx+10h], 0
0x1400066a9  movzx   eax, word ptr [rdx+40h]
0x1400066ad  mov     [rcx+18h], ax
0x1400066b1  mov     al, [rdx]
0x1400066b3  mov     [rcx+1Ah], al
0x1400066b6  mov     qword ptr [rcx+20h], 0
0x1400066be  mov     rax, [rdx+88h]
0x1400066c5  mov     [rcx+28h], rax
0x1400066c9  mov     rax, [rdx+90h]
0x1400066d0  mov     [rcx+30h], rax
0x1400066d4  mov     qword ptr [r14], 0
0x1400066db  mov     rcx, [rdx+18h]; this
0x1400066df  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1400066e4  mov     rcx, [r15+38h]; this
0x1400066e8  mov     rbp, rax
0x1400066eb  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400066f0  mov     rcx, [r15+80h]; this
0x1400066f7  add     rbp, rax
0x1400066fa  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400066ff  add     rbp, rax
0x140006702  lea     rdi, [rsi+48h]
0x140006706  cmp     qword ptr [rsi+40h], 0
0x14000670b  jz      short loc_140006712
0x14000670d  cmp     [rdi], rbp
0x140006710  jnb     short loc_140006756
0x140006712  mov     rdx, rbp; dwBytes
0x140006715  mov     ecx, 8; dwFlags
0x14000671a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000671f  mov     r14, rax
0x140006722  test    rax, rax
0x140006725  jz      short loc_140006752
0x140006727  mov     rbx, [rsi+40h]
0x14000672b  call    cs:__imp_GetProcessHeap
0x140006732  nop     dword ptr [rax+rax+00h]
0x140006737  mov     r8, rbx; lpMem
0x14000673a  xor     edx, edx; dwFlags
0x14000673c  mov     rcx, rax; hHeap
0x14000673f  call    cs:__imp_HeapFree
0x140006746  nop     dword ptr [rax+rax+00h]
0x14000674b  mov     [rsi+40h], r14
0x14000674f  mov     [rdi], rbp
0x140006752  lea     r14, [rsi+38h]
0x140006756  mov     rcx, [rsi+40h]; Destination
0x14000675a  test    rcx, rcx
0x14000675d  jz      short loc_1400067AD
0x14000675f  mov     rbx, [rdi]
0x140006762  lea     r9, [rsi+10h]
0x140006766  mov     r8, [r15+38h]
0x14000676a  add     rbx, rcx
0x14000676d  mov     rdx, rbx
0x140006770  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006775  mov     r8, [r15+80h]
0x14000677c  lea     r9, [rsi+20h]
0x140006780  mov     rdx, rbx
0x140006783  mov     rcx, rax; Destination
0x140006786  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000678b  mov     r8, [r15+18h]
0x14000678f  mov     r9, r14
0x140006792  mov     rdx, rbx
0x140006795  mov     rcx, rax; Destination
0x140006798  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x14000679d  sub     rbx, rax
0x1400067a0  xor     edx, edx; Val
0x1400067a2  mov     r8, rbx; Size
0x1400067a5  mov     rcx, rax; void *
0x1400067a8  call    memset_0
0x1400067ad  add     rsp, 28h
0x1400067b1  pop     r15
0x1400067b3  pop     r14
0x1400067b5  pop     r13
0x1400067b7  pop     r12
0x1400067b9  pop     rdi
0x1400067ba  pop     rsi
0x1400067bb  pop     rbp
0x1400067bc  pop     rbx
0x1400067bd  retn
```
