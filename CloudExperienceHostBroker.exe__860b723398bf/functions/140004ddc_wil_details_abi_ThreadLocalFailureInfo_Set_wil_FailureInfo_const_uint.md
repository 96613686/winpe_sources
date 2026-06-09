# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140004ddc`
- end: `0x140004f12`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140005174`

## callees

- `0x14000252f`
- `0x140002ef0`
- `0x140002f68`
- `0x140004958`
- `0x140004cf8`
- `0x140004d18`
- `0x140004ddc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004e8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004e8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004e99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004e99`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int16 **v3; // r14
  __int64 v6; // rbp
  const char *v7; // rdx
  __int64 v8; // rbp
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
0x140004ddc  push    rbx
0x140004dde  push    rbp
0x140004ddf  push    rsi
0x140004de0  push    rdi
0x140004de1  push    r12
0x140004de3  push    r13
0x140004de5  push    r14
0x140004de7  push    r15
0x140004de9  sub     rsp, 28h
0x140004ded  mov     [rcx+4], r8d
0x140004df1  lea     r14, [rcx+38h]
0x140004df5  mov     eax, [rdx+8]
0x140004df8  mov     rsi, rcx
0x140004dfb  mov     [rcx+8], eax
0x140004dfe  mov     r15, rdx
0x140004e01  mov     qword ptr [rcx+10h], 0
0x140004e09  movzx   eax, word ptr [rdx+40h]
0x140004e0d  mov     [rcx+18h], ax
0x140004e11  mov     al, [rdx]
0x140004e13  mov     [rcx+1Ah], al
0x140004e16  mov     qword ptr [rcx+20h], 0
0x140004e1e  mov     rax, [rdx+88h]
0x140004e25  mov     [rcx+28h], rax
0x140004e29  mov     rax, [rdx+90h]
0x140004e30  mov     [rcx+30h], rax
0x140004e34  mov     qword ptr [r14], 0
0x140004e3b  mov     rcx, [rdx+18h]; this
0x140004e3f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140004e44  mov     rcx, [r15+38h]; this
0x140004e48  mov     rbp, rax
0x140004e4b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140004e50  mov     rcx, [r15+80h]; this
0x140004e57  add     rbp, rax
0x140004e5a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140004e5f  add     rbp, rax
0x140004e62  lea     rdi, [rsi+48h]
0x140004e66  cmp     qword ptr [rsi+40h], 0
0x140004e6b  jz      short loc_140004E72
0x140004e6d  cmp     [rdi], rbp
0x140004e70  jnb     short loc_140004EAA
0x140004e72  mov     rdx, rbp; dwBytes
0x140004e75  mov     ecx, 8; dwFlags
0x140004e7a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004e7f  mov     r14, rax
0x140004e82  test    rax, rax
0x140004e85  jz      short loc_140004EA6
0x140004e87  mov     rbx, [rsi+40h]
0x140004e8b  call    cs:__imp_GetProcessHeap
0x140004e91  mov     r8, rbx; lpMem
0x140004e94  xor     edx, edx; dwFlags
0x140004e96  mov     rcx, rax; hHeap
0x140004e99  call    cs:__imp_HeapFree
0x140004e9f  mov     [rsi+40h], r14
0x140004ea3  mov     [rdi], rbp
0x140004ea6  lea     r14, [rsi+38h]
0x140004eaa  mov     rcx, [rsi+40h]; Destination
0x140004eae  test    rcx, rcx
0x140004eb1  jz      short loc_140004F01
0x140004eb3  mov     rbx, [rdi]
0x140004eb6  lea     r9, [rsi+10h]
0x140004eba  mov     r8, [r15+38h]
0x140004ebe  add     rbx, rcx
0x140004ec1  mov     rdx, rbx
0x140004ec4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140004ec9  mov     r8, [r15+80h]
0x140004ed0  lea     r9, [rsi+20h]
0x140004ed4  mov     rdx, rbx
0x140004ed7  mov     rcx, rax; Destination
0x140004eda  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140004edf  mov     r8, [r15+18h]
0x140004ee3  mov     r9, r14
0x140004ee6  mov     rdx, rbx
0x140004ee9  mov     rcx, rax; Destination
0x140004eec  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x140004ef1  sub     rbx, rax
0x140004ef4  xor     edx, edx; Val
0x140004ef6  mov     r8, rbx; Size
0x140004ef9  mov     rcx, rax; void *
0x140004efc  call    memset_0
0x140004f01  add     rsp, 28h
0x140004f05  pop     r15
0x140004f07  pop     r14
0x140004f09  pop     r13
0x140004f0b  pop     r12
0x140004f0d  pop     rdi
0x140004f0e  pop     rsi
0x140004f0f  pop     rbp
0x140004f10  pop     rbx
0x140004f11  retn
```
