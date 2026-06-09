# CMPEG2SplitterFilter::CreateInstance(IUnknown *,long *)

- ea: `0x180007cc0`
- end: `0x180007d6b`
- name: `?CreateInstance@CMPEG2SplitterFilter@@SAPEAVCUnknown@@PEAUIUnknown@@PEAJ@Z`
- size: `171`
- prototype: `struct CUnknown *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180007cc0`
- `0x18000b558`
- `0x18000b784`

## pseudocode

```c
struct CUnknown *__fastcall CMPEG2SplitterFilter::CreateInstance(struct IUnknown *a1, int *a2)
{
  CBaseSplitterFilter *v3; // rax
  const unsigned __int16 *v4; // rdx
  struct CBaseSplitterFilter *v5; // rbx
  CSplitterInputPin *v6; // rax
  int *v7; // r8
  int *v9; // [rsp+20h] [rbp-18h]

  v3 = (CBaseSplitterFilter *)operator new(0x190u);
  v5 = v3;
  if ( !v3 )
    return 0;
  CBaseSplitterFilter::CBaseSplitterFilter(v3, v4, a1, &CLSID_MMSPLITTER, v9);
  *(_QWORD *)v5 = &CMPEG2SplitterFilter::`vftable'{for `CUnknown'};
  *((_QWORD *)v5 + 3) = &CMPEG2SplitterFilter::`vftable'{for `IBaseFilter'};
  *((_QWORD *)v5 + 4) = &CMPEG2SplitterFilter::`vftable'{for `IAMovieSetup'};
  *((_QWORD *)v5 + 15) = &CMPEG2SplitterFilter::`vftable'{for `CBaseSplitterFilter'};
  *((_QWORD *)v5 + 48) = &CMPEG2SplitterFilter::`vftable'{for `IAMParse'};
  *((_QWORD *)v5 + 49) = &CMPEG2SplitterFilter::`vftable'{for `IAMStreamSelect'};
  v6 = (CSplitterInputPin *)operator new(0x1F8u);
  if ( v6 )
    v6 = CSplitterInputPin::CSplitterInputPin(v6, v5, v7);
  *((_QWORD *)v5 + 16) = v6;
  return v5;
}

```

## disassembly

```asm
0x180007cc0  mov     [rsp+arg_0], rbx
0x180007cc5  push    rdi
0x180007cc6  sub     rsp, 30h
0x180007cca  mov     rdi, rcx
0x180007ccd  mov     ecx, 190h; Size
0x180007cd2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007cd7  mov     rbx, rax
0x180007cda  test    rax, rax
0x180007cdd  jz      short loc_180007D5B
0x180007cdf  lea     r9, CLSID_MMSPLITTER; struct _GUID *
0x180007ce6  mov     r8, rdi; struct IUnknown *
0x180007ce9  mov     rcx, rax; this
0x180007cec  call    ??0CBaseSplitterFilter@@QEAA@PEBGPEAUIUnknown@@AEBU_GUID@@PEAJ@Z; CBaseSplitterFilter::CBaseSplitterFilter(ushort const *,IUnknown *,_GUID const &,long *)
0x180007cf1  lea     rax, ??_7CMPEG2SplitterFilter@@6BCUnknown@@@; const CMPEG2SplitterFilter::`vftable'{for `CUnknown'}
0x180007cf8  mov     ecx, 1F8h; Size
0x180007cfd  mov     [rbx], rax
0x180007d00  lea     rax, ??_7CMPEG2SplitterFilter@@6BIBaseFilter@@@; const CMPEG2SplitterFilter::`vftable'{for `IBaseFilter'}
0x180007d07  mov     [rbx+18h], rax
0x180007d0b  lea     rax, ??_7CMPEG2SplitterFilter@@6BIAMovieSetup@@@; const CMPEG2SplitterFilter::`vftable'{for `IAMovieSetup'}
0x180007d12  mov     [rbx+20h], rax
0x180007d16  lea     rax, ??_7CMPEG2SplitterFilter@@6BCBaseSplitterFilter@@@; const CMPEG2SplitterFilter::`vftable'{for `CBaseSplitterFilter'}
0x180007d1d  mov     [rbx+78h], rax
0x180007d21  lea     rax, ??_7CMPEG2SplitterFilter@@6BIAMParse@@@; const CMPEG2SplitterFilter::`vftable'{for `IAMParse'}
0x180007d28  mov     [rbx+180h], rax
0x180007d2f  lea     rax, ??_7CMPEG2SplitterFilter@@6BIAMStreamSelect@@@; const CMPEG2SplitterFilter::`vftable'{for `IAMStreamSelect'}
0x180007d36  mov     [rbx+188h], rax
0x180007d3d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007d42  test    rax, rax
0x180007d45  jz      short loc_180007D52
0x180007d47  mov     rdx, rbx; struct CBaseSplitterFilter *
0x180007d4a  mov     rcx, rax; this
0x180007d4d  call    ??0CSplitterInputPin@@QEAA@PEAVCBaseSplitterFilter@@PEAJ@Z; CSplitterInputPin::CSplitterInputPin(CBaseSplitterFilter *,long *)
0x180007d52  mov     [rbx+80h], rax
0x180007d59  jmp     short loc_180007D5D
0x180007d5b  xor     ebx, ebx
0x180007d5d  mov     rax, rbx
0x180007d60  mov     rbx, [rsp+38h+arg_0]
0x180007d65  add     rsp, 30h
0x180007d69  pop     rdi
0x180007d6a  retn
```
