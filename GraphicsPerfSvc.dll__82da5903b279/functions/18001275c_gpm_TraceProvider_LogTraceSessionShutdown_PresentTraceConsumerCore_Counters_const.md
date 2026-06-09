# gpm::TraceProvider::LogTraceSessionShutdown(PresentTraceConsumerCore::Counters const &)

- ea: `0x18001275c`
- end: `0x180012af4`
- name: `?LogTraceSessionShutdown@TraceProvider@gpm@@SAXAEBUCounters@PresentTraceConsumerCore@@@Z`
- size: `920`
- prototype: `void __fastcall(const struct Counters *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180011f90`

## callees

- `0x1800018ac`
- `0x180001d8c`
- `0x180003ab0`
- `0x1800047f0`
- `0x180010f1c`
- `0x18001275c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001279b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001279b`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1800127ac`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1800127ac`

## string_xrefs

- `0x1800127bd`: `onecoreuap\windows\directx\dxg\gpm\service\traceprovider.cpp`

## pseudocode

```c
void __fastcall gpm::TraceProvider::LogTraceSessionShutdown(const struct Counters *a1)
{
  HANDLE CurrentProcess; // rax
  const char *v3; // r9
  int v4; // r8d
  int v5; // r9d
  __int64 i; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  const char *v10; // rax
  int v11; // [rsp+150h] [rbp-80h] BYREF
  int v12; // [rsp+154h] [rbp-7Ch] BYREF
  int v13; // [rsp+158h] [rbp-78h] BYREF
  int v14; // [rsp+15Ch] [rbp-74h] BYREF
  int v15; // [rsp+160h] [rbp-70h] BYREF
  int v16; // [rsp+164h] [rbp-6Ch] BYREF
  int v17; // [rsp+168h] [rbp-68h] BYREF
  DWORD PageFaultCount; // [rsp+16Ch] [rbp-64h] BYREF
  int v19; // [rsp+170h] [rbp-60h] BYREF
  int v20; // [rsp+174h] [rbp-5Ch] BYREF
  int v21; // [rsp+178h] [rbp-58h] BYREF
  int v22; // [rsp+17Ch] [rbp-54h] BYREF
  int v23; // [rsp+180h] [rbp-50h] BYREF
  int v24; // [rsp+184h] [rbp-4Ch] BYREF
  int v25; // [rsp+188h] [rbp-48h] BYREF
  int v26; // [rsp+18Ch] [rbp-44h] BYREF
  int v27; // [rsp+190h] [rbp-40h] BYREF
  int v28; // [rsp+194h] [rbp-3Ch] BYREF
  int v29; // [rsp+198h] [rbp-38h] BYREF
  int v30; // [rsp+19Ch] [rbp-34h] BYREF
  int v31; // [rsp+1A0h] [rbp-30h] BYREF
  int v32; // [rsp+1A4h] [rbp-2Ch] BYREF
  int v33; // [rsp+1A8h] [rbp-28h] BYREF
  int v34; // [rsp+1ACh] [rbp-24h] BYREF
  int v35; // [rsp+1B0h] [rbp-20h] BYREF
  int v36; // [rsp+1B4h] [rbp-1Ch] BYREF
  SIZE_T WorkingSetSize; // [rsp+1B8h] [rbp-18h] BYREF
  SIZE_T PeakWorkingSetSize; // [rsp+1C0h] [rbp-10h] BYREF
  SIZE_T PeakPagefileUsage; // [rsp+1C8h] [rbp-8h] BYREF
  __int64 v40; // [rsp+1D0h] [rbp+0h] BYREF
  __int64 v41; // [rsp+1D8h] [rbp+8h] BYREF
  const char *v42; // [rsp+1E0h] [rbp+10h] BYREF
  __int64 v43; // [rsp+1E8h] [rbp+18h] BYREF
  __int64 v44; // [rsp+1F0h] [rbp+20h] BYREF
  __int64 v45; // [rsp+1F8h] [rbp+28h] BYREF
  __int64 v46; // [rsp+200h] [rbp+30h] BYREF
  __int64 v47; // [rsp+208h] [rbp+38h] BYREF
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+210h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+A8h]

  memset_0(&ppsmemCounters, 0, 0x50u);
  ppsmemCounters.cb = 80;
  CurrentProcess = GetCurrentProcess();
  if ( !K32GetProcessMemoryInfo(CurrentProcess, &ppsmemCounters, ppsmemCounters.cb) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\service\\traceprovider.cpp",
      v3);
  v4 = 0;
  v5 = 0;
  for ( i = 0; i != 5; ++i )
  {
    v4 += *((_DWORD *)a1 + i);
    v5 += *((_DWORD *)a1 + i + 5);
  }
  if ( (unsigned int)dword_180042048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180042048, 0x400000000000LL) )
  {
    v11 = *((_DWORD *)a1 + 24);
    v12 = *((_DWORD *)a1 + 25);
    v13 = *((_DWORD *)a1 + 53);
    v14 = *((_DWORD *)a1 + 49);
    v15 = *((_DWORD *)a1 + 52);
    v16 = *((_DWORD *)a1 + 51);
    v17 = *((_DWORD *)a1 + 50);
    WorkingSetSize = ppsmemCounters.WorkingSetSize;
    PeakWorkingSetSize = ppsmemCounters.PeakWorkingSetSize;
    PeakPagefileUsage = ppsmemCounters.PeakPagefileUsage;
    PageFaultCount = ppsmemCounters.PageFaultCount;
    v19 = *((_DWORD *)a1 + 48);
    v40 = (__int64)a1 + 176;
    v41 = *((_QWORD *)a1 + 17);
    v10 = (char *)a1 + 144;
    if ( *((_QWORD *)a1 + 21) > 0xFu )
      v10 = *(const char **)v10;
    v42 = v10;
    v43 = *((_QWORD *)a1 + 14);
    v44 = *((_QWORD *)a1 + 13);
    v45 = *((_QWORD *)a1 + 16);
    v46 = *((_QWORD *)a1 + 15);
    v20 = *((_DWORD *)a1 + 6);
    v21 = *((_DWORD *)a1 + 1);
    v22 = *((_DWORD *)a1 + 23);
    v23 = *((_DWORD *)a1 + 22);
    v24 = *((_DWORD *)a1 + 21);
    v25 = *((_DWORD *)a1 + 20);
    v26 = *((_DWORD *)a1 + 18);
    v27 = *((_DWORD *)a1 + 17);
    v30 = *((_DWORD *)a1 + 15);
    v31 = *((_DWORD *)a1 + 13);
    v32 = *((_DWORD *)a1 + 10);
    v33 = *((_DWORD *)a1 + 7);
    v34 = *((_DWORD *)a1 + 2);
    v28 = v9;
    v29 = v8;
    v35 = 9;
    v36 = 1;
    v47 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v7,
      (__int64)byte_18003A39D,
      v8,
      v9,
      (__int64)&v47,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v46,
      (__int64)&v45,
      (__int64)&v44,
      (__int64)&v43,
      &v42,
      (__int64)&v41,
      &v40,
      (__int64)&v19,
      (__int64)&PageFaultCount,
      (__int64)&PeakPagefileUsage,
      (__int64)&PeakWorkingSetSize,
      (__int64)&WorkingSetSize,
      (__int64)&v17,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v11);
  }
}

```

## disassembly

```asm
0x18001275c  mov     [rsp-8+arg_0], rbx
0x180012761  push    rbp
0x180012762  lea     rbp, [rsp-0A0h]
0x18001276a  sub     rsp, 270h
0x180012771  mov     rax, cs:__security_cookie
0x180012778  xor     rax, rsp
0x18001277b  mov     [rbp+0A0h+var_10], rax
0x180012782  xor     edx, edx; Val
0x180012784  mov     rbx, rcx
0x180012787  lea     rcx, [rbp+0A0h+ppsmemCounters]; void *
0x18001278b  lea     r8d, [rdx+50h]; Size
0x18001278f  call    memset_0
0x180012794  mov     [rbp+0A0h+ppsmemCounters.cb], 50h ; 'P'
0x18001279b  call    cs:__imp_GetCurrentProcess
0x1800127a1  mov     r8d, [rbp+0A0h+ppsmemCounters.cb]; cb
0x1800127a5  lea     rdx, [rbp+0A0h+ppsmemCounters]; ppsmemCounters
0x1800127a9  mov     rcx, rax; Process
0x1800127ac  call    cs:__imp_K32GetProcessMemoryInfo
0x1800127b2  test    eax, eax
0x1800127b4  jnz     short loc_1800127CC
0x1800127b6  mov     rcx, [rbp+0A8h]; this
0x1800127bd  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x1800127c4  lea     edx, [rax+40h]; void *
0x1800127c7  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800127cc  xor     r8d, r8d
0x1800127cf  xor     r9d, r9d
0x1800127d2  xor     eax, eax
0x1800127d4  add     r8d, [rbx+rax*4]
0x1800127d8  add     r9d, [rbx+rax*4+14h]
0x1800127dd  inc     rax
0x1800127e0  cmp     rax, 5
0x1800127e4  jnz     short loc_1800127D4
0x1800127e6  mov     eax, cs:dword_180042048
0x1800127ec  cmp     eax, 5
0x1800127ef  jbe     loc_180012AD4
0x1800127f5  mov     rdx, 400000000000h
0x1800127ff  lea     rcx, dword_180042048
0x180012806  call    _tlgKeywordOn
0x18001280b  test    al, al
0x18001280d  jz      loc_180012AD4
0x180012813  mov     eax, [rbx+60h]
0x180012816  mov     [rbp+0A0h+var_120], eax
0x180012819  mov     eax, [rbx+64h]
0x18001281c  mov     [rbp+0A0h+var_11C], eax
0x18001281f  mov     eax, [rbx+0D4h]
0x180012825  mov     [rbp+0A0h+var_118], eax
0x180012828  mov     eax, [rbx+0C4h]
0x18001282e  mov     [rbp+0A0h+var_114], eax
0x180012831  mov     eax, [rbx+0D0h]
0x180012837  mov     [rbp+0A0h+var_110], eax
0x18001283a  mov     eax, [rbx+0CCh]
0x180012840  mov     [rbp+0A0h+var_10C], eax
0x180012843  mov     eax, [rbx+0C8h]
0x180012849  mov     [rbp+0A0h+var_108], eax
0x18001284c  mov     rax, [rbp+0A0h+ppsmemCounters.WorkingSetSize]
0x180012850  mov     [rbp+0A0h+var_B8], rax
0x180012854  mov     rax, [rbp+0A0h+ppsmemCounters.PeakWorkingSetSize]
0x180012858  mov     [rbp+0A0h+var_B0], rax
0x18001285c  mov     rax, [rbp+0A0h+ppsmemCounters.PeakPagefileUsage]
0x180012863  mov     [rbp+0A0h+var_A8], rax
0x180012867  mov     eax, [rbp+0A0h+ppsmemCounters.PageFaultCount]
0x18001286a  mov     [rbp+0A0h+var_104], eax
0x18001286d  mov     eax, [rbx+0C0h]
0x180012873  mov     [rbp+0A0h+var_100], eax
0x180012876  lea     rax, [rbx+0B0h]
0x18001287d  mov     [rbp+0A0h+var_A0], rax
0x180012881  mov     rax, [rbx+88h]
0x180012888  mov     [rbp+0A0h+var_98], rax
0x18001288c  lea     rax, [rbx+90h]
0x180012893  cmp     qword ptr [rax+18h], 0Fh
0x180012898  jbe     short loc_18001289D
0x18001289a  mov     rax, [rax]
0x18001289d  mov     [rbp+0A0h+var_90], rax
0x1800128a1  mov     rax, [rbx+70h]
0x1800128a5  mov     [rbp+0A0h+var_88], rax
0x1800128a9  mov     rax, [rbx+68h]
0x1800128ad  mov     [rbp+0A0h+var_80], rax
0x1800128b1  mov     rax, [rbx+80h]
0x1800128b8  mov     [rbp+0A0h+var_78], rax
0x1800128bc  mov     rax, [rbx+78h]
0x1800128c0  mov     [rbp+0A0h+var_70], rax
0x1800128c4  mov     eax, [rbx+18h]
0x1800128c7  mov     [rbp+0A0h+var_FC], eax
0x1800128ca  mov     eax, [rbx+4]
0x1800128cd  mov     [rbp+0A0h+var_F8], eax
0x1800128d0  mov     eax, [rbx+5Ch]
0x1800128d3  mov     [rbp+0A0h+var_F4], eax
0x1800128d6  mov     eax, [rbx+58h]
0x1800128d9  mov     [rbp+0A0h+var_F0], eax
0x1800128dc  mov     eax, [rbx+54h]
0x1800128df  mov     [rbp+0A0h+var_EC], eax
0x1800128e2  mov     eax, [rbx+50h]
0x1800128e5  mov     [rbp+0A0h+var_E8], eax
0x1800128e8  mov     eax, [rbx+48h]
0x1800128eb  mov     [rbp+0A0h+var_E4], eax
0x1800128ee  mov     eax, [rbx+44h]
0x1800128f1  mov     [rbp+0A0h+var_E0], eax
0x1800128f4  mov     eax, [rbx+3Ch]
0x1800128f7  mov     [rbp+0A0h+var_D4], eax
0x1800128fa  mov     eax, [rbx+34h]
0x1800128fd  mov     [rbp+0A0h+var_D0], eax
0x180012900  mov     eax, [rbx+28h]
0x180012903  mov     [rbp+0A0h+var_CC], eax
0x180012906  mov     eax, [rbx+1Ch]
0x180012909  mov     [rbp+0A0h+var_C8], eax
0x18001290c  mov     eax, [rbx+8]
0x18001290f  mov     [rbp+0A0h+var_C4], eax
0x180012912  lea     rax, [rbp+0A0h+var_120]
0x180012916  mov     [rsp+270h+var_130], rax
0x18001291e  lea     rax, [rbp+0A0h+var_11C]
0x180012922  mov     [rsp+270h+var_138], rax
0x18001292a  lea     rax, [rbp+0A0h+var_118]
0x18001292e  mov     [rsp+270h+var_140], rax
0x180012936  lea     rax, [rbp+0A0h+var_114]
0x18001293a  mov     [rsp+270h+var_148], rax
0x180012942  lea     rax, [rbp+0A0h+var_110]
0x180012946  mov     [rsp+270h+var_150], rax
0x18001294e  lea     rax, [rbp+0A0h+var_10C]
0x180012952  mov     [rsp+270h+var_158], rax
0x18001295a  lea     rax, [rbp+0A0h+var_108]
0x18001295e  mov     [rsp+270h+var_160], rax
0x180012966  lea     rax, [rbp+0A0h+var_B8]
0x18001296a  mov     [rsp+270h+var_168], rax
0x180012972  lea     rax, [rbp+0A0h+var_B0]
0x180012976  mov     [rsp+270h+var_170], rax
0x18001297e  lea     rax, [rbp+0A0h+var_A8]
0x180012982  mov     [rsp+270h+var_178], rax
0x18001298a  lea     rax, [rbp+0A0h+var_104]
0x18001298e  mov     [rsp+270h+var_180], rax
0x180012996  lea     rax, [rbp+0A0h+var_100]
0x18001299a  mov     [rsp+270h+var_188], rax
0x1800129a2  lea     rax, [rbp+0A0h+var_A0]
0x1800129a6  mov     [rsp+270h+var_190], rax
0x1800129ae  lea     rax, [rbp+0A0h+var_98]
0x1800129b2  mov     [rsp+270h+var_198], rax
0x1800129ba  lea     rax, [rbp+0A0h+var_90]
0x1800129be  mov     [rsp+270h+var_1A0], rax
0x1800129c6  lea     rax, [rbp+0A0h+var_88]
0x1800129ca  mov     [rsp+270h+var_1A8], rax
0x1800129d2  lea     rax, [rbp+0A0h+var_80]
0x1800129d6  mov     [rsp+270h+var_1B0], rax
0x1800129de  lea     rax, [rbp+0A0h+var_78]
0x1800129e2  mov     [rsp+270h+var_1B8], rax
0x1800129ea  lea     rax, [rbp+0A0h+var_70]
0x1800129ee  mov     [rsp+270h+var_1C0], rax
0x1800129f6  lea     rax, [rbp+0A0h+var_FC]
0x1800129fa  mov     [rsp+270h+var_1C8], rax
0x180012a02  lea     rax, [rbp+0A0h+var_F8]
0x180012a06  mov     [rbp+0A0h+var_DC], r9d
0x180012a0a  mov     [rbp+0A0h+var_D8], r8d
0x180012a0e  mov     [rbp+0A0h+var_C0], 9
0x180012a15  mov     [rbp+0A0h+var_BC], 1
0x180012a1c  mov     [rbp+0A0h+var_68], 1000000h
0x180012a24  mov     [rsp+270h+var_1D0], rax
0x180012a2c  lea     rdx, byte_18003A39D
0x180012a33  lea     rax, [rbp+0A0h+var_F4]
0x180012a37  mov     [rsp+270h+var_1D8], rax
0x180012a3f  lea     rax, [rbp+0A0h+var_F0]
0x180012a43  mov     [rsp+270h+var_1E0], rax
0x180012a4b  lea     rax, [rbp+0A0h+var_EC]
0x180012a4f  mov     [rsp+270h+var_1E8], rax
0x180012a57  lea     rax, [rbp+0A0h+var_E8]
0x180012a5b  mov     [rsp+270h+var_1F0], rax
0x180012a63  lea     rax, [rbp+0A0h+var_E4]
0x180012a67  mov     [rsp+270h+var_1F8], rax
0x180012a6c  lea     rax, [rbp+0A0h+var_E0]
0x180012a70  mov     [rsp+270h+var_200], rax
0x180012a75  lea     rax, [rbp+0A0h+var_DC]
0x180012a79  mov     [rsp+270h+var_208], rax
0x180012a7e  lea     rax, [rbp+0A0h+var_D8]
0x180012a82  mov     [rsp+270h+var_210], rax
0x180012a87  lea     rax, [rbp+0A0h+var_D4]
0x180012a8b  mov     [rsp+270h+var_218], rax
0x180012a90  lea     rax, [rbp+0A0h+var_D0]
0x180012a94  mov     [rsp+270h+var_220], rax
0x180012a99  lea     rax, [rbp+0A0h+var_CC]
0x180012a9d  mov     [rsp+270h+var_228], rax
0x180012aa2  lea     rax, [rbp+0A0h+var_C8]
0x180012aa6  mov     [rsp+270h+var_230], rax
0x180012aab  lea     rax, [rbp+0A0h+var_C4]
0x180012aaf  mov     [rsp+270h+var_238], rax
0x180012ab4  lea     rax, [rbp+0A0h+var_C0]
0x180012ab8  mov     [rsp+270h+var_240], rax
0x180012abd  lea     rax, [rbp+0A0h+var_BC]
0x180012ac1  mov     [rsp+270h+var_248], rax
0x180012ac6  lea     rax, [rbp+0A0h+var_68]
0x180012aca  mov     [rsp+270h+var_250], rax
0x180012acf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U1@U1@U1@U1@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U2@U2@U1@U1@U1@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44444444444444443333AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@443334444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180012ad4  mov     rcx, [rbp+0A0h+var_10]
0x180012adb  xor     rcx, rsp; StackCookie
0x180012ade  call    __security_check_cookie
0x180012ae3  mov     rbx, [rsp+270h+arg_0]
0x180012aeb  add     rsp, 270h
0x180012af2  pop     rbp
0x180012af3  retn
```
