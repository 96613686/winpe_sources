# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180026648`
- end: `0x18002677e`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180026ad8`

## callees

- `0x18001c684`
- `0x18001ddbc`
- `0x18001de34`
- `0x180024860`
- `0x1800259b8`
- `0x1800259d8`
- `0x180026648`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800266f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800266f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026705`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026705`

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
0x180026648  push    rbx
0x18002664a  push    rbp
0x18002664b  push    rsi
0x18002664c  push    rdi
0x18002664d  push    r12
0x18002664f  push    r13
0x180026651  push    r14
0x180026653  push    r15
0x180026655  sub     rsp, 28h
0x180026659  mov     [rcx+4], r8d
0x18002665d  lea     r14, [rcx+38h]
0x180026661  mov     eax, [rdx+8]
0x180026664  mov     rsi, rcx
0x180026667  mov     [rcx+8], eax
0x18002666a  mov     r15, rdx
0x18002666d  mov     qword ptr [rcx+10h], 0
0x180026675  movzx   eax, word ptr [rdx+40h]
0x180026679  mov     [rcx+18h], ax
0x18002667d  mov     al, [rdx]
0x18002667f  mov     [rcx+1Ah], al
0x180026682  mov     qword ptr [rcx+20h], 0
0x18002668a  mov     rax, [rdx+88h]
0x180026691  mov     [rcx+28h], rax
0x180026695  mov     rax, [rdx+90h]
0x18002669c  mov     [rcx+30h], rax
0x1800266a0  mov     qword ptr [r14], 0
0x1800266a7  mov     rcx, [rdx+18h]; this
0x1800266ab  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800266b0  mov     rcx, [r15+38h]; this
0x1800266b4  mov     rbp, rax
0x1800266b7  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800266bc  mov     rcx, [r15+80h]; this
0x1800266c3  add     rbp, rax
0x1800266c6  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800266cb  add     rbp, rax
0x1800266ce  lea     rdi, [rsi+48h]
0x1800266d2  cmp     qword ptr [rsi+40h], 0
0x1800266d7  jz      short loc_1800266DE
0x1800266d9  cmp     [rdi], rbp
0x1800266dc  jnb     short loc_180026716
0x1800266de  mov     rdx, rbp; dwBytes
0x1800266e1  mov     ecx, 8; dwFlags
0x1800266e6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800266eb  mov     r14, rax
0x1800266ee  test    rax, rax
0x1800266f1  jz      short loc_180026712
0x1800266f3  mov     rbx, [rsi+40h]
0x1800266f7  call    cs:__imp_GetProcessHeap
0x1800266fd  mov     r8, rbx; lpMem
0x180026700  xor     edx, edx; dwFlags
0x180026702  mov     rcx, rax; hHeap
0x180026705  call    cs:__imp_HeapFree
0x18002670b  mov     [rsi+40h], r14
0x18002670f  mov     [rdi], rbp
0x180026712  lea     r14, [rsi+38h]
0x180026716  mov     rcx, [rsi+40h]; Destination
0x18002671a  test    rcx, rcx
0x18002671d  jz      short loc_18002676D
0x18002671f  mov     rbx, [rdi]
0x180026722  lea     r9, [rsi+10h]
0x180026726  mov     r8, [r15+38h]
0x18002672a  add     rbx, rcx
0x18002672d  mov     rdx, rbx
0x180026730  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180026735  mov     r8, [r15+80h]
0x18002673c  lea     r9, [rsi+20h]
0x180026740  mov     rdx, rbx
0x180026743  mov     rcx, rax; Destination
0x180026746  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002674b  mov     r8, [r15+18h]
0x18002674f  mov     r9, r14
0x180026752  mov     rdx, rbx
0x180026755  mov     rcx, rax; Destination
0x180026758  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18002675d  sub     rbx, rax
0x180026760  xor     edx, edx; Val
0x180026762  mov     r8, rbx; Size
0x180026765  mov     rcx, rax; void *
0x180026768  call    memset_0
0x18002676d  add     rsp, 28h
0x180026771  pop     r15
0x180026773  pop     r14
0x180026775  pop     r13
0x180026777  pop     r12
0x180026779  pop     rdi
0x18002677a  pop     rsi
0x18002677b  pop     rbp
0x18002677c  pop     rbx
0x18002677d  retn
```
