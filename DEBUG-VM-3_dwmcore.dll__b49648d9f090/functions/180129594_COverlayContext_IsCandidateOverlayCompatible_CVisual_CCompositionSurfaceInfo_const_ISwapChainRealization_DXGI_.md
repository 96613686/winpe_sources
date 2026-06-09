# COverlayContext::IsCandidateOverlayCompatible(CVisual *,CCompositionSurfaceInfo const *,ISwapChainRealization *,DXGI_MULTIPLANE_OVERLAY_ATTRIBUTES &,OverlaySize,bool,uint,bool)

- ea: `0x180129594`
- end: `0x180129741`
- name: `?IsCandidateOverlayCompatible@COverlayContext@@IEBA_NPEAVCVisual@@PEBVCCompositionSurfaceInfo@@PEAVISwapChainRealization@@AEAUDXGI_MULTIPLANE_OVERLAY_ATTRIBUTES@@W4OverlaySize@@_NI5@Z`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180129e4c`

## callees

- `0x1801288f8`
- `0x180129594`
- `0x180129748`
- `0x1802b6010`

## import_xrefs

- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180129638`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180129646`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180129654`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180129638`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180129646`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180129654`

## pseudocode

```c
char __fastcall COverlayContext::IsCandidateOverlayCompatible(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        char a7,
        unsigned int a8,
        char a9)
{
  char v12; // bp
  __int64 v13; // r10
  unsigned int v14; // r8d
  __int64 v15; // r9
  __int64 v16; // rax
  unsigned int i; // r8d
  __int64 v18; // r9
  __int64 v19; // rcx
  unsigned int v21; // [rsp+6Ch] [rbp+24h]

  v12 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a4 + 144LL))(a4) )
  {
    v13 = *(_QWORD *)(a1 + 96);
    v14 = 0;
    v15 = (*(_QWORD *)(a1 + 104) - v13) / 392;
    while ( v14 < (unsigned int)v15 )
    {
      if ( !a2 || *(_QWORD *)(392LL * v14 + v13 + 8) == a2 )
      {
        if ( v14 != -1 )
          return v12;
        break;
      }
      ++v14;
    }
    LODWORD(v16) = 0;
    v21 = 0;
    if ( a3 )
    {
      v16 = a3[5];
      v21 = HIDWORD(v16);
    }
    for ( i = 0; i < (unsigned int)v15; ++i )
    {
      if ( !a3 || *(_QWORD *)(*(_QWORD *)(392LL * i + v13 + 16) + 40LL) == __PAIR64__(v21, v16) )
      {
        if ( i != -1 )
          return v12;
        break;
      }
    }
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *))(*a3 + 200LL))(a3)
      && !IsRectEmpty((const RECT *)(a5 + 4))
      && !IsRectEmpty((const RECT *)(a5 + 20))
      && !IsRectEmpty((const RECT *)(a5 + 36)) )
    {
      LOBYTE(v18) = a7;
      if ( (unsigned __int8)COverlayContext::IsOverlayCompatibleScale(a1, a5, a6, v18) )
      {
        if ( a9 && *(_BYTE *)(a1 + 19476) || *(_BYTE *)(a1 + 44) || a8 > 2 )
          return 1;
      }
      else if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x200) != 0 )
      {
        McTemplateU0xq_EventWriteTransfer(v19, EVTDESC_DISPLAYSURFACE_REJECTCANDIDATE, a3[5], 4);
      }
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180129594  push    rbx
0x180129596  push    rbp
0x180129597  push    rsi
0x180129598  push    rdi
0x180129599  sub     rsp, 28h
0x18012959d  mov     rax, [r9]
0x1801295a0  mov     rsi, rcx
0x1801295a3  mov     rcx, r9
0x1801295a6  mov     rdi, r8
0x1801295a9  mov     rbx, rdx
0x1801295ac  xor     bpl, bpl
0x1801295af  mov     rax, [rax+90h]
0x1801295b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801295bb  test    al, al
0x1801295bd  jz      loc_180129694
0x1801295c3  mov     r10, [rsi+60h]
0x1801295c7  mov     rax, 5397829CBC14E5E1h
0x1801295d1  mov     rcx, [rsi+68h]
0x1801295d5  xor     r8d, r8d
0x1801295d8  sub     rcx, r10
0x1801295db  imul    rcx
0x1801295de  mov     r9, rdx
0x1801295e1  sar     r9, 7
0x1801295e5  mov     rax, r9
0x1801295e8  shr     rax, 3Fh
0x1801295ec  add     r9, rax
0x1801295ef  cmp     r8d, r9d
0x1801295f2  jb      loc_1801296A0
0x1801295f8  xor     eax, eax
0x1801295fa  mov     [rsp+48h+arg_18], rax
0x1801295ff  test    rdi, rdi
0x180129602  jz      short loc_18012960D
0x180129604  mov     rax, [rdi+28h]
0x180129608  mov     [rsp+48h+arg_18], rax
0x18012960d  xor     r8d, r8d
0x180129610  cmp     r8d, r9d
0x180129613  jb      loc_1801296BE
0x180129619  mov     rax, [rdi]
0x18012961c  mov     rcx, rdi
0x18012961f  mov     rax, [rax+0C8h]
0x180129626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012962b  test    al, al
0x18012962d  jz      short loc_180129694
0x18012962f  mov     rbx, [rsp+48h+arg_20]
0x180129634  lea     rcx, [rbx+4]; lprc
0x180129638  call    cs:__imp_IsRectEmpty
0x18012963e  test    eax, eax
0x180129640  jnz     short loc_180129694
0x180129642  lea     rcx, [rbx+14h]; lprc
0x180129646  call    cs:__imp_IsRectEmpty
0x18012964c  test    eax, eax
0x18012964e  jnz     short loc_180129694
0x180129650  lea     rcx, [rbx+24h]; lprc
0x180129654  call    cs:__imp_IsRectEmpty
0x18012965a  test    eax, eax
0x18012965c  jnz     short loc_180129694
0x18012965e  mov     r9b, [rsp+48h+arg_30]
0x180129666  mov     rdx, rbx
0x180129669  mov     r8d, [rsp+48h+arg_28]
0x18012966e  mov     rcx, rsi
0x180129671  call    ?IsOverlayCompatibleScale@COverlayContext@@IEBA_NPEAUDXGI_MULTIPLANE_OVERLAY_ATTRIBUTES@@W4OverlaySize@@_N@Z; COverlayContext::IsOverlayCompatibleScale(DXGI_MULTIPLANE_OVERLAY_ATTRIBUTES *,OverlaySize,bool)
0x180129676  test    al, al
0x180129678  jz      loc_180129719
0x18012967e  cmp     [rsp+48h+arg_40], bpl
0x180129686  jz      short loc_180129704
0x180129688  cmp     [rsi+4C14h], bpl
0x18012968f  jz      short loc_180129704
0x180129691  mov     bpl, 1
0x180129694  mov     al, bpl
0x180129697  add     rsp, 28h
0x18012969b  pop     rdi
0x18012969c  pop     rsi
0x18012969d  pop     rbp
0x18012969e  pop     rbx
0x18012969f  retn
0x1801296a0  test    rbx, rbx
0x1801296a3  jz      short loc_1801296F0
0x1801296a5  mov     eax, r8d
0x1801296a8  imul    rcx, rax, 188h
0x1801296af  cmp     [rcx+r10+8], rbx
0x1801296b4  jz      short loc_1801296F0
0x1801296b6  inc     r8d
0x1801296b9  jmp     loc_1801295EF
0x1801296be  test    rdi, rdi
0x1801296c1  jz      short loc_1801296E4
0x1801296c3  mov     ecx, r8d
0x1801296c6  imul    rdx, rcx, 188h
0x1801296cd  mov     rcx, [rdx+r10+10h]
0x1801296d2  mov     rcx, [rcx+28h]
0x1801296d6  cmp     ecx, eax
0x1801296d8  jnz     short loc_1801296FC
0x1801296da  shr     rcx, 20h
0x1801296de  cmp     ecx, dword ptr [rsp+48h+arg_18+4]
0x1801296e2  jnz     short loc_1801296FC
0x1801296e4  cmp     r8d, 0FFFFFFFFh
0x1801296e8  jz      loc_180129619
0x1801296ee  jmp     short loc_180129694
0x1801296f0  cmp     r8d, 0FFFFFFFFh
0x1801296f4  jz      loc_1801295F8
0x1801296fa  jmp     short loc_180129694
0x1801296fc  inc     r8d
0x1801296ff  jmp     loc_180129610
0x180129704  cmp     [rsi+2Ch], bpl
0x180129708  jnz     short loc_180129691
0x18012970a  cmp     [rsp+48h+arg_38], 2
0x180129712  jbe     short loc_180129694
0x180129714  jmp     loc_180129691
0x180129719  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+1, 2
0x180129720  jz      loc_180129694
0x180129726  mov     r8, [rdi+28h]
0x18012972a  lea     rdx, EVTDESC_DISPLAYSURFACE_REJECTCANDIDATE
0x180129731  mov     r9d, 4
0x180129737  call    McTemplateU0xq_EventWriteTransfer
0x18012973c  jmp     loc_180129694
```
