# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000e7a8`
- end: `0x18000e8de`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000e92c`

## callees

- `0x180002b78`
- `0x1800035d8`
- `0x180003650`
- `0x180004d88`
- `0x180004da8`
- `0x18000decc`
- `0x18000e7a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e865`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e865`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e857`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e857`

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
0x18000e7a8  push    rbx
0x18000e7aa  push    rbp
0x18000e7ab  push    rsi
0x18000e7ac  push    rdi
0x18000e7ad  push    r12
0x18000e7af  push    r13
0x18000e7b1  push    r14
0x18000e7b3  push    r15
0x18000e7b5  sub     rsp, 28h
0x18000e7b9  mov     [rcx+4], r8d
0x18000e7bd  lea     r14, [rcx+38h]
0x18000e7c1  mov     eax, [rdx+8]
0x18000e7c4  mov     rsi, rcx
0x18000e7c7  mov     [rcx+8], eax
0x18000e7ca  mov     r15, rdx
0x18000e7cd  mov     qword ptr [rcx+10h], 0
0x18000e7d5  movzx   eax, word ptr [rdx+40h]
0x18000e7d9  mov     [rcx+18h], ax
0x18000e7dd  mov     al, [rdx]
0x18000e7df  mov     [rcx+1Ah], al
0x18000e7e2  mov     qword ptr [rcx+20h], 0
0x18000e7ea  mov     rax, [rdx+88h]
0x18000e7f1  mov     [rcx+28h], rax
0x18000e7f5  mov     rax, [rdx+90h]
0x18000e7fc  mov     [rcx+30h], rax
0x18000e800  mov     qword ptr [r14], 0
0x18000e807  mov     rcx, [rdx+18h]; this
0x18000e80b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000e810  mov     rcx, [r15+38h]; this
0x18000e814  mov     rbp, rax
0x18000e817  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000e81c  mov     rcx, [r15+80h]; this
0x18000e823  add     rbp, rax
0x18000e826  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000e82b  add     rbp, rax
0x18000e82e  lea     rdi, [rsi+48h]
0x18000e832  cmp     qword ptr [rsi+40h], 0
0x18000e837  jz      short loc_18000E83E
0x18000e839  cmp     [rdi], rbp
0x18000e83c  jnb     short loc_18000E876
0x18000e83e  mov     rdx, rbp; dwBytes
0x18000e841  mov     ecx, 8; dwFlags
0x18000e846  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000e84b  mov     r14, rax
0x18000e84e  test    rax, rax
0x18000e851  jz      short loc_18000E872
0x18000e853  mov     rbx, [rsi+40h]
0x18000e857  call    cs:__imp_GetProcessHeap
0x18000e85d  mov     r8, rbx; lpMem
0x18000e860  xor     edx, edx; dwFlags
0x18000e862  mov     rcx, rax; hHeap
0x18000e865  call    cs:__imp_HeapFree
0x18000e86b  mov     [rsi+40h], r14
0x18000e86f  mov     [rdi], rbp
0x18000e872  lea     r14, [rsi+38h]
0x18000e876  mov     rcx, [rsi+40h]; Destination
0x18000e87a  test    rcx, rcx
0x18000e87d  jz      short loc_18000E8CD
0x18000e87f  mov     rbx, [rdi]
0x18000e882  lea     r9, [rsi+10h]
0x18000e886  mov     r8, [r15+38h]
0x18000e88a  add     rbx, rcx
0x18000e88d  mov     rdx, rbx
0x18000e890  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000e895  mov     r8, [r15+80h]
0x18000e89c  lea     r9, [rsi+20h]
0x18000e8a0  mov     rdx, rbx
0x18000e8a3  mov     rcx, rax; Destination
0x18000e8a6  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000e8ab  mov     r8, [r15+18h]
0x18000e8af  mov     r9, r14
0x18000e8b2  mov     rdx, rbx
0x18000e8b5  mov     rcx, rax; Destination
0x18000e8b8  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000e8bd  sub     rbx, rax
0x18000e8c0  xor     edx, edx; Val
0x18000e8c2  mov     r8, rbx; Size
0x18000e8c5  mov     rcx, rax; void *
0x18000e8c8  call    memset_0
0x18000e8cd  add     rsp, 28h
0x18000e8d1  pop     r15
0x18000e8d3  pop     r14
0x18000e8d5  pop     r13
0x18000e8d7  pop     r12
0x18000e8d9  pop     rdi
0x18000e8da  pop     rsi
0x18000e8db  pop     rbp
0x18000e8dc  pop     rbx
0x18000e8dd  retn
```
