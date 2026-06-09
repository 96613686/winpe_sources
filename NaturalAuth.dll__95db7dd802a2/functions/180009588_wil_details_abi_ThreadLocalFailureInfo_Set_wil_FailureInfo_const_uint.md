# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009588`
- end: `0x1800096be`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180009920`

## callees

- `0x180005140`
- `0x180006ae8`
- `0x180006b60`
- `0x180008c98`
- `0x180009098`
- `0x1800090b8`
- `0x180009588`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009645`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009645`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009637`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009637`

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
0x180009588  push    rbx
0x18000958a  push    rbp
0x18000958b  push    rsi
0x18000958c  push    rdi
0x18000958d  push    r12
0x18000958f  push    r13
0x180009591  push    r14
0x180009593  push    r15
0x180009595  sub     rsp, 28h
0x180009599  mov     [rcx+4], r8d
0x18000959d  lea     r14, [rcx+38h]
0x1800095a1  mov     eax, [rdx+8]
0x1800095a4  mov     rsi, rcx
0x1800095a7  mov     [rcx+8], eax
0x1800095aa  mov     r15, rdx
0x1800095ad  mov     qword ptr [rcx+10h], 0
0x1800095b5  movzx   eax, word ptr [rdx+40h]
0x1800095b9  mov     [rcx+18h], ax
0x1800095bd  mov     al, [rdx]
0x1800095bf  mov     [rcx+1Ah], al
0x1800095c2  mov     qword ptr [rcx+20h], 0
0x1800095ca  mov     rax, [rdx+88h]
0x1800095d1  mov     [rcx+28h], rax
0x1800095d5  mov     rax, [rdx+90h]
0x1800095dc  mov     [rcx+30h], rax
0x1800095e0  mov     qword ptr [r14], 0
0x1800095e7  mov     rcx, [rdx+18h]; this
0x1800095eb  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800095f0  mov     rcx, [r15+38h]; this
0x1800095f4  mov     rbp, rax
0x1800095f7  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800095fc  mov     rcx, [r15+80h]; this
0x180009603  add     rbp, rax
0x180009606  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000960b  add     rbp, rax
0x18000960e  lea     rdi, [rsi+48h]
0x180009612  cmp     qword ptr [rsi+40h], 0
0x180009617  jz      short loc_18000961E
0x180009619  cmp     [rdi], rbp
0x18000961c  jnb     short loc_180009656
0x18000961e  mov     rdx, rbp; dwBytes
0x180009621  mov     ecx, 8; dwFlags
0x180009626  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000962b  mov     r14, rax
0x18000962e  test    rax, rax
0x180009631  jz      short loc_180009652
0x180009633  mov     rbx, [rsi+40h]
0x180009637  call    cs:__imp_GetProcessHeap
0x18000963d  mov     r8, rbx; lpMem
0x180009640  xor     edx, edx; dwFlags
0x180009642  mov     rcx, rax; hHeap
0x180009645  call    cs:__imp_HeapFree
0x18000964b  mov     [rsi+40h], r14
0x18000964f  mov     [rdi], rbp
0x180009652  lea     r14, [rsi+38h]
0x180009656  mov     rcx, [rsi+40h]; Destination
0x18000965a  test    rcx, rcx
0x18000965d  jz      short loc_1800096AD
0x18000965f  mov     rbx, [rdi]
0x180009662  lea     r9, [rsi+10h]
0x180009666  mov     r8, [r15+38h]
0x18000966a  add     rbx, rcx
0x18000966d  mov     rdx, rbx
0x180009670  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009675  mov     r8, [r15+80h]
0x18000967c  lea     r9, [rsi+20h]
0x180009680  mov     rdx, rbx
0x180009683  mov     rcx, rax; Destination
0x180009686  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000968b  mov     r8, [r15+18h]
0x18000968f  mov     r9, r14
0x180009692  mov     rdx, rbx
0x180009695  mov     rcx, rax; Destination
0x180009698  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000969d  sub     rbx, rax
0x1800096a0  xor     edx, edx; Val
0x1800096a2  mov     r8, rbx; Size
0x1800096a5  mov     rcx, rax; void *
0x1800096a8  call    memset_0
0x1800096ad  add     rsp, 28h
0x1800096b1  pop     r15
0x1800096b3  pop     r14
0x1800096b5  pop     r13
0x1800096b7  pop     r12
0x1800096b9  pop     rdi
0x1800096ba  pop     rsi
0x1800096bb  pop     rbp
0x1800096bc  pop     rbx
0x1800096bd  retn
```
