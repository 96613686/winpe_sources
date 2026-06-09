# RecreateEnrollmentTasks

- ea: `0x180033584`
- end: `0x18003386d`
- name: `RecreateEnrollmentTasks`
- size: `745`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800258dc`

## callees

- `0x180004d50`
- `0x180005904`
- `0x18000992c`
- `0x18000a2a4`
- `0x180017244`
- `0x18001a46c`
- `0x18001b190`
- `0x180033584`
- `0x18008e2b4`
- `0x18009251c`
- `0x180092d8c`
- `0x180093124`
- `0x180093250`
- `0x1800934b4`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmDeleteTask` at `0x18003370c`
- `DMCmnUtils!DmDeleteTask` at `0x18003370c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800336db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800336db`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x18003381c`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x18003381c`

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
         (__int64)v24,
         (__int64)&v22);
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
0x180033584  push    rbp
0x180033586  push    rbx
0x180033587  push    rsi
0x180033588  push    rdi
0x180033589  lea     rbp, [rsp-8]
0x18003358e  sub     rsp, 108h
0x180033595  mov     rax, cs:__security_cookie
0x18003359c  xor     rax, rsp
0x18003359f  mov     [rbp+20h+var_30], rax
0x1800335a3  lea     rcx, [rsp+120h+var_A8]; string
0x1800335a8  call    ??$?0$0DA@@StringReference@Internal@Windows@@QEAA@AEAY0DA@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[48])
0x1800335ad  xor     esi, esi
0x1800335af  mov     [rsp+120h+var_B8], rsi
0x1800335b4  lea     rdx, [rsp+120h+var_B8]
0x1800335b9  mov     rcx, [rsp+120h+var_A8]
0x1800335be  call    ??$ActivateInstance@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>)
0x1800335c3  mov     ebx, eax
0x1800335c5  test    eax, eax
0x1800335c7  jns     short loc_1800335E6
0x1800335c9  mov     rcx, [rbp+28h]; this
0x1800335cd  mov     r9d, eax; char *
0x1800335d0  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800335d7  mov     edx, 793h; void *
0x1800335dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800335e1  jmp     loc_180033849
0x1800335e6  mov     [rsp+120h+var_E0], rsi
0x1800335eb  mov     rdi, [rsp+120h+var_B8]
0x1800335f0  mov     rax, [rdi]
0x1800335f3  mov     rbx, [rax+60h]
0x1800335f7  lea     rcx, [rsp+120h+var_E0]
0x1800335fc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180033601  lea     r8, [rsp+120h+var_E0]
0x180033606  mov     edx, 6
0x18003360b  mov     rcx, rdi
0x18003360e  mov     rax, rbx
0x180033611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033616  mov     ebx, eax
0x180033618  test    eax, eax
0x18003361a  jns     short loc_180033644
0x18003361c  mov     edx, 796h; void *
0x180033621  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180033628  mov     r9d, eax; char *
0x18003362b  mov     rcx, [rbp+28h]; this
0x18003362f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033634  nop
0x180033635  lea     rcx, [rsp+120h+var_E0]
0x18003363a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003363f  jmp     loc_180033849
0x180033644  mov     [rsp+120h+var_D0], esi
0x180033648  mov     rcx, [rsp+120h+var_E0]
0x18003364d  mov     rax, [rcx]
0x180033650  lea     rdx, [rsp+120h+var_D0]
0x180033655  mov     rax, [rax+38h]
0x180033659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003365e  mov     ebx, eax
0x180033660  test    eax, eax
0x180033662  jns     short loc_18003366B
0x180033664  mov     edx, 79Ah
0x180033669  jmp     short loc_180033621
0x18003366b  cmp     [rsp+120h+var_D0], esi
0x18003366f  jbe     loc_18003383D
0x180033675  mov     [rsp+120h+string], rsi
0x18003367a  mov     rcx, [rsp+120h+var_E0]
0x18003367f  mov     rax, [rcx]
0x180033682  mov     [rsp+120h+string], rsi
0x180033687  lea     r8, [rsp+120h+string]
0x18003368c  xor     edx, edx
0x18003368e  mov     rax, [rax+30h]
0x180033692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033697  mov     ebx, eax
0x180033699  test    eax, eax
0x18003369b  jns     short loc_1800336C5
0x18003369d  mov     edx, 7A0h; void *
0x1800336a2  mov     rcx, [rbp+28h]; this
0x1800336a6  mov     r9d, eax; char *
0x1800336a9  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800336b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800336b5  nop
0x1800336b6  lea     rcx, [rsp+120h+string]; this
0x1800336bb  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800336c0  jmp     loc_180033635
0x1800336c5  xor     edx, edx; Val
0x1800336c7  lea     r8d, [rdx+4Eh]; Size
0x1800336cb  lea     rcx, [rbp+20h+var_80]; void *
0x1800336cf  call    memset_0
0x1800336d4  xor     edx, edx; length
0x1800336d6  mov     rcx, [rsp+120h+string]; string
0x1800336db  call    cs:__imp_WindowsGetStringRawBuffer
0x1800336e1  mov     rcx, rax; unsigned __int16 *
0x1800336e4  lea     rdx, [rbp+20h+var_80]; unsigned __int16 *
0x1800336e8  call    ?TrimGuidBracket@@YAJPEBGPEAG@Z; TrimGuidBracket(ushort const *,ushort *)
0x1800336ed  mov     ebx, eax
0x1800336ef  test    eax, eax
0x1800336f1  jns     short loc_1800336FA
0x1800336f3  mov     edx, 7A3h
0x1800336f8  jmp     short loc_1800336A2
0x1800336fa  lea     r8, aScheduleToRunO; "Schedule to run OMADMClient by client"
0x180033701  lea     rdx, [rbp+20h+var_80]
0x180033705  lea     rcx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x18003370c  call    cs:__imp_?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x180033712  mov     qword ptr [rsp+120h+var_B0.dwLowDateTime], rsi
0x180033717  lea     rdx, [rsp+120h+var_B0]; struct _FILETIME *
0x18003371c  lea     rcx, [rbp+20h+var_80]; unsigned __int16 *
0x180033720  call    ?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z; GetDeviceCertExpiryTime(ushort const *,_FILETIME *)
0x180033725  mov     ebx, eax
0x180033727  test    eax, eax
0x180033729  jns     short loc_180033735
0x18003372b  mov     edx, 7ACh
0x180033730  jmp     loc_1800336A2
0x180033735  mov     [rsp+120h+var_C0], esi
0x180033739  lea     rdx, [rsp+120h+var_C0]; unsigned int *
0x18003373e  lea     rcx, [rbp+20h+var_80]; unsigned __int16 *
0x180033742  call    ?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z; GetRenewPeriodInSeconds(ushort const *,ulong *)
0x180033747  mov     ebx, eax
0x180033749  test    eax, eax
0x18003374b  jns     short loc_180033757
0x18003374d  mov     edx, 7AFh
0x180033752  jmp     loc_1800336A2
0x180033757  mov     [rsp+120h+var_C4], esi
0x18003375b  lea     r8, [rsp+120h+var_C4]; unsigned int *
0x180033760  mov     edi, 1
0x180033765  mov     edx, edi; int
0x180033767  lea     rcx, [rbp+20h+var_80]; unsigned __int16 *
0x18003376b  call    ?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z; GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)
0x180033770  mov     ebx, eax
0x180033772  test    eax, eax
0x180033774  jns     short loc_180033780
0x180033776  mov     edx, 7B2h
0x18003377b  jmp     loc_1800336A2
0x180033780  mov     [rsp+120h+var_C8], esi
0x180033784  lea     r8, [rsp+120h+var_C8]; unsigned int *
0x180033789  xor     edx, edx; int
0x18003378b  lea     rcx, [rbp+20h+var_80]; unsigned __int16 *
0x18003378f  call    ?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z; GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)
0x180033794  mov     ebx, eax
0x180033796  test    eax, eax
0x180033798  jns     short loc_1800337A4
0x18003379a  mov     edx, 7B5h
0x18003379f  jmp     loc_1800336A2
0x1800337a4  mov     [rsp+120h+var_CC], esi
0x1800337a8  lea     rdx, [rsp+120h+var_CC]; int *
0x1800337ad  lea     rcx, [rbp+20h+var_80]; unsigned __int16 *
0x1800337b1  call    ?IsROBOMode@@YAJPEBGPEAH@Z; IsROBOMode(ushort const *,int *)
0x1800337b6  mov     ebx, eax
0x1800337b8  test    eax, eax
0x1800337ba  jns     short loc_1800337C6
0x1800337bc  mov     edx, 7B8h
0x1800337c1  jmp     loc_1800336A2
0x1800337c6  mov     eax, [rsp+120h+var_CC]
0x1800337ca  mov     [rsp+120h+var_F8], eax; int
0x1800337ce  mov     eax, [rsp+120h+var_C8]
0x1800337d2  mov     [rsp+120h+var_100], eax; unsigned int
0x1800337d6  mov     r9d, [rsp+120h+var_C4]; unsigned int
0x1800337db  mov     r8d, [rsp+120h+var_C0]; unsigned int
0x1800337e0  mov     rdx, qword ptr [rsp+120h+var_B0.dwLowDateTime]; struct _FILETIME
0x1800337e5  lea     rcx, [rbp+20h+var_80]; unsigned __int16 *
0x1800337e9  call    ?SetupAllEnrollmentSchedules@@YAJPEBGU_FILETIME@@KKKH0@Z; SetupAllEnrollmentSchedules(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)
0x1800337ee  mov     ebx, eax
0x1800337f0  test    eax, eax
0x1800337f2  jns     short loc_1800337FE
0x1800337f4  mov     edx, 7C1h
0x1800337f9  jmp     loc_1800336A2
0x1800337fe  mov     [rsp+120h+var_F0], 12h
0x180033806  mov     qword ptr [rsp+120h+var_F8], rsi
0x18003380b  mov     [rsp+120h+var_100], esi
0x18003380f  xor     r9d, r9d
0x180033812  lea     r8d, [r9+2]
0x180033816  mov     edx, edi
0x180033818  lea     rcx, [rbp+20h+var_80]
0x18003381c  call    cs:__imp_OmaDmInitiateSessionAsDevice
0x180033822  mov     ebx, eax
0x180033824  test    eax, eax
0x180033826  jns     short loc_180033832
0x180033828  mov     edx, 7CBh
0x18003382d  jmp     loc_1800336A2
0x180033832  lea     rcx, [rsp+120h+string]; this
0x180033837  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003383c  nop
0x18003383d  lea     rcx, [rsp+120h+var_E0]
0x180033842  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180033847  mov     ebx, esi
0x180033849  lea     rcx, [rsp+120h+var_B8]
0x18003384e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180033853  mov     eax, ebx
0x180033855  mov     rcx, [rbp+20h+var_30]
0x180033859  xor     rcx, rsp; StackCookie
0x18003385c  call    __security_check_cookie
0x180033861  add     rsp, 108h
0x180033868  pop     rdi
0x180033869  pop     rsi
0x18003386a  pop     rbx
0x18003386b  pop     rbp
0x18003386c  retn
```
