# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140013eec`
- end: `0x140014022`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140014380`

## callees

- `0x1400042c4`
- `0x1400070ec`
- `0x140007164`
- `0x1400107dc`
- `0x14001362c`
- `0x14001364c`
- `0x140013eec`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140013fa9`
- `KERNEL32!HeapFree` at `0x140013fa9`
- `KERNEL32!GetProcessHeap` at `0x140013f9b`
- `KERNEL32!GetProcessHeap` at `0x140013f9b`

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
0x140013eec  push    rbx
0x140013eee  push    rbp
0x140013eef  push    rsi
0x140013ef0  push    rdi
0x140013ef1  push    r12
0x140013ef3  push    r13
0x140013ef5  push    r14
0x140013ef7  push    r15
0x140013ef9  sub     rsp, 28h
0x140013efd  mov     [rcx+4], r8d
0x140013f01  lea     r14, [rcx+38h]
0x140013f05  mov     eax, [rdx+8]
0x140013f08  mov     rsi, rcx
0x140013f0b  mov     [rcx+8], eax
0x140013f0e  mov     r15, rdx
0x140013f11  mov     qword ptr [rcx+10h], 0
0x140013f19  movzx   eax, word ptr [rdx+40h]
0x140013f1d  mov     [rcx+18h], ax
0x140013f21  mov     al, [rdx]
0x140013f23  mov     [rcx+1Ah], al
0x140013f26  mov     qword ptr [rcx+20h], 0
0x140013f2e  mov     rax, [rdx+88h]
0x140013f35  mov     [rcx+28h], rax
0x140013f39  mov     rax, [rdx+90h]
0x140013f40  mov     [rcx+30h], rax
0x140013f44  mov     qword ptr [r14], 0
0x140013f4b  mov     rcx, [rdx+18h]; this
0x140013f4f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140013f54  mov     rcx, [r15+38h]; this
0x140013f58  mov     rbp, rax
0x140013f5b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140013f60  mov     rcx, [r15+80h]; this
0x140013f67  add     rbp, rax
0x140013f6a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140013f6f  add     rbp, rax
0x140013f72  lea     rdi, [rsi+48h]
0x140013f76  cmp     qword ptr [rsi+40h], 0
0x140013f7b  jz      short loc_140013F82
0x140013f7d  cmp     [rdi], rbp
0x140013f80  jnb     short loc_140013FBA
0x140013f82  mov     rdx, rbp; dwBytes
0x140013f85  mov     ecx, 8; dwFlags
0x140013f8a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140013f8f  mov     r14, rax
0x140013f92  test    rax, rax
0x140013f95  jz      short loc_140013FB6
0x140013f97  mov     rbx, [rsi+40h]
0x140013f9b  call    cs:__imp_GetProcessHeap
0x140013fa1  mov     r8, rbx; lpMem
0x140013fa4  xor     edx, edx; dwFlags
0x140013fa6  mov     rcx, rax; hHeap
0x140013fa9  call    cs:__imp_HeapFree
0x140013faf  mov     [rsi+40h], r14
0x140013fb3  mov     [rdi], rbp
0x140013fb6  lea     r14, [rsi+38h]
0x140013fba  mov     rcx, [rsi+40h]; Destination
0x140013fbe  test    rcx, rcx
0x140013fc1  jz      short loc_140014011
0x140013fc3  mov     rbx, [rdi]
0x140013fc6  lea     r9, [rsi+10h]
0x140013fca  mov     r8, [r15+38h]
0x140013fce  add     rbx, rcx
0x140013fd1  mov     rdx, rbx
0x140013fd4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140013fd9  mov     r8, [r15+80h]
0x140013fe0  lea     r9, [rsi+20h]
0x140013fe4  mov     rdx, rbx
0x140013fe7  mov     rcx, rax; Destination
0x140013fea  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140013fef  mov     r8, [r15+18h]
0x140013ff3  mov     r9, r14
0x140013ff6  mov     rdx, rbx
0x140013ff9  mov     rcx, rax; Destination
0x140013ffc  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x140014001  sub     rbx, rax
0x140014004  xor     edx, edx; Val
0x140014006  mov     r8, rbx; Size
0x140014009  mov     rcx, rax; void *
0x14001400c  call    memset_0
0x140014011  add     rsp, 28h
0x140014015  pop     r15
0x140014017  pop     r14
0x140014019  pop     r13
0x14001401b  pop     r12
0x14001401d  pop     rdi
0x14001401e  pop     rsi
0x14001401f  pop     rbp
0x140014020  pop     rbx
0x140014021  retn
```
