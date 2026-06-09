# CProgramStreamMapper::ProcessStream_(IMediaSample *,MPEG2_SYS_BUFFER *,CTStickyVal<int> *)

- ea: `0x180032688`
- end: `0x180032852`
- name: `?ProcessStream_@CProgramStreamMapper@@AEAAHPEAUIMediaSample@@PEAUMPEG2_SYS_BUFFER@@PEAV?$CTStickyVal@H@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64, struct IMediaSample *, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180031e10`

## callees

- `0x180001008`
- `0x180031798`
- `0x1800322f0`
- `0x180032688`
- `0x180033dfd`
- `0x180034010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800327a4`
- `ole32!CoTaskMemAlloc` at `0x1800327a4`

## pseudocode

```c
__int64 __fastcall CProgramStreamMapper::ProcessStream_(__int64 a1, struct IMediaSample *a2, __int64 a3, __int64 a4)
{
  int v4; // r11d
  unsigned int v8; // r11d
  bool v9; // cc
  _BYTE *v10; // rax
  int v11; // esi
  __int64 v12; // rax
  __int64 v13; // r11
  __int64 v14; // r14
  __int64 result; // rax
  __int64 v16; // rdi
  SIZE_T v17; // r12
  void *v18; // rax
  __int64 v19; // rax
  void *Src; // [rsp+90h] [rbp+8h]

  v4 = *(_DWORD *)(a3 + 28);
  if ( !*(_BYTE *)((v4 & 0x1FFF) + *(_QWORD *)(a1 + 112)) )
  {
    *(_DWORD *)(a3 + 28) = v4 & 0xFFFF9FFF | 0x2000;
    goto LABEL_18;
  }
  v8 = v4 & 0xFFFF9FFF | 0x4000;
  v9 = *(_DWORD *)(a3 + 8) <= 4;
  *(_DWORD *)(a3 + 28) = v8;
  if ( v9
    || (v10 = *(_BYTE **)a3, **(_BYTE **)a3)
    || v10[1]
    || v10[2] != 1
    || (v11 = 1, (unsigned __int8)v10[3] != (v8 & 0x1FFF)) )
  {
    v11 = 0;
  }
  v12 = *(_QWORD *)(a1 + 112);
  v13 = v8 & 0x1FFF;
  if ( !*(_BYTE *)(v13 + v12) )
    goto LABEL_18;
  v14 = *(_QWORD *)(*(_QWORD *)(a1 + 120) + 16LL * *(unsigned __int8 *)(v13 + v12) - 8);
  if ( !v14 )
    goto LABEL_18;
  if ( a2 )
  {
    CStreamMapContext::Process(v14, (_DWORD)a2, a3, 0, 0, 0, v11, 0, a4);
LABEL_18:
    CMpeg2Stats::OnPacket(*(CMpeg2Stats **)(a1 + 56), a2, (struct MPEG2_SYS_BUFFER *)a3);
    return 1;
  }
  result = (__int64)operator new(0x20u);
  v16 = result;
  if ( result )
  {
    *(_DWORD *)(result + 8) = 1;
    *(_QWORD *)result = &CScratchMediaSample::`vftable';
    *(_QWORD *)(result + 16) = 0;
    *(_DWORD *)(result + 24) = 0;
    v17 = *(int *)(a3 + 8);
    Src = *(void **)a3;
    v18 = CoTaskMemAlloc(v17);
    *(_QWORD *)(v16 + 16) = v18;
    if ( v18 )
    {
      memcpy_0(v18, Src, v17);
      v19 = *(_QWORD *)(v16 + 16);
      *(_DWORD *)(v16 + 24) = v17;
      *(_QWORD *)(a3 + 16) = v19;
      *(_QWORD *)a3 = v19;
      CStreamMapContext::Process(v14, v16, a3, 0, 0, 0, v11, 0, a4);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    goto LABEL_18;
  }
  return result;
}

```

## disassembly

```asm
0x180032688  mov     [rsp+arg_8], rbx
0x18003268d  mov     [rsp+arg_18], r9
0x180032692  push    rbp
0x180032693  push    rsi
0x180032694  push    rdi
0x180032695  push    r12
0x180032697  push    r13
0x180032699  push    r14
0x18003269b  push    r15
0x18003269d  sub     rsp, 50h
0x1800326a1  mov     r11d, [r8+1Ch]
0x1800326a5  mov     r15, rdx
0x1800326a8  mov     rax, [rcx+70h]
0x1800326ac  mov     r10d, r11d
0x1800326af  mov     edx, 1FFFh
0x1800326b4  xor     r12d, r12d
0x1800326b7  and     r10, rdx
0x1800326ba  mov     rbx, r8
0x1800326bd  mov     rbp, rcx
0x1800326c0  cmp     [r10+rax], r12b
0x1800326c4  jz      loc_180032818
0x1800326ca  btr     r11d, 0Dh
0x1800326cf  bts     r11d, 0Eh
0x1800326d4  cmp     dword ptr [r8+8], 4
0x1800326d9  mov     [r8+1Ch], r11d
0x1800326dd  jle     short loc_180032705
0x1800326df  mov     rax, [r8]
0x1800326e2  cmp     [rax], r12b
0x1800326e5  jnz     short loc_180032705
0x1800326e7  cmp     [rax+1], r12b
0x1800326eb  jnz     short loc_180032705
0x1800326ed  cmp     byte ptr [rax+2], 1
0x1800326f1  jnz     short loc_180032705
0x1800326f3  movzx   ecx, byte ptr [rax+3]
0x1800326f7  lea     esi, [r12+1]
0x1800326fc  mov     eax, r11d
0x1800326ff  and     eax, edx
0x180032701  cmp     ecx, eax
0x180032703  jz      short loc_180032708
0x180032705  mov     esi, r12d
0x180032708  mov     rax, [rbp+70h]
0x18003270c  and     r11, rdx
0x18003270f  cmp     [r11+rax], r12b
0x180032713  jz      loc_180032826
0x180032719  movzx   ecx, byte ptr [r11+rax]
0x18003271e  mov     rax, [rbp+78h]
0x180032722  add     rcx, rcx
0x180032725  mov     r14, [rax+rcx*8-8]
0x18003272a  test    r14, r14
0x18003272d  jz      loc_180032826
0x180032733  test    r15, r15
0x180032736  jz      short loc_180032763
0x180032738  mov     [rsp+88h+var_48], r9
0x18003273d  mov     rdx, r15
0x180032740  mov     [rsp+88h+var_50], r12d
0x180032745  xor     r9d, r9d
0x180032748  mov     [rsp+88h+var_58], esi
0x18003274c  mov     rcx, r14
0x18003274f  mov     [rsp+88h+var_60], r12d
0x180032754  mov     [rsp+88h+var_68], r12d
0x180032759  call    ?Process@CStreamMapContext@@QEAAXPEAUIMediaSample@@PEAUMPEG2_SYS_BUFFER@@HHHHHPEAV?$CTStickyVal@H@@@Z; CStreamMapContext::Process(IMediaSample *,MPEG2_SYS_BUFFER *,int,int,int,int,int,CTStickyVal<int> *)
0x18003275e  jmp     loc_180032826
0x180032763  mov     ecx, 20h ; ' '; Size
0x180032768  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003276d  mov     rdi, rax
0x180032770  test    rax, rax
0x180032773  jz      loc_180032816
0x180032779  mov     dword ptr [rdi+8], 1
0x180032780  lea     rax, ??_7CScratchMediaSample@@6B@; const CScratchMediaSample::`vftable'
0x180032787  mov     [rdi], rax
0x18003278a  mov     [rdi+10h], r12
0x18003278e  mov     [rdi+18h], r12d
0x180032792  movsxd  r12, dword ptr [rbx+8]
0x180032796  mov     rax, [rbx]
0x180032799  mov     rcx, r12; cb
0x18003279c  mov     [rsp+88h+Src], rax
0x1800327a4  call    cs:__imp_CoTaskMemAlloc
0x1800327aa  mov     [rdi+10h], rax
0x1800327ae  test    rax, rax
0x1800327b1  jz      short loc_180032805
0x1800327b3  mov     rdx, [rsp+88h+Src]; Src
0x1800327bb  mov     r8, r12; Size
0x1800327be  mov     rcx, rax; void *
0x1800327c1  call    memcpy_0
0x1800327c6  mov     rax, [rdi+10h]
0x1800327ca  xor     r9d, r9d
0x1800327cd  mov     [rdi+18h], r12d
0x1800327d1  mov     r8, rbx
0x1800327d4  mov     [rbx+10h], rax
0x1800327d8  mov     rdx, rdi
0x1800327db  mov     [rbx], rax
0x1800327de  mov     rcx, r14
0x1800327e1  mov     rax, [rsp+88h+arg_18]
0x1800327e9  mov     [rsp+88h+var_48], rax
0x1800327ee  xor     eax, eax
0x1800327f0  mov     [rsp+88h+var_50], eax
0x1800327f4  mov     [rsp+88h+var_58], esi
0x1800327f8  mov     [rsp+88h+var_60], eax
0x1800327fc  mov     [rsp+88h+var_68], eax
0x180032800  call    ?Process@CStreamMapContext@@QEAAXPEAUIMediaSample@@PEAUMPEG2_SYS_BUFFER@@HHHHHPEAV?$CTStickyVal@H@@@Z; CStreamMapContext::Process(IMediaSample *,MPEG2_SYS_BUFFER *,int,int,int,int,int,CTStickyVal<int> *)
0x180032805  mov     rax, [rdi]
0x180032808  mov     rcx, rdi
0x18003280b  mov     rax, [rax+10h]
0x18003280f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032814  jmp     short loc_180032826
0x180032816  jmp     short loc_18003283A
0x180032818  btr     r11d, 0Eh
0x18003281d  bts     r11d, 0Dh
0x180032822  mov     [r8+1Ch], r11d
0x180032826  mov     rcx, [rbp+38h]; this
0x18003282a  mov     r8, rbx; struct MPEG2_SYS_BUFFER *
0x18003282d  mov     rdx, r15; struct IMediaSample *
0x180032830  call    ?OnPacket@CMpeg2Stats@@QEAAXPEAUIMediaSample@@PEAUMPEG2_SYS_BUFFER@@@Z; CMpeg2Stats::OnPacket(IMediaSample *,MPEG2_SYS_BUFFER *)
0x180032835  mov     eax, 1
0x18003283a  mov     rbx, [rsp+88h+arg_8]
0x180032842  add     rsp, 50h
0x180032846  pop     r15
0x180032848  pop     r14
0x18003284a  pop     r13
0x18003284c  pop     r12
0x18003284e  pop     rdi
0x18003284f  pop     rsi
0x180032850  pop     rbp
0x180032851  retn
```
