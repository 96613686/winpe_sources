# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180011510`
- end: `0x180011646`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180011984`

## callees

- `0x18000f204`
- `0x18000f27c`
- `0x180010bf8`
- `0x180011420`
- `0x180011440`
- `0x180011510`
- `0x18001a342`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800115bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800115bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800115cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800115cd`

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
0x180011510  push    rbx
0x180011512  push    rbp
0x180011513  push    rsi
0x180011514  push    rdi
0x180011515  push    r12
0x180011517  push    r13
0x180011519  push    r14
0x18001151b  push    r15
0x18001151d  sub     rsp, 28h
0x180011521  mov     [rcx+4], r8d
0x180011525  lea     r14, [rcx+38h]
0x180011529  mov     eax, [rdx+8]
0x18001152c  mov     rsi, rcx
0x18001152f  mov     [rcx+8], eax
0x180011532  mov     r15, rdx
0x180011535  mov     qword ptr [rcx+10h], 0
0x18001153d  movzx   eax, word ptr [rdx+40h]
0x180011541  mov     [rcx+18h], ax
0x180011545  mov     al, [rdx]
0x180011547  mov     [rcx+1Ah], al
0x18001154a  mov     qword ptr [rcx+20h], 0
0x180011552  mov     rax, [rdx+88h]
0x180011559  mov     [rcx+28h], rax
0x18001155d  mov     rax, [rdx+90h]
0x180011564  mov     [rcx+30h], rax
0x180011568  mov     qword ptr [r14], 0
0x18001156f  mov     rcx, [rdx+18h]; this
0x180011573  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180011578  mov     rcx, [r15+38h]; this
0x18001157c  mov     rbp, rax
0x18001157f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180011584  mov     rcx, [r15+80h]; this
0x18001158b  add     rbp, rax
0x18001158e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180011593  add     rbp, rax
0x180011596  lea     rdi, [rsi+48h]
0x18001159a  cmp     qword ptr [rsi+40h], 0
0x18001159f  jz      short loc_1800115A6
0x1800115a1  cmp     [rdi], rbp
0x1800115a4  jnb     short loc_1800115DE
0x1800115a6  mov     rdx, rbp; dwBytes
0x1800115a9  mov     ecx, 8; dwFlags
0x1800115ae  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800115b3  mov     r14, rax
0x1800115b6  test    rax, rax
0x1800115b9  jz      short loc_1800115DA
0x1800115bb  mov     rbx, [rsi+40h]
0x1800115bf  call    cs:__imp_GetProcessHeap
0x1800115c5  mov     r8, rbx; lpMem
0x1800115c8  xor     edx, edx; dwFlags
0x1800115ca  mov     rcx, rax; hHeap
0x1800115cd  call    cs:__imp_HeapFree
0x1800115d3  mov     [rsi+40h], r14
0x1800115d7  mov     [rdi], rbp
0x1800115da  lea     r14, [rsi+38h]
0x1800115de  mov     rcx, [rsi+40h]; Destination
0x1800115e2  test    rcx, rcx
0x1800115e5  jz      short loc_180011635
0x1800115e7  mov     rbx, [rdi]
0x1800115ea  lea     r9, [rsi+10h]
0x1800115ee  mov     r8, [r15+38h]
0x1800115f2  add     rbx, rcx
0x1800115f5  mov     rdx, rbx
0x1800115f8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800115fd  mov     r8, [r15+80h]
0x180011604  lea     r9, [rsi+20h]
0x180011608  mov     rdx, rbx
0x18001160b  mov     rcx, rax; Destination
0x18001160e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180011613  mov     r8, [r15+18h]
0x180011617  mov     r9, r14
0x18001161a  mov     rdx, rbx
0x18001161d  mov     rcx, rax; Destination
0x180011620  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180011625  sub     rbx, rax
0x180011628  xor     edx, edx; Val
0x18001162a  mov     r8, rbx; Size
0x18001162d  mov     rcx, rax; void *
0x180011630  call    memset_0
0x180011635  add     rsp, 28h
0x180011639  pop     r15
0x18001163b  pop     r14
0x18001163d  pop     r13
0x18001163f  pop     r12
0x180011641  pop     rdi
0x180011642  pop     rsi
0x180011643  pop     rbp
0x180011644  pop     rbx
0x180011645  retn
```
