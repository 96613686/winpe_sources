# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007fe0`
- end: `0x180008116`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008470`

## callees

- `0x180003710`
- `0x180004154`
- `0x1800041cc`
- `0x180006f5c`
- `0x180007e4c`
- `0x180007e6c`
- `0x180007fe0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000808f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000808f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000809d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000809d`

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
0x180007fe0  push    rbx
0x180007fe2  push    rbp
0x180007fe3  push    rsi
0x180007fe4  push    rdi
0x180007fe5  push    r12
0x180007fe7  push    r13
0x180007fe9  push    r14
0x180007feb  push    r15
0x180007fed  sub     rsp, 28h
0x180007ff1  mov     [rcx+4], r8d
0x180007ff5  lea     r14, [rcx+38h]
0x180007ff9  mov     eax, [rdx+8]
0x180007ffc  mov     rsi, rcx
0x180007fff  mov     [rcx+8], eax
0x180008002  mov     r15, rdx
0x180008005  mov     qword ptr [rcx+10h], 0
0x18000800d  movzx   eax, word ptr [rdx+40h]
0x180008011  mov     [rcx+18h], ax
0x180008015  mov     al, [rdx]
0x180008017  mov     [rcx+1Ah], al
0x18000801a  mov     qword ptr [rcx+20h], 0
0x180008022  mov     rax, [rdx+88h]
0x180008029  mov     [rcx+28h], rax
0x18000802d  mov     rax, [rdx+90h]
0x180008034  mov     [rcx+30h], rax
0x180008038  mov     qword ptr [r14], 0
0x18000803f  mov     rcx, [rdx+18h]; this
0x180008043  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180008048  mov     rcx, [r15+38h]; this
0x18000804c  mov     rbp, rax
0x18000804f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008054  mov     rcx, [r15+80h]; this
0x18000805b  add     rbp, rax
0x18000805e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008063  add     rbp, rax
0x180008066  lea     rdi, [rsi+48h]
0x18000806a  cmp     qword ptr [rsi+40h], 0
0x18000806f  jz      short loc_180008076
0x180008071  cmp     [rdi], rbp
0x180008074  jnb     short loc_1800080AE
0x180008076  mov     rdx, rbp; dwBytes
0x180008079  mov     ecx, 8; dwFlags
0x18000807e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008083  mov     r14, rax
0x180008086  test    rax, rax
0x180008089  jz      short loc_1800080AA
0x18000808b  mov     rbx, [rsi+40h]
0x18000808f  call    cs:__imp_GetProcessHeap
0x180008095  mov     r8, rbx; lpMem
0x180008098  xor     edx, edx; dwFlags
0x18000809a  mov     rcx, rax; hHeap
0x18000809d  call    cs:__imp_HeapFree
0x1800080a3  mov     [rsi+40h], r14
0x1800080a7  mov     [rdi], rbp
0x1800080aa  lea     r14, [rsi+38h]
0x1800080ae  mov     rcx, [rsi+40h]; Destination
0x1800080b2  test    rcx, rcx
0x1800080b5  jz      short loc_180008105
0x1800080b7  mov     rbx, [rdi]
0x1800080ba  lea     r9, [rsi+10h]
0x1800080be  mov     r8, [r15+38h]
0x1800080c2  add     rbx, rcx
0x1800080c5  mov     rdx, rbx
0x1800080c8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800080cd  mov     r8, [r15+80h]
0x1800080d4  lea     r9, [rsi+20h]
0x1800080d8  mov     rdx, rbx
0x1800080db  mov     rcx, rax; Destination
0x1800080de  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800080e3  mov     r8, [r15+18h]
0x1800080e7  mov     r9, r14
0x1800080ea  mov     rdx, rbx
0x1800080ed  mov     rcx, rax; Destination
0x1800080f0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800080f5  sub     rbx, rax
0x1800080f8  xor     edx, edx; Val
0x1800080fa  mov     r8, rbx; Size
0x1800080fd  mov     rcx, rax; void *
0x180008100  call    memset_0
0x180008105  add     rsp, 28h
0x180008109  pop     r15
0x18000810b  pop     r14
0x18000810d  pop     r13
0x18000810f  pop     r12
0x180008111  pop     rdi
0x180008112  pop     rsi
0x180008113  pop     rbp
0x180008114  pop     rbx
0x180008115  retn
```
