# AC3ParserFilter::CreateInstance(IUnknown *,long *)

- ea: `0x18000a5d0`
- end: `0x18000a672`
- name: `?CreateInstance@AC3ParserFilter@@SAPEAVCUnknown@@PEAUIUnknown@@PEAJ@Z`
- size: `162`
- prototype: `struct CUnknown *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x18000a5d0`
- `0x18000b558`
- `0x18000b784`

## pseudocode

```c
struct CUnknown *__fastcall AC3ParserFilter::CreateInstance(struct IUnknown *a1, int *a2)
{
  CBaseSplitterFilter *v4; // rax
  const unsigned __int16 *v5; // rdx
  struct CBaseSplitterFilter *v6; // rbx
  CSplitterInputPin *v7; // rax
  int *v8; // r8
  int *v10; // [rsp+20h] [rbp-18h]

  v4 = (CBaseSplitterFilter *)operator new(0x180u);
  v6 = v4;
  if ( v4 )
  {
    CBaseSplitterFilter::CBaseSplitterFilter(v4, v5, a1, &CLSID_MM_AC3_Parser, v10);
    *(_QWORD *)v6 = &AC3ParserFilter::`vftable'{for `CUnknown'};
    *((_QWORD *)v6 + 3) = &CBaseSplitterFilter::`vftable'{for `IBaseFilter'};
    *((_QWORD *)v6 + 4) = &AC3ParserFilter::`vftable'{for `IAMovieSetup'};
    *((_QWORD *)v6 + 15) = &CMPEG2SplitterFilter::`vftable'{for `CBaseSplitterFilter'};
    v7 = (CSplitterInputPin *)operator new(0x1F8u);
    if ( v7 )
      v7 = CSplitterInputPin::CSplitterInputPin(v7, v6, v8);
    *((_QWORD *)v6 + 16) = v7;
  }
  else
  {
    *a2 = -2147024882;
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18000a5d0  mov     [rsp+arg_0], rbx
0x18000a5d5  mov     [rsp+arg_8], rsi
0x18000a5da  push    rdi
0x18000a5db  sub     rsp, 30h
0x18000a5df  mov     rsi, rcx
0x18000a5e2  mov     rdi, rdx
0x18000a5e5  mov     ecx, 180h; Size
0x18000a5ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a5ef  mov     rbx, rax
0x18000a5f2  test    rax, rax
0x18000a5f5  jz      short loc_18000A657
0x18000a5f7  lea     r9, CLSID_MM_AC3_Parser; struct _GUID *
0x18000a5fe  mov     r8, rsi; struct IUnknown *
0x18000a601  mov     rcx, rax; this
0x18000a604  call    ??0CBaseSplitterFilter@@QEAA@PEBGPEAUIUnknown@@AEBU_GUID@@PEAJ@Z; CBaseSplitterFilter::CBaseSplitterFilter(ushort const *,IUnknown *,_GUID const &,long *)
0x18000a609  lea     rax, ??_7AC3ParserFilter@@6BCUnknown@@@; const AC3ParserFilter::`vftable'{for `CUnknown'}
0x18000a610  mov     ecx, 1F8h; Size
0x18000a615  mov     [rbx], rax
0x18000a618  lea     rax, ??_7CBaseSplitterFilter@@6BIBaseFilter@@@; const CBaseSplitterFilter::`vftable'{for `IBaseFilter'}
0x18000a61f  mov     [rbx+18h], rax
0x18000a623  lea     rax, ??_7AC3ParserFilter@@6BIAMovieSetup@@@; const AC3ParserFilter::`vftable'{for `IAMovieSetup'}
0x18000a62a  mov     [rbx+20h], rax
0x18000a62e  lea     rax, ??_7CMPEG2SplitterFilter@@6BCBaseSplitterFilter@@@; const CMPEG2SplitterFilter::`vftable'{for `CBaseSplitterFilter'}
0x18000a635  mov     [rbx+78h], rax
0x18000a639  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a63e  test    rax, rax
0x18000a641  jz      short loc_18000A64E
0x18000a643  mov     rdx, rbx; struct CBaseSplitterFilter *
0x18000a646  mov     rcx, rax; this
0x18000a649  call    ??0CSplitterInputPin@@QEAA@PEAVCBaseSplitterFilter@@PEAJ@Z; CSplitterInputPin::CSplitterInputPin(CBaseSplitterFilter *,long *)
0x18000a64e  mov     [rbx+80h], rax
0x18000a655  jmp     short loc_18000A65F
0x18000a657  mov     dword ptr [rdi], 8007000Eh
0x18000a65d  xor     ebx, ebx
0x18000a65f  mov     rsi, [rsp+38h+arg_8]
0x18000a664  mov     rax, rbx
0x18000a667  mov     rbx, [rsp+38h+arg_0]
0x18000a66c  add     rsp, 30h
0x18000a670  pop     rdi
0x18000a671  retn
```
