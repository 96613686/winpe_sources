# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140006b50`
- end: `0x140006c86`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140006ee8`

## callees

- `0x140002d50`
- `0x1400039ec`
- `0x140003a64`
- `0x140006638`
- `0x1400069d8`
- `0x1400069f8`
- `0x140006b50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006c0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006c0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006bff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006bff`

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
0x140006b50  push    rbx
0x140006b52  push    rbp
0x140006b53  push    rsi
0x140006b54  push    rdi
0x140006b55  push    r12
0x140006b57  push    r13
0x140006b59  push    r14
0x140006b5b  push    r15
0x140006b5d  sub     rsp, 28h
0x140006b61  mov     [rcx+4], r8d
0x140006b65  lea     r14, [rcx+38h]
0x140006b69  mov     eax, [rdx+8]
0x140006b6c  mov     rsi, rcx
0x140006b6f  mov     [rcx+8], eax
0x140006b72  mov     r15, rdx
0x140006b75  mov     qword ptr [rcx+10h], 0
0x140006b7d  movzx   eax, word ptr [rdx+40h]
0x140006b81  mov     [rcx+18h], ax
0x140006b85  mov     al, [rdx]
0x140006b87  mov     [rcx+1Ah], al
0x140006b8a  mov     qword ptr [rcx+20h], 0
0x140006b92  mov     rax, [rdx+88h]
0x140006b99  mov     [rcx+28h], rax
0x140006b9d  mov     rax, [rdx+90h]
0x140006ba4  mov     [rcx+30h], rax
0x140006ba8  mov     qword ptr [r14], 0
0x140006baf  mov     rcx, [rdx+18h]; this
0x140006bb3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140006bb8  mov     rcx, [r15+38h]; this
0x140006bbc  mov     rbp, rax
0x140006bbf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140006bc4  mov     rcx, [r15+80h]; this
0x140006bcb  add     rbp, rax
0x140006bce  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140006bd3  add     rbp, rax
0x140006bd6  lea     rdi, [rsi+48h]
0x140006bda  cmp     qword ptr [rsi+40h], 0
0x140006bdf  jz      short loc_140006BE6
0x140006be1  cmp     [rdi], rbp
0x140006be4  jnb     short loc_140006C1E
0x140006be6  mov     rdx, rbp; dwBytes
0x140006be9  mov     ecx, 8; dwFlags
0x140006bee  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006bf3  mov     r14, rax
0x140006bf6  test    rax, rax
0x140006bf9  jz      short loc_140006C1A
0x140006bfb  mov     rbx, [rsi+40h]
0x140006bff  call    cs:__imp_GetProcessHeap
0x140006c05  mov     r8, rbx; lpMem
0x140006c08  xor     edx, edx; dwFlags
0x140006c0a  mov     rcx, rax; hHeap
0x140006c0d  call    cs:__imp_HeapFree
0x140006c13  mov     [rsi+40h], r14
0x140006c17  mov     [rdi], rbp
0x140006c1a  lea     r14, [rsi+38h]
0x140006c1e  mov     rcx, [rsi+40h]; Destination
0x140006c22  test    rcx, rcx
0x140006c25  jz      short loc_140006C75
0x140006c27  mov     rbx, [rdi]
0x140006c2a  lea     r9, [rsi+10h]
0x140006c2e  mov     r8, [r15+38h]
0x140006c32  add     rbx, rcx
0x140006c35  mov     rdx, rbx
0x140006c38  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006c3d  mov     r8, [r15+80h]
0x140006c44  lea     r9, [rsi+20h]
0x140006c48  mov     rdx, rbx
0x140006c4b  mov     rcx, rax; Destination
0x140006c4e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006c53  mov     r8, [r15+18h]
0x140006c57  mov     r9, r14
0x140006c5a  mov     rdx, rbx
0x140006c5d  mov     rcx, rax; Destination
0x140006c60  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x140006c65  sub     rbx, rax
0x140006c68  xor     edx, edx; Val
0x140006c6a  mov     r8, rbx; Size
0x140006c6d  mov     rcx, rax; void *
0x140006c70  call    memset_0
0x140006c75  add     rsp, 28h
0x140006c79  pop     r15
0x140006c7b  pop     r14
0x140006c7d  pop     r13
0x140006c7f  pop     r12
0x140006c81  pop     rdi
0x140006c82  pop     rsi
0x140006c83  pop     rbp
0x140006c84  pop     rbx
0x140006c85  retn
```
