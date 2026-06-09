# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180057068`
- end: `0x1800571e5`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `381`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800572dc`

## callees

- `0x18004a6d4`
- `0x18004a71c`
- `0x1800524c0`
- `0x180055d40`
- `0x180056ee0`
- `0x180056f04`
- `0x180057068`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180057110`
- `KERNEL32!GetProcessHeap` at `0x180057110`
- `KERNEL32!HeapFree` at `0x180057124`
- `KERNEL32!HeapFree` at `0x180057124`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  char **v3; // rbx
  char **v4; // rsi
  __int64 v7; // r15
  const char *v8; // rdx
  __int64 v9; // r15
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
0x180057068  push    rbx
0x18005706a  push    rbp
0x18005706b  push    rsi
0x18005706c  push    rdi
0x18005706d  push    r12
0x18005706f  push    r13
0x180057071  push    r14
0x180057073  push    r15
0x180057075  sub     rsp, 28h
0x180057079  mov     [rcx+4], r8d
0x18005707d  lea     rbx, [rcx+20h]
0x180057081  mov     eax, [rdx+8]
0x180057084  lea     rsi, [rcx+38h]
0x180057088  mov     [rcx+8], eax
0x18005708b  xor     r12d, r12d
0x18005708e  mov     [rcx+10h], r12
0x180057092  mov     rbp, rcx
0x180057095  movzx   eax, word ptr [rdx+40h]
0x180057099  mov     r14, rdx
0x18005709c  mov     [rcx+18h], ax
0x1800570a0  mov     al, [rdx]
0x1800570a2  mov     [rcx+1Ah], al
0x1800570a5  mov     [rbx], r12
0x1800570a8  mov     rax, [rdx+88h]
0x1800570af  mov     [rcx+28h], rax
0x1800570b3  mov     rax, [rdx+90h]
0x1800570ba  mov     [rcx+30h], rax
0x1800570be  mov     [rsi], r12
0x1800570c1  mov     rcx, [rdx+18h]; this
0x1800570c5  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800570ca  mov     rcx, [r14+38h]; this
0x1800570ce  mov     r15, rax
0x1800570d1  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800570d6  mov     rcx, [r14+80h]; this
0x1800570dd  add     r15, rax
0x1800570e0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800570e5  add     r15, rax
0x1800570e8  lea     rdi, [rbp+48h]
0x1800570ec  cmp     [rbp+40h], r12
0x1800570f0  jz      short loc_1800570F7
0x1800570f2  cmp     [rdi], r15
0x1800570f5  jnb     short loc_18005713E
0x1800570f7  mov     rdx, r15; dwBytes
0x1800570fa  mov     ecx, 8; dwFlags
0x1800570ff  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180057104  mov     r12, rax
0x180057107  test    rax, rax
0x18005710a  jz      short loc_18005713B
0x18005710c  mov     rbx, [rbp+40h]
0x180057110  call    cs:__imp_GetProcessHeap
0x180057117  nop     dword ptr [rax+rax+00h]
0x18005711c  mov     r8, rbx; lpMem
0x18005711f  xor     edx, edx; dwFlags
0x180057121  mov     rcx, rax; hHeap
0x180057124  call    cs:__imp_HeapFree
0x18005712b  nop     dword ptr [rax+rax+00h]
0x180057130  mov     [rbp+40h], r12
0x180057134  lea     rbx, [rbp+20h]
0x180057138  mov     [rdi], r15
0x18005713b  xor     r12d, r12d
0x18005713e  mov     rcx, [rbp+40h]; Destination
0x180057142  test    rcx, rcx
0x180057145  jz      loc_1800571D3
0x18005714b  mov     rdi, [rdi]
0x18005714e  lea     r9, [rbp+10h]
0x180057152  mov     r8, [r14+38h]
0x180057156  add     rdi, rcx
0x180057159  mov     rdx, rdi
0x18005715c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180057161  mov     r8, [r14+80h]
0x180057168  mov     r9, rbx
0x18005716b  mov     rdx, rdi
0x18005716e  mov     rcx, rax; Destination
0x180057171  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180057176  mov     rbx, rax
0x180057179  cmp     rax, rdi
0x18005717c  jz      short loc_1800571BB
0x18005717e  mov     rcx, [r14+18h]; this
0x180057182  test    rcx, rcx
0x180057185  jz      short loc_1800571BB
0x180057187  cmp     [rcx], r12w
0x18005718b  jz      short loc_1800571BB
0x18005718d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180057192  mov     rdx, rdi
0x180057195  mov     r14, rax
0x180057198  sub     rdx, rbx; DestinationSize
0x18005719b  cmp     rdx, rax
0x18005719e  jb      short loc_1800571BB
0x1800571a0  mov     r8, rcx; Source
0x1800571a3  mov     r9, rax; SourceSize
0x1800571a6  mov     rcx, rbx; Destination
0x1800571a9  call    memcpy_s
0x1800571ae  test    rsi, rsi
0x1800571b1  jz      short loc_1800571B6
0x1800571b3  mov     [rsi], rbx
0x1800571b6  add     rbx, r14
0x1800571b9  jmp     short loc_1800571C3
0x1800571bb  test    rsi, rsi
0x1800571be  jz      short loc_1800571C3
0x1800571c0  mov     [rsi], r12
0x1800571c3  sub     rdi, rbx
0x1800571c6  xor     edx, edx; Val
0x1800571c8  mov     r8, rdi; Size
0x1800571cb  mov     rcx, rbx; void *
0x1800571ce  call    memset_0
0x1800571d3  add     rsp, 28h
0x1800571d7  pop     r15
0x1800571d9  pop     r14
0x1800571db  pop     r13
0x1800571dd  pop     r12
0x1800571df  pop     rdi
0x1800571e0  pop     rsi
0x1800571e1  pop     rbp
0x1800571e2  pop     rbx
0x1800571e3  retn
```
