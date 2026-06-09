# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1400042b8`
- end: `0x140004428`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140004430`

## callees

- `0x140001fa2`
- `0x140002728`
- `0x140003e78`
- `0x140004090`
- `0x1400040b0`
- `0x1400042b8`
- `0x140004bb8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000436e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000436e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004360`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004360`

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
0x1400042b8  push    rbx
0x1400042ba  push    rbp
0x1400042bb  push    rsi
0x1400042bc  push    rdi
0x1400042bd  push    r12
0x1400042bf  push    r13
0x1400042c1  push    r14
0x1400042c3  push    r15
0x1400042c5  sub     rsp, 28h
0x1400042c9  mov     [rcx+4], r8d
0x1400042cd  lea     rbx, [rcx+20h]
0x1400042d1  mov     eax, [rdx+8]
0x1400042d4  lea     rsi, [rcx+38h]
0x1400042d8  mov     [rcx+8], eax
0x1400042db  xor     r12d, r12d
0x1400042de  mov     [rcx+10h], r12
0x1400042e2  mov     rbp, rcx
0x1400042e5  movzx   eax, word ptr [rdx+40h]
0x1400042e9  mov     r14, rdx
0x1400042ec  mov     [rcx+18h], ax
0x1400042f0  mov     al, [rdx]
0x1400042f2  mov     [rcx+1Ah], al
0x1400042f5  mov     [rbx], r12
0x1400042f8  mov     rax, [rdx+88h]
0x1400042ff  mov     [rcx+28h], rax
0x140004303  mov     rax, [rdx+90h]
0x14000430a  mov     [rcx+30h], rax
0x14000430e  mov     [rsi], r12
0x140004311  mov     rcx, [rdx+18h]; this
0x140004315  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x14000431a  mov     rcx, [r14+38h]; this
0x14000431e  mov     r15, rax
0x140004321  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140004326  mov     rcx, [r14+80h]; this
0x14000432d  add     r15, rax
0x140004330  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140004335  add     r15, rax
0x140004338  lea     rdi, [rbp+48h]
0x14000433c  cmp     [rbp+40h], r12
0x140004340  jz      short loc_140004347
0x140004342  cmp     [rdi], r15
0x140004345  jnb     short loc_140004382
0x140004347  mov     rdx, r15; dwBytes
0x14000434a  mov     ecx, 8; dwFlags
0x14000434f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004354  mov     r12, rax
0x140004357  test    rax, rax
0x14000435a  jz      short loc_14000437F
0x14000435c  mov     rbx, [rbp+40h]
0x140004360  call    cs:__imp_GetProcessHeap
0x140004366  mov     r8, rbx; lpMem
0x140004369  xor     edx, edx; dwFlags
0x14000436b  mov     rcx, rax; hHeap
0x14000436e  call    cs:__imp_HeapFree
0x140004374  mov     [rbp+40h], r12
0x140004378  lea     rbx, [rbp+20h]
0x14000437c  mov     [rdi], r15
0x14000437f  xor     r12d, r12d
0x140004382  mov     rcx, [rbp+40h]; Destination
0x140004386  test    rcx, rcx
0x140004389  jz      loc_140004417
0x14000438f  mov     rdi, [rdi]
0x140004392  lea     r9, [rbp+10h]
0x140004396  mov     r8, [r14+38h]
0x14000439a  add     rdi, rcx
0x14000439d  mov     rdx, rdi
0x1400043a0  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1400043a5  mov     r8, [r14+80h]
0x1400043ac  mov     r9, rbx
0x1400043af  mov     rdx, rdi
0x1400043b2  mov     rcx, rax; Destination
0x1400043b5  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1400043ba  mov     rbx, rax
0x1400043bd  cmp     rax, rdi
0x1400043c0  jz      short loc_1400043FF
0x1400043c2  mov     rcx, [r14+18h]; this
0x1400043c6  test    rcx, rcx
0x1400043c9  jz      short loc_1400043FF
0x1400043cb  cmp     [rcx], r12w
0x1400043cf  jz      short loc_1400043FF
0x1400043d1  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1400043d6  mov     rdx, rdi
0x1400043d9  mov     r14, rax
0x1400043dc  sub     rdx, rbx; DestinationSize
0x1400043df  cmp     rdx, rax
0x1400043e2  jb      short loc_1400043FF
0x1400043e4  mov     r8, rcx; Source
0x1400043e7  mov     r9, rax; SourceSize
0x1400043ea  mov     rcx, rbx; Destination
0x1400043ed  call    memcpy_s
0x1400043f2  test    rsi, rsi
0x1400043f5  jz      short loc_1400043FA
0x1400043f7  mov     [rsi], rbx
0x1400043fa  add     rbx, r14
0x1400043fd  jmp     short loc_140004407
0x1400043ff  test    rsi, rsi
0x140004402  jz      short loc_140004407
0x140004404  mov     [rsi], r12
0x140004407  sub     rdi, rbx
0x14000440a  xor     edx, edx; Val
0x14000440c  mov     r8, rdi; Size
0x14000440f  mov     rcx, rbx; void *
0x140004412  call    memset_0
0x140004417  add     rsp, 28h
0x14000441b  pop     r15
0x14000441d  pop     r14
0x14000441f  pop     r13
0x140004421  pop     r12
0x140004423  pop     rdi
0x140004424  pop     rsi
0x140004425  pop     rbp
0x140004426  pop     rbx
0x140004427  retn
```
