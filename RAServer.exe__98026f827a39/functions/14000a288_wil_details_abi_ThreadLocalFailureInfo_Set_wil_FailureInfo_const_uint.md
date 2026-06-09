# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000a288`
- end: `0x14000a3be`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000a70c`

## callees

- `0x1400022d3`
- `0x140002e80`
- `0x140002ef8`
- `0x140008694`
- `0x14000a0a4`
- `0x14000a0c4`
- `0x14000a288`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14000a337`
- `KERNEL32!GetProcessHeap` at `0x14000a337`
- `KERNEL32!HeapFree` at `0x14000a345`
- `KERNEL32!HeapFree` at `0x14000a345`

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
0x14000a288  push    rbx
0x14000a28a  push    rbp
0x14000a28b  push    rsi
0x14000a28c  push    rdi
0x14000a28d  push    r12
0x14000a28f  push    r13
0x14000a291  push    r14
0x14000a293  push    r15
0x14000a295  sub     rsp, 28h
0x14000a299  mov     [rcx+4], r8d
0x14000a29d  lea     r14, [rcx+38h]
0x14000a2a1  mov     eax, [rdx+8]
0x14000a2a4  mov     rsi, rcx
0x14000a2a7  mov     [rcx+8], eax
0x14000a2aa  mov     r15, rdx
0x14000a2ad  mov     qword ptr [rcx+10h], 0
0x14000a2b5  movzx   eax, word ptr [rdx+40h]
0x14000a2b9  mov     [rcx+18h], ax
0x14000a2bd  mov     al, [rdx]
0x14000a2bf  mov     [rcx+1Ah], al
0x14000a2c2  mov     qword ptr [rcx+20h], 0
0x14000a2ca  mov     rax, [rdx+88h]
0x14000a2d1  mov     [rcx+28h], rax
0x14000a2d5  mov     rax, [rdx+90h]
0x14000a2dc  mov     [rcx+30h], rax
0x14000a2e0  mov     qword ptr [r14], 0
0x14000a2e7  mov     rcx, [rdx+18h]; this
0x14000a2eb  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x14000a2f0  mov     rcx, [r15+38h]; this
0x14000a2f4  mov     rbp, rax
0x14000a2f7  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14000a2fc  mov     rcx, [r15+80h]; this
0x14000a303  add     rbp, rax
0x14000a306  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14000a30b  add     rbp, rax
0x14000a30e  lea     rdi, [rsi+48h]
0x14000a312  cmp     qword ptr [rsi+40h], 0
0x14000a317  jz      short loc_14000A31E
0x14000a319  cmp     [rdi], rbp
0x14000a31c  jnb     short loc_14000A356
0x14000a31e  mov     rdx, rbp; dwBytes
0x14000a321  mov     ecx, 8; dwFlags
0x14000a326  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000a32b  mov     r14, rax
0x14000a32e  test    rax, rax
0x14000a331  jz      short loc_14000A352
0x14000a333  mov     rbx, [rsi+40h]
0x14000a337  call    cs:__imp_GetProcessHeap
0x14000a33d  mov     r8, rbx; lpMem
0x14000a340  xor     edx, edx; dwFlags
0x14000a342  mov     rcx, rax; hHeap
0x14000a345  call    cs:__imp_HeapFree
0x14000a34b  mov     [rsi+40h], r14
0x14000a34f  mov     [rdi], rbp
0x14000a352  lea     r14, [rsi+38h]
0x14000a356  mov     rcx, [rsi+40h]; Destination
0x14000a35a  test    rcx, rcx
0x14000a35d  jz      short loc_14000A3AD
0x14000a35f  mov     rbx, [rdi]
0x14000a362  lea     r9, [rsi+10h]
0x14000a366  mov     r8, [r15+38h]
0x14000a36a  add     rbx, rcx
0x14000a36d  mov     rdx, rbx
0x14000a370  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000a375  mov     r8, [r15+80h]
0x14000a37c  lea     r9, [rsi+20h]
0x14000a380  mov     rdx, rbx
0x14000a383  mov     rcx, rax; Destination
0x14000a386  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000a38b  mov     r8, [r15+18h]
0x14000a38f  mov     r9, r14
0x14000a392  mov     rdx, rbx
0x14000a395  mov     rcx, rax; Destination
0x14000a398  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x14000a39d  sub     rbx, rax
0x14000a3a0  xor     edx, edx; Val
0x14000a3a2  mov     r8, rbx; Size
0x14000a3a5  mov     rcx, rax; void *
0x14000a3a8  call    memset_0
0x14000a3ad  add     rsp, 28h
0x14000a3b1  pop     r15
0x14000a3b3  pop     r14
0x14000a3b5  pop     r13
0x14000a3b7  pop     r12
0x14000a3b9  pop     rdi
0x14000a3ba  pop     rsi
0x14000a3bb  pop     rbp
0x14000a3bc  pop     rbx
0x14000a3bd  retn
```
