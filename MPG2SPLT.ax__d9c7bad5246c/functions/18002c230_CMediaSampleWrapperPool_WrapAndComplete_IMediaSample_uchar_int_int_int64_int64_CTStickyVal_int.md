# CMediaSampleWrapperPool::WrapAndComplete(IMediaSample *,uchar *,int,int,__int64 *,__int64 *,CTStickyVal<int> *)

- ea: `0x18002c230`
- end: `0x18002c31c`
- name: `?WrapAndComplete@CMediaSampleWrapperPool@@UEAAJPEAUIMediaSample@@PEAEHHPEA_J2PEAV?$CTStickyVal@H@@@Z`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180023c8c`
- `0x18002b80c`
- `0x18002c230`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002c2d3`
- `KERNEL32!LeaveCriticalSection` at `0x18002c2d3`
- `KERNEL32!EnterCriticalSection` at `0x18002c2ee`
- `KERNEL32!EnterCriticalSection` at `0x18002c2ee`

## pseudocode

```c
__int64 __fastcall CMediaSampleWrapperPool::WrapAndComplete(
        __int64 a1,
        struct IMediaSample *a2,
        unsigned __int8 *a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  int MediaSampleWrapper; // edi
  struct IMediaSample *v9; // rbx
  _BOOL8 v10; // rdx
  struct IMediaSample *v12; // [rsp+30h] [rbp-18h] BYREF

  v12 = 0;
  MediaSampleWrapper = CMediaSampleWrapperPool::GetMediaSampleWrapper_(
                         (CMediaSampleWrapperPool *)a1,
                         a2,
                         a3,
                         a4,
                         (struct CMediaSampleWrapper **)&v12);
  if ( MediaSampleWrapper >= 0 )
  {
    v9 = v12;
    if ( v12 )
    {
      MediaSampleWrapper = ((__int64 (__fastcall *)(struct IMediaSample *, __int64, __int64))v12->lpVtbl->SetTime)(
                             v12,
                             a6,
                             a7);
      if ( MediaSampleWrapper >= 0 )
      {
        v10 = a5 && *(_DWORD *)(a1 + 120);
        ((void (__fastcall *)(struct IMediaSample *, _BOOL8))v9->lpVtbl->SetDiscontinuity)(v9, v10);
        ((void (__fastcall *)(struct IMediaSample *, _QWORD))v9->lpVtbl->SetSyncPoint)(v9, *(unsigned int *)(a1 + 124));
        LeaveCriticalSection(*(LPCRITICAL_SECTION *)(a1 + 128));
        MediaSampleWrapper = CMPEG2DemuxOutputPin::SendSample(*(CMPEG2DemuxOutputPin **)(a1 + 112), v9);
        EnterCriticalSection(*(LPCRITICAL_SECTION *)(a1 + 128));
      }
      ((void (__fastcall *)(struct IMediaSample *))v9->lpVtbl->Release)(v9);
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  return (unsigned int)MediaSampleWrapper;
}

```

## disassembly

```asm
0x18002c230  mov     r11, rsp
0x18002c233  mov     [r11+8], rbx
0x18002c237  mov     [r11+10h], rsi
0x18002c23b  push    rdi
0x18002c23c  sub     rsp, 40h
0x18002c240  lea     rax, [r11-18h]
0x18002c244  mov     qword ptr [r11-18h], 0
0x18002c24c  mov     [r11-28h], rax
0x18002c250  mov     rsi, rcx
0x18002c253  call    ?GetMediaSampleWrapper_@CMediaSampleWrapperPool@@AEAAJPEAUIMediaSample@@PEAEHPEAPEAVCMediaSampleWrapper@@@Z; CMediaSampleWrapperPool::GetMediaSampleWrapper_(IMediaSample *,uchar *,int,CMediaSampleWrapper * *)
0x18002c258  mov     edi, eax
0x18002c25a  test    eax, eax
0x18002c25c  js      loc_18002C30A
0x18002c262  mov     rbx, [rsp+48h+var_18]
0x18002c267  test    rbx, rbx
0x18002c26a  jz      loc_18002C305
0x18002c270  mov     rax, [rbx]
0x18002c273  mov     rcx, rbx
0x18002c276  mov     r8, [rsp+48h+arg_30]
0x18002c27e  mov     rdx, [rsp+48h+arg_28]
0x18002c283  mov     rax, [rax+30h]
0x18002c287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c28c  mov     edi, eax
0x18002c28e  test    eax, eax
0x18002c290  js      short loc_18002C2F4
0x18002c292  cmp     [rsp+48h+arg_20], 0
0x18002c297  mov     rax, [rbx]
0x18002c29a  jz      short loc_18002C2A9
0x18002c29c  cmp     dword ptr [rsi+78h], 0
0x18002c2a0  jz      short loc_18002C2A9
0x18002c2a2  mov     edx, 1
0x18002c2a7  jmp     short loc_18002C2AB
0x18002c2a9  xor     edx, edx
0x18002c2ab  mov     rax, [rax+80h]
0x18002c2b2  mov     rcx, rbx
0x18002c2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2ba  mov     rax, [rbx]
0x18002c2bd  mov     rcx, rbx
0x18002c2c0  mov     edx, [rsi+7Ch]
0x18002c2c3  mov     rax, [rax+40h]
0x18002c2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2cc  mov     rcx, [rsi+80h]; lpCriticalSection
0x18002c2d3  call    cs:__imp_LeaveCriticalSection
0x18002c2d9  mov     rcx, [rsi+70h]; this
0x18002c2dd  mov     rdx, rbx; struct IMediaSample *
0x18002c2e0  call    ?SendSample@CMPEG2DemuxOutputPin@@QEAAJPEAUIMediaSample@@@Z; CMPEG2DemuxOutputPin::SendSample(IMediaSample *)
0x18002c2e5  mov     rcx, [rsi+80h]; lpCriticalSection
0x18002c2ec  mov     edi, eax
0x18002c2ee  call    cs:__imp_EnterCriticalSection
0x18002c2f4  mov     rax, [rbx]
0x18002c2f7  mov     rcx, rbx
0x18002c2fa  mov     rax, [rax+10h]
0x18002c2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c303  jmp     short loc_18002C30A
0x18002c305  mov     edi, 8000FFFFh
0x18002c30a  mov     rbx, [rsp+48h+arg_0]
0x18002c30f  mov     eax, edi
0x18002c311  mov     rsi, [rsp+48h+arg_8]
0x18002c316  add     rsp, 40h
0x18002c31a  pop     rdi
0x18002c31b  retn
```
