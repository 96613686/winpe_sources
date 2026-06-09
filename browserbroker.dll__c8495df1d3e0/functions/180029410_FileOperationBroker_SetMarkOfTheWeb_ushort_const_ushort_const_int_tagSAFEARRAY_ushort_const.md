# FileOperationBroker::SetMarkOfTheWeb(ushort const *,ushort const *,int,tagSAFEARRAY *,ushort const *)

- ea: `0x180029410`
- end: `0x180029827`
- name: `?SetMarkOfTheWeb@FileOperationBroker@@UEAAJPEBG0HPEAUtagSAFEARRAY@@0@Z`
- size: `1047`
- prototype: `int(FileOperationBroker *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int, struct tagSAFEARRAY *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002ce0`
- `0x180003764`
- `0x18000a4d0`
- `0x18000dc74`
- `0x18000e428`
- `0x180026e5c`
- `0x180028ca0`
- `0x180028cc4`
- `0x180029410`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029521`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029651`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029521`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029651`
- `urlmon!CoInternetCreateSecurityManager` at `0x180029597`
- `urlmon!CoInternetCreateSecurityManager` at `0x180029597`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002972d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002972d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180029789`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180029789`
- `WS2_32!GetNameInfoW` at `0x180029761`
- `WS2_32!GetNameInfoW` at `0x180029761`

## string_xrefs

- `0x180029815`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\fileoperationbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall FileOperationBroker::SetMarkOfTheWeb(
        FileOperationBroker *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        struct tagSAFEARRAY *psa,
        const unsigned __int16 *a6)
{
  __int64 v8; // rdx
  int PIC; // ebx
  __int64 v10; // rdx
  unsigned int v11; // r14d
  char v12; // di
  IInternetSecurityManager *v13; // rbx
  HRESULT (__stdcall *QueryInterface)(IInternetSecurityManager *, const IID *const, void **); // rdi
  HRESULT v15; // eax
  int ppv; // [rsp+20h] [rbp-B9h]
  unsigned int v18; // [rsp+40h] [rbp-99h] BYREF
  LPVOID v19; // [rsp+48h] [rbp-91h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-89h] BYREF
  IInternetSecurityManager *ppSM; // [rsp+58h] [rbp-81h] BYREF
  __int64 v22; // [rsp+60h] [rbp-79h] BYREF
  unsigned int v23; // [rsp+68h] [rbp-71h] BYREF
  void *ppvData[2]; // [rsp+70h] [rbp-69h] BYREF
  WCHAR pNodeBuffer[48]; // [rsp+80h] [rbp-59h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+4Fh]

  LODWORD(v22) = a4;
  v18 = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &v18);
  if ( PIC < 0 )
    return (unsigned int)PIC;
  v18 = 4;
  v23 = 4;
  if ( !a3 || wcsnicmp(a3, L"blob:", 5u) )
  {
    PIC = anonymous_namespace_::MapUrlToZone(a3, v8, &v18);
  }
  else
  {
    v18 = -1;
    if ( a6 )
    {
LABEL_9:
      PIC = anonymous_namespace_::MapUrlToZone(a6, v8, &v23);
      if ( PIC < 0 )
        return (unsigned int)PIC;
      v10 = v23;
      goto LABEL_12;
    }
    PIC = -2147024809;
  }
  if ( PIC < 0 )
    return (unsigned int)PIC;
  if ( a6 )
    goto LABEL_9;
  v10 = 0xFFFFFFFFLL;
  v23 = -1;
LABEL_12:
  v11 = anonymous_namespace_::LessTrustedZone(v18, v10);
  v19 = 0;
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v19);
  PIC = CoCreateInstance(&CLSID_PersistentZoneIdentifier, 0, 1u, &GUID_0000010b_0000_0000_c000_000000000046, &v19);
  if ( PIC >= 0 )
  {
    v20 = -1;
    if ( (*(int (__fastcall **)(LPVOID, const unsigned __int16 *, __int64))(*(_QWORD *)v19 + 40LL))(v19, a2, 2) < 0 )
    {
      v12 = 0;
      Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v19);
      Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v19);
      PIC = CoCreateInstance(&CLSID_PersistentZoneIdentifier, 0, 1u, &GUID_0000010b_0000_0000_c000_000000000046, &v19);
    }
    else
    {
      v12 = 1;
      ppvData[0] = 0;
      PIC = Microsoft::WRL::ComPtr<IPersistFile>::As<IZoneIdentifier>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v19,
              (__int64)ppvData);
      if ( PIC >= 0 )
      {
        ppSM = 0;
        Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&ppSM);
        PIC = CoInternetCreateSecurityManager(0, &ppSM, 0);
        if ( PIC >= 0 )
        {
          PIC = ((__int64 (__fastcall *)(IInternetSecurityManager *, const unsigned __int16 *, unsigned int *, _QWORD))ppSM->lpVtbl->MapUrlToZone)(
                  ppSM,
                  a2,
                  &v20,
                  0);
          if ( PIC >= 0
            && v20 < 3
            && (*(int (__fastcall **)(void *))(*(_QWORD *)ppvData[0] + 40LL))(ppvData[0]) >= 0
            && (*(int (__fastcall **)(LPVOID, const unsigned __int16 *, _QWORD))(*(_QWORD *)v19 + 48LL))(v19, a2, 0) >= 0 )
          {
            v20 = -1;
            v12 = 0;
          }
        }
        Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&ppSM);
      }
      Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(ppvData);
    }
    if ( PIC >= 0 )
    {
      ppSM = 0;
      PIC = Microsoft::WRL::ComPtr<IPersistFile>::As<IZoneIdentifier>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v19,
              (__int64)&ppSM);
      if ( PIC >= 0 )
      {
        if ( v12 )
          v11 = anonymous_namespace_::LessTrustedZone(v20, v11);
        if ( v11 >= 3 )
        {
          PIC = ((__int64 (__fastcall *)(IInternetSecurityManager *, _QWORD))ppSM->lpVtbl->GetSecuritySite)(ppSM, v11);
          if ( PIC >= 0 )
          {
            if ( (_DWORD)v22 )
            {
              v22 = 0;
              v13 = ppSM;
              QueryInterface = ppSM->lpVtbl->QueryInterface;
              Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v22);
              if ( ((int (__fastcall *)(IInternetSecurityManager *, GUID *, __int64 *))QueryInterface)(
                     v13,
                     &GUID_31114b0a_accb_4e12_a053_754cb41c1d0f,
                     &v22) >= 0 )
              {
                (*(void (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)v22 + 48LL))(
                  v22,
                  L"HostUrl",
                  a3);
                if ( psa )
                {
                  ppvData[0] = 0;
                  v15 = SafeArrayAccessData(psa, ppvData);
                  if ( v15 < 0 )
                    wil::details::in1diag3::_FailFast_Hr(
                      retaddr,
                      (void *)0x3D1,
                      (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\fileoperationbroker.cpp",
                      (const char *)(unsigned int)v15,
                      ppv);
                  if ( !GetNameInfoW(
                          (const SOCKADDR *)ppvData[0],
                          psa->rgsabound[0].cElements,
                          pNodeBuffer,
                          0x2Fu,
                          0,
                          0,
                          2) )
                    (*(void (__fastcall **)(__int64, const wchar_t *, WCHAR *))(*(_QWORD *)v22 + 48LL))(
                      v22,
                      L"HostIpAddress",
                      pNodeBuffer);
                  SafeArrayUnaccessData(psa);
                }
                if ( a6 )
                  (*(void (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)v22 + 48LL))(
                    v22,
                    L"ReferrerUrl",
                    a6);
              }
              Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v22);
            }
            PIC = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int64))(*(_QWORD *)v19 + 48LL))(
                    v19,
                    a2,
                    1);
          }
        }
      }
      Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&ppSM);
    }
  }
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v19);
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180029410  mov     [rsp-8+arg_0], rbx
0x180029415  push    rbp
0x180029416  push    rsi
0x180029417  push    rdi
0x180029418  push    r12
0x18002941a  push    r13
0x18002941c  push    r14
0x18002941e  push    r15
0x180029420  lea     rbp, [rsp-17h]
0x180029425  sub     rsp, 0F0h
0x18002942c  mov     rax, cs:__security_cookie
0x180029433  xor     rax, rsp
0x180029436  mov     [rbp+47h+var_40], rax
0x18002943a  mov     dword ptr [rbp+47h+var_C0], r9d
0x18002943e  mov     r15, r8
0x180029441  mov     r12, rdx
0x180029444  mov     r13, [rbp+47h+psa]
0x180029448  mov     rsi, [rbp+47h+arg_28]
0x18002944c  mov     [rsp+120h+var_E0], 0
0x180029454  lea     rdx, [rsp+120h+var_E0]; unsigned int *
0x180029459  mov     ecx, 1; unsigned int
0x18002945e  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180029463  mov     ebx, eax
0x180029465  test    eax, eax
0x180029467  js      loc_1800297E9
0x18002946d  mov     eax, 4
0x180029472  mov     [rsp+120h+var_E0], eax
0x180029476  mov     [rbp+47h+var_B8], eax
0x180029479  or      edi, 0FFFFFFFFh
0x18002947c  test    r15, r15
0x18002947f  jz      short loc_1800294A8
0x180029481  lea     r8d, [rax+1]; MaxCount
0x180029485  lea     rdx, aBlob; "blob:"
0x18002948c  mov     rcx, r15; String1
0x18002948f  call    _wcsnicmp
0x180029494  test    eax, eax
0x180029496  jnz     short loc_1800294A8
0x180029498  mov     [rsp+120h+var_E0], edi
0x18002949c  test    rsi, rsi
0x18002949f  jnz     short loc_1800294C4
0x1800294a1  mov     ebx, 80070057h
0x1800294a6  jmp     short loc_1800294B7
0x1800294a8  lea     r8, [rsp+120h+var_E0]
0x1800294ad  mov     rcx, r15
0x1800294b0  call    _anonymous_namespace___MapUrlToZone
0x1800294b5  mov     ebx, eax
0x1800294b7  test    ebx, ebx
0x1800294b9  js      loc_1800297E9
0x1800294bf  test    rsi, rsi
0x1800294c2  jz      short loc_1800294DF
0x1800294c4  lea     r8, [rbp+47h+var_B8]
0x1800294c8  mov     rcx, rsi
0x1800294cb  call    _anonymous_namespace___MapUrlToZone
0x1800294d0  mov     ebx, eax
0x1800294d2  test    eax, eax
0x1800294d4  js      loc_1800297E9
0x1800294da  mov     edx, [rbp+47h+var_B8]
0x1800294dd  jmp     short loc_1800294E4
0x1800294df  mov     edx, edi
0x1800294e1  mov     [rbp+47h+var_B8], edx
0x1800294e4  mov     ecx, [rsp+120h+var_E0]
0x1800294e8  call    _anonymous_namespace___LessTrustedZone
0x1800294ed  mov     r14d, eax
0x1800294f0  mov     [rsp+120h+var_D8], 0
0x1800294f9  lea     rcx, [rsp+120h+var_D8]
0x1800294fe  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180029503  lea     rax, [rsp+120h+var_D8]
0x180029508  mov     [rsp+120h+ppv], rax; ppv
0x18002950d  lea     r9, _GUID_0000010b_0000_0000_c000_000000000046; riid
0x180029514  xor     edx, edx; pUnkOuter
0x180029516  lea     r8d, [rdx+1]; dwClsContext
0x18002951a  lea     rcx, CLSID_PersistentZoneIdentifier; rclsid
0x180029521  call    cs:__imp_CoCreateInstance
0x180029527  mov     ebx, eax
0x180029529  test    eax, eax
0x18002952b  js      loc_1800297DF
0x180029531  mov     [rsp+120h+var_D0], edi
0x180029535  mov     rcx, [rsp+120h+var_D8]
0x18002953a  mov     rax, [rcx]
0x18002953d  mov     r8d, 2
0x180029543  mov     rdx, r12
0x180029546  mov     rax, [rax+28h]
0x18002954a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002954f  test    eax, eax
0x180029551  js      loc_18002961C
0x180029557  mov     dil, 1
0x18002955a  mov     [rbp+47h+ppvData], 0
0x180029562  lea     rdx, [rbp+47h+ppvData]
0x180029566  lea     rcx, [rsp+120h+var_D8]
0x18002956b  call    ??$As@UIZoneIdentifier@@@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIZoneIdentifier@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IPersistFile>::As<IZoneIdentifier>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IZoneIdentifier>>)
0x180029570  mov     ebx, eax
0x180029572  test    eax, eax
0x180029574  js      loc_180029611
0x18002957a  mov     [rsp+120h+ppSM], 0
0x180029583  lea     rcx, [rsp+120h+ppSM]
0x180029588  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18002958d  xor     r8d, r8d; dwReserved
0x180029590  lea     rdx, [rsp+120h+ppSM]; ppSM
0x180029595  xor     ecx, ecx; pSP
0x180029597  call    cs:__imp_CoInternetCreateSecurityManager
0x18002959d  mov     ebx, eax
0x18002959f  test    eax, eax
0x1800295a1  js      short loc_180029606
0x1800295a3  mov     rcx, [rsp+120h+ppSM]
0x1800295a8  mov     rax, [rcx]
0x1800295ab  xor     r9d, r9d
0x1800295ae  lea     r8, [rsp+120h+var_D0]
0x1800295b3  mov     rdx, r12
0x1800295b6  mov     rax, [rax+28h]
0x1800295ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295bf  mov     ebx, eax
0x1800295c1  test    eax, eax
0x1800295c3  js      short loc_180029606
0x1800295c5  cmp     [rsp+120h+var_D0], 3
0x1800295ca  jnb     short loc_180029606
0x1800295cc  mov     rcx, [rbp+47h+ppvData]
0x1800295d0  mov     rax, [rcx]
0x1800295d3  mov     rax, [rax+28h]
0x1800295d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295dc  test    eax, eax
0x1800295de  js      short loc_180029606
0x1800295e0  mov     rcx, [rsp+120h+var_D8]
0x1800295e5  mov     rax, [rcx]
0x1800295e8  xor     r8d, r8d
0x1800295eb  mov     rdx, r12
0x1800295ee  mov     rax, [rax+30h]
0x1800295f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295f7  test    eax, eax
0x1800295f9  js      short loc_180029606
0x1800295fb  mov     [rsp+120h+var_D0], 0FFFFFFFFh
0x180029603  xor     dil, dil
0x180029606  lea     rcx, [rsp+120h+ppSM]
0x18002960b  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180029610  nop
0x180029611  lea     rcx, [rbp+47h+ppvData]
0x180029615  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18002961a  jmp     short loc_180029659
0x18002961c  xor     dil, dil
0x18002961f  lea     rcx, [rsp+120h+var_D8]
0x180029624  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180029629  lea     rcx, [rsp+120h+var_D8]
0x18002962e  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180029633  lea     rax, [rsp+120h+var_D8]
0x180029638  mov     [rsp+120h+ppv], rax; int
0x18002963d  lea     r9, _GUID_0000010b_0000_0000_c000_000000000046; riid
0x180029644  xor     edx, edx; pUnkOuter
0x180029646  lea     r8d, [rdx+1]; dwClsContext
0x18002964a  lea     rcx, CLSID_PersistentZoneIdentifier; rclsid
0x180029651  call    cs:__imp_CoCreateInstance
0x180029657  mov     ebx, eax
0x180029659  test    ebx, ebx
0x18002965b  js      loc_1800297DF
0x180029661  mov     [rsp+120h+ppSM], 0
0x18002966a  lea     rdx, [rsp+120h+ppSM]
0x18002966f  lea     rcx, [rsp+120h+var_D8]
0x180029674  call    ??$As@UIZoneIdentifier@@@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIZoneIdentifier@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IPersistFile>::As<IZoneIdentifier>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IZoneIdentifier>>)
0x180029679  mov     ebx, eax
0x18002967b  test    eax, eax
0x18002967d  js      loc_1800297D4
0x180029683  test    dil, dil
0x180029686  jz      short loc_180029697
0x180029688  mov     edx, r14d
0x18002968b  mov     ecx, [rsp+120h+var_D0]
0x18002968f  call    _anonymous_namespace___LessTrustedZone
0x180029694  mov     r14d, eax
0x180029697  cmp     r14d, 3
0x18002969b  jb      loc_1800297D4
0x1800296a1  mov     rcx, [rsp+120h+ppSM]
0x1800296a6  mov     rax, [rcx]
0x1800296a9  mov     edx, r14d
0x1800296ac  mov     rax, [rax+20h]
0x1800296b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296b5  mov     ebx, eax
0x1800296b7  xor     r14d, r14d
0x1800296ba  test    eax, eax
0x1800296bc  js      loc_1800297D4
0x1800296c2  cmp     dword ptr [rbp+47h+var_C0], r14d
0x1800296c6  jz      loc_1800297B8
0x1800296cc  mov     [rbp+47h+var_C0], r14
0x1800296d0  mov     rbx, [rsp+120h+ppSM]
0x1800296d5  mov     rax, [rbx]
0x1800296d8  mov     rdi, [rax]
0x1800296db  lea     rcx, [rbp+47h+var_C0]
0x1800296df  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x1800296e4  lea     r8, [rbp+47h+var_C0]
0x1800296e8  lea     rdx, _GUID_31114b0a_accb_4e12_a053_754cb41c1d0f
0x1800296ef  mov     rcx, rbx
0x1800296f2  mov     rax, rdi
0x1800296f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296fa  nop
0x1800296fb  test    eax, eax
0x1800296fd  js      loc_1800297AF
0x180029703  mov     rcx, [rbp+47h+var_C0]
0x180029707  mov     rax, [rcx]
0x18002970a  mov     r8, r15
0x18002970d  lea     rdx, aHosturl; "HostUrl"
0x180029714  mov     rax, [rax+30h]
0x180029718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002971d  test    r13, r13
0x180029720  jz      short loc_18002978F
0x180029722  mov     [rbp+47h+ppvData], r14
0x180029726  lea     rdx, [rbp+47h+ppvData]; ppvData
0x18002972a  mov     rcx, r13; psa
0x18002972d  call    cs:__imp_SafeArrayAccessData
0x180029733  mov     rcx, [rbp+4Fh]; this
0x180029737  test    eax, eax
0x180029739  js      loc_180029812
0x18002973f  mov     [rsp+120h+Flags], 2; Flags
0x180029747  mov     [rsp+120h+ServiceBufferSize], r14d; ServiceBufferSize
0x18002974c  mov     [rsp+120h+ppv], r14; pServiceBuffer
0x180029751  lea     r9d, [r14+2Fh]; NodeBufferSize
0x180029755  lea     r8, [rbp+47h+pNodeBuffer]; pNodeBuffer
0x180029759  mov     edx, [r13+18h]; SockaddrLength
0x18002975d  mov     rcx, [rbp+47h+ppvData]; pSockaddr
0x180029761  call    cs:__imp_GetNameInfoW
0x180029767  test    eax, eax
0x180029769  jnz     short loc_180029786
0x18002976b  mov     rcx, [rbp+47h+var_C0]
0x18002976f  mov     rax, [rcx]
0x180029772  lea     r8, [rbp+47h+pNodeBuffer]
0x180029776  lea     rdx, aHostipaddress; "HostIpAddress"
0x18002977d  mov     rax, [rax+30h]
0x180029781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029786  mov     rcx, r13; psa
0x180029789  call    cs:__imp_SafeArrayUnaccessData
0x18002978f  test    rsi, rsi
0x180029792  jz      short loc_1800297AF
0x180029794  mov     rcx, [rbp+47h+var_C0]
0x180029798  mov     rax, [rcx]
0x18002979b  mov     r8, rsi
0x18002979e  lea     rdx, aReferrerurl; "ReferrerUrl"
0x1800297a5  mov     rax, [rax+30h]
0x1800297a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297ae  nop
0x1800297af  lea     rcx, [rbp+47h+var_C0]
0x1800297b3  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x1800297b8  mov     rcx, [rsp+120h+var_D8]
0x1800297bd  mov     rax, [rcx]
0x1800297c0  mov     r8d, 1
0x1800297c6  mov     rdx, r12
0x1800297c9  mov     rax, [rax+30h]
0x1800297cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297d2  mov     ebx, eax
0x1800297d4  lea     rcx, [rsp+120h+ppSM]
0x1800297d9  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x1800297de  nop
0x1800297df  lea     rcx, [rsp+120h+var_D8]
0x1800297e4  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x1800297e9  mov     eax, ebx
0x1800297eb  mov     rcx, [rbp+47h+var_40]
0x1800297ef  xor     rcx, rsp; StackCookie
0x1800297f2  call    __security_check_cookie
0x1800297f7  mov     rbx, [rsp+120h+arg_0]
0x1800297ff  add     rsp, 0F0h
0x180029806  pop     r15
0x180029808  pop     r14
0x18002980a  pop     r13
0x18002980c  pop     r12
0x18002980e  pop     rdi
0x18002980f  pop     rsi
0x180029810  pop     rbp
0x180029811  retn
0x180029812  mov     r9d, eax; char *
0x180029815  lea     r8, aOnecoreuapInet_7; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18002981c  mov     edx, 3D1h; void *
0x180029821  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
