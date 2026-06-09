# CServiceModule::StartPenProcessCore(CPenProcessInfo const *,CPenSession *,void *,CPenProcessStartInfo const *)

- ea: `0x180014d40`
- end: `0x180014fe6`
- name: `?StartPenProcessCore@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEAXPEBUCPenProcessStartInfo@@@Z`
- size: `678`
- prototype: `void __fastcall(CServiceModule *this, const struct CPenProcessInfo *, struct CPenSession *, void *, const struct CPenProcessStartInfo *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, service_task`

## callers

- `0x180014a80`
- `0x18002718c`

## callees

- `0x180001008`
- `0x180001dcc`
- `0x18000ea30`
- `0x180012dc0`
- `0x180013da0`
- `0x180014124`
- `0x180014d40`
- `0x180015630`
- `0x180015660`
- `0x1800163c0`
- `0x180016620`
- `0x18001a7ac`
- `0x18001bc20`
- `0x18001fd50`
- `0x18002b3a8`
- `0x180031010`

## string_xrefs

- `0x180014da5`: `PENSERVICE_CServiceModule::StartPenProcessCore`
- `0x180014e46`: `PENSERVICE_CServiceModule::StartPenProcessCore`
- `0x180014e85`: `Process already exists`

## pseudocode

```c
void __fastcall CServiceModule::StartPenProcessCore(
        CServiceModule *this,
        const struct CPenProcessInfo *a2,
        struct CPenSession *a3,
        void *a4,
        const struct CPenProcessStartInfo *a5)
{
  const struct CPenProcessStartInfo *v6; // rdi
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  CPenProcess *PenProcess; // rbx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rax
  CPenProcess *v18; // rax
  CPenProcess *v19; // rax
  CPenProcess *v20; // rbx
  unsigned int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // rax
  void *v24; // [rsp+40h] [rbp-20h] BYREF
  const char *v25; // [rsp+48h] [rbp-18h] BYREF
  __int64 v26; // [rsp+50h] [rbp-10h] BYREF
  const char *v27; // [rsp+98h] [rbp+38h] BYREF

  v6 = a5;
  if ( *((_DWORD *)a2 + 3) || *((_DWORD *)a5 + 2) || *((_BYTE *)a3 + 8) )
  {
    if ( *((_DWORD *)a5 + 4) && (PenProcess = CServiceModule::FindPenProcess(this, a2, *((_DWORD *)a3 + 1))) != 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          31,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::StartPenProcessCore");
      if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
      {
        LODWORD(v27) = v15;
        v25 = "Process already exists";
        v26 = *((_QWORD *)a2 + 68);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v14,
          (unsigned int)&word_18003A466,
          v15,
          v16,
          (__int64)&v26,
          (__int64)&v27,
          (__int64)&v25);
      }
      CPenProcess::EnsureRunning(PenProcess, v6, 1, *((_DWORD *)v6 + 5));
    }
    else
    {
      v17 = *(_QWORD *)a2;
      v24 = 0;
      if ( (*(unsigned int (__fastcall **)(const struct CPenProcessInfo *, void *, void **))(v17 + 72))(a2, a4, &v24) )
      {
        v18 = (CPenProcess *)operator new(0x480u, (const struct std::nothrow_t *)&std::nothrow);
        v27 = (const char *)v18;
        if ( v18 )
        {
          v19 = CPenProcess::CPenProcess(v18);
          v20 = v19;
          if ( v19 )
          {
            if ( CPenProcess::Init(v19, a2, a3)
              && CPenProcess::GetDuplicateToken(v20, v24, (void **)v20 + 138, *(_DWORD *)v6)
              && (*(_OWORD *)((char *)v20 + 8) = *(_OWORD *)v6,
                  *((_QWORD *)v20 + 3) = *((_QWORD *)v6 + 2),
                  (unsigned int)CPenProcess::Start(v20))
              && *((_DWORD *)v6 + 4)
              && (v21 = *((_DWORD *)this + 95), v22 = v21 + 1, v21 + 1 >= v21)
              && (int)CPbPreallocArray<CPenProcess *,10>::EnsureSize((char *)this + 288) >= 0 )
            {
              v23 = *((_QWORD *)this + 46);
              *((_DWORD *)this + 95) = v22;
              *(_QWORD *)(v23 + 8LL * (v22 - 1)) = v20;
            }
            else
            {
              CPenProcess::Release(v20);
            }
          }
        }
      }
      if ( v24 != a4 )
        SH<void *,SH_HANDLE>::Reset(&v24);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
      WPP_SF_s(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        30,
        WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
        "PENSERVICE_CServiceModule::StartPenProcessCore");
    if ( (unsigned int)dword_1800411A8 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
      {
        v27 = "Pen process has been disabled.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v10,
          (unsigned int)&byte_18003A0A7,
          v11,
          v12,
          (__int64)&v27);
      }
    }
  }
}

```

## disassembly

```asm
0x180014d40  mov     [rsp-28h+arg_0], rbx
0x180014d45  mov     [rsp-28h+arg_10], rsi
0x180014d4a  push    rbp
0x180014d4b  push    rdi
0x180014d4c  push    r12
0x180014d4e  push    r14
0x180014d50  push    r15
0x180014d52  mov     rbp, rsp
0x180014d55  sub     rsp, 60h
0x180014d59  cmp     dword ptr [rdx+0Ch], 0
0x180014d5d  mov     r12, r9
0x180014d60  mov     rdi, [rbp+arg_20]
0x180014d64  mov     r14, r8
0x180014d67  mov     rsi, rdx
0x180014d6a  mov     r15, rcx
0x180014d6d  jnz     loc_180014E0A
0x180014d73  cmp     dword ptr [rdi+8], 0
0x180014d77  jnz     loc_180014E0A
0x180014d7d  cmp     byte ptr [r8+8], 0
0x180014d82  jnz     loc_180014E0A
0x180014d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d8f  lea     rax, WPP_GLOBAL_Control
0x180014d96  cmp     rcx, rax
0x180014d99  jz      short loc_180014DBD
0x180014d9b  test    byte ptr [rcx+1Ch], 10h
0x180014d9f  jz      short loc_180014DBD
0x180014da1  mov     rcx, [rcx+10h]
0x180014da5  lea     r9, aPenserviceCser_16; "PENSERVICE_CServiceModule::StartPenProc"...
0x180014dac  mov     edx, 1Eh
0x180014db1  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180014db8  call    WPP_SF_s
0x180014dbd  mov     eax, cs:dword_1800411A8
0x180014dc3  cmp     eax, 5
0x180014dc6  jbe     loc_180014FCD
0x180014dcc  mov     edx, 4000000h
0x180014dd1  lea     rcx, dword_1800411A8
0x180014dd8  call    _tlgKeywordOn
0x180014ddd  test    al, al
0x180014ddf  jz      loc_180014FCD
0x180014de5  lea     rax, aPenProcessHasB; "Pen process has been disabled."
0x180014dec  mov     [rbp+arg_8], rax
0x180014df0  lea     rdx, byte_18003A0A7
0x180014df7  lea     rax, [rbp+arg_8]
0x180014dfb  mov     [rsp+60h+var_40], rax
0x180014e00  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180014e05  jmp     loc_180014FCD
0x180014e0a  cmp     dword ptr [rdi+10h], 0
0x180014e0e  jz      loc_180014EE0
0x180014e14  mov     r8d, [r8+4]; unsigned int
0x180014e18  call    ?FindPenProcess@CServiceModule@@QEAAPEAVCPenProcess@@PEBVCPenProcessInfo@@K@Z; CServiceModule::FindPenProcess(CPenProcessInfo const *,ulong)
0x180014e1d  mov     rbx, rax
0x180014e20  test    rax, rax
0x180014e23  jz      loc_180014EE0
0x180014e29  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e30  lea     rax, WPP_GLOBAL_Control
0x180014e37  cmp     rcx, rax
0x180014e3a  jz      short loc_180014E5E
0x180014e3c  test    byte ptr [rcx+1Ch], 10h
0x180014e40  jz      short loc_180014E5E
0x180014e42  mov     rcx, [rcx+10h]
0x180014e46  lea     r9, aPenserviceCser_16; "PENSERVICE_CServiceModule::StartPenProc"...
0x180014e4d  mov     edx, 1Fh
0x180014e52  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180014e59  call    WPP_SF_s
0x180014e5e  mov     eax, cs:dword_1800411A8
0x180014e64  mov     r8d, [rbx+43Ch]
0x180014e6b  cmp     eax, 5
0x180014e6e  jbe     short loc_180014EC6
0x180014e70  mov     edx, 4000000h
0x180014e75  lea     rcx, dword_1800411A8
0x180014e7c  call    _tlgKeywordOn
0x180014e81  test    al, al
0x180014e83  jz      short loc_180014EC6
0x180014e85  lea     rax, aProcessAlready; "Process already exists"
0x180014e8c  mov     dword ptr [rbp+arg_8], r8d
0x180014e90  mov     [rbp+var_18], rax
0x180014e94  lea     rdx, word_18003A466
0x180014e9b  mov     rax, [rsi+220h]
0x180014ea2  mov     [rbp+var_10], rax
0x180014ea6  lea     rax, [rbp+var_18]
0x180014eaa  mov     [rsp+60h+var_30], rax
0x180014eaf  lea     rax, [rbp+arg_8]
0x180014eb3  mov     [rsp+60h+var_38], rax
0x180014eb8  lea     rax, [rbp+var_10]
0x180014ebc  mov     [rsp+60h+var_40], rax
0x180014ec1  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180014ec6  mov     r9d, [rdi+14h]; int
0x180014eca  mov     r8d, 1; int
0x180014ed0  mov     rdx, rdi; struct CPenProcessStartInfo *
0x180014ed3  mov     rcx, rbx; this
0x180014ed6  call    ?EnsureRunning@CPenProcess@@QEAAHPEBUCPenProcessStartInfo@@HH@Z; CPenProcess::EnsureRunning(CPenProcessStartInfo const *,int,int)
0x180014edb  jmp     loc_180014FCD
0x180014ee0  mov     rax, [rdx]
0x180014ee3  lea     r8, [rbp+var_20]
0x180014ee7  mov     rdx, r12
0x180014eea  mov     [rbp+var_20], 0
0x180014ef2  mov     rcx, rsi
0x180014ef5  mov     rax, [rax+48h]
0x180014ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014efe  test    eax, eax
0x180014f00  jz      loc_180014FBE
0x180014f06  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014f0d  mov     ecx, 480h; unsigned __int64
0x180014f12  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014f17  mov     [rbp+arg_8], rax
0x180014f1b  test    rax, rax
0x180014f1e  jz      loc_180014FBE
0x180014f24  mov     rcx, rax; this
0x180014f27  call    ??0CPenProcess@@QEAA@XZ; CPenProcess::CPenProcess(void)
0x180014f2c  mov     rbx, rax
0x180014f2f  test    rax, rax
0x180014f32  jz      loc_180014FBE
0x180014f38  mov     r8, r14; struct CPenSession *
0x180014f3b  mov     rdx, rsi; struct CPenProcessInfo *
0x180014f3e  mov     rcx, rax; this
0x180014f41  call    ?Init@CPenProcess@@QEAAHPEBVCPenProcessInfo@@PEAVCPenSession@@@Z; CPenProcess::Init(CPenProcessInfo const *,CPenSession *)
0x180014f46  test    eax, eax
0x180014f48  jz      short loc_180014FB6
0x180014f4a  mov     r9d, [rdi]; int
0x180014f4d  lea     r8, [rbx+450h]; void **
0x180014f54  mov     rdx, [rbp+var_20]; void *
0x180014f58  mov     rcx, rbx; this
0x180014f5b  call    ?GetDuplicateToken@CPenProcess@@AEAAHPEAXPEAPEAXH@Z; CPenProcess::GetDuplicateToken(void *,void * *,int)
0x180014f60  test    eax, eax
0x180014f62  jz      short loc_180014FB6
0x180014f64  movups  xmm0, xmmword ptr [rdi]
0x180014f67  mov     rcx, rbx; this
0x180014f6a  movups  xmmword ptr [rbx+8], xmm0
0x180014f6e  movsd   xmm1, qword ptr [rdi+10h]
0x180014f73  movsd   qword ptr [rbx+18h], xmm1
0x180014f78  call    ?Start@CPenProcess@@QEAAHXZ; CPenProcess::Start(void)
0x180014f7d  test    eax, eax
0x180014f7f  jz      short loc_180014FB6
0x180014f81  cmp     dword ptr [rdi+10h], 0
0x180014f85  jz      short loc_180014FB6
0x180014f87  lea     rdi, [r15+120h]
0x180014f8e  mov     eax, [rdi+5Ch]
0x180014f91  lea     esi, [rax+1]
0x180014f94  cmp     esi, eax
0x180014f96  jb      short loc_180014FB6
0x180014f98  mov     edx, esi
0x180014f9a  mov     rcx, rdi; Src
0x180014f9d  call    ?EnsureSize@?$CPbPreallocArray@PEAVCPenProcess@@$09@@IEAAJIH@Z; CPbPreallocArray<CPenProcess *,10>::EnsureSize(uint,int)
0x180014fa2  test    eax, eax
0x180014fa4  js      short loc_180014FB6
0x180014fa6  mov     rax, [rdi+50h]
0x180014faa  lea     ecx, [rsi-1]
0x180014fad  mov     [rdi+5Ch], esi
0x180014fb0  mov     [rax+rcx*8], rbx
0x180014fb4  jmp     short loc_180014FBE
0x180014fb6  mov     rcx, rbx; this
0x180014fb9  call    ?Release@CPenProcess@@QEAAKXZ; CPenProcess::Release(void)
0x180014fbe  cmp     [rbp+var_20], r12
0x180014fc2  jz      short loc_180014FCD
0x180014fc4  lea     rcx, [rbp+var_20]
0x180014fc8  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180014fcd  lea     r11, [rsp+60h+var_s0]
0x180014fd2  mov     rbx, [r11+30h]
0x180014fd6  mov     rsi, [r11+40h]
0x180014fda  mov     rsp, r11
0x180014fdd  pop     r15
0x180014fdf  pop     r14
0x180014fe1  pop     r12
0x180014fe3  pop     rdi
0x180014fe4  pop     rbp
0x180014fe5  retn
```
