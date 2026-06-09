# WdcStartupMonitor::MapStartupProcesses(_STARTUP_LOCATION,_WDC_STARTUP_INFO * *)

- ea: `0x1800d5988`
- end: `0x1800d5dcb`
- name: `?MapStartupProcesses@WdcStartupMonitor@@QEAAJW4_STARTUP_LOCATION@@PEAPEAU_WDC_STARTUP_INFO@@@Z`
- size: `1091`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d4d24`
- `0x1800d5164`
- `0x1800d5540`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x180009710`
- `0x18000e6cc`
- `0x18004e674`
- `0x1800d0614`
- `0x1800d1d00`
- `0x1800d1d1c`
- `0x1800d26ec`
- `0x1800d284c`
- `0x1800d5988`
- `0x1800d6704`
- `0x1800d6cd8`
- `0x1800d728c`
- `0x1800d779c`
- `0x1800d9588`
- `0x1800d98c4`
- `0x1800d9da0`
- `0x1800da32c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5b70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5c9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5d8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5b70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5c9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5d8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5ba5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5bd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5ba5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5bd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WdcStartupMonitor::MapStartupProcesses(WdcStartupMonitor *a1, __int64 a2, __int64 *a3)
{
  WdcStartupMonitor *v4; // r14
  __int64 v5; // r12
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rax
  int v8; // r8d
  int StartupProcessesIndex; // eax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 *v13; // r12
  int v14; // esi
  double v15; // xmm6_8
  double v16; // xmm7_8
  unsigned int i; // r15d
  unsigned int v18; // edx
  struct _WDC_STARTUP_INFO *v19; // rbx
  int DetailsFromCrudeCmdLine; // r14d
  unsigned int v21; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  bool v23; // r8
  WdcStartupMonitor *v24; // rcx
  __int64 v25; // r8
  const unsigned __int16 *v26; // rax
  WdcStartupMonitor *v27; // rcx
  __int64 v28; // rdx
  __int64 v30; // r8
  unsigned int v31; // eax
  int ResIDFromStartupImpact; // eax
  __int64 v33; // r8
  int v34; // [rsp+28h] [rbp-E0h]
  HSTRING string; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v36[2]; // [rsp+40h] [rbp-C8h] BYREF
  struct _WDC_STARTUP_INFO *v37; // [rsp+48h] [rbp-C0h] BYREF
  struct _WDC_DATA_INFO *v38; // [rsp+50h] [rbp-B8h] BYREF
  void *v39; // [rsp+58h] [rbp-B0h] BYREF
  WdcStartupMonitor *v40; // [rsp+60h] [rbp-A8h]
  _BYTE v41[16]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 v42[1024]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v43; // [rsp+878h] [rbp+770h]
  int v44; // [rsp+880h] [rbp+778h]
  double v45; // [rsp+890h] [rbp+788h]
  double v46; // [rsp+898h] [rbp+790h]
  wil::details::in1diag3 *retaddr; // [rsp+910h] [rbp+808h]

  v4 = a1;
  v40 = a1;
  v36[0] = 0;
  string = 0;
  v37 = 0;
  memset_0(v41, 0, 0x840u);
  v5 = *a3;
  v6 = *(unsigned int *)(*((_QWORD *)v4 + 2) + 16LL);
  v7 = 4 * v6;
  if ( !is_mul_ok(v6, 4u) )
    v7 = -1;
  v39 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  memset_0(v39, 0, 4 * v6);
  StartupProcessesIndex = CStartupImpactHelper::GetStartupProcessesIndex(
                            *((CStartupImpactHelper **)v4 + 2),
                            *(HSTRING *)(*a3 + 440),
                            v8,
                            (unsigned int *)v39,
                            v36);
  v11 = StartupProcessesIndex;
  if ( StartupProcessesIndex >= 0 )
  {
    v13 = (__int64 *)(v5 + 624);
    v14 = 0;
    v15 = 0.0;
    v16 = 0.0;
    for ( i = 0; i < v36[0]; ++i )
    {
      v38 = 0;
      v14 = WdcStartupMonitor::CreateEntry(v10, &v38, 0x4000);
      if ( v14 < 0 )
      {
        WdcStartupMonitor::DataExpire(v38, v18);
        v11 = v14;
        goto LABEL_22;
      }
      std::unique_ptr<_WDC_STARTUP_INFO *,WdcStartupMonitor::StartupInfoDeleter>::reset(&v37, v38);
      StartupProcessesIndex = CStartupImpactHelper::GetProcStartupImpact(
                                *((CStartupImpactHelper **)v4 + 2),
                                *((_DWORD *)v39 + i),
                                (struct _STARTUPIMPACT *)v41);
      v11 = StartupProcessesIndex;
      if ( StartupProcessesIndex < 0 )
      {
        v12 = 1162;
        goto LABEL_20;
      }
      v19 = v37;
      DetailsFromCrudeCmdLine = Microsoft::WRL::Wrappers::HString::Set<260>((char *)v37 + 440, v42);
      if ( DetailsFromCrudeCmdLine < 0 )
      {
        v28 = 1164;
        goto LABEL_18;
      }
      *((double *)v19 + 41) = v46;
      *((double *)v19 + 36) = v45;
      *((_QWORD *)v19 + 63) = v43;
      *((_DWORD *)v19 + 128) = v44;
      v15 = v15 + v46;
      v16 = v16 + v45;
      v21 = CStartupImpactHelper::CalcStartupImpact();
      *((double *)v19 + 26) = (double)(int)TmGetResIDFromStartupImpact(v21);
      WindowsDeleteString(string);
      string = 0;
      DetailsFromCrudeCmdLine = TmGetDetailsFromCrudeCmdLine(v42, 0, &string, 0);
      if ( DetailsFromCrudeCmdLine < 0 )
      {
        v28 = 1194;
        goto LABEL_18;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      DetailsFromCrudeCmdLine = WdcStartupMonitor::SetFileData(v40, StringRawBuffer, v23, v19);
      if ( DetailsFromCrudeCmdLine < 0 )
      {
        v28 = 1196;
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v28,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
          (const char *)(unsigned int)DetailsFromCrudeCmdLine,
          v34);
        v11 = DetailsFromCrudeCmdLine;
        goto LABEL_22;
      }
      WdcStartupMonitor::_SetIcon(v24, string, v25, (HSTRING *)v19);
      v26 = WindowsGetStringRawBuffer(string, 0);
      WdcStartupMonitor::_CheckAndSetInvalidPathFlag(v27, v26, v19);
      v10 = *v13;
      if ( *(__int64 **)(*v13 + 8) != v13 )
        __fastfail(3u);
      *((_QWORD *)v19 + 2) = v10;
      *((_QWORD *)v19 + 3) = v13;
      *(_QWORD *)(v10 + 8) = (char *)v19 + 16;
      *v13 = (__int64)v19 + 16;
      *((_QWORD *)v19 + 4) = i;
      ++*(_DWORD *)(*a3 + 616);
      v37 = 0;
      v4 = v40;
    }
    *(_DWORD *)(*a3 + 184) &= ~0x800u;
    *(_QWORD *)(*a3 + 192) = 0;
    v30 = *a3;
    if ( *(_DWORD *)(*a3 + 616) )
    {
      v31 = CStartupImpactHelper::CalcStartupImpact();
      ResIDFromStartupImpact = TmGetResIDFromStartupImpact(v31);
      *(double *)(v33 + 208) = (double)ResIDFromStartupImpact;
      *(double *)(*a3 + 328) = v15;
      *(double *)(*a3 + 288) = v16;
      *(double *)(*a3 + 72) = (double)*(int *)(*a3 + 616);
    }
    else if ( *(double *)(v30 + 168) == 36006.0 )
    {
      *(_QWORD *)(v30 + 208) = 0x40E24F4000000000LL;
    }
    else
    {
      *(_QWORD *)(v30 + 208) = 0x40E24F6000000000LL;
      *(_DWORD *)(*a3 + 184) |= 0x800u;
      *(_QWORD *)(*a3 + 192) = 0x40E30C0000000000LL;
    }
    std::unique_ptr<unsigned long [0]>::~unique_ptr<unsigned long [0]>(&v39);
    std::unique_ptr<_WDC_STARTUP_INFO *,WdcStartupMonitor::StartupInfoDeleter>::~unique_ptr<_WDC_STARTUP_INFO *,WdcStartupMonitor::StartupInfoDeleter>(&v37);
    WindowsDeleteString(string);
    return (unsigned int)v14;
  }
  else
  {
    v12 = 1146;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
      (const char *)(unsigned int)StartupProcessesIndex,
      v34);
LABEL_22:
    std::unique_ptr<unsigned long [0]>::~unique_ptr<unsigned long [0]>(&v39);
    std::unique_ptr<_WDC_STARTUP_INFO *,WdcStartupMonitor::StartupInfoDeleter>::~unique_ptr<_WDC_STARTUP_INFO *,WdcStartupMonitor::StartupInfoDeleter>(&v37);
    WindowsDeleteString(string);
    return v11;
  }
}

```

## disassembly

```asm
0x1800d5988  mov     rax, rsp
0x1800d598b  mov     [rax+10h], rbx
0x1800d598f  push    rbp
0x1800d5990  push    rsi
0x1800d5991  push    rdi
0x1800d5992  push    r12
0x1800d5994  push    r13
0x1800d5996  push    r14
0x1800d5998  push    r15
0x1800d599a  lea     rbp, [rax-808h]
0x1800d59a1  sub     rsp, 8D0h
0x1800d59a8  movaps  xmmword ptr [rax-48h], xmm6
0x1800d59ac  movaps  xmmword ptr [rax-58h], xmm7
0x1800d59b0  mov     rax, cs:__security_cookie
0x1800d59b7  xor     rax, rsp
0x1800d59ba  mov     [rbp+800h+var_60], rax
0x1800d59c1  mov     rdi, r8
0x1800d59c4  mov     r14, rcx
0x1800d59c7  mov     [rsp+900h+var_8A8], rcx
0x1800d59cc  xor     r13d, r13d
0x1800d59cf  mov     [rsp+900h+var_8C8], r13d
0x1800d59d4  mov     [rsp+900h+string], r13
0x1800d59d9  mov     [rsp+900h+var_8C0], r13
0x1800d59de  xor     edx, edx; Val
0x1800d59e0  mov     r8d, 840h; Size
0x1800d59e6  lea     rcx, [rsp+900h+var_8A0]; void *
0x1800d59eb  call    memset_0
0x1800d59f0  mov     r12, [rdi]
0x1800d59f3  mov     rax, [r14+10h]
0x1800d59f7  mov     ebx, [rax+10h]
0x1800d59fa  lea     eax, [r13+4]
0x1800d59fe  mul     rbx
0x1800d5a01  lea     rcx, [r13-1]
0x1800d5a05  cmovb   rax, rcx
0x1800d5a09  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d5a10  mov     rcx, rax; unsigned __int64
0x1800d5a13  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800d5a18  mov     rsi, rax
0x1800d5a1b  mov     [rsp+900h+var_8B0], rax
0x1800d5a20  lea     r8, ds:0[rbx*4]; Size
0x1800d5a28  xor     edx, edx; Val
0x1800d5a2a  mov     rcx, rax; void *
0x1800d5a2d  call    memset_0
0x1800d5a32  mov     rdx, [rdi]
0x1800d5a35  lea     rax, [rsp+900h+var_8C8]
0x1800d5a3a  mov     qword ptr [rsp+900h+var_8E0], rax; int
0x1800d5a3f  mov     r9, rsi; unsigned int *
0x1800d5a42  mov     rdx, [rdx+1B8h]; HSTRING
0x1800d5a49  mov     rcx, [r14+10h]; this
0x1800d5a4d  call    ?GetStartupProcessesIndex@CStartupImpactHelper@@QEAAJPEAUHSTRING__@@HPEAK1@Z; CStartupImpactHelper::GetStartupProcessesIndex(HSTRING__ *,int,ulong *,ulong *)
0x1800d5a52  mov     ebx, eax
0x1800d5a54  test    eax, eax
0x1800d5a56  jns     short loc_1800D5A62
0x1800d5a58  mov     edx, 47Ah
0x1800d5a5d  jmp     loc_1800D5C60
0x1800d5a62  add     r12, 270h
0x1800d5a69  mov     esi, r13d
0x1800d5a6c  xorps   xmm6, xmm6
0x1800d5a6f  xorps   xmm7, xmm7
0x1800d5a72  mov     r15d, r13d
0x1800d5a75  cmp     r15d, [rsp+900h+var_8C8]
0x1800d5a7a  jnb     loc_1800D5CAC
0x1800d5a80  mov     [rsp+900h+var_8B8], r13
0x1800d5a85  mov     r8d, 4000h
0x1800d5a8b  lea     rdx, [rsp+900h+var_8B8]
0x1800d5a90  call    ?CreateEntry@WdcStartupMonitor@@QEAAJPEAPEAU_WDC_STARTUP_INFO@@W4_tagTM_ITEMTYPE@@@Z; WdcStartupMonitor::CreateEntry(_WDC_STARTUP_INFO * *,_tagTM_ITEMTYPE)
0x1800d5a95  mov     esi, eax
0x1800d5a97  test    eax, eax
0x1800d5a99  js      loc_1800D5C78
0x1800d5a9f  mov     rdx, [rsp+900h+var_8B8]
0x1800d5aa4  lea     rcx, [rsp+900h+var_8C0]
0x1800d5aa9  call    ?reset@?$unique_ptr@PEAU_WDC_STARTUP_INFO@@UStartupInfoDeleter@WdcStartupMonitor@@@std@@QEAAXPEAU_WDC_STARTUP_INFO@@@Z; std::unique_ptr<_WDC_STARTUP_INFO *,WdcStartupMonitor::StartupInfoDeleter>::reset(_WDC_STARTUP_INFO *)
0x1800d5aae  mov     r13d, r15d
0x1800d5ab1  lea     r8, [rsp+900h+var_8A0]; struct _STARTUPIMPACT *
0x1800d5ab6  mov     rax, [rsp+900h+var_8B0]
0x1800d5abb  mov     edx, [rax+r13*4]; unsigned int
0x1800d5abf  mov     rcx, [r14+10h]; this
0x1800d5ac3  call    ?GetProcStartupImpact@CStartupImpactHelper@@QEAAJKPEAU_STARTUPIMPACT@@@Z; CStartupImpactHelper::GetProcStartupImpact(ulong,_STARTUPIMPACT *)
0x1800d5ac8  mov     ebx, eax
0x1800d5aca  test    eax, eax
0x1800d5acc  js      loc_1800D5C5B
0x1800d5ad2  mov     rbx, [rsp+900h+var_8C0]
0x1800d5ad7  lea     rcx, [rbx+1B8h]
0x1800d5ade  lea     rdx, [rsp+900h+var_890]
0x1800d5ae3  call    ??$Set@$0BAE@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HString::Set<260>(ushort (&)[260])
0x1800d5ae8  mov     r14d, eax
0x1800d5aeb  test    eax, eax
0x1800d5aed  js      loc_1800D5C3B
0x1800d5af3  movsd   xmm0, [rbp+800h+var_70]
0x1800d5afb  movsd   qword ptr [rbx+148h], xmm0
0x1800d5b03  movsd   xmm1, [rbp+800h+var_78]
0x1800d5b0b  movsd   qword ptr [rbx+120h], xmm1
0x1800d5b13  movsd   xmm0, [rbp+800h+var_90]
0x1800d5b1b  movsd   qword ptr [rbx+1F8h], xmm0
0x1800d5b23  mov     eax, [rbp+800h+var_88]
0x1800d5b29  mov     [rbx+200h], eax
0x1800d5b2f  addsd   xmm6, [rbp+800h+var_70]
0x1800d5b37  addsd   xmm7, [rbp+800h+var_78]
0x1800d5b3f  movsd   xmm1, [rbp+800h+var_78]
0x1800d5b47  movsd   xmm0, [rbp+800h+var_70]
0x1800d5b4f  call    ?CalcStartupImpact@CStartupImpactHelper@@SA?AW4_TM_STARTUPIMPACT@@NN@Z; CStartupImpactHelper::CalcStartupImpact(double,double)
0x1800d5b54  mov     ecx, eax
0x1800d5b56  call    ?TmGetResIDFromStartupImpact@@YAHW4_TM_STARTUPIMPACT@@@Z; TmGetResIDFromStartupImpact(_TM_STARTUPIMPACT)
0x1800d5b5b  movd    xmm0, eax
0x1800d5b5f  cvtdq2pd xmm0, xmm0
0x1800d5b63  movsd   qword ptr [rbx+0D0h], xmm0
0x1800d5b6b  mov     rcx, [rsp+900h+string]; string
0x1800d5b70  call    cs:__imp_WindowsDeleteString
0x1800d5b76  mov     [rsp+900h+string], 0
0x1800d5b7f  xor     r9d, r9d; HSTRING *
0x1800d5b82  lea     r8, [rsp+900h+string]; HSTRING *
0x1800d5b87  xor     edx, edx; HSTRING *
0x1800d5b89  lea     rcx, [rsp+900h+var_890]; unsigned __int16 *
0x1800d5b8e  call    ?TmGetDetailsFromCrudeCmdLine@@YAJPEBGPEAPEAUHSTRING__@@11@Z; TmGetDetailsFromCrudeCmdLine(ushort const *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1800d5b93  mov     r14d, eax
0x1800d5b96  test    eax, eax
0x1800d5b98  js      loc_1800D5C34
0x1800d5b9e  xor     edx, edx; length
0x1800d5ba0  mov     rcx, [rsp+900h+string]; string
0x1800d5ba5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5bab  mov     r9, rbx; struct _WDC_STARTUP_INFO *
0x1800d5bae  mov     rdx, rax; unsigned __int16 *
0x1800d5bb1  mov     rcx, [rsp+900h+var_8A8]; this
0x1800d5bb6  call    ?SetFileData@WdcStartupMonitor@@QEAAJPEBG_NPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::SetFileData(ushort const *,bool,_WDC_STARTUP_INFO *)
0x1800d5bbb  mov     r14d, eax
0x1800d5bbe  test    eax, eax
0x1800d5bc0  js      short loc_1800D5C2D
0x1800d5bc2  mov     r9, rbx; struct _WDC_STARTUP_INFO *
0x1800d5bc5  mov     rdx, [rsp+900h+string]; HSTRING
0x1800d5bca  call    ?_SetIcon@WdcStartupMonitor@@AEAAJPEAUHSTRING__@@_NPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::_SetIcon(HSTRING__ *,bool,_WDC_STARTUP_INFO *)
0x1800d5bcf  xor     edx, edx; length
0x1800d5bd1  mov     rcx, [rsp+900h+string]; string
0x1800d5bd6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5bdc  mov     r8, rbx; struct _WDC_STARTUP_INFO *
0x1800d5bdf  mov     rdx, rax; unsigned __int16 *
0x1800d5be2  call    ?_CheckAndSetInvalidPathFlag@WdcStartupMonitor@@AEAAXPEBGPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::_CheckAndSetInvalidPathFlag(ushort const *,_WDC_STARTUP_INFO *)
0x1800d5be7  mov     rcx, [r12]
0x1800d5beb  cmp     [rcx+8], r12
0x1800d5bef  jnz     short loc_1800D5C26
0x1800d5bf1  lea     rax, [rbx+10h]
0x1800d5bf5  mov     [rax], rcx
0x1800d5bf8  mov     [rax+8], r12
0x1800d5bfc  mov     [rcx+8], rax
0x1800d5c00  mov     [r12], rax
0x1800d5c04  mov     [rbx+20h], r13
0x1800d5c08  mov     rax, [rdi]
0x1800d5c0b  inc     dword ptr [rax+268h]
0x1800d5c11  xor     r13d, r13d
0x1800d5c14  mov     [rsp+900h+var_8C0], r13
0x1800d5c19  inc     r15d
0x1800d5c1c  mov     r14, [rsp+900h+var_8A8]
0x1800d5c21  jmp     loc_1800D5A75
0x1800d5c26  mov     ecx, 3
0x1800d5c2b  int     29h; Win8: RtlFailFast(ecx)
0x1800d5c2d  mov     edx, 4ACh
0x1800d5c32  jmp     short loc_1800D5C40
0x1800d5c34  mov     edx, 4AAh
0x1800d5c39  jmp     short loc_1800D5C40
0x1800d5c3b  mov     edx, 48Ch; void *
0x1800d5c40  mov     rcx, [rbp+808h]; this
0x1800d5c47  mov     r9d, r14d; char *
0x1800d5c4a  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d5c51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d5c56  mov     ebx, r14d
0x1800d5c59  jmp     short loc_1800D5C84
0x1800d5c5b  mov     edx, 48Ah; void *
0x1800d5c60  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d5c67  mov     r9d, eax; char *
0x1800d5c6a  mov     rcx, [rbp+808h]; this
0x1800d5c71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d5c76  jmp     short loc_1800D5C84
0x1800d5c78  mov     rcx, [rsp+900h+var_8B8]; struct _WDC_DATA_INFO *
0x1800d5c7d  call    ?DataExpire@WdcStartupMonitor@@SAJPEAU_WDC_DATA_INFO@@K@Z; WdcStartupMonitor::DataExpire(_WDC_DATA_INFO *,ulong)
0x1800d5c82  mov     ebx, esi
0x1800d5c84  lea     rcx, [rsp+900h+var_8B0]
0x1800d5c89  call    ??1?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@std@@@std@@QEAA@XZ; std::unique_ptr<ulong [0]>::~unique_ptr<ulong [0]>(void)
0x1800d5c8e  nop
0x1800d5c8f  lea     rcx, [rsp+900h+var_8C0]
0x1800d5c94  call    ??1?$unique_ptr@PEAU_WDC_STARTUP_INFO@@UStartupInfoDeleter@WdcStartupMonitor@@@std@@QEAA@XZ; std::unique_ptr<_WDC_STARTUP_INFO *,WdcStartupMonitor::StartupInfoDeleter>::~unique_ptr<_WDC_STARTUP_INFO *,WdcStartupMonitor::StartupInfoDeleter>(void)
0x1800d5c99  nop
0x1800d5c9a  mov     rcx, [rsp+900h+string]; string
0x1800d5c9f  call    cs:__imp_WindowsDeleteString
0x1800d5ca5  mov     eax, ebx
0x1800d5ca7  jmp     loc_1800D5D97
0x1800d5cac  mov     rax, [rdi]
0x1800d5caf  btr     dword ptr [rax+0B8h], 0Bh
0x1800d5cb7  mov     rax, [rdi]
0x1800d5cba  mov     [rax+0C0h], r13
0x1800d5cc1  mov     r8, [rdi]
0x1800d5cc4  cmp     [r8+268h], r13d
0x1800d5ccb  jz      short loc_1800D5D1C
0x1800d5ccd  movaps  xmm1, xmm7
0x1800d5cd0  movaps  xmm0, xmm6
0x1800d5cd3  call    ?CalcStartupImpact@CStartupImpactHelper@@SA?AW4_TM_STARTUPIMPACT@@NN@Z; CStartupImpactHelper::CalcStartupImpact(double,double)
0x1800d5cd8  mov     ecx, eax
0x1800d5cda  call    ?TmGetResIDFromStartupImpact@@YAHW4_TM_STARTUPIMPACT@@@Z; TmGetResIDFromStartupImpact(_TM_STARTUPIMPACT)
0x1800d5cdf  movd    xmm0, eax
0x1800d5ce3  cvtdq2pd xmm0, xmm0
0x1800d5ce7  movsd   qword ptr [r8+0D0h], xmm0
0x1800d5cf0  mov     rax, [rdi]
0x1800d5cf3  movsd   qword ptr [rax+148h], xmm6
0x1800d5cfb  mov     rax, [rdi]
0x1800d5cfe  movsd   qword ptr [rax+120h], xmm7
0x1800d5d06  mov     rax, [rdi]
0x1800d5d09  movd    xmm0, dword ptr [rax+268h]
0x1800d5d11  cvtdq2pd xmm0, xmm0
0x1800d5d15  movsd   qword ptr [rax+48h], xmm0
0x1800d5d1a  jmp     short loc_1800D5D74
0x1800d5d1c  movsd   xmm0, qword ptr [r8+0A8h]
0x1800d5d25  ucomisd xmm0, cs:__real@40e194c000000000
0x1800d5d2d  jp      short loc_1800D5D44
0x1800d5d2f  jnz     short loc_1800D5D44
0x1800d5d31  mov     rax, 40E24F4000000000h
0x1800d5d3b  mov     [r8+0D0h], rax
0x1800d5d42  jmp     short loc_1800D5D74
0x1800d5d44  mov     rax, 40E24F6000000000h
0x1800d5d4e  mov     [r8+0D0h], rax
0x1800d5d55  mov     rax, [rdi]
0x1800d5d58  bts     dword ptr [rax+0B8h], 0Bh
0x1800d5d60  mov     rax, [rdi]
0x1800d5d63  mov     rcx, 40E30C0000000000h
0x1800d5d6d  mov     [rax+0C0h], rcx
0x1800d5d74  lea     rcx, [rsp+900h+var_8B0]
0x1800d5d79  call    ??1?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@std@@@std@@QEAA@XZ; std::unique_ptr<ulong [0]>::~unique_ptr<ulong [0]>(void)
0x1800d5d7e  nop
0x1800d5d7f  lea     rcx, [rsp+900h+var_8C0]
0x1800d5d84  call    ??1?$unique_ptr@PEAU_WDC_STARTUP_INFO@@UStartupInfoDeleter@WdcStartupMonitor@@@std@@QEAA@XZ; std::unique_ptr<_WDC_STARTUP_INFO *,WdcStartupMonitor::StartupInfoDeleter>::~unique_ptr<_WDC_STARTUP_INFO *,WdcStartupMonitor::StartupInfoDeleter>(void)
0x1800d5d89  nop
0x1800d5d8a  mov     rcx, [rsp+900h+string]; string
0x1800d5d8f  call    cs:__imp_WindowsDeleteString
0x1800d5d95  mov     eax, esi
0x1800d5d97  mov     rcx, [rbp+800h+var_60]
0x1800d5d9e  xor     rcx, rsp; StackCookie
0x1800d5da1  call    __security_check_cookie
0x1800d5da6  lea     r11, [rsp+900h+var_30]
0x1800d5dae  mov     rbx, [r11+48h]
0x1800d5db2  movaps  xmm6, xmmword ptr [r11-10h]
0x1800d5db7  movaps  xmm7, xmmword ptr [r11-20h]
0x1800d5dbc  mov     rsp, r11
0x1800d5dbf  pop     r15
0x1800d5dc1  pop     r14
0x1800d5dc3  pop     r13
0x1800d5dc5  pop     r12
0x1800d5dc7  pop     rdi
0x1800d5dc8  pop     rsi
0x1800d5dc9  pop     rbp
0x1800d5dca  retn
```
