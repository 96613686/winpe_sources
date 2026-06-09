# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001aa3c`
- end: `0x18001abad`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001abb4`

## callees

- `0x18001878c`
- `0x18001a760`
- `0x18001a96c`
- `0x18001a98c`
- `0x18001aa3c`
- `0x18001b94e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001ab71`
- `msvcrt!memcpy_s` at `0x18001ab71`
- `KERNEL32!HeapFree` at `0x18001aaf2`
- `KERNEL32!HeapFree` at `0x18001aaf2`
- `KERNEL32!GetProcessHeap` at `0x18001aae4`
- `KERNEL32!GetProcessHeap` at `0x18001aae4`

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
0x18001aa3c  push    rbx
0x18001aa3e  push    rbp
0x18001aa3f  push    rsi
0x18001aa40  push    rdi
0x18001aa41  push    r12
0x18001aa43  push    r13
0x18001aa45  push    r14
0x18001aa47  push    r15
0x18001aa49  sub     rsp, 28h
0x18001aa4d  mov     [rcx+4], r8d
0x18001aa51  lea     rbx, [rcx+20h]
0x18001aa55  mov     eax, [rdx+8]
0x18001aa58  lea     rsi, [rcx+38h]
0x18001aa5c  mov     [rcx+8], eax
0x18001aa5f  xor     r12d, r12d
0x18001aa62  mov     [rcx+10h], r12
0x18001aa66  mov     rbp, rcx
0x18001aa69  movzx   eax, word ptr [rdx+40h]
0x18001aa6d  mov     r14, rdx
0x18001aa70  mov     [rcx+18h], ax
0x18001aa74  mov     al, [rdx]
0x18001aa76  mov     [rcx+1Ah], al
0x18001aa79  mov     [rbx], r12
0x18001aa7c  mov     rax, [rdx+88h]
0x18001aa83  mov     [rcx+28h], rax
0x18001aa87  mov     rax, [rdx+90h]
0x18001aa8e  mov     [rcx+30h], rax
0x18001aa92  mov     [rsi], r12
0x18001aa95  mov     rcx, [rdx+18h]; this
0x18001aa99  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001aa9e  mov     rcx, [r14+38h]; this
0x18001aaa2  mov     r15, rax
0x18001aaa5  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001aaaa  mov     rcx, [r14+80h]; this
0x18001aab1  add     r15, rax
0x18001aab4  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001aab9  add     r15, rax
0x18001aabc  lea     rdi, [rbp+48h]
0x18001aac0  cmp     [rbp+40h], r12
0x18001aac4  jz      short loc_18001AACB
0x18001aac6  cmp     [rdi], r15
0x18001aac9  jnb     short loc_18001AB06
0x18001aacb  mov     rdx, r15; dwBytes
0x18001aace  mov     ecx, 8; dwFlags
0x18001aad3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001aad8  mov     r12, rax
0x18001aadb  test    rax, rax
0x18001aade  jz      short loc_18001AB03
0x18001aae0  mov     rbx, [rbp+40h]
0x18001aae4  call    cs:__imp_GetProcessHeap
0x18001aaea  mov     r8, rbx; lpMem
0x18001aaed  xor     edx, edx; dwFlags
0x18001aaef  mov     rcx, rax; hHeap
0x18001aaf2  call    cs:__imp_HeapFree
0x18001aaf8  mov     [rbp+40h], r12
0x18001aafc  lea     rbx, [rbp+20h]
0x18001ab00  mov     [rdi], r15
0x18001ab03  xor     r12d, r12d
0x18001ab06  mov     rcx, [rbp+40h]; Destination
0x18001ab0a  test    rcx, rcx
0x18001ab0d  jz      loc_18001AB9C
0x18001ab13  mov     rdi, [rdi]
0x18001ab16  lea     r9, [rbp+10h]
0x18001ab1a  mov     r8, [r14+38h]
0x18001ab1e  add     rdi, rcx
0x18001ab21  mov     rdx, rdi
0x18001ab24  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001ab29  mov     r8, [r14+80h]
0x18001ab30  mov     r9, rbx
0x18001ab33  mov     rdx, rdi
0x18001ab36  mov     rcx, rax; Destination
0x18001ab39  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001ab3e  mov     rbx, rax
0x18001ab41  cmp     rax, rdi
0x18001ab44  jz      short loc_18001AB84
0x18001ab46  mov     rcx, [r14+18h]; this
0x18001ab4a  test    rcx, rcx
0x18001ab4d  jz      short loc_18001AB84
0x18001ab4f  cmp     [rcx], r12w
0x18001ab53  jz      short loc_18001AB84
0x18001ab55  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001ab5a  mov     rdx, rdi
0x18001ab5d  mov     r14, rax
0x18001ab60  sub     rdx, rbx; DestinationSize
0x18001ab63  cmp     rdx, rax
0x18001ab66  jb      short loc_18001AB84
0x18001ab68  mov     r8, rcx; Source
0x18001ab6b  mov     r9, rax; SourceSize
0x18001ab6e  mov     rcx, rbx; Destination
0x18001ab71  call    cs:__imp_memcpy_s
0x18001ab77  test    rsi, rsi
0x18001ab7a  jz      short loc_18001AB7F
0x18001ab7c  mov     [rsi], rbx
0x18001ab7f  add     rbx, r14
0x18001ab82  jmp     short loc_18001AB8C
0x18001ab84  test    rsi, rsi
0x18001ab87  jz      short loc_18001AB8C
0x18001ab89  mov     [rsi], r12
0x18001ab8c  sub     rdi, rbx
0x18001ab8f  xor     edx, edx; Val
0x18001ab91  mov     r8, rdi; Size
0x18001ab94  mov     rcx, rbx; void *
0x18001ab97  call    memset_0
0x18001ab9c  add     rsp, 28h
0x18001aba0  pop     r15
0x18001aba2  pop     r14
0x18001aba4  pop     r13
0x18001aba6  pop     r12
0x18001aba8  pop     rdi
0x18001aba9  pop     rsi
0x18001abaa  pop     rbp
0x18001abab  pop     rbx
0x18001abac  retn
```
