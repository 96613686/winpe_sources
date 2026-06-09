# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009260`
- end: `0x180009396`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800096e4`

## callees

- `0x1800047f0`
- `0x18000551c`
- `0x180005594`
- `0x1800082d4`
- `0x1800090d8`
- `0x1800090f8`
- `0x180009260`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000931d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000931d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000930f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000930f`

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
0x180009260  push    rbx
0x180009262  push    rbp
0x180009263  push    rsi
0x180009264  push    rdi
0x180009265  push    r12
0x180009267  push    r13
0x180009269  push    r14
0x18000926b  push    r15
0x18000926d  sub     rsp, 28h
0x180009271  mov     [rcx+4], r8d
0x180009275  lea     r14, [rcx+38h]
0x180009279  mov     eax, [rdx+8]
0x18000927c  mov     rsi, rcx
0x18000927f  mov     [rcx+8], eax
0x180009282  mov     r15, rdx
0x180009285  mov     qword ptr [rcx+10h], 0
0x18000928d  movzx   eax, word ptr [rdx+40h]
0x180009291  mov     [rcx+18h], ax
0x180009295  mov     al, [rdx]
0x180009297  mov     [rcx+1Ah], al
0x18000929a  mov     qword ptr [rcx+20h], 0
0x1800092a2  mov     rax, [rdx+88h]
0x1800092a9  mov     [rcx+28h], rax
0x1800092ad  mov     rax, [rdx+90h]
0x1800092b4  mov     [rcx+30h], rax
0x1800092b8  mov     qword ptr [r14], 0
0x1800092bf  mov     rcx, [rdx+18h]; this
0x1800092c3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800092c8  mov     rcx, [r15+38h]; this
0x1800092cc  mov     rbp, rax
0x1800092cf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800092d4  mov     rcx, [r15+80h]; this
0x1800092db  add     rbp, rax
0x1800092de  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800092e3  add     rbp, rax
0x1800092e6  lea     rdi, [rsi+48h]
0x1800092ea  cmp     qword ptr [rsi+40h], 0
0x1800092ef  jz      short loc_1800092F6
0x1800092f1  cmp     [rdi], rbp
0x1800092f4  jnb     short loc_18000932E
0x1800092f6  mov     rdx, rbp; dwBytes
0x1800092f9  mov     ecx, 8; dwFlags
0x1800092fe  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009303  mov     r14, rax
0x180009306  test    rax, rax
0x180009309  jz      short loc_18000932A
0x18000930b  mov     rbx, [rsi+40h]
0x18000930f  call    cs:__imp_GetProcessHeap
0x180009315  mov     r8, rbx; lpMem
0x180009318  xor     edx, edx; dwFlags
0x18000931a  mov     rcx, rax; hHeap
0x18000931d  call    cs:__imp_HeapFree
0x180009323  mov     [rsi+40h], r14
0x180009327  mov     [rdi], rbp
0x18000932a  lea     r14, [rsi+38h]
0x18000932e  mov     rcx, [rsi+40h]; Destination
0x180009332  test    rcx, rcx
0x180009335  jz      short loc_180009385
0x180009337  mov     rbx, [rdi]
0x18000933a  lea     r9, [rsi+10h]
0x18000933e  mov     r8, [r15+38h]
0x180009342  add     rbx, rcx
0x180009345  mov     rdx, rbx
0x180009348  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000934d  mov     r8, [r15+80h]
0x180009354  lea     r9, [rsi+20h]
0x180009358  mov     rdx, rbx
0x18000935b  mov     rcx, rax; Destination
0x18000935e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009363  mov     r8, [r15+18h]
0x180009367  mov     r9, r14
0x18000936a  mov     rdx, rbx
0x18000936d  mov     rcx, rax; Destination
0x180009370  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180009375  sub     rbx, rax
0x180009378  xor     edx, edx; Val
0x18000937a  mov     r8, rbx; Size
0x18000937d  mov     rcx, rax; void *
0x180009380  call    memset_0
0x180009385  add     rsp, 28h
0x180009389  pop     r15
0x18000938b  pop     r14
0x18000938d  pop     r13
0x18000938f  pop     r12
0x180009391  pop     rdi
0x180009392  pop     rsi
0x180009393  pop     rbp
0x180009394  pop     rbx
0x180009395  retn
```
