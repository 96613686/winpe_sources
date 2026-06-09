# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009120`
- end: `0x180009256`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800095b4`

## callees

- `0x180003bc8`
- `0x180004ce8`
- `0x180004d60`
- `0x18000819c`
- `0x180008f98`
- `0x180008fb8`
- `0x180009120`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091cf`

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
0x180009120  push    rbx
0x180009122  push    rbp
0x180009123  push    rsi
0x180009124  push    rdi
0x180009125  push    r12
0x180009127  push    r13
0x180009129  push    r14
0x18000912b  push    r15
0x18000912d  sub     rsp, 28h
0x180009131  mov     [rcx+4], r8d
0x180009135  lea     r14, [rcx+38h]
0x180009139  mov     eax, [rdx+8]
0x18000913c  mov     rsi, rcx
0x18000913f  mov     [rcx+8], eax
0x180009142  mov     r15, rdx
0x180009145  mov     qword ptr [rcx+10h], 0
0x18000914d  movzx   eax, word ptr [rdx+40h]
0x180009151  mov     [rcx+18h], ax
0x180009155  mov     al, [rdx]
0x180009157  mov     [rcx+1Ah], al
0x18000915a  mov     qword ptr [rcx+20h], 0
0x180009162  mov     rax, [rdx+88h]
0x180009169  mov     [rcx+28h], rax
0x18000916d  mov     rax, [rdx+90h]
0x180009174  mov     [rcx+30h], rax
0x180009178  mov     qword ptr [r14], 0
0x18000917f  mov     rcx, [rdx+18h]; this
0x180009183  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180009188  mov     rcx, [r15+38h]; this
0x18000918c  mov     rbp, rax
0x18000918f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180009194  mov     rcx, [r15+80h]; this
0x18000919b  add     rbp, rax
0x18000919e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800091a3  add     rbp, rax
0x1800091a6  lea     rdi, [rsi+48h]
0x1800091aa  cmp     qword ptr [rsi+40h], 0
0x1800091af  jz      short loc_1800091B6
0x1800091b1  cmp     [rdi], rbp
0x1800091b4  jnb     short loc_1800091EE
0x1800091b6  mov     rdx, rbp; dwBytes
0x1800091b9  mov     ecx, 8; dwFlags
0x1800091be  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800091c3  mov     r14, rax
0x1800091c6  test    rax, rax
0x1800091c9  jz      short loc_1800091EA
0x1800091cb  mov     rbx, [rsi+40h]
0x1800091cf  call    cs:__imp_GetProcessHeap
0x1800091d5  mov     r8, rbx; lpMem
0x1800091d8  xor     edx, edx; dwFlags
0x1800091da  mov     rcx, rax; hHeap
0x1800091dd  call    cs:__imp_HeapFree
0x1800091e3  mov     [rsi+40h], r14
0x1800091e7  mov     [rdi], rbp
0x1800091ea  lea     r14, [rsi+38h]
0x1800091ee  mov     rcx, [rsi+40h]; Destination
0x1800091f2  test    rcx, rcx
0x1800091f5  jz      short loc_180009245
0x1800091f7  mov     rbx, [rdi]
0x1800091fa  lea     r9, [rsi+10h]
0x1800091fe  mov     r8, [r15+38h]
0x180009202  add     rbx, rcx
0x180009205  mov     rdx, rbx
0x180009208  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000920d  mov     r8, [r15+80h]
0x180009214  lea     r9, [rsi+20h]
0x180009218  mov     rdx, rbx
0x18000921b  mov     rcx, rax; Destination
0x18000921e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009223  mov     r8, [r15+18h]
0x180009227  mov     r9, r14
0x18000922a  mov     rdx, rbx
0x18000922d  mov     rcx, rax; Destination
0x180009230  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180009235  sub     rbx, rax
0x180009238  xor     edx, edx; Val
0x18000923a  mov     r8, rbx; Size
0x18000923d  mov     rcx, rax; void *
0x180009240  call    memset_0
0x180009245  add     rsp, 28h
0x180009249  pop     r15
0x18000924b  pop     r14
0x18000924d  pop     r13
0x18000924f  pop     r12
0x180009251  pop     rdi
0x180009252  pop     rsi
0x180009253  pop     rbp
0x180009254  pop     rbx
0x180009255  retn
```
