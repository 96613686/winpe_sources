# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140006c8c`
- end: `0x140006dc2`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140007024`

## callees

- `0x140003f8c`
- `0x140004fb8`
- `0x140005030`
- `0x1400069b8`
- `0x140006ba4`
- `0x140006bc4`
- `0x140006c8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006d49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006d49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006d3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006d3b`

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
0x140006c8c  push    rbx
0x140006c8e  push    rbp
0x140006c8f  push    rsi
0x140006c90  push    rdi
0x140006c91  push    r12
0x140006c93  push    r13
0x140006c95  push    r14
0x140006c97  push    r15
0x140006c99  sub     rsp, 28h
0x140006c9d  mov     [rcx+4], r8d
0x140006ca1  lea     r14, [rcx+38h]
0x140006ca5  mov     eax, [rdx+8]
0x140006ca8  mov     rsi, rcx
0x140006cab  mov     [rcx+8], eax
0x140006cae  mov     r15, rdx
0x140006cb1  mov     qword ptr [rcx+10h], 0
0x140006cb9  movzx   eax, word ptr [rdx+40h]
0x140006cbd  mov     [rcx+18h], ax
0x140006cc1  mov     al, [rdx]
0x140006cc3  mov     [rcx+1Ah], al
0x140006cc6  mov     qword ptr [rcx+20h], 0
0x140006cce  mov     rax, [rdx+88h]
0x140006cd5  mov     [rcx+28h], rax
0x140006cd9  mov     rax, [rdx+90h]
0x140006ce0  mov     [rcx+30h], rax
0x140006ce4  mov     qword ptr [r14], 0
0x140006ceb  mov     rcx, [rdx+18h]; this
0x140006cef  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140006cf4  mov     rcx, [r15+38h]; this
0x140006cf8  mov     rbp, rax
0x140006cfb  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140006d00  mov     rcx, [r15+80h]; this
0x140006d07  add     rbp, rax
0x140006d0a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140006d0f  add     rbp, rax
0x140006d12  lea     rdi, [rsi+48h]
0x140006d16  cmp     qword ptr [rsi+40h], 0
0x140006d1b  jz      short loc_140006D22
0x140006d1d  cmp     [rdi], rbp
0x140006d20  jnb     short loc_140006D5A
0x140006d22  mov     rdx, rbp; dwBytes
0x140006d25  mov     ecx, 8; dwFlags
0x140006d2a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006d2f  mov     r14, rax
0x140006d32  test    rax, rax
0x140006d35  jz      short loc_140006D56
0x140006d37  mov     rbx, [rsi+40h]
0x140006d3b  call    cs:__imp_GetProcessHeap
0x140006d41  mov     r8, rbx; lpMem
0x140006d44  xor     edx, edx; dwFlags
0x140006d46  mov     rcx, rax; hHeap
0x140006d49  call    cs:__imp_HeapFree
0x140006d4f  mov     [rsi+40h], r14
0x140006d53  mov     [rdi], rbp
0x140006d56  lea     r14, [rsi+38h]
0x140006d5a  mov     rcx, [rsi+40h]; Destination
0x140006d5e  test    rcx, rcx
0x140006d61  jz      short loc_140006DB1
0x140006d63  mov     rbx, [rdi]
0x140006d66  lea     r9, [rsi+10h]
0x140006d6a  mov     r8, [r15+38h]
0x140006d6e  add     rbx, rcx
0x140006d71  mov     rdx, rbx
0x140006d74  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006d79  mov     r8, [r15+80h]
0x140006d80  lea     r9, [rsi+20h]
0x140006d84  mov     rdx, rbx
0x140006d87  mov     rcx, rax; Destination
0x140006d8a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006d8f  mov     r8, [r15+18h]
0x140006d93  mov     r9, r14
0x140006d96  mov     rdx, rbx
0x140006d99  mov     rcx, rax; Destination
0x140006d9c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x140006da1  sub     rbx, rax
0x140006da4  xor     edx, edx; Val
0x140006da6  mov     r8, rbx; Size
0x140006da9  mov     rcx, rax; void *
0x140006dac  call    memset_0
0x140006db1  add     rsp, 28h
0x140006db5  pop     r15
0x140006db7  pop     r14
0x140006db9  pop     r13
0x140006dbb  pop     r12
0x140006dbd  pop     rdi
0x140006dbe  pop     rsi
0x140006dbf  pop     rbp
0x140006dc0  pop     rbx
0x140006dc1  retn
```
