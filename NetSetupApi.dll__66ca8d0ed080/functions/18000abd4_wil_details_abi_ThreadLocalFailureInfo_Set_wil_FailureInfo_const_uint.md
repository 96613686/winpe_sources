# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000abd4`
- end: `0x18000ad0a`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ad10`

## callees

- `0x180005a44`
- `0x180007404`
- `0x180007458`
- `0x180009240`
- `0x18000a8fc`
- `0x18000abd4`
- `0x1800119c2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ac91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ac91`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  wchar_t **v3; // r14
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
  char *v18; // rax
  char *v19; // rax

  *((_DWORD *)this + 1) = a3;
  v3 = (wchar_t **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const wchar_t *)a2);
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
    v3 = (wchar_t **)((char *)this + 56);
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = wil::details::WriteResultString<char const *>(v15, v16, *((wil::details **)a2 + 7), (char **)this + 2);
    v18 = wil::details::WriteResultString<char const *>(v17, v16, *((wil::details **)a2 + 16), (char **)this + 4);
    v19 = wil::details::WriteResultString<wchar_t const *>(
            (wchar_t *)v18,
            (const wchar_t *)v16,
            *((wil::details **)a2 + 3),
            v3);
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x18000abd4  push    rbx
0x18000abd6  push    rbp
0x18000abd7  push    rsi
0x18000abd8  push    rdi
0x18000abd9  push    r12
0x18000abdb  push    r13
0x18000abdd  push    r14
0x18000abdf  push    r15
0x18000abe1  sub     rsp, 28h
0x18000abe5  mov     [rcx+4], r8d
0x18000abe9  lea     r14, [rcx+38h]
0x18000abed  mov     eax, [rdx+8]
0x18000abf0  mov     rsi, rcx
0x18000abf3  mov     [rcx+8], eax
0x18000abf6  mov     r15, rdx
0x18000abf9  mov     qword ptr [rcx+10h], 0
0x18000ac01  movzx   eax, word ptr [rdx+40h]
0x18000ac05  mov     [rcx+18h], ax
0x18000ac09  mov     al, [rdx]
0x18000ac0b  mov     [rcx+1Ah], al
0x18000ac0e  mov     qword ptr [rcx+20h], 0
0x18000ac16  mov     rax, [rdx+88h]
0x18000ac1d  mov     [rcx+28h], rax
0x18000ac21  mov     rax, [rdx+90h]
0x18000ac28  mov     [rcx+30h], rax
0x18000ac2c  mov     qword ptr [r14], 0
0x18000ac33  mov     rcx, [rdx+18h]; this
0x18000ac37  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x18000ac3c  mov     rcx, [r15+38h]; this
0x18000ac40  mov     rbp, rax
0x18000ac43  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000ac48  mov     rcx, [r15+80h]; this
0x18000ac4f  add     rbp, rax
0x18000ac52  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000ac57  add     rbp, rax
0x18000ac5a  lea     rdi, [rsi+48h]
0x18000ac5e  cmp     qword ptr [rsi+40h], 0
0x18000ac63  jz      short loc_18000AC6A
0x18000ac65  cmp     [rdi], rbp
0x18000ac68  jnb     short loc_18000ACA2
0x18000ac6a  mov     rdx, rbp; dwBytes
0x18000ac6d  mov     ecx, 8; dwFlags
0x18000ac72  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ac77  mov     r14, rax
0x18000ac7a  test    rax, rax
0x18000ac7d  jz      short loc_18000AC9E
0x18000ac7f  mov     rbx, [rsi+40h]
0x18000ac83  call    cs:__imp_GetProcessHeap
0x18000ac89  mov     r8, rbx; lpMem
0x18000ac8c  xor     edx, edx; dwFlags
0x18000ac8e  mov     rcx, rax; hHeap
0x18000ac91  call    cs:__imp_HeapFree
0x18000ac97  mov     [rsi+40h], r14
0x18000ac9b  mov     [rdi], rbp
0x18000ac9e  lea     r14, [rsi+38h]
0x18000aca2  mov     rcx, [rsi+40h]; Destination
0x18000aca6  test    rcx, rcx
0x18000aca9  jz      short loc_18000ACF9
0x18000acab  mov     rbx, [rdi]
0x18000acae  lea     r9, [rsi+10h]
0x18000acb2  mov     r8, [r15+38h]
0x18000acb6  add     rbx, rcx
0x18000acb9  mov     rdx, rbx
0x18000acbc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000acc1  mov     r8, [r15+80h]
0x18000acc8  lea     r9, [rsi+20h]
0x18000accc  mov     rdx, rbx
0x18000accf  mov     rcx, rax; Destination
0x18000acd2  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000acd7  mov     r8, [r15+18h]
0x18000acdb  mov     r9, r14
0x18000acde  mov     rdx, rbx
0x18000ace1  mov     rcx, rax; Destination
0x18000ace4  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x18000ace9  sub     rbx, rax
0x18000acec  xor     edx, edx; Val
0x18000acee  mov     r8, rbx; Size
0x18000acf1  mov     rcx, rax; void *
0x18000acf4  call    memset_0
0x18000acf9  add     rsp, 28h
0x18000acfd  pop     r15
0x18000acff  pop     r14
0x18000ad01  pop     r13
0x18000ad03  pop     r12
0x18000ad05  pop     rdi
0x18000ad06  pop     rsi
0x18000ad07  pop     rbp
0x18000ad08  pop     rbx
0x18000ad09  retn
```
