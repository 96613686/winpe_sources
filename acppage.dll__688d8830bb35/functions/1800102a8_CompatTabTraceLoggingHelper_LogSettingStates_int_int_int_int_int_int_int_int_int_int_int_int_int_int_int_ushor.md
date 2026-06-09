# CompatTabTraceLoggingHelper::LogSettingStates(int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,ushort const *,ushort const *,int,int,ushort const *,ushort const *,ushort const *)

- ea: `0x1800102a8`
- end: `0x18001056d`
- name: `?LogSettingStates@CompatTabTraceLoggingHelper@@YAXHHHHHHHHHHHHHHHPEBG0HH000@Z`
- size: `709`
- prototype: `void __fastcall(CompatTabTraceLoggingHelper *__hidden this, int, int, int, int, int, int, int, int, int, int, int, int, int, int, __int64, const unsigned __int16 *, const unsigned __int16 *, int, __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d14c`

## callees

- `0x180001008`
- `0x18000ffcc`
- `0x1800102a8`
- `0x1800136f4`
- `0x180016280`

## import_xrefs

- `AEPIC!PicFreeFileInfo` at `0x180010548`
- `AEPIC!PicFreeFileInfo` at `0x180010548`
- `AEPIC!PicRetrieveFileInfo` at `0x180010329`
- `AEPIC!PicRetrieveFileInfo` at `0x180010329`

## pseudocode

```c
void __fastcall CompatTabTraceLoggingHelper::LogSettingStates(
        CompatTabTraceLoggingHelper *this,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        int a14,
        int a15,
        __int64 a16,
        const unsigned __int16 *a17,
        const unsigned __int16 *a18,
        int a19,
        __int64 a20,
        const unsigned __int16 *a21,
        const unsigned __int16 *a22)
{
  int v25; // r15d
  __int64 v26; // rdx
  int v27; // r9d
  char *v28; // rcx
  int v29; // [rsp+E0h] [rbp-80h] BYREF
  int v30; // [rsp+E4h] [rbp-7Ch] BYREF
  int v31; // [rsp+E8h] [rbp-78h] BYREF
  int v32; // [rsp+ECh] [rbp-74h] BYREF
  int v33; // [rsp+F0h] [rbp-70h] BYREF
  int v34; // [rsp+F4h] [rbp-6Ch] BYREF
  int v35; // [rsp+F8h] [rbp-68h] BYREF
  int v36; // [rsp+FCh] [rbp-64h] BYREF
  int v37; // [rsp+100h] [rbp-60h] BYREF
  int v38; // [rsp+104h] [rbp-5Ch] BYREF
  int v39; // [rsp+108h] [rbp-58h] BYREF
  int v40; // [rsp+10Ch] [rbp-54h] BYREF
  int v41; // [rsp+110h] [rbp-50h] BYREF
  int v42; // [rsp+114h] [rbp-4Ch] BYREF
  int v43; // [rsp+118h] [rbp-48h] BYREF
  int v44; // [rsp+11Ch] [rbp-44h] BYREF
  int v45; // [rsp+120h] [rbp-40h] BYREF
  char **v46; // [rsp+128h] [rbp-38h] BYREF
  char *v47; // [rsp+130h] [rbp-30h] BYREF
  unsigned __int16 *v48; // [rsp+138h] [rbp-28h] BYREF
  const unsigned __int16 *v49; // [rsp+140h] [rbp-20h] BYREF
  __int64 v50; // [rsp+148h] [rbp-18h] BYREF
  const unsigned __int16 *v51; // [rsp+150h] [rbp-10h] BYREF
  __int64 v52; // [rsp+158h] [rbp-8h] BYREF
  unsigned __int16 v53[264]; // [rsp+160h] [rbp+0h] BYREF

  v46 = 0;
  v25 = (int)this;
  if ( !dword_180020D80 && (PiiFilter::Initialize(this), !dword_180020D80) || (int)PiiFilterExecute(v53) < 0 )
    v53[0] = 0;
  if ( (int)PicRetrieveFileInfo(a22, 0, &v46) < 0 || !v46 || (v28 = *v46) == 0 )
    v28 = byte_1800196B4;
  if ( (unsigned int)dword_180020098 > 5 )
  {
    v26 = qword_1800200B0;
    if ( (qword_1800200A8 & 0x400000000000LL) != 0 && (qword_1800200B0 & 0x400000000000LL) == qword_1800200B0 )
    {
      v47 = v28;
      v48 = v53;
      v49 = a21;
      v50 = a20;
      v29 = a19;
      v30 = (int)a18;
      v51 = a17;
      v52 = a16;
      v31 = a15;
      v32 = a14;
      v33 = a13;
      v34 = a12;
      v35 = a11;
      v37 = a9;
      v38 = a8;
      v39 = a7;
      v40 = a6;
      v41 = a5;
      v36 = 0;
      v42 = a4;
      v43 = a3;
      v44 = a2;
      v45 = v25;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v28,
        (unsigned int)byte_18001CC59,
        0,
        v27,
        (__int64)&v45,
        (__int64)&v44,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v52,
        (__int64)&v51,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v50,
        (__int64)&v49,
        (__int64)&v48,
        (__int64)&v47);
    }
  }
  if ( v46 )
    PicFreeFileInfo(v46, v26);
}

```

## disassembly

```asm
0x1800102a8  push    rbp
0x1800102aa  push    rbx
0x1800102ab  push    rsi
0x1800102ac  push    rdi
0x1800102ad  push    r14
0x1800102af  push    r15
0x1800102b1  lea     rbp, [rsp-228h]
0x1800102b9  sub     rsp, 388h
0x1800102c0  mov     rax, cs:__security_cookie
0x1800102c7  xor     rax, rsp
0x1800102ca  mov     [rbp+250h+var_40], rax
0x1800102d1  cmp     cs:dword_180020D80, 0
0x1800102d8  mov     edi, r9d
0x1800102db  mov     rbx, [rbp+250h+arg_A8]
0x1800102e2  mov     esi, r8d
0x1800102e5  mov     r14d, edx
0x1800102e8  mov     [rbp+250h+var_288], 0
0x1800102f0  mov     r15d, ecx
0x1800102f3  jnz     short loc_180010303
0x1800102f5  call    ?Initialize@PiiFilter@@QEAAJXZ; PiiFilter::Initialize(void)
0x1800102fa  cmp     cs:dword_180020D80, 0
0x180010301  jz      short loc_18001031A
0x180010303  mov     r8, cs:?TelemetryPiiFilter@CompatTabTraceLoggingHelper@@3VPiiFilter@@A; PiiFilter CompatTabTraceLoggingHelper::TelemetryPiiFilter
0x18001030a  lea     rcx, [rbp+250h+var_250]; unsigned __int16 *
0x18001030e  mov     r9, rbx
0x180010311  call    PiiFilterExecute
0x180010316  test    eax, eax
0x180010318  jns     short loc_180010320
0x18001031a  xor     eax, eax
0x18001031c  mov     [rbp+250h+var_250], ax
0x180010320  lea     r8, [rbp+250h+var_288]
0x180010324  xor     edx, edx
0x180010326  mov     rcx, rbx
0x180010329  call    cs:__imp_PicRetrieveFileInfo
0x18001032f  test    eax, eax
0x180010331  js      short loc_180010344
0x180010333  mov     rax, [rbp+250h+var_288]
0x180010337  test    rax, rax
0x18001033a  jz      short loc_180010344
0x18001033c  mov     rcx, [rax]
0x18001033f  test    rcx, rcx
0x180010342  jnz     short loc_18001034B
0x180010344  lea     rcx, byte_1800196B4
0x18001034b  mov     eax, cs:dword_180020098
0x180010351  cmp     eax, 5
0x180010354  jbe     loc_18001053F
0x18001035a  mov     rdx, cs:qword_1800200B0
0x180010361  mov     r8, 400000000000h
0x18001036b  mov     rax, cs:qword_1800200A8
0x180010372  test    r8, rax
0x180010375  jz      loc_18001053F
0x18001037b  mov     rax, rdx
0x18001037e  and     rax, r8
0x180010381  cmp     rax, rdx
0x180010384  jnz     loc_18001053F
0x18001038a  lea     rax, [rbp+250h+var_250]
0x18001038e  mov     [rbp+250h+var_280], rcx
0x180010392  mov     [rbp+250h+var_278], rax
0x180010396  mov     rax, [rbp+250h+arg_A0]
0x18001039d  mov     [rbp+250h+var_270], rax
0x1800103a1  mov     rax, [rbp+250h+arg_98]
0x1800103a8  mov     [rbp+250h+var_268], rax
0x1800103ac  mov     eax, [rbp+250h+arg_90]
0x1800103b2  mov     [rbp+250h+var_2D0], eax
0x1800103b5  mov     eax, dword ptr [rbp+250h+arg_88]
0x1800103bb  mov     [rbp+250h+var_2CC], eax
0x1800103be  mov     rax, [rbp+250h+arg_80]
0x1800103c5  mov     [rbp+250h+var_260], rax
0x1800103c9  mov     rax, [rbp+250h+arg_78]
0x1800103d0  mov     [rbp+250h+var_258], rax
0x1800103d4  mov     eax, [rbp+250h+arg_70]
0x1800103da  mov     [rbp+250h+var_2C8], eax
0x1800103dd  mov     eax, [rbp+250h+arg_68]
0x1800103e3  mov     [rbp+250h+var_2C4], eax
0x1800103e6  mov     eax, [rbp+250h+arg_60]
0x1800103ec  mov     [rbp+250h+var_2C0], eax
0x1800103ef  mov     eax, [rbp+250h+arg_58]
0x1800103f5  mov     [rbp+250h+var_2BC], eax
0x1800103f8  mov     eax, [rbp+250h+arg_50]
0x1800103fe  mov     [rbp+250h+var_2B8], eax
0x180010401  mov     eax, [rbp+250h+arg_40]
0x180010407  mov     [rbp+250h+var_2B0], eax
0x18001040a  mov     eax, [rbp+250h+arg_38]
0x180010410  mov     [rbp+250h+var_2AC], eax
0x180010413  mov     eax, [rbp+250h+arg_30]
0x180010419  mov     [rbp+250h+var_2A8], eax
0x18001041c  mov     eax, [rbp+250h+arg_28]
0x180010422  mov     [rbp+250h+var_2A4], eax
0x180010425  mov     eax, [rbp+250h+arg_20]
0x18001042b  mov     [rbp+250h+var_2A0], eax
0x18001042e  lea     rax, [rbp+250h+var_280]
0x180010432  mov     [rsp+3B0h+var_2E0], rax
0x18001043a  lea     rax, [rbp+250h+var_278]
0x18001043e  mov     [rsp+3B0h+var_2E8], rax
0x180010446  lea     rax, [rbp+250h+var_270]
0x18001044a  mov     [rsp+3B0h+var_2F0], rax
0x180010452  lea     rax, [rbp+250h+var_268]
0x180010456  mov     [rsp+3B0h+var_2F8], rax
0x18001045e  lea     rax, [rbp+250h+var_2D0]
0x180010462  mov     [rsp+3B0h+var_300], rax
0x18001046a  lea     rax, [rbp+250h+var_2CC]
0x18001046e  mov     [rsp+3B0h+var_308], rax
0x180010476  lea     rax, [rbp+250h+var_260]
0x18001047a  mov     [rsp+3B0h+var_310], rax
0x180010482  lea     rax, [rbp+250h+var_258]
0x180010486  mov     [rsp+3B0h+var_318], rax
0x18001048e  lea     rax, [rbp+250h+var_2C8]
0x180010492  mov     [rsp+3B0h+var_320], rax
0x18001049a  lea     rax, [rbp+250h+var_2C4]
0x18001049e  mov     [rsp+3B0h+var_328], rax
0x1800104a6  lea     rax, [rbp+250h+var_2C0]
0x1800104aa  mov     [rsp+3B0h+var_330], rax
0x1800104b2  lea     rax, [rbp+250h+var_2BC]
0x1800104b6  mov     [rsp+3B0h+var_338], rax
0x1800104bb  lea     rax, [rbp+250h+var_2B8]
0x1800104bf  mov     [rsp+3B0h+var_340], rax
0x1800104c4  lea     rax, [rbp+250h+var_2B4]
0x1800104c8  mov     [rsp+3B0h+var_348], rax
0x1800104cd  lea     rax, [rbp+250h+var_2B0]
0x1800104d1  mov     [rsp+3B0h+var_350], rax
0x1800104d6  lea     rax, [rbp+250h+var_2AC]
0x1800104da  mov     [rsp+3B0h+var_358], rax
0x1800104df  lea     rax, [rbp+250h+var_2A8]
0x1800104e3  mov     [rsp+3B0h+var_360], rax
0x1800104e8  lea     rax, [rbp+250h+var_2A4]
0x1800104ec  mov     [rsp+3B0h+var_368], rax
0x1800104f1  lea     rax, [rbp+250h+var_2A0]
0x1800104f5  mov     [rsp+3B0h+var_370], rax
0x1800104fa  lea     rax, [rbp+250h+var_29C]
0x1800104fe  mov     [rsp+3B0h+var_378], rax
0x180010503  lea     rax, [rbp+250h+var_298]
0x180010507  mov     [rbp+250h+var_2B4], 0
0x18001050e  mov     [rbp+250h+var_29C], edi
0x180010511  mov     [rbp+250h+var_298], esi
0x180010514  mov     [rbp+250h+var_294], r14d
0x180010518  mov     [rbp+250h+var_290], r15d
0x18001051c  mov     [rsp+3B0h+var_380], rax
0x180010521  lea     rdx, byte_18001CC59
0x180010528  lea     rax, [rbp+250h+var_294]
0x18001052c  mov     [rsp+3B0h+var_388], rax
0x180010531  lea     rax, [rbp+250h+var_290]
0x180010535  mov     [rsp+3B0h+var_390], rax
0x18001053a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U?$_tlgWrapSz@G@@U2@U1@U1@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33333333333333AEBU?$_tlgWrapSz@G@@4334444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001053f  mov     rcx, [rbp+250h+var_288]
0x180010543  test    rcx, rcx
0x180010546  jz      short loc_18001054E
0x180010548  call    cs:__imp_PicFreeFileInfo
0x18001054e  mov     rcx, [rbp+250h+var_40]
0x180010555  xor     rcx, rsp; StackCookie
0x180010558  call    __security_check_cookie
0x18001055d  add     rsp, 388h
0x180010564  pop     r15
0x180010566  pop     r14
0x180010568  pop     rdi
0x180010569  pop     rsi
0x18001056a  pop     rbx
0x18001056b  pop     rbp
0x18001056c  retn
```
