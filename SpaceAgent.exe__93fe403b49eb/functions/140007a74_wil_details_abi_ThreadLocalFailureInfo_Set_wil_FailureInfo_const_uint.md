# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140007a74`
- end: `0x140007be5`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140007cd8`

## callees

- `0x140001caf`
- `0x140003fa0`
- `0x140006c60`
- `0x1400078fc`
- `0x14000791c`
- `0x140007a74`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140007b2a`
- `KERNEL32!HeapFree` at `0x140007b2a`
- `KERNEL32!GetProcessHeap` at `0x140007b1c`
- `KERNEL32!GetProcessHeap` at `0x140007b1c`
- `msvcrt!memcpy_s` at `0x140007ba9`
- `msvcrt!memcpy_s` at `0x140007ba9`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  char **v3; // rbx
  char **v4; // rsi
  unsigned __int64 v7; // r15
  const char *v8; // rdx
  unsigned __int64 v9; // r15
  const char *v10; // rdx
  SIZE_T v11; // r15
  SIZE_T *v12; // rdi
  LPVOID v13; // r12
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  char *v16; // rcx
  const char *v17; // rdi
  char *v18; // rax
  const unsigned __int16 *v19; // rdx
  char *v20; // rbx
  wil::details *v21; // rcx
  rsize_t v22; // rax
  const void *v23; // rcx
  rsize_t v24; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (char **)((char *)this + 32);
  v4 = (char **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v8) + v7;
  v11 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v10) + v9;
  v12 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v12 < v11 )
  {
    v13 = wil::details::ProcessHeapAlloc(8u, v11);
    if ( v13 )
    {
      v14 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
      *((_QWORD *)this + 8) = v13;
      v3 = (char **)((char *)this + 32);
      *v12 = v11;
    }
  }
  v16 = (char *)*((_QWORD *)this + 8);
  if ( v16 )
  {
    v17 = &v16[*v12];
    v18 = wil::details::WriteResultString<char const *>(v16, v17, *((wil::details **)a2 + 7), (char **)this + 2);
    v20 = wil::details::WriteResultString<char const *>(v18, v17, *((wil::details **)a2 + 16), v3);
    if ( v20 != v17
      && (v21 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v21
      && (v22 = wil::details::ResultStringSize(v21, v19), v24 = v22, v17 - v20 >= v22) )
    {
      memcpy_s(v20, v17 - v20, v23, v22);
      if ( v4 )
        *v4 = v20;
      v20 += v24;
    }
    else if ( v4 )
    {
      *v4 = 0;
    }
    memset_0(v20, 0, v17 - v20);
  }
}

```

## disassembly

```asm
0x140007a74  push    rbx
0x140007a76  push    rbp
0x140007a77  push    rsi
0x140007a78  push    rdi
0x140007a79  push    r12
0x140007a7b  push    r13
0x140007a7d  push    r14
0x140007a7f  push    r15
0x140007a81  sub     rsp, 28h
0x140007a85  mov     [rcx+4], r8d
0x140007a89  lea     rbx, [rcx+20h]
0x140007a8d  mov     eax, [rdx+8]
0x140007a90  lea     rsi, [rcx+38h]
0x140007a94  mov     [rcx+8], eax
0x140007a97  xor     r12d, r12d
0x140007a9a  mov     [rcx+10h], r12
0x140007a9e  mov     rbp, rcx
0x140007aa1  movzx   eax, word ptr [rdx+40h]
0x140007aa5  mov     r14, rdx
0x140007aa8  mov     [rcx+18h], ax
0x140007aac  mov     al, [rdx]
0x140007aae  mov     [rcx+1Ah], al
0x140007ab1  mov     [rbx], r12
0x140007ab4  mov     rax, [rdx+88h]
0x140007abb  mov     [rcx+28h], rax
0x140007abf  mov     rax, [rdx+90h]
0x140007ac6  mov     [rcx+30h], rax
0x140007aca  mov     [rsi], r12
0x140007acd  mov     rcx, [rdx+18h]; this
0x140007ad1  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140007ad6  mov     rcx, [r14+38h]; this
0x140007ada  mov     r15, rax
0x140007add  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140007ae2  mov     rcx, [r14+80h]; this
0x140007ae9  add     r15, rax
0x140007aec  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140007af1  add     r15, rax
0x140007af4  lea     rdi, [rbp+48h]
0x140007af8  cmp     [rbp+40h], r12
0x140007afc  jz      short loc_140007B03
0x140007afe  cmp     [rdi], r15
0x140007b01  jnb     short loc_140007B3E
0x140007b03  mov     rdx, r15; dwBytes
0x140007b06  mov     ecx, 8; dwFlags
0x140007b0b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140007b10  mov     r12, rax
0x140007b13  test    rax, rax
0x140007b16  jz      short loc_140007B3B
0x140007b18  mov     rbx, [rbp+40h]
0x140007b1c  call    cs:__imp_GetProcessHeap
0x140007b22  mov     r8, rbx; lpMem
0x140007b25  xor     edx, edx; dwFlags
0x140007b27  mov     rcx, rax; hHeap
0x140007b2a  call    cs:__imp_HeapFree
0x140007b30  mov     [rbp+40h], r12
0x140007b34  lea     rbx, [rbp+20h]
0x140007b38  mov     [rdi], r15
0x140007b3b  xor     r12d, r12d
0x140007b3e  mov     rcx, [rbp+40h]; Destination
0x140007b42  test    rcx, rcx
0x140007b45  jz      loc_140007BD4
0x140007b4b  mov     rdi, [rdi]
0x140007b4e  lea     r9, [rbp+10h]
0x140007b52  mov     r8, [r14+38h]
0x140007b56  add     rdi, rcx
0x140007b59  mov     rdx, rdi
0x140007b5c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140007b61  mov     r8, [r14+80h]
0x140007b68  mov     r9, rbx
0x140007b6b  mov     rdx, rdi
0x140007b6e  mov     rcx, rax; Destination
0x140007b71  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140007b76  mov     rbx, rax
0x140007b79  cmp     rax, rdi
0x140007b7c  jz      short loc_140007BBC
0x140007b7e  mov     rcx, [r14+18h]; this
0x140007b82  test    rcx, rcx
0x140007b85  jz      short loc_140007BBC
0x140007b87  cmp     [rcx], r12w
0x140007b8b  jz      short loc_140007BBC
0x140007b8d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140007b92  mov     rdx, rdi
0x140007b95  mov     r14, rax
0x140007b98  sub     rdx, rbx; DestinationSize
0x140007b9b  cmp     rdx, rax
0x140007b9e  jb      short loc_140007BBC
0x140007ba0  mov     r8, rcx; Source
0x140007ba3  mov     r9, rax; SourceSize
0x140007ba6  mov     rcx, rbx; Destination
0x140007ba9  call    cs:__imp_memcpy_s
0x140007baf  test    rsi, rsi
0x140007bb2  jz      short loc_140007BB7
0x140007bb4  mov     [rsi], rbx
0x140007bb7  add     rbx, r14
0x140007bba  jmp     short loc_140007BC4
0x140007bbc  test    rsi, rsi
0x140007bbf  jz      short loc_140007BC4
0x140007bc1  mov     [rsi], r12
0x140007bc4  sub     rdi, rbx
0x140007bc7  xor     edx, edx; Val
0x140007bc9  mov     r8, rdi; Size
0x140007bcc  mov     rcx, rbx; void *
0x140007bcf  call    memset_0
0x140007bd4  add     rsp, 28h
0x140007bd8  pop     r15
0x140007bda  pop     r14
0x140007bdc  pop     r13
0x140007bde  pop     r12
0x140007be0  pop     rdi
0x140007be1  pop     rsi
0x140007be2  pop     rbp
0x140007be3  pop     rbx
0x140007be4  retn
```
