# CGuestAudioClient::Initialize(_AUDCLNT_SHAREMODE,ulong,__int64,__int64,tWAVEFORMATEX const *,_GUID const *)

- ea: `0x1800b0080`
- end: `0x1800b0468`
- name: `?Initialize@CGuestAudioClient@@UEAAJW4_AUDCLNT_SHAREMODE@@K_J1PEBUtWAVEFORMATEX@@PEBU_GUID@@@Z`
- size: `1000`
- prototype: `__int64 __fastcall(CGuestAudioClient *__hidden this, enum _AUDCLNT_SHAREMODE, unsigned int, __int64, __int64, const struct tWAVEFORMATEX *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000cd10`
- `0x180010a90`
- `0x18004d8a8`
- `0x18004e2a8`
- `0x180087e80`
- `0x180088ce8`
- `0x18008ac99`
- `0x1800931a8`
- `0x1800a42bc`
- `0x1800ab230`
- `0x1800ace2c`
- `0x1800b0080`
- `0x18011ddd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0234`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0234`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b02dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b043d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b02dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b043d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b02cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b042f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b02cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b042f`

## pseudocode

```c
__int64 __fastcall CGuestAudioClient::Initialize(
        CGuestAudioClient *this,
        enum _AUDCLNT_SHAREMODE a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        struct tWAVEFORMATEX *a6,
        const struct _GUID *a7)
{
  int v11; // eax
  int v12; // ebx
  GUID v14; // xmm0
  __int64 v15; // rdx
  void *v16; // rcx
  __int64 v17; // rdx
  _OWORD *v18; // rcx
  _OWORD *v19; // rax
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int64 v32; // rax
  void *v33; // rcx
  int v34; // [rsp+20h] [rbp-E0h]
  int *v35; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  int v37[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct tWAVEFORMATEX *v38; // [rsp+60h] [rbp-A0h]
  LPVOID *p_pv; // [rsp+68h] [rbp-98h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  char v41; // [rsp+78h] [rbp-88h]
  _BYTE v42[1344]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD Src[2]; // [rsp+5C0h] [rbp+4C0h] BYREF
  __int64 v44; // [rsp+5C8h] [rbp+4C8h]
  __int64 v45; // [rsp+5D0h] [rbp+4D0h]
  _OWORD v46[2]; // [rsp+5D8h] [rbp+4D8h] BYREF
  __int64 v47; // [rsp+5F8h] [rbp+4F8h]
  __int128 v48; // [rsp+600h] [rbp+500h]
  __int128 v49; // [rsp+610h] [rbp+510h]
  GUID v50; // [rsp+620h] [rbp+520h]
  __int128 v51; // [rsp+630h] [rbp+530h]
  int v52; // [rsp+640h] [rbp+540h]
  __int64 v53; // [rsp+644h] [rbp+544h]
  __int64 v54; // [rsp+64Ch] [rbp+54Ch]
  int v55; // [rsp+654h] [rbp+554h]
  _BYTE v56[288]; // [rsp+658h] [rbp+558h] BYREF
  int v57; // [rsp+778h] [rbp+678h]
  _BYTE v58[288]; // [rsp+77Ch] [rbp+67Ch] BYREF
  int v59; // [rsp+89Ch] [rbp+79Ch]
  _BYTE v60[288]; // [rsp+8A0h] [rbp+7A0h] BYREF
  __int64 v61; // [rsp+9C0h] [rbp+8C0h]
  _BYTE v62[288]; // [rsp+9C8h] [rbp+8C8h] BYREF
  __int64 v63; // [rsp+AE8h] [rbp+9E8h]
  int v64; // [rsp+AF0h] [rbp+9F0h]
  _BYTE v65[640]; // [rsp+B00h] [rbp+A00h] BYREF
  _BYTE v66[624]; // [rsp+D80h] [rbp+C80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1048h] [rbp+F48h]

  v38 = a6;
  memset_0(v65, 0, 0x4E8u);
  v45 = a5;
  Src[0] = a2;
  v47 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  Src[1] = a3;
  v44 = a4;
  memset(v46, 0, sizeof(v46));
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  memset_0(v56, 0, sizeof(v56));
  v57 = 0;
  memset_0(v58, 0, sizeof(v58));
  v59 = 0;
  memset_0(v60, 0, sizeof(v60));
  v61 = 0;
  memset_0(v62, 0, sizeof(v62));
  v63 = 0;
  v64 = 0;
  v11 = CopyToXvmWaveFormatExtensible(a6, (struct XvmWaveFormatExtensible *)v46);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x144,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientcore.cpp",
      (const char *)(unsigned int)v11,
      v34);
    return (unsigned int)v12;
  }
  if ( a7 )
    v14 = *a7;
  else
    v14 = GUID_00000000_0000_0000_0000_000000000000;
  v50 = v14;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1456));
  pv = 0;
  p_pv = &pv;
  *(_QWORD *)v37 = 0;
  v40 = 0;
  v41 = 1;
  memcpy_0(v42, Src, 0x534u);
  v35 = v37;
  v12 = CGuestXvmAudioObject::SendAndValidateResponse<XvmInitialize>(
          (char *)this + 16,
          *((unsigned int *)this + 16),
          v42,
          &v40);
  wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v12 < 0 )
  {
    v15 = 341;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientcore.cpp",
      (const char *)(unsigned int)v12,
      (int)v35);
    v16 = pv;
    pv = 0;
    if ( v16 )
      CoTaskMemFree(v16);
    if ( this != (CGuestAudioClient *)-1456LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1456));
    return (unsigned int)v12;
  }
  v12 = PopulateSystemAudioStream<XvmInitialize>(*(_QWORD *)v37, v65);
  if ( v12 < 0 )
  {
    v15 = 343;
    goto LABEL_9;
  }
  wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset((char *)this + 1432);
  v12 = WrapCrossProcessEvent((struct CP_EVENT_METADATA_BLOB *)v66, (struct ICrossProcessEvent **)this + 179);
  if ( v12 < 0 )
  {
    v15 = 346;
    goto LABEL_9;
  }
  v12 = CAudioClient::InitializeStreamingEndpoint(
          *((CAudioClient **)this + 18),
          a2,
          a3,
          *((_DWORD *)this + 357),
          a4,
          a5,
          v38,
          a7,
          (struct SYSTEM_AUDIO_STREAM *)v65);
  if ( v12 < 0 )
  {
    v15 = 348;
    goto LABEL_9;
  }
  v17 = 9;
  v18 = (_OWORD *)((char *)this + 152);
  v19 = v65;
  do
  {
    v20 = v19[1];
    *v18 = *v19;
    v21 = v19[2];
    v18[1] = v20;
    v22 = v19[3];
    v18[2] = v21;
    v23 = v19[4];
    v18[3] = v22;
    v24 = v19[5];
    v18[4] = v23;
    v25 = v19[6];
    v18[5] = v24;
    v26 = v19[7];
    v19 += 8;
    v18[6] = v25;
    v18[7] = v26;
    v18 += 8;
    --v17;
  }
  while ( v17 );
  v27 = v19[1];
  *v18 = *v19;
  v28 = v19[2];
  v18[1] = v27;
  v29 = v19[3];
  v18[2] = v28;
  v30 = v19[4];
  v18[3] = v29;
  v31 = v19[5];
  v32 = *((_QWORD *)v19 + 12);
  v18[4] = v30;
  v18[5] = v31;
  *((_QWORD *)v18 + 12) = v32;
  v33 = pv;
  pv = 0;
  if ( v33 )
    CoTaskMemFree(v33);
  if ( this != (CGuestAudioClient *)-1456LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1456));
  return 0;
}

```

## disassembly

```asm
0x1800b0080  push    rbp
0x1800b0082  push    rbx
0x1800b0083  push    rsi
0x1800b0084  push    rdi
0x1800b0085  push    r12
0x1800b0087  push    r13
0x1800b0089  push    r14
0x1800b008b  push    r15
0x1800b008d  lea     rbp, [rsp-0F08h]
0x1800b0095  mov     eax, 1008h
0x1800b009a  call    _alloca_probe
0x1800b009f  sub     rsp, rax
0x1800b00a2  mov     rax, cs:__security_cookie
0x1800b00a9  xor     rax, rsp
0x1800b00ac  mov     [rbp+0F40h+var_50], rax
0x1800b00b3  mov     rbx, [rbp+0F40h+arg_28]
0x1800b00ba  mov     r12d, r8d
0x1800b00bd  mov     r14, [rbp+0F40h+arg_30]
0x1800b00c4  mov     r15d, edx
0x1800b00c7  mov     rsi, rcx
0x1800b00ca  mov     [rsp+1040h+var_FE0], rbx
0x1800b00cf  xor     edx, edx; Val
0x1800b00d1  lea     rcx, [rbp+0F40h+var_540]; void *
0x1800b00d8  mov     r8d, 4E8h; Size
0x1800b00de  mov     r13, r9
0x1800b00e1  call    memset_0
0x1800b00e6  mov     rax, [rbp+0F40h+arg_20]
0x1800b00ed  lea     rcx, [rbp+0F40h+var_9E8]; void *
0x1800b00f4  xorps   xmm0, xmm0
0x1800b00f7  mov     [rbp+0F40h+var_A70], rax
0x1800b00fe  xor     eax, eax
0x1800b0100  mov     [rbp+0F40h+Src], r15d
0x1800b0107  xorps   xmm1, xmm1
0x1800b010a  mov     [rbp+0F40h+var_A48], rax
0x1800b0111  mov     edi, 120h
0x1800b0116  mov     [rbp+0F40h+var_A00], eax
0x1800b011c  mov     r8d, edi; Size
0x1800b011f  mov     [rbp+0F40h+var_9FC], rax
0x1800b0126  xor     edx, edx; Val
0x1800b0128  mov     [rbp+0F40h+var_9F4], rax
0x1800b012f  mov     [rbp+0F40h+var_9EC], eax
0x1800b0135  mov     [rbp+0F40h+var_A7C], r12d
0x1800b013c  mov     [rbp+0F40h+var_A78], r13
0x1800b0143  movups  [rbp+0F40h+var_A68], xmm0
0x1800b014a  movups  [rbp+0F40h+var_A58], xmm0
0x1800b0151  movups  [rbp+0F40h+var_A40], xmm0
0x1800b0158  movups  [rbp+0F40h+var_A30], xmm0
0x1800b015f  movups  [rbp+0F40h+var_A20], xmm0
0x1800b0166  movups  [rbp+0F40h+var_A10], xmm1
0x1800b016d  call    memset_0
0x1800b0172  mov     r8d, edi; Size
0x1800b0175  mov     [rbp+0F40h+var_8C8], 0
0x1800b017f  xor     edx, edx; Val
0x1800b0181  lea     rcx, [rbp+0F40h+var_8C4]; void *
0x1800b0188  call    memset_0
0x1800b018d  mov     r8d, edi; Size
0x1800b0190  mov     [rbp+0F40h+var_7A4], 0
0x1800b019a  xor     edx, edx; Val
0x1800b019c  lea     rcx, [rbp+0F40h+var_7A0]; void *
0x1800b01a3  call    memset_0
0x1800b01a8  mov     r8d, edi; Size
0x1800b01ab  mov     [rbp+0F40h+var_680], 0
0x1800b01b6  xor     edx, edx; Val
0x1800b01b8  lea     rcx, [rbp+0F40h+var_678]; void *
0x1800b01bf  call    memset_0
0x1800b01c4  lea     rdx, [rbp+0F40h+var_A68]; struct XvmWaveFormatExtensible *
0x1800b01cb  mov     [rbp+0F40h+var_558], 0
0x1800b01d6  mov     rcx, rbx; Src
0x1800b01d9  mov     [rbp+0F40h+var_550], 0
0x1800b01e3  call    ?CopyToXvmWaveFormatExtensible@@YAJPEBUtWAVEFORMATEX@@PEAUXvmWaveFormatExtensible@@@Z; CopyToXvmWaveFormatExtensible(tWAVEFORMATEX const *,XvmWaveFormatExtensible *)
0x1800b01e8  mov     ebx, eax
0x1800b01ea  test    eax, eax
0x1800b01ec  jns     short loc_1800B020E
0x1800b01ee  mov     rcx, [rbp+0F48h]; this
0x1800b01f5  lea     r8, aAvcoreAudiocor_66; "avcore\\audiocore\\client\\audioclient"...
0x1800b01fc  mov     r9d, eax; char *
0x1800b01ff  lea     edx, [rdi+24h]; void *
0x1800b0202  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b0207  mov     eax, ebx
0x1800b0209  jmp     loc_1800B0445
0x1800b020e  xor     ebx, ebx
0x1800b0210  test    r14, r14
0x1800b0213  jz      short loc_1800B021B
0x1800b0215  movups  xmm0, xmmword ptr [r14]
0x1800b0219  jmp     short loc_1800B0222
0x1800b021b  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800b0222  lea     rdi, [rsi+5B0h]
0x1800b0229  mov     rcx, rdi; lpCriticalSection
0x1800b022c  movdqu  [rbp+0F40h+var_A20], xmm0
0x1800b0234  call    cs:__imp_EnterCriticalSection
0x1800b023a  lea     rax, [rsp+1040h+pv]
0x1800b023f  mov     [rsp+1040h+pv], rbx
0x1800b0244  lea     rcx, [rbp+0F40h+var_FC0]; void *
0x1800b0248  mov     [rsp+1040h+var_FD8], rax
0x1800b024d  lea     rdx, [rbp+0F40h+Src]; Src
0x1800b0254  mov     qword ptr [rsp+1040h+var_FE8], rbx
0x1800b0259  mov     r8d, 534h; Size
0x1800b025f  mov     [rsp+1040h+var_FD0], rbx
0x1800b0264  mov     [rsp+1040h+var_FC8], 1
0x1800b0269  call    memcpy_0
0x1800b026e  mov     edx, [rsi+40h]
0x1800b0271  lea     rax, [rsp+1040h+var_FE8]
0x1800b0276  lea     rcx, [rsi+10h]
0x1800b027a  mov     [rsp+1040h+var_1020], rax; int
0x1800b027f  lea     r9, [rsp+1040h+var_FD0]
0x1800b0284  lea     r8, [rbp+0F40h+var_FC0]
0x1800b0288  call    ??$SendAndValidateResponse@UXvmInitialize@@@CGuestXvmAudioObject@@QEAAJIUXvmInitialize@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmInitialize>(uint,XvmInitialize,XvmMessage * *,XvmInitialize * *)
0x1800b028d  lea     rcx, [rsp+1040h+var_FD8]
0x1800b0292  mov     ebx, eax
0x1800b0294  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800b0299  test    ebx, ebx
0x1800b029b  jns     short loc_1800B02E8
0x1800b029d  mov     edx, 155h; void *
0x1800b02a2  mov     rcx, [rbp+0F48h]; this
0x1800b02a9  lea     r8, aAvcoreAudiocor_66; "avcore\\audiocore\\client\\audioclient"...
0x1800b02b0  mov     r9d, ebx; char *
0x1800b02b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b02b8  mov     rcx, [rsp+1040h+pv]; pv
0x1800b02bd  mov     [rsp+1040h+pv], 0
0x1800b02c6  test    rcx, rcx
0x1800b02c9  jz      short loc_1800B02D1
0x1800b02cb  call    cs:__imp_CoTaskMemFree
0x1800b02d1  test    rdi, rdi
0x1800b02d4  jz      loc_1800B0207
0x1800b02da  mov     rcx, rdi; lpCriticalSection
0x1800b02dd  call    cs:__imp_LeaveCriticalSection
0x1800b02e3  jmp     loc_1800B0207
0x1800b02e8  mov     rcx, qword ptr [rsp+1040h+var_FE8]
0x1800b02ed  lea     rdx, [rbp+0F40h+var_540]
0x1800b02f4  call    ??$PopulateSystemAudioStream@UXvmInitialize@@@@YAJPEAUXvmInitialize@@PEAUSYSTEM_AUDIO_STREAM@@@Z; PopulateSystemAudioStream<XvmInitialize>(XvmInitialize *,SYSTEM_AUDIO_STREAM *)
0x1800b02f9  mov     ebx, eax
0x1800b02fb  test    eax, eax
0x1800b02fd  jns     short loc_1800B0306
0x1800b02ff  mov     edx, 157h
0x1800b0304  jmp     short loc_1800B02A2
0x1800b0306  lea     rbx, [rsi+598h]
0x1800b030d  mov     rcx, rbx
0x1800b0310  call    ?reset@?$com_ptr_t@UIMediaNotificationCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset(void)
0x1800b0315  mov     rdx, rbx; struct ICrossProcessEvent **
0x1800b0318  lea     rcx, [rbp+0F40h+var_2C0]; struct CP_EVENT_METADATA_BLOB *
0x1800b031f  call    ?WrapCrossProcessEvent@@YAJPEAUCP_EVENT_METADATA_BLOB@@PEAPEAUICrossProcessEvent@@@Z; WrapCrossProcessEvent(CP_EVENT_METADATA_BLOB *,ICrossProcessEvent * *)
0x1800b0324  mov     ebx, eax
0x1800b0326  test    eax, eax
0x1800b0328  jns     short loc_1800B0334
0x1800b032a  mov     edx, 15Ah
0x1800b032f  jmp     loc_1800B02A2
0x1800b0334  mov     r9d, [rsi+594h]; int
0x1800b033b  lea     rax, [rbp+0F40h+var_540]
0x1800b0342  mov     rcx, [rsi+90h]; this
0x1800b0349  mov     r8d, r12d; unsigned int
0x1800b034c  mov     [rsp+1040h+var_1000], rax; struct SYSTEM_AUDIO_STREAM *
0x1800b0351  mov     edx, r15d; enum _AUDCLNT_SHAREMODE
0x1800b0354  mov     rax, [rsp+1040h+var_FE0]
0x1800b0359  mov     [rsp+1040h+var_1008], r14; struct _GUID *
0x1800b035e  mov     [rsp+1040h+var_1010], rax; struct tWAVEFORMATEX *
0x1800b0363  mov     rax, [rbp+0F40h+arg_20]
0x1800b036a  mov     [rsp+1040h+var_1018], rax; __int64
0x1800b036f  mov     [rsp+1040h+var_1020], r13; __int64
0x1800b0374  call    ?InitializeStreamingEndpoint@CAudioClient@@QEAAJW4_AUDCLNT_SHAREMODE@@KH_J1PEBUtWAVEFORMATEX@@PEBU_GUID@@PEAUSYSTEM_AUDIO_STREAM@@@Z; CAudioClient::InitializeStreamingEndpoint(_AUDCLNT_SHAREMODE,ulong,int,__int64,__int64,tWAVEFORMATEX const *,_GUID const *,SYSTEM_AUDIO_STREAM *)
0x1800b0379  mov     ebx, eax
0x1800b037b  test    eax, eax
0x1800b037d  jns     short loc_1800B0389
0x1800b037f  mov     edx, 15Ch
0x1800b0384  jmp     loc_1800B02A2
0x1800b0389  mov     edx, 9
0x1800b038e  lea     rcx, [rsi+98h]
0x1800b0395  lea     rax, [rbp+0F40h+var_540]
0x1800b039c  lea     r8d, [rdx+77h]
0x1800b03a0  movups  xmm0, xmmword ptr [rax]
0x1800b03a3  movups  xmm1, xmmword ptr [rax+10h]
0x1800b03a7  movups  xmmword ptr [rcx], xmm0
0x1800b03aa  movups  xmm0, xmmword ptr [rax+20h]
0x1800b03ae  movups  xmmword ptr [rcx+10h], xmm1
0x1800b03b2  movups  xmm1, xmmword ptr [rax+30h]
0x1800b03b6  movups  xmmword ptr [rcx+20h], xmm0
0x1800b03ba  movups  xmm0, xmmword ptr [rax+40h]
0x1800b03be  movups  xmmword ptr [rcx+30h], xmm1
0x1800b03c2  movups  xmm1, xmmword ptr [rax+50h]
0x1800b03c6  movups  xmmword ptr [rcx+40h], xmm0
0x1800b03ca  movups  xmm0, xmmword ptr [rax+60h]
0x1800b03ce  movups  xmmword ptr [rcx+50h], xmm1
0x1800b03d2  movups  xmm1, xmmword ptr [rax+70h]
0x1800b03d6  add     rax, r8
0x1800b03d9  movups  xmmword ptr [rcx+60h], xmm0
0x1800b03dd  movups  xmmword ptr [rcx+70h], xmm1
0x1800b03e1  add     rcx, r8
0x1800b03e4  sub     rdx, 1
0x1800b03e8  jnz     short loc_1800B03A0
0x1800b03ea  movups  xmm0, xmmword ptr [rax]
0x1800b03ed  movups  xmm1, xmmword ptr [rax+10h]
0x1800b03f1  movups  xmmword ptr [rcx], xmm0
0x1800b03f4  movups  xmm0, xmmword ptr [rax+20h]
0x1800b03f8  movups  xmmword ptr [rcx+10h], xmm1
0x1800b03fc  movups  xmm1, xmmword ptr [rax+30h]
0x1800b0400  movups  xmmword ptr [rcx+20h], xmm0
0x1800b0404  movups  xmm0, xmmword ptr [rax+40h]
0x1800b0408  movups  xmmword ptr [rcx+30h], xmm1
0x1800b040c  movups  xmm1, xmmword ptr [rax+50h]
0x1800b0410  mov     rax, [rax+60h]
0x1800b0414  movups  xmmword ptr [rcx+40h], xmm0
0x1800b0418  movups  xmmword ptr [rcx+50h], xmm1
0x1800b041c  mov     [rcx+60h], rax
0x1800b0420  mov     rcx, [rsp+1040h+pv]; pv
0x1800b0425  mov     [rsp+1040h+pv], rdx
0x1800b042a  test    rcx, rcx
0x1800b042d  jz      short loc_1800B0435
0x1800b042f  call    cs:__imp_CoTaskMemFree
0x1800b0435  test    rdi, rdi
0x1800b0438  jz      short loc_1800B0443
0x1800b043a  mov     rcx, rdi; lpCriticalSection
0x1800b043d  call    cs:__imp_LeaveCriticalSection
0x1800b0443  xor     eax, eax
0x1800b0445  mov     rcx, [rbp+0F40h+var_50]
0x1800b044c  xor     rcx, rsp; StackCookie
0x1800b044f  call    __security_check_cookie
0x1800b0454  add     rsp, 1008h
0x1800b045b  pop     r15
0x1800b045d  pop     r14
0x1800b045f  pop     r13
0x1800b0461  pop     r12
0x1800b0463  pop     rdi
0x1800b0464  pop     rsi
0x1800b0465  pop     rbx
0x1800b0466  pop     rbp
0x1800b0467  retn
```
