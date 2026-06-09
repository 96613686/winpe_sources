# _lambda_af5ee0e8a808b2b37da8c471ee883efa_::operator()

- ea: `0x18002bba0`
- end: `0x18002bfff`
- name: `_lambda_af5ee0e8a808b2b37da8c471ee883efa_::operator()`
- size: `1119`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002d370`

## callees

- `0x180009570`
- `0x180009e14`
- `0x180009f84`
- `0x180026af8`
- `0x180027108`
- `0x18002bba0`
- `0x18002cc3c`
- `0x18003d864`
- `0x180049b50`
- `0x18004ad26`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x18002bdb1`
- `VCRUNTIME140!memmove` at `0x18002bdc9`
- `VCRUNTIME140!memmove` at `0x18002bde3`
- `VCRUNTIME140!memmove` at `0x18002bdb1`
- `VCRUNTIME140!memmove` at `0x18002bdc9`
- `VCRUNTIME140!memmove` at `0x18002bde3`
- `KERNEL32!WaitForSingleObject` at `0x18002bf98`
- `KERNEL32!WaitForSingleObject` at `0x18002bf98`
- `KERNEL32!QueryPerformanceCounter` at `0x18002bc2d`
- `KERNEL32!QueryPerformanceCounter` at `0x18002bc2d`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x18002be7f`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x18002be7f`
- `KERNEL32!LeaveCriticalSection` at `0x18002bf6c`
- `KERNEL32!LeaveCriticalSection` at `0x18002bfaf`
- `KERNEL32!LeaveCriticalSection` at `0x18002bfe6`
- `KERNEL32!LeaveCriticalSection` at `0x18002bf6c`
- `KERNEL32!LeaveCriticalSection` at `0x18002bfaf`
- `KERNEL32!LeaveCriticalSection` at `0x18002bfe6`
- `KERNEL32!EnterCriticalSection` at `0x18002bc22`
- `KERNEL32!EnterCriticalSection` at `0x18002bc22`
- `KERNEL32!GetLastError` at `0x18002be89`
- `KERNEL32!GetLastError` at `0x18002be89`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_af5ee0e8a808b2b37da8c471ee883efa_::operator()(__int64 *a1, __int64 a2)
{
  __int64 v2; // r9
  unsigned int v4; // r14d
  unsigned int v5; // r15d
  unsigned int v6; // edi
  double v7; // xmm6_8
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  LARGE_INTEGER v9; // r12
  __int64 v10; // rsi
  int CpuData; // eax
  __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  _QWORD *v14; // rax
  unsigned __int64 *v15; // rcx
  unsigned __int64 *v16; // rdi
  __int64 v17; // r14
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r12
  char *v21; // r15
  __int64 v22; // r14
  unsigned __int64 *v23; // r8
  __int64 v24; // rdi
  __int64 v25; // r14
  signed int LastError; // eax
  unsigned int v27; // edi
  __int64 v28; // rdx
  __int64 v30; // [rsp+28h] [rbp-B9h]
  unsigned __int64 v31; // [rsp+30h] [rbp-B1h] BYREF
  unsigned __int64 v32; // [rsp+38h] [rbp-A9h] BYREF
  double v33; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v34; // [rsp+48h] [rbp-99h]
  __int64 v35; // [rsp+50h] [rbp-91h]
  LARGE_INTEGER v36; // [rsp+58h] [rbp-89h]
  _QWORD v37[2]; // [rsp+60h] [rbp-81h] BYREF
  _QWORD v38[3]; // [rsp+70h] [rbp-71h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+88h] [rbp-59h] BYREF
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+98h] [rbp-49h] BYREF
  __int64 v41; // [rsp+E0h] [rbp-1h]

  v2 = a2;
  v34 = a2;
  v4 = 0x493E0u / *(_DWORD *)(*a1 + 556);
  HIDWORD(v30) = v4;
  v5 = 0;
  v6 = 0;
  LODWORD(v30) = 0;
  v7 = v33;
  while ( 1 )
  {
    if ( *(_BYTE *)(*a1 + 24) )
      goto LABEL_46;
    v8 = (struct _RTL_CRITICAL_SECTION *)(*a1 + 144);
    v38[2] = v8;
    EnterCriticalSection(v8);
    if ( !QueryPerformanceCounter(&PerformanceCount) )
      break;
    v9 = PerformanceCount;
    v36 = PerformanceCount;
    v10 = *a1;
    if ( *(_BYTE *)(*a1 + 328) )
    {
      v5 += *(_DWORD *)(v10 + 556);
      if ( v5 >= *(_DWORD *)(v10 + 332) )
      {
        v31 = 0;
        v32 = 0;
        CpuData = Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::GetCpuData(
                    (Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters *)v10,
                    &v33,
                    &v31,
                    &v32);
        v7 = v33;
        if ( !CpuData )
        {
          v37[0] = v9.QuadPart;
          *(double *)&v37[1] = v33;
          v12 = *(_QWORD *)(v10 + 344);
          if ( v12 == *(_QWORD *)(v10 + 352) )
          {
            std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(
              v10 + 336,
              v12,
              v37);
          }
          else
          {
            *(LARGE_INTEGER *)v12 = v9;
            *(double *)(v12 + 8) = v7;
            *(_QWORD *)(v10 + 344) += 16LL;
          }
          v13 = v31;
          v14 = (_QWORD *)(v10 + 360);
          v15 = *(unsigned __int64 **)(v10 + 376);
          v16 = *(unsigned __int64 **)(v10 + 368);
          if ( v16 == v15 )
          {
            v17 = ((__int64)v16 - *v14) >> 4;
            if ( v17 == 0xFFFFFFFFFFFFFFFLL )
              std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(
                v15,
                v31);
            v35 = v17 + 1;
            v18 = ((__int64)v15 - *v14) >> 4;
            v19 = v18 >> 1;
            if ( v18 <= 0xFFFFFFFFFFFFFFFLL - (v18 >> 1) )
            {
              v20 = v17 + 1;
              if ( v19 + v18 >= v17 + 1 )
                v20 = v19 + v18;
              if ( v20 > 0xFFFFFFFFFFFFFFFLL )
                __scrt_throw_std_bad_array_new_length();
            }
            else
            {
              v20 = 0xFFFFFFFFFFFFFFFLL;
            }
            _mm_lfence();
            v21 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(16 * v20);
            v22 = 16 * v17;
            *(_QWORD *)&v21[v22] = v32;
            *(_QWORD *)&v21[v22 + 8] = v31;
            v23 = *(unsigned __int64 **)(v10 + 368);
            if ( v16 == v23 )
            {
              v24 = v10 + 360;
              memmove(v21, *(const void **)(v10 + 360), (size_t)v23 - *(_QWORD *)(v10 + 360));
            }
            else
            {
              memmove(v21, *(const void **)(v10 + 360), (size_t)v16 - *(_QWORD *)(v10 + 360));
              memmove(&v21[v22 + 16], v16, *(_QWORD *)(v10 + 368) - (_QWORD)v16);
              v24 = v10 + 360;
            }
            std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DataPoint>::_Change_array(
              v24,
              v21,
              v35,
              v20);
            v9 = v36;
            v4 = HIDWORD(v30);
          }
          else
          {
            *v16 = v32;
            v16[1] = v13;
            *(_QWORD *)(v10 + 368) += 16LL;
          }
          v6 = v30;
        }
        v5 = 0;
      }
      if ( (unsigned int)((__int64)(*(_QWORD *)(v10 + 344) - *(_QWORD *)(v10 + 336)) >> 4) > v4 )
        *(_BYTE *)(v10 + 328) = 0;
    }
    v25 = *a1;
    if ( !*(_BYTE *)(*a1 + 256) )
      goto LABEL_43;
    v6 += *(_DWORD *)(v25 + 556);
    LODWORD(v30) = v6;
    if ( v6 >= *(_DWORD *)(v25 + 260) )
    {
      memset_0(&ppsmemCounters, 0, 0x50u);
      ppsmemCounters.cb = 80;
      if ( !K32GetProcessMemoryInfo(*(HANDLE *)(v25 + 16), &ppsmemCounters, 0x50u) )
      {
        LastError = GetLastError();
        v27 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v27 = LastError;
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 168),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\ProcessCounters.cpp",
          L"Failed to get private bytes counter. Error code: 0x%08x",
          v27,
          v30);
        if ( !v27 )
        {
LABEL_37:
          v38[0] = v9.QuadPart;
          *(double *)&v38[1] = v7;
          v28 = *(_QWORD *)(v25 + 272);
          if ( v28 == *(_QWORD *)(v25 + 280) )
          {
            std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(
              v25 + 264,
              v28,
              v38);
          }
          else
          {
            *(LARGE_INTEGER *)v28 = v9;
            *(double *)(v28 + 8) = v7;
            *(_QWORD *)(v25 + 272) += 16LL;
          }
        }
        v6 = 0;
        LODWORD(v30) = 0;
        goto LABEL_41;
      }
      if ( v41 < 0 )
        v7 = (double)(int)(v41 & 1 | ((unsigned __int64)v41 >> 1))
           + (double)(int)(v41 & 1 | ((unsigned __int64)v41 >> 1));
      else
        v7 = (double)(int)v41;
      v33 = v7;
      goto LABEL_37;
    }
LABEL_41:
    if ( (unsigned int)((__int64)(*(_QWORD *)(v25 + 272) - *(_QWORD *)(v25 + 264)) >> 4) > HIDWORD(v30) )
      *(_BYTE *)(v25 + 256) = 0;
LABEL_43:
    if ( !*(_BYTE *)(v10 + 328) && !*(_BYTE *)(v25 + 256) )
    {
      LeaveCriticalSection(v8);
      return 0;
    }
    LeaveCriticalSection(v8);
    v2 = v34;
    v4 = HIDWORD(v30);
LABEL_46:
    if ( *(int *)(v2 + 8) >= 0 )
    {
      if ( !WaitForSingleObject(*(HANDLE *)v2, *(_DWORD *)(*a1 + 556)) )
        return 0;
      v2 = v34;
    }
  }
  LeaveCriticalSection(v8);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18002bba0  mov     rax, rsp
0x18002bba3  mov     [rax+18h], rbx
0x18002bba7  push    rbp
0x18002bba8  push    rsi
0x18002bba9  push    rdi
0x18002bbaa  push    r12
0x18002bbac  push    r13
0x18002bbae  push    r14
0x18002bbb0  push    r15
0x18002bbb2  lea     rbp, [rax-5Fh]
0x18002bbb6  sub     rsp, 100h
0x18002bbbd  movaps  xmmword ptr [rax-48h], xmm6
0x18002bbc1  mov     rax, cs:__security_cookie
0x18002bbc8  xor     rax, rsp
0x18002bbcb  mov     [rbp+57h+var_50], rax
0x18002bbcf  mov     r9, rdx
0x18002bbd2  mov     [rsp+130h+var_F0], rdx
0x18002bbd7  mov     r13, rcx
0x18002bbda  mov     r8, [rcx]
0x18002bbdd  xor     edx, edx
0x18002bbdf  mov     eax, 493E0h
0x18002bbe4  div     dword ptr [r8+22Ch]
0x18002bbeb  mov     r14d, eax
0x18002bbee  mov     dword ptr [rsp+130h+var_110+4], eax
0x18002bbf2  xor     r15d, r15d
0x18002bbf5  xor     edi, edi
0x18002bbf7  mov     dword ptr [rsp+130h+var_110], edi
0x18002bbfb  movsd   xmm6, [rsp+130h+var_F8]
0x18002bc01  mov     rcx, [r13+0]
0x18002bc05  mov     dl, [rcx+18h]
0x18002bc08  test    dl, dl
0x18002bc0a  jnz     loc_18002BF7C
0x18002bc10  mov     rbx, [r13+0]
0x18002bc14  add     rbx, 90h
0x18002bc1b  mov     [rbp+57h+var_B8], rbx
0x18002bc1f  mov     rcx, rbx; lpCriticalSection
0x18002bc22  call    cs:__imp_EnterCriticalSection
0x18002bc28  nop
0x18002bc29  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18002bc2d  call    cs:__imp_QueryPerformanceCounter
0x18002bc33  xor     r8d, r8d
0x18002bc36  test    eax, eax
0x18002bc38  jz      loc_18002BFE3
0x18002bc3e  mov     r12, qword ptr [rbp+57h+PerformanceCount]
0x18002bc42  mov     [rsp+130h+var_E0], r12
0x18002bc47  mov     rsi, [r13+0]
0x18002bc4b  cmp     [rsi+148h], r8b
0x18002bc52  jz      loc_18002BE35
0x18002bc58  add     r15d, [rsi+22Ch]
0x18002bc5f  cmp     r15d, [rsi+14Ch]
0x18002bc66  jb      loc_18002BE17
0x18002bc6c  mov     [rsp+130h+var_108], r8
0x18002bc71  mov     [rsp+130h+var_100], r8
0x18002bc76  lea     r9, [rsp+130h+var_100]; unsigned __int64 *
0x18002bc7b  lea     r8, [rsp+130h+var_108]; unsigned __int64 *
0x18002bc80  lea     rdx, [rsp+130h+var_F8]; double *
0x18002bc85  mov     rcx, rsi; this
0x18002bc88  call    ?GetCpuData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEANAEA_K1@Z; Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::GetCpuData(double &,unsigned __int64 &,unsigned __int64 &)
0x18002bc8d  movsd   xmm6, [rsp+130h+var_F8]
0x18002bc93  test    eax, eax
0x18002bc95  jnz     loc_18002BE11
0x18002bc9b  lea     rcx, [rsi+150h]
0x18002bca2  mov     [rsp+130h+var_D8], r12
0x18002bca7  movsd   [rbp+57h+var_D0], xmm6
0x18002bcac  mov     rdx, [rsi+158h]
0x18002bcb3  cmp     rdx, [rsi+160h]
0x18002bcba  jz      short loc_18002BCCB
0x18002bcbc  mov     [rdx], r12
0x18002bcbf  movsd   qword ptr [rdx+8], xmm6
0x18002bcc4  add     qword ptr [rcx+8], 10h
0x18002bcc9  jmp     short loc_18002BCD5
0x18002bccb  lea     r8, [rsp+130h+var_D8]
0x18002bcd0  call    ??$_Emplace_reallocate@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@?$vector@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@AEAAPEATRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@QEAT234567@$$QEAT234567@@Z; std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint * const,Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint &&)
0x18002bcd5  mov     rdx, [rsp+130h+var_108]
0x18002bcda  mov     [rsp+130h+var_108], rdx
0x18002bcdf  lea     rax, [rsi+168h]
0x18002bce6  mov     rcx, [rsi+178h]
0x18002bced  mov     rdi, [rsi+170h]
0x18002bcf4  cmp     rdi, rcx
0x18002bcf7  jz      short loc_18002BD12
0x18002bcf9  mov     rax, [rsp+130h+var_100]
0x18002bcfe  mov     [rdi], rax
0x18002bd01  mov     [rdi+8], rdx
0x18002bd05  add     qword ptr [rsi+170h], 10h
0x18002bd0d  jmp     loc_18002BE0D
0x18002bd12  mov     r14, rdi
0x18002bd15  sub     r14, [rax]
0x18002bd18  sar     r14, 4
0x18002bd1c  mov     r9, 0FFFFFFFFFFFFFFFh
0x18002bd26  cmp     r14, r9
0x18002bd29  jz      loc_18002BFF3
0x18002bd2f  lea     r8, [r14+1]
0x18002bd33  mov     [rsp+130h+var_E8], r8
0x18002bd38  sub     rcx, [rax]
0x18002bd3b  sar     rcx, 4
0x18002bd3f  mov     rdx, rcx
0x18002bd42  shr     rdx, 1
0x18002bd45  mov     rax, r9
0x18002bd48  sub     rax, rdx
0x18002bd4b  cmp     rcx, rax
0x18002bd4e  jbe     short loc_18002BD55
0x18002bd50  mov     r12, r9
0x18002bd53  jmp     short loc_18002BD6C
0x18002bd55  lea     rax, [rdx+rcx]
0x18002bd59  mov     r12, r8
0x18002bd5c  cmp     rax, r8
0x18002bd5f  cmovnb  r12, rax
0x18002bd63  cmp     r12, r9
0x18002bd66  ja      loc_18002BFF9
0x18002bd6c  lfence
0x18002bd6f  mov     rcx, r12
0x18002bd72  shl     rcx, 4
0x18002bd76  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002bd7b  mov     r15, rax
0x18002bd7e  shl     r14, 4
0x18002bd82  mov     rcx, [rsp+130h+var_100]
0x18002bd87  mov     [r14+rax], rcx
0x18002bd8b  mov     rax, [rsp+130h+var_108]
0x18002bd90  mov     [r14+r15+8], rax
0x18002bd95  mov     r8, [rsi+170h]
0x18002bd9c  mov     rcx, r15; void *
0x18002bd9f  cmp     rdi, r8
0x18002bda2  jnz     short loc_18002BDB9
0x18002bda4  lea     rdi, [rsi+168h]
0x18002bdab  sub     r8, [rdi]; Size
0x18002bdae  mov     rdx, [rdi]; Src
0x18002bdb1  call    cs:__imp_memmove
0x18002bdb7  jmp     short loc_18002BDF0
0x18002bdb9  mov     r8, rdi
0x18002bdbc  lea     rax, [rsi+168h]
0x18002bdc3  sub     r8, [rax]; Size
0x18002bdc6  mov     rdx, [rax]; Src
0x18002bdc9  call    cs:__imp_memmove
0x18002bdcf  mov     r8, [rsi+170h]
0x18002bdd6  sub     r8, rdi; Size
0x18002bdd9  lea     rcx, [r14+10h]
0x18002bddd  add     rcx, r15; void *
0x18002bde0  mov     rdx, rdi; Src
0x18002bde3  call    cs:__imp_memmove
0x18002bde9  lea     rdi, [rsi+168h]
0x18002bdf0  mov     r9, r12
0x18002bdf3  mov     r8, [rsp+130h+var_E8]
0x18002bdf8  mov     rdx, r15
0x18002bdfb  mov     rcx, rdi
0x18002bdfe  call    ?_Change_array@?$vector@UDataPoint@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UDataPoint@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@AEAAXQEAUDataPoint@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@_K1@Z; std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DataPoint>::_Change_array(Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::DataPoint * const,unsigned __int64,unsigned __int64)
0x18002be03  mov     r12, [rsp+130h+var_E0]
0x18002be08  mov     r14d, dword ptr [rsp+130h+var_110+4]
0x18002be0d  mov     edi, dword ptr [rsp+130h+var_110]
0x18002be11  xor     r8d, r8d
0x18002be14  mov     r15d, r8d
0x18002be17  mov     rax, [rsi+158h]
0x18002be1e  sub     rax, [rsi+150h]
0x18002be25  sar     rax, 4
0x18002be29  cmp     eax, r14d
0x18002be2c  jbe     short loc_18002BE35
0x18002be2e  mov     [rsi+148h], r8b
0x18002be35  mov     r14, [r13+0]
0x18002be39  cmp     [r14+100h], r8b
0x18002be40  jz      loc_18002BF57
0x18002be46  add     edi, [r14+22Ch]
0x18002be4d  mov     dword ptr [rsp+130h+var_110], edi
0x18002be51  cmp     edi, [r14+104h]
0x18002be58  jb      loc_18002BF38
0x18002be5e  mov     edi, 50h ; 'P'
0x18002be63  mov     r8d, edi; Size
0x18002be66  xor     edx, edx; Val
0x18002be68  lea     rcx, [rbp+57h+ppsmemCounters]; void *
0x18002be6c  call    memset_0
0x18002be71  mov     [rbp+57h+ppsmemCounters.cb], edi
0x18002be74  mov     r8d, edi; cb
0x18002be77  lea     rdx, [rbp+57h+ppsmemCounters]; ppsmemCounters
0x18002be7b  mov     rcx, [r14+10h]; Process
0x18002be7f  call    cs:__imp_K32GetProcessMemoryInfo
0x18002be85  test    eax, eax
0x18002be87  jnz     short loc_18002BEC7
0x18002be89  call    cs:__imp_GetLastError
0x18002be8f  movzx   edi, ax
0x18002be92  or      edi, 80070000h
0x18002be98  test    eax, eax
0x18002be9a  cmovle  edi, eax
0x18002be9d  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18002bea4  add     rcx, 0A8h; this
0x18002beab  mov     r9d, edi
0x18002beae  lea     r8, aFailedToGetPri; "Failed to get private bytes counter. Er"...
0x18002beb5  lea     rdx, aDAWork1SSource_6; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18002bebc  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18002bec1  test    edi, edi
0x18002bec3  jnz     short loc_18002BF2D
0x18002bec5  jmp     short loc_18002BEF5
0x18002bec7  mov     rcx, [rbp+57h+var_58]
0x18002becb  xorps   xmm6, xmm6
0x18002bece  test    rcx, rcx
0x18002bed1  js      short loc_18002BEDA
0x18002bed3  cvtsi2sd xmm6, rcx
0x18002bed8  jmp     short loc_18002BEEF
0x18002beda  mov     rax, rcx
0x18002bedd  shr     rax, 1
0x18002bee0  and     ecx, 1
0x18002bee3  or      rax, rcx
0x18002bee6  cvtsi2sd xmm6, rax
0x18002beeb  addsd   xmm6, xmm6
0x18002beef  movsd   [rsp+130h+var_F8], xmm6
0x18002bef5  lea     rcx, [r14+108h]
0x18002befc  mov     [rbp+57h+var_C8], r12
0x18002bf00  movsd   [rbp+57h+var_C0], xmm6
0x18002bf05  mov     rdx, [r14+110h]
0x18002bf0c  cmp     rdx, [r14+118h]
0x18002bf13  jz      short loc_18002BF24
0x18002bf15  mov     [rdx], r12
0x18002bf18  movsd   qword ptr [rdx+8], xmm6
0x18002bf1d  add     qword ptr [rcx+8], 10h
0x18002bf22  jmp     short loc_18002BF2D
0x18002bf24  lea     r8, [rbp+57h+var_C8]
0x18002bf28  call    ??$_Emplace_reallocate@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@?$vector@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@TRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@AEAAPEATRawDataPoint@CounterData@ProcessCounters@StandardCollector@DiagnosticsHub@Microsoft@@QEAT234567@$$QEAT234567@@Z; std::vector<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>::_Emplace_reallocate<Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint>(Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint * const,Microsoft::DiagnosticsHub::StandardCollector::ProcessCounters::CounterData::RawDataPoint &&)
0x18002bf2d  xor     r8d, r8d
0x18002bf30  mov     edi, r8d
0x18002bf33  mov     dword ptr [rsp+130h+var_110], r8d
0x18002bf38  mov     rax, [r14+110h]
0x18002bf3f  sub     rax, [r14+108h]
0x18002bf46  sar     rax, 4
0x18002bf4a  cmp     eax, dword ptr [rsp+130h+var_110+4]
0x18002bf4e  jbe     short loc_18002BF57
0x18002bf50  mov     [r14+100h], r8b
0x18002bf57  cmp     [rsi+148h], r8b
0x18002bf5e  jnz     short loc_18002BF69
0x18002bf60  cmp     [r14+100h], r8b
0x18002bf67  jz      short loc_18002BFAC
0x18002bf69  mov     rcx, rbx; lpCriticalSection
0x18002bf6c  call    cs:__imp_LeaveCriticalSection
0x18002bf72  mov     r9, [rsp+130h+var_F0]
0x18002bf77  mov     r14d, dword ptr [rsp+130h+var_110+4]
0x18002bf7c  mov     rax, [r13+0]
0x18002bf80  mov     edx, [rax+22Ch]; dwMilliseconds
0x18002bf86  mov     eax, [r9+8]
0x18002bf8a  shr     eax, 1Fh
0x18002bf8d  test    al, al
0x18002bf8f  jnz     loc_18002BC01
0x18002bf95  mov     rcx, [r9]; hHandle
0x18002bf98  call    cs:__imp_WaitForSingleObject
0x18002bf9e  test    eax, eax
0x18002bfa0  jz      short loc_18002BFB5
0x18002bfa2  mov     r9, [rsp+130h+var_F0]
0x18002bfa7  jmp     loc_18002BC01
0x18002bfac  mov     rcx, rbx; lpCriticalSection
0x18002bfaf  call    cs:__imp_LeaveCriticalSection
0x18002bfb5  xor     eax, eax
0x18002bfb7  mov     rcx, [rbp+57h+var_50]
0x18002bfbb  xor     rcx, rsp; StackCookie
0x18002bfbe  call    __security_check_cookie
0x18002bfc3  lea     r11, [rsp+130h+var_30]
0x18002bfcb  mov     rbx, [r11+50h]
0x18002bfcf  movaps  xmm6, xmmword ptr [r11-10h]
0x18002bfd4  mov     rsp, r11
0x18002bfd7  pop     r15
0x18002bfd9  pop     r14
0x18002bfdb  pop     r13
0x18002bfdd  pop     r12
0x18002bfdf  pop     rdi
0x18002bfe0  pop     rsi
0x18002bfe1  pop     rbp
0x18002bfe2  retn
0x18002bfe3  mov     rcx, rbx; lpCriticalSection
0x18002bfe6  call    cs:__imp_LeaveCriticalSection
0x18002bfec  mov     eax, 8000FFFFh
0x18002bff1  jmp     short loc_18002BFB7
0x18002bff3  call    ?_Xlength@?$vector@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@CAXXZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(void)
0x18002bff9  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
