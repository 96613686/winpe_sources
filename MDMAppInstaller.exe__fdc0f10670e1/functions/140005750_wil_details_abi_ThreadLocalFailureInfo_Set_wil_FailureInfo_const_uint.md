# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140005750`
- end: `0x140005886`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140005ae8`

## callees

- `0x14000346c`
- `0x1400034e4`
- `0x140005488`
- `0x14000561c`
- `0x14000563c`
- `0x140005750`
- `0x14001a8aa`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000580d`
- `KERNEL32!HeapFree` at `0x14000580d`
- `KERNEL32!GetProcessHeap` at `0x1400057ff`
- `KERNEL32!GetProcessHeap` at `0x1400057ff`

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
0x140005750  push    rbx
0x140005752  push    rbp
0x140005753  push    rsi
0x140005754  push    rdi
0x140005755  push    r12
0x140005757  push    r13
0x140005759  push    r14
0x14000575b  push    r15
0x14000575d  sub     rsp, 28h
0x140005761  mov     [rcx+4], r8d
0x140005765  lea     r14, [rcx+38h]
0x140005769  mov     eax, [rdx+8]
0x14000576c  mov     rsi, rcx
0x14000576f  mov     [rcx+8], eax
0x140005772  mov     r15, rdx
0x140005775  mov     qword ptr [rcx+10h], 0
0x14000577d  movzx   eax, word ptr [rdx+40h]
0x140005781  mov     [rcx+18h], ax
0x140005785  mov     al, [rdx]
0x140005787  mov     [rcx+1Ah], al
0x14000578a  mov     qword ptr [rcx+20h], 0
0x140005792  mov     rax, [rdx+88h]
0x140005799  mov     [rcx+28h], rax
0x14000579d  mov     rax, [rdx+90h]
0x1400057a4  mov     [rcx+30h], rax
0x1400057a8  mov     qword ptr [r14], 0
0x1400057af  mov     rcx, [rdx+18h]; this
0x1400057b3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1400057b8  mov     rcx, [r15+38h]; this
0x1400057bc  mov     rbp, rax
0x1400057bf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400057c4  mov     rcx, [r15+80h]; this
0x1400057cb  add     rbp, rax
0x1400057ce  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400057d3  add     rbp, rax
0x1400057d6  lea     rdi, [rsi+48h]
0x1400057da  cmp     qword ptr [rsi+40h], 0
0x1400057df  jz      short loc_1400057E6
0x1400057e1  cmp     [rdi], rbp
0x1400057e4  jnb     short loc_14000581E
0x1400057e6  mov     rdx, rbp; dwBytes
0x1400057e9  mov     ecx, 8; dwFlags
0x1400057ee  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400057f3  mov     r14, rax
0x1400057f6  test    rax, rax
0x1400057f9  jz      short loc_14000581A
0x1400057fb  mov     rbx, [rsi+40h]
0x1400057ff  call    cs:__imp_GetProcessHeap
0x140005805  mov     r8, rbx; lpMem
0x140005808  xor     edx, edx; dwFlags
0x14000580a  mov     rcx, rax; hHeap
0x14000580d  call    cs:__imp_HeapFree
0x140005813  mov     [rsi+40h], r14
0x140005817  mov     [rdi], rbp
0x14000581a  lea     r14, [rsi+38h]
0x14000581e  mov     rcx, [rsi+40h]; Destination
0x140005822  test    rcx, rcx
0x140005825  jz      short loc_140005875
0x140005827  mov     rbx, [rdi]
0x14000582a  lea     r9, [rsi+10h]
0x14000582e  mov     r8, [r15+38h]
0x140005832  add     rbx, rcx
0x140005835  mov     rdx, rbx
0x140005838  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000583d  mov     r8, [r15+80h]
0x140005844  lea     r9, [rsi+20h]
0x140005848  mov     rdx, rbx
0x14000584b  mov     rcx, rax; Destination
0x14000584e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140005853  mov     r8, [r15+18h]
0x140005857  mov     r9, r14
0x14000585a  mov     rdx, rbx
0x14000585d  mov     rcx, rax; Destination
0x140005860  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x140005865  sub     rbx, rax
0x140005868  xor     edx, edx; Val
0x14000586a  mov     r8, rbx; Size
0x14000586d  mov     rcx, rax; void *
0x140005870  call    memset_0
0x140005875  add     rsp, 28h
0x140005879  pop     r15
0x14000587b  pop     r14
0x14000587d  pop     r13
0x14000587f  pop     r12
0x140005881  pop     rdi
0x140005882  pop     rsi
0x140005883  pop     rbp
0x140005884  pop     rbx
0x140005885  retn
```
