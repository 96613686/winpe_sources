# Trace::LevelSettings::Output(Trace::Level,char const *,char *)

- ea: `0x1801ccdf0`
- end: `0x1801cd2a0`
- name: `?Output@LevelSettings@Trace@@QEAAXW4Level@2@PEBDPEAD@Z`
- size: `1200`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801cd2a0`

## callees

- `0x180016430`
- `0x1800230b0`
- `0x1801cc220`
- `0x1801cc280`
- `0x1801cc9c0`
- `0x1801ccdf0`
- `0x1801d50f0`
- `0x18039e5b0`
- `0x18039eac0`
- `0x18039eb30`
- `0x18039ebb0`
- `0x18039ed40`
- `0x1803a0e96`
- `0x1803a0f8f`

## import_xrefs

- `KERNEL32!OutputDebugStringA` at `0x1801cd22a`
- `KERNEL32!OutputDebugStringA` at `0x1801cd22a`
- `KERNEL32!GetCurrentThreadId` at `0x1801cd018`
- `KERNEL32!GetCurrentThreadId` at `0x1801cd018`
- `KERNEL32!IsDebuggerPresent` at `0x1801cd237`
- `KERNEL32!IsDebuggerPresent` at `0x1801cd237`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnprintf_s` at `0x1801cce7f`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnprintf_s` at `0x1801cce7f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1801cd07f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1801cd0d2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1801cd1aa`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1801cd1f8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1801cd07f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1801cd0d2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1801cd1aa`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1801cd1f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Trace::LevelSettings::Output(int *a1, signed int a2, const char *a3, va_list a4)
{
  int v8; // r13d
  unsigned __int64 *v9; // rax
  __int64 v10; // r14
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 perf_frequency_0; // rbx
  __int64 perf_counter_0; // rax
  __int64 v15; // rbx
  __int64 v16; // r8
  _BYTE *v17; // rcx
  const char *v18; // rdx
  void *v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rdx
  void *v22; // rcx
  void *v23; // rcx
  int v24; // [rsp+40h] [rbp-C0h]
  int v25; // [rsp+44h] [rbp-BCh]
  void *v26[3]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v27; // [rsp+60h] [rbp-A0h]
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h]
  unsigned __int64 v30; // [rsp+80h] [rbp-80h]
  void *v31[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v32; // [rsp+98h] [rbp-68h]
  unsigned __int64 v33; // [rsp+A0h] [rbp-60h]
  void *v34[3]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v35; // [rsp+C0h] [rbp-40h]
  char v36[256]; // [rsp+D0h] [rbp-30h] BYREF
  CHAR OutputString[2112]; // [rsp+1D0h] [rbp+D0h] BYREF
  char Buffer[2048]; // [rsp+A10h] [rbp+910h] BYREF

  if ( dword_1807A14D4 <= 0 )
  {
    v24 = a1[2];
    v8 = a1[1];
    v25 = *a1;
    v9 = _local_stdio_printf_options();
    v10 = -1;
    __stdio_common_vsnprintf_s(*v9, Buffer, 0x800u, 0xFFFFFFFFFFFFFFFFuLL, a3, 0, a4);
    v11 = *((_QWORD *)a1 + 2);
    v26[0] = 0;
    v26[2] = 0;
    v27 = 15;
    v12 = -1;
    do
      ++v12;
    while ( *(_BYTE *)(v11 + v12) );
    std::string::assign(v26);
    perf_frequency_0 = Query_perf_frequency_0();
    perf_counter_0 = Query_perf_counter_0();
    if ( perf_frequency_0 == 10000000 )
      v15 = 100 * perf_counter_0;
    else
      v15 = 1000000000 * (perf_counter_0 % perf_frequency_0) / perf_frequency_0
          + 1000000000 * (perf_counter_0 / perf_frequency_0);
    if ( dword_1807A14E0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 44LL) )
    {
      Init_thread_header(&dword_1807A14E0);
      if ( dword_1807A14E0 == -1 )
      {
        qword_1807A14D8 = v15;
        Init_thread_footer(&dword_1807A14E0);
      }
    }
    sprintf_s<256>(v36, "%.3d:%.2d:%.2d:%.3d");
    Block = 0;
    v29 = 0;
    v30 = 15;
    v16 = -1;
    do
      ++v16;
    while ( v36[v16] );
    std::string::assign(&Block);
    GetCurrentThreadId();
    sprintf_s<2112>(OutputString, "[%s][%s][%s][0x%.8x] %s\n");
    if ( v30 >= 0x10 )
    {
      v17 = Block;
      if ( v30 + 1 >= 0x1000 )
      {
        v17 = (_BYTE *)*((_QWORD *)Block - 1);
        if ( (unsigned __int64)((_BYTE *)Block - v17 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v17);
    }
    v29 = 0;
    v30 = 15;
    LOBYTE(Block) = 0;
    v18 = (const char *)v27;
    if ( v27 >= 0x10 )
    {
      v19 = v26[0];
      if ( v27 + 1 >= 0x1000 )
      {
        v19 = (void *)*((_QWORD *)v26[0] - 1);
        if ( (unsigned __int64)((char *)v26[0] - (char *)v19 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v19);
    }
    v27 = 15;
    LOBYTE(v26[0]) = 0;
    if ( a2 >= v8 )
    {
      v34[0] = 0;
      v34[2] = 0;
      v35 = 15;
      v20 = -1;
      do
        ++v20;
      while ( OutputString[v20] );
      std::string::assign(v34);
      v21 = *((_QWORD *)a1 + 2);
      v31[0] = 0;
      v32 = 0;
      v33 = 15;
      do
        ++v10;
      while ( *(_BYTE *)(v21 + v10) );
      std::string::assign(v31);
      Trace::NotifyHandlers(v31, (unsigned int)a2, v34);
      if ( v33 >= 0x10 )
      {
        v22 = v31[0];
        if ( v33 + 1 >= 0x1000 )
        {
          v22 = (void *)*((_QWORD *)v31[0] - 1);
          if ( (unsigned __int64)((char *)v31[0] - (char *)v22 - 8) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
        operator delete(v22);
      }
      v32 = 0;
      v33 = 15;
      LOBYTE(v31[0]) = 0;
      v18 = (const char *)v35;
      if ( v35 >= 0x10 )
      {
        v23 = v34[0];
        if ( v35 + 1 >= 0x1000 )
        {
          v23 = (void *)*((_QWORD *)v34[0] - 1);
          if ( (unsigned __int64)((char *)v34[0] - (char *)v23 - 8) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
        operator delete(v23);
      }
      v35 = 15;
      LOBYTE(v34[0]) = 0;
    }
    if ( a2 >= v24 )
      Trace::PrintLogMessage((Trace *)OutputString, v18);
    OutputDebugStringA(OutputString);
    if ( a2 >= v25 )
    {
      if ( !IsDebuggerPresent() )
        __fastfail(7u);
      __debugbreak();
    }
  }
}

```

## disassembly

```asm
0x1801ccdf0  push    rbp
0x1801ccdf2  push    rbx
0x1801ccdf3  push    rsi
0x1801ccdf4  push    rdi
0x1801ccdf5  push    r12
0x1801ccdf7  push    r13
0x1801ccdf9  push    r14
0x1801ccdfb  push    r15
0x1801ccdfd  lea     rbp, [rsp-1128h]
0x1801cce05  mov     eax, 1228h
0x1801cce0a  call    _alloca_probe
0x1801cce0f  sub     rsp, rax
0x1801cce12  mov     rax, cs:__security_cookie
0x1801cce19  xor     rax, rsp
0x1801cce1c  mov     [rbp+1160h+var_50], rax
0x1801cce23  mov     rdi, r9
0x1801cce26  mov     rbx, r8
0x1801cce29  movsxd  r15, edx
0x1801cce2c  mov     r12, rcx
0x1801cce2f  mov     eax, cs:dword_1807A14D4
0x1801cce35  nop
0x1801cce36  test    eax, eax
0x1801cce38  jg      loc_1801CD24B
0x1801cce3e  mov     eax, [rcx+8]
0x1801cce41  mov     [rsp+1260h+var_1220], eax
0x1801cce45  mov     r13d, [rcx+4]
0x1801cce49  mov     eax, [rcx]
0x1801cce4b  mov     [rsp+1260h+var_121C], eax
0x1801cce4f  call    __local_stdio_printf_options
0x1801cce54  mov     [rsp+1260h+ArgList], rdi; ArgList
0x1801cce59  xor     edi, edi
0x1801cce5b  mov     [rsp+1260h+Locale], rdi; Locale
0x1801cce60  mov     [rsp+1260h+Format], rbx; Format
0x1801cce65  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1801cce6c  mov     r9, r14; MaxCount
0x1801cce6f  mov     r8d, 800h; BufferCount
0x1801cce75  lea     rdx, [rbp+1160h+Buffer]; Buffer
0x1801cce7c  mov     rcx, [rax]; Options
0x1801cce7f  call    cs:__imp___stdio_common_vsnprintf_s
0x1801cce85  mov     rdx, [r12+10h]
0x1801cce8a  mov     [rsp+1260h+var_1218], rdi
0x1801cce8f  mov     [rsp+1260h+var_1208], rdi
0x1801cce94  mov     [rsp+1260h+var_1200], 0Fh
0x1801cce9d  mov     byte ptr [rsp+1260h+var_1218], dil
0x1801ccea2  mov     r8, r14
0x1801ccea5  inc     r8
0x1801ccea8  cmp     [rdx+r8], dil
0x1801cceac  jnz     short loc_1801CCEA5
0x1801cceae  lea     rcx, [rsp+1260h+var_1218]; void *
0x1801cceb3  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1801cceb8  nop
0x1801cceb9  call    _Query_perf_frequency_0
0x1801ccebe  mov     rbx, rax
0x1801ccec1  call    _Query_perf_counter_0
0x1801ccec6  cmp     rbx, 989680h
0x1801ccecd  jnz     short loc_1801CCED5
0x1801ccecf  imul    rbx, rax, 64h ; 'd'
0x1801cced3  jmp     short loc_1801CCEF1
0x1801cced5  cqo
0x1801cced7  idiv    rbx
0x1801cceda  imul    rcx, rax, 3B9ACA00h
0x1801ccee1  imul    rax, rdx, 3B9ACA00h
0x1801ccee8  cqo
0x1801cceea  idiv    rbx
0x1801cceed  lea     rbx, [rax+rcx]
0x1801ccef1  mov     ecx, cs:_tls_index
0x1801ccef7  mov     rax, gs:58h
0x1801ccf00  mov     edx, 2Ch ; ','
0x1801ccf05  mov     rax, [rax+rcx*8]
0x1801ccf09  mov     ecx, [rdx+rax]
0x1801ccf0c  cmp     cs:dword_1807A14E0, ecx
0x1801ccf12  jg      loc_1801CD26E
0x1801ccf18  sub     rbx, cs:qword_1807A14D8
0x1801ccf1f  mov     rax, 431BDE82D7B634DBh
0x1801ccf29  imul    rbx
0x1801ccf2c  mov     r10, rdx
0x1801ccf2f  sar     r10, 12h
0x1801ccf33  mov     rax, r10
0x1801ccf36  shr     rax, 3Fh
0x1801ccf3a  add     r10, rax
0x1801ccf3d  mov     rax, 624DD2F1A9FBE77h
0x1801ccf47  mul     r10
0x1801ccf4a  mov     r9, r10
0x1801ccf4d  sub     r9, rdx
0x1801ccf50  shr     r9, 1
0x1801ccf53  add     r9, rdx
0x1801ccf56  shr     r9, 9
0x1801ccf5a  imul    rax, r9, 3E8h
0x1801ccf61  sub     r10, rax
0x1801ccf64  mov     r11, 8888888888888889h
0x1801ccf6e  mov     rax, r11
0x1801ccf71  mul     r9
0x1801ccf74  mov     r8, rdx
0x1801ccf77  shr     r8, 5
0x1801ccf7b  imul    rcx, r8, 3Ch ; '<'
0x1801ccf7f  sub     r9, rcx
0x1801ccf82  mov     rax, r11
0x1801ccf85  mul     r8
0x1801ccf88  shr     rdx, 5
0x1801ccf8c  imul    rax, rdx, 3Ch ; '<'
0x1801ccf90  sub     r8, rax
0x1801ccf93  mov     dword ptr [rsp+1260h+Locale], r10d
0x1801ccf98  mov     dword ptr [rsp+1260h+Format], r9d
0x1801ccf9d  mov     r9d, r8d
0x1801ccfa0  mov     r8d, edx
0x1801ccfa3  lea     rdx, a3d2d2d3d; "%.3d:%.2d:%.2d:%.3d"
0x1801ccfaa  lea     rcx, [rbp+1160h+var_1190]; Buffer
0x1801ccfae  call    ??$sprintf_s@$0BAA@@@YAHAEAY0BAA@DPEBDZZ; sprintf_s<256>(char (&)[256],char const *,...)
0x1801ccfb3  mov     [rsp+1260h+Block], rdi
0x1801ccfb8  mov     [rsp+1260h+var_11E8], rdi
0x1801ccfbd  mov     [rbp+1160h+var_11E0], 0Fh
0x1801ccfc5  lea     rax, [rbp+1160h+var_1190]
0x1801ccfc9  mov     r8, r14
0x1801ccfcc  nop     dword ptr [rax+00h]
0x1801ccfd0  inc     r8
0x1801ccfd3  cmp     byte ptr [rax+r8], 0
0x1801ccfd8  jnz     short loc_1801CCFD0
0x1801ccfda  lea     rdx, [rbp+1160h+var_1190]
0x1801ccfde  lea     rcx, [rsp+1260h+Block]; void *
0x1801ccfe3  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1801ccfe8  lea     rsi, [rsp+1260h+var_1218]
0x1801ccfed  cmp     [rsp+1260h+var_1200], 10h
0x1801ccff3  cmovnb  rsi, [rsp+1260h+var_1218]
0x1801ccff9  lea     rcx, [r15+r15*2]
0x1801ccffd  lea     rbx, off_180754860; "N"
0x1801cd004  mov     rbx, [rbx+rcx*8]
0x1801cd008  lea     rdi, [rsp+1260h+Block]
0x1801cd00d  cmp     [rbp+1160h+var_11E0], 10h
0x1801cd012  cmovnb  rdi, [rsp+1260h+Block]
0x1801cd018  call    cs:__imp_GetCurrentThreadId
0x1801cd01e  lea     rcx, [rbp+1160h+Buffer]
0x1801cd025  mov     [rsp+1260h+ArgList], rcx
0x1801cd02a  mov     dword ptr [rsp+1260h+Locale], eax
0x1801cd02e  mov     [rsp+1260h+Format], rsi
0x1801cd033  mov     r9, rbx
0x1801cd036  mov     r8, rdi
0x1801cd039  lea     rdx, aSSS0x8xS; "[%s][%s][%s][0x%.8x] %s\n"
0x1801cd040  lea     rcx, [rbp+1160h+OutputString]; Buffer
0x1801cd047  call    ??$sprintf_s@$0IEA@@@YAHAEAY0IEA@DPEBDZZ; sprintf_s<2112>(char (&)[2112],char const *,...)
0x1801cd04c  mov     rdx, [rbp+1160h+var_11E0]
0x1801cd050  cmp     rdx, 10h
0x1801cd054  jb      short loc_1801CD08B
0x1801cd056  inc     rdx
0x1801cd059  mov     rcx, [rsp+1260h+Block]; Block
0x1801cd05e  mov     rax, rcx
0x1801cd061  cmp     rdx, 1000h
0x1801cd068  jb      short loc_1801CD086
0x1801cd06a  add     rdx, 27h ; '''
0x1801cd06e  mov     rcx, [rcx-8]
0x1801cd072  sub     rax, rcx
0x1801cd075  add     rax, 0FFFFFFFFFFFFFFF8h
0x1801cd079  cmp     rax, 1Fh
0x1801cd07d  jbe     short loc_1801CD086
0x1801cd07f  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1801cd086  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801cd08b  xor     ebx, ebx
0x1801cd08d  mov     [rsp+1260h+var_11E8], rbx
0x1801cd092  mov     [rbp+1160h+var_11E0], 0Fh
0x1801cd09a  mov     byte ptr [rsp+1260h+Block], bl
0x1801cd09e  mov     rdx, [rsp+1260h+var_1200]
0x1801cd0a3  cmp     rdx, 10h
0x1801cd0a7  jb      short loc_1801CD0DE
0x1801cd0a9  inc     rdx
0x1801cd0ac  mov     rcx, [rsp+1260h+var_1218]; Block
0x1801cd0b1  mov     rax, rcx
0x1801cd0b4  cmp     rdx, 1000h
0x1801cd0bb  jb      short loc_1801CD0D9
0x1801cd0bd  add     rdx, 27h ; '''
0x1801cd0c1  mov     rcx, [rcx-8]
0x1801cd0c5  sub     rax, rcx
0x1801cd0c8  add     rax, 0FFFFFFFFFFFFFFF8h
0x1801cd0cc  cmp     rax, 1Fh
0x1801cd0d0  jbe     short loc_1801CD0D9
0x1801cd0d2  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1801cd0d9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801cd0de  mov     [rsp+1260h+var_1200], 0Fh
0x1801cd0e7  mov     byte ptr [rsp+1260h+var_1218], 0
0x1801cd0ec  cmp     r15d, r13d
0x1801cd0ef  jl      loc_1801CD210
0x1801cd0f5  mov     [rbp+1160h+var_11B8], rbx
0x1801cd0f9  mov     [rbp+1160h+var_11A8], rbx
0x1801cd0fd  mov     [rbp+1160h+var_11A0], 0Fh
0x1801cd105  mov     byte ptr [rbp+1160h+var_11B8], 0
0x1801cd109  lea     rax, [rbp+1160h+OutputString]
0x1801cd110  mov     r8, r14
0x1801cd113  inc     r8
0x1801cd116  cmp     byte ptr [rax+r8], 0
0x1801cd11b  jnz     short loc_1801CD113
0x1801cd11d  lea     rdx, [rbp+1160h+OutputString]
0x1801cd124  lea     rcx, [rbp+1160h+var_11B8]; void *
0x1801cd128  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1801cd12d  nop
0x1801cd12e  mov     rdx, [r12+10h]
0x1801cd133  mov     [rbp+1160h+var_11D8], rbx
0x1801cd137  mov     [rbp+1160h+var_11C8], rbx
0x1801cd13b  mov     [rbp+1160h+var_11C0], 0Fh
0x1801cd143  mov     byte ptr [rbp+1160h+var_11D8], 0
0x1801cd147  nop     word ptr [rax+rax+00000000h]
0x1801cd150  inc     r14
0x1801cd153  cmp     byte ptr [rdx+r14], 0
0x1801cd158  jnz     short loc_1801CD150
0x1801cd15a  mov     r8, r14
0x1801cd15d  lea     rcx, [rbp+1160h+var_11D8]; void *
0x1801cd161  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1801cd166  nop
0x1801cd167  lea     r8, [rbp+1160h+var_11B8]
0x1801cd16b  mov     edx, r15d
0x1801cd16e  lea     rcx, [rbp+1160h+var_11D8]
0x1801cd172  call    ?NotifyHandlers@Trace@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Level@1@0@Z; Trace::NotifyHandlers(std::string const &,Trace::Level,std::string const &)
0x1801cd177  nop
0x1801cd178  mov     rdx, [rbp+1160h+var_11C0]
0x1801cd17c  cmp     rdx, 10h
0x1801cd180  jb      short loc_1801CD1B6
0x1801cd182  inc     rdx
0x1801cd185  mov     rcx, [rbp+1160h+var_11D8]; Block
0x1801cd189  mov     rax, rcx
0x1801cd18c  cmp     rdx, 1000h
0x1801cd193  jb      short loc_1801CD1B1
0x1801cd195  add     rdx, 27h ; '''
0x1801cd199  mov     rcx, [rcx-8]
0x1801cd19d  sub     rax, rcx
0x1801cd1a0  add     rax, 0FFFFFFFFFFFFFFF8h
0x1801cd1a4  cmp     rax, 1Fh
0x1801cd1a8  jbe     short loc_1801CD1B1
0x1801cd1aa  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1801cd1b1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801cd1b6  mov     [rbp+1160h+var_11C8], rbx
0x1801cd1ba  mov     [rbp+1160h+var_11C0], 0Fh
0x1801cd1c2  mov     byte ptr [rbp+1160h+var_11D8], 0
0x1801cd1c6  mov     rdx, [rbp+1160h+var_11A0]
0x1801cd1ca  cmp     rdx, 10h
0x1801cd1ce  jb      short loc_1801CD204
0x1801cd1d0  inc     rdx
0x1801cd1d3  mov     rcx, [rbp+1160h+var_11B8]; Block
0x1801cd1d7  mov     rax, rcx
0x1801cd1da  cmp     rdx, 1000h
0x1801cd1e1  jb      short loc_1801CD1FF
0x1801cd1e3  add     rdx, 27h ; '''
0x1801cd1e7  mov     rcx, [rcx-8]
0x1801cd1eb  sub     rax, rcx
0x1801cd1ee  add     rax, 0FFFFFFFFFFFFFFF8h
0x1801cd1f2  cmp     rax, 1Fh
0x1801cd1f6  jbe     short loc_1801CD1FF
0x1801cd1f8  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1801cd1ff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801cd204  mov     [rbp+1160h+var_11A0], 0Fh
0x1801cd20c  mov     byte ptr [rbp+1160h+var_11B8], 0
0x1801cd210  cmp     r15d, [rsp+1260h+var_1220]
0x1801cd215  jl      short loc_1801CD223
0x1801cd217  lea     rcx, [rbp+1160h+OutputString]; this
0x1801cd21e  call    ?PrintLogMessage@Trace@@YAXPEBD@Z; Trace::PrintLogMessage(char const *)
0x1801cd223  lea     rcx, [rbp+1160h+OutputString]; lpOutputString
0x1801cd22a  call    cs:__imp_OutputDebugStringA
0x1801cd230  cmp     r15d, [rsp+1260h+var_121C]
0x1801cd235  jl      short loc_1801CD24B
0x1801cd237  call    cs:__imp_IsDebuggerPresent
0x1801cd23d  test    eax, eax
0x1801cd23f  jnz     short loc_1801CD24A
0x1801cd241  mov     ecx, 7
0x1801cd246  int     29h; Win8: RtlFailFast(ecx)
0x1801cd248  jmp     short loc_1801CD24B
0x1801cd24a  int     3; Trap to Debugger
0x1801cd24b  mov     rcx, [rbp+1160h+var_50]
0x1801cd252  xor     rcx, rsp; StackCookie
0x1801cd255  call    __security_check_cookie
0x1801cd25a  add     rsp, 1228h
0x1801cd261  pop     r15
0x1801cd263  pop     r14
0x1801cd265  pop     r13
0x1801cd267  pop     r12
0x1801cd269  pop     rdi
0x1801cd26a  pop     rsi
0x1801cd26b  pop     rbx
0x1801cd26c  pop     rbp
0x1801cd26d  retn
0x1801cd26e  lea     rcx, dword_1807A14E0
0x1801cd275  call    _Init_thread_header
0x1801cd27a  cmp     cs:dword_1807A14E0, 0FFFFFFFFh
0x1801cd281  jnz     loc_1801CCF18
0x1801cd287  mov     cs:qword_1807A14D8, rbx
0x1801cd28e  lea     rcx, dword_1807A14E0
0x1801cd295  call    _Init_thread_footer
0x1801cd29a  jmp     loc_1801CCF18
```
