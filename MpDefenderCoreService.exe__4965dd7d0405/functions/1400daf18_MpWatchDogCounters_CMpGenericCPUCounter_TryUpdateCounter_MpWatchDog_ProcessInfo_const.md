# MpWatchDogCounters::CMpGenericCPUCounter::TryUpdateCounter(MpWatchDog::ProcessInfo const *)

- ea: `0x1400daf18`
- end: `0x1400db274`
- name: `?TryUpdateCounter@CMpGenericCPUCounter@MpWatchDogCounters@@QEAA_NPEBVProcessInfo@MpWatchDog@@@Z`
- size: `860`
- prototype: `bool __fastcall(MpWatchDogCounters::CMpGenericCPUCounter *__hidden this, const struct MpWatchDog::ProcessInfo *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400db280`

## callees

- `0x14003a5c0`
- `0x140049330`
- `0x14007d210`
- `0x140085d38`
- `0x140085eb4`
- `0x1400da4cc`
- `0x1400da5c8`
- `0x1400da838`
- `0x1400daf18`
- `0x1400db290`
- `0x140166250`

## import_xrefs

- `KERNEL32!GetProcessTimes` at `0x1400db0c0`
- `KERNEL32!GetProcessTimes` at `0x1400db0c0`
- `KERNEL32!OpenProcess` at `0x1400db032`
- `KERNEL32!OpenProcess` at `0x1400db032`
- `KERNEL32!CloseHandle` at `0x1400db22c`
- `KERNEL32!CloseHandle` at `0x1400db22c`
- `KERNEL32!GetLastError` at `0x1400db0e4`
- `KERNEL32!GetLastError` at `0x1400db1ec`
- `KERNEL32!GetLastError` at `0x1400db0e4`
- `KERNEL32!GetLastError` at `0x1400db1ec`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400db0a2`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400db0a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall MpWatchDogCounters::CMpGenericCPUCounter::TryUpdateCounter(
        MpWatchDogCounters::CMpGenericCPUCounter *this,
        const struct MpWatchDog::ProcessInfo *a2)
{
  __int64 *v4; // rbx
  __int64 v5; // rdi
  const wchar_t *v6; // rax
  const wchar_t *v7; // rcx
  __int64 **v8; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  DWORD v11; // r15d
  HANDLE v12; // rbx
  DWORD LastError; // eax
  __int64 *v14; // rdx
  __int64 *v15; // rax
  __int64 *v16; // rcx
  const struct MpWatchDogCounters::CPUDataPoint *v17; // r8
  __int128 v18; // xmm7
  __int128 v19; // xmm8
  __int64 v20; // xmm6_8
  __int64 v21; // rax
  DWORD v22; // eax
  unsigned int v24; // [rsp+38h] [rbp-89h] BYREF
  DWORD v25; // [rsp+40h] [rbp-81h] BYREF
  struct _FILETIME v26; // [rsp+44h] [rbp-7Dh]
  int v27; // [rsp+4Ch] [rbp-75h]
  __int128 v28; // [rsp+50h] [rbp-71h]
  __int64 v29; // [rsp+60h] [rbp-61h]
  HANDLE v30; // [rsp+68h] [rbp-59h]
  __int64 v31; // [rsp+70h] [rbp-51h] BYREF
  struct _FILETIME CreationTime; // [rsp+78h] [rbp-49h] BYREF
  _BYTE SystemTimeAsFileTime[40]; // [rsp+80h] [rbp-41h] BYREF
  struct _FILETIME ExitTime; // [rsp+A8h] [rbp-19h] BYREF

  if ( !a2 )
    return 0;
  v4 = (__int64 *)**((_QWORD **)this + 10);
  while ( !*((_BYTE *)v4 + 25) )
  {
    v24 = *((_DWORD *)v4 + 7);
    v5 = std::map<unsigned int,std::wstring const>::operator[]((char *)this + 64, &v24);
    v31 = 0;
    v6 = (const wchar_t *)(*(__int64 (__fastcall **)(const struct MpWatchDog::ProcessInfo *, __int64 *))(*(_QWORD *)a2 + 8LL))(
                            a2,
                            &v31);
    if ( v31 && v6 )
    {
      v7 = (const wchar_t *)v5;
      if ( *(_QWORD *)(v5 + 24) > 7u )
        v7 = *(const wchar_t **)v5;
      if ( !wcsicmp(v7, v6) )
      {
        v11 = (**(__int64 (__fastcall ***)(const struct MpWatchDog::ProcessInfo *))a2)(a2);
        v12 = OpenProcess(0x1000u, 0, v11);
        v30 = v12;
        if ( v12 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 )
          {
            if ( *(_QWORD *)(v5 + 24) > 7u )
              v5 = *(_QWORD *)v5;
            WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_5c0db30039763a4066e32a4d389367bf_Traceguids, v5);
          }
          *(_DWORD *)SystemTimeAsFileTime = v11;
          memset(&SystemTimeAsFileTime[4], 0, 36);
          CreationTime = 0;
          ExitTime = 0;
          GetSystemTimeAsFileTime((LPFILETIME)&SystemTimeAsFileTime[4]);
          if ( GetProcessTimes(
                 v12,
                 &CreationTime,
                 &ExitTime,
                 (LPFILETIME)&SystemTimeAsFileTime[20],
                 (LPFILETIME)&SystemTimeAsFileTime[12]) )
          {
            v14 = (__int64 *)*((_QWORD *)this + 12);
            v15 = (__int64 *)v14[1];
            v27 = 0;
            v16 = v14;
            while ( !*((_BYTE *)v15 + 25) )
            {
              if ( *((_DWORD *)v15 + 8) >= v24 )
                v16 = v15;
              else
                v15 += 2;
              v15 = (__int64 *)*v15;
            }
            if ( *((_BYTE *)v16 + 25)
              || v24 < *((_DWORD *)v16 + 8)
              || v16 == v14
              || *(_DWORD *)std::map<unsigned int,MpWatchDogCounters::CPUDataPoint>::operator[]((char *)this + 96, &v24) != v11 )
            {
              v25 = v11;
              v26 = CreationTime;
              v27 = 0;
              v28 = 0;
              v29 = 0;
              v17 = (const struct MpWatchDogCounters::CPUDataPoint *)&v25;
            }
            else
            {
              v17 = (const struct MpWatchDogCounters::CPUDataPoint *)std::map<unsigned int,MpWatchDogCounters::CPUDataPoint>::operator[](
                                                                       (char *)this + 96,
                                                                       &v24);
            }
            *(_QWORD *)&SystemTimeAsFileTime[32] = MpWatchDogCounters::CMpGenericCPUCounter::ComputeCPUPercentage(
                                                     this,
                                                     (const struct MpWatchDogCounters::CPUDataPoint *)SystemTimeAsFileTime,
                                                     v17);
            v18 = *(_OWORD *)SystemTimeAsFileTime;
            v19 = *(_OWORD *)&SystemTimeAsFileTime[16];
            v20 = *(_QWORD *)&SystemTimeAsFileTime[32];
            v21 = std::map<unsigned int,MpWatchDogCounters::CPUDataPoint>::operator[]((char *)this + 96, &v24);
            *(_OWORD *)v21 = v18;
            *(_OWORD *)(v21 + 16) = v19;
            *(_QWORD *)(v21 + 32) = v20;
          }
          else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 )
          {
            LastError = GetLastError();
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              13,
              WPP_5c0db30039763a4066e32a4d389367bf_Traceguids,
              LastError);
          }
        }
        else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 )
        {
          v22 = GetLastError();
          WPP_SF_Dd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            14,
            WPP_5c0db30039763a4066e32a4d389367bf_Traceguids,
            v11,
            v22);
        }
        std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::erase(
          (char *)this + 80,
          &v24);
        if ( v12 )
          CloseHandle(v12);
        return *((_QWORD *)this + 11) != 0;
      }
    }
    v8 = (__int64 **)v4[2];
    if ( *((_BYTE *)v8 + 25) )
    {
      for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v4 = i;
      v4 = i;
    }
    else
    {
      v4 = (__int64 *)v4[2];
      for ( j = *v8; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v4 = j;
    }
  }
  return *((_QWORD *)this + 11) != 0;
}

```

## disassembly

```asm
0x1400daf18  mov     rax, rsp
0x1400daf1b  mov     [rax+18h], rbx
0x1400daf1f  push    rbp
0x1400daf20  push    rsi
0x1400daf21  push    rdi
0x1400daf22  push    r12
0x1400daf24  push    r13
0x1400daf26  push    r14
0x1400daf28  push    r15
0x1400daf2a  lea     rbp, [rax-5Fh]
0x1400daf2e  sub     rsp, 0E0h
0x1400daf35  movaps  xmmword ptr [rax-48h], xmm6
0x1400daf39  movaps  xmmword ptr [rax-58h], xmm7
0x1400daf3d  movaps  xmmword ptr [rax-68h], xmm8
0x1400daf42  mov     rax, cs:__security_cookie
0x1400daf49  xor     rax, rsp
0x1400daf4c  mov     [rbp+57h+var_68], rax
0x1400daf50  mov     rsi, rdx
0x1400daf53  mov     r14, rcx
0x1400daf56  xor     r13d, r13d
0x1400daf59  test    rdx, rdx
0x1400daf5c  jz      loc_1400DB23C
0x1400daf62  mov     rbx, [rcx+50h]
0x1400daf66  mov     rbx, [rbx]
0x1400daf69  cmp     [rbx+19h], r13b
0x1400daf6d  jnz     loc_1400DB232
0x1400daf73  mov     eax, [rbx+1Ch]
0x1400daf76  mov     [rsp+110h+var_E0], eax
0x1400daf7a  lea     rcx, [r14+40h]
0x1400daf7e  lea     rdx, [rsp+110h+var_E0]
0x1400daf83  call    ??A?$map@I$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBI$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBI@Z; std::map<uint,std::wstring const>::operator[](uint const &)
0x1400daf88  mov     rdi, rax
0x1400daf8b  mov     [rbp+57h+var_A8], r13
0x1400daf8f  mov     rax, [rsi]
0x1400daf92  lea     rdx, [rbp+57h+var_A8]
0x1400daf96  mov     rcx, rsi
0x1400daf99  mov     rax, [rax+8]
0x1400daf9d  call    cs:__guard_dispatch_icall_fptr
0x1400dafa3  cmp     [rbp+57h+var_A8], r13
0x1400dafa7  jz      short loc_1400DAFC7
0x1400dafa9  test    rax, rax
0x1400dafac  jz      short loc_1400DAFC7
0x1400dafae  mov     rcx, rdi
0x1400dafb1  cmp     qword ptr [rdi+18h], 7
0x1400dafb6  jbe     short loc_1400DAFBB
0x1400dafb8  mov     rcx, [rdi]; String1
0x1400dafbb  mov     rdx, rax; String2
0x1400dafbe  call    _wcsicmp
0x1400dafc3  test    eax, eax
0x1400dafc5  jz      short loc_1400DB016
0x1400dafc7  mov     rcx, [rbx+10h]
0x1400dafcb  cmp     [rcx+19h], r13b
0x1400dafcf  jz      short loc_1400DAFF2
0x1400dafd1  mov     rax, [rbx+8]
0x1400dafd5  jmp     short loc_1400DAFE4
0x1400dafd7  cmp     rbx, [rax+10h]
0x1400dafdb  jnz     short loc_1400DAFEA
0x1400dafdd  mov     rbx, rax
0x1400dafe0  mov     rax, [rax+8]
0x1400dafe4  cmp     [rax+19h], r13b
0x1400dafe8  jz      short loc_1400DAFD7
0x1400dafea  mov     rbx, rax
0x1400dafed  jmp     loc_1400DAF69
0x1400daff2  mov     rbx, rcx
0x1400daff5  mov     rcx, [rcx]
0x1400daff8  cmp     [rcx+19h], r13b
0x1400daffc  jnz     loc_1400DAF69
0x1400db002  mov     rbx, rcx
0x1400db005  mov     rax, [rcx]
0x1400db008  mov     rcx, rax
0x1400db00b  cmp     [rax+19h], r13b
0x1400db00f  jz      short loc_1400DB002
0x1400db011  jmp     loc_1400DAF69
0x1400db016  mov     rax, [rsi]
0x1400db019  mov     rcx, rsi
0x1400db01c  mov     rax, [rax]
0x1400db01f  call    cs:__guard_dispatch_icall_fptr
0x1400db025  mov     r15d, eax
0x1400db028  mov     r8d, eax; dwProcessId
0x1400db02b  xor     edx, edx; bInheritHandle
0x1400db02d  mov     ecx, 1000h; dwDesiredAccess
0x1400db032  call    cs:__imp_OpenProcess
0x1400db038  mov     rbx, rax
0x1400db03b  mov     [rbp+57h+var_B0], rax
0x1400db03f  test    rax, rax
0x1400db042  jz      loc_1400DB1D3
0x1400db048  lea     rsi, WPP_GLOBAL_Control
0x1400db04f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400db056  cmp     rcx, rsi
0x1400db059  jz      short loc_1400DB083
0x1400db05b  test    byte ptr [rcx+1Ch], 10h
0x1400db05f  jz      short loc_1400DB083
0x1400db061  cmp     qword ptr [rdi+18h], 7
0x1400db066  jbe     short loc_1400DB06B
0x1400db068  mov     rdi, [rdi]
0x1400db06b  mov     edx, 0Ch
0x1400db070  mov     r9, rdi
0x1400db073  lea     r8, WPP_5c0db30039763a4066e32a4d389367bf_Traceguids
0x1400db07a  mov     rcx, [rcx+10h]
0x1400db07e  call    WPP_SF_S
0x1400db083  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15d
0x1400db087  mov     [rbp+57h+SystemTimeAsFileTime.dwHighDateTime], r13d
0x1400db08b  xorps   xmm0, xmm0
0x1400db08e  movups  xmmword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime+8], xmm0
0x1400db092  movups  xmmword ptr [rbp+57h+KernelTime.dwHighDateTime], xmm0
0x1400db096  mov     qword ptr [rbp+57h+CreationTime.dwLowDateTime], r13
0x1400db09a  mov     qword ptr [rbp+57h+ExitTime.dwLowDateTime], r13
0x1400db09e  lea     rcx, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]; lpSystemTimeAsFileTime
0x1400db0a2  call    cs:__imp_GetSystemTimeAsFileTime
0x1400db0a8  lea     rax, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime+8]
0x1400db0ac  mov     [rsp+110h+lpUserTime], rax; lpUserTime
0x1400db0b1  lea     r9, [rbp+57h+KernelTime]; lpKernelTime
0x1400db0b5  lea     r8, [rbp+57h+ExitTime]; lpExitTime
0x1400db0b9  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x1400db0bd  mov     rcx, rbx; hProcess
0x1400db0c0  call    cs:__imp_GetProcessTimes
0x1400db0c6  test    eax, eax
0x1400db0c8  jnz     short loc_1400DB10E
0x1400db0ca  mov     rax, cs:WPP_GLOBAL_Control
0x1400db0d1  cmp     rax, rsi
0x1400db0d4  jz      loc_1400DB215
0x1400db0da  test    byte ptr [rax+1Ch], 10h
0x1400db0de  jz      loc_1400DB215
0x1400db0e4  call    cs:__imp_GetLastError
0x1400db0ea  mov     edx, 0Dh
0x1400db0ef  mov     r9d, eax
0x1400db0f2  lea     r8, WPP_5c0db30039763a4066e32a4d389367bf_Traceguids
0x1400db0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400db100  mov     rcx, [rcx+10h]
0x1400db104  call    WPP_SF_d
0x1400db109  jmp     loc_1400DB215
0x1400db10e  lea     rdi, [r14+60h]
0x1400db112  mov     rdx, [rdi]
0x1400db115  mov     rax, [rdx+8]
0x1400db119  xor     ecx, ecx
0x1400db11b  mov     [rbp+57h+var_CC], ecx
0x1400db11e  mov     rcx, rdx
0x1400db121  mov     r8d, [rsp+110h+var_E0]
0x1400db126  jmp     short loc_1400DB13A
0x1400db128  cmp     [rax+20h], r8d
0x1400db12c  jnb     short loc_1400DB134
0x1400db12e  add     rax, 10h
0x1400db132  jmp     short loc_1400DB137
0x1400db134  mov     rcx, rax
0x1400db137  mov     rax, [rax]
0x1400db13a  cmp     [rax+19h], r13b
0x1400db13e  jz      short loc_1400DB128
0x1400db140  cmp     [rcx+19h], r13b
0x1400db144  jnz     short loc_1400DB175
0x1400db146  cmp     r8d, [rcx+20h]
0x1400db14a  jb      short loc_1400DB175
0x1400db14c  cmp     rcx, rdx
0x1400db14f  jz      short loc_1400DB175
0x1400db151  lea     rdx, [rsp+110h+var_E0]
0x1400db156  mov     rcx, rdi
0x1400db159  call    ??A?$map@IUCPUDataPoint@MpWatchDogCounters@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIUCPUDataPoint@MpWatchDogCounters@@@std@@@4@@std@@QEAAAEAUCPUDataPoint@MpWatchDogCounters@@AEBI@Z; std::map<uint,MpWatchDogCounters::CPUDataPoint>::operator[](uint const &)
0x1400db15e  cmp     [rax], r15d
0x1400db161  jnz     short loc_1400DB175
0x1400db163  lea     rdx, [rsp+110h+var_E0]
0x1400db168  mov     rcx, rdi
0x1400db16b  call    ??A?$map@IUCPUDataPoint@MpWatchDogCounters@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIUCPUDataPoint@MpWatchDogCounters@@@std@@@4@@std@@QEAAAEAUCPUDataPoint@MpWatchDogCounters@@AEBI@Z; std::map<uint,MpWatchDogCounters::CPUDataPoint>::operator[](uint const &)
0x1400db170  mov     r8, rax
0x1400db173  jmp     short loc_1400DB198
0x1400db175  mov     [rsp+110h+var_D8], r15d
0x1400db17a  mov     rax, qword ptr [rbp+57h+CreationTime.dwLowDateTime]
0x1400db17e  mov     [rbp+57h+var_D4], rax
0x1400db182  mov     [rbp+57h+var_CC], r13d
0x1400db186  xorps   xmm0, xmm0
0x1400db189  xor     eax, eax
0x1400db18b  movups  [rbp+57h+var_C8], xmm0
0x1400db18f  mov     [rbp+57h+var_B8], rax
0x1400db193  lea     r8, [rsp+110h+var_D8]; struct MpWatchDogCounters::CPUDataPoint *
0x1400db198  lea     rdx, [rbp+57h+SystemTimeAsFileTime]; struct MpWatchDogCounters::CPUDataPoint *
0x1400db19c  mov     rcx, r14; this
0x1400db19f  call    ?ComputeCPUPercentage@CMpGenericCPUCounter@MpWatchDogCounters@@IEAANAEBUCPUDataPoint@2@0@Z; MpWatchDogCounters::CMpGenericCPUCounter::ComputeCPUPercentage(MpWatchDogCounters::CPUDataPoint const &,MpWatchDogCounters::CPUDataPoint const &)
0x1400db1a4  movsd   qword ptr [rbp-21h], xmm0
0x1400db1a9  movups  xmm7, xmmword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1400db1ad  movups  xmm8, xmmword ptr [rbp-31h]
0x1400db1b2  movsd   xmm6, qword ptr [rbp-21h]
0x1400db1b7  lea     rdx, [rsp+110h+var_E0]
0x1400db1bc  mov     rcx, rdi
0x1400db1bf  call    ??A?$map@IUCPUDataPoint@MpWatchDogCounters@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIUCPUDataPoint@MpWatchDogCounters@@@std@@@4@@std@@QEAAAEAUCPUDataPoint@MpWatchDogCounters@@AEBI@Z; std::map<uint,MpWatchDogCounters::CPUDataPoint>::operator[](uint const &)
0x1400db1c4  movups  xmmword ptr [rax], xmm7
0x1400db1c7  movups  xmmword ptr [rax+10h], xmm8
0x1400db1cc  movsd   qword ptr [rax+20h], xmm6
0x1400db1d1  jmp     short loc_1400DB215
0x1400db1d3  lea     rsi, WPP_GLOBAL_Control
0x1400db1da  mov     rax, cs:WPP_GLOBAL_Control
0x1400db1e1  cmp     rax, rsi
0x1400db1e4  jz      short loc_1400DB215
0x1400db1e6  test    byte ptr [rax+1Ch], 10h
0x1400db1ea  jz      short loc_1400DB215
0x1400db1ec  call    cs:__imp_GetLastError
0x1400db1f2  mov     edx, 0Eh
0x1400db1f7  mov     dword ptr [rsp+110h+lpUserTime], eax
0x1400db1fb  mov     r9d, r15d
0x1400db1fe  lea     r8, WPP_5c0db30039763a4066e32a4d389367bf_Traceguids
0x1400db205  mov     rcx, cs:WPP_GLOBAL_Control
0x1400db20c  mov     rcx, [rcx+10h]
0x1400db210  call    WPP_SF_Dd
0x1400db215  lea     rdx, [rsp+110h+var_E0]
0x1400db21a  lea     rcx, [r14+50h]
0x1400db21e  call    ?erase@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@QEAA_KAEBI@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::erase(uint const &)
0x1400db223  nop
0x1400db224  test    rbx, rbx
0x1400db227  jz      short loc_1400DB232
0x1400db229  mov     rcx, rbx; hObject
0x1400db22c  call    cs:__imp_CloseHandle
0x1400db232  cmp     [r14+58h], r13
0x1400db236  jz      short loc_1400DB23C
0x1400db238  mov     al, 1
0x1400db23a  jmp     short loc_1400DB23E
0x1400db23c  xor     al, al
0x1400db23e  mov     rcx, [rbp+57h+var_68]
0x1400db242  xor     rcx, rsp; StackCookie
0x1400db245  call    __security_check_cookie
0x1400db24a  lea     r11, [rsp+110h+var_30]
0x1400db252  mov     rbx, [r11+50h]
0x1400db256  movaps  xmm6, xmmword ptr [r11-10h]
0x1400db25b  movaps  xmm7, xmmword ptr [r11-20h]
0x1400db260  movaps  xmm8, xmmword ptr [r11-30h]
0x1400db265  mov     rsp, r11
0x1400db268  pop     r15
0x1400db26a  pop     r14
0x1400db26c  pop     r13
0x1400db26e  pop     r12
0x1400db270  pop     rdi
0x1400db271  pop     rsi
0x1400db272  pop     rbp
0x1400db273  retn
```
