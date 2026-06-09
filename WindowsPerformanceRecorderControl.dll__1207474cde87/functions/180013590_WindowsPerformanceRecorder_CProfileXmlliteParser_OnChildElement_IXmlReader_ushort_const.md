# WindowsPerformanceRecorder::CProfileXmlliteParser::OnChildElement(IXmlReader *,ushort const *)

- ea: `0x180013590`
- end: `0x1800138b0`
- name: `?OnChildElement@CProfileXmlliteParser@WindowsPerformanceRecorder@@MEAAJPEAUIXmlReader@@PEBG@Z`
- size: `800`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CProfileXmlliteParser *this, struct IXmlReader *, char *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x18000c514`
- `0x180011280`
- `0x180013590`
- `0x1800138c0`
- `0x180013940`
- `0x18002f0e4`
- `0x180041ca4`
- `0x180044210`
- `0x18004f2b0`
- `0x18004f8ce`
- `0x1800519b4`
- `0x180056898`
- `0x180082d3c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800136d8`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180013740`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800136d8`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180013740`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013725`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013725`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013704`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800137e6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013704`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800137e6`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CProfileXmlliteParser::OnChildElement(
        WindowsPerformanceRecorder::CProfileXmlliteParser *this,
        struct IXmlReader *a2,
        char *a3)
{
  struct IXmlReader *v4; // r15
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  char **v8; // r15
  _DWORD *v9; // rax
  char *v10; // rdx
  int v11; // ebx
  __int64 result; // rax
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // rcx
  size_t v15; // rdx
  size_t v16; // r15
  void *v17; // rax
  __int64 v18; // rcx
  void *v19; // r12
  size_t v20; // r8
  const void *v21; // rdx
  void *v22; // rax
  __int64 v23; // rbx
  unsigned __int64 v24; // r13
  char *v25; // rcx
  __int64 v26; // r12
  HINSTANCE StringResourceInstance; // rax
  ATL::CAtlException *v28; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v30; // [rsp+88h] [rbp+20h]

  v4 = a2;
  v6 = operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    *v6 = &XmlObjBase::`vftable';
    v8 = (char **)(v6 + 1);
    v9 = (_DWORD *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
    v10 = (char *)(v9 + 6);
    *v8 = (char *)(v9 + 6);
    if ( a3 )
    {
      if ( (unsigned __int64)a3 < 0x10000 )
      {
        StringResourceInstance = ATL::AtlFindStringResourceInstance((unsigned __int16)a3, (unsigned __int16)v10);
        if ( StringResourceInstance )
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
            v7 + 1,
            StringResourceInstance,
            (unsigned __int16)a3);
        goto LABEL_4;
      }
      v23 = -1;
      do
        ++v23;
      while ( *(_WORD *)&a3[2 * v23] );
      if ( (_DWORD)v23 )
      {
        v30 = v9[2];
        v24 = (a3 - v10) >> 1;
        if ( (int)((v9[3] - v23) | (1 - v9[4])) < 0 )
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v7 + 1, (unsigned int)v23);
        v25 = *v8;
        v26 = 2LL * (int)v23;
        if ( v24 <= v30 )
        {
          memmove_s(v25, 2LL * (int)v23, &v25[2 * v24], 2LL * (int)v23);
        }
        else if ( v26 )
        {
          if ( v25 )
          {
            memcpy_0(v25, a3, 2LL * (int)v23);
          }
          else
          {
            *(_DWORD *)_o__errno(0, v10) = 22;
            invalid_parameter_noinfo();
          }
        }
        if ( (int)v23 < 0 || (int)v23 > *((_DWORD *)*v8 - 3) )
          ATL::AtlThrowImpl(-2147024809);
        *((_DWORD *)*v8 - 4) = v23;
        v11 = 0;
        *(_WORD *)&(*v8)[v26] = 0;
        goto LABEL_5;
      }
    }
    ATL::CSimpleStringT<unsigned short,0>::Empty(v7 + 1);
LABEL_4:
    v11 = 0;
LABEL_5:
    v7[2] = &Attributes::`vftable';
    std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(v7 + 3);
    *v7 = &WindowsPerformanceRecorder::CProfileXmlliteParser::`vftable';
    v7[6] = 0;
    v7[7] = 0;
    v7[8] = 0;
    *((_DWORD *)v7 + 18) = 0;
    v4 = a2;
    goto LABEL_6;
  }
  v11 = 0;
  v7 = 0;
LABEL_6:
  if ( !v7 )
    return 2147942414LL;
  try
  {
    v7[10] = *((_QWORD *)this + 10);
    result = XmlObjBase::Read((XmlObjBase *)v7, v4);
    if ( (int)result >= 0 )
    {
      v13 = *((_QWORD *)this + 7);
      v14 = *((_QWORD *)this + 8);
      if ( v13 < v14 )
        goto LABEL_26;
      v15 = v13 + 1;
      if ( v13 + 1 <= v14 )
        goto LABEL_26;
      v16 = *((int *)this + 18);
      if ( *((_QWORD *)this + 6) )
      {
        if ( !*((_DWORD *)this + 18) )
        {
          v16 = v14 >> 1;
          if ( v15 - v14 > v14 >> 1 )
            v16 = v15 - v14;
        }
        v16 += v14;
        if ( v15 >= v16 )
          v16 = v13 + 1;
        v17 = calloc(v16, 8u);
        v19 = v17;
        if ( v17 )
        {
          v20 = 8LL * *((_QWORD *)this + 7);
          if ( v20 )
          {
            v21 = (const void *)*((_QWORD *)this + 6);
            if ( v21 )
            {
              memcpy_0(v17, v21, v20);
            }
            else
            {
              *(_DWORD *)_o__errno(v18, 0) = 22;
              invalid_parameter_noinfo();
              v11 = 22;
            }
          }
          ATL::AtlCrtErrorCheck(v11);
          free(*((void **)this + 6));
          *((_QWORD *)this + 6) = v19;
LABEL_25:
          *((_QWORD *)this + 8) = v16;
LABEL_26:
          *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v13) = v7;
          ++*((_QWORD *)this + 7);
          return 0;
        }
      }
      else
      {
        if ( v16 <= v15 )
          v16 = v13 + 1;
        v22 = calloc(v16, 8u);
        *((_QWORD *)this + 6) = v22;
        if ( v22 )
          goto LABEL_25;
      }
      ATL::AtlThrowImpl(-2147024882);
    }
  }
  catch ( ATL::CAtlException *v28 )
  {
    return *(unsigned int *)v28;
  }
  v7[10] = *((_QWORD *)this + 10);
}

```

## disassembly

```asm
0x180013590  mov     rax, rsp
0x180013593  mov     [rax+10h], rdx
0x180013597  push    rdi
0x180013598  push    r12
0x18001359a  push    r13
0x18001359c  push    r14
0x18001359e  push    r15
0x1800135a0  sub     rsp, 40h
0x1800135a4  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800135ac  mov     [rax+8], rbx
0x1800135b0  mov     [rax+18h], rsi
0x1800135b4  mov     rsi, r8
0x1800135b7  mov     r15, rdx
0x1800135ba  mov     r14, rcx
0x1800135bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800135c4  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800135c9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800135ce  mov     rdi, rax
0x1800135d1  mov     [rsp+68h+var_40], rax
0x1800135d6  test    rax, rax
0x1800135d9  jz      loc_180013879
0x1800135df  lea     rax, ??_7XmlObjBase@@6B@; const XmlObjBase::`vftable'
0x1800135e6  mov     [rdi], rax
0x1800135e9  lea     r15, [rdi+8]
0x1800135ed  mov     [rsp+68h+var_38], r15
0x1800135f2  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800135f9  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180013600  mov     rax, [rax+18h]
0x180013604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013609  lea     rdx, [rax+18h]; unsigned __int16
0x18001360d  mov     [r15], rdx
0x180013610  test    rsi, rsi
0x180013613  jnz     loc_180013822
0x180013619  mov     rcx, r15
0x18001361c  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180013621  xor     ebx, ebx
0x180013623  lea     rax, ??_7Attributes@@6B@; const Attributes::`vftable'
0x18001362a  mov     [rdi+10h], rax
0x18001362e  lea     rcx, [rdi+18h]
0x180013632  call    ??0?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(void)
0x180013637  lea     rcx, ??_7CProfileXmlliteParser@WindowsPerformanceRecorder@@6B@; const WindowsPerformanceRecorder::CProfileXmlliteParser::`vftable'
0x18001363e  mov     [rdi], rcx
0x180013641  mov     [rdi+30h], rbx
0x180013645  mov     [rdi+38h], rbx
0x180013649  mov     [rdi+40h], rbx
0x18001364d  mov     [rdi+48h], ebx
0x180013650  mov     r15, [rsp+68h+arg_8]
0x180013655  test    rdi, rdi
0x180013658  jz      loc_180013882
0x18001365e  mov     rax, [r14+50h]
0x180013662  mov     [rdi+50h], rax
0x180013666  mov     rdx, r15; struct IXmlReader *
0x180013669  mov     rcx, rdi; this
0x18001366c  call    ?Read@XmlObjBase@@QEAAJPEAUIXmlReader@@@Z; XmlObjBase::Read(IXmlReader *)
0x180013671  test    eax, eax
0x180013673  js      loc_180013780
0x180013679  mov     [rsp+68h+arg_18], rdi
0x180013681  mov     rsi, [r14+38h]
0x180013685  mov     rcx, [r14+40h]
0x180013689  cmp     rsi, rcx
0x18001368c  jb      loc_180013757
0x180013692  lea     rdx, [rsi+1]
0x180013696  cmp     rdx, rcx
0x180013699  jbe     loc_180013757
0x18001369f  movsxd  r15, dword ptr [r14+48h]
0x1800136a3  cmp     qword ptr [r14+30h], 0
0x1800136a8  jz      loc_180013731
0x1800136ae  test    r15, r15
0x1800136b1  jnz     short loc_1800136C6
0x1800136b3  mov     r15, rcx
0x1800136b6  shr     r15, 1
0x1800136b9  mov     rax, rdx
0x1800136bc  sub     rax, rcx
0x1800136bf  cmp     rax, r15
0x1800136c2  cmova   r15, rax
0x1800136c6  add     r15, rcx
0x1800136c9  cmp     rdx, r15
0x1800136cc  cmovnb  r15, rdx
0x1800136d0  mov     edx, 8; Size
0x1800136d5  mov     rcx, r15; Count
0x1800136d8  call    cs:__imp_calloc
0x1800136de  mov     r12, rax
0x1800136e1  test    rax, rax
0x1800136e4  jz      loc_180013899
0x1800136ea  mov     r8, [r14+38h]
0x1800136ee  shl     r8, 3; Size
0x1800136f2  test    r8, r8
0x1800136f5  jz      short loc_18001371A
0x1800136f7  mov     rdx, [r14+30h]; Src
0x1800136fb  test    rdx, rdx
0x1800136fe  jnz     loc_18001388C
0x180013704  call    cs:__imp__o__errno
0x18001370a  mov     dword ptr [rax], 16h
0x180013710  call    _invalid_parameter_noinfo
0x180013715  mov     ebx, 16h
0x18001371a  mov     ecx, ebx; int
0x18001371c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180013721  mov     rcx, [r14+30h]; Block
0x180013725  call    cs:__imp_free
0x18001372b  mov     [r14+30h], r12
0x18001372f  jmp     short loc_180013753
0x180013731  cmp     r15, rdx
0x180013734  cmovbe  r15, rdx
0x180013738  mov     edx, 8; Size
0x18001373d  mov     rcx, r15; Count
0x180013740  call    cs:__imp_calloc
0x180013746  mov     [r14+30h], rax
0x18001374a  test    rax, rax
0x18001374d  jz      loc_180013899
0x180013753  mov     [r14+40h], r15
0x180013757  mov     rax, [r14+30h]
0x18001375b  mov     [rax+rsi*8], rdi
0x18001375f  inc     qword ptr [r14+38h]
0x180013763  xor     eax, eax
0x180013765  mov     rbx, [rsp+68h+arg_0]
0x18001376a  mov     rsi, [rsp+68h+arg_10]
0x180013772  add     rsp, 40h
0x180013776  pop     r15
0x180013778  pop     r14
0x18001377a  pop     r13
0x18001377c  pop     r12
0x18001377e  pop     rdi
0x18001377f  retn
0x180013780  jmp     short loc_180013765
0x180013782  inc     rbx
0x180013785  cmp     word ptr [rsi+rbx*2], 0
0x18001378a  jnz     short loc_180013782
0x18001378c  test    ebx, ebx
0x18001378e  jz      loc_180013619
0x180013794  mov     eax, [rdx-10h]
0x180013797  mov     dword ptr [rsp+68h+arg_18], eax
0x18001379e  mov     r13, rsi
0x1800137a1  sub     r13, rdx
0x1800137a4  sar     r13, 1
0x1800137a7  mov     ecx, 1
0x1800137ac  sub     ecx, [rdx-8]
0x1800137af  mov     eax, [rdx-0Ch]
0x1800137b2  sub     eax, ebx
0x1800137b4  or      ecx, eax
0x1800137b6  jge     short loc_1800137C2
0x1800137b8  mov     edx, ebx
0x1800137ba  mov     rcx, r15
0x1800137bd  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800137c2  mov     rcx, [r15]; void *
0x1800137c5  movsxd  rax, ebx
0x1800137c8  lea     r12, [rax+rax]
0x1800137cc  mov     eax, dword ptr [rsp+68h+arg_18]
0x1800137d3  cmp     r13, rax
0x1800137d6  jbe     loc_18001385D
0x1800137dc  test    r12, r12
0x1800137df  jz      short loc_1800137F7
0x1800137e1  test    rcx, rcx
0x1800137e4  jnz     short loc_180013815
0x1800137e6  call    cs:__imp__o__errno
0x1800137ec  mov     dword ptr [rax], 16h
0x1800137f2  call    _invalid_parameter_noinfo
0x1800137f7  test    ebx, ebx
0x1800137f9  js      short loc_18001386E
0x1800137fb  mov     rax, [r15]
0x1800137fe  cmp     ebx, [rax-0Ch]
0x180013801  jg      short loc_18001386E
0x180013803  mov     [rax-10h], ebx
0x180013806  mov     rax, [r15]
0x180013809  xor     ebx, ebx
0x18001380b  mov     [r12+rax], bx
0x180013810  jmp     loc_180013623
0x180013815  mov     r8, r12; Size
0x180013818  mov     rdx, rsi; Src
0x18001381b  call    memcpy_0
0x180013820  jmp     short loc_1800137F7
0x180013822  cmp     rsi, 10000h
0x180013829  jnb     short loc_180013851
0x18001382b  movzx   ebx, si
0x18001382e  mov     ecx, ebx; unsigned int
0x180013830  call    ?AtlFindStringResourceInstance@ATL@@YAPEAUHINSTANCE__@@IG@Z; ATL::AtlFindStringResourceInstance(uint,ushort)
0x180013835  test    rax, rax
0x180013838  jz      loc_180013621
0x18001383e  mov     r8d, ebx
0x180013841  mov     rdx, rax
0x180013844  mov     rcx, r15
0x180013847  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)
0x18001384c  jmp     loc_180013621
0x180013851  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180013858  jmp     loc_180013782
0x18001385d  lea     r8, [rcx+r13*2]; Source
0x180013861  mov     r9, r12; SourceSize
0x180013864  mov     rdx, r12; DestinationSize
0x180013867  call    memmove_s
0x18001386c  jmp     short loc_1800137F7
0x18001386e  mov     ecx, 80070057h; int
0x180013873  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180013879  xor     ebx, ebx
0x18001387b  mov     edi, ebx
0x18001387d  jmp     loc_180013655
0x180013882  mov     eax, 8007000Eh
0x180013887  jmp     loc_180013765
0x18001388c  mov     rcx, r12; void *
0x18001388f  call    memcpy_0
0x180013894  jmp     loc_18001371A
0x180013899  mov     ecx, 8007000Eh; int
0x18001389e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800138a4  mov     eax, dword ptr [rsp+68h+arg_18]
0x1800138ab  jmp     loc_180013765
```
