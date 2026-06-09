# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000577c`
- end: `0x1400058b2`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140005b14`

## callees

- `0x140002d98`
- `0x140003a04`
- `0x140003a7c`
- `0x1400054b0`
- `0x140005628`
- `0x140005648`
- `0x14000577c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000582b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000582b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005839`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005839`

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
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const wchar_t *)a2);
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
    v18 = (void *)wil::details::WriteResultString<wchar_t const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x14000577c  push    rbx
0x14000577e  push    rbp
0x14000577f  push    rsi
0x140005780  push    rdi
0x140005781  push    r12
0x140005783  push    r13
0x140005785  push    r14
0x140005787  push    r15
0x140005789  sub     rsp, 28h
0x14000578d  mov     [rcx+4], r8d
0x140005791  lea     r14, [rcx+38h]
0x140005795  mov     eax, [rdx+8]
0x140005798  mov     rsi, rcx
0x14000579b  mov     [rcx+8], eax
0x14000579e  mov     r15, rdx
0x1400057a1  mov     qword ptr [rcx+10h], 0
0x1400057a9  movzx   eax, word ptr [rdx+40h]
0x1400057ad  mov     [rcx+18h], ax
0x1400057b1  mov     al, [rdx]
0x1400057b3  mov     [rcx+1Ah], al
0x1400057b6  mov     qword ptr [rcx+20h], 0
0x1400057be  mov     rax, [rdx+88h]
0x1400057c5  mov     [rcx+28h], rax
0x1400057c9  mov     rax, [rdx+90h]
0x1400057d0  mov     [rcx+30h], rax
0x1400057d4  mov     qword ptr [r14], 0
0x1400057db  mov     rcx, [rdx+18h]; this
0x1400057df  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x1400057e4  mov     rcx, [r15+38h]; this
0x1400057e8  mov     rbp, rax
0x1400057eb  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400057f0  mov     rcx, [r15+80h]; this
0x1400057f7  add     rbp, rax
0x1400057fa  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400057ff  add     rbp, rax
0x140005802  lea     rdi, [rsi+48h]
0x140005806  cmp     qword ptr [rsi+40h], 0
0x14000580b  jz      short loc_140005812
0x14000580d  cmp     [rdi], rbp
0x140005810  jnb     short loc_14000584A
0x140005812  mov     rdx, rbp; dwBytes
0x140005815  mov     ecx, 8; dwFlags
0x14000581a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000581f  mov     r14, rax
0x140005822  test    rax, rax
0x140005825  jz      short loc_140005846
0x140005827  mov     rbx, [rsi+40h]
0x14000582b  call    cs:__imp_GetProcessHeap
0x140005831  mov     r8, rbx; lpMem
0x140005834  xor     edx, edx; dwFlags
0x140005836  mov     rcx, rax; hHeap
0x140005839  call    cs:__imp_HeapFree
0x14000583f  mov     [rsi+40h], r14
0x140005843  mov     [rdi], rbp
0x140005846  lea     r14, [rsi+38h]
0x14000584a  mov     rcx, [rsi+40h]; Destination
0x14000584e  test    rcx, rcx
0x140005851  jz      short loc_1400058A1
0x140005853  mov     rbx, [rdi]
0x140005856  lea     r9, [rsi+10h]
0x14000585a  mov     r8, [r15+38h]
0x14000585e  add     rbx, rcx
0x140005861  mov     rdx, rbx
0x140005864  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140005869  mov     r8, [r15+80h]
0x140005870  lea     r9, [rsi+20h]
0x140005874  mov     rdx, rbx
0x140005877  mov     rcx, rax; Destination
0x14000587a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000587f  mov     r8, [r15+18h]
0x140005883  mov     r9, r14
0x140005886  mov     rdx, rbx
0x140005889  mov     rcx, rax; Destination
0x14000588c  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x140005891  sub     rbx, rax
0x140005894  xor     edx, edx; Val
0x140005896  mov     r8, rbx; Size
0x140005899  mov     rcx, rax; void *
0x14000589c  call    memset_0
0x1400058a1  add     rsp, 28h
0x1400058a5  pop     r15
0x1400058a7  pop     r14
0x1400058a9  pop     r13
0x1400058ab  pop     r12
0x1400058ad  pop     rdi
0x1400058ae  pop     rsi
0x1400058af  pop     rbp
0x1400058b0  pop     rbx
0x1400058b1  retn
```
