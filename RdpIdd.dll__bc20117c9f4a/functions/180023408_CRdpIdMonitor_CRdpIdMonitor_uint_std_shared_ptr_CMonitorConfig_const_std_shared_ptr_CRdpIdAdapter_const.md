# CRdpIdMonitor::CRdpIdMonitor(uint,std::shared_ptr<CMonitorConfig> const &,std::shared_ptr<CRdpIdAdapter> const &)

- ea: `0x180023408`
- end: `0x180023571`
- name: `??0CRdpIdMonitor@@QEAA@IAEBV?$shared_ptr@VCMonitorConfig@@@std@@AEBV?$shared_ptr@VCRdpIdAdapter@@@2@@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180012c7c`

## callees

- `0x180013bb0`
- `0x18001dd70`
- `0x180023408`
- `0x1800257d8`
- `0x180025a34`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
CRdpIdMonitor *__fastcall CRdpIdMonitor::CRdpIdMonitor(CRdpIdMonitor *this, __int64 a2, __int64 a3)
{
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // r10d
  __int64 v8; // r8
  const char *v10; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_BYTE *)this + 16) = 0;
  *((_DWORD *)this + 5) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 2;
  *(_OWORD *)((char *)this + 56) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  *(_OWORD *)((char *)this + 88) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 26) = -1;
  *((_DWORD *)this + 27) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *(_OWORD *)((char *)this + 136) = 0;
  *(_OWORD *)((char *)this + 152) = 0;
  *(_OWORD *)((char *)this + 168) = 0;
  *(_OWORD *)((char *)this + 184) = 0;
  *((_DWORD *)this + 50) = 0;
  std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>((char *)this + 208, a3);
  *((_QWORD *)this + 28) = v5;
  std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>((char *)this + 232, v6);
  *((_QWORD *)this + 31) = v8;
  *((_QWORD *)this + 32) = v8;
  *((_QWORD *)this + 33) = v8;
  *((_QWORD *)this + 34) = v8;
  *((_DWORD *)this + 71) = v7;
  *((_DWORD *)this + 72) = v8;
  *(_QWORD *)((char *)this + 292) = 0;
  *((_QWORD *)this + 38) = v8;
  *((_QWORD *)this + 39) = v8;
  if ( *(_DWORD *)(*(_QWORD *)a3 + 32LL) < 0x10u )
    v7 = *(_DWORD *)(*(_QWORD *)a3 + 32LL);
  *((_DWORD *)this + 70) = v7;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x43,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
    (const char *)0x80070057LL,
    (*(_DWORD *)(*(_QWORD *)a3 + 28LL) & 0xE) != 14,
    (bool)"At least valid display mode, scale factor and physical size structures should be present",
    v10);
  if ( (*(_BYTE *)(*(_QWORD *)a3 + 28LL) & 1) != 0 )
    CRdpIdMonitor::PrepareTargetModeList(this);
  else
    CRdpIdMonitor::PrepareTargetModeListFromDisplayMode(this);
  return this;
}

```

## disassembly

```asm
0x180023408  mov     [rsp+arg_8], rbx
0x18002340d  mov     [rsp+arg_0], rcx
0x180023412  push    rdi; char *
0x180023413  sub     rsp, 30h
0x180023417  mov     rbx, r8
0x18002341a  mov     r10d, edx
0x18002341d  mov     rdi, rcx
0x180023420  xor     r8d, r8d
0x180023423  mov     [rcx], r8
0x180023426  mov     [rcx+8], r8
0x18002342a  mov     [rcx+10h], r8b
0x18002342e  mov     [rcx+14h], r8d
0x180023432  mov     [rcx+18h], r8
0x180023436  mov     qword ptr [rcx+20h], 2
0x18002343e  xorps   xmm0, xmm0
0x180023441  movups  xmmword ptr [rcx+38h], xmm0
0x180023445  movups  xmmword ptr [rcx+48h], xmm0
0x180023449  movups  xmmword ptr [rcx+58h], xmm0
0x18002344d  mov     [rcx+28h], r8
0x180023451  mov     [rcx+30h], r8
0x180023455  mov     dword ptr [rcx+68h], 0FFFFFFFFh
0x18002345c  mov     [rcx+6Ch], r8d
0x180023460  mov     [rcx+70h], r8
0x180023464  mov     [rcx+78h], r8
0x180023468  mov     [rcx+80h], r8
0x18002346f  movups  xmmword ptr [rcx+88h], xmm0
0x180023476  movups  xmmword ptr [rcx+98h], xmm0
0x18002347d  movups  xmmword ptr [rcx+0A8h], xmm0
0x180023484  xor     eax, eax
0x180023486  movups  xmmword ptr [rcx+0B8h], xmm0
0x18002348d  mov     [rcx+0C8h], eax
0x180023493  add     rcx, 0D0h
0x18002349a  mov     rdx, rbx
0x18002349d  call    ??0?$shared_ptr@VCRdpIdAdapter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(std::shared_ptr<CRdpIdAdapter> const &)
0x1800234a2  nop
0x1800234a3  mov     [rdi+0E0h], r8
0x1800234aa  lea     rcx, [rdi+0E8h]
0x1800234b1  mov     rdx, r9
0x1800234b4  call    ??0?$shared_ptr@VCRdpIdAdapter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(std::shared_ptr<CRdpIdAdapter> const &)
0x1800234b9  nop
0x1800234ba  mov     [rdi+0F8h], r8
0x1800234c1  mov     [rdi+100h], r8
0x1800234c8  mov     [rdi+108h], r8
0x1800234cf  mov     [rdi+110h], r8
0x1800234d6  mov     [rdi+11Ch], r10d
0x1800234dd  mov     [rdi+120h], r8d
0x1800234e4  xor     eax, eax
0x1800234e6  mov     [rdi+124h], rax
0x1800234ed  mov     [rdi+130h], r8
0x1800234f4  mov     [rdi+138h], r8
0x1800234fb  mov     rax, [rbx]
0x1800234fe  cmp     dword ptr [rax+20h], 10h
0x180023502  cmovb   r10d, [rax+20h]
0x180023507  mov     [rdi+118h], r10d
0x18002350e  mov     rax, [rbx]
0x180023511  mov     ecx, [rax+1Ch]
0x180023514  and     ecx, 0Eh
0x180023517  cmp     cl, 0Eh
0x18002351a  setnz   al
0x18002351d  mov     rcx, [rsp+38h]; this
0x180023522  lea     rdx, aAtLeastValidDi; "At least valid display mode, scale fact"...
0x180023529  mov     qword ptr [rsp+38h+var_10], rdx; bool
0x18002352e  mov     [rsp+38h+var_18], al; char
0x180023532  mov     r9d, 80070057h; char *
0x180023538  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002353f  mov     edx, 43h ; 'C'; void *
0x180023544  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180023549  mov     rax, [rbx]
0x18002354c  mov     rcx, rdi; this
0x18002354f  test    byte ptr [rax+1Ch], 1
0x180023553  jz      short loc_18002355C
0x180023555  call    ?PrepareTargetModeList@CRdpIdMonitor@@AEAAXXZ; CRdpIdMonitor::PrepareTargetModeList(void)
0x18002355a  jmp     short loc_180023562
0x18002355c  call    ?PrepareTargetModeListFromDisplayMode@CRdpIdMonitor@@AEAAXXZ; CRdpIdMonitor::PrepareTargetModeListFromDisplayMode(void)
0x180023561  nop
0x180023562  mov     rax, rdi
0x180023565  mov     rbx, [rsp+38h+arg_8]
0x18002356a  add     rsp, 30h
0x18002356e  pop     rdi
0x18002356f  retn
```
