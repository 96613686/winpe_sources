# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009240`
- end: `0x180009376`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800095d8`

## callees

- `0x18000365c`
- `0x180004a0c`
- `0x180004a84`
- `0x180008420`
- `0x1800090f8`
- `0x180009118`
- `0x180009240`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800092ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800092ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800092fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800092fd`

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
0x180009240  push    rbx
0x180009242  push    rbp
0x180009243  push    rsi
0x180009244  push    rdi
0x180009245  push    r12
0x180009247  push    r13
0x180009249  push    r14
0x18000924b  push    r15
0x18000924d  sub     rsp, 28h
0x180009251  mov     [rcx+4], r8d
0x180009255  lea     r14, [rcx+38h]
0x180009259  mov     eax, [rdx+8]
0x18000925c  mov     rsi, rcx
0x18000925f  mov     [rcx+8], eax
0x180009262  mov     r15, rdx
0x180009265  mov     qword ptr [rcx+10h], 0
0x18000926d  movzx   eax, word ptr [rdx+40h]
0x180009271  mov     [rcx+18h], ax
0x180009275  mov     al, [rdx]
0x180009277  mov     [rcx+1Ah], al
0x18000927a  mov     qword ptr [rcx+20h], 0
0x180009282  mov     rax, [rdx+88h]
0x180009289  mov     [rcx+28h], rax
0x18000928d  mov     rax, [rdx+90h]
0x180009294  mov     [rcx+30h], rax
0x180009298  mov     qword ptr [r14], 0
0x18000929f  mov     rcx, [rdx+18h]; this
0x1800092a3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800092a8  mov     rcx, [r15+38h]; this
0x1800092ac  mov     rbp, rax
0x1800092af  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800092b4  mov     rcx, [r15+80h]; this
0x1800092bb  add     rbp, rax
0x1800092be  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800092c3  add     rbp, rax
0x1800092c6  lea     rdi, [rsi+48h]
0x1800092ca  cmp     qword ptr [rsi+40h], 0
0x1800092cf  jz      short loc_1800092D6
0x1800092d1  cmp     [rdi], rbp
0x1800092d4  jnb     short loc_18000930E
0x1800092d6  mov     rdx, rbp; dwBytes
0x1800092d9  mov     ecx, 8; dwFlags
0x1800092de  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800092e3  mov     r14, rax
0x1800092e6  test    rax, rax
0x1800092e9  jz      short loc_18000930A
0x1800092eb  mov     rbx, [rsi+40h]
0x1800092ef  call    cs:__imp_GetProcessHeap
0x1800092f5  mov     r8, rbx; lpMem
0x1800092f8  xor     edx, edx; dwFlags
0x1800092fa  mov     rcx, rax; hHeap
0x1800092fd  call    cs:__imp_HeapFree
0x180009303  mov     [rsi+40h], r14
0x180009307  mov     [rdi], rbp
0x18000930a  lea     r14, [rsi+38h]
0x18000930e  mov     rcx, [rsi+40h]; Destination
0x180009312  test    rcx, rcx
0x180009315  jz      short loc_180009365
0x180009317  mov     rbx, [rdi]
0x18000931a  lea     r9, [rsi+10h]
0x18000931e  mov     r8, [r15+38h]
0x180009322  add     rbx, rcx
0x180009325  mov     rdx, rbx
0x180009328  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000932d  mov     r8, [r15+80h]
0x180009334  lea     r9, [rsi+20h]
0x180009338  mov     rdx, rbx
0x18000933b  mov     rcx, rax; Destination
0x18000933e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009343  mov     r8, [r15+18h]
0x180009347  mov     r9, r14
0x18000934a  mov     rdx, rbx
0x18000934d  mov     rcx, rax; Destination
0x180009350  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180009355  sub     rbx, rax
0x180009358  xor     edx, edx; Val
0x18000935a  mov     r8, rbx; Size
0x18000935d  mov     rcx, rax; void *
0x180009360  call    memset_0
0x180009365  add     rsp, 28h
0x180009369  pop     r15
0x18000936b  pop     r14
0x18000936d  pop     r13
0x18000936f  pop     r12
0x180009371  pop     rdi
0x180009372  pop     rsi
0x180009373  pop     rbp
0x180009374  pop     rbx
0x180009375  retn
```
