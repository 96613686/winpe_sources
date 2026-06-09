# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007740`
- end: `0x180007876`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007ad8`

## callees

- `0x180003888`
- `0x180004838`
- `0x1800048b0`
- `0x180006fcc`
- `0x1800075b8`
- `0x1800075d8`
- `0x180007740`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077ef`

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
0x180007740  push    rbx
0x180007742  push    rbp
0x180007743  push    rsi
0x180007744  push    rdi
0x180007745  push    r12
0x180007747  push    r13
0x180007749  push    r14
0x18000774b  push    r15
0x18000774d  sub     rsp, 28h
0x180007751  mov     [rcx+4], r8d
0x180007755  lea     r14, [rcx+38h]
0x180007759  mov     eax, [rdx+8]
0x18000775c  mov     rsi, rcx
0x18000775f  mov     [rcx+8], eax
0x180007762  mov     r15, rdx
0x180007765  mov     qword ptr [rcx+10h], 0
0x18000776d  movzx   eax, word ptr [rdx+40h]
0x180007771  mov     [rcx+18h], ax
0x180007775  mov     al, [rdx]
0x180007777  mov     [rcx+1Ah], al
0x18000777a  mov     qword ptr [rcx+20h], 0
0x180007782  mov     rax, [rdx+88h]
0x180007789  mov     [rcx+28h], rax
0x18000778d  mov     rax, [rdx+90h]
0x180007794  mov     [rcx+30h], rax
0x180007798  mov     qword ptr [r14], 0
0x18000779f  mov     rcx, [rdx+18h]; this
0x1800077a3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800077a8  mov     rcx, [r15+38h]; this
0x1800077ac  mov     rbp, rax
0x1800077af  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800077b4  mov     rcx, [r15+80h]; this
0x1800077bb  add     rbp, rax
0x1800077be  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800077c3  add     rbp, rax
0x1800077c6  lea     rdi, [rsi+48h]
0x1800077ca  cmp     qword ptr [rsi+40h], 0
0x1800077cf  jz      short loc_1800077D6
0x1800077d1  cmp     [rdi], rbp
0x1800077d4  jnb     short loc_18000780E
0x1800077d6  mov     rdx, rbp; dwBytes
0x1800077d9  mov     ecx, 8; dwFlags
0x1800077de  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800077e3  mov     r14, rax
0x1800077e6  test    rax, rax
0x1800077e9  jz      short loc_18000780A
0x1800077eb  mov     rbx, [rsi+40h]
0x1800077ef  call    cs:__imp_GetProcessHeap
0x1800077f5  mov     r8, rbx; lpMem
0x1800077f8  xor     edx, edx; dwFlags
0x1800077fa  mov     rcx, rax; hHeap
0x1800077fd  call    cs:__imp_HeapFree
0x180007803  mov     [rsi+40h], r14
0x180007807  mov     [rdi], rbp
0x18000780a  lea     r14, [rsi+38h]
0x18000780e  mov     rcx, [rsi+40h]; Destination
0x180007812  test    rcx, rcx
0x180007815  jz      short loc_180007865
0x180007817  mov     rbx, [rdi]
0x18000781a  lea     r9, [rsi+10h]
0x18000781e  mov     r8, [r15+38h]
0x180007822  add     rbx, rcx
0x180007825  mov     rdx, rbx
0x180007828  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000782d  mov     r8, [r15+80h]
0x180007834  lea     r9, [rsi+20h]
0x180007838  mov     rdx, rbx
0x18000783b  mov     rcx, rax; Destination
0x18000783e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007843  mov     r8, [r15+18h]
0x180007847  mov     r9, r14
0x18000784a  mov     rdx, rbx
0x18000784d  mov     rcx, rax; Destination
0x180007850  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180007855  sub     rbx, rax
0x180007858  xor     edx, edx; Val
0x18000785a  mov     r8, rbx; Size
0x18000785d  mov     rcx, rax; void *
0x180007860  call    memset_0
0x180007865  add     rsp, 28h
0x180007869  pop     r15
0x18000786b  pop     r14
0x18000786d  pop     r13
0x18000786f  pop     r12
0x180007871  pop     rdi
0x180007872  pop     rsi
0x180007873  pop     rbp
0x180007874  pop     rbx
0x180007875  retn
```
