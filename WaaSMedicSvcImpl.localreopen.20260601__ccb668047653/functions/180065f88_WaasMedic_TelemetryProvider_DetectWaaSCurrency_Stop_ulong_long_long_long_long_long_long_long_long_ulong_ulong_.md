# WaasMedic::TelemetryProvider::DetectWaaSCurrency::Stop(ulong,long,long,long,long,long,long,long,long,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong)

- ea: `0x180065f88`
- end: `0x180066748`
- name: `?Stop@DetectWaaSCurrency@TelemetryProvider@WaasMedic@@QEAAXKJJJJJJJJKKKKKKKKKKKKK@Z`
- size: `1984`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::DetectWaaSCurrency *__hidden this, unsigned int, int, int, int, int, int, int, int, int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180065920`

## callees

- `0x180001718`
- `0x180003638`
- `0x1800050a0`
- `0x18000d04c`
- `0x180014ed4`
- `0x18001575c`
- `0x180065f88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180066010`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180066377`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180066010`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180066377`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066478`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066478`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::DetectWaaSCurrency::Stop(
        WaasMedic::TelemetryProvider::DetectWaaSCurrency *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        unsigned int a11,
        unsigned int a12,
        unsigned int a13,
        unsigned int a14,
        unsigned int a15,
        unsigned int a16,
        unsigned int a17,
        unsigned int a18,
        unsigned int a19,
        unsigned int a20,
        unsigned int a21,
        unsigned int a22,
        unsigned int a23)
{
  __int64 v23; // rdi
  int v28; // eax
  __int64 v29; // rdi
  RTL_SRWLOCK *v30; // rcx
  __int64 v31; // r9
  __int64 v32; // r8
  RTL_SRWLOCK *v33; // rcx
  __int64 v34; // rdi
  const unsigned __int16 *v35; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v37; // r8
  __int64 v38; // rax
  int v39; // eax
  unsigned int v40; // [rsp+160h] [rbp-80h] BYREF
  int v41; // [rsp+164h] [rbp-7Ch] BYREF
  int v42; // [rsp+168h] [rbp-78h] BYREF
  unsigned int v43; // [rsp+16Ch] [rbp-74h] BYREF
  unsigned int v44; // [rsp+170h] [rbp-70h] BYREF
  unsigned int v45; // [rsp+174h] [rbp-6Ch] BYREF
  unsigned int v46; // [rsp+178h] [rbp-68h] BYREF
  unsigned int v47; // [rsp+17Ch] [rbp-64h] BYREF
  unsigned int v48; // [rsp+180h] [rbp-60h] BYREF
  int v49; // [rsp+184h] [rbp-5Ch] BYREF
  int v50; // [rsp+188h] [rbp-58h] BYREF
  int v51; // [rsp+18Ch] [rbp-54h] BYREF
  int v52; // [rsp+190h] [rbp-50h] BYREF
  int v53; // [rsp+194h] [rbp-4Ch] BYREF
  int v54; // [rsp+198h] [rbp-48h] BYREF
  int v55; // [rsp+19Ch] [rbp-44h] BYREF
  int v56; // [rsp+1A0h] [rbp-40h] BYREF
  unsigned int v57; // [rsp+1A4h] [rbp-3Ch] BYREF
  unsigned int v58; // [rsp+1A8h] [rbp-38h] BYREF
  unsigned int v59; // [rsp+1ACh] [rbp-34h] BYREF
  unsigned int v60; // [rsp+1B0h] [rbp-30h] BYREF
  unsigned int v61; // [rsp+1B4h] [rbp-2Ch] BYREF
  unsigned int v62; // [rsp+1B8h] [rbp-28h] BYREF
  PSRWLOCK SRWLock; // [rsp+1C0h] [rbp-20h] BYREF
  PSRWLOCK v64; // [rsp+1C8h] [rbp-18h] BYREF
  unsigned int v65; // [rsp+1D0h] [rbp-10h] BYREF
  unsigned int v66; // [rsp+1D4h] [rbp-Ch] BYREF
  unsigned int v67; // [rsp+1D8h] [rbp-8h] BYREF
  unsigned int v68; // [rsp+1DCh] [rbp-4h] BYREF
  __int64 v69; // [rsp+1E0h] [rbp+0h] BYREF
  __int64 v70; // [rsp+1E8h] [rbp+8h] BYREF
  __int64 v71; // [rsp+1F0h] [rbp+10h] BYREF
  __int64 v72; // [rsp+1F8h] [rbp+18h] BYREF
  __int64 v73; // [rsp+200h] [rbp+20h] BYREF
  __int64 v74; // [rsp+208h] [rbp+28h] BYREF
  __int64 v75; // [rsp+210h] [rbp+30h] BYREF
  __int64 v76; // [rsp+218h] [rbp+38h] BYREF
  __int64 v77; // [rsp+220h] [rbp+40h] BYREF
  char *v78; // [rsp+228h] [rbp+48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v79; // [rsp+230h] [rbp+50h] BYREF
  PSRWLOCK *v80; // [rsp+250h] [rbp+70h]
  __int64 v81; // [rsp+258h] [rbp+78h]
  unsigned int *v82; // [rsp+260h] [rbp+80h]
  __int64 v83; // [rsp+268h] [rbp+88h]
  unsigned int *v84; // [rsp+270h] [rbp+90h]
  __int64 v85; // [rsp+278h] [rbp+98h]
  const unsigned __int16 *v86; // [rsp+280h] [rbp+A0h]
  int v87; // [rsp+288h] [rbp+A8h]
  int v88; // [rsp+28Ch] [rbp+ACh]
  unsigned int *v89; // [rsp+290h] [rbp+B0h]
  __int64 v90; // [rsp+298h] [rbp+B8h]
  unsigned int *v91; // [rsp+2A0h] [rbp+C0h]
  __int64 v92; // [rsp+2A8h] [rbp+C8h]
  unsigned int *v93; // [rsp+2B0h] [rbp+D0h]
  __int64 v94; // [rsp+2B8h] [rbp+D8h]
  int *v95; // [rsp+2C0h] [rbp+E0h]
  __int64 v96; // [rsp+2C8h] [rbp+E8h]
  int *v97; // [rsp+2D0h] [rbp+F0h]
  __int64 v98; // [rsp+2D8h] [rbp+F8h]
  int *v99; // [rsp+2E0h] [rbp+100h]
  __int64 v100; // [rsp+2E8h] [rbp+108h]
  int *v101; // [rsp+2F0h] [rbp+110h]
  __int64 v102; // [rsp+2F8h] [rbp+118h]
  int *v103; // [rsp+300h] [rbp+120h]
  __int64 v104; // [rsp+308h] [rbp+128h]
  int *v105; // [rsp+310h] [rbp+130h]
  __int64 v106; // [rsp+318h] [rbp+138h]
  int *v107; // [rsp+320h] [rbp+140h]
  __int64 v108; // [rsp+328h] [rbp+148h]
  int *v109; // [rsp+330h] [rbp+150h]
  __int64 v110; // [rsp+338h] [rbp+158h]
  int *v111; // [rsp+340h] [rbp+160h]
  __int64 v112; // [rsp+348h] [rbp+168h]
  int *v113; // [rsp+350h] [rbp+170h]
  __int64 v114; // [rsp+358h] [rbp+178h]
  unsigned int *v115; // [rsp+360h] [rbp+180h]
  __int64 v116; // [rsp+368h] [rbp+188h]
  unsigned int *v117; // [rsp+370h] [rbp+190h]
  __int64 v118; // [rsp+378h] [rbp+198h]
  unsigned int *v119; // [rsp+380h] [rbp+1A0h]
  __int64 v120; // [rsp+388h] [rbp+1A8h]
  unsigned int *v121; // [rsp+390h] [rbp+1B0h]
  __int64 v122; // [rsp+398h] [rbp+1B8h]
  unsigned int *v123; // [rsp+3A0h] [rbp+1C0h]
  __int64 v124; // [rsp+3A8h] [rbp+1C8h]
  unsigned int *v125; // [rsp+3B0h] [rbp+1D0h]
  __int64 v126; // [rsp+3B8h] [rbp+1D8h]
  unsigned int *v127; // [rsp+3C0h] [rbp+1E0h]
  __int64 v128; // [rsp+3C8h] [rbp+1E8h]
  unsigned int *v129; // [rsp+3D0h] [rbp+1F0h]
  __int64 v130; // [rsp+3D8h] [rbp+1F8h]
  PSRWLOCK *p_SRWLock; // [rsp+3E0h] [rbp+200h]
  __int64 v132; // [rsp+3E8h] [rbp+208h]

  v23 = *((_QWORD *)this + 34);
  v28 = *(_DWORD *)(v23 + 72);
  if ( v28 < 0 && (v29 = v23 + 80, v28 == *(_DWORD *)(v29 + 8)) && v29 )
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v30 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v30 )
      ReleaseSRWLockExclusive(v30);
    v31 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v31 > 5u
      && (*(_QWORD *)(v31 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v31 + 24) & 0x400000000000LL) == *(_QWORD *)(v31 + 24) )
    {
      v68 = a23;
      v65 = a22;
      v66 = a21;
      v67 = a20;
      v44 = a19;
      v45 = a18;
      v46 = a17;
      v32 = *((_QWORD *)this + 34);
      v47 = a16;
      v48 = a15;
      v49 = a14;
      v50 = a13;
      v51 = a12;
      v52 = a11;
      v53 = a10;
      v54 = a9;
      v55 = a8;
      v56 = a7;
      v41 = a6;
      v42 = a5;
      v78 = (char *)this + 336;
      v69 = *(_QWORD *)(v29 + 120);
      v70 = *(_QWORD *)(v29 + 112);
      v58 = *(_DWORD *)(v29 + 104);
      v71 = *(_QWORD *)(v29 + 96);
      v72 = *(_QWORD *)(v29 + 88);
      v59 = *(_DWORD *)(v29 + 80);
      v73 = *(_QWORD *)(v29 + 72);
      v60 = *(_DWORD *)(v29 + 32);
      v74 = *(_QWORD *)(v29 + 24);
      v61 = *(_DWORD *)v29;
      v75 = *(_QWORD *)(v29 + 128);
      v62 = *(_DWORD *)(v29 + 64);
      v76 = *(_QWORD *)(v29 + 56);
      LODWORD(SRWLock) = *(_DWORD *)(v29 + 8);
      v77 = 0x1000000;
      v64 = (PSRWLOCK)0x1000000;
      v43 = a4;
      v40 = a3;
      v57 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v31,
        (unsigned int)&dword_180094B44,
        v32 + 8,
        v31,
        (__int64)&v64,
        (__int64)&v77,
        (__int64)&SRWLock,
        (__int64)&v76,
        (__int64)&v62,
        (__int64)&v75,
        (__int64)&v61,
        (__int64)&v74,
        (__int64)&v60,
        (__int64)&v73,
        (__int64)&v59,
        (__int64)&v72,
        (__int64)&v71,
        (__int64)&v58,
        (__int64)&v70,
        (__int64)&v69,
        (__int64)&v78,
        (__int64)&v57,
        (__int64)&v40,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v56,
        (__int64)&v55,
        (__int64)&v54,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v51,
        (__int64)&v50,
        (__int64)&v49,
        (__int64)&v48,
        (__int64)&v47,
        (__int64)&v46,
        (__int64)&v45,
        (__int64)&v44,
        (__int64)&v67,
        (__int64)&v66,
        (__int64)&v65,
        (__int64)&v68);
    }
  }
  else
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v64);
    v33 = v64;
    **((_DWORD **)this + 34) = 2;
    if ( v33 )
      ReleaseSRWLockExclusive(v33);
    v34 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v34 > 5u
      && (*(_QWORD *)(v34 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v34 + 24) & 0x400000000000LL) == *(_QWORD *)(v34 + 24) )
    {
      LODWORD(SRWLock) = a23;
      v62 = a22;
      v61 = a21;
      v60 = a20;
      v59 = a19;
      v58 = a18;
      v57 = a17;
      v40 = a16;
      v43 = a15;
      v42 = a14;
      v41 = a13;
      v56 = a12;
      v55 = a11;
      v54 = a10;
      v53 = a9;
      v52 = a8;
      v51 = a7;
      v50 = a6;
      v48 = a4;
      v35 = (const unsigned __int16 *)((char *)this + 336);
      v49 = a5;
      v47 = a3;
      v46 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v37 = *((_QWORD *)this + 34);
      v45 = CurrentThreadId;
      v132 = 4;
      v130 = 4;
      v44 = *(_DWORD *)(v37 + 72);
      v64 = (PSRWLOCK)0x1000000;
      p_SRWLock = &SRWLock;
      v129 = &v62;
      v127 = &v61;
      v125 = &v60;
      v123 = &v59;
      v121 = &v58;
      v119 = &v57;
      v117 = &v40;
      v115 = &v43;
      v113 = &v42;
      v111 = &v41;
      v128 = 4;
      v126 = 4;
      v124 = 4;
      v122 = 4;
      v120 = 4;
      v118 = 4;
      v116 = 4;
      v114 = 4;
      v112 = 4;
      v109 = &v56;
      v107 = &v55;
      v105 = &v54;
      v103 = &v53;
      v101 = &v52;
      v99 = &v51;
      v97 = &v50;
      v95 = &v49;
      v93 = &v48;
      v91 = &v47;
      v89 = &v46;
      v110 = 4;
      v108 = 4;
      v106 = 4;
      v104 = 4;
      v102 = 4;
      v100 = 4;
      v98 = 4;
      v96 = 4;
      v94 = 4;
      v92 = 4;
      v90 = 4;
      if ( this == (WaasMedic::TelemetryProvider::DetectWaaSCurrency *)-336LL )
      {
        v35 = &qword_180072C40;
        v39 = 1;
      }
      else
      {
        v38 = -1;
        do
          ++v38;
        while ( *((_BYTE *)v35 + v38) );
        v39 = v38 + 1;
      }
      v87 = v39;
      v86 = v35;
      v84 = &v45;
      v88 = 0;
      v82 = &v44;
      v85 = 4;
      v80 = &v64;
      v83 = 4;
      v81 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        v34,
        (unsigned __int8 *)byte_180094ED1,
        (const GUID *)(v37 + 8),
        0,
        0x1Cu,
        &v79);
    }
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180065f88  mov     [rsp-8+arg_8], rbx
0x180065f8d  mov     [rsp-8+arg_10], rsi
0x180065f92  push    rbp
0x180065f93  push    rdi
0x180065f94  push    r12
0x180065f96  push    r14
0x180065f98  push    r15
0x180065f9a  lea     rbp, [rsp-220h]
0x180065fa2  sub     rsp, 400h
0x180065fa9  mov     rax, cs:__security_cookie
0x180065fb0  xor     rax, rsp
0x180065fb3  mov     [rbp+240h+var_30], rax
0x180065fba  mov     rdi, [rcx+110h]
0x180065fc1  xor     r12d, r12d
0x180065fc4  mov     esi, r9d
0x180065fc7  mov     r14d, r8d
0x180065fca  mov     r15d, edx
0x180065fcd  mov     rbx, rcx
0x180065fd0  mov     eax, [rdi+48h]
0x180065fd3  test    eax, eax
0x180065fd5  jns     loc_180066358
0x180065fdb  add     rdi, 50h ; 'P'
0x180065fdf  cmp     eax, [rdi+8]
0x180065fe2  jnz     loc_180066358
0x180065fe8  test    rdi, rdi
0x180065feb  jz      loc_180066358
0x180065ff1  lea     rdx, [rbp+240h+SRWLock]
0x180065ff5  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180065ffa  mov     rax, [rbx+110h]
0x180066001  mov     rcx, [rbp+240h+SRWLock]; SRWLock
0x180066005  mov     dword ptr [rax], 2
0x18006600b  test    rcx, rcx
0x18006600e  jz      short loc_180066016
0x180066010  call    cs:__imp_ReleaseSRWLockExclusive
0x180066016  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18006601b  mov     r9, [rax+8]
0x18006601f  mov     eax, [r9]
0x180066022  cmp     eax, 5
0x180066025  jbe     loc_180066715
0x18006602b  mov     rdx, [r9+18h]
0x18006602f  mov     rcx, 400000000000h
0x180066039  mov     rax, [r9+10h]
0x18006603d  test    rcx, rax
0x180066040  jz      loc_180066715
0x180066046  mov     rax, rdx
0x180066049  and     rax, rcx
0x18006604c  cmp     rax, rdx
0x18006604f  jnz     loc_180066715
0x180066055  mov     eax, [rbp+240h+arg_B0]
0x18006605b  mov     [rbp+240h+var_244], eax
0x18006605e  mov     eax, [rbp+240h+arg_A8]
0x180066064  mov     [rbp+240h+var_250], eax
0x180066067  mov     eax, [rbp+240h+arg_A0]
0x18006606d  mov     [rbp+240h+var_24C], eax
0x180066070  mov     eax, [rbp+240h+arg_98]
0x180066076  mov     [rbp+240h+var_248], eax
0x180066079  mov     eax, [rbp+240h+arg_90]
0x18006607f  mov     [rbp+240h+var_2B0], eax
0x180066082  mov     eax, [rbp+240h+arg_88]
0x180066088  mov     [rbp+240h+var_2AC], eax
0x18006608b  mov     eax, [rbp+240h+arg_80]
0x180066091  mov     [rbp+240h+var_2A8], eax
0x180066094  mov     eax, [rbp+240h+arg_78]
0x18006609a  mov     r8, [rbx+110h]
0x1800660a1  mov     [rbp+240h+var_2A4], eax
0x1800660a4  add     r8, 8
0x1800660a8  mov     eax, [rbp+240h+arg_70]
0x1800660ae  mov     [rbp+240h+var_2A0], eax
0x1800660b1  mov     eax, [rbp+240h+arg_68]
0x1800660b7  mov     [rbp+240h+var_29C], eax
0x1800660ba  mov     eax, [rbp+240h+arg_60]
0x1800660c0  mov     [rbp+240h+var_298], eax
0x1800660c3  mov     eax, [rbp+240h+arg_58]
0x1800660c9  mov     [rbp+240h+var_294], eax
0x1800660cc  mov     eax, [rbp+240h+arg_50]
0x1800660d2  mov     [rbp+240h+var_290], eax
0x1800660d5  mov     eax, [rbp+240h+arg_48]
0x1800660db  mov     [rbp+240h+var_28C], eax
0x1800660de  mov     eax, [rbp+240h+arg_40]
0x1800660e4  mov     [rbp+240h+var_288], eax
0x1800660e7  mov     eax, [rbp+240h+arg_38]
0x1800660ed  mov     [rbp+240h+var_284], eax
0x1800660f0  mov     eax, [rbp+240h+arg_30]
0x1800660f6  mov     [rbp+240h+var_280], eax
0x1800660f9  mov     eax, [rbp+240h+arg_28]
0x1800660ff  mov     [rbp+240h+var_2BC], eax
0x180066102  mov     eax, [rbp+240h+arg_20]
0x180066108  mov     [rbp+240h+var_2B8], eax
0x18006610b  lea     rax, [rbx+150h]
0x180066112  mov     [rbp+240h+var_1F8], rax
0x180066116  mov     rax, [rdi+78h]
0x18006611a  mov     [rbp+240h+var_240], rax
0x18006611e  mov     rax, [rdi+70h]
0x180066122  mov     [rbp+240h+var_238], rax
0x180066126  mov     eax, [rdi+68h]
0x180066129  mov     [rbp+240h+var_278], eax
0x18006612c  mov     rax, [rdi+60h]
0x180066130  mov     [rbp+240h+var_230], rax
0x180066134  mov     rax, [rdi+58h]
0x180066138  mov     [rbp+240h+var_228], rax
0x18006613c  mov     eax, [rdi+50h]
0x18006613f  mov     [rbp+240h+var_274], eax
0x180066142  mov     rax, [rdi+48h]
0x180066146  mov     [rbp+240h+var_220], rax
0x18006614a  mov     eax, [rdi+20h]
0x18006614d  mov     [rbp+240h+var_270], eax
0x180066150  mov     rax, [rdi+18h]
0x180066154  mov     [rbp+240h+var_218], rax
0x180066158  mov     eax, [rdi]
0x18006615a  mov     [rbp+240h+var_26C], eax
0x18006615d  mov     rax, [rdi+80h]
0x180066164  mov     [rbp+240h+var_210], rax
0x180066168  mov     eax, [rdi+40h]
0x18006616b  mov     [rbp+240h+var_268], eax
0x18006616e  mov     rax, [rdi+38h]
0x180066172  mov     [rbp+240h+var_208], rax
0x180066176  mov     eax, [rdi+8]
0x180066179  mov     dword ptr [rbp+240h+SRWLock], eax
0x18006617c  mov     eax, 1000000h
0x180066181  mov     [rbp+240h+var_200], rax
0x180066185  mov     [rbp+240h+var_258], rax
0x180066189  lea     rax, [rbp+240h+var_244]
0x18006618d  mov     [rsp+420h+var_2D0], rax
0x180066195  lea     rax, [rbp+240h+var_250]
0x180066199  mov     [rsp+420h+var_2D8], rax
0x1800661a1  lea     rax, [rbp+240h+var_24C]
0x1800661a5  mov     [rbp+240h+var_2B4], esi
0x1800661a8  mov     [rbp+240h+var_2C0], r14d
0x1800661ac  mov     [rbp+240h+var_27C], r15d
0x1800661b0  mov     [rsp+420h+var_2E0], rax
0x1800661b8  lea     rdx, dword_180094B44
0x1800661bf  lea     rax, [rbp+240h+var_248]
0x1800661c3  mov     rcx, r9
0x1800661c6  mov     [rsp+420h+var_2E8], rax
0x1800661ce  lea     rax, [rbp+240h+var_2B0]
0x1800661d2  mov     [rsp+420h+var_2F0], rax
0x1800661da  lea     rax, [rbp+240h+var_2AC]
0x1800661de  mov     [rsp+420h+var_2F8], rax
0x1800661e6  lea     rax, [rbp+240h+var_2A8]
0x1800661ea  mov     [rsp+420h+var_300], rax
0x1800661f2  lea     rax, [rbp+240h+var_2A4]
0x1800661f6  mov     [rsp+420h+var_308], rax
0x1800661fe  lea     rax, [rbp+240h+var_2A0]
0x180066202  mov     [rsp+420h+var_310], rax
0x18006620a  lea     rax, [rbp+240h+var_29C]
0x18006620e  mov     [rsp+420h+var_318], rax
0x180066216  lea     rax, [rbp+240h+var_298]
0x18006621a  mov     [rsp+420h+var_320], rax
0x180066222  lea     rax, [rbp+240h+var_294]
0x180066226  mov     [rsp+420h+var_328], rax
0x18006622e  lea     rax, [rbp+240h+var_290]
0x180066232  mov     [rsp+420h+var_330], rax
0x18006623a  lea     rax, [rbp+240h+var_28C]
0x18006623e  mov     [rsp+420h+var_338], rax
0x180066246  lea     rax, [rbp+240h+var_288]
0x18006624a  mov     [rsp+420h+var_340], rax
0x180066252  lea     rax, [rbp+240h+var_284]
0x180066256  mov     [rsp+420h+var_348], rax
0x18006625e  lea     rax, [rbp+240h+var_280]
0x180066262  mov     [rsp+420h+var_350], rax
0x18006626a  lea     rax, [rbp+240h+var_2BC]
0x18006626e  mov     [rsp+420h+var_358], rax
0x180066276  lea     rax, [rbp+240h+var_2B8]
0x18006627a  mov     [rsp+420h+var_360], rax
0x180066282  lea     rax, [rbp+240h+var_2B4]
0x180066286  mov     [rsp+420h+var_368], rax
0x18006628e  lea     rax, [rbp+240h+var_2C0]
0x180066292  mov     [rsp+420h+var_370], rax
0x18006629a  lea     rax, [rbp+240h+var_27C]
0x18006629e  mov     [rsp+420h+var_378], rax
0x1800662a6  lea     rax, [rbp+240h+var_1F8]
0x1800662aa  mov     [rsp+420h+var_380], rax
0x1800662b2  lea     rax, [rbp+240h+var_240]
0x1800662b6  mov     [rsp+420h+var_388], rax
0x1800662be  lea     rax, [rbp+240h+var_238]
0x1800662c2  mov     [rsp+420h+var_390], rax
0x1800662ca  lea     rax, [rbp+240h+var_278]
0x1800662ce  mov     [rsp+420h+var_398], rax
0x1800662d6  lea     rax, [rbp+240h+var_230]
0x1800662da  mov     [rsp+420h+var_3A0], rax
0x1800662e2  lea     rax, [rbp+240h+var_228]
0x1800662e6  mov     [rsp+420h+var_3A8], rax
0x1800662eb  lea     rax, [rbp+240h+var_274]
0x1800662ef  mov     [rsp+420h+var_3B0], rax
0x1800662f4  lea     rax, [rbp+240h+var_220]
0x1800662f8  mov     [rsp+420h+var_3B8], rax
0x1800662fd  lea     rax, [rbp+240h+var_270]
0x180066301  mov     [rsp+420h+var_3C0], rax
0x180066306  lea     rax, [rbp+240h+var_218]
0x18006630a  mov     [rsp+420h+var_3C8], rax
0x18006630f  lea     rax, [rbp+240h+var_26C]
0x180066313  mov     [rsp+420h+var_3D0], rax
0x180066318  lea     rax, [rbp+240h+var_210]
0x18006631c  mov     [rsp+420h+var_3D8], rax
0x180066321  lea     rax, [rbp+240h+var_268]
0x180066325  mov     [rsp+420h+var_3E0], rax
0x18006632a  lea     rax, [rbp+240h+var_208]
0x18006632e  mov     [rsp+420h+var_3E8], rax
0x180066333  lea     rax, [rbp+240h+SRWLock]
0x180066337  mov     [rsp+420h+var_3F0], rax
0x18006633c  lea     rax, [rbp+240h+var_200]
0x180066340  mov     [rsp+420h+var_3F8], rax
0x180066345  lea     rax, [rbp+240h+var_258]
0x180066349  mov     [rsp+420h+var_400], rax
0x18006634e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U3@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645654444444444444444444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180066353  jmp     loc_180066715
0x180066358  lea     rdx, [rbp+240h+var_258]
0x18006635c  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180066361  mov     rax, [rbx+110h]
0x180066368  mov     rcx, [rbp+240h+var_258]; SRWLock
0x18006636c  mov     dword ptr [rax], 2
0x180066372  test    rcx, rcx
0x180066375  jz      short loc_18006637D
0x180066377  call    cs:__imp_ReleaseSRWLockExclusive
0x18006637d  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x180066382  mov     rdi, [rax+8]
0x180066386  mov     eax, [rdi]
0x180066388  cmp     eax, 5
0x18006638b  jbe     loc_180066715
0x180066391  mov     rdx, [rdi+18h]
0x180066395  mov     rcx, 400000000000h
0x18006639f  mov     rax, [rdi+10h]
0x1800663a3  test    rcx, rax
0x1800663a6  jz      loc_180066715
0x1800663ac  mov     rax, rdx
0x1800663af  and     rax, rcx
0x1800663b2  cmp     rax, rdx
0x1800663b5  jnz     loc_180066715
0x1800663bb  mov     eax, [rbp+240h+arg_B0]
0x1800663c1  mov     dword ptr [rbp+240h+SRWLock], eax
0x1800663c4  mov     eax, [rbp+240h+arg_A8]
0x1800663ca  mov     [rbp+240h+var_268], eax
0x1800663cd  mov     eax, [rbp+240h+arg_A0]
0x1800663d3  mov     [rbp+240h+var_26C], eax
0x1800663d6  mov     eax, [rbp+240h+arg_98]
0x1800663dc  mov     [rbp+240h+var_270], eax
0x1800663df  mov     eax, [rbp+240h+arg_90]
0x1800663e5  mov     [rbp+240h+var_274], eax
0x1800663e8  mov     eax, [rbp+240h+arg_88]
0x1800663ee  mov     [rbp+240h+var_278], eax
0x1800663f1  mov     eax, [rbp+240h+arg_80]
0x1800663f7  mov     [rbp+240h+var_27C], eax
0x1800663fa  mov     eax, [rbp+240h+arg_78]
0x180066400  mov     [rbp+240h+var_2C0], eax
0x180066403  mov     eax, [rbp+240h+arg_70]
0x180066409  mov     [rbp+240h+var_2B4], eax
0x18006640c  mov     eax, [rbp+240h+arg_68]
0x180066412  mov     [rbp+240h+var_2B8], eax
0x180066415  mov     eax, [rbp+240h+arg_60]
0x18006641b  mov     [rbp+240h+var_2BC], eax
0x18006641e  mov     eax, [rbp+240h+arg_58]
0x180066424  mov     [rbp+240h+var_280], eax
0x180066427  mov     eax, [rbp+240h+arg_50]
0x18006642d  mov     [rbp+240h+var_284], eax
0x180066430  mov     eax, [rbp+240h+arg_48]
0x180066436  mov     [rbp+240h+var_288], eax
0x180066439  mov     eax, [rbp+240h+arg_40]
0x18006643f  mov     [rbp+240h+var_28C], eax
0x180066442  mov     eax, [rbp+240h+arg_38]
0x180066448  mov     [rbp+240h+var_290], eax
0x18006644b  mov     eax, [rbp+240h+arg_30]
0x180066451  mov     [rbp+240h+var_294], eax
0x180066454  mov     eax, [rbp+240h+arg_28]
0x18006645a  mov     [rbp+240h+var_298], eax
0x18006645d  mov     eax, [rbp+240h+arg_20]
0x180066463  mov     [rbp+240h+var_2A0], esi
0x180066466  lea     rsi, [rbx+150h]
0x18006646d  mov     [rbp+240h+var_29C], eax
0x180066470  mov     [rbp+240h+var_2A4], r14d
0x180066474  mov     [rbp+240h+var_2A8], r15d
0x180066478  call    cs:__imp_GetCurrentThreadId
0x18006647e  mov     r8, [rbx+110h]
0x180066485  mov     [rbp+240h+var_2AC], eax
0x180066488  mov     [rbp+240h+var_38], 4
0x180066493  mov     [rbp+240h+var_48], 4
0x18006649e  mov     eax, [r8+48h]
0x1800664a2  mov     [rbp+240h+var_2B0], eax
0x1800664a5  mov     eax, 1000000h
0x1800664aa  mov     [rbp+240h+var_258], rax
0x1800664ae  lea     rax, [rbp+240h+SRWLock]
0x1800664b2  mov     [rbp+240h+var_40], rax
0x1800664b9  lea     rax, [rbp+240h+var_268]
0x1800664bd  mov     [rbp+240h+var_50], rax
0x1800664c4  lea     rax, [rbp+240h+var_26C]
0x1800664c8  mov     [rbp+240h+var_60], rax
0x1800664cf  lea     rax, [rbp+240h+var_270]
0x1800664d3  mov     [rbp+240h+var_70], rax
0x1800664da  lea     rax, [rbp+240h+var_274]
0x1800664de  mov     [rbp+240h+var_80], rax
0x1800664e5  lea     rax, [rbp+240h+var_278]
0x1800664e9  mov     [rbp+240h+var_90], rax
0x1800664f0  lea     rax, [rbp+240h+var_27C]
0x1800664f4  mov     [rbp+240h+var_A0], rax
0x1800664fb  lea     rax, [rbp+240h+var_2C0]
0x1800664ff  mov     [rbp+240h+var_B0], rax
0x180066506  lea     rax, [rbp+240h+var_2B4]
0x18006650a  mov     [rbp+240h+var_C0], rax
0x180066511  lea     rax, [rbp+240h+var_2B8]
0x180066515  mov     [rbp+240h+var_D0], rax
0x18006651c  lea     rax, [rbp+240h+var_2BC]
  ... truncated ...
```
