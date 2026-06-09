# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008860`
- end: `0x180008996`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008ce4`

## callees

- `0x180002b28`
- `0x1800046e8`
- `0x180004760`
- `0x180007590`
- `0x1800086d8`
- `0x1800086f8`
- `0x180008860`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000890f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000890f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000891d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000891d`

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
0x180008860  push    rbx
0x180008862  push    rbp
0x180008863  push    rsi
0x180008864  push    rdi
0x180008865  push    r12
0x180008867  push    r13
0x180008869  push    r14
0x18000886b  push    r15
0x18000886d  sub     rsp, 28h
0x180008871  mov     [rcx+4], r8d
0x180008875  lea     r14, [rcx+38h]
0x180008879  mov     eax, [rdx+8]
0x18000887c  mov     rsi, rcx
0x18000887f  mov     [rcx+8], eax
0x180008882  mov     r15, rdx
0x180008885  mov     qword ptr [rcx+10h], 0
0x18000888d  movzx   eax, word ptr [rdx+40h]
0x180008891  mov     [rcx+18h], ax
0x180008895  mov     al, [rdx]
0x180008897  mov     [rcx+1Ah], al
0x18000889a  mov     qword ptr [rcx+20h], 0
0x1800088a2  mov     rax, [rdx+88h]
0x1800088a9  mov     [rcx+28h], rax
0x1800088ad  mov     rax, [rdx+90h]
0x1800088b4  mov     [rcx+30h], rax
0x1800088b8  mov     qword ptr [r14], 0
0x1800088bf  mov     rcx, [rdx+18h]; this
0x1800088c3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800088c8  mov     rcx, [r15+38h]; this
0x1800088cc  mov     rbp, rax
0x1800088cf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800088d4  mov     rcx, [r15+80h]; this
0x1800088db  add     rbp, rax
0x1800088de  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800088e3  add     rbp, rax
0x1800088e6  lea     rdi, [rsi+48h]
0x1800088ea  cmp     qword ptr [rsi+40h], 0
0x1800088ef  jz      short loc_1800088F6
0x1800088f1  cmp     [rdi], rbp
0x1800088f4  jnb     short loc_18000892E
0x1800088f6  mov     rdx, rbp; dwBytes
0x1800088f9  mov     ecx, 8; dwFlags
0x1800088fe  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008903  mov     r14, rax
0x180008906  test    rax, rax
0x180008909  jz      short loc_18000892A
0x18000890b  mov     rbx, [rsi+40h]
0x18000890f  call    cs:__imp_GetProcessHeap
0x180008915  mov     r8, rbx; lpMem
0x180008918  xor     edx, edx; dwFlags
0x18000891a  mov     rcx, rax; hHeap
0x18000891d  call    cs:__imp_HeapFree
0x180008923  mov     [rsi+40h], r14
0x180008927  mov     [rdi], rbp
0x18000892a  lea     r14, [rsi+38h]
0x18000892e  mov     rcx, [rsi+40h]; Destination
0x180008932  test    rcx, rcx
0x180008935  jz      short loc_180008985
0x180008937  mov     rbx, [rdi]
0x18000893a  lea     r9, [rsi+10h]
0x18000893e  mov     r8, [r15+38h]
0x180008942  add     rbx, rcx
0x180008945  mov     rdx, rbx
0x180008948  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000894d  mov     r8, [r15+80h]
0x180008954  lea     r9, [rsi+20h]
0x180008958  mov     rdx, rbx
0x18000895b  mov     rcx, rax; Destination
0x18000895e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180008963  mov     r8, [r15+18h]
0x180008967  mov     r9, r14
0x18000896a  mov     rdx, rbx
0x18000896d  mov     rcx, rax; Destination
0x180008970  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180008975  sub     rbx, rax
0x180008978  xor     edx, edx; Val
0x18000897a  mov     r8, rbx; Size
0x18000897d  mov     rcx, rax; void *
0x180008980  call    memset_0
0x180008985  add     rsp, 28h
0x180008989  pop     r15
0x18000898b  pop     r14
0x18000898d  pop     r13
0x18000898f  pop     r12
0x180008991  pop     rdi
0x180008992  pop     rsi
0x180008993  pop     rbp
0x180008994  pop     rbx
0x180008995  retn
```
