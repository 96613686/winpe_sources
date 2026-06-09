# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800097d0`
- end: `0x180009906`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180009c60`

## callees

- `0x180002c18`
- `0x180003e2c`
- `0x180003ea4`
- `0x180007e0c`
- `0x180009648`
- `0x180009668`
- `0x1800097d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000988d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000988d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000987f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000987f`

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
0x1800097d0  push    rbx
0x1800097d2  push    rbp
0x1800097d3  push    rsi
0x1800097d4  push    rdi
0x1800097d5  push    r12
0x1800097d7  push    r13
0x1800097d9  push    r14
0x1800097db  push    r15
0x1800097dd  sub     rsp, 28h
0x1800097e1  mov     [rcx+4], r8d
0x1800097e5  lea     r14, [rcx+38h]
0x1800097e9  mov     eax, [rdx+8]
0x1800097ec  mov     rsi, rcx
0x1800097ef  mov     [rcx+8], eax
0x1800097f2  mov     r15, rdx
0x1800097f5  mov     qword ptr [rcx+10h], 0
0x1800097fd  movzx   eax, word ptr [rdx+40h]
0x180009801  mov     [rcx+18h], ax
0x180009805  mov     al, [rdx]
0x180009807  mov     [rcx+1Ah], al
0x18000980a  mov     qword ptr [rcx+20h], 0
0x180009812  mov     rax, [rdx+88h]
0x180009819  mov     [rcx+28h], rax
0x18000981d  mov     rax, [rdx+90h]
0x180009824  mov     [rcx+30h], rax
0x180009828  mov     qword ptr [r14], 0
0x18000982f  mov     rcx, [rdx+18h]; this
0x180009833  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180009838  mov     rcx, [r15+38h]; this
0x18000983c  mov     rbp, rax
0x18000983f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180009844  mov     rcx, [r15+80h]; this
0x18000984b  add     rbp, rax
0x18000984e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180009853  add     rbp, rax
0x180009856  lea     rdi, [rsi+48h]
0x18000985a  cmp     qword ptr [rsi+40h], 0
0x18000985f  jz      short loc_180009866
0x180009861  cmp     [rdi], rbp
0x180009864  jnb     short loc_18000989E
0x180009866  mov     rdx, rbp; dwBytes
0x180009869  mov     ecx, 8; dwFlags
0x18000986e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009873  mov     r14, rax
0x180009876  test    rax, rax
0x180009879  jz      short loc_18000989A
0x18000987b  mov     rbx, [rsi+40h]
0x18000987f  call    cs:__imp_GetProcessHeap
0x180009885  mov     r8, rbx; lpMem
0x180009888  xor     edx, edx; dwFlags
0x18000988a  mov     rcx, rax; hHeap
0x18000988d  call    cs:__imp_HeapFree
0x180009893  mov     [rsi+40h], r14
0x180009897  mov     [rdi], rbp
0x18000989a  lea     r14, [rsi+38h]
0x18000989e  mov     rcx, [rsi+40h]; Destination
0x1800098a2  test    rcx, rcx
0x1800098a5  jz      short loc_1800098F5
0x1800098a7  mov     rbx, [rdi]
0x1800098aa  lea     r9, [rsi+10h]
0x1800098ae  mov     r8, [r15+38h]
0x1800098b2  add     rbx, rcx
0x1800098b5  mov     rdx, rbx
0x1800098b8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800098bd  mov     r8, [r15+80h]
0x1800098c4  lea     r9, [rsi+20h]
0x1800098c8  mov     rdx, rbx
0x1800098cb  mov     rcx, rax; Destination
0x1800098ce  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800098d3  mov     r8, [r15+18h]
0x1800098d7  mov     r9, r14
0x1800098da  mov     rdx, rbx
0x1800098dd  mov     rcx, rax; Destination
0x1800098e0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800098e5  sub     rbx, rax
0x1800098e8  xor     edx, edx; Val
0x1800098ea  mov     r8, rbx; Size
0x1800098ed  mov     rcx, rax; void *
0x1800098f0  call    memset_0
0x1800098f5  add     rsp, 28h
0x1800098f9  pop     r15
0x1800098fb  pop     r14
0x1800098fd  pop     r13
0x1800098ff  pop     r12
0x180009901  pop     rdi
0x180009902  pop     rsi
0x180009903  pop     rbp
0x180009904  pop     rbx
0x180009905  retn
```
