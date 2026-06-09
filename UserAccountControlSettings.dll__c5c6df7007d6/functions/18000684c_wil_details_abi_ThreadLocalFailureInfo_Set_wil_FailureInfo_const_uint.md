# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000684c`
- end: `0x1800069bd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800069c4`

## callees

- `0x180004998`
- `0x180006450`
- `0x180006784`
- `0x1800067a4`
- `0x18000684c`
- `0x18000b6de`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006981`
- `msvcrt!memcpy_s` at `0x180006981`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006902`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006902`

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
0x18000684c  push    rbx
0x18000684e  push    rbp
0x18000684f  push    rsi
0x180006850  push    rdi
0x180006851  push    r12
0x180006853  push    r13
0x180006855  push    r14
0x180006857  push    r15
0x180006859  sub     rsp, 28h
0x18000685d  mov     [rcx+4], r8d
0x180006861  lea     rbx, [rcx+20h]
0x180006865  mov     eax, [rdx+8]
0x180006868  lea     rsi, [rcx+38h]
0x18000686c  mov     [rcx+8], eax
0x18000686f  xor     r12d, r12d
0x180006872  mov     [rcx+10h], r12
0x180006876  mov     rbp, rcx
0x180006879  movzx   eax, word ptr [rdx+40h]
0x18000687d  mov     r14, rdx
0x180006880  mov     [rcx+18h], ax
0x180006884  mov     al, [rdx]
0x180006886  mov     [rcx+1Ah], al
0x180006889  mov     [rbx], r12
0x18000688c  mov     rax, [rdx+88h]
0x180006893  mov     [rcx+28h], rax
0x180006897  mov     rax, [rdx+90h]
0x18000689e  mov     [rcx+30h], rax
0x1800068a2  mov     [rsi], r12
0x1800068a5  mov     rcx, [rdx+18h]; this
0x1800068a9  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800068ae  mov     rcx, [r14+38h]; this
0x1800068b2  mov     r15, rax
0x1800068b5  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800068ba  mov     rcx, [r14+80h]; this
0x1800068c1  add     r15, rax
0x1800068c4  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800068c9  add     r15, rax
0x1800068cc  lea     rdi, [rbp+48h]
0x1800068d0  cmp     [rbp+40h], r12
0x1800068d4  jz      short loc_1800068DB
0x1800068d6  cmp     [rdi], r15
0x1800068d9  jnb     short loc_180006916
0x1800068db  mov     rdx, r15; dwBytes
0x1800068de  mov     ecx, 8; dwFlags
0x1800068e3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800068e8  mov     r12, rax
0x1800068eb  test    rax, rax
0x1800068ee  jz      short loc_180006913
0x1800068f0  mov     rbx, [rbp+40h]
0x1800068f4  call    cs:__imp_GetProcessHeap
0x1800068fa  mov     r8, rbx; lpMem
0x1800068fd  xor     edx, edx; dwFlags
0x1800068ff  mov     rcx, rax; hHeap
0x180006902  call    cs:__imp_HeapFree
0x180006908  mov     [rbp+40h], r12
0x18000690c  lea     rbx, [rbp+20h]
0x180006910  mov     [rdi], r15
0x180006913  xor     r12d, r12d
0x180006916  mov     rcx, [rbp+40h]; Destination
0x18000691a  test    rcx, rcx
0x18000691d  jz      loc_1800069AC
0x180006923  mov     rdi, [rdi]
0x180006926  lea     r9, [rbp+10h]
0x18000692a  mov     r8, [r14+38h]
0x18000692e  add     rdi, rcx
0x180006931  mov     rdx, rdi
0x180006934  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006939  mov     r8, [r14+80h]
0x180006940  mov     r9, rbx
0x180006943  mov     rdx, rdi
0x180006946  mov     rcx, rax; Destination
0x180006949  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000694e  mov     rbx, rax
0x180006951  cmp     rax, rdi
0x180006954  jz      short loc_180006994
0x180006956  mov     rcx, [r14+18h]; this
0x18000695a  test    rcx, rcx
0x18000695d  jz      short loc_180006994
0x18000695f  cmp     [rcx], r12w
0x180006963  jz      short loc_180006994
0x180006965  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000696a  mov     rdx, rdi
0x18000696d  mov     r14, rax
0x180006970  sub     rdx, rbx; DestinationSize
0x180006973  cmp     rdx, rax
0x180006976  jb      short loc_180006994
0x180006978  mov     r8, rcx; Source
0x18000697b  mov     r9, rax; SourceSize
0x18000697e  mov     rcx, rbx; Destination
0x180006981  call    cs:__imp_memcpy_s
0x180006987  test    rsi, rsi
0x18000698a  jz      short loc_18000698F
0x18000698c  mov     [rsi], rbx
0x18000698f  add     rbx, r14
0x180006992  jmp     short loc_18000699C
0x180006994  test    rsi, rsi
0x180006997  jz      short loc_18000699C
0x180006999  mov     [rsi], r12
0x18000699c  sub     rdi, rbx
0x18000699f  xor     edx, edx; Val
0x1800069a1  mov     r8, rdi; Size
0x1800069a4  mov     rcx, rbx; void *
0x1800069a7  call    memset_0
0x1800069ac  add     rsp, 28h
0x1800069b0  pop     r15
0x1800069b2  pop     r14
0x1800069b4  pop     r13
0x1800069b6  pop     r12
0x1800069b8  pop     rdi
0x1800069b9  pop     rsi
0x1800069ba  pop     rbp
0x1800069bb  pop     rbx
0x1800069bc  retn
```
