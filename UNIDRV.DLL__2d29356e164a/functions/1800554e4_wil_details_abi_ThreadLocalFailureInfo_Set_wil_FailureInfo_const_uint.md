# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800554e4`
- end: `0x180055654`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18005574c`

## callees

- `0x180049194`
- `0x1800491dc`
- `0x180050cfc`
- `0x18005423c`
- `0x180055360`
- `0x180055380`
- `0x1800554e4`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18005558c`
- `KERNEL32!GetProcessHeap` at `0x18005558c`
- `KERNEL32!HeapFree` at `0x18005559a`
- `KERNEL32!HeapFree` at `0x18005559a`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  _QWORD *v3; // rsi
  unsigned __int64 v6; // r15
  const char *v7; // rdx
  unsigned __int64 v8; // r15
  const char *v9; // rdx
  SIZE_T v10; // r15
  SIZE_T *v11; // rdi
  LPVOID v12; // r12
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  char *v16; // rdi
  void *v17; // rax
  const unsigned __int16 *v18; // rdx
  char *v19; // rbx
  wil::details *v20; // rcx
  rsize_t v21; // rax
  const void *v22; // rcx
  rsize_t v23; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (_QWORD *)((char *)this + 56);
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
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = (void *)wil::details::WriteResultString<char const *>(v15);
    v19 = (char *)wil::details::WriteResultString<char const *>(v17);
    if ( v19 != v16
      && (v20 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v20
      && (v21 = wil::details::ResultStringSize(v20, v18), v23 = v21, v16 - v19 >= v21) )
    {
      memcpy_s(v19, v16 - v19, v22, v21);
      if ( v3 )
        *v3 = v19;
      v19 += v23;
    }
    else if ( v3 )
    {
      *v3 = 0;
    }
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x1800554e4  push    rbx
0x1800554e6  push    rbp
0x1800554e7  push    rsi
0x1800554e8  push    rdi
0x1800554e9  push    r12
0x1800554eb  push    r13
0x1800554ed  push    r14
0x1800554ef  push    r15
0x1800554f1  sub     rsp, 28h
0x1800554f5  mov     [rcx+4], r8d
0x1800554f9  lea     rbx, [rcx+20h]
0x1800554fd  mov     eax, [rdx+8]
0x180055500  lea     rsi, [rcx+38h]
0x180055504  mov     [rcx+8], eax
0x180055507  xor     r12d, r12d
0x18005550a  mov     [rcx+10h], r12
0x18005550e  mov     rbp, rcx
0x180055511  movzx   eax, word ptr [rdx+40h]
0x180055515  mov     r14, rdx
0x180055518  mov     [rcx+18h], ax
0x18005551c  mov     al, [rdx]
0x18005551e  mov     [rcx+1Ah], al
0x180055521  mov     [rbx], r12
0x180055524  mov     rax, [rdx+88h]
0x18005552b  mov     [rcx+28h], rax
0x18005552f  mov     rax, [rdx+90h]
0x180055536  mov     [rcx+30h], rax
0x18005553a  mov     [rsi], r12
0x18005553d  mov     rcx, [rdx+18h]; this
0x180055541  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180055546  mov     rcx, [r14+38h]; this
0x18005554a  mov     r15, rax
0x18005554d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180055552  mov     rcx, [r14+80h]; this
0x180055559  add     r15, rax
0x18005555c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180055561  add     r15, rax
0x180055564  lea     rdi, [rbp+48h]
0x180055568  cmp     [rbp+40h], r12
0x18005556c  jz      short loc_180055573
0x18005556e  cmp     [rdi], r15
0x180055571  jnb     short loc_1800555AE
0x180055573  mov     rdx, r15; dwBytes
0x180055576  mov     ecx, 8; dwFlags
0x18005557b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180055580  mov     r12, rax
0x180055583  test    rax, rax
0x180055586  jz      short loc_1800555AB
0x180055588  mov     rbx, [rbp+40h]
0x18005558c  call    cs:__imp_GetProcessHeap
0x180055592  mov     r8, rbx; lpMem
0x180055595  xor     edx, edx; dwFlags
0x180055597  mov     rcx, rax; hHeap
0x18005559a  call    cs:__imp_HeapFree
0x1800555a0  mov     [rbp+40h], r12
0x1800555a4  lea     rbx, [rbp+20h]
0x1800555a8  mov     [rdi], r15
0x1800555ab  xor     r12d, r12d
0x1800555ae  mov     rcx, [rbp+40h]; Destination
0x1800555b2  test    rcx, rcx
0x1800555b5  jz      loc_180055643
0x1800555bb  mov     rdi, [rdi]
0x1800555be  lea     r9, [rbp+10h]
0x1800555c2  mov     r8, [r14+38h]
0x1800555c6  add     rdi, rcx
0x1800555c9  mov     rdx, rdi
0x1800555cc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800555d1  mov     r8, [r14+80h]
0x1800555d8  mov     r9, rbx
0x1800555db  mov     rdx, rdi
0x1800555de  mov     rcx, rax; Destination
0x1800555e1  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800555e6  mov     rbx, rax
0x1800555e9  cmp     rax, rdi
0x1800555ec  jz      short loc_18005562B
0x1800555ee  mov     rcx, [r14+18h]; this
0x1800555f2  test    rcx, rcx
0x1800555f5  jz      short loc_18005562B
0x1800555f7  cmp     [rcx], r12w
0x1800555fb  jz      short loc_18005562B
0x1800555fd  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180055602  mov     rdx, rdi
0x180055605  mov     r14, rax
0x180055608  sub     rdx, rbx; DestinationSize
0x18005560b  cmp     rdx, rax
0x18005560e  jb      short loc_18005562B
0x180055610  mov     r8, rcx; Source
0x180055613  mov     r9, rax; SourceSize
0x180055616  mov     rcx, rbx; Destination
0x180055619  call    memcpy_s
0x18005561e  test    rsi, rsi
0x180055621  jz      short loc_180055626
0x180055623  mov     [rsi], rbx
0x180055626  add     rbx, r14
0x180055629  jmp     short loc_180055633
0x18005562b  test    rsi, rsi
0x18005562e  jz      short loc_180055633
0x180055630  mov     [rsi], r12
0x180055633  sub     rdi, rbx
0x180055636  xor     edx, edx; Val
0x180055638  mov     r8, rdi; Size
0x18005563b  mov     rcx, rbx; void *
0x18005563e  call    memset_0
0x180055643  add     rsp, 28h
0x180055647  pop     r15
0x180055649  pop     r14
0x18005564b  pop     r13
0x18005564d  pop     r12
0x18005564f  pop     rdi
0x180055650  pop     rsi
0x180055651  pop     rbp
0x180055652  pop     rbx
0x180055653  retn
```
