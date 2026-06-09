# CMediaSampleWrapperPool::WrapAndComplete(IMediaSample *,uchar *,int,int,CTStickyVal<int> *)

- ea: `0x18002c170`
- end: `0x18002c220`
- name: `?WrapAndComplete@CMediaSampleWrapperPool@@UEAAJPEAUIMediaSample@@PEAEHHPEAV?$CTStickyVal@H@@@Z`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180023c8c`
- `0x18002b80c`
- `0x18002c170`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002c1d7`
- `KERNEL32!LeaveCriticalSection` at `0x18002c1d7`
- `KERNEL32!EnterCriticalSection` at `0x18002c1f2`
- `KERNEL32!EnterCriticalSection` at `0x18002c1f2`

## pseudocode

```c
__int64 __fastcall CMediaSampleWrapperPool::WrapAndComplete(
        __int64 a1,
        struct IMediaSample *a2,
        unsigned __int8 *a3,
        int a4,
        int a5)
{
  int MediaSampleWrapper; // edi
  struct IMediaSample *v7; // rbx
  _BOOL8 v8; // rdx
  struct IMediaSample *v10; // [rsp+30h] [rbp-18h] BYREF

  v10 = 0;
  MediaSampleWrapper = CMediaSampleWrapperPool::GetMediaSampleWrapper_(
                         (CMediaSampleWrapperPool *)a1,
                         a2,
                         a3,
                         a4,
                         (struct CMediaSampleWrapper **)&v10);
  if ( MediaSampleWrapper >= 0 )
  {
    v7 = v10;
    if ( v10 )
    {
      v8 = *(_DWORD *)(a1 + 120) && a5;
      ((void (__fastcall *)(struct IMediaSample *, _BOOL8))v10->lpVtbl->SetDiscontinuity)(v10, v8);
      LeaveCriticalSection(*(LPCRITICAL_SECTION *)(a1 + 128));
      MediaSampleWrapper = CMPEG2DemuxOutputPin::SendSample(*(CMPEG2DemuxOutputPin **)(a1 + 112), v7);
      EnterCriticalSection(*(LPCRITICAL_SECTION *)(a1 + 128));
      ((void (__fastcall *)(struct IMediaSample *))v7->lpVtbl->Release)(v7);
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
0x18002c170  mov     r11, rsp
0x18002c173  mov     [r11+8], rbx
0x18002c177  mov     [r11+10h], rsi
0x18002c17b  push    rdi
0x18002c17c  sub     rsp, 40h
0x18002c180  lea     rax, [r11-18h]
0x18002c184  mov     qword ptr [r11-18h], 0
0x18002c18c  mov     [r11-28h], rax
0x18002c190  mov     rsi, rcx
0x18002c193  call    ?GetMediaSampleWrapper_@CMediaSampleWrapperPool@@AEAAJPEAUIMediaSample@@PEAEHPEAPEAVCMediaSampleWrapper@@@Z; CMediaSampleWrapperPool::GetMediaSampleWrapper_(IMediaSample *,uchar *,int,CMediaSampleWrapper * *)
0x18002c198  mov     edi, eax
0x18002c19a  test    eax, eax
0x18002c19c  js      short loc_18002C20E
0x18002c19e  mov     rbx, [rsp+48h+var_18]
0x18002c1a3  test    rbx, rbx
0x18002c1a6  jz      short loc_18002C209
0x18002c1a8  cmp     dword ptr [rsi+78h], 0
0x18002c1ac  mov     rax, [rbx]
0x18002c1af  jz      short loc_18002C1BF
0x18002c1b1  cmp     [rsp+48h+arg_20], 0
0x18002c1b6  jz      short loc_18002C1BF
0x18002c1b8  mov     edx, 1
0x18002c1bd  jmp     short loc_18002C1C1
0x18002c1bf  xor     edx, edx
0x18002c1c1  mov     rax, [rax+80h]
0x18002c1c8  mov     rcx, rbx
0x18002c1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1d0  mov     rcx, [rsi+80h]; lpCriticalSection
0x18002c1d7  call    cs:__imp_LeaveCriticalSection
0x18002c1dd  mov     rcx, [rsi+70h]; this
0x18002c1e1  mov     rdx, rbx; struct IMediaSample *
0x18002c1e4  call    ?SendSample@CMPEG2DemuxOutputPin@@QEAAJPEAUIMediaSample@@@Z; CMPEG2DemuxOutputPin::SendSample(IMediaSample *)
0x18002c1e9  mov     rcx, [rsi+80h]; lpCriticalSection
0x18002c1f0  mov     edi, eax
0x18002c1f2  call    cs:__imp_EnterCriticalSection
0x18002c1f8  mov     rax, [rbx]
0x18002c1fb  mov     rcx, rbx
0x18002c1fe  mov     rax, [rax+10h]
0x18002c202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c207  jmp     short loc_18002C20E
0x18002c209  mov     edi, 8000FFFFh
0x18002c20e  mov     rbx, [rsp+48h+arg_0]
0x18002c213  mov     eax, edi
0x18002c215  mov     rsi, [rsp+48h+arg_8]
0x18002c21a  add     rsp, 40h
0x18002c21e  pop     rdi
0x18002c21f  retn
```
