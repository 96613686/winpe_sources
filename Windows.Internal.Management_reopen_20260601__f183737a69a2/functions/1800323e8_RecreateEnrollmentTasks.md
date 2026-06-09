# RecreateEnrollmentTasks

- ea: `0x1800323e8`
- end: `0x1800326e4`
- name: `RecreateEnrollmentTasks`
- size: `764`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180023ff0`

## callees

- `0x180004eb0`
- `0x180005a74`
- `0x180009be4`
- `0x18000a5c4`
- `0x180017a40`
- `0x1800188f4`
- `0x180019640`
- `0x1800323e8`
- `0x1800907b8`
- `0x180094c70`
- `0x1800954f0`
- `0x180095910`
- `0x180095a58`
- `0x180095d0c`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmDeleteTask` at `0x180032576`
- `DMCmnUtils!DmDeleteTask` at `0x180032576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003253f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003253f`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x18003268c`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x18003268c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RecreateEnrollmentTasks(__int64 a1, const unsigned __int16 *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, __int64 **); // rbx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rax
  int DeviceCertExpiryTime; // eax
  __int64 v10; // rdx
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int v13; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v14; // [rsp+30h] [rbp-D0h]
  __int64 *v15; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v19; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v20; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v21; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  struct _FILETIME v23; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v24; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v25[40]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  Windows::Internal::StringReference::StringReference(&v24, (const unsigned __int16 (*)[48])a2);
  v22 = 0;
  v2 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(
         v24,
         &v22);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v15 = 0;
    v4 = v22;
    v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)v22 + 96LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
    v6 = v5(v4, 6, &v15);
    v3 = v6;
    if ( v6 < 0 )
    {
      v7 = 1942;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v6,
        v13);
LABEL_6:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
      goto LABEL_31;
    }
    v17 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v15 + 56))(v15, &v17);
    v3 = v6;
    if ( v6 < 0 )
    {
      v7 = 1946;
      goto LABEL_5;
    }
    if ( v17 )
    {
      string = 0;
      v8 = *v15;
      string = 0;
      DeviceCertExpiryTime = (*(__int64 (__fastcall **)(__int64 *, _QWORD, HSTRING *))(v8 + 48))(v15, 0, &string);
      v3 = DeviceCertExpiryTime;
      if ( DeviceCertExpiryTime < 0 )
      {
        v10 = 1952;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
          (const char *)(unsigned int)DeviceCertExpiryTime,
          v13);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        goto LABEL_6;
      }
      memset_0(v25, 0, 0x4Eu);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      DeviceCertExpiryTime = TrimGuidBracket(StringRawBuffer, v25);
      v3 = DeviceCertExpiryTime;
      if ( DeviceCertExpiryTime < 0 )
      {
        v10 = 1955;
        goto LABEL_12;
      }
      DmDeleteTask(L"\\Microsoft\\Windows\\EnterpriseMgmt", v25, L"Schedule to run OMADMClient by client");
      v23 = 0;
      DeviceCertExpiryTime = GetDeviceCertExpiryTime(v25, &v23);
      v3 = DeviceCertExpiryTime;
      if ( DeviceCertExpiryTime < 0 )
      {
        v10 = 1964;
        goto LABEL_12;
      }
      v21 = 0;
      DeviceCertExpiryTime = GetRenewPeriodInSeconds(v25, &v21);
      v3 = DeviceCertExpiryTime;
      if ( DeviceCertExpiryTime < 0 )
      {
        v10 = 1967;
        goto LABEL_12;
      }
      v20 = 0;
      DeviceCertExpiryTime = GetRenewRetryIntervalInSeconds(v25, 1, &v20);
      v3 = DeviceCertExpiryTime;
      if ( DeviceCertExpiryTime < 0 )
      {
        v10 = 1970;
        goto LABEL_12;
      }
      v19 = 0;
      DeviceCertExpiryTime = GetRenewRetryIntervalInSeconds(v25, 0, &v19);
      v3 = DeviceCertExpiryTime;
      if ( DeviceCertExpiryTime < 0 )
      {
        v10 = 1973;
        goto LABEL_12;
      }
      v18 = 0;
      DeviceCertExpiryTime = IsROBOMode(v25, &v18);
      v3 = DeviceCertExpiryTime;
      if ( DeviceCertExpiryTime < 0 )
      {
        v10 = 1976;
        goto LABEL_12;
      }
      DeviceCertExpiryTime = SetupAllEnrollmentSchedules(v25, v23, v21, v20, v19, v18, v14);
      v3 = DeviceCertExpiryTime;
      if ( DeviceCertExpiryTime < 0 )
      {
        v10 = 1985;
        goto LABEL_12;
      }
      DeviceCertExpiryTime = OmaDmInitiateSessionAsDevice(v25, 1, 2, 0, 0, 0, 18);
      v3 = DeviceCertExpiryTime;
      if ( DeviceCertExpiryTime < 0 )
      {
        v10 = 1995;
        goto LABEL_12;
      }
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
    v3 = 0;
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x793,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
    (const char *)(unsigned int)v2,
    v13);
LABEL_31:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  return v3;
}

```

## disassembly

```asm
0x1800323e8  push    rbp
0x1800323ea  push    rbx
0x1800323eb  push    rsi
0x1800323ec  push    rdi
0x1800323ed  lea     rbp, [rsp-8]
0x1800323f2  sub     rsp, 108h
0x1800323f9  mov     rax, cs:__security_cookie
0x180032400  xor     rax, rsp
0x180032403  mov     [rbp+20h+var_30], rax
0x180032407  lea     rcx, [rsp+120h+var_A8]; string
0x18003240c  call    ??$?0$0DA@@StringReference@Internal@Windows@@QEAA@AEAY0DA@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[48])
0x180032411  xor     esi, esi
0x180032413  mov     [rsp+120h+var_B8], rsi
0x180032418  lea     rdx, [rsp+120h+var_B8]
0x18003241d  mov     rcx, [rsp+120h+var_A8]
0x180032422  call    ??$ActivateInstance@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>)
0x180032427  mov     ebx, eax
0x180032429  test    eax, eax
0x18003242b  jns     short loc_18003244A
0x18003242d  mov     rcx, [rbp+28h]; this
0x180032431  mov     r9d, eax; char *
0x180032434  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003243b  mov     edx, 793h; void *
0x180032440  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032445  jmp     loc_1800326BF
0x18003244a  mov     [rsp+120h+var_E0], rsi
0x18003244f  mov     rdi, [rsp+120h+var_B8]
0x180032454  mov     rax, [rdi]
0x180032457  mov     rbx, [rax+60h]
0x18003245b  lea     rcx, [rsp+120h+var_E0]
0x180032460  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032465  lea     r8, [rsp+120h+var_E0]
0x18003246a  mov     edx, 6
0x18003246f  mov     rcx, rdi
0x180032472  mov     rax, rbx
0x180032475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003247a  mov     ebx, eax
0x18003247c  test    eax, eax
0x18003247e  jns     short loc_1800324A8
0x180032480  mov     edx, 796h; void *
0x180032485  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003248c  mov     r9d, eax; char *
0x18003248f  mov     rcx, [rbp+28h]; this
0x180032493  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032498  nop
0x180032499  lea     rcx, [rsp+120h+var_E0]
0x18003249e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800324a3  jmp     loc_1800326BF
0x1800324a8  mov     [rsp+120h+var_D0], esi
0x1800324ac  mov     rcx, [rsp+120h+var_E0]
0x1800324b1  mov     rax, [rcx]
0x1800324b4  lea     rdx, [rsp+120h+var_D0]
0x1800324b9  mov     rax, [rax+38h]
0x1800324bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324c2  mov     ebx, eax
0x1800324c4  test    eax, eax
0x1800324c6  jns     short loc_1800324CF
0x1800324c8  mov     edx, 79Ah
0x1800324cd  jmp     short loc_180032485
0x1800324cf  cmp     [rsp+120h+var_D0], esi
0x1800324d3  jbe     loc_1800326B3
0x1800324d9  mov     [rsp+120h+string], rsi
0x1800324de  mov     rcx, [rsp+120h+var_E0]
0x1800324e3  mov     rax, [rcx]
0x1800324e6  mov     [rsp+120h+string], rsi
0x1800324eb  lea     r8, [rsp+120h+string]
0x1800324f0  xor     edx, edx
0x1800324f2  mov     rax, [rax+30h]
0x1800324f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324fb  mov     ebx, eax
0x1800324fd  test    eax, eax
0x1800324ff  jns     short loc_180032529
0x180032501  mov     edx, 7A0h; void *
0x180032506  mov     rcx, [rbp+28h]; this
0x18003250a  mov     r9d, eax; char *
0x18003250d  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180032514  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032519  nop
0x18003251a  lea     rcx, [rsp+120h+string]; this
0x18003251f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180032524  jmp     loc_180032499
0x180032529  xor     edx, edx; Val
0x18003252b  lea     r8d, [rdx+4Eh]; Size
0x18003252f  lea     rcx, [rbp+20h+var_80]; void *
0x180032533  call    memset_0
0x180032538  xor     edx, edx; length
0x18003253a  mov     rcx, [rsp+120h+string]; string
0x18003253f  call    cs:__imp_WindowsGetStringRawBuffer
0x180032546  nop     dword ptr [rax+rax+00h]
0x18003254b  mov     rcx, rax; unsigned __int16 *
0x18003254e  lea     rdx, [rbp+20h+var_80]; unsigned __int16 *
0x180032552  call    ?TrimGuidBracket@@YAJPEBGPEAG@Z; TrimGuidBracket(ushort const *,ushort *)
0x180032557  mov     ebx, eax
0x180032559  test    eax, eax
0x18003255b  jns     short loc_180032564
0x18003255d  mov     edx, 7A3h
0x180032562  jmp     short loc_180032506
0x180032564  lea     r8, aScheduleToRunO; "Schedule to run OMADMClient by client"
0x18003256b  lea     rdx, [rbp+20h+var_80]
0x18003256f  lea     rcx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180032576  call    cs:__imp_?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x18003257d  nop     dword ptr [rax+rax+00h]
0x180032582  mov     qword ptr [rsp+120h+var_B0.dwLowDateTime], rsi
0x180032587  lea     rdx, [rsp+120h+var_B0]; struct _FILETIME *
0x18003258c  lea     rcx, [rbp+20h+var_80]; unsigned __int16 *
0x180032590  call    ?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z; GetDeviceCertExpiryTime(ushort const *,_FILETIME *)
0x180032595  mov     ebx, eax
0x180032597  test    eax, eax
0x180032599  jns     short loc_1800325A5
0x18003259b  mov     edx, 7ACh
0x1800325a0  jmp     loc_180032506
0x1800325a5  mov     [rsp+120h+var_C0], esi
0x1800325a9  lea     rdx, [rsp+120h+var_C0]; unsigned int *
0x1800325ae  lea     rcx, [rbp+20h+var_80]; unsigned __int16 *
0x1800325b2  call    ?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z; GetRenewPeriodInSeconds(ushort const *,ulong *)
0x1800325b7  mov     ebx, eax
0x1800325b9  test    eax, eax
0x1800325bb  jns     short loc_1800325C7
0x1800325bd  mov     edx, 7AFh
0x1800325c2  jmp     loc_180032506
0x1800325c7  mov     [rsp+120h+var_C4], esi
0x1800325cb  lea     r8, [rsp+120h+var_C4]; unsigned int *
0x1800325d0  mov     edi, 1
0x1800325d5  mov     edx, edi; int
0x1800325d7  lea     rcx, [rbp+20h+var_80]; unsigned __int16 *
0x1800325db  call    ?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z; GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)
0x1800325e0  mov     ebx, eax
0x1800325e2  test    eax, eax
0x1800325e4  jns     short loc_1800325F0
0x1800325e6  mov     edx, 7B2h
0x1800325eb  jmp     loc_180032506
0x1800325f0  mov     [rsp+120h+var_C8], esi
0x1800325f4  lea     r8, [rsp+120h+var_C8]; unsigned int *
0x1800325f9  xor     edx, edx; int
0x1800325fb  lea     rcx, [rbp+20h+var_80]; unsigned __int16 *
0x1800325ff  call    ?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z; GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)
0x180032604  mov     ebx, eax
0x180032606  test    eax, eax
0x180032608  jns     short loc_180032614
0x18003260a  mov     edx, 7B5h
0x18003260f  jmp     loc_180032506
0x180032614  mov     [rsp+120h+var_CC], esi
0x180032618  lea     rdx, [rsp+120h+var_CC]; int *
0x18003261d  lea     rcx, [rbp+20h+var_80]; unsigned __int16 *
0x180032621  call    ?IsROBOMode@@YAJPEBGPEAH@Z; IsROBOMode(ushort const *,int *)
0x180032626  mov     ebx, eax
0x180032628  test    eax, eax
0x18003262a  jns     short loc_180032636
0x18003262c  mov     edx, 7B8h
0x180032631  jmp     loc_180032506
0x180032636  mov     eax, [rsp+120h+var_CC]
0x18003263a  mov     [rsp+120h+var_F8], eax; int
0x18003263e  mov     eax, [rsp+120h+var_C8]
0x180032642  mov     [rsp+120h+var_100], eax; unsigned int
0x180032646  mov     r9d, [rsp+120h+var_C4]; unsigned int
0x18003264b  mov     r8d, [rsp+120h+var_C0]; unsigned int
0x180032650  mov     rdx, qword ptr [rsp+120h+var_B0.dwLowDateTime]; struct _FILETIME
0x180032655  lea     rcx, [rbp+20h+var_80]; unsigned __int16 *
0x180032659  call    ?SetupAllEnrollmentSchedules@@YAJPEBGU_FILETIME@@KKKH0@Z; SetupAllEnrollmentSchedules(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)
0x18003265e  mov     ebx, eax
0x180032660  test    eax, eax
0x180032662  jns     short loc_18003266E
0x180032664  mov     edx, 7C1h
0x180032669  jmp     loc_180032506
0x18003266e  mov     [rsp+120h+var_F0], 12h
0x180032676  mov     qword ptr [rsp+120h+var_F8], rsi
0x18003267b  mov     [rsp+120h+var_100], esi
0x18003267f  xor     r9d, r9d
0x180032682  lea     r8d, [r9+2]
0x180032686  mov     edx, edi
0x180032688  lea     rcx, [rbp+20h+var_80]
0x18003268c  call    cs:__imp_OmaDmInitiateSessionAsDevice
0x180032693  nop     dword ptr [rax+rax+00h]
0x180032698  mov     ebx, eax
0x18003269a  test    eax, eax
0x18003269c  jns     short loc_1800326A8
0x18003269e  mov     edx, 7CBh
0x1800326a3  jmp     loc_180032506
0x1800326a8  lea     rcx, [rsp+120h+string]; this
0x1800326ad  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800326b2  nop
0x1800326b3  lea     rcx, [rsp+120h+var_E0]
0x1800326b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800326bd  mov     ebx, esi
0x1800326bf  lea     rcx, [rsp+120h+var_B8]
0x1800326c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800326c9  mov     eax, ebx
0x1800326cb  mov     rcx, [rbp+20h+var_30]
0x1800326cf  xor     rcx, rsp; StackCookie
0x1800326d2  call    __security_check_cookie
0x1800326d7  add     rsp, 108h
0x1800326de  pop     rdi
0x1800326df  pop     rsi
0x1800326e0  pop     rbx
0x1800326e1  pop     rbp
0x1800326e2  retn
```
