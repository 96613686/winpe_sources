# CUpdateDeploymentJob::WaitForCallbackThreads(void)

- ea: `0x180032338`
- end: `0x180032624`
- name: `?WaitForCallbackThreads@CUpdateDeploymentJob@@AEAAJXZ`
- size: `748`
- prototype: `__int64 __fastcall(CUpdateDeploymentJob *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800291d0`
- `0x180031dcc`

## callees

- `0x180003180`
- `0x1800110fc`
- `0x180011b44`
- `0x180032338`
- `0x180037278`
- `0x180038258`
- `0x18003843c`
- `0x1800692e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032578`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800323cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800323cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003249a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003249a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180032546`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180032546`

## string_xrefs

- `0x180032503`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x1800325ab`: `Deployment job Id %ws : WaitForEnd update deployment wait failed`
- `0x1800324d1`: `Deployment job Id %ws : WaitForEnd for deployment job completed. Job state = %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUpdateDeploymentJob::WaitForCallbackThreads(const struct _GUID *this)
{
  const struct _GUID *v1; // rbx
  unsigned __int64 v2; // r13
  DWORD v3; // r14d
  struct _RTL_CRITICAL_SECTION *Data4; // rax
  char *v5; // r15
  _BYTE *v6; // r12
  signed int v7; // edi
  void *v8; // rcx
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // r15
  size_t v11; // rsi
  unsigned __int64 v12; // rbx
  const struct _GUID *v13; // rsi
  DWORD v14; // eax
  signed int LastError; // eax
  char *v17; // [rsp+48h] [rbp-59h]
  struct _GUID *v18; // [rsp+50h] [rbp-51h]
  void *v19[2]; // [rsp+58h] [rbp-49h] BYREF
  __int64 v20; // [rsp+68h] [rbp-39h]
  void *Src; // [rsp+70h] [rbp-31h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-29h]
  const struct _GUID *v23; // [rsp+80h] [rbp-21h]
  wchar_t v24[40]; // [rsp+88h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]

  v1 = this;
  v23 = this;
  v2 = 0;
  v3 = 0;
  *(_OWORD *)v19 = 0;
  v20 = 0;
  v18 = (struct _GUID *)&this[1];
  Trace::GuidToString::GuidToString(v24, this + 1);
  WUTrace(0, 0, 0x1000000, 4);
  Data4 = (struct _RTL_CRITICAL_SECTION *)v1[55].Data4;
  lpCriticalSection = (LPCRITICAL_SECTION)v1[55].Data4;
  v5 = 0;
  v17 = 0;
  v6 = 0;
  while ( 1 )
  {
    v7 = 0;
    EnterCriticalSection(Data4);
    v8 = *(void **)&v1[47].Data1;
    Src = v8;
    v9 = (__int64)(*(_QWORD *)v1[47].Data4 - (_QWORD)v8) >> 3;
    if ( v9 > (v20 - (__int64)v6) >> 3 )
    {
      std::vector<void *>::_Clear_and_reserve_geometric(v19, (__int64)(*(_QWORD *)v1[47].Data4 - (_QWORD)v8) >> 3);
      v6 = v19[0];
      memmove(v19[0], Src, 8 * v9);
      v5 = &v6[8 * v9];
LABEL_4:
      v17 = v5;
      goto LABEL_8;
    }
    v10 = (v5 - v6) >> 3;
    if ( v9 > v10 )
    {
      memmove(v6, v8, 8 * v10);
      v11 = 8 * (v9 - v10);
      memmove(v17, (char *)Src + 8 * v10, v11);
      v5 = &v17[v11];
      goto LABEL_4;
    }
    v5 = &v6[8 * v9];
    v17 = v5;
    memmove(v6, v8, 8 * v9);
LABEL_8:
    v19[1] = v5;
    v12 = (v5 - v6) >> 3;
    LeaveCriticalSection(lpCriticalSection);
    if ( !v12 )
      goto LABEL_9;
    while ( v3 < 0x40 && v2 < v12 )
    {
      ++v2;
      ++v3;
    }
    v14 = WaitForMultipleObjects(v3, (const HANDLE *)&v6[8 * (v2 - v3)], 1, 0x1F4u);
    if ( !v14 )
      goto LABEL_18;
    if ( v14 != 258 )
      break;
    v2 = 0;
LABEL_18:
    v3 = 0;
    if ( v2 >= v12 )
    {
LABEL_9:
      v13 = v18;
      goto LABEL_10;
    }
    v1 = v23;
    Data4 = lpCriticalSection;
  }
  if ( v14 == -1 )
  {
    LastError = GetLastError();
    v7 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v7 = LastError;
    if ( v7 >= 0 )
      v7 = -2147418113;
    v13 = v18;
    Trace::GuidToString::GuidToString(v24, v18);
  }
  else
  {
    v7 = -2145120257;
    v13 = v18;
    Trace::GuidToString::GuidToString(v24, v18);
  }
  WUTrace(0, 0, 0x1000000, 3);
LABEL_10:
  GetDeploymentJobStatusAsString(*(unsigned int *)v23[54].Data4);
  Trace::GuidToString::GuidToString(v24, v13);
  WUTrace(0, 0, 0x1000000, 4);
  if ( v7 >= 0 )
    v7 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10EC,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)v7,
      v7);
  std::vector<void *>::~vector<void *>(v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180032338  mov     rax, rsp
0x18003233b  mov     [rax+10h], rbx
0x18003233f  mov     [rax+18h], rsi
0x180032343  mov     [rax+20h], rdi
0x180032347  push    rbp
0x180032348  push    r12
0x18003234a  push    r13
0x18003234c  push    r14
0x18003234e  push    r15
0x180032350  lea     rbp, [rax-5Fh]
0x180032354  sub     rsp, 0D0h
0x18003235b  mov     rbx, rcx
0x18003235e  mov     [rbp+57h+var_78], rcx
0x180032362  xor     r13d, r13d
0x180032365  xor     r14d, r14d
0x180032368  xor     eax, eax
0x18003236a  xorps   xmm1, xmm1
0x18003236d  movdqu  xmmword ptr [rbp+57h+var_A0], xmm1
0x180032372  mov     [rbp+57h+var_90], rax
0x180032376  lea     rax, [rcx+10h]
0x18003237a  mov     [rbp+57h+var_A8], rax
0x18003237e  mov     rdx, rax; struct _GUID *
0x180032381  lea     rcx, [rbp+57h+var_70]; this
0x180032385  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18003238a  mov     [rsp+0F0h+var_C0], rax
0x18003238f  lea     rax, aDeploymentJobI_26; "Deployment job Id %ws : WaitForEnd invo"...
0x180032396  mov     [rsp+0F0h+var_C8], rax
0x18003239b  mov     qword ptr [rsp+0F0h+var_D0], r14
0x1800323a0  xor     edx, edx
0x1800323a2  xor     ecx, ecx
0x1800323a4  lea     r9d, [r13+4]
0x1800323a8  mov     r8d, 1000000h
0x1800323ae  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800323b3  lea     rax, [rbx+378h]
0x1800323ba  mov     [rbp+57h+lpCriticalSection], rax
0x1800323be  mov     r15, [rbp+57h+var_A0+8]
0x1800323c2  mov     [rbp+57h+var_B0], r15
0x1800323c6  mov     r12, [rbp+57h+var_A0]
0x1800323ca  xor     edi, edi
0x1800323cc  mov     rcx, rax; lpCriticalSection
0x1800323cf  call    cs:__imp_EnterCriticalSection
0x1800323d5  mov     rcx, [rbx+2F0h]
0x1800323dc  mov     [rbp+57h+Src], rcx
0x1800323e0  mov     rsi, [rbx+2F8h]
0x1800323e7  sub     rsi, rcx
0x1800323ea  sar     rsi, 3
0x1800323ee  mov     rax, [rbp+57h+var_90]
0x1800323f2  sub     rax, r12
0x1800323f5  sar     rax, 3
0x1800323f9  cmp     rsi, rax
0x1800323fc  jbe     short loc_18003242F
0x1800323fe  mov     rdx, rsi
0x180032401  lea     rcx, [rbp+57h+var_A0]
0x180032405  call    ?_Clear_and_reserve_geometric@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAX_K@Z; std::vector<void *>::_Clear_and_reserve_geometric(unsigned __int64)
0x18003240a  lea     rbx, ds:0[rsi*8]
0x180032412  mov     r8, rbx; Size
0x180032415  mov     rdx, [rbp+57h+Src]; Src
0x180032419  mov     r12, [rbp+57h+var_A0]
0x18003241d  mov     rcx, r12; void *
0x180032420  call    memmove
0x180032425  lea     r15, [rbx+r12]
0x180032429  mov     [rbp+57h+var_B0], r15
0x18003242d  jmp     short loc_180032488
0x18003242f  sub     r15, r12
0x180032432  sar     r15, 3
0x180032436  mov     rdx, rcx; Src
0x180032439  mov     rcx, r12; void *
0x18003243c  cmp     rsi, r15
0x18003243f  jbe     short loc_180032473
0x180032441  lea     rbx, ds:0[r15*8]
0x180032449  mov     r8, rbx; Size
0x18003244c  call    memmove
0x180032451  sub     rsi, r15
0x180032454  shl     rsi, 3
0x180032458  mov     rdx, [rbp+57h+Src]
0x18003245c  add     rdx, rbx; Src
0x18003245f  mov     r8, rsi; Size
0x180032462  mov     r15, [rbp+57h+var_B0]
0x180032466  mov     rcx, r15; void *
0x180032469  call    memmove
0x18003246e  add     r15, rsi
0x180032471  jmp     short loc_180032429
0x180032473  lea     r8, ds:0[rsi*8]; Size
0x18003247b  lea     r15, [r8+r12]
0x18003247f  mov     [rbp+57h+var_B0], r15
0x180032483  call    memmove
0x180032488  mov     [rbp+57h+var_A0+8], r15
0x18003248c  mov     rbx, r15
0x18003248f  sub     rbx, r12
0x180032492  sar     rbx, 3
0x180032496  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18003249a  call    cs:__imp_LeaveCriticalSection
0x1800324a0  test    rbx, rbx
0x1800324a3  jnz     short loc_180032524
0x1800324a5  mov     rsi, [rbp+57h+var_A8]
0x1800324a9  mov     rcx, [rbp+57h+var_78]
0x1800324ad  mov     ecx, [rcx+368h]
0x1800324b3  call    GetDeploymentJobStatusAsString
0x1800324b8  mov     rbx, rax
0x1800324bb  mov     rdx, rsi; struct _GUID *
0x1800324be  lea     rcx, [rbp+57h+var_70]; this
0x1800324c2  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800324c7  mov     [rsp+0F0h+var_B8], rbx
0x1800324cc  mov     [rsp+0F0h+var_C0], rax
0x1800324d1  lea     rax, aDeploymentJobI_33; "Deployment job Id %ws : WaitForEnd for "...
0x1800324d8  mov     [rsp+0F0h+var_C8], rax
0x1800324dd  mov     [rsp+0F0h+var_D0], edi; int
0x1800324e1  xor     edx, edx
0x1800324e3  xor     ecx, ecx
0x1800324e5  lea     r9d, [rdx+4]
0x1800324e9  mov     r8d, 1000000h
0x1800324ef  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800324f4  test    edi, edi
0x1800324f6  jns     loc_1800325F6
0x1800324fc  mov     rcx, [rbp+5Fh]; this
0x180032500  mov     r9d, edi; char *
0x180032503  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18003250a  mov     edx, 10ECh; void *
0x18003250f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032514  jmp     loc_1800325F8
0x180032519  cmp     r13, rbx
0x18003251c  jnb     short loc_18003252A
0x18003251e  inc     r13
0x180032521  inc     r14d
0x180032524  cmp     r14d, 40h ; '@'
0x180032528  jb      short loc_180032519
0x18003252a  mov     eax, r14d
0x18003252d  mov     rcx, r13
0x180032530  sub     rcx, rax
0x180032533  lea     rdx, [r12+rcx*8]; lpHandles
0x180032537  mov     r9d, 1F4h; dwMilliseconds
0x18003253d  mov     r8d, 1; bWaitAll
0x180032543  mov     ecx, r14d; nCount
0x180032546  call    cs:__imp_WaitForMultipleObjects
0x18003254c  test    eax, eax
0x18003254e  jz      short loc_18003255A
0x180032550  cmp     eax, 102h
0x180032555  jnz     short loc_180032573
0x180032557  xor     r13d, r13d
0x18003255a  xor     r14d, r14d
0x18003255d  cmp     r13, rbx
0x180032560  jnb     loc_1800324A5
0x180032566  mov     rbx, [rbp+57h+var_78]
0x18003256a  mov     rax, [rbp+57h+lpCriticalSection]
0x18003256e  jmp     loc_1800323CA
0x180032573  cmp     eax, 0FFFFFFFFh
0x180032576  jnz     short loc_1800325D3
0x180032578  call    cs:__imp_GetLastError
0x18003257e  movzx   edi, ax
0x180032581  or      edi, 80070000h
0x180032587  test    eax, eax
0x180032589  cmovle  edi, eax
0x18003258c  mov     eax, 8000FFFFh
0x180032591  test    edi, edi
0x180032593  cmovns  edi, eax
0x180032596  mov     rsi, [rbp+57h+var_A8]
0x18003259a  mov     rdx, rsi; struct _GUID *
0x18003259d  lea     rcx, [rbp+57h+var_70]; this
0x1800325a1  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800325a6  mov     [rsp+0F0h+var_C0], rax
0x1800325ab  lea     rax, aDeploymentJobI_40; "Deployment job Id %ws : WaitForEnd upda"...
0x1800325b2  mov     [rsp+0F0h+var_C8], rax
0x1800325b7  mov     [rsp+0F0h+var_D0], edi
0x1800325bb  xor     edx, edx
0x1800325bd  xor     ecx, ecx
0x1800325bf  lea     r9d, [rdx+3]
0x1800325c3  mov     r8d, 1000000h
0x1800325c9  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800325ce  jmp     loc_1800324A9
0x1800325d3  mov     edi, 80240FFFh
0x1800325d8  mov     rsi, [rbp+57h+var_A8]
0x1800325dc  mov     rdx, rsi; struct _GUID *
0x1800325df  lea     rcx, [rbp+57h+var_70]; this
0x1800325e3  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800325e8  mov     [rsp+0F0h+var_C0], rax
0x1800325ed  lea     rax, aDeploymentJobI_6; "Deployment job Id %ws : WaitForEnd enco"...
0x1800325f4  jmp     short loc_1800325B2
0x1800325f6  xor     edi, edi
0x1800325f8  lea     rcx, [rbp+57h+var_A0]
0x1800325fc  call    ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
0x180032601  mov     eax, edi
0x180032603  lea     r11, [rsp+0F0h+var_20]
0x18003260b  mov     rbx, [r11+38h]
0x18003260f  mov     rsi, [r11+40h]
0x180032613  mov     rdi, [r11+48h]
0x180032617  mov     rsp, r11
0x18003261a  pop     r15
0x18003261c  pop     r14
0x18003261e  pop     r13
0x180032620  pop     r12
0x180032622  pop     rbp
0x180032623  retn
```
