# gpm::TraceProvider::LogCreatePresentEventConsumer(ulong,gpm::TraceProvider::TrackingReason)

- ea: `0x1800125fc`
- end: `0x180012753`
- name: `?LogCreatePresentEventConsumer@TraceProvider@gpm@@SAXKW4TrackingReason@12@@Z`
- size: `343`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000c218`
- `0x18000df34`

## callees

- `0x1800018ac`
- `0x180002578`
- `0x180003ab0`
- `0x18000d778`
- `0x180011fe0`
- `0x180012004`
- `0x1800125fc`
- `0x180022dec`
- `0x180022e90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180012648`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180012648`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall gpm::TraceProvider::LogCreatePresentEventConsumer(DWORD a1, int a2)
{
  HANDLE v4; // rbx
  __int64 ProcessName; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  const char *v9; // rax
  int v10; // [rsp+50h] [rbp-59h] BYREF
  DWORD v11; // [rsp+54h] [rbp-55h] BYREF
  int v12; // [rsp+58h] [rbp-51h] BYREF
  const char *v13; // [rsp+60h] [rbp-49h] BYREF
  struct _GUID *v14; // [rsp+68h] [rbp-41h] BYREF
  __int64 v15; // [rsp+70h] [rbp-39h] BYREF
  HANDLE v16; // [rsp+78h] [rbp-31h] BYREF
  __int128 v17; // [rsp+80h] [rbp-29h] BYREF
  __m128i si128; // [rsp+90h] [rbp-19h]
  struct _GUID v19; // [rsp+A0h] [rbp-9h] BYREF
  _BYTE v20[32]; // [rsp+B0h] [rbp+7h] BYREF

  v19 = 0;
  v17 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v17) = 0;
  v4 = OpenProcess(0x1000u, 0, a1);
  v16 = v4;
  if ( (((unsigned __int64)v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    ProcessName = GetProcessName(v20, v4);
    std::string::operator=(&v17, ProcessName);
    std::string::_Tidy_deallocate((__int64)v20);
    GetProcessTelemetryAppSessionGuid(v4, &v19);
  }
  if ( (unsigned int)dword_180042048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180042048, 0x400000000000LL) )
  {
    v10 = a2;
    v9 = (const char *)&v17;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v9 = (const char *)v17;
    v13 = v9;
    v11 = a1;
    v14 = &v19;
    v12 = 1;
    v15 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v6,
      (__int64)word_180039EB2,
      v7,
      v8,
      (__int64)&v15,
      (__int64)&v12,
      (__int64 *)&v14,
      (__int64)&v11,
      &v13,
      (__int64)&v10);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
  std::string::_Tidy_deallocate((__int64)&v17);
}

```

## disassembly

```asm
0x1800125fc  push    rbp
0x1800125fe  push    rbx
0x1800125ff  push    rsi
0x180012600  push    rdi
0x180012601  lea     rbp, [rsp-3Fh]
0x180012606  sub     rsp, 0E8h
0x18001260d  mov     rax, cs:__security_cookie
0x180012614  xor     rax, rsp
0x180012617  mov     [rbp+57h+var_30], rax
0x18001261b  mov     esi, edx
0x18001261d  mov     edi, ecx
0x18001261f  xorps   xmm0, xmm0
0x180012622  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x180012626  xorps   xmm1, xmm1
0x180012629  movups  [rbp+57h+var_80], xmm1
0x18001262d  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180012635  movdqu  [rbp+57h+var_70], xmm0
0x18001263a  mov     byte ptr [rbp+57h+var_80], 0
0x18001263e  mov     r8d, ecx; dwProcessId
0x180012641  xor     edx, edx; bInheritHandle
0x180012643  mov     ecx, 1000h; dwDesiredAccess
0x180012648  call    cs:__imp_OpenProcess
0x18001264e  mov     rbx, rax
0x180012651  mov     [rbp+57h+var_88], rax
0x180012655  inc     rax
0x180012658  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001265e  jz      short loc_18001268D
0x180012660  mov     rdx, rbx
0x180012663  lea     rcx, [rbp+57h+var_50]
0x180012667  call    ?GetProcessName@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@Z; GetProcessName(void *)
0x18001266c  mov     rdx, rax
0x18001266f  lea     rcx, [rbp+57h+var_80]
0x180012673  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180012678  lea     rcx, [rbp+57h+var_50]
0x18001267c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180012681  lea     rdx, [rbp+57h+var_60]; struct _GUID *
0x180012685  mov     rcx, rbx; ProcessHandle
0x180012688  call    ?GetProcessTelemetryAppSessionGuid@@YAJPEAXPEAU_GUID@@@Z; GetProcessTelemetryAppSessionGuid(void *,_GUID *)
0x18001268d  mov     eax, cs:dword_180042048
0x180012693  cmp     eax, 5
0x180012696  jbe     loc_180012728
0x18001269c  mov     rdx, 400000000000h
0x1800126a6  lea     rcx, dword_180042048
0x1800126ad  call    _tlgKeywordOn
0x1800126b2  test    al, al
0x1800126b4  jz      short loc_180012728
0x1800126b6  mov     [rbp+57h+var_B0], esi
0x1800126b9  lea     rax, [rbp+57h+var_80]
0x1800126bd  cmp     qword ptr [rbp+57h+var_70+8], 0Fh
0x1800126c2  cmova   rax, qword ptr [rbp+57h+var_80]
0x1800126c7  mov     [rbp+57h+var_A0], rax
0x1800126cb  mov     [rbp+57h+var_AC], edi
0x1800126ce  lea     rax, [rbp+57h+var_60]
0x1800126d2  mov     [rbp+57h+var_98], rax
0x1800126d6  mov     [rbp+57h+var_A8], 1
0x1800126dd  mov     [rbp+57h+var_90], 1000000h
0x1800126e5  lea     rax, [rbp+57h+var_B0]
0x1800126e9  mov     [rsp+100h+var_B8], rax
0x1800126ee  lea     rax, [rbp+57h+var_A0]
0x1800126f2  mov     [rsp+100h+var_C0], rax
0x1800126f7  lea     rax, [rbp+57h+var_AC]
0x1800126fb  mov     [rsp+100h+var_C8], rax
0x180012700  lea     rax, [rbp+57h+var_98]
0x180012704  mov     [rsp+100h+var_D0], rax
0x180012709  lea     rax, [rbp+57h+var_A8]
0x18001270d  mov     [rsp+100h+var_D8], rax
0x180012712  lea     rax, [rbp+57h+var_90]
0x180012716  mov     [rsp+100h+var_E0], rax
0x18001271b  lea     rdx, word_180039EB2
0x180012722  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180012727  nop
0x180012728  lea     rcx, [rbp+57h+var_88]
0x18001272c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180012731  nop
0x180012732  lea     rcx, [rbp+57h+var_80]
0x180012736  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001273b  mov     rcx, [rbp+57h+var_30]
0x18001273f  xor     rcx, rsp; StackCookie
0x180012742  call    __security_check_cookie
0x180012747  add     rsp, 0E8h
0x18001274e  pop     rdi
0x18001274f  pop     rsi
0x180012750  pop     rbx
0x180012751  pop     rbp
0x180012752  retn
```
