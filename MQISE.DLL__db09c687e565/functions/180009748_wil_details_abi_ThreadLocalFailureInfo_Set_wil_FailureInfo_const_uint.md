# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009748`
- end: `0x180009932`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `490`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180006060`

## callees

- `0x180001c0c`
- `0x180002b90`
- `0x180002c38`
- `0x180007dfc`
- `0x180009748`
- `0x18000f5c2`

## import_xrefs

- `msvcrt!??0exception@@QEAA@XZ` at `0x1800098e0`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800098fd`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18000991a`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800098e0`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800098fd`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18000991a`
- `KERNEL32!GetProcessHeap` at `0x180009854`
- `KERNEL32!GetProcessHeap` at `0x180009854`
- `KERNEL32!HeapFree` at `0x180009862`
- `KERNEL32!HeapFree` at `0x180009862`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  _QWORD *v3; // r15
  unsigned __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned __int64 v10; // rax
  __int64 v11; // r9
  unsigned __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // rbp
  unsigned __int64 *v16; // rsi
  LPVOID v17; // r15
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rcx
  char *v21; // rbx
  void *v22; // rax
  void *v23; // rax
  void *v24; // rax
  _BYTE pExceptionObject[104]; // [rsp+20h] [rbp-68h] BYREF

  *((_DWORD *)this + 1) = a3;
  v3 = (_QWORD *)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  v6 = -1;
  *v3 = 0;
  v7 = *((_QWORD *)a2 + 7);
  if ( v7 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_BYTE *)(v7 + v10) );
    if ( v10 > 0xFFFFFFFF )
    {
      exception::exception((exception *)pExceptionObject);
      throw (exception *)pExceptionObject;
    }
    v8 = 1;
    v9 = (unsigned int)v10 + 1LL;
  }
  else
  {
    v8 = 1;
    v9 = 1;
  }
  v11 = *((_QWORD *)a2 + 16);
  if ( v11 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_BYTE *)(v11 + v12) );
    if ( v12 > 0xFFFFFFFF )
    {
      exception::exception((exception *)pExceptionObject);
      throw (exception *)pExceptionObject;
    }
    v8 = (unsigned int)v12 + 1LL;
  }
  v13 = *((_QWORD *)a2 + 3);
  if ( v13 )
  {
    do
      ++v6;
    while ( *(_WORD *)(v13 + 2 * v6) );
    if ( v6 > 0xFFFFFFFF )
    {
      exception::exception((exception *)pExceptionObject);
      throw (exception *)pExceptionObject;
    }
    v14 = 2LL * (unsigned int)(v6 + 1);
  }
  else
  {
    v14 = 2;
  }
  v15 = v9 + v8 + v14;
  v16 = (unsigned __int64 *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v9 + v8 + v14);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = &v20[*v16];
    v22 = (void *)wil::details::WriteResultString<char const *>(v20);
    v23 = (void *)wil::details::WriteResultString<char const *>(v22);
    v24 = (void *)wil::details::WriteResultString<wchar_t const *>(v23);
    memset_0(v24, 0, v21 - (_BYTE *)v24);
  }
}

```

## disassembly

```asm
0x180009748  push    rbx
0x18000974a  push    rbp
0x18000974b  push    rsi
0x18000974c  push    rdi
0x18000974d  push    r12
0x18000974f  push    r13
0x180009751  push    r14
0x180009753  push    r15
0x180009755  sub     rsp, 48h
0x180009759  mov     [rcx+4], r8d
0x18000975d  lea     r15, [rcx+38h]
0x180009761  mov     eax, [rdx+8]
0x180009764  xor     ebx, ebx
0x180009766  mov     [rcx+8], eax
0x180009769  mov     r14, rdx
0x18000976c  mov     [rcx+10h], rbx
0x180009770  mov     rdi, rcx
0x180009773  movzx   eax, word ptr [rdx+40h]
0x180009777  mov     r10d, 0FFFFFFFFh
0x18000977d  mov     [rcx+18h], ax
0x180009781  mov     al, [rdx]
0x180009783  mov     [rcx+1Ah], al
0x180009786  mov     [rcx+20h], rbx
0x18000978a  mov     rax, [rdx+88h]
0x180009791  mov     [rcx+28h], rax
0x180009795  mov     rax, [rdx+90h]
0x18000979c  mov     [rcx+30h], rax
0x1800097a0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800097a4  mov     [r15], rbx
0x1800097a7  mov     rdx, [rdx+38h]
0x1800097ab  test    rdx, rdx
0x1800097ae  jnz     short loc_1800097B8
0x1800097b0  lea     edx, [rbx+1]
0x1800097b3  mov     r8d, edx
0x1800097b6  jmp     short loc_1800097D7
0x1800097b8  mov     rax, rcx
0x1800097bb  inc     rax
0x1800097be  cmp     [rdx+rax], bl
0x1800097c1  jnz     short loc_1800097BB
0x1800097c3  cmp     rax, r10
0x1800097c6  ja      loc_1800098DB
0x1800097cc  mov     r8d, eax
0x1800097cf  mov     edx, 1
0x1800097d4  add     r8, rdx; unsigned __int64
0x1800097d7  mov     r9, [r14+80h]
0x1800097de  test    r9, r9
0x1800097e1  jz      short loc_1800097FD
0x1800097e3  mov     rax, rcx
0x1800097e6  inc     rax
0x1800097e9  cmp     [r9+rax], bl
0x1800097ed  jnz     short loc_1800097E6
0x1800097ef  cmp     rax, r10
0x1800097f2  ja      loc_180009915
0x1800097f8  mov     eax, eax
0x1800097fa  add     rdx, rax
0x1800097fd  mov     rax, [r14+18h]
0x180009801  test    rax, rax
0x180009804  jnz     short loc_18000980D
0x180009806  mov     eax, 2
0x18000980b  jmp     short loc_180009825
0x18000980d  inc     rcx
0x180009810  cmp     [rax+rcx*2], bx
0x180009814  jnz     short loc_18000980D
0x180009816  cmp     rcx, r10
0x180009819  ja      loc_1800098F8
0x18000981f  lea     eax, [rcx+1]
0x180009822  add     rax, rax
0x180009825  lea     rbp, [rdx+rax]
0x180009829  add     rbp, r8
0x18000982c  lea     rsi, [rdi+48h]
0x180009830  cmp     [rdi+40h], rbx
0x180009834  jz      short loc_18000983B
0x180009836  cmp     [rsi], rbp
0x180009839  jnb     short loc_180009873
0x18000983b  mov     rdx, rbp; dwBytes
0x18000983e  mov     ecx, 8; dwFlags
0x180009843  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009848  mov     r15, rax
0x18000984b  test    rax, rax
0x18000984e  jz      short loc_18000986F
0x180009850  mov     rbx, [rdi+40h]
0x180009854  call    cs:__imp_GetProcessHeap
0x18000985a  mov     r8, rbx; lpMem
0x18000985d  xor     edx, edx; dwFlags
0x18000985f  mov     rcx, rax; hHeap
0x180009862  call    cs:__imp_HeapFree
0x180009868  mov     [rdi+40h], r15
0x18000986c  mov     [rsi], rbp
0x18000986f  lea     r15, [rdi+38h]
0x180009873  mov     rcx, [rdi+40h]; Destination
0x180009877  test    rcx, rcx
0x18000987a  jz      short loc_1800098CA
0x18000987c  mov     rbx, [rsi]
0x18000987f  lea     r9, [rdi+10h]
0x180009883  mov     r8, [r14+38h]
0x180009887  add     rbx, rcx
0x18000988a  mov     rdx, rbx
0x18000988d  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009892  mov     r8, [r14+80h]
0x180009899  lea     r9, [rdi+20h]
0x18000989d  mov     rdx, rbx
0x1800098a0  mov     rcx, rax; Destination
0x1800098a3  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800098a8  mov     r8, [r14+18h]
0x1800098ac  mov     r9, r15
0x1800098af  mov     rdx, rbx
0x1800098b2  mov     rcx, rax; Destination
0x1800098b5  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x1800098ba  sub     rbx, rax
0x1800098bd  xor     edx, edx; Val
0x1800098bf  mov     r8, rbx; Size
0x1800098c2  mov     rcx, rax; void *
0x1800098c5  call    memset_0
0x1800098ca  add     rsp, 48h
0x1800098ce  pop     r15
0x1800098d0  pop     r14
0x1800098d2  pop     r13
0x1800098d4  pop     r12
0x1800098d6  pop     rdi
0x1800098d7  pop     rsi
0x1800098d8  pop     rbp
0x1800098d9  pop     rbx
0x1800098da  retn
0x1800098db  lea     rcx, [rsp+88h+pExceptionObject]
0x1800098e0  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x1800098e6  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x1800098ed  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800098f2  call    _CxxThrowException_0
0x1800098f8  lea     rcx, [rsp+88h+pExceptionObject]
0x1800098fd  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180009903  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x18000990a  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000990f  call    _CxxThrowException_0
0x180009915  lea     rcx, [rsp+88h+pExceptionObject]
0x18000991a  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180009920  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x180009927  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000992c  call    _CxxThrowException_0
```
