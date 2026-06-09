# CMPEG2Demultiplexer::LoadMpeg2Transport_(void)

- ea: `0x180015a0c`
- end: `0x180015d5f`
- name: `?LoadMpeg2Transport_@CMPEG2Demultiplexer@@AEAAJXZ`
- size: `851`
- prototype: `__int64 __fastcall(CMPEG2Demultiplexer *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800176e8`

## callees

- `0x180001008`
- `0x180001048`
- `0x180011d44`
- `0x180015a0c`
- `0x18001991c`
- `0x18001a160`
- `0x18001d190`
- `0x18002506c`
- `0x180025570`
- `0x180034010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180015d43`
- `ADVAPI32!RegCloseKey` at `0x180015d43`
- `ADVAPI32!RegCreateKeyExW` at `0x180015a87`
- `ADVAPI32!RegCreateKeyExW` at `0x180015a87`

## pseudocode

```c
__int64 __fastcall CMPEG2Demultiplexer::LoadMpeg2Transport_(CMPEG2Demultiplexer *this)
{
  HKEY *v1; // r15
  int v3; // esi
  CMPEG2TransportController *v4; // rdi
  BOOL v5; // eax
  struct CMpeg2Stats **v6; // rbx
  CMPEG2PushClock *v7; // r10
  CMPEG2PushClock *v8; // rax
  CMPEG2TransportController *v9; // rax
  CMPEG2TransportController *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  CMpeg2Stats *v13; // rbx
  int v14; // eax
  void *v15; // rbx
  HKEY v16; // rcx
  unsigned int v18; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v19; // [rsp+64h] [rbp-14h] BYREF
  unsigned int v20; // [rsp+68h] [rbp-10h] BYREF
  DWORD dwDisposition[3]; // [rsp+6Ch] [rbp-Ch] BYREF
  int v22; // [rsp+C0h] [rbp+48h] BYREF
  unsigned int v23; // [rsp+C8h] [rbp+50h] BYREF
  unsigned int v24; // [rsp+D0h] [rbp+58h] BYREF
  unsigned int v25; // [rsp+D8h] [rbp+60h] BYREF

  v1 = (HKEY *)((char *)this + 272);
  v22 = 0;
  v3 = 0;
  dwDisposition[0] = 0;
  v23 = 0;
  v4 = 0;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  v25 = 0;
  v24 = 0;
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\MPEG2Demultiplexer\\Transport",
         0,
         0,
         0,
         0x2001Fu,
         0,
         (PHKEY)this + 34,
         dwDisposition) )
  {
    *v1 = 0;
  }
  if ( *((_DWORD *)this + 73) )
  {
    v5 = 0;
  }
  else
  {
    RegGetValIfExist(*v1, L"Clock", 1u, 1, &v23);
    v5 = v23 != 0;
  }
  *((_DWORD *)this + 72) = v5;
  RegGetValIfExist(*v1, L"ClockSubordinateMinSamplingWindowMillis", 0x7D0u, 1, &v20);
  RegGetValIfExist(*v1, L"ClockSubordinateHistoryMillis", 0x3A980u, 1, &v19);
  RegGetValIfExist(*v1, L"ClockSubordinateMinSlavable", 0x5Fu, 1, &v18);
  RegGetValIfExist(*v1, L"ClockSubordinateMaxSlavable", 0x69u, 1, &v25);
  RegGetValIfExist(*v1, L"ShiftMaxGlitchesPerHour", 0x3Cu, 1, &v24);
  RegGetValIfExist(*v1, L"SimulatePBDA", 0, 1, (unsigned int *)this + 356);
  v6 = (struct CMpeg2Stats **)((char *)this + 264);
  v7 = (CMPEG2PushClock *)operator new(0x2B8u);
  if ( v7 )
  {
    v8 = CMPEG2PushClock::CMPEG2PushClock(v7, *((_DWORD *)this + 72), *v1, *v6, this, v20, v19, v18, v25, v24, &v22);
    v3 = v22;
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 35) = v8;
  if ( !v8 )
    goto LABEL_23;
  if ( v3 < 0 )
    goto LABEL_26;
  v9 = (CMPEG2TransportController *)operator new(0xE0u);
  if ( !v9 )
    goto LABEL_20;
  v10 = CMPEG2TransportController::CMPEG2TransportController(
          v9,
          *v1,
          this,
          *v6,
          *((struct CMPEG2PushClock **)this + 35),
          &v22);
  v3 = v22;
  v4 = v10;
  if ( !v10 )
    goto LABEL_20;
  v11 = *(_QWORD *)v10;
  if ( v22 < 0 )
  {
    (*(void (__fastcall **)(CMPEG2TransportController *, __int64))(v11 + 40))(v4, 1);
LABEL_20:
    if ( v3 < 0 )
      goto LABEL_26;
    v3 = -2147024882;
    goto LABEL_22;
  }
  v3 = (*(__int64 (__fastcall **)(CMPEG2TransportController *))(v11 + 48))(v4);
  if ( v3 >= 0 )
    v3 = (*(__int64 (__fastcall **)(CMPEG2TransportController *))(*(_QWORD *)v4 + 56LL))(v4);
  if ( v3 < 0 )
  {
    (*(void (__fastcall **)(CMPEG2TransportController *, __int64))(*(_QWORD *)v4 + 40LL))(v4, 1);
LABEL_22:
    v4 = 0;
    goto LABEL_23;
  }
  v12 = *((_QWORD *)this + 35);
  *((_QWORD *)this + 42) = v4;
  *(_QWORD *)(v12 + 624) = *((_QWORD *)v4 + 17);
  v13 = *v6;
  v14 = StatsEnabled(L"SOFTWARE\\Microsoft\\MPEG2Demultiplexer\\Transport");
  CMpeg2Stats::Initialize(v13, v14, 1u);
LABEL_23:
  if ( v3 >= 0 )
    return (unsigned int)v3;
  if ( v4 )
    (*(void (__fastcall **)(CMPEG2TransportController *, __int64))(*(_QWORD *)v4 + 40LL))(v4, 1);
LABEL_26:
  v15 = (void *)*((_QWORD *)this + 35);
  if ( v15 )
  {
    CMPEG2PushClock::~CMPEG2PushClock(*((CMPEG2PushClock **)this + 35));
    operator delete(v15, 0x2B8u);
  }
  v16 = *v1;
  *((_QWORD *)this + 35) = 0;
  if ( v16 )
  {
    RegCloseKey(v16);
    *v1 = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180015a0c  push    rbp
0x180015a0e  push    rbx
0x180015a0f  push    rsi
0x180015a10  push    rdi
0x180015a11  push    r12
0x180015a13  push    r13
0x180015a15  push    r14
0x180015a17  push    r15
0x180015a19  mov     rbp, rsp
0x180015a1c  sub     rsp, 78h
0x180015a20  xor     r12d, r12d
0x180015a23  lea     r15, [rcx+110h]
0x180015a2a  lea     rax, [rbp+dwDisposition]
0x180015a2e  mov     [rbp+arg_0], r12d
0x180015a32  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180015a37  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\MPEG2Demultiplexer"...
0x180015a3e  mov     [rsp+78h+phkResult], r15; phkResult
0x180015a43  mov     r14, rcx
0x180015a46  mov     [rsp+78h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180015a4b  xor     r9d, r9d; lpClass
0x180015a4e  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180015a56  xor     r8d, r8d; Reserved
0x180015a59  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180015a60  mov     [rsp+78h+dwOptions], r12d; dwOptions
0x180015a65  mov     esi, r12d
0x180015a68  mov     [rbp+dwDisposition], r12d
0x180015a6c  mov     [rbp+arg_8], r12d
0x180015a70  mov     edi, r12d
0x180015a73  mov     [rbp+var_10], r12d
0x180015a77  mov     [rbp+var_14], r12d
0x180015a7b  mov     [rbp+var_18], r12d
0x180015a7f  mov     [rbp+arg_18], r12d
0x180015a83  mov     [rbp+arg_10], r12d
0x180015a87  call    cs:__imp_RegCreateKeyExW
0x180015a8d  test    eax, eax
0x180015a8f  jz      short loc_180015A94
0x180015a91  mov     [r15], r12
0x180015a94  mov     r13d, 1
0x180015a9a  cmp     [r14+124h], r12d
0x180015aa1  jnz     short loc_180015ACD
0x180015aa3  mov     rcx, [r15]; hKey
0x180015aa6  lea     rax, [rbp+arg_8]
0x180015aaa  mov     r9d, r13d; int
0x180015aad  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int *
0x180015ab2  mov     r8d, r13d; unsigned int
0x180015ab5  lea     rdx, aClock; "Clock"
0x180015abc  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180015ac1  cmp     [rbp+arg_8], r12d
0x180015ac5  mov     eax, r12d
0x180015ac8  setnz   al
0x180015acb  jmp     short loc_180015AD0
0x180015acd  mov     eax, r12d
0x180015ad0  mov     [r14+120h], eax
0x180015ad7  lea     rdx, aClocksubordina_0; "ClockSubordinateMinSamplingWindowMillis"
0x180015ade  mov     rcx, [r15]; hKey
0x180015ae1  lea     rax, [rbp+var_10]
0x180015ae5  mov     r9d, r13d; int
0x180015ae8  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int *
0x180015aed  mov     r8d, 7D0h; unsigned int
0x180015af3  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180015af8  mov     rcx, [r15]; hKey
0x180015afb  lea     rax, [rbp+var_14]
0x180015aff  mov     r9d, r13d; int
0x180015b02  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int *
0x180015b07  mov     r8d, 3A980h; unsigned int
0x180015b0d  lea     rdx, aClocksubordina; "ClockSubordinateHistoryMillis"
0x180015b14  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180015b19  mov     rcx, [r15]; hKey
0x180015b1c  lea     rax, [rbp+var_18]
0x180015b20  mov     r9d, r13d; int
0x180015b23  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int *
0x180015b28  mov     r8d, 5Fh ; '_'; unsigned int
0x180015b2e  lea     rdx, aClocksubordina_3; "ClockSubordinateMinSlavable"
0x180015b35  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180015b3a  mov     rcx, [r15]; hKey
0x180015b3d  lea     rax, [rbp+arg_18]
0x180015b41  mov     r9d, r13d; int
0x180015b44  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int *
0x180015b49  mov     r8d, 69h ; 'i'; unsigned int
0x180015b4f  lea     rdx, aClocksubordina_1; "ClockSubordinateMaxSlavable"
0x180015b56  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180015b5b  mov     rcx, [r15]; hKey
0x180015b5e  lea     rax, [rbp+arg_10]
0x180015b62  mov     r9d, r13d; int
0x180015b65  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int *
0x180015b6a  mov     r8d, 3Ch ; '<'; unsigned int
0x180015b70  lea     rdx, aShiftmaxglitch; "ShiftMaxGlitchesPerHour"
0x180015b77  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180015b7c  mov     rcx, [r15]; hKey
0x180015b7f  lea     rax, [r14+590h]
0x180015b86  mov     r9d, r13d; int
0x180015b89  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int *
0x180015b8e  xor     r8d, r8d; unsigned int
0x180015b91  lea     rdx, aSimulatepbda; "SimulatePBDA"
0x180015b98  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180015b9d  mov     ecx, 2B8h; Size
0x180015ba2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015ba7  lea     rbx, [r14+108h]
0x180015bae  mov     r10, rax
0x180015bb1  test    rax, rax
0x180015bb4  jz      short loc_180015C01
0x180015bb6  mov     ecx, [rbp+arg_10]
0x180015bb9  lea     rax, [rbp+arg_0]
0x180015bbd  mov     r9, [rbx]; struct CMpeg2Stats *
0x180015bc0  mov     r8, [r15]; HKEY
0x180015bc3  mov     edx, [r14+120h]; int
0x180015bca  mov     [rsp+78h+var_28], rax; int *
0x180015bcf  mov     eax, [rbp+var_10]
0x180015bd2  mov     [rsp+78h+var_30], ecx; unsigned int
0x180015bd6  mov     ecx, [rbp+arg_18]
0x180015bd9  mov     dword ptr [rsp+78h+lpdwDisposition], ecx; unsigned int
0x180015bdd  mov     ecx, [rbp+var_18]
0x180015be0  mov     dword ptr [rsp+78h+phkResult], ecx; unsigned int
0x180015be4  mov     ecx, [rbp+var_14]
0x180015be7  mov     dword ptr [rsp+78h+lpSecurityAttributes], ecx; unsigned int
0x180015beb  mov     rcx, r10; this
0x180015bee  mov     [rsp+78h+samDesired], eax; unsigned int
0x180015bf2  mov     qword ptr [rsp+78h+dwOptions], r14; struct CMPEG2Demultiplexer *
0x180015bf7  call    ??0CMPEG2PushClock@@QEAA@HPEAUHKEY__@@PEAVCMpeg2Stats@@PEAVCMPEG2Demultiplexer@@KKKKKPEAJ@Z; CMPEG2PushClock::CMPEG2PushClock(int,HKEY__ *,CMpeg2Stats *,CMPEG2Demultiplexer *,ulong,ulong,ulong,ulong,ulong,long *)
0x180015bfc  mov     esi, [rbp+arg_0]
0x180015bff  jmp     short loc_180015C04
0x180015c01  mov     rax, r12
0x180015c04  mov     [r14+118h], rax
0x180015c0b  test    rax, rax
0x180015c0e  jz      loc_180015CF8
0x180015c14  test    esi, esi
0x180015c16  js      loc_180015D13
0x180015c1c  mov     ecx, 0E0h; Size
0x180015c21  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015c26  test    rax, rax
0x180015c29  jz      loc_180015CEC
0x180015c2f  mov     r9, [rbx]; struct CMpeg2Stats *
0x180015c32  lea     rcx, [rbp+arg_0]
0x180015c36  mov     rdx, [r15]; hKey
0x180015c39  mov     r8, r14; struct CMPEG2Demultiplexer *
0x180015c3c  mov     qword ptr [rsp+78h+samDesired], rcx; int *
0x180015c41  mov     rcx, [r14+118h]
0x180015c48  mov     qword ptr [rsp+78h+dwOptions], rcx; struct CMPEG2PushClock *
0x180015c4d  mov     rcx, rax; this
0x180015c50  call    ??0CMPEG2TransportController@@QEAA@PEAUHKEY__@@PEAVCMPEG2Demultiplexer@@PEAVCMpeg2Stats@@PEAVCMPEG2PushClock@@PEAJ@Z; CMPEG2TransportController::CMPEG2TransportController(HKEY__ *,CMPEG2Demultiplexer *,CMpeg2Stats *,CMPEG2PushClock *,long *)
0x180015c55  mov     esi, [rbp+arg_0]
0x180015c58  mov     rdi, rax
0x180015c5b  test    rax, rax
0x180015c5e  jz      loc_180015CEC
0x180015c64  mov     rax, [rax]
0x180015c67  mov     rcx, rdi
0x180015c6a  test    esi, esi
0x180015c6c  js      short loc_180015CE0
0x180015c6e  mov     rax, [rax+30h]
0x180015c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c77  mov     esi, eax
0x180015c79  test    eax, eax
0x180015c7b  js      short loc_180015C8E
0x180015c7d  mov     rax, [rdi]
0x180015c80  mov     rcx, rdi
0x180015c83  mov     rax, [rax+38h]
0x180015c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c8c  mov     esi, eax
0x180015c8e  test    esi, esi
0x180015c90  js      short loc_180015CCC
0x180015c92  mov     rdx, [r14+118h]
0x180015c99  lea     rcx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\MPEG2Demultiplexer"...
0x180015ca0  mov     [r14+150h], rdi
0x180015ca7  mov     rax, [rdi+88h]
0x180015cae  mov     [rdx+270h], rax
0x180015cb5  mov     rbx, [rbx]
0x180015cb8  call    ?StatsEnabled@@YAHPEBG@Z; StatsEnabled(ushort const *)
0x180015cbd  mov     r8d, r13d; unsigned int
0x180015cc0  mov     edx, eax; int
0x180015cc2  mov     rcx, rbx; this
0x180015cc5  call    ?Initialize@CMpeg2Stats@@QEAAJHK@Z; CMpeg2Stats::Initialize(int,ulong)
0x180015cca  jmp     short loc_180015CF8
0x180015ccc  mov     rax, [rdi]
0x180015ccf  mov     edx, r13d
0x180015cd2  mov     rcx, rdi
0x180015cd5  mov     rax, [rax+28h]
0x180015cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cde  jmp     short loc_180015CF5
0x180015ce0  mov     rax, [rax+28h]
0x180015ce4  mov     edx, r13d
0x180015ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cec  test    esi, esi
0x180015cee  js      short loc_180015D13
0x180015cf0  mov     esi, 8007000Eh
0x180015cf5  mov     rdi, r12
0x180015cf8  test    esi, esi
0x180015cfa  jns     short loc_180015D4C
0x180015cfc  test    rdi, rdi
0x180015cff  jz      short loc_180015D13
0x180015d01  mov     rax, [rdi]
0x180015d04  mov     edx, r13d
0x180015d07  mov     rcx, rdi
0x180015d0a  mov     rax, [rax+28h]
0x180015d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d13  mov     rbx, [r14+118h]
0x180015d1a  test    rbx, rbx
0x180015d1d  jz      short loc_180015D34
0x180015d1f  mov     rcx, rbx; this
0x180015d22  call    ??1CMPEG2PushClock@@QEAA@XZ; CMPEG2PushClock::~CMPEG2PushClock(void)
0x180015d27  mov     edx, 2B8h; unsigned __int64
0x180015d2c  mov     rcx, rbx; void *
0x180015d2f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015d34  mov     rcx, [r15]; hKey
0x180015d37  mov     [r14+118h], r12
0x180015d3e  test    rcx, rcx
0x180015d41  jz      short loc_180015D4C
0x180015d43  call    cs:__imp_RegCloseKey
0x180015d49  mov     [r15], r12
0x180015d4c  mov     eax, esi
0x180015d4e  add     rsp, 78h
0x180015d52  pop     r15
0x180015d54  pop     r14
0x180015d56  pop     r13
0x180015d58  pop     r12
0x180015d5a  pop     rdi
0x180015d5b  pop     rsi
0x180015d5c  pop     rbx
0x180015d5d  pop     rbp
0x180015d5e  retn
```
