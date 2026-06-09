# FSCameraControlStates::CreateCameraControlStates(uchar *,ulong,IFSCameraControlStates * *)

- ea: `0x1800437cc`
- end: `0x18004396e`
- name: `?CreateCameraControlStates@FSCameraControlStates@@SAJPEAEKPEAPEAUIFSCameraControlStates@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(unsigned __int8 *, __int64, struct IFSCameraControlStates **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009f90`
- `0x180043650`

## callees

- `0x180002346`
- `0x18000261c`
- `0x180005f98`
- `0x1800060f8`
- `0x180006a98`
- `0x1800437cc`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180043844`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180043844`
- `MFPlat!MFGetSystemTime` at `0x1800438df`
- `MFPlat!MFGetSystemTime` at `0x1800438e9`
- `MFPlat!MFGetSystemTime` at `0x1800438df`
- `MFPlat!MFGetSystemTime` at `0x1800438e9`

## pseudocode

```c
__int64 __fastcall FSCameraControlStates::CreateCameraControlStates(
        unsigned __int8 *a1,
        __int64 a2,
        struct IFSCameraControlStates **a3)
{
  int v5; // edi
  int v6; // r8d
  __int64 v7; // rdx
  char *v8; // rax
  __int64 v9; // rbx
  __int64 v11; // [rsp+50h] [rbp+18h] BYREF

  v11 = 0;
  if ( a3 )
  {
    *a3 = 0;
    v8 = (char *)operator new(0x80u);
    v9 = (__int64)v8;
    if ( v8 )
    {
      memset_0(v8 + 8, 0, 0x78u);
      *(_QWORD *)v9 = &FSCameraControlStates::`vftable';
      InitializeCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
      *(_DWORD *)(v9 + 48) = 1;
      *(_QWORD *)(v9 + 56) = 0;
      *(_QWORD *)(v9 + 68) = 0;
      *(_DWORD *)(v9 + 64) = 0;
      v11 = v9;
      *(_OWORD *)(v9 + 80) = 0;
      *(_OWORD *)(v9 + 96) = 0;
      *(_QWORD *)(v9 + 112) = 0;
      *(_QWORD *)(v9 + 120) = 0;
      if ( a1 )
      {
        *(_OWORD *)(v9 + 80) = *(_OWORD *)a1;
        *(_OWORD *)(v9 + 96) = *((_OWORD *)a1 + 1);
        *(_QWORD *)(v9 + 112) = MFGetSystemTime();
        *(_QWORD *)(v9 + 120) = MFGetSystemTime();
        v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IFSCameraControlStates **))v9)(
               v9,
               &GUID_1e546f2d_6ef3_46b6_8407_e341e5aea0d1,
               a3);
        if ( v5 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v7 = 13;
          goto LABEL_15;
        }
      }
      else
      {
        v5 = -2147024809;
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            &WPP_1715f7faf12f35edaec9cafca56f2968_Traceguids,
            v9,
            -2147024809);
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v7 = 12;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v5 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 11;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v5 = -2147467261;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = (unsigned int)(v6 + 10);
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_1715f7faf12f35edaec9cafca56f2968_Traceguids, 0, v5);
    }
  }
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800437cc  mov     [rsp+arg_0], rbx
0x1800437d1  mov     [rsp+arg_8], rsi
0x1800437d6  push    rdi
0x1800437d7  sub     rsp, 30h
0x1800437db  mov     [rsp+38h+arg_10], 0
0x1800437e4  mov     rdi, r8
0x1800437e7  mov     rsi, rcx
0x1800437ea  test    r8, r8
0x1800437ed  jnz     short loc_18004380A
0x1800437ef  mov     edi, 80004003h
0x1800437f4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800437f9  cmp     al, 1
0x1800437fb  jb      loc_180043952
0x180043801  lea     edx, [r8+0Ah]
0x180043805  jmp     loc_180043934
0x18004380a  mov     ecx, 80h; Size
0x18004380f  mov     qword ptr [r8], 0
0x180043816  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004381b  mov     rbx, rax
0x18004381e  test    rax, rax
0x180043821  jz      loc_180043921
0x180043827  xor     edx, edx; Val
0x180043829  lea     rcx, [rax+8]; void *
0x18004382d  lea     r8d, [rdx+78h]; Size
0x180043831  call    memset_0
0x180043836  lea     rax, ??_7FSCameraControlStates@@6B@; const FSCameraControlStates::`vftable'
0x18004383d  lea     rcx, [rbx+8]; lpCriticalSection
0x180043841  mov     [rbx], rax
0x180043844  call    cs:__imp_InitializeCriticalSection
0x18004384a  mov     dword ptr [rbx+30h], 1
0x180043851  xorps   xmm0, xmm0
0x180043854  mov     qword ptr [rbx+38h], 0
0x18004385c  mov     qword ptr [rbx+44h], 0
0x180043864  mov     dword ptr [rbx+40h], 0
0x18004386b  mov     [rsp+38h+arg_10], rbx
0x180043870  movups  xmmword ptr [rbx+50h], xmm0
0x180043874  movups  xmmword ptr [rbx+60h], xmm0
0x180043878  mov     qword ptr [rbx+70h], 0
0x180043880  mov     qword ptr [rbx+78h], 0
0x180043888  test    rsi, rsi
0x18004388b  jnz     short loc_1800438D0
0x18004388d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180043892  mov     edi, 80070057h
0x180043897  cmp     al, 1
0x180043899  jb      short loc_1800438BC
0x18004389b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800438a2  lea     edx, [rsi+21h]
0x1800438a5  mov     r9, rbx
0x1800438a8  mov     [rsp+38h+var_18], edi
0x1800438ac  lea     r8, WPP_1715f7faf12f35edaec9cafca56f2968_Traceguids
0x1800438b3  mov     rcx, [rcx+10h]
0x1800438b7  call    WPP_SF_qD
0x1800438bc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800438c1  cmp     al, 1
0x1800438c3  jb      loc_180043952
0x1800438c9  mov     edx, 0Ch
0x1800438ce  jmp     short loc_180043934
0x1800438d0  movups  xmm0, xmmword ptr [rsi]
0x1800438d3  movups  xmmword ptr [rbx+50h], xmm0
0x1800438d7  movups  xmm1, xmmword ptr [rsi+10h]
0x1800438db  movups  xmmword ptr [rbx+60h], xmm1
0x1800438df  call    cs:__imp_MFGetSystemTime
0x1800438e5  mov     [rbx+70h], rax
0x1800438e9  call    cs:__imp_MFGetSystemTime
0x1800438ef  mov     [rbx+78h], rax
0x1800438f3  mov     rax, [rbx]
0x1800438f6  lea     rdx, _GUID_1e546f2d_6ef3_46b6_8407_e341e5aea0d1
0x1800438fd  mov     r8, rdi
0x180043900  mov     rcx, rbx
0x180043903  mov     rax, [rax]
0x180043906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004390b  mov     edi, eax
0x18004390d  test    eax, eax
0x18004390f  jns     short loc_180043952
0x180043911  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180043916  cmp     al, 1
0x180043918  jb      short loc_180043952
0x18004391a  mov     edx, 0Dh
0x18004391f  jmp     short loc_180043934
0x180043921  mov     edi, 8007000Eh
0x180043926  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004392b  cmp     al, 1
0x18004392d  jb      short loc_180043952
0x18004392f  mov     edx, 0Bh
0x180043934  mov     rcx, cs:WPP_GLOBAL_Control
0x18004393b  lea     r8, WPP_1715f7faf12f35edaec9cafca56f2968_Traceguids
0x180043942  xor     r9d, r9d
0x180043945  mov     [rsp+38h+var_18], edi
0x180043949  mov     rcx, [rcx+10h]
0x18004394d  call    WPP_SF_qD
0x180043952  lea     rcx, [rsp+38h+arg_10]
0x180043957  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18004395c  mov     rbx, [rsp+38h+arg_0]
0x180043961  mov     eax, edi
0x180043963  mov     rsi, [rsp+38h+arg_8]
0x180043968  add     rsp, 30h
0x18004396c  pop     rdi
0x18004396d  retn
```
