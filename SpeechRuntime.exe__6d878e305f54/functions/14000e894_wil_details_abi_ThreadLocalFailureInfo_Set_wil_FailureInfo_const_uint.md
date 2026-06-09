# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000e894`
- end: `0x14000e9ca`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000ec2c`

## callees

- `0x140003848`
- `0x140007180`
- `0x1400071f8`
- `0x14000d2fc`
- `0x14000dfc8`
- `0x14000dfe8`
- `0x14000e894`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e943`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e943`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e951`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e951`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int64 v5; // rbp
  const char *v6; // rdx
  unsigned __int64 v7; // rbp
  const char *v8; // rdx
  SIZE_T v9; // rbp
  SIZE_T *v10; // rdi
  LPVOID v11; // r14
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  char *v14; // rcx
  char *v15; // rbx
  void *v16; // rax
  void *v17; // rax
  void *v18; // rax

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v6) + v5;
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v8) + v7;
  v10 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v10 < v9 )
  {
    v11 = wil::details::ProcessHeapAlloc(8u, v9);
    if ( v11 )
    {
      v12 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
      *((_QWORD *)this + 8) = v11;
      *v10 = v9;
    }
  }
  v14 = (char *)*((_QWORD *)this + 8);
  if ( v14 )
  {
    v15 = &v14[*v10];
    v16 = (void *)wil::details::WriteResultString<char const *>(v14);
    v17 = (void *)wil::details::WriteResultString<char const *>(v16);
    v18 = (void *)wil::details::WriteResultString<unsigned short const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x14000e894  push    rbx
0x14000e896  push    rbp
0x14000e897  push    rsi
0x14000e898  push    rdi
0x14000e899  push    r12
0x14000e89b  push    r13
0x14000e89d  push    r14
0x14000e89f  push    r15
0x14000e8a1  sub     rsp, 28h
0x14000e8a5  mov     [rcx+4], r8d
0x14000e8a9  lea     r14, [rcx+38h]
0x14000e8ad  mov     eax, [rdx+8]
0x14000e8b0  mov     rsi, rcx
0x14000e8b3  mov     [rcx+8], eax
0x14000e8b6  mov     r15, rdx
0x14000e8b9  mov     qword ptr [rcx+10h], 0
0x14000e8c1  movzx   eax, word ptr [rdx+40h]
0x14000e8c5  mov     [rcx+18h], ax
0x14000e8c9  mov     al, [rdx]
0x14000e8cb  mov     [rcx+1Ah], al
0x14000e8ce  mov     qword ptr [rcx+20h], 0
0x14000e8d6  mov     rax, [rdx+88h]
0x14000e8dd  mov     [rcx+28h], rax
0x14000e8e1  mov     rax, [rdx+90h]
0x14000e8e8  mov     [rcx+30h], rax
0x14000e8ec  mov     qword ptr [r14], 0
0x14000e8f3  mov     rcx, [rdx+18h]; this
0x14000e8f7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x14000e8fc  mov     rcx, [r15+38h]; this
0x14000e900  mov     rbp, rax
0x14000e903  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14000e908  mov     rcx, [r15+80h]; this
0x14000e90f  add     rbp, rax
0x14000e912  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14000e917  add     rbp, rax
0x14000e91a  lea     rdi, [rsi+48h]
0x14000e91e  cmp     qword ptr [rsi+40h], 0
0x14000e923  jz      short loc_14000E92A
0x14000e925  cmp     [rdi], rbp
0x14000e928  jnb     short loc_14000E962
0x14000e92a  mov     rdx, rbp; dwBytes
0x14000e92d  mov     ecx, 8; dwFlags
0x14000e932  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000e937  mov     r14, rax
0x14000e93a  test    rax, rax
0x14000e93d  jz      short loc_14000E95E
0x14000e93f  mov     rbx, [rsi+40h]
0x14000e943  call    cs:__imp_GetProcessHeap
0x14000e949  mov     r8, rbx; lpMem
0x14000e94c  xor     edx, edx; dwFlags
0x14000e94e  mov     rcx, rax; hHeap
0x14000e951  call    cs:__imp_HeapFree
0x14000e957  mov     [rsi+40h], r14
0x14000e95b  mov     [rdi], rbp
0x14000e95e  lea     r14, [rsi+38h]
0x14000e962  mov     rcx, [rsi+40h]; Destination
0x14000e966  test    rcx, rcx
0x14000e969  jz      short loc_14000E9B9
0x14000e96b  mov     rbx, [rdi]
0x14000e96e  lea     r9, [rsi+10h]
0x14000e972  mov     r8, [r15+38h]
0x14000e976  add     rbx, rcx
0x14000e979  mov     rdx, rbx
0x14000e97c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000e981  mov     r8, [r15+80h]
0x14000e988  lea     r9, [rsi+20h]
0x14000e98c  mov     rdx, rbx
0x14000e98f  mov     rcx, rax; Destination
0x14000e992  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000e997  mov     r8, [r15+18h]
0x14000e99b  mov     r9, r14
0x14000e99e  mov     rdx, rbx
0x14000e9a1  mov     rcx, rax; Destination
0x14000e9a4  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x14000e9a9  sub     rbx, rax
0x14000e9ac  xor     edx, edx; Val
0x14000e9ae  mov     r8, rbx; Size
0x14000e9b1  mov     rcx, rax; void *
0x14000e9b4  call    memset_0
0x14000e9b9  add     rsp, 28h
0x14000e9bd  pop     r15
0x14000e9bf  pop     r14
0x14000e9c1  pop     r13
0x14000e9c3  pop     r12
0x14000e9c5  pop     rdi
0x14000e9c6  pop     rsi
0x14000e9c7  pop     rbp
0x14000e9c8  pop     rbx
0x14000e9c9  retn
```
