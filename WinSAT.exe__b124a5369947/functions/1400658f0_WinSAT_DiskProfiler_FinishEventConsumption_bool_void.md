# WinSAT::DiskProfiler::FinishEventConsumption(bool,void *)

- ea: `0x1400658f0`
- end: `0x140065e17`
- name: `?FinishEventConsumption@DiskProfiler@WinSAT@@MEAA_N_NPEAX@Z`
- size: `1319`
- prototype: `bool __fastcall(WinSAT::DiskProfiler *__hidden this, bool, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140005f4c`
- `0x140007674`
- `0x140016d04`
- `0x14003ec14`
- `0x1400633d0`
- `0x14006358c`
- `0x140063d14`
- `0x1400658f0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140065abf`
- `KERNEL32!CloseHandle` at `0x140065b22`
- `KERNEL32!CloseHandle` at `0x140065abf`
- `KERNEL32!CloseHandle` at `0x140065b22`
- `KERNEL32!OpenThread` at `0x140065aa1`
- `KERNEL32!OpenThread` at `0x140065aa1`
- `KERNEL32!OpenProcess` at `0x140065ad4`
- `KERNEL32!OpenProcess` at `0x140065ad4`
- `KERNEL32!K32GetProcessImageFileNameW` at `0x140065af5`
- `KERNEL32!K32GetProcessImageFileNameW` at `0x140065af5`
- `KERNEL32!GetProcessIdOfThread` at `0x140065ab3`
- `KERNEL32!GetProcessIdOfThread` at `0x140065ab3`
- `KERNEL32!SetLastError` at `0x140065b46`
- `KERNEL32!SetLastError` at `0x140065df8`
- `KERNEL32!SetLastError` at `0x140065b46`
- `KERNEL32!SetLastError` at `0x140065df8`

## string_xrefs

- `0x14006597d`: `No Registry or pbip, using the default value of permitted BG Interference`
- `0x140065965`: `Using the Registry value for permitted BG Interference`
- `0x140065c1e`: `CCC - Normalized the high IO values - SEQ Heuristic`
- `0x140065b7e`: `CCC - Skipping the heuristic for random assessment`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
char __fastcall WinSAT::DiskProfiler::FinishEventConsumption(WinSAT::DiskProfiler *this, char a2, int *a3)
{
  DWORD v5; // ecx
  char v6; // r13
  unsigned int v7; // r15d
  int v8; // r12d
  unsigned __int64 v9; // r14
  int v10; // eax
  int v11; // r9d
  unsigned int v12; // edx
  int v13; // ecx
  unsigned int v14; // eax
  unsigned int v15; // eax
  DWORD v16; // r15d
  DWORD *i; // rbx
  DWORD v18; // r14d
  HANDLE v19; // rax
  void *v20; // r15
  DWORD ProcessIdOfThread; // r12d
  HANDLE v22; // rax
  void *v23; // r15
  __int64 v25; // rdx
  unsigned __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // r9
  unsigned __int64 v31; // rdx
  __int64 v32; // r9
  __int64 v33; // rax
  __int64 v34; // rcx
  double v35; // xmm1_8
  __int64 v36; // rcx
  double v37; // xmm0_8
  __int64 v38; // rax
  __int64 v39; // rcx
  double v40; // xmm0_8
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rcx
  double v44; // xmm0_8
  __int64 v45; // rax
  double v46; // xmm0_8
  double v47; // xmm1_8
  __int64 v48; // rcx
  unsigned int v49; // [rsp+28h] [rbp-50h]
  __int64 v50; // [rsp+30h] [rbp-48h] BYREF
  __int64 v51; // [rsp+38h] [rbp-40h]
  char v52; // [rsp+88h] [rbp+10h]
  __int64 v53; // [rsp+98h] [rbp+20h] BYREF

  if ( a2 )
    return 0;
  if ( !a3 )
  {
    v5 = 87;
LABEL_69:
    SetLastError(v5);
    return 0;
  }
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  if ( *((_DWORD *)this + 109) || (*((_DWORD *)this + 51) & 0x1000000) == 0 )
  {
    if ( (*((_DWORD *)this + 51) & 0x10000000) != 0 )
    {
LABEL_50:
      if ( a3[28] )
      {
        v35 = (double)a3[28];
        *((double *)a3 + 11) = *((double *)a3 + 11) / v35;
        v36 = *((_QWORD *)a3 + 6);
        if ( v36 < 0 )
        {
          v38 = *((_QWORD *)a3 + 6) & 1LL | ((unsigned __int64)v36 >> 1);
          v37 = (double)(int)v38 + (double)(int)v38;
        }
        else
        {
          v37 = (double)(int)v36;
        }
        *((double *)a3 + 12) = v37 / v35;
        v39 = *((_QWORD *)a3 + 5);
        if ( v39 < 0 )
        {
          v41 = *((_QWORD *)a3 + 5) & 1LL | ((unsigned __int64)v39 >> 1);
          v40 = (double)(int)v41 + (double)(int)v41;
        }
        else
        {
          v40 = (double)(int)v39;
        }
        *((double *)a3 + 13) = v40 / v35;
      }
      else
      {
        v6 = 1;
      }
      v42 = *((_QWORD *)a3 + 5);
      if ( v42 )
      {
        v43 = *((_QWORD *)a3 + 2);
        if ( v43 < 0 )
        {
          v45 = *((_QWORD *)a3 + 2) & 1LL | ((unsigned __int64)v43 >> 1);
          v44 = (double)(int)v45 + (double)(int)v45;
        }
        else
        {
          v44 = (double)(int)v43;
        }
        v46 = v44 * 0.00000095367431640625;
        if ( v42 < 0 )
        {
          v48 = *((_QWORD *)a3 + 5) & 1LL | ((unsigned __int64)v42 >> 1);
          v47 = (double)(int)v48 + (double)(int)v48;
        }
        else
        {
          v47 = (double)(int)v42;
        }
        *((double *)a3 + 10) = v46 / (v47 / 1000000.0);
        if ( !v6 )
          return 1;
      }
      v5 = 13;
      goto LABEL_69;
    }
    std::vector<WinSAT::StorageDevice::IOInformation>::vector<WinSAT::StorageDevice::IOInformation>(&v50, a3 + 38);
    LOBYTE(v32) = v52;
    std::_Sort<WinSAT::StorageDevice::IOInformation *,__int64,WinSAT::StorageDevice::IOInformation::SDescendingSrvTime>(
      v50,
      v51,
      0xCCCCCCCCCCCCCCCDuLL * ((v51 - v50) >> 3),
      v32);
    v26 = (unsigned int)a3[35];
    v33 = v50;
    if ( 0xCCCCCCCCCCCCCCCDuLL * ((v51 - v50) >> 3) >= v26 )
    {
      v27 = 0;
      if ( (_DWORD)v26 )
      {
        v34 = *((_QWORD *)a3 + 2);
        v25 = *((_QWORD *)a3 + 5);
        do
        {
          v34 -= *(_QWORD *)(v33 + 24);
          *((_QWORD *)a3 + 2) = v34;
          v25 -= *(_QWORD *)(v33 + 8);
          *((_QWORD *)a3 + 5) = v25;
          v33 += 40;
          v27 = (unsigned int)(v27 + 1);
        }
        while ( (unsigned int)v27 < (unsigned int)v26 );
      }
    }
LABEL_49:
    std::vector<_D3DRECT *>::~vector<_D3DRECT *>(&v50, v25, v26, v27);
    goto LABEL_50;
  }
  if ( !*((_DWORD *)this + 108) )
  {
    v10 = *((_DWORD *)this + 110);
    if ( v10 )
    {
      *((_DWORD *)this + 108) = v10;
      Log_Text_F("base\\winsat\\storage\\diskprof.cpp", 3827, "Using the Registry value for permitted BG Interference");
    }
    else
    {
      *((_DWORD *)this + 108) = 100;
      Log_Text_F(
        "base\\winsat\\storage\\diskprof.cpp",
        3830,
        "No Registry or pbip, using the default value of permitted BG Interference");
    }
  }
  Log_Text_F(
    "base\\winsat\\storage\\diskprof.cpp",
    3833,
    "Permitted background Interference in percentage = %d",
    *((_DWORD *)this + 108));
  v11 = *((_DWORD *)this + 55);
  v12 = *((_DWORD *)this + 108) * v11 / 0x64u;
  v13 = *((_DWORD *)this + 51);
  if ( (v13 & 2) != 0 )
  {
    v14 = a3[35];
    if ( *((_DWORD *)this + 113) < v14 )
      *((_DWORD *)this + 113) = v14;
  }
  if ( (v13 & 1) != 0 )
  {
    v15 = a3[35];
    if ( *((_DWORD *)this + 112) < v15 )
      *((_DWORD *)this + 112) = v15;
  }
  v49 = a3[35];
  if ( v49 <= v12 )
  {
    Log_Text_F(
      "base\\winsat\\storage\\diskprof.cpp",
      3891,
      "info: WinSAT IOs = %u, Allowed interference = %u Actual Interference = %u ",
      v11,
      v12,
      v49);
    std::vector<WinSAT::StorageDevice::IOInformation>::vector<WinSAT::StorageDevice::IOInformation>(&v50, a3 + 38);
    if ( (*((_BYTE *)this + 204) & 2) != 0 )
      Log_Text_F("base\\winsat\\storage\\diskprof.cpp", 3898, "CCC - Skipping the heuristic for random assessment");
    if ( (*((_BYTE *)this + 204) & 1) != 0 )
    {
      v28 = v50;
      v29 = v50;
      v30 = v51;
      while ( v29 != v51 )
      {
        v9 += *(_QWORD *)(v29 + 8);
        ++v7;
        v29 += 40;
      }
      if ( v7 )
        v9 /= v7;
      v31 = (unsigned int)a3[35];
      if ( 0xCCCCCCCCCCCCCCCDuLL * ((v51 - v50) >> 3) >= v31 && (_DWORD)v31 )
      {
        do
        {
          if ( v28 == v30 )
            break;
          if ( *(_QWORD *)(v28 + 8) > v9 )
          {
            *((_QWORD *)a3 + 5) += v9 - *(_QWORD *)(v28 + 8);
            ++v8;
          }
          v28 += 40;
        }
        while ( v8 != (_DWORD)v31 );
      }
      Log_Text_F(
        "base\\winsat\\storage\\diskprof.cpp",
        3922,
        "CCC - Normalized the high IO values - SEQ Heuristic",
        v30);
    }
    goto LABEL_49;
  }
  Log_Text_F(
    "base\\winsat\\storage\\diskprof.cpp",
    3846,
    "CANNOT PROCEED - WinSAT IOs = %u, Allowed interference = %u Actual Interference = %u ",
    v11,
    v12,
    v49);
  if ( *((_BYTE *)this + 444) )
  {
    v16 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v53,
      260);
    std::_Sort<unsigned long *,__int64>(
      *((_QWORD *)this + 57),
      *((_QWORD *)this + 58),
      (__int64)(*((_QWORD *)this + 58) - *((_QWORD *)this + 57)) >> 2);
    for ( i = (DWORD *)*((_QWORD *)this + 57); i != *((DWORD **)this + 58); ++i )
    {
      v18 = *i;
      if ( *i != v16 )
      {
        v19 = OpenThread(0x40u, 0, v18);
        v20 = v19;
        if ( v19 != (HANDLE)-1LL )
        {
          ProcessIdOfThread = GetProcessIdOfThread(v19);
          CloseHandle(v20);
          if ( ProcessIdOfThread )
          {
            v22 = OpenProcess(0x400u, 0, ProcessIdOfThread);
            v23 = v22;
            if ( v22 != (HANDLE)-1LL )
            {
              K32GetProcessImageFileNameW(v22, *(LPWSTR *)(v53 + 24), 0x104u);
              Log_Text_F(
                "base\\winsat\\storage\\diskprof.cpp",
                3876,
                "Interfering Process Name %S",
                *(const wchar_t **)(v53 + 24));
              CloseHandle(v23);
            }
          }
        }
        v16 = v18;
      }
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v53);
  }
  SetLastError(0x201000Bu);
  return 0;
}

```

## disassembly

```asm
0x1400658f0  mov     [rsp+arg_0], rbx
0x1400658f5  mov     [rsp+arg_10], r8
0x1400658fa  push    rdi
0x1400658fb  push    r12
0x1400658fd  push    r13
0x1400658ff  push    r14
0x140065901  push    r15
0x140065903  sub     rsp, 50h
0x140065907  mov     rbx, r8
0x14006590a  mov     rdi, rcx
0x14006590d  test    dl, dl
0x14006590f  jnz     loc_140065DFE
0x140065915  test    rbx, rbx
0x140065918  jnz     short loc_140065923
0x14006591a  lea     ecx, [r8+57h]
0x14006591e  jmp     loc_140065DF8
0x140065923  xor     r13b, r13b
0x140065926  xor     r15d, r15d
0x140065929  xor     r12d, r12d
0x14006592c  xor     r14d, r14d
0x14006592f  cmp     [rcx+1B4h], r14d
0x140065936  jnz     loc_140065C3B
0x14006593c  test    dword ptr [rcx+0CCh], 1000000h
0x140065946  jz      loc_140065C3B
0x14006594c  cmp     [rcx+1B0h], r14d
0x140065953  jnz     short loc_140065995
0x140065955  mov     eax, [rcx+1B8h]
0x14006595b  test    eax, eax
0x14006595d  jz      short loc_140065973
0x14006595f  mov     [rcx+1B0h], eax
0x140065965  lea     r8, aUsingTheRegist; "Using the Registry value for permitted "...
0x14006596c  mov     edx, 0EF3h
0x140065971  jmp     short loc_140065989
0x140065973  mov     dword ptr [rcx+1B0h], 64h ; 'd'
0x14006597d  lea     r8, aNoRegistryOrPb; "No Registry or pbip, using the default "...
0x140065984  mov     edx, 0EF6h
0x140065989  lea     rcx, aBaseWinsatStor; "base\\winsat\\storage\\diskprof.cpp"
0x140065990  call    Log_Text_F
0x140065995  mov     r9d, [rdi+1B0h]
0x14006599c  lea     r8, aPermittedBackg; "Permitted background Interference in pe"...
0x1400659a3  mov     edx, 0EF9h
0x1400659a8  lea     rcx, aBaseWinsatStor; "base\\winsat\\storage\\diskprof.cpp"
0x1400659af  call    Log_Text_F
0x1400659b4  mov     r9d, [rdi+0DCh]
0x1400659bb  mov     ecx, r9d
0x1400659be  imul    ecx, [rdi+1B0h]
0x1400659c5  mov     eax, 51EB851Fh
0x1400659ca  mul     ecx
0x1400659cc  shr     edx, 5
0x1400659cf  mov     ecx, [rdi+0CCh]
0x1400659d5  test    cl, 2
0x1400659d8  jz      short loc_1400659EE
0x1400659da  mov     eax, [rbx+8Ch]
0x1400659e0  cmp     [rdi+1C4h], eax
0x1400659e6  jnb     short loc_1400659EE
0x1400659e8  mov     [rdi+1C4h], eax
0x1400659ee  test    cl, 1
0x1400659f1  jz      short loc_140065A07
0x1400659f3  mov     eax, [rbx+8Ch]
0x1400659f9  cmp     [rdi+1C0h], eax
0x1400659ff  jnb     short loc_140065A07
0x140065a01  mov     [rdi+1C0h], eax
0x140065a07  mov     eax, [rbx+8Ch]
0x140065a0d  mov     [rsp+78h+var_50], eax
0x140065a11  lea     rcx, aBaseWinsatStor; "base\\winsat\\storage\\diskprof.cpp"
0x140065a18  mov     [rsp+78h+var_58], edx
0x140065a1c  cmp     eax, edx
0x140065a1e  jbe     loc_140065B53
0x140065a24  lea     r8, aCannotProceedW; "CANNOT PROCEED - WinSAT IOs = %u, Allow"...
0x140065a2b  mov     edx, 0F06h
0x140065a30  call    Log_Text_F
0x140065a35  cmp     byte ptr [rdi+1BCh], 0
0x140065a3c  jz      loc_140065B41
0x140065a42  xor     r15d, r15d
0x140065a45  mov     r13d, 104h
0x140065a4b  mov     edx, r13d
0x140065a4e  lea     rcx, [rsp+78h+arg_18]
0x140065a56  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x140065a5b  nop
0x140065a5c  mov     rdx, [rdi+1D0h]
0x140065a63  mov     rcx, [rdi+1C8h]
0x140065a6a  mov     r8, rdx
0x140065a6d  sub     r8, rcx
0x140065a70  sar     r8, 2
0x140065a74  call    ??$_Sort@PEAK_J@std@@YAXPEAK0_J@Z; std::_Sort<ulong *,__int64>(ulong *,ulong *,__int64)
0x140065a79  mov     rbx, [rdi+1C8h]
0x140065a80  cmp     rbx, [rdi+1D0h]
0x140065a87  jz      loc_140065B34
0x140065a8d  mov     r14d, [rbx]
0x140065a90  cmp     r14d, r15d
0x140065a93  jz      loc_140065B2B
0x140065a99  mov     r8d, r14d; dwThreadId
0x140065a9c  xor     edx, edx; bInheritHandle
0x140065a9e  lea     ecx, [rdx+40h]; dwDesiredAccess
0x140065aa1  call    cs:__imp_OpenThread
0x140065aa7  mov     r15, rax
0x140065aaa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140065aae  jz      short loc_140065B28
0x140065ab0  mov     rcx, rax; Thread
0x140065ab3  call    cs:__imp_GetProcessIdOfThread
0x140065ab9  mov     r12d, eax
0x140065abc  mov     rcx, r15; hObject
0x140065abf  call    cs:__imp_CloseHandle
0x140065ac5  test    r12d, r12d
0x140065ac8  jz      short loc_140065B28
0x140065aca  mov     r8d, r12d; dwProcessId
0x140065acd  xor     edx, edx; bInheritHandle
0x140065acf  mov     ecx, 400h; dwDesiredAccess
0x140065ad4  call    cs:__imp_OpenProcess
0x140065ada  mov     r15, rax
0x140065add  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140065ae1  jz      short loc_140065B28
0x140065ae3  mov     r8d, r13d; nSize
0x140065ae6  mov     rdx, [rsp+78h+arg_18]
0x140065aee  mov     rdx, [rdx+18h]; lpImageFileName
0x140065af2  mov     rcx, rax; hProcess
0x140065af5  call    cs:__imp_K32GetProcessImageFileNameW
0x140065afb  mov     r9, [rsp+78h+arg_18]
0x140065b03  mov     r9, [r9+18h]
0x140065b07  lea     r8, aInterferingPro; "Interfering Process Name %S"
0x140065b0e  mov     edx, 0F24h
0x140065b13  lea     rcx, aBaseWinsatStor; "base\\winsat\\storage\\diskprof.cpp"
0x140065b1a  call    Log_Text_F
0x140065b1f  mov     rcx, r15; hObject
0x140065b22  call    cs:__imp_CloseHandle
0x140065b28  mov     r15d, r14d
0x140065b2b  add     rbx, 4
0x140065b2f  jmp     loc_140065A80
0x140065b34  lea     rcx, [rsp+78h+arg_18]
0x140065b3c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140065b41  mov     ecx, 201000Bh; dwErrCode
0x140065b46  call    cs:__imp_SetLastError
0x140065b4c  xor     al, al
0x140065b4e  jmp     loc_140065E00
0x140065b53  lea     r8, aInfoWinsatIosU; "info: WinSAT IOs = %u, Allowed interfer"...
0x140065b5a  mov     edx, 0F33h
0x140065b5f  call    Log_Text_F
0x140065b64  lea     rdx, [rbx+98h]
0x140065b6b  lea     rcx, [rsp+78h+var_48]
0x140065b70  call    ??0?$vector@UIOInformation@StorageDevice@WinSAT@@V?$allocator@UIOInformation@StorageDevice@WinSAT@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<WinSAT::StorageDevice::IOInformation>::vector<WinSAT::StorageDevice::IOInformation>(std::vector<WinSAT::StorageDevice::IOInformation> const &)
0x140065b75  test    byte ptr [rdi+0CCh], 2
0x140065b7c  jz      short loc_140065B96
0x140065b7e  lea     r8, aCccSkippingThe; "CCC - Skipping the heuristic for random"...
0x140065b85  mov     edx, 0F3Ah
0x140065b8a  lea     rcx, aBaseWinsatStor; "base\\winsat\\storage\\diskprof.cpp"
0x140065b91  call    Log_Text_F
0x140065b96  test    byte ptr [rdi+0CCh], 1
0x140065b9d  jz      loc_140065CD9
0x140065ba3  mov     rcx, [rsp+78h+var_48]
0x140065ba8  mov     rax, rcx
0x140065bab  mov     r9, [rsp+78h+var_40]
0x140065bb0  cmp     rax, r9
0x140065bb3  jz      short loc_140065BC2
0x140065bb5  add     r14, [rax+8]
0x140065bb9  inc     r15d
0x140065bbc  add     rax, 28h ; '('
0x140065bc0  jmp     short loc_140065BB0
0x140065bc2  test    r15d, r15d
0x140065bc5  jz      short loc_140065BD5
0x140065bc7  mov     r8d, r15d
0x140065bca  xor     edx, edx
0x140065bcc  mov     rax, r14
0x140065bcf  div     r8
0x140065bd2  mov     r14, rax
0x140065bd5  mov     edx, [rbx+8Ch]
0x140065bdb  mov     rax, r9
0x140065bde  sub     rax, rcx
0x140065be1  sar     rax, 3
0x140065be5  mov     rdi, 0CCCCCCCCCCCCCCCDh
0x140065bef  imul    rax, rdi
0x140065bf3  cmp     rax, rdx
0x140065bf6  jb      short loc_140065C1E
0x140065bf8  test    edx, edx
0x140065bfa  jz      short loc_140065C1E
0x140065bfc  cmp     rcx, r9
0x140065bff  jz      short loc_140065C1E
0x140065c01  cmp     [rcx+8], r14
0x140065c05  jbe     short loc_140065C15
0x140065c07  mov     rax, r14
0x140065c0a  sub     rax, [rcx+8]
0x140065c0e  add     [rbx+28h], rax
0x140065c12  inc     r12d
0x140065c15  add     rcx, 28h ; '('
0x140065c19  cmp     r12d, edx
0x140065c1c  jnz     short loc_140065BFC
0x140065c1e  lea     r8, aCccNormalizedT; "CCC - Normalized the high IO values - S"...
0x140065c25  mov     edx, 0F52h
0x140065c2a  lea     rcx, aBaseWinsatStor; "base\\winsat\\storage\\diskprof.cpp"
0x140065c31  call    Log_Text_F
0x140065c36  jmp     loc_140065CD9
0x140065c3b  test    dword ptr [rcx+0CCh], 10000000h
0x140065c45  jnz     loc_140065CE4
0x140065c4b  lea     rdx, [r8+98h]
0x140065c52  lea     rcx, [rsp+78h+var_48]
0x140065c57  call    ??0?$vector@UIOInformation@StorageDevice@WinSAT@@V?$allocator@UIOInformation@StorageDevice@WinSAT@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<WinSAT::StorageDevice::IOInformation>::vector<WinSAT::StorageDevice::IOInformation>(std::vector<WinSAT::StorageDevice::IOInformation> const &)
0x140065c5c  nop
0x140065c5d  mov     rdx, [rsp+78h+var_40]
0x140065c62  mov     rcx, [rsp+78h+var_48]
0x140065c67  mov     r8, rdx
0x140065c6a  sub     r8, rcx
0x140065c6d  sar     r8, 3
0x140065c71  mov     rdi, 0CCCCCCCCCCCCCCCDh
0x140065c7b  imul    r8, rdi
0x140065c7f  mov     r9b, [rsp+78h+arg_8]
0x140065c87  call    ??$_Sort@PEAUIOInformation@StorageDevice@WinSAT@@_JUSDescendingSrvTime@123@@std@@YAXPEAUIOInformation@StorageDevice@WinSAT@@0_JUSDescendingSrvTime@123@@Z; std::_Sort<WinSAT::StorageDevice::IOInformation *,__int64,WinSAT::StorageDevice::IOInformation::SDescendingSrvTime>(WinSAT::StorageDevice::IOInformation *,WinSAT::StorageDevice::IOInformation *,__int64,WinSAT::StorageDevice::IOInformation::SDescendingSrvTime)
0x140065c8c  mov     r8d, [rbx+8Ch]
0x140065c93  mov     rcx, [rsp+78h+var_40]
0x140065c98  mov     rax, [rsp+78h+var_48]
0x140065c9d  sub     rcx, rax
0x140065ca0  sar     rcx, 3
0x140065ca4  imul    rcx, rdi
0x140065ca8  cmp     rcx, r8
0x140065cab  jb      short loc_140065CD9
0x140065cad  xor     r9d, r9d
0x140065cb0  test    r8d, r8d
0x140065cb3  jz      short loc_140065CD9
0x140065cb5  mov     rcx, [rbx+10h]
0x140065cb9  mov     rdx, [rbx+28h]
0x140065cbd  sub     rcx, [rax+18h]
0x140065cc1  mov     [rbx+10h], rcx
0x140065cc5  sub     rdx, [rax+8]
0x140065cc9  mov     [rbx+28h], rdx
0x140065ccd  lea     rax, [rax+28h]
0x140065cd1  inc     r9d
0x140065cd4  cmp     r9d, r8d
0x140065cd7  jb      short loc_140065CBD
0x140065cd9  lea     rcx, [rsp+78h+var_48]
0x140065cde  call    ??1?$vector@PEAU_D3DRECT@@V?$allocator@PEAU_D3DRECT@@@std@@@std@@QEAA@XZ; std::vector<_D3DRECT *>::~vector<_D3DRECT *>(void)
0x140065ce3  nop
0x140065ce4  jmp     short loc_140065CF6
0x140065ce6  mov     rbx, [rsp+78h+arg_10]
0x140065cee  mov     r13b, [rsp+78h+arg_8]
0x140065cf6  cmp     dword ptr [rbx+70h], 0
0x140065cfa  jbe     short loc_140065D79
0x140065cfc  mov     eax, [rbx+70h]
0x140065cff  xorps   xmm1, xmm1
0x140065d02  cvtsi2sd xmm1, rax
0x140065d07  movsd   xmm0, qword ptr [rbx+58h]
0x140065d0c  divsd   xmm0, xmm1
0x140065d10  movsd   qword ptr [rbx+58h], xmm0
0x140065d15  mov     rcx, [rbx+30h]
0x140065d19  xorps   xmm0, xmm0
0x140065d1c  test    rcx, rcx
0x140065d1f  js      short loc_140065D28
0x140065d21  cvtsi2sd xmm0, rcx
0x140065d26  jmp     short loc_140065D3D
0x140065d28  mov     rax, rcx
0x140065d2b  shr     rax, 1
0x140065d2e  and     ecx, 1
0x140065d31  or      rax, rcx
0x140065d34  cvtsi2sd xmm0, rax
0x140065d39  addsd   xmm0, xmm0
0x140065d3d  divsd   xmm0, xmm1
0x140065d41  movsd   qword ptr [rbx+60h], xmm0
0x140065d46  mov     rcx, [rbx+28h]
0x140065d4a  xorps   xmm0, xmm0
0x140065d4d  test    rcx, rcx
0x140065d50  js      short loc_140065D59
0x140065d52  cvtsi2sd xmm0, rcx
0x140065d57  jmp     short loc_140065D6E
0x140065d59  mov     rax, rcx
0x140065d5c  shr     rax, 1
0x140065d5f  and     ecx, 1
0x140065d62  or      rax, rcx
0x140065d65  cvtsi2sd xmm0, rax
0x140065d6a  addsd   xmm0, xmm0
0x140065d6e  divsd   xmm0, xmm1
0x140065d72  movsd   qword ptr [rbx+68h], xmm0
0x140065d77  jmp     short loc_140065D7C
0x140065d79  mov     r13b, 1
0x140065d7c  mov     rdx, [rbx+28h]
0x140065d80  test    rdx, rdx
0x140065d83  jz      short loc_140065DF3
0x140065d85  mov     rcx, [rbx+10h]
0x140065d89  xorps   xmm0, xmm0
0x140065d8c  test    rcx, rcx
0x140065d8f  js      short loc_140065D98
0x140065d91  cvtsi2sd xmm0, rcx
0x140065d96  jmp     short loc_140065DAD
0x140065d98  mov     rax, rcx
0x140065d9b  shr     rax, 1
0x140065d9e  and     ecx, 1
0x140065da1  or      rax, rcx
0x140065da4  cvtsi2sd xmm0, rax
0x140065da9  addsd   xmm0, xmm0
0x140065dad  mulsd   xmm0, cs:__real@3eb0000000000000
0x140065db5  xorps   xmm1, xmm1
0x140065db8  test    rdx, rdx
0x140065dbb  js      short loc_140065DC4
0x140065dbd  cvtsi2sd xmm1, rdx
0x140065dc2  jmp     short loc_140065DD9
0x140065dc4  mov     rcx, rdx
0x140065dc7  shr     rcx, 1
0x140065dca  and     edx, 1
0x140065dcd  or      rcx, rdx
0x140065dd0  cvtsi2sd xmm1, rcx
0x140065dd5  addsd   xmm1, xmm1
0x140065dd9  divsd   xmm1, cs:__real@412e848000000000
0x140065de1  divsd   xmm0, xmm1
0x140065de5  movsd   qword ptr [rbx+50h], xmm0
  ... truncated ...
```
