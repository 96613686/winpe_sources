# CMediaSampleCopyBuffer::CompleteCopyBuffer(unsigned __int64,uchar *,int,int,__int64 *,__int64 *,CTStickyVal<int> *,Mpeg2DemuxAttributes::CAttributeList *)

- ea: `0x18002b570`
- end: `0x18002b686`
- name: `?CompleteCopyBuffer@CMediaSampleCopyBuffer@@UEAAJ_KPEAEHHPEA_J2PEAV?$CTStickyVal@H@@PEAVCAttributeList@Mpeg2DemuxAttributes@@@Z`
- size: `278`
- prototype: `__int64 __usercall@<rax>(CMediaSampleCopyBuffer *this@<rcx>, struct IMediaSample *@<rdx>, int, __int64, __int64, int, struct Mpeg2DemuxAttributes::CAttributeList *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002b570`
- `0x18002bd38`
- `0x18002bf7c`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMediaSampleCopyBuffer::CompleteCopyBuffer(
        CMediaSampleCopyBuffer *this,
        struct IMediaSample *a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        int a8,
        struct Mpeg2DemuxAttributes::CAttributeList *a9)
{
  struct IMediaSampleVtbl *lpVtbl; // rax
  int v12; // ebx
  unsigned int v13; // ebp
  __int64 v14; // rcx
  struct IMediaSample *v15; // rdx
  struct IMediaSample *v17; // [rsp+58h] [rbp+10h] BYREF

  lpVtbl = a2->lpVtbl;
  v17 = 0;
  v12 = ((__int64 (__fastcall *)(struct IMediaSample *, _QWORD))lpVtbl->SetActualDataLength)(a2, a4);
  if ( v12 >= 0 )
  {
    v13 = 1;
    if ( a6 && a7 )
    {
      v12 = ((__int64 (__fastcall *)(struct IMediaSample *))a2->lpVtbl->SetTime)(a2);
      if ( v12 < 0 )
        goto LABEL_17;
      ((void (__fastcall *)(struct IMediaSample *, _QWORD))a2->lpVtbl->SetSyncPoint)(a2, *((unsigned int *)this + 11));
      v14 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL);
      if ( v14 && *((_DWORD *)this + 11) )
        ++*(_QWORD *)(v14 + 48);
    }
    if ( !a5 || !*((_DWORD *)this + 10) )
      v13 = 0;
    ((void (__fastcall *)(struct IMediaSample *, _QWORD))a2->lpVtbl->SetDiscontinuity)(a2, v13);
    if ( a9 && *((int *)a9 + 40) > 0 )
    {
      v12 = CMediaSampleCopyBuffer::WrapAndAttributeSample(this, a9, a2, &v17);
      if ( v12 < 0 )
        goto LABEL_17;
      v15 = v17;
    }
    else
    {
      v15 = a2;
    }
    v12 = CMediaSampleCopyBuffer::SendSample(this, v15);
  }
LABEL_17:
  if ( v17 )
    ((void (__fastcall *)(struct IMediaSample *))v17->lpVtbl->Release)(v17);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002b570  push    rbx
0x18002b572  push    rbp
0x18002b573  push    rsi
0x18002b574  push    rdi
0x18002b575  sub     rsp, 28h
0x18002b579  mov     rax, [rdx]
0x18002b57c  mov     rdi, rdx
0x18002b57f  mov     rsi, rcx
0x18002b582  mov     [rsp+48h+arg_8], 0
0x18002b58b  mov     edx, r9d
0x18002b58e  mov     rcx, rdi
0x18002b591  mov     rax, [rax+60h]
0x18002b595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b59a  mov     ebx, eax
0x18002b59c  test    eax, eax
0x18002b59e  js      loc_18002B665
0x18002b5a4  mov     rdx, [rsp+48h+arg_28]
0x18002b5a9  mov     ebp, 1
0x18002b5ae  test    rdx, rdx
0x18002b5b1  jz      short loc_18002B602
0x18002b5b3  mov     r8, [rsp+48h+arg_30]
0x18002b5bb  test    r8, r8
0x18002b5be  jz      short loc_18002B602
0x18002b5c0  mov     rax, [rdi]
0x18002b5c3  mov     rcx, rdi
0x18002b5c6  mov     rax, [rax+30h]
0x18002b5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5cf  mov     ebx, eax
0x18002b5d1  test    eax, eax
0x18002b5d3  js      loc_18002B665
0x18002b5d9  mov     rax, [rdi]
0x18002b5dc  mov     rcx, rdi
0x18002b5df  mov     edx, [rsi+2Ch]
0x18002b5e2  mov     rax, [rax+40h]
0x18002b5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5eb  mov     rax, [rsi+10h]
0x18002b5ef  mov     rcx, [rax+8]
0x18002b5f3  test    rcx, rcx
0x18002b5f6  jz      short loc_18002B602
0x18002b5f8  cmp     dword ptr [rsi+2Ch], 0
0x18002b5fc  jz      short loc_18002B602
0x18002b5fe  add     [rcx+30h], rbp
0x18002b602  cmp     [rsp+48h+arg_20], 0
0x18002b607  mov     rax, [rdi]
0x18002b60a  jz      short loc_18002B612
0x18002b60c  cmp     dword ptr [rsi+28h], 0
0x18002b610  jnz     short loc_18002B614
0x18002b612  xor     ebp, ebp
0x18002b614  mov     rax, [rax+80h]
0x18002b61b  mov     edx, ebp
0x18002b61d  mov     rcx, rdi
0x18002b620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b625  mov     rdx, [rsp+48h+arg_40]; struct Mpeg2DemuxAttributes::CAttributeList *
0x18002b62d  test    rdx, rdx
0x18002b630  jz      short loc_18002B658
0x18002b632  cmp     dword ptr [rdx+0A0h], 0
0x18002b639  jle     short loc_18002B658
0x18002b63b  lea     r9, [rsp+48h+arg_8]; struct IMediaSample **
0x18002b640  mov     r8, rdi; struct IMediaSample *
0x18002b643  mov     rcx, rsi; this
0x18002b646  call    ?WrapAndAttributeSample@CMediaSampleCopyBuffer@@AEAAJPEAVCAttributeList@Mpeg2DemuxAttributes@@PEAUIMediaSample@@PEAPEAU4@@Z; CMediaSampleCopyBuffer::WrapAndAttributeSample(Mpeg2DemuxAttributes::CAttributeList *,IMediaSample *,IMediaSample * *)
0x18002b64b  mov     ebx, eax
0x18002b64d  test    eax, eax
0x18002b64f  js      short loc_18002B665
0x18002b651  mov     rdx, [rsp+48h+arg_8]
0x18002b656  jmp     short loc_18002B65B
0x18002b658  mov     rdx, rdi; struct IMediaSample *
0x18002b65b  mov     rcx, rsi; this
0x18002b65e  call    ?SendSample@CMediaSampleCopyBuffer@@AEAAJPEAUIMediaSample@@@Z; CMediaSampleCopyBuffer::SendSample(IMediaSample *)
0x18002b663  mov     ebx, eax
0x18002b665  mov     rcx, [rsp+48h+arg_8]
0x18002b66a  test    rcx, rcx
0x18002b66d  jz      short loc_18002B67B
0x18002b66f  mov     rax, [rcx]
0x18002b672  mov     rax, [rax+10h]
0x18002b676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b67b  mov     eax, ebx
0x18002b67d  add     rsp, 28h
0x18002b681  pop     rdi
0x18002b682  pop     rsi
0x18002b683  pop     rbp
0x18002b684  pop     rbx
0x18002b685  retn
```
