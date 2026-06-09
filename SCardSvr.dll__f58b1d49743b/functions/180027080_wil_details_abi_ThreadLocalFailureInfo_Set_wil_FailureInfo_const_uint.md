# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180027080`
- end: `0x1800271b6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180027504`

## callees

- `0x180023282`
- `0x180023bcc`
- `0x180023c44`
- `0x1800263c4`
- `0x180026f18`
- `0x180026f38`
- `0x180027080`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002713d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002713d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002712f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002712f`

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
0x180027080  push    rbx
0x180027082  push    rbp
0x180027083  push    rsi
0x180027084  push    rdi
0x180027085  push    r12
0x180027087  push    r13
0x180027089  push    r14
0x18002708b  push    r15
0x18002708d  sub     rsp, 28h
0x180027091  mov     [rcx+4], r8d
0x180027095  lea     r14, [rcx+38h]
0x180027099  mov     eax, [rdx+8]
0x18002709c  mov     rsi, rcx
0x18002709f  mov     [rcx+8], eax
0x1800270a2  mov     r15, rdx
0x1800270a5  mov     qword ptr [rcx+10h], 0
0x1800270ad  movzx   eax, word ptr [rdx+40h]
0x1800270b1  mov     [rcx+18h], ax
0x1800270b5  mov     al, [rdx]
0x1800270b7  mov     [rcx+1Ah], al
0x1800270ba  mov     qword ptr [rcx+20h], 0
0x1800270c2  mov     rax, [rdx+88h]
0x1800270c9  mov     [rcx+28h], rax
0x1800270cd  mov     rax, [rdx+90h]
0x1800270d4  mov     [rcx+30h], rax
0x1800270d8  mov     qword ptr [r14], 0
0x1800270df  mov     rcx, [rdx+18h]; this
0x1800270e3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800270e8  mov     rcx, [r15+38h]; this
0x1800270ec  mov     rbp, rax
0x1800270ef  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800270f4  mov     rcx, [r15+80h]; this
0x1800270fb  add     rbp, rax
0x1800270fe  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180027103  add     rbp, rax
0x180027106  lea     rdi, [rsi+48h]
0x18002710a  cmp     qword ptr [rsi+40h], 0
0x18002710f  jz      short loc_180027116
0x180027111  cmp     [rdi], rbp
0x180027114  jnb     short loc_18002714E
0x180027116  mov     rdx, rbp; dwBytes
0x180027119  mov     ecx, 8; dwFlags
0x18002711e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180027123  mov     r14, rax
0x180027126  test    rax, rax
0x180027129  jz      short loc_18002714A
0x18002712b  mov     rbx, [rsi+40h]
0x18002712f  call    cs:__imp_GetProcessHeap
0x180027135  mov     r8, rbx; lpMem
0x180027138  xor     edx, edx; dwFlags
0x18002713a  mov     rcx, rax; hHeap
0x18002713d  call    cs:__imp_HeapFree
0x180027143  mov     [rsi+40h], r14
0x180027147  mov     [rdi], rbp
0x18002714a  lea     r14, [rsi+38h]
0x18002714e  mov     rcx, [rsi+40h]; Destination
0x180027152  test    rcx, rcx
0x180027155  jz      short loc_1800271A5
0x180027157  mov     rbx, [rdi]
0x18002715a  lea     r9, [rsi+10h]
0x18002715e  mov     r8, [r15+38h]
0x180027162  add     rbx, rcx
0x180027165  mov     rdx, rbx
0x180027168  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002716d  mov     r8, [r15+80h]
0x180027174  lea     r9, [rsi+20h]
0x180027178  mov     rdx, rbx
0x18002717b  mov     rcx, rax; Destination
0x18002717e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180027183  mov     r8, [r15+18h]
0x180027187  mov     r9, r14
0x18002718a  mov     rdx, rbx
0x18002718d  mov     rcx, rax; Destination
0x180027190  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180027195  sub     rbx, rax
0x180027198  xor     edx, edx; Val
0x18002719a  mov     r8, rbx; Size
0x18002719d  mov     rcx, rax; void *
0x1800271a0  call    memset_0
0x1800271a5  add     rsp, 28h
0x1800271a9  pop     r15
0x1800271ab  pop     r14
0x1800271ad  pop     r13
0x1800271af  pop     r12
0x1800271b1  pop     rdi
0x1800271b2  pop     rsi
0x1800271b3  pop     rbp
0x1800271b4  pop     rbx
0x1800271b5  retn
```
