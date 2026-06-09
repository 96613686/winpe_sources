# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180010cb0`
- end: `0x180010de6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180011138`

## callees

- `0x180004b78`
- `0x180009454`
- `0x1800094cc`
- `0x18000e730`
- `0x180010170`
- `0x180010190`
- `0x180010cb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010d5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010d5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010d6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010d6d`

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
0x180010cb0  push    rbx
0x180010cb2  push    rbp
0x180010cb3  push    rsi
0x180010cb4  push    rdi
0x180010cb5  push    r12
0x180010cb7  push    r13
0x180010cb9  push    r14
0x180010cbb  push    r15
0x180010cbd  sub     rsp, 28h
0x180010cc1  mov     [rcx+4], r8d
0x180010cc5  lea     r14, [rcx+38h]
0x180010cc9  mov     eax, [rdx+8]
0x180010ccc  mov     rsi, rcx
0x180010ccf  mov     [rcx+8], eax
0x180010cd2  mov     r15, rdx
0x180010cd5  mov     qword ptr [rcx+10h], 0
0x180010cdd  movzx   eax, word ptr [rdx+40h]
0x180010ce1  mov     [rcx+18h], ax
0x180010ce5  mov     al, [rdx]
0x180010ce7  mov     [rcx+1Ah], al
0x180010cea  mov     qword ptr [rcx+20h], 0
0x180010cf2  mov     rax, [rdx+88h]
0x180010cf9  mov     [rcx+28h], rax
0x180010cfd  mov     rax, [rdx+90h]
0x180010d04  mov     [rcx+30h], rax
0x180010d08  mov     qword ptr [r14], 0
0x180010d0f  mov     rcx, [rdx+18h]; this
0x180010d13  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180010d18  mov     rcx, [r15+38h]; this
0x180010d1c  mov     rbp, rax
0x180010d1f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180010d24  mov     rcx, [r15+80h]; this
0x180010d2b  add     rbp, rax
0x180010d2e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180010d33  add     rbp, rax
0x180010d36  lea     rdi, [rsi+48h]
0x180010d3a  cmp     qword ptr [rsi+40h], 0
0x180010d3f  jz      short loc_180010D46
0x180010d41  cmp     [rdi], rbp
0x180010d44  jnb     short loc_180010D7E
0x180010d46  mov     rdx, rbp; dwBytes
0x180010d49  mov     ecx, 8; dwFlags
0x180010d4e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010d53  mov     r14, rax
0x180010d56  test    rax, rax
0x180010d59  jz      short loc_180010D7A
0x180010d5b  mov     rbx, [rsi+40h]
0x180010d5f  call    cs:__imp_GetProcessHeap
0x180010d65  mov     r8, rbx; lpMem
0x180010d68  xor     edx, edx; dwFlags
0x180010d6a  mov     rcx, rax; hHeap
0x180010d6d  call    cs:__imp_HeapFree
0x180010d73  mov     [rsi+40h], r14
0x180010d77  mov     [rdi], rbp
0x180010d7a  lea     r14, [rsi+38h]
0x180010d7e  mov     rcx, [rsi+40h]; Destination
0x180010d82  test    rcx, rcx
0x180010d85  jz      short loc_180010DD5
0x180010d87  mov     rbx, [rdi]
0x180010d8a  lea     r9, [rsi+10h]
0x180010d8e  mov     r8, [r15+38h]
0x180010d92  add     rbx, rcx
0x180010d95  mov     rdx, rbx
0x180010d98  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180010d9d  mov     r8, [r15+80h]
0x180010da4  lea     r9, [rsi+20h]
0x180010da8  mov     rdx, rbx
0x180010dab  mov     rcx, rax; Destination
0x180010dae  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180010db3  mov     r8, [r15+18h]
0x180010db7  mov     r9, r14
0x180010dba  mov     rdx, rbx
0x180010dbd  mov     rcx, rax; Destination
0x180010dc0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180010dc5  sub     rbx, rax
0x180010dc8  xor     edx, edx; Val
0x180010dca  mov     r8, rbx; Size
0x180010dcd  mov     rcx, rax; void *
0x180010dd0  call    memset_0
0x180010dd5  add     rsp, 28h
0x180010dd9  pop     r15
0x180010ddb  pop     r14
0x180010ddd  pop     r13
0x180010ddf  pop     r12
0x180010de1  pop     rdi
0x180010de2  pop     rsi
0x180010de3  pop     rbp
0x180010de4  pop     rbx
0x180010de5  retn
```
