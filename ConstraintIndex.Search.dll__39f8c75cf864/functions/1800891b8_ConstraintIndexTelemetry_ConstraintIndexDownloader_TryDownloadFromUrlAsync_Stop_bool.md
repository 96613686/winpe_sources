# ConstraintIndexTelemetry::ConstraintIndexDownloader_TryDownloadFromUrlAsync::Stop(bool)

- ea: `0x1800891b8`
- end: `0x180089480`
- name: `?Stop@ConstraintIndexDownloader_TryDownloadFromUrlAsync@ConstraintIndexTelemetry@@QEAAX_N@Z`
- size: `712`
- prototype: `void __fastcall(ConstraintIndexTelemetry::ConstraintIndexDownloader_TryDownloadFromUrlAsync *__hidden this, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800831f4`
- `0x180084e24`

## callees

- `0x18000243c`
- `0x180002468`
- `0x180002524`
- `0x1800049e0`
- `0x18003bf74`
- `0x18003c9b8`
- `0x180040bb8`
- `0x1800891b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800893da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800893da`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::ConstraintIndexDownloader_TryDownloadFromUrlAsync::Stop(
        ConstraintIndexTelemetry::ConstraintIndexDownloader_TryDownloadFromUrlAsync *this,
        unsigned __int8 a2)
{
  __int64 v2; // rdi
  int v4; // esi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  int v9; // r9d
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  int v17; // [rsp+C0h] [rbp-80h] BYREF
  DWORD v18; // [rsp+C4h] [rbp-7Ch] BYREF
  int v19; // [rsp+C8h] [rbp-78h] BYREF
  int v20; // [rsp+CCh] [rbp-74h] BYREF
  int v21; // [rsp+D0h] [rbp-70h] BYREF
  int v22; // [rsp+D4h] [rbp-6Ch] BYREF
  int v23; // [rsp+D8h] [rbp-68h] BYREF
  int v24; // [rsp+DCh] [rbp-64h] BYREF
  int v25; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v27; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v29; // [rsp+100h] [rbp-40h] BYREF
  __int64 v30; // [rsp+108h] [rbp-38h] BYREF
  __int64 v31; // [rsp+110h] [rbp-30h] BYREF
  __int64 v32; // [rsp+118h] [rbp-28h] BYREF
  __int64 v33; // [rsp+120h] [rbp-20h] BYREF
  __int64 v34; // [rsp+128h] [rbp-18h] BYREF
  __int64 v35; // [rsp+130h] [rbp-10h] BYREF
  __int64 v36; // [rsp+138h] [rbp-8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+140h] [rbp+0h] BYREF
  __int64 *v38; // [rsp+160h] [rbp+20h]
  __int64 v39; // [rsp+168h] [rbp+28h]
  int *v40; // [rsp+170h] [rbp+30h]
  __int64 v41; // [rsp+178h] [rbp+38h]
  DWORD *v42; // [rsp+180h] [rbp+40h]
  __int64 v43; // [rsp+188h] [rbp+48h]
  int *v44; // [rsp+190h] [rbp+50h]
  __int64 v45; // [rsp+198h] [rbp+58h]

  v2 = *((_QWORD *)this + 34);
  v4 = a2;
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = CortanaSearchTelemetryLogging::Provider();
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 1, v8, v7) )
    {
      v27 = *((_QWORD *)v6 + 6);
      v21 = v6[17];
      v22 = v6[4];
      v28 = *((_QWORD *)v6 + 15);
      v29 = *((_QWORD *)v6 + 14);
      v23 = v6[26];
      v10 = *((_QWORD *)this + 34);
      v30 = *((_QWORD *)v6 + 12);
      v31 = *((_QWORD *)v6 + 11);
      v24 = v6[20];
      v32 = *((_QWORD *)v6 + 9);
      v25 = v6[8];
      v33 = *((_QWORD *)v6 + 3);
      v17 = *v6;
      v34 = *((_QWORD *)v6 + 16);
      v18 = v6[16];
      v35 = *((_QWORD *)v6 + 7);
      v19 = v6[2];
      v20 = v4;
      v36 = 0x1000000;
      v26 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v9,
        (int)&byte_1801123F9,
        v10 + 8,
        (__int64)&v26,
        (__int64)&v36,
        (__int64)&v19,
        (__int64)&v35,
        (__int64)&v18,
        (__int64)&v34,
        (__int64)&v17,
        (__int64)&v33,
        (__int64)&v25,
        (__int64)&v32,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v23,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v27,
        (__int64)&v20);
    }
  }
  else
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = CortanaSearchTelemetryLogging::Provider();
    v14 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 1, v12, v13) )
    {
      v19 = v4;
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      v18 = CurrentThreadId;
      v45 = 4;
      v43 = 4;
      v17 = *(_DWORD *)(v16 + 72);
      v44 = &v19;
      v42 = &v18;
      v40 = &v17;
      v38 = &v26;
      v26 = 0;
      v41 = 4;
      v39 = 8;
      tlgWriteTransfer_EventWriteTransfer(v14, (unsigned __int8 *)&unk_180112578, (const GUID *)(v16 + 8), 0, 6u, &v37);
    }
  }
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x1800891b8  push    rbp
0x1800891ba  push    rbx
0x1800891bb  push    rsi
0x1800891bc  push    rdi
0x1800891bd  lea     rbp, [rsp-78h]
0x1800891c2  sub     rsp, 1B8h
0x1800891c9  mov     rax, cs:__security_cookie
0x1800891d0  xor     rax, rsp
0x1800891d3  mov     [rbp+90h+var_30], rax
0x1800891d7  mov     rdi, [rcx+110h]
0x1800891de  mov     rbx, rcx
0x1800891e1  movzx   esi, dl
0x1800891e4  mov     eax, [rdi+48h]
0x1800891e7  test    eax, eax
0x1800891e9  jns     loc_1800893AA
0x1800891ef  add     rdi, 50h ; 'P'
0x1800891f3  cmp     eax, [rdi+8]
0x1800891f6  jnz     loc_1800893AA
0x1800891fc  test    rdi, rdi
0x1800891ff  jz      loc_1800893AA
0x180089205  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18008920a  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18008920f  mov     r9, rax
0x180089212  mov     ecx, [rax]
0x180089214  cmp     ecx, 5
0x180089217  jbe     loc_180089460
0x18008921d  mov     edx, 1
0x180089222  mov     rcx, rax
0x180089225  call    _tlgKeywordOn
0x18008922a  test    al, al
0x18008922c  jz      loc_180089460
0x180089232  mov     rax, [rdi+30h]
0x180089236  lea     rdx, byte_1801123F9; int
0x18008923d  mov     [rbp+90h+var_E0], rax
0x180089241  mov     rcx, r9; int
0x180089244  mov     eax, [rdi+44h]
0x180089247  mov     dword ptr [rbp+90h+var_100], eax
0x18008924a  mov     eax, [rdi+10h]
0x18008924d  mov     dword ptr [rbp+90h+var_100+4], eax
0x180089250  mov     rax, [rdi+78h]
0x180089254  mov     [rbp+90h+var_D8], rax
0x180089258  mov     rax, [rdi+70h]
0x18008925c  mov     [rbp+90h+var_D0], rax
0x180089260  mov     eax, [rdi+68h]
0x180089263  mov     [rbp+90h+var_F8], eax
0x180089266  mov     rax, [rdi+60h]
0x18008926a  mov     r8, [rbx+110h]
0x180089271  mov     [rbp+90h+var_C8], rax
0x180089275  add     r8, 8; int
0x180089279  mov     rax, [rdi+58h]
0x18008927d  mov     [rbp+90h+var_C0], rax
0x180089281  mov     eax, [rdi+50h]
0x180089284  mov     [rbp+90h+var_F4], eax
0x180089287  mov     rax, [rdi+48h]
0x18008928b  mov     [rbp+90h+var_B8], rax
0x18008928f  mov     eax, [rdi+20h]
0x180089292  mov     [rbp+90h+var_F0], eax
0x180089295  mov     rax, [rdi+18h]
0x180089299  mov     [rbp+90h+var_B0], rax
0x18008929d  mov     eax, [rdi]
0x18008929f  mov     dword ptr [rbp+90h+var_110], eax
0x1800892a2  mov     rax, [rdi+80h]
0x1800892a9  mov     [rbp+90h+var_A8], rax
0x1800892ad  mov     eax, [rdi+40h]
0x1800892b0  mov     dword ptr [rbp+90h+var_110+4], eax
0x1800892b3  mov     rax, [rdi+38h]
0x1800892b7  mov     [rbp+90h+var_A0], rax
0x1800892bb  mov     eax, [rdi+8]
0x1800892be  mov     dword ptr [rbp+90h+var_108], eax
0x1800892c1  lea     rax, [rbp+90h+var_108+4]
0x1800892c5  mov     [rsp+1D0h+var_118], rax; __int64
0x1800892cd  lea     rax, [rbp+90h+var_E0]
0x1800892d1  mov     [rsp+1D0h+var_120], rax; __int64
0x1800892d9  lea     rax, [rbp+90h+var_100]
0x1800892dd  mov     [rsp+1D0h+var_128], rax; __int64
0x1800892e5  lea     rax, [rbp+90h+var_100+4]
0x1800892e9  mov     [rsp+1D0h+var_130], rax; __int64
0x1800892f1  lea     rax, [rbp+90h+var_D8]
0x1800892f5  mov     [rsp+1D0h+var_138], rax; __int64
0x1800892fd  lea     rax, [rbp+90h+var_D0]
0x180089301  mov     [rsp+1D0h+var_140], rax; __int64
0x180089309  lea     rax, [rbp+90h+var_F8]
0x18008930d  mov     [rsp+1D0h+var_148], rax; __int64
0x180089315  lea     rax, [rbp+90h+var_C8]
0x180089319  mov     [rsp+1D0h+var_150], rax; __int64
0x180089321  lea     rax, [rbp+90h+var_C0]
0x180089325  mov     [rsp+1D0h+var_158], rax; __int64
0x18008932a  lea     rax, [rbp+90h+var_F4]
0x18008932e  mov     [rsp+1D0h+var_160], rax; __int64
0x180089333  lea     rax, [rbp+90h+var_B8]
0x180089337  mov     [rsp+1D0h+var_168], rax; __int64
0x18008933c  lea     rax, [rbp+90h+var_F0]
0x180089340  mov     [rsp+1D0h+var_170], rax; __int64
0x180089345  lea     rax, [rbp+90h+var_B0]
0x180089349  mov     [rsp+1D0h+var_178], rax; __int64
0x18008934e  lea     rax, [rbp+90h+var_110]
0x180089352  mov     [rsp+1D0h+var_180], rax; __int64
0x180089357  lea     rax, [rbp+90h+var_A8]
0x18008935b  mov     [rsp+1D0h+var_188], rax; __int64
0x180089360  lea     rax, [rbp+90h+var_110+4]
0x180089364  mov     [rsp+1D0h+var_190], rax; __int64
0x180089369  lea     rax, [rbp+90h+var_A0]
0x18008936d  mov     [rsp+1D0h+var_198], rax; __int64
0x180089372  lea     rax, [rbp+90h+var_108]
0x180089376  mov     [rsp+1D0h+var_1A0], rax; __int64
0x18008937b  lea     rax, [rbp+90h+var_98]
0x18008937f  mov     [rsp+1D0h+var_1A8], rax; __int64
0x180089384  lea     rax, [rbp+90h+var_E8]
0x180089388  mov     qword ptr [rsp+1D0h+var_1B0], rax; __int64
0x18008938d  mov     dword ptr [rbp+90h+var_108+4], esi
0x180089390  mov     [rbp+90h+var_98], 1000000h
0x180089398  mov     [rbp+90h+var_E8], 0
0x1800893a0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564564454@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800893a5  jmp     loc_180089460
0x1800893aa  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800893af  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800893b4  mov     rdi, rax
0x1800893b7  mov     ecx, [rax]
0x1800893b9  cmp     ecx, 5
0x1800893bc  jbe     loc_180089460
0x1800893c2  mov     edx, 1
0x1800893c7  mov     rcx, rax
0x1800893ca  call    _tlgKeywordOn
0x1800893cf  test    al, al
0x1800893d1  jz      loc_180089460
0x1800893d7  mov     dword ptr [rbp+90h+var_108], esi
0x1800893da  call    cs:__imp_GetCurrentThreadId
0x1800893e0  mov     r8, [rbx+110h]
0x1800893e7  lea     rdx, unk_180112578; int
0x1800893ee  mov     dword ptr [rbp+90h+var_110+4], eax
0x1800893f1  xor     r9d, r9d; int
0x1800893f4  mov     rcx, rdi; int
0x1800893f7  mov     [rbp+90h+var_38], 4
0x1800893ff  mov     [rbp+90h+var_48], 4
0x180089407  mov     eax, [r8+48h]
0x18008940b  add     r8, 8; int
0x18008940f  mov     dword ptr [rbp+90h+var_110], eax
0x180089412  lea     rax, [rbp+90h+var_108]
0x180089416  mov     [rbp+90h+var_40], rax
0x18008941a  lea     rax, [rbp+90h+var_110+4]
0x18008941e  mov     [rbp+90h+var_50], rax
0x180089422  lea     rax, [rbp+90h+var_110]
0x180089426  mov     [rbp+90h+var_60], rax
0x18008942a  lea     rax, [rbp+90h+var_E8]
0x18008942e  mov     [rbp+90h+var_70], rax
0x180089432  lea     rax, [rbp+90h+var_90]
0x180089436  mov     [rsp+1D0h+var_1A8], rax; PEVENT_DATA_DESCRIPTOR
0x18008943b  mov     [rsp+1D0h+var_1B0], 6; ULONG
0x180089443  mov     [rbp+90h+var_E8], 0
0x18008944b  mov     [rbp+90h+var_58], 4
0x180089453  mov     [rbp+90h+var_68], 8
0x18008945b  call    _tlgWriteTransfer_EventWriteTransfer
0x180089460  mov     rcx, rbx
0x180089463  call    ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180089468  mov     rcx, [rbp+90h+var_30]
0x18008946c  xor     rcx, rsp; StackCookie
0x18008946f  call    __security_check_cookie
0x180089474  add     rsp, 1B8h
0x18008947b  pop     rdi
0x18008947c  pop     rsi
0x18008947d  pop     rbx
0x18008947e  pop     rbp
0x18008947f  retn
```
