# CMediaSampleCopyBuffer::WrapAndAttributeSample(Mpeg2DemuxAttributes::CAttributeList *,IMediaSample *,IMediaSample * *)

- ea: `0x18002bf7c`
- end: `0x18002c164`
- name: `?WrapAndAttributeSample@CMediaSampleCopyBuffer@@AEAAJPEAVCAttributeList@Mpeg2DemuxAttributes@@PEAUIMediaSample@@PEAPEAU4@@Z`
- size: `488`
- prototype: `int(CMediaSampleCopyBuffer *__hidden this, struct Mpeg2DemuxAttributes::CAttributeList *, struct IMediaSample *, struct IMediaSample **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18002b570`

## callees

- `0x180001048`
- `0x180001054`
- `0x180018940`
- `0x180018c74`
- `0x18002288c`
- `0x18002bf7c`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMediaSampleCopyBuffer::WrapAndAttributeSample(
        CMediaSampleCopyBuffer *this,
        struct Mpeg2DemuxAttributes::CAttributeList *a2,
        struct IMediaSample *a3,
        struct IMediaSample **a4)
{
  struct IMediaSampleVtbl *lpVtbl; // rax
  int Instance; // ebx
  struct IMediaSample *Wrapper; // rax
  struct IMediaSample *v12; // rdi
  int v13; // edi
  __int64 v14; // r13
  unsigned int v15; // ebx
  void *v16; // r15
  void *v17; // r9
  _QWORD v18[2]; // [rsp+30h] [rbp-28h] BYREF
  struct _GUID v19; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v20; // [rsp+A8h] [rbp+50h] BYREF

  if ( *((_DWORD *)a2 + 40) )
  {
    *a4 = 0;
    lpVtbl = a3->lpVtbl;
    v18[0] = 0;
    if ( ((__int64 (__fastcall *)(struct IMediaSample *, GUID *, _QWORD *))lpVtbl->QueryInterface)(
           a3,
           &IID_IAttributeSet,
           v18) >= 0 )
      goto LABEL_9;
    if ( !*((_QWORD *)this + 7) )
    {
      Instance = Mpeg2DemuxAttributes::CDemuxIMediaSamplePool::CreateInstance((struct Mpeg2DemuxAttributes::CDemuxIMediaSamplePool **)this + 7);
      if ( Instance < 0 )
        goto LABEL_19;
    }
    Wrapper = Mpeg2DemuxAttributes::CDemuxIMediaSamplePool::GetWrapper(
                *((Mpeg2DemuxAttributes::CDemuxIMediaSamplePool **)this + 7),
                a3);
    v12 = Wrapper;
    if ( !Wrapper )
    {
      Instance = -2147024882;
      goto LABEL_19;
    }
    Instance = ((__int64 (__fastcall *)(struct IMediaSample *, GUID *, _QWORD *))Wrapper->lpVtbl->QueryInterface)(
                 Wrapper,
                 &IID_IAttributeSet,
                 v18);
    ((void (__fastcall *)(struct IMediaSample *))v12->lpVtbl->Release)(v12);
    if ( Instance >= 0 )
    {
LABEL_9:
      v13 = 0;
      if ( *((int *)a2 + 40) <= 0 )
      {
LABEL_18:
        Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IMediaSample **))v18[0])(
                     v18[0],
                     &IID_IMediaSample,
                     a4);
        goto LABEL_19;
      }
      while ( 1 )
      {
        v14 = v18[0];
        v20 = 0;
        v19 = 0;
        Instance = Mpeg2DemuxAttributes::CAttributeList::GetAttributeIndexed(a2, v13, &v19, 0, &v20);
        if ( Instance >= 0 )
        {
          v15 = v20;
          if ( v20 > *((_DWORD *)this + 18) )
          {
            v16 = operator new[](v20);
            if ( !v16 )
            {
              Instance = -2147024888;
              break;
            }
            operator delete(*((void **)this + 8));
            *((_QWORD *)this + 8) = v16;
            *((_DWORD *)this + 18) = v15;
          }
          v17 = (void *)*((_QWORD *)this + 8);
          v20 = *((_DWORD *)this + 18);
          Instance = Mpeg2DemuxAttributes::CAttributeList::GetAttributeIndexed(a2, v13, &v19, v17, &v20);
          if ( Instance >= 0 )
            Instance = (*(__int64 (__fastcall **)(__int64, struct _GUID *, _QWORD, _QWORD))(*(_QWORD *)v14 + 24LL))(
                         v14,
                         &v19,
                         *((_QWORD *)this + 8),
                         v20);
        }
        if ( Instance < 0 )
          break;
        if ( ++v13 >= *((_DWORD *)a2 + 40) )
          goto LABEL_18;
      }
    }
LABEL_19:
    if ( v18[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v18[0] + 16LL))(v18[0]);
    return (unsigned int)Instance;
  }
  else
  {
    *a4 = a3;
    ((void (__fastcall *)(struct IMediaSample *))a3->lpVtbl->AddRef)(a3);
    return 0;
  }
}

```

## disassembly

```asm
0x18002bf7c  push    rbp
0x18002bf7e  push    rbx
0x18002bf7f  push    rsi
0x18002bf80  push    rdi
0x18002bf81  push    r12
0x18002bf83  push    r13
0x18002bf85  push    r14
0x18002bf87  push    r15
0x18002bf89  mov     rbp, rsp
0x18002bf8c  sub     rsp, 58h
0x18002bf90  xor     r13d, r13d
0x18002bf93  mov     rsi, rcx
0x18002bf96  mov     r12, r9
0x18002bf99  mov     rdi, r8
0x18002bf9c  mov     r14, rdx
0x18002bf9f  mov     rcx, r8
0x18002bfa2  cmp     [rdx+0A0h], r13d
0x18002bfa9  jnz     short loc_18002BFC1
0x18002bfab  mov     [r9], r8
0x18002bfae  mov     rax, [r8]
0x18002bfb1  mov     rax, [rax+8]
0x18002bfb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfba  xor     eax, eax
0x18002bfbc  jmp     loc_18002C14C
0x18002bfc1  mov     [r9], r13
0x18002bfc4  lea     rdx, IID_IAttributeSet
0x18002bfcb  mov     rax, [r8]
0x18002bfce  lea     r8, [rbp+var_28]
0x18002bfd2  mov     [rbp+var_28], r13
0x18002bfd6  mov     rax, [rax]
0x18002bfd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfde  test    eax, eax
0x18002bfe0  jns     short loc_18002C04C
0x18002bfe2  lea     r15, [rsi+38h]
0x18002bfe6  cmp     [r15], r13
0x18002bfe9  jnz     short loc_18002BFFD
0x18002bfeb  mov     rcx, r15; struct Mpeg2DemuxAttributes::CDemuxIMediaSamplePool **
0x18002bfee  call    ?CreateInstance@CDemuxIMediaSamplePool@Mpeg2DemuxAttributes@@SAJPEAPEAV12@@Z; Mpeg2DemuxAttributes::CDemuxIMediaSamplePool::CreateInstance(Mpeg2DemuxAttributes::CDemuxIMediaSamplePool * *)
0x18002bff3  mov     ebx, eax
0x18002bff5  test    eax, eax
0x18002bff7  js      loc_18002C135
0x18002bffd  mov     rcx, [r15]; this
0x18002c000  mov     rdx, rdi; struct IMediaSample *
0x18002c003  call    ?GetWrapper@CDemuxIMediaSamplePool@Mpeg2DemuxAttributes@@QEAAPEAUIMediaSample@@PEAU3@@Z; Mpeg2DemuxAttributes::CDemuxIMediaSamplePool::GetWrapper(IMediaSample *)
0x18002c008  mov     rdi, rax
0x18002c00b  test    rax, rax
0x18002c00e  jnz     short loc_18002C01A
0x18002c010  mov     ebx, 8007000Eh
0x18002c015  jmp     loc_18002C135
0x18002c01a  mov     rax, [rax]
0x18002c01d  lea     r8, [rbp+var_28]
0x18002c021  lea     rdx, IID_IAttributeSet
0x18002c028  mov     rcx, rdi
0x18002c02b  mov     rax, [rax]
0x18002c02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c033  mov     ebx, eax
0x18002c035  mov     rax, [rdi]
0x18002c038  mov     rcx, rdi
0x18002c03b  mov     rax, [rax+10h]
0x18002c03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c044  test    ebx, ebx
0x18002c046  js      loc_18002C135
0x18002c04c  mov     edi, r13d
0x18002c04f  cmp     [r14+0A0h], r13d
0x18002c056  jle     loc_18002C11A
0x18002c05c  mov     r13, [rbp+var_28]
0x18002c060  lea     rax, [rbp+arg_8]
0x18002c064  xorps   xmm0, xmm0
0x18002c067  mov     [rsp+58h+var_38], rax; unsigned int *
0x18002c06c  xor     r9d, r9d; void *
0x18002c06f  mov     [rbp+arg_8], 0
0x18002c076  lea     r8, [rbp+var_18]; struct _GUID *
0x18002c07a  mov     edx, edi; int
0x18002c07c  mov     rcx, r14; this
0x18002c07f  movups  xmmword ptr [rbp+var_18.Data1], xmm0
0x18002c083  call    ?GetAttributeIndexed@CAttributeList@Mpeg2DemuxAttributes@@QEAAJJPEAU_GUID@@PEAXPEAK@Z; Mpeg2DemuxAttributes::CAttributeList::GetAttributeIndexed(long,_GUID *,void *,ulong *)
0x18002c088  mov     ebx, eax
0x18002c08a  test    eax, eax
0x18002c08c  js      short loc_18002C107
0x18002c08e  mov     ebx, [rbp+arg_8]
0x18002c091  cmp     ebx, [rsi+48h]
0x18002c094  jbe     short loc_18002C0B9
0x18002c096  mov     ecx, ebx; unsigned __int64
0x18002c098  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002c09d  mov     r15, rax
0x18002c0a0  test    rax, rax
0x18002c0a3  jz      loc_18002C15D
0x18002c0a9  mov     rcx, [rsi+40h]; void *
0x18002c0ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002c0b2  mov     [rsi+40h], r15
0x18002c0b6  mov     [rsi+48h], ebx
0x18002c0b9  mov     eax, [rsi+48h]
0x18002c0bc  lea     r8, [rbp+var_18]; struct _GUID *
0x18002c0c0  mov     r9, [rsi+40h]; void *
0x18002c0c4  mov     edx, edi; int
0x18002c0c6  mov     [rbp+arg_8], eax
0x18002c0c9  mov     rcx, r14; this
0x18002c0cc  lea     rax, [rbp+arg_8]
0x18002c0d0  mov     [rsp+58h+var_38], rax; unsigned int *
0x18002c0d5  call    ?GetAttributeIndexed@CAttributeList@Mpeg2DemuxAttributes@@QEAAJJPEAU_GUID@@PEAXPEAK@Z; Mpeg2DemuxAttributes::CAttributeList::GetAttributeIndexed(long,_GUID *,void *,ulong *)
0x18002c0da  mov     ebx, eax
0x18002c0dc  test    eax, eax
0x18002c0de  js      short loc_18002C107
0x18002c0e0  mov     rax, [r13+0]
0x18002c0e4  lea     rdx, [rbp+var_18]
0x18002c0e8  movaps  xmm0, xmmword ptr [rbp+var_18.Data1]
0x18002c0ec  mov     rcx, r13
0x18002c0ef  mov     r9d, [rbp+arg_8]
0x18002c0f3  mov     r8, [rsi+40h]
0x18002c0f7  mov     rax, [rax+18h]
0x18002c0fb  movdqa  xmmword ptr [rbp+var_18.Data1], xmm0
0x18002c100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c105  mov     ebx, eax
0x18002c107  test    ebx, ebx
0x18002c109  js      short loc_18002C135
0x18002c10b  inc     edi
0x18002c10d  cmp     edi, [r14+0A0h]
0x18002c114  jl      loc_18002C05C
0x18002c11a  mov     rcx, [rbp+var_28]
0x18002c11e  lea     rdx, IID_IMediaSample
0x18002c125  mov     r8, r12
0x18002c128  mov     rax, [rcx]
0x18002c12b  mov     rax, [rax]
0x18002c12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c133  mov     ebx, eax
0x18002c135  mov     rcx, [rbp+var_28]
0x18002c139  test    rcx, rcx
0x18002c13c  jz      short loc_18002C14A
0x18002c13e  mov     rdx, [rcx]
0x18002c141  mov     rax, [rdx+10h]
0x18002c145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c14a  mov     eax, ebx
0x18002c14c  add     rsp, 58h
0x18002c150  pop     r15
0x18002c152  pop     r14
0x18002c154  pop     r13
0x18002c156  pop     r12
0x18002c158  pop     rdi
0x18002c159  pop     rsi
0x18002c15a  pop     rbx
0x18002c15b  pop     rbp
0x18002c15c  retn
0x18002c15d  mov     ebx, 80070008h
0x18002c162  jmp     short loc_18002C135
```
