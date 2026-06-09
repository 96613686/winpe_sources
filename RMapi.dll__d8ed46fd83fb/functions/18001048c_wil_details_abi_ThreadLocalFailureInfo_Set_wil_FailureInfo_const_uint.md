# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001048c`
- end: `0x1800105c2`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800105c8`

## callees

- `0x180008cc0`
- `0x180009020`
- `0x18000c1ac`
- `0x18000df4c`
- `0x18000e354`
- `0x1800102ac`
- `0x18001048c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001053b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001053b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010549`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010549`

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
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const wchar_t *)a2);
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
    v18 = (void *)wil::details::WriteResultString<wchar_t const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x18001048c  push    rbx
0x18001048e  push    rbp
0x18001048f  push    rsi
0x180010490  push    rdi
0x180010491  push    r12
0x180010493  push    r13
0x180010495  push    r14
0x180010497  push    r15
0x180010499  sub     rsp, 28h
0x18001049d  mov     [rcx+4], r8d
0x1800104a1  lea     r14, [rcx+38h]
0x1800104a5  mov     eax, [rdx+8]
0x1800104a8  mov     rsi, rcx
0x1800104ab  mov     [rcx+8], eax
0x1800104ae  mov     r15, rdx
0x1800104b1  mov     qword ptr [rcx+10h], 0
0x1800104b9  movzx   eax, word ptr [rdx+40h]
0x1800104bd  mov     [rcx+18h], ax
0x1800104c1  mov     al, [rdx]
0x1800104c3  mov     [rcx+1Ah], al
0x1800104c6  mov     qword ptr [rcx+20h], 0
0x1800104ce  mov     rax, [rdx+88h]
0x1800104d5  mov     [rcx+28h], rax
0x1800104d9  mov     rax, [rdx+90h]
0x1800104e0  mov     [rcx+30h], rax
0x1800104e4  mov     qword ptr [r14], 0
0x1800104eb  mov     rcx, [rdx+18h]; this
0x1800104ef  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x1800104f4  mov     rcx, [r15+38h]; this
0x1800104f8  mov     rbp, rax
0x1800104fb  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180010500  mov     rcx, [r15+80h]; this
0x180010507  add     rbp, rax
0x18001050a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001050f  add     rbp, rax
0x180010512  lea     rdi, [rsi+48h]
0x180010516  cmp     qword ptr [rsi+40h], 0
0x18001051b  jz      short loc_180010522
0x18001051d  cmp     [rdi], rbp
0x180010520  jnb     short loc_18001055A
0x180010522  mov     rdx, rbp; dwBytes
0x180010525  mov     ecx, 8; dwFlags
0x18001052a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001052f  mov     r14, rax
0x180010532  test    rax, rax
0x180010535  jz      short loc_180010556
0x180010537  mov     rbx, [rsi+40h]
0x18001053b  call    cs:__imp_GetProcessHeap
0x180010541  mov     r8, rbx; lpMem
0x180010544  xor     edx, edx; dwFlags
0x180010546  mov     rcx, rax; hHeap
0x180010549  call    cs:__imp_HeapFree
0x18001054f  mov     [rsi+40h], r14
0x180010553  mov     [rdi], rbp
0x180010556  lea     r14, [rsi+38h]
0x18001055a  mov     rcx, [rsi+40h]; Destination
0x18001055e  test    rcx, rcx
0x180010561  jz      short loc_1800105B1
0x180010563  mov     rbx, [rdi]
0x180010566  lea     r9, [rsi+10h]
0x18001056a  mov     r8, [r15+38h]
0x18001056e  add     rbx, rcx
0x180010571  mov     rdx, rbx
0x180010574  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180010579  mov     r8, [r15+80h]
0x180010580  lea     r9, [rsi+20h]
0x180010584  mov     rdx, rbx
0x180010587  mov     rcx, rax; Destination
0x18001058a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001058f  mov     r8, [r15+18h]
0x180010593  mov     r9, r14
0x180010596  mov     rdx, rbx
0x180010599  mov     rcx, rax; Destination
0x18001059c  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x1800105a1  sub     rbx, rax
0x1800105a4  xor     edx, edx; Val
0x1800105a6  mov     r8, rbx; Size
0x1800105a9  mov     rcx, rax; void *
0x1800105ac  call    memset_0
0x1800105b1  add     rsp, 28h
0x1800105b5  pop     r15
0x1800105b7  pop     r14
0x1800105b9  pop     r13
0x1800105bb  pop     r12
0x1800105bd  pop     rdi
0x1800105be  pop     rsi
0x1800105bf  pop     rbp
0x1800105c0  pop     rbx
0x1800105c1  retn
```
