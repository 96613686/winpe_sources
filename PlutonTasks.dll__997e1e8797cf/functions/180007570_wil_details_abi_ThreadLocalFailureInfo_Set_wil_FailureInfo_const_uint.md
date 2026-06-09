# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007570`
- end: `0x1800076a6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800079f4`

## callees

- `0x180002858`
- `0x180002fac`
- `0x180003024`
- `0x1800062c4`
- `0x1800073e0`
- `0x180007400`
- `0x180007570`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000762d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000762d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000761f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000761f`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int16 **v3; // r14
  __int64 v6; // rbp
  const char *v7; // rdx
  __int64 v8; // rbp
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
0x180007570  push    rbx
0x180007572  push    rbp
0x180007573  push    rsi
0x180007574  push    rdi
0x180007575  push    r12
0x180007577  push    r13
0x180007579  push    r14
0x18000757b  push    r15
0x18000757d  sub     rsp, 28h
0x180007581  mov     [rcx+4], r8d
0x180007585  lea     r14, [rcx+38h]
0x180007589  mov     eax, [rdx+8]
0x18000758c  mov     rsi, rcx
0x18000758f  mov     [rcx+8], eax
0x180007592  mov     r15, rdx
0x180007595  mov     qword ptr [rcx+10h], 0
0x18000759d  movzx   eax, word ptr [rdx+40h]
0x1800075a1  mov     [rcx+18h], ax
0x1800075a5  mov     al, [rdx]
0x1800075a7  mov     [rcx+1Ah], al
0x1800075aa  mov     qword ptr [rcx+20h], 0
0x1800075b2  mov     rax, [rdx+88h]
0x1800075b9  mov     [rcx+28h], rax
0x1800075bd  mov     rax, [rdx+90h]
0x1800075c4  mov     [rcx+30h], rax
0x1800075c8  mov     qword ptr [r14], 0
0x1800075cf  mov     rcx, [rdx+18h]; this
0x1800075d3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800075d8  mov     rcx, [r15+38h]; this
0x1800075dc  mov     rbp, rax
0x1800075df  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800075e4  mov     rcx, [r15+80h]; this
0x1800075eb  add     rbp, rax
0x1800075ee  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800075f3  add     rbp, rax
0x1800075f6  lea     rdi, [rsi+48h]
0x1800075fa  cmp     qword ptr [rsi+40h], 0
0x1800075ff  jz      short loc_180007606
0x180007601  cmp     [rdi], rbp
0x180007604  jnb     short loc_18000763E
0x180007606  mov     rdx, rbp; dwBytes
0x180007609  mov     ecx, 8; dwFlags
0x18000760e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007613  mov     r14, rax
0x180007616  test    rax, rax
0x180007619  jz      short loc_18000763A
0x18000761b  mov     rbx, [rsi+40h]
0x18000761f  call    cs:__imp_GetProcessHeap
0x180007625  mov     r8, rbx; lpMem
0x180007628  xor     edx, edx; dwFlags
0x18000762a  mov     rcx, rax; hHeap
0x18000762d  call    cs:__imp_HeapFree
0x180007633  mov     [rsi+40h], r14
0x180007637  mov     [rdi], rbp
0x18000763a  lea     r14, [rsi+38h]
0x18000763e  mov     rcx, [rsi+40h]; Destination
0x180007642  test    rcx, rcx
0x180007645  jz      short loc_180007695
0x180007647  mov     rbx, [rdi]
0x18000764a  lea     r9, [rsi+10h]
0x18000764e  mov     r8, [r15+38h]
0x180007652  add     rbx, rcx
0x180007655  mov     rdx, rbx
0x180007658  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000765d  mov     r8, [r15+80h]
0x180007664  lea     r9, [rsi+20h]
0x180007668  mov     rdx, rbx
0x18000766b  mov     rcx, rax; Destination
0x18000766e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007673  mov     r8, [r15+18h]
0x180007677  mov     r9, r14
0x18000767a  mov     rdx, rbx
0x18000767d  mov     rcx, rax; Destination
0x180007680  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180007685  sub     rbx, rax
0x180007688  xor     edx, edx; Val
0x18000768a  mov     r8, rbx; Size
0x18000768d  mov     rcx, rax; void *
0x180007690  call    memset_0
0x180007695  add     rsp, 28h
0x180007699  pop     r15
0x18000769b  pop     r14
0x18000769d  pop     r13
0x18000769f  pop     r12
0x1800076a1  pop     rdi
0x1800076a2  pop     rsi
0x1800076a3  pop     rbp
0x1800076a4  pop     rbx
0x1800076a5  retn
```
