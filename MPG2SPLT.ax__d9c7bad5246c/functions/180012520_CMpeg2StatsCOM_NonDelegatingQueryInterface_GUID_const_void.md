# CMpeg2StatsCOM::NonDelegatingQueryInterface(_GUID const &,void * *)

- ea: `0x180012520`
- end: `0x180012738`
- name: `?NonDelegatingQueryInterface@CMpeg2StatsCOM@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `536`
- prototype: `__int64 __fastcall(CMpeg2StatsCOM *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001008`
- `0x180002bb8`
- `0x180010280`
- `0x180012520`
- `0x1800184fc`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMpeg2StatsCOM::NonDelegatingQueryInterface(CMpeg2StatsCOM *this, const struct _GUID *a2, void **a3)
{
  int v3; // ebx
  _QWORD *v6; // rsi
  __int64 v7; // rdi
  int v8; // edi
  __int64 v10; // rdi
  int v11; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  v11 = 0;
  if ( *(_OWORD *)a2 == *(_OWORD *)&IID_IMpeg2TransportStatsRaw )
  {
    v6 = (_QWORD *)*((_QWORD *)this + 3);
    if ( !v6 )
    {
      v6 = operator new(0x30u);
      if ( !v6 )
      {
        v8 = -2147024882;
        goto LABEL_9;
      }
      if ( !*((_QWORD *)this + 10) )
      {
        Mp2DemuxSec::CDemuxSec::CreateSids((CMpeg2StatsCOM *)((char *)this + 40));
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 5) + 32LL))((char *)this + 40);
      }
      v7 = *((_QWORD *)this + 1);
      CMpeg2SharedMem::CMpeg2SharedMem(
        (CMpeg2SharedMem *)(v6 + 1),
        L"Global\\MPEG2_DEMULTIPLEXER_STATS_TRANSPORT",
        0x60138u,
        *((LPSECURITY_ATTRIBUTES *)this + 10),
        &v11);
      v6[5] = v7;
      v8 = v11;
      *v6 = &CMpeg2TransportStatsCOM::`vftable'{for `IMpeg2TransportStatsRaw'};
      v6[1] = &CMpeg2ProgramStatsCOM::`vftable'{for `CMpeg2SharedMem'};
      *((_QWORD *)this + 3) = v6;
      if ( v8 < 0 )
      {
        (*(void (__fastcall **)(_QWORD *, __int64))v6[1])(v6 + 1, 1);
LABEL_9:
        *((_QWORD *)this + 3) = 0;
        return (unsigned int)v8;
      }
    }
    goto LABEL_10;
  }
  if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_IMpeg2ProgramStatsRaw.Data1
    || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_IMpeg2ProgramStatsRaw.Data4 )
  {
    return CUnknown::NonDelegatingQueryInterface(this, a2, a3);
  }
  v6 = (_QWORD *)*((_QWORD *)this + 4);
  if ( v6 )
    goto LABEL_10;
  v6 = operator new(0x30u);
  if ( v6 )
  {
    if ( !*((_QWORD *)this + 10) )
    {
      Mp2DemuxSec::CDemuxSec::CreateSids((CMpeg2StatsCOM *)((char *)this + 40));
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 5) + 32LL))((char *)this + 40);
    }
    v10 = *((_QWORD *)this + 1);
    CMpeg2SharedMem::CMpeg2SharedMem(
      (CMpeg2SharedMem *)(v6 + 1),
      L"Global\\MPEG2_DEMULTIPLEXER_STATS_PROGRAM",
      0x2130u,
      *((LPSECURITY_ATTRIBUTES *)this + 10),
      &v11);
    v3 = v11;
    *v6 = &CMpeg2ProgramStatsCOM::`vftable'{for `IMpeg2ProgramStatsRaw'};
    v6[1] = &CMpeg2ProgramStatsCOM::`vftable'{for `CMpeg2SharedMem'};
    v6[5] = v10;
    *((_QWORD *)this + 4) = v6;
    if ( v3 >= 0 )
    {
LABEL_10:
      if ( !a3 )
        return 2147500035LL;
      *a3 = v6;
      (*(void (__fastcall **)(_QWORD *))(*v6 + 8LL))(v6);
      return 0;
    }
  }
  else
  {
    v6 = 0;
    *((_QWORD *)this + 4) = 0;
  }
  if ( v3 >= 0 )
    v3 = -2147024882;
  if ( v6 )
    (*(void (__fastcall **)(_QWORD *, __int64))v6[1])(v6 + 1, 1);
  *((_QWORD *)this + 4) = 0;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180012520  mov     rax, rsp
0x180012523  push    rbx
0x180012524  push    rbp
0x180012525  push    rsi
0x180012526  push    rdi
0x180012527  push    r14
0x180012529  push    r15
0x18001252b  sub     rsp, 38h
0x18001252f  xor     ebx, ebx
0x180012531  mov     r14, r8
0x180012534  mov     [rax+20h], ebx
0x180012537  mov     rbp, rcx
0x18001253a  mov     rax, [rdx]
0x18001253d  cmp     rax, qword ptr cs:IID_IMpeg2TransportStatsRaw.Data1
0x180012544  jnz     loc_18001263E
0x18001254a  mov     rax, [rdx+8]
0x18001254e  cmp     rax, qword ptr cs:IID_IMpeg2TransportStatsRaw.Data4
0x180012555  jnz     loc_18001263E
0x18001255b  mov     rsi, [rcx+18h]
0x18001255f  test    rsi, rsi
0x180012562  jnz     loc_180012616
0x180012568  lea     ecx, [rbx+30h]; Size
0x18001256b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012570  mov     rsi, rax
0x180012573  test    rax, rax
0x180012576  jz      loc_180012606
0x18001257c  lea     r15, [rbp+28h]
0x180012580  cmp     [r15+28h], rbx
0x180012584  jnz     short loc_18001259D
0x180012586  mov     rcx, r15; this
0x180012589  call    ?CreateSids@CDemuxSec@Mp2DemuxSec@@AEAAJXZ; Mp2DemuxSec::CDemuxSec::CreateSids(void)
0x18001258e  mov     rax, [r15]
0x180012591  mov     rcx, r15
0x180012594  mov     rax, [rax+20h]
0x180012598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001259d  mov     r9, [r15+28h]; lpFileMappingAttributes
0x1800125a1  lea     rax, [rsp+68h+arg_18]
0x1800125a9  mov     rdi, [rbp+8]
0x1800125ad  lea     rdx, aGlobalMpeg2Dem_0; "Global\\MPEG2_DEMULTIPLEXER_STATS_TRANS"...
0x1800125b4  mov     r8d, 60138h; dwMaximumSizeLow
0x1800125ba  mov     [rsp+68h+var_48], rax; int *
0x1800125bf  lea     rcx, [rsi+8]; this
0x1800125c3  call    ??0CMpeg2SharedMem@@QEAA@PEBGKPEAU_SECURITY_ATTRIBUTES@@PEAJ@Z; CMpeg2SharedMem::CMpeg2SharedMem(ushort const *,ulong,_SECURITY_ATTRIBUTES *,long *)
0x1800125c8  lea     rax, ??_7CMpeg2TransportStatsCOM@@6BIMpeg2TransportStatsRaw@@@; const CMpeg2TransportStatsCOM::`vftable'{for `IMpeg2TransportStatsRaw'}
0x1800125cf  mov     [rsi+28h], rdi
0x1800125d3  mov     edi, [rsp+68h+arg_18]
0x1800125da  mov     [rsi], rax
0x1800125dd  lea     rax, ??_7CMpeg2ProgramStatsCOM@@6BCMpeg2SharedMem@@@; const CMpeg2ProgramStatsCOM::`vftable'{for `CMpeg2SharedMem'}
0x1800125e4  mov     [rsi+8], rax
0x1800125e8  mov     [rbp+18h], rsi
0x1800125ec  test    edi, edi
0x1800125ee  jns     short loc_180012616
0x1800125f0  lea     rcx, [rsi+8]
0x1800125f4  mov     edx, 1
0x1800125f9  mov     rax, [rcx]
0x1800125fc  mov     rax, [rax]
0x1800125ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012604  jmp     short loc_18001260B
0x180012606  mov     edi, 8007000Eh
0x18001260b  mov     [rbp+18h], rbx
0x18001260f  mov     eax, edi
0x180012611  jmp     loc_18001272B
0x180012616  test    r14, r14
0x180012619  jnz     short loc_180012625
0x18001261b  mov     eax, 80004003h
0x180012620  jmp     loc_18001272B
0x180012625  mov     [r14], rsi
0x180012628  mov     rcx, rsi
0x18001262b  mov     rax, [rsi]
0x18001262e  mov     rax, [rax+8]
0x180012632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012637  xor     eax, eax
0x180012639  jmp     loc_18001272B
0x18001263e  mov     rax, [rdx]
0x180012641  cmp     rax, qword ptr cs:IID_IMpeg2ProgramStatsRaw.Data1
0x180012648  jnz     loc_180012726
0x18001264e  mov     rax, [rdx+8]
0x180012652  cmp     rax, qword ptr cs:IID_IMpeg2ProgramStatsRaw.Data4
0x180012659  jnz     loc_180012726
0x18001265f  mov     rsi, [rcx+20h]
0x180012663  test    rsi, rsi
0x180012666  jnz     short loc_180012616
0x180012668  lea     ecx, [rsi+30h]; Size
0x18001266b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012670  mov     rsi, rax
0x180012673  test    rax, rax
0x180012676  jz      short loc_1800126F1
0x180012678  lea     r15, [rbp+28h]
0x18001267c  cmp     [r15+28h], rbx
0x180012680  jnz     short loc_180012699
0x180012682  mov     rcx, r15; this
0x180012685  call    ?CreateSids@CDemuxSec@Mp2DemuxSec@@AEAAJXZ; Mp2DemuxSec::CDemuxSec::CreateSids(void)
0x18001268a  mov     rax, [r15]
0x18001268d  mov     rcx, r15
0x180012690  mov     rax, [rax+20h]
0x180012694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012699  mov     r9, [r15+28h]; lpFileMappingAttributes
0x18001269d  lea     rax, [rsp+68h+arg_18]
0x1800126a5  mov     rdi, [rbp+8]
0x1800126a9  lea     rdx, aGlobalMpeg2Dem; "Global\\MPEG2_DEMULTIPLEXER_STATS_PROGR"...
0x1800126b0  mov     r8d, 2130h; dwMaximumSizeLow
0x1800126b6  mov     [rsp+68h+var_48], rax; int *
0x1800126bb  lea     rcx, [rsi+8]; this
0x1800126bf  call    ??0CMpeg2SharedMem@@QEAA@PEBGKPEAU_SECURITY_ATTRIBUTES@@PEAJ@Z; CMpeg2SharedMem::CMpeg2SharedMem(ushort const *,ulong,_SECURITY_ATTRIBUTES *,long *)
0x1800126c4  mov     ebx, [rsp+68h+arg_18]
0x1800126cb  lea     rax, ??_7CMpeg2ProgramStatsCOM@@6BIMpeg2ProgramStatsRaw@@@; const CMpeg2ProgramStatsCOM::`vftable'{for `IMpeg2ProgramStatsRaw'}
0x1800126d2  mov     [rsi], rax
0x1800126d5  lea     rax, ??_7CMpeg2ProgramStatsCOM@@6BCMpeg2SharedMem@@@; const CMpeg2ProgramStatsCOM::`vftable'{for `CMpeg2SharedMem'}
0x1800126dc  mov     [rsi+8], rax
0x1800126e0  mov     [rsi+28h], rdi
0x1800126e4  mov     [rbp+20h], rsi
0x1800126e8  test    ebx, ebx
0x1800126ea  js      short loc_1800126F7
0x1800126ec  jmp     loc_180012616
0x1800126f1  xor     esi, esi
0x1800126f3  mov     [rbp+20h], rbx
0x1800126f7  test    ebx, ebx
0x1800126f9  mov     edi, 8007000Eh
0x1800126fe  cmovns  ebx, edi
0x180012701  test    rsi, rsi
0x180012704  jz      short loc_18001271A
0x180012706  lea     rcx, [rsi+8]
0x18001270a  mov     rdx, [rcx]
0x18001270d  mov     rax, [rdx]
0x180012710  mov     edx, 1
0x180012715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001271a  mov     qword ptr [rbp+20h], 0
0x180012722  mov     eax, ebx
0x180012724  jmp     short loc_18001272B
0x180012726  call    ?NonDelegatingQueryInterface@CUnknown@@UEAAJAEBU_GUID@@PEAPEAX@Z; CUnknown::NonDelegatingQueryInterface(_GUID const &,void * *)
0x18001272b  add     rsp, 38h
0x18001272f  pop     r15
0x180012731  pop     r14
0x180012733  pop     rdi
0x180012734  pop     rsi
0x180012735  pop     rbp
0x180012736  pop     rbx
0x180012737  retn
```
