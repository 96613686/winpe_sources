# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800279a0`
- end: `0x180027ad6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180027adc`

## callees

- `0x18000e6f0`
- `0x18000f3f0`
- `0x180014390`
- `0x1800155a4`
- `0x180017b1c`
- `0x180026cd0`
- `0x1800279a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027a5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027a5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027a4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027a4f`

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
  char *v16; // rbx
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
    v17 = wil::details::WriteResultString<char const *>(v15, v16, *((_BYTE **)a2 + 7), (_QWORD *)this + 2);
    v18 = (unsigned __int16 *)wil::details::WriteResultString<char const *>(
                                v17,
                                v16,
                                *((_BYTE **)a2 + 16),
                                (_QWORD *)this + 4);
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
0x1800279a0  push    rbx
0x1800279a2  push    rbp
0x1800279a3  push    rsi
0x1800279a4  push    rdi
0x1800279a5  push    r12
0x1800279a7  push    r13
0x1800279a9  push    r14
0x1800279ab  push    r15
0x1800279ad  sub     rsp, 28h
0x1800279b1  mov     [rcx+4], r8d
0x1800279b5  lea     r14, [rcx+38h]
0x1800279b9  mov     eax, [rdx+8]
0x1800279bc  mov     rsi, rcx
0x1800279bf  mov     [rcx+8], eax
0x1800279c2  mov     r15, rdx
0x1800279c5  mov     qword ptr [rcx+10h], 0
0x1800279cd  movzx   eax, word ptr [rdx+40h]
0x1800279d1  mov     [rcx+18h], ax
0x1800279d5  mov     al, [rdx]
0x1800279d7  mov     [rcx+1Ah], al
0x1800279da  mov     qword ptr [rcx+20h], 0
0x1800279e2  mov     rax, [rdx+88h]
0x1800279e9  mov     [rcx+28h], rax
0x1800279ed  mov     rax, [rdx+90h]
0x1800279f4  mov     [rcx+30h], rax
0x1800279f8  mov     qword ptr [r14], 0
0x1800279ff  mov     rcx, [rdx+18h]; this
0x180027a03  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180027a08  mov     rcx, [r15+38h]; this
0x180027a0c  mov     rbp, rax
0x180027a0f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180027a14  mov     rcx, [r15+80h]; this
0x180027a1b  add     rbp, rax
0x180027a1e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180027a23  add     rbp, rax
0x180027a26  lea     rdi, [rsi+48h]
0x180027a2a  cmp     qword ptr [rsi+40h], 0
0x180027a2f  jz      short loc_180027A36
0x180027a31  cmp     [rdi], rbp
0x180027a34  jnb     short loc_180027A6E
0x180027a36  mov     rdx, rbp; dwBytes
0x180027a39  mov     ecx, 8; dwFlags
0x180027a3e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180027a43  mov     r14, rax
0x180027a46  test    rax, rax
0x180027a49  jz      short loc_180027A6A
0x180027a4b  mov     rbx, [rsi+40h]
0x180027a4f  call    cs:__imp_GetProcessHeap
0x180027a55  mov     r8, rbx; lpMem
0x180027a58  xor     edx, edx; dwFlags
0x180027a5a  mov     rcx, rax; hHeap
0x180027a5d  call    cs:__imp_HeapFree
0x180027a63  mov     [rsi+40h], r14
0x180027a67  mov     [rdi], rbp
0x180027a6a  lea     r14, [rsi+38h]
0x180027a6e  mov     rcx, [rsi+40h]
0x180027a72  test    rcx, rcx
0x180027a75  jz      short loc_180027AC5
0x180027a77  mov     rbx, [rdi]
0x180027a7a  lea     r9, [rsi+10h]
0x180027a7e  mov     r8, [r15+38h]
0x180027a82  add     rbx, rcx
0x180027a85  mov     rdx, rbx
0x180027a88  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180027a8d  mov     r8, [r15+80h]
0x180027a94  lea     r9, [rsi+20h]
0x180027a98  mov     rdx, rbx
0x180027a9b  mov     rcx, rax
0x180027a9e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180027aa3  mov     r8, [r15+18h]
0x180027aa7  mov     r9, r14
0x180027aaa  mov     rdx, rbx
0x180027aad  mov     rcx, rax; Destination
0x180027ab0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180027ab5  sub     rbx, rax
0x180027ab8  xor     edx, edx; Val
0x180027aba  mov     r8, rbx; Size
0x180027abd  mov     rcx, rax; void *
0x180027ac0  call    memset_0
0x180027ac5  add     rsp, 28h
0x180027ac9  pop     r15
0x180027acb  pop     r14
0x180027acd  pop     r13
0x180027acf  pop     r12
0x180027ad1  pop     rdi
0x180027ad2  pop     rsi
0x180027ad3  pop     rbp
0x180027ad4  pop     rbx
0x180027ad5  retn
```
