# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180004aac`
- end: `0x180004be2`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004e44`

## callees

- `0x180002c10`
- `0x180002c88`
- `0x180004628`
- `0x1800049c8`
- `0x1800049e8`
- `0x180004aac`
- `0x18001dfe2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b5b`

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
0x180004aac  push    rbx
0x180004aae  push    rbp
0x180004aaf  push    rsi
0x180004ab0  push    rdi
0x180004ab1  push    r12
0x180004ab3  push    r13
0x180004ab5  push    r14
0x180004ab7  push    r15
0x180004ab9  sub     rsp, 28h
0x180004abd  mov     [rcx+4], r8d
0x180004ac1  lea     r14, [rcx+38h]
0x180004ac5  mov     eax, [rdx+8]
0x180004ac8  mov     rsi, rcx
0x180004acb  mov     [rcx+8], eax
0x180004ace  mov     r15, rdx
0x180004ad1  mov     qword ptr [rcx+10h], 0
0x180004ad9  movzx   eax, word ptr [rdx+40h]
0x180004add  mov     [rcx+18h], ax
0x180004ae1  mov     al, [rdx]
0x180004ae3  mov     [rcx+1Ah], al
0x180004ae6  mov     qword ptr [rcx+20h], 0
0x180004aee  mov     rax, [rdx+88h]
0x180004af5  mov     [rcx+28h], rax
0x180004af9  mov     rax, [rdx+90h]
0x180004b00  mov     [rcx+30h], rax
0x180004b04  mov     qword ptr [r14], 0
0x180004b0b  mov     rcx, [rdx+18h]; this
0x180004b0f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180004b14  mov     rcx, [r15+38h]; this
0x180004b18  mov     rbp, rax
0x180004b1b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180004b20  mov     rcx, [r15+80h]; this
0x180004b27  add     rbp, rax
0x180004b2a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180004b2f  add     rbp, rax
0x180004b32  lea     rdi, [rsi+48h]
0x180004b36  cmp     qword ptr [rsi+40h], 0
0x180004b3b  jz      short loc_180004B42
0x180004b3d  cmp     [rdi], rbp
0x180004b40  jnb     short loc_180004B7A
0x180004b42  mov     rdx, rbp; dwBytes
0x180004b45  mov     ecx, 8; dwFlags
0x180004b4a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004b4f  mov     r14, rax
0x180004b52  test    rax, rax
0x180004b55  jz      short loc_180004B76
0x180004b57  mov     rbx, [rsi+40h]
0x180004b5b  call    cs:__imp_GetProcessHeap
0x180004b61  mov     r8, rbx; lpMem
0x180004b64  xor     edx, edx; dwFlags
0x180004b66  mov     rcx, rax; hHeap
0x180004b69  call    cs:__imp_HeapFree
0x180004b6f  mov     [rsi+40h], r14
0x180004b73  mov     [rdi], rbp
0x180004b76  lea     r14, [rsi+38h]
0x180004b7a  mov     rcx, [rsi+40h]; Destination
0x180004b7e  test    rcx, rcx
0x180004b81  jz      short loc_180004BD1
0x180004b83  mov     rbx, [rdi]
0x180004b86  lea     r9, [rsi+10h]
0x180004b8a  mov     r8, [r15+38h]
0x180004b8e  add     rbx, rcx
0x180004b91  mov     rdx, rbx
0x180004b94  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004b99  mov     r8, [r15+80h]
0x180004ba0  lea     r9, [rsi+20h]
0x180004ba4  mov     rdx, rbx
0x180004ba7  mov     rcx, rax; Destination
0x180004baa  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004baf  mov     r8, [r15+18h]
0x180004bb3  mov     r9, r14
0x180004bb6  mov     rdx, rbx
0x180004bb9  mov     rcx, rax; Destination
0x180004bbc  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180004bc1  sub     rbx, rax
0x180004bc4  xor     edx, edx; Val
0x180004bc6  mov     r8, rbx; Size
0x180004bc9  mov     rcx, rax; void *
0x180004bcc  call    memset_0
0x180004bd1  add     rsp, 28h
0x180004bd5  pop     r15
0x180004bd7  pop     r14
0x180004bd9  pop     r13
0x180004bdb  pop     r12
0x180004bdd  pop     rdi
0x180004bde  pop     rsi
0x180004bdf  pop     rbp
0x180004be0  pop     rbx
0x180004be1  retn
```
