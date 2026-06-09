# ReadingPool::Create(void *,InputDataLayout const *,ReadingPool * *)

- ea: `0x1800239a4`
- end: `0x180023c44`
- name: `?Create@ReadingPool@@SAJPEAXPEBVInputDataLayout@@PEAPEAV1@@Z`
- size: `672`
- prototype: `__int64 __fastcall(void *, const struct InputDataLayout *, struct ReadingPool **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18002f774`

## callees

- `0x180001304`
- `0x18000391c`
- `0x18000c11c`
- `0x1800234b4`
- `0x1800239a4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800239f3`
- `ntdll!RtlAllocateHeap` at `0x180023a38`
- `ntdll!RtlAllocateHeap` at `0x1800239f3`
- `ntdll!RtlAllocateHeap` at `0x180023a38`

## string_xrefs

- `0x180023aad`: `onecore\xbox\gameinput\memory\ReadingPool.cpp`
- `0x180023b7a`: `onecore\xbox\gameinput\memory\ReadingPool.cpp`
- `0x180023bed`: `onecore\xbox\gameinput\memory\ReadingPool.cpp`

## pseudocode

```c
__int64 __fastcall ReadingPool::Create(void *a1, const struct InputDataLayout *a2, struct ReadingPool **a3)
{
  unsigned __int64 v3; // rbx
  SIZE_T v7; // rax
  PVOID ProcessHeap; // rcx
  PVOID Heap; // rax
  int v10; // r8d
  int v11; // r9d
  void *v12; // r14
  HString *i; // rsi
  ReadingPool *v14; // rax
  const struct std::nothrow_t *v15; // rdx
  int v16; // r8d
  int v17; // r9d
  ReadingPool *v18; // rax
  ReadingPool *v19; // rbx
  unsigned __int64 v20; // rax
  void *v21; // rcx
  unsigned __int64 *v23; // rdx
  int v24; // ecx
  unsigned __int64 *v25; // rax
  int v26; // [rsp+88h] [rbp+48h] BYREF
  int v27; // [rsp+90h] [rbp+50h] BYREF
  const char *v28; // [rsp+98h] [rbp+58h] BYREF

  v3 = *((unsigned int *)a2 + 6);
  *a3 = 0;
  v7 = 8 * v3;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  if ( !is_mul_ok(v3, 8u) )
    v7 = -1;
  Heap = RtlAllocateHeap(ProcessHeap, 0, v7);
  v12 = Heap;
  if ( !Heap )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x20) != 0
      && (qword_180069018 & 0x20) == qword_180069018 )
    {
      v26 = -2147024882;
      v28 = "onecore\\xbox\\gameinput\\memory\\ReadingPool.cpp";
      v27 = 43;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)byte_18005E8EB,
        v10,
        v11,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
    return 2147942414LL;
  }
  for ( i = (HString *)Heap; v3; --v3 )
  {
    HString::HString(i);
    i = (HString *)((char *)i + 8);
  }
  v14 = (ReadingPool *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x48u);
  if ( !v14 || (v18 = ReadingPool::ReadingPool(v14, a1, a2, (struct ReadingPoolElementId *)v12), (v19 = v18) == 0) )
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x20) != 0
      && (qword_180069018 & 0x20) == qword_180069018 )
    {
      v26 = -2147024882;
      v28 = "onecore\\xbox\\gameinput\\memory\\ReadingPool.cpp";
      v27 = 48;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)&unk_18005E9C8,
        v16,
        v17,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
    operator delete(v12, v15);
    return 2147942414LL;
  }
  v20 = **(_QWORD **)v18;
  if ( v20 < 0x10000 )
  {
    v23 = (unsigned __int64 *)*((_QWORD *)v19 + 4);
    v24 = *((_DWORD *)v19 + 10) - 1;
    if ( *((_DWORD *)v19 + 10) != 1 )
    {
      do
      {
        v25 = v23++;
        *v25 = -1;
        --v24;
      }
      while ( v24 );
    }
    *v23 = 0xFFFFFFFFFFFFFFFFuLL >> -*((_BYTE *)v19 + 44);
    goto LABEL_21;
  }
  if ( v20 == 0x10000 )
  {
    **((_QWORD **)v19 + 6) = 0x10000;
    ++*((_DWORD *)v19 + 14);
    ++*((_QWORD *)v19 + 8);
LABEL_21:
    *a3 = v19;
    return 0;
  }
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 0x20) != 0 && (qword_180069018 & 0x20) == qword_180069018 )
  {
    v26 = -2147418113;
    v28 = "onecore\\xbox\\gameinput\\memory\\ReadingPool.cpp";
    v27 = 61;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned int)byte_18005E98B,
      v16,
      v17,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26);
  }
  v21 = (void *)*((_QWORD *)v19 + 6);
  if ( v21 )
    operator delete(v21, v15);
  operator delete(v19, v15);
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800239a4  mov     [rsp-38h+arg_0], rbx
0x1800239a9  push    rbp
0x1800239aa  push    rsi
0x1800239ab  push    rdi
0x1800239ac  push    r12
0x1800239ae  push    r13
0x1800239b0  push    r14
0x1800239b2  push    r15
0x1800239b4  mov     rbp, rsp
0x1800239b7  sub     rsp, 40h
0x1800239bb  mov     ebx, [rdx+18h]
0x1800239be  mov     r12, rdx
0x1800239c1  mov     r13, rcx
0x1800239c4  mov     qword ptr [r8], 0
0x1800239cb  mov     rcx, gs:60h
0x1800239d4  mov     r15, r8
0x1800239d7  mov     eax, 8
0x1800239dc  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800239e3  mul     rbx
0x1800239e6  mov     rcx, [rcx+30h]; HeapHandle
0x1800239ea  cmovb   rax, rdi
0x1800239ee  xor     edx, edx; Flags
0x1800239f0  mov     r8, rax; Size
0x1800239f3  call    cs:__imp_RtlAllocateHeap
0x1800239fa  nop     dword ptr [rax+rax+00h]
0x1800239ff  mov     r14, rax
0x180023a02  test    rax, rax
0x180023a05  jz      loc_180023BC0
0x180023a0b  mov     rsi, rax
0x180023a0e  test    rbx, rbx
0x180023a11  jz      short loc_180023A25
0x180023a13  mov     rcx, rsi; this
0x180023a16  call    ??0HString@@QEAA@XZ; HString::HString(void)
0x180023a1b  add     rsi, 8
0x180023a1f  sub     rbx, 1
0x180023a23  jnz     short loc_180023A13
0x180023a25  mov     rcx, gs:60h
0x180023a2e  xor     edx, edx; Flags
0x180023a30  mov     rcx, [rcx+30h]; HeapHandle
0x180023a34  lea     r8d, [rdx+48h]; Size
0x180023a38  call    cs:__imp_RtlAllocateHeap
0x180023a3f  nop     dword ptr [rax+rax+00h]
0x180023a44  test    rax, rax
0x180023a47  jz      loc_180023B4D
0x180023a4d  mov     r9, r14; struct ReadingPoolElementId *
0x180023a50  mov     r8, r12; struct InputDataLayout *
0x180023a53  mov     rdx, r13; void *
0x180023a56  mov     rcx, rax; this
0x180023a59  call    ??0ReadingPool@@AEAA@PEAXPEBVInputDataLayout@@PEAVReadingPoolElementId@@@Z; ReadingPool::ReadingPool(void *,InputDataLayout const *,ReadingPoolElementId *)
0x180023a5e  mov     rbx, rax
0x180023a61  test    rax, rax
0x180023a64  jz      loc_180023B4D
0x180023a6a  mov     rcx, [rax]
0x180023a6d  mov     rax, [rcx]
0x180023a70  mov     ecx, 10000h
0x180023a75  nop
0x180023a76  cmp     rax, rcx
0x180023a79  jb      loc_180023B1D
0x180023a7f  jz      loc_180023B0D
0x180023a85  mov     eax, cs:dword_180069000
0x180023a8b  cmp     eax, 2
0x180023a8e  jbe     short loc_180023AED
0x180023a90  mov     rcx, cs:qword_180069018
0x180023a97  mov     rax, cs:qword_180069010
0x180023a9e  test    al, 20h
0x180023aa0  jz      short loc_180023AED
0x180023aa2  mov     rax, rcx
0x180023aa5  and     eax, 20h
0x180023aa8  cmp     rax, rcx
0x180023aab  jnz     short loc_180023AED
0x180023aad  lea     rax, aOnecoreXboxGam_41; "onecore\\xbox\\gameinput\\memory\\Readi"...
0x180023ab4  mov     [rbp+arg_8], 8000FFFFh
0x180023abb  mov     [rbp+arg_18], rax
0x180023abf  lea     rdx, byte_18005E98B
0x180023ac6  lea     rax, [rbp+arg_8]
0x180023aca  mov     [rbp+arg_10], 3Dh ; '='
0x180023ad1  mov     [rsp+40h+var_10], rax
0x180023ad6  lea     rax, [rbp+arg_10]
0x180023ada  mov     [rsp+40h+var_18], rax
0x180023adf  lea     rax, [rbp+arg_18]
0x180023ae3  mov     [rsp+40h+var_20], rax
0x180023ae8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180023aed  mov     rcx, [rbx+30h]; P
0x180023af1  test    rcx, rcx
0x180023af4  jz      short loc_180023AFB
0x180023af6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023afb  mov     rcx, rbx; P
0x180023afe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023b03  mov     eax, 8000FFFFh
0x180023b08  jmp     loc_180023C2B
0x180023b0d  mov     rax, [rbx+30h]
0x180023b11  mov     [rax], rcx
0x180023b14  inc     dword ptr [rbx+38h]
0x180023b17  inc     qword ptr [rbx+40h]
0x180023b1b  jmp     short loc_180023B43
0x180023b1d  mov     ecx, [rbx+28h]
0x180023b20  mov     rdx, [rbx+20h]
0x180023b24  sub     ecx, 1
0x180023b27  jz      short loc_180023B38
0x180023b29  mov     rax, rdx
0x180023b2c  add     rdx, 8
0x180023b30  mov     [rax], rdi
0x180023b33  add     ecx, 0FFFFFFFFh
0x180023b36  jnz     short loc_180023B29
0x180023b38  mov     ecx, [rbx+2Ch]
0x180023b3b  neg     ecx
0x180023b3d  shr     rdi, cl
0x180023b40  mov     [rdx], rdi
0x180023b43  mov     [r15], rbx
0x180023b46  xor     eax, eax
0x180023b48  jmp     loc_180023C2B
0x180023b4d  mov     eax, cs:dword_180069000
0x180023b53  mov     ebx, 8007000Eh
0x180023b58  cmp     eax, 2
0x180023b5b  jbe     short loc_180023BB6
0x180023b5d  mov     rcx, cs:qword_180069018
0x180023b64  mov     rax, cs:qword_180069010
0x180023b6b  test    al, 20h
0x180023b6d  jz      short loc_180023BB6
0x180023b6f  mov     rax, rcx
0x180023b72  and     eax, 20h
0x180023b75  cmp     rax, rcx
0x180023b78  jnz     short loc_180023BB6
0x180023b7a  lea     rax, aOnecoreXboxGam_41; "onecore\\xbox\\gameinput\\memory\\Readi"...
0x180023b81  mov     [rbp+arg_8], ebx
0x180023b84  mov     [rbp+arg_18], rax
0x180023b88  lea     rdx, unk_18005E9C8
0x180023b8f  lea     rax, [rbp+arg_8]
0x180023b93  mov     [rbp+arg_10], 30h ; '0'
0x180023b9a  mov     [rsp+40h+var_10], rax
0x180023b9f  lea     rax, [rbp+arg_10]
0x180023ba3  mov     [rsp+40h+var_18], rax
0x180023ba8  lea     rax, [rbp+arg_18]
0x180023bac  mov     [rsp+40h+var_20], rax
0x180023bb1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180023bb6  mov     rcx, r14; P
0x180023bb9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023bbe  jmp     short loc_180023C29
0x180023bc0  mov     eax, cs:dword_180069000
0x180023bc6  mov     ebx, 8007000Eh
0x180023bcb  cmp     eax, 2
0x180023bce  jbe     short loc_180023C29
0x180023bd0  mov     rcx, cs:qword_180069018
0x180023bd7  mov     rax, cs:qword_180069010
0x180023bde  test    al, 20h
0x180023be0  jz      short loc_180023C29
0x180023be2  mov     rax, rcx
0x180023be5  and     eax, 20h
0x180023be8  cmp     rax, rcx
0x180023beb  jnz     short loc_180023C29
0x180023bed  lea     rax, aOnecoreXboxGam_41; "onecore\\xbox\\gameinput\\memory\\Readi"...
0x180023bf4  mov     [rbp+arg_8], ebx
0x180023bf7  mov     [rbp+arg_18], rax
0x180023bfb  lea     rdx, byte_18005E8EB
0x180023c02  lea     rax, [rbp+arg_8]
0x180023c06  mov     [rbp+arg_10], 2Bh ; '+'
0x180023c0d  mov     [rsp+40h+var_10], rax
0x180023c12  lea     rax, [rbp+arg_10]
0x180023c16  mov     [rsp+40h+var_18], rax
0x180023c1b  lea     rax, [rbp+arg_18]
0x180023c1f  mov     [rsp+40h+var_20], rax
0x180023c24  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180023c29  mov     eax, ebx
0x180023c2b  mov     rbx, [rsp+40h+arg_0]
0x180023c33  add     rsp, 40h
0x180023c37  pop     r15
0x180023c39  pop     r14
0x180023c3b  pop     r13
0x180023c3d  pop     r12
0x180023c3f  pop     rdi
0x180023c40  pop     rsi
0x180023c41  pop     rbp
0x180023c42  retn
```
