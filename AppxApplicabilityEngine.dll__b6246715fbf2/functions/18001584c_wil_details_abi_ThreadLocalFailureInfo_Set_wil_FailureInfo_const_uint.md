# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001584c`
- end: `0x180015982`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180015be4`

## callees

- `0x180013f98`
- `0x180014010`
- `0x180015348`
- `0x1800156f0`
- `0x180015710`
- `0x18001584c`
- `0x180022792`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800158fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800158fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015909`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015909`

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
0x18001584c  push    rbx
0x18001584e  push    rbp
0x18001584f  push    rsi
0x180015850  push    rdi
0x180015851  push    r12
0x180015853  push    r13
0x180015855  push    r14
0x180015857  push    r15
0x180015859  sub     rsp, 28h
0x18001585d  mov     [rcx+4], r8d
0x180015861  lea     r14, [rcx+38h]
0x180015865  mov     eax, [rdx+8]
0x180015868  mov     rsi, rcx
0x18001586b  mov     [rcx+8], eax
0x18001586e  mov     r15, rdx
0x180015871  mov     qword ptr [rcx+10h], 0
0x180015879  movzx   eax, word ptr [rdx+40h]
0x18001587d  mov     [rcx+18h], ax
0x180015881  mov     al, [rdx]
0x180015883  mov     [rcx+1Ah], al
0x180015886  mov     qword ptr [rcx+20h], 0
0x18001588e  mov     rax, [rdx+88h]
0x180015895  mov     [rcx+28h], rax
0x180015899  mov     rax, [rdx+90h]
0x1800158a0  mov     [rcx+30h], rax
0x1800158a4  mov     qword ptr [r14], 0
0x1800158ab  mov     rcx, [rdx+18h]; this
0x1800158af  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800158b4  mov     rcx, [r15+38h]; this
0x1800158b8  mov     rbp, rax
0x1800158bb  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800158c0  mov     rcx, [r15+80h]; this
0x1800158c7  add     rbp, rax
0x1800158ca  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800158cf  add     rbp, rax
0x1800158d2  lea     rdi, [rsi+48h]
0x1800158d6  cmp     qword ptr [rsi+40h], 0
0x1800158db  jz      short loc_1800158E2
0x1800158dd  cmp     [rdi], rbp
0x1800158e0  jnb     short loc_18001591A
0x1800158e2  mov     rdx, rbp; dwBytes
0x1800158e5  mov     ecx, 8; dwFlags
0x1800158ea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800158ef  mov     r14, rax
0x1800158f2  test    rax, rax
0x1800158f5  jz      short loc_180015916
0x1800158f7  mov     rbx, [rsi+40h]
0x1800158fb  call    cs:__imp_GetProcessHeap
0x180015901  mov     r8, rbx; lpMem
0x180015904  xor     edx, edx; dwFlags
0x180015906  mov     rcx, rax; hHeap
0x180015909  call    cs:__imp_HeapFree
0x18001590f  mov     [rsi+40h], r14
0x180015913  mov     [rdi], rbp
0x180015916  lea     r14, [rsi+38h]
0x18001591a  mov     rcx, [rsi+40h]; Destination
0x18001591e  test    rcx, rcx
0x180015921  jz      short loc_180015971
0x180015923  mov     rbx, [rdi]
0x180015926  lea     r9, [rsi+10h]
0x18001592a  mov     r8, [r15+38h]
0x18001592e  add     rbx, rcx
0x180015931  mov     rdx, rbx
0x180015934  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180015939  mov     r8, [r15+80h]
0x180015940  lea     r9, [rsi+20h]
0x180015944  mov     rdx, rbx
0x180015947  mov     rcx, rax; Destination
0x18001594a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001594f  mov     r8, [r15+18h]
0x180015953  mov     r9, r14
0x180015956  mov     rdx, rbx
0x180015959  mov     rcx, rax; Destination
0x18001595c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180015961  sub     rbx, rax
0x180015964  xor     edx, edx; Val
0x180015966  mov     r8, rbx; Size
0x180015969  mov     rcx, rax; void *
0x18001596c  call    memset_0
0x180015971  add     rsp, 28h
0x180015975  pop     r15
0x180015977  pop     r14
0x180015979  pop     r13
0x18001597b  pop     r12
0x18001597d  pop     rdi
0x18001597e  pop     rsi
0x18001597f  pop     rbp
0x180015980  pop     rbx
0x180015981  retn
```
