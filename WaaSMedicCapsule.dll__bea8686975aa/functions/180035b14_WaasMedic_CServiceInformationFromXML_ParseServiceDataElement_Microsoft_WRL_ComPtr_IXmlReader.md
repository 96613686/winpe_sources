# WaasMedic::CServiceInformationFromXML::ParseServiceDataElement(Microsoft::WRL::ComPtr<IXmlReader>)

- ea: `0x180035b14`
- end: `0x180035ef5`
- name: `?ParseServiceDataElement@CServiceInformationFromXML@WaasMedic@@QEAAJV?$ComPtr@UIXmlReader@@@WRL@Microsoft@@@Z`
- size: `993`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800344c4`

## callees

- `0x180009a54`
- `0x180024ff0`
- `0x1800250e0`
- `0x18002543c`
- `0x180032d90`
- `0x180035a6c`
- `0x180035b14`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035c2f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035c73`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035cbc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035ce3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035cfe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035d4e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035db8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035dfc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035e6b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035eb3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035c2f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035c73`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035cbc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035ce3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035cfe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035d4e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035db8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035dfc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035e6b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035eb3`

## string_xrefs

- `0x180035d2b`: `ParseServiceAttribute failed looking for Service Error control attribute [%s] hr = 0x%08x`
- `0x180035c57`: `CreateMultisz failed for attribute name [%s] and value [%s] hr = 0x%08x`
- `0x180035c9d`: `CreateMultisz failed for attribute name [%s] and value [%s] hr = 0x%08x`
- `0x180035e1e`: `ParseServiceAttribute failed to make a copy of Service start attribute [%s] hr = 0x%08x`
- `0x180035de5`: `ParseServiceAttribute failed looking for Service SID type attribute [%s] hr = 0x%08x`
- `0x180035e9c`: `ParseServiceAttribute failed looking for Service launch protected attribute [%s] hr = 0x%08x`
- `0x180035e54`: `ParseServiceAttribute failed looking for Service start attribute [%s] hr = 0x%08x`
- `0x180035ee8`: `ParseServiceAttribute failed looking for Service type attribute [%s] hr = 0x%08x`
- `0x180035c68`: `RequiredPrivileges`
- `0x180035dad`: `sidType`
- `0x180035cb1`: `imagePath`
- `0x180035c28`: `dependOnService`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaasMedic::CServiceInformationFromXML::ParseServiceDataElement(__int64 a1, _QWORD *a2)
{
  int i; // ebx
  __int64 v5; // rcx
  unsigned __int16 **v6; // r8
  int Multisz; // eax
  unsigned __int16 **v8; // r8
  int v9; // eax
  unsigned __int16 **v10; // r8
  int v11; // eax
  unsigned __int16 **v12; // r8
  const unsigned __int16 *v13; // rdx
  WaasMedic::CServiceInformationFromXML *v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  WaasMedic::CServiceInformationFromXML *v18; // rcx
  int v19; // eax
  unsigned __int16 **v20; // r8
  int v21; // eax
  WaasMedic::CServiceInformationFromXML *v22; // rcx
  int v23; // eax
  WaasMedic::CServiceInformationFromXML *v24; // rcx
  int v25; // eax
  WaasMedic::CServiceInformationFromXML *v26; // rcx
  int v27; // eax
  unsigned int *v28; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  LPCWSTR lpSrc; // [rsp+70h] [rbp+40h] BYREF
  _WORD *v31; // [rsp+78h] [rbp+48h] BYREF

  if ( !*a2 )
  {
    i = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x365,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
      (const char *)0x80004003LL,
      (int)v28);
    v5 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    return (unsigned int)i;
  }
  for ( i = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 64LL))(*a2);
        !i;
        i = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 72LL))(*a2) )
  {
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 152LL))(*a2) )
    {
      v31 = 0;
      lpSrc = 0;
      i = (*(__int64 (__fastcall **)(_QWORD, _WORD **, _QWORD))(*(_QWORD *)*a2 + 112LL))(*a2, &v31, 0);
      if ( i < 0 )
        break;
      i = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR *, _QWORD))(*(_QWORD *)*a2 + 128LL))(*a2, &lpSrc, 0);
      if ( i < 0 )
        break;
      if ( v31 && *v31 && lpSrc && *lpSrc )
      {
        if ( !(unsigned int)_o__wcsicmp(v31, L"dependOnService") )
        {
          Multisz = WaasMedic::CreateMultisz((WaasMedic *)lpSrc, (const unsigned __int16 *)(a1 + 16), v6);
          i = Multisz;
          if ( Multisz < 0 )
          {
            LODWORD(v28) = Multisz;
            LogLevelW(2u, L"CreateMultisz failed for attribute name [%s] and value [%s] hr = 0x%08x", lpSrc, lpSrc, v28);
            i = 0;
          }
        }
        if ( (unsigned int)_o__wcsicmp(v31, L"RequiredPrivileges") )
        {
          if ( !(unsigned int)_o__wcsicmp(v31, L"imagePath") )
          {
            v11 = WaasMedic::SafeExpandEnvironmentString(lpSrc, (const unsigned __int16 *)(a1 + 32), v10);
            goto LABEL_29;
          }
          if ( !(unsigned int)_o__wcsicmp(v31, L"name") )
          {
            v13 = (const unsigned __int16 *)(a1 + 8);
            goto LABEL_28;
          }
          if ( (unsigned int)_o__wcsicmp(v31, L"errorControl") )
          {
            if ( !(unsigned int)_o__wcsicmp(v31, L"objectName") )
            {
              v13 = (const unsigned __int16 *)(a1 + 40);
LABEL_28:
              v11 = WaasMedic::SafeAllocString((WaasMedic *)lpSrc, v13, v12);
LABEL_29:
              i = v11;
LABEL_30:
              if ( i < 0 )
                break;
              continue;
            }
            if ( (unsigned int)_o__wcsicmp(v31, L"sidType") )
            {
              if ( (unsigned int)_o__wcsicmp(v31, L"start") )
              {
                if ( (unsigned int)_o__wcsicmp(v31, L"LaunchProtected") )
                {
                  if ( (unsigned int)_o__wcsicmp(v31, L"type") )
                    goto LABEL_30;
                  v27 = WaasMedic::CServiceInformationFromXML::ParseServiceAttribute(
                          v26,
                          (const struct WaasMedic::_SERVICE_ATTRIBUTE *const)&qword_180066140,
                          6u,
                          lpSrc,
                          (unsigned int *)(a1 + 72));
                  if ( v27 < 0 )
                    LogLevelW(
                      2u,
                      L"ParseServiceAttribute failed looking for Service type attribute [%s] hr = 0x%08x",
                      lpSrc,
                      (unsigned int)v27);
                }
                else
                {
                  v25 = WaasMedic::CServiceInformationFromXML::ParseServiceAttribute(
                          v24,
                          (const struct WaasMedic::_SERVICE_ATTRIBUTE *const)&qword_180066090,
                          4u,
                          lpSrc,
                          (unsigned int *)(a1 + 76));
                  if ( v25 < 0 )
                    LogLevelW(
                      2u,
                      L"ParseServiceAttribute failed looking for Service launch protected attribute [%s] hr = 0x%08x",
                      lpSrc,
                      (unsigned int)v25);
                }
              }
              else
              {
                v21 = WaasMedic::SafeAllocString((WaasMedic *)lpSrc, (const unsigned __int16 *)(a1 + 64), v20);
                if ( v21 < 0 )
                  LogLevelW(
                    2u,
                    L"ParseServiceAttribute failed to make a copy of Service start attribute [%s] hr = 0x%08x",
                    lpSrc,
                    (unsigned int)v21);
                v23 = WaasMedic::CServiceInformationFromXML::ParseServiceAttribute(
                        v22,
                        (const struct WaasMedic::_SERVICE_ATTRIBUTE *const)&qword_1800661A0,
                        6u,
                        lpSrc,
                        (unsigned int *)(a1 + 56));
                if ( v23 < 0 )
                  LogLevelW(
                    2u,
                    L"ParseServiceAttribute failed looking for Service start attribute [%s] hr = 0x%08x",
                    lpSrc,
                    (unsigned int)v23);
              }
            }
            else
            {
              v19 = WaasMedic::CServiceInformationFromXML::ParseServiceAttribute(
                      v18,
                      (const struct WaasMedic::_SERVICE_ATTRIBUTE *const)&qword_180066110,
                      3u,
                      lpSrc,
                      (unsigned int *)(a1 + 48));
              if ( v19 < 0 )
                LogLevelW(
                  2u,
                  L"ParseServiceAttribute failed looking for Service SID type attribute [%s] hr = 0x%08x",
                  lpSrc,
                  (unsigned int)v19);
            }
          }
          else
          {
            v15 = WaasMedic::CServiceInformationFromXML::ParseServiceAttribute(
                    v14,
                    (const struct WaasMedic::_SERVICE_ATTRIBUTE *const)&qword_1800660D0,
                    4u,
                    lpSrc,
                    (unsigned int *)(a1 + 52));
            if ( v15 < 0 )
              LogLevelW(
                2u,
                L"ParseServiceAttribute failed looking for Service Error control attribute [%s] hr = 0x%08x",
                lpSrc,
                (unsigned int)v15);
          }
        }
        else
        {
          v9 = WaasMedic::CreateMultisz((WaasMedic *)lpSrc, (const unsigned __int16 *)(a1 + 24), v8);
          if ( v9 < 0 )
          {
            LODWORD(v28) = v9;
            LogLevelW(2u, L"CreateMultisz failed for attribute name [%s] and value [%s] hr = 0x%08x", lpSrc, lpSrc, v28);
          }
        }
      }
    }
  }
  v16 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return (unsigned int)i;
}

```

## disassembly

```asm
0x180035b14  mov     [rsp-28h+arg_8], rdx
0x180035b19  push    rbp
0x180035b1a  push    rbx
0x180035b1b  push    rsi
0x180035b1c  push    rdi
0x180035b1d  push    r15
0x180035b1f  mov     rbp, rsp
0x180035b22  sub     rsp, 30h
0x180035b26  mov     rsi, rdx
0x180035b29  mov     rdi, rcx
0x180035b2c  mov     rcx, [rdx]
0x180035b2f  test    rcx, rcx
0x180035b32  jnz     short loc_180035B73
0x180035b34  mov     rcx, [rbp+28h]; this
0x180035b38  mov     ebx, 80004003h
0x180035b3d  mov     r9d, ebx; char *
0x180035b40  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180035b47  mov     edx, 365h; void *
0x180035b4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035b51  nop
0x180035b52  mov     rcx, [rsi]
0x180035b55  test    rcx, rcx
0x180035b58  jz      short loc_180035B6E
0x180035b5a  mov     qword ptr [rsi], 0
0x180035b61  mov     rdx, [rcx]
0x180035b64  mov     rax, [rdx+10h]
0x180035b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b6d  nop
0x180035b6e  jmp     loc_180035DA0
0x180035b73  mov     rax, [rcx]
0x180035b76  mov     rax, [rax+40h]
0x180035b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b7f  mov     ebx, eax
0x180035b81  test    eax, eax
0x180035b83  jnz     loc_180035D84
0x180035b89  lea     r15d, [rax+2]
0x180035b8d  mov     rcx, [rsi]
0x180035b90  mov     rax, [rcx]
0x180035b93  mov     rax, [rax+98h]
0x180035b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b9f  test    eax, eax
0x180035ba1  jnz     loc_180035D6B
0x180035ba7  mov     [rbp+arg_18], 0
0x180035baf  mov     [rbp+lpSrc], 0
0x180035bb7  mov     rcx, [rsi]
0x180035bba  mov     rax, [rcx]
0x180035bbd  xor     r8d, r8d
0x180035bc0  lea     rdx, [rbp+arg_18]
0x180035bc4  mov     rax, [rax+70h]
0x180035bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bcd  mov     ebx, eax
0x180035bcf  test    eax, eax
0x180035bd1  js      loc_180035D84
0x180035bd7  mov     rcx, [rsi]
0x180035bda  mov     rax, [rcx]
0x180035bdd  xor     r8d, r8d
0x180035be0  lea     rdx, [rbp+lpSrc]
0x180035be4  mov     rax, [rax+80h]
0x180035beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bf0  mov     ebx, eax
0x180035bf2  test    eax, eax
0x180035bf4  js      loc_180035D84
0x180035bfa  mov     rcx, [rbp+arg_18]
0x180035bfe  test    rcx, rcx
0x180035c01  jz      loc_180035D6B
0x180035c07  xor     eax, eax
0x180035c09  cmp     ax, [rcx]
0x180035c0c  jz      loc_180035D6B
0x180035c12  mov     rdx, [rbp+lpSrc]
0x180035c16  test    rdx, rdx
0x180035c19  jz      loc_180035D6B
0x180035c1f  cmp     ax, [rdx]
0x180035c22  jz      loc_180035D6B
0x180035c28  lea     rdx, aDependonservic; "dependOnService"
0x180035c2f  call    cs:__imp__o__wcsicmp
0x180035c35  test    eax, eax
0x180035c37  jnz     short loc_180035C68
0x180035c39  lea     rdx, [rdi+10h]; unsigned __int16 *
0x180035c3d  mov     rcx, [rbp+lpSrc]; this
0x180035c41  call    ?CreateMultisz@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::CreateMultisz(ushort const *,ushort * *)
0x180035c46  mov     ebx, eax
0x180035c48  test    eax, eax
0x180035c4a  jns     short loc_180035C68
0x180035c4c  mov     dword ptr [rsp+30h+var_10], eax
0x180035c50  mov     r8, [rbp+lpSrc]
0x180035c54  mov     r9, r8
0x180035c57  lea     rdx, aCreatemultiszF; "CreateMultisz failed for attribute name"...
0x180035c5e  mov     ecx, r15d; unsigned __int8
0x180035c61  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180035c66  xor     ebx, ebx
0x180035c68  lea     rdx, aRequiredprivil; "RequiredPrivileges"
0x180035c6f  mov     rcx, [rbp+arg_18]
0x180035c73  call    cs:__imp__o__wcsicmp
0x180035c79  test    eax, eax
0x180035c7b  jnz     short loc_180035CB1
0x180035c7d  lea     rdx, [rdi+18h]; unsigned __int16 *
0x180035c81  mov     rcx, [rbp+lpSrc]; this
0x180035c85  call    ?CreateMultisz@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::CreateMultisz(ushort const *,ushort * *)
0x180035c8a  test    eax, eax
0x180035c8c  jns     loc_180035D6B
0x180035c92  mov     dword ptr [rsp+30h+var_10], eax
0x180035c96  mov     r8, [rbp+lpSrc]
0x180035c9a  mov     r9, r8
0x180035c9d  lea     rdx, aCreatemultiszF; "CreateMultisz failed for attribute name"...
0x180035ca4  mov     ecx, r15d; unsigned __int8
0x180035ca7  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180035cac  jmp     loc_180035D6B
0x180035cb1  lea     rdx, aImagepath; "imagePath"
0x180035cb8  mov     rcx, [rbp+arg_18]
0x180035cbc  call    cs:__imp__o__wcsicmp
0x180035cc2  test    eax, eax
0x180035cc4  jnz     short loc_180035CD8
0x180035cc6  lea     rdx, [rdi+20h]; unsigned __int16 *
0x180035cca  mov     rcx, [rbp+lpSrc]; lpSrc
0x180035cce  call    ?SafeExpandEnvironmentString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeExpandEnvironmentString(ushort const *,ushort * *)
0x180035cd3  jmp     loc_180035D65
0x180035cd8  lea     rdx, aName_0; "name"
0x180035cdf  mov     rcx, [rbp+arg_18]
0x180035ce3  call    cs:__imp__o__wcsicmp
0x180035ce9  test    eax, eax
0x180035ceb  jnz     short loc_180035CF3
0x180035ced  lea     rdx, [rdi+8]
0x180035cf1  jmp     short loc_180035D5C
0x180035cf3  lea     rdx, aErrorcontrol; "errorControl"
0x180035cfa  mov     rcx, [rbp+arg_18]
0x180035cfe  call    cs:__imp__o__wcsicmp
0x180035d04  test    eax, eax
0x180035d06  jnz     short loc_180035D43
0x180035d08  lea     rax, [rdi+34h]
0x180035d0c  mov     [rsp+30h+var_10], rax; unsigned int *
0x180035d11  mov     r9, [rbp+lpSrc]; unsigned __int16 *
0x180035d15  mov     r8d, 4; unsigned int
0x180035d1b  lea     rdx, qword_1800660D0; struct WaasMedic::_SERVICE_ATTRIBUTE *
0x180035d22  call    ?ParseServiceAttribute@CServiceInformationFromXML@WaasMedic@@QEAAJQEBU_SERVICE_ATTRIBUTE@2@KPEBGPEAK@Z; WaasMedic::CServiceInformationFromXML::ParseServiceAttribute(WaasMedic::_SERVICE_ATTRIBUTE const * const,ulong,ushort const *,ulong *)
0x180035d27  test    eax, eax
0x180035d29  jns     short loc_180035D6B
0x180035d2b  lea     rdx, aParseserviceat_3; "ParseServiceAttribute failed looking fo"...
0x180035d32  mov     r9d, eax
0x180035d35  mov     r8, [rbp+lpSrc]
0x180035d39  mov     ecx, r15d; unsigned __int8
0x180035d3c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180035d41  jmp     short loc_180035D6B
0x180035d43  lea     rdx, aObjectname; "objectName"
0x180035d4a  mov     rcx, [rbp+arg_18]
0x180035d4e  call    cs:__imp__o__wcsicmp
0x180035d54  test    eax, eax
0x180035d56  jnz     short loc_180035DAD
0x180035d58  lea     rdx, [rdi+28h]; unsigned __int16 *
0x180035d5c  mov     rcx, [rbp+lpSrc]; this
0x180035d60  call    ?SafeAllocString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeAllocString(ushort const *,ushort * *)
0x180035d65  mov     ebx, eax
0x180035d67  test    ebx, ebx
0x180035d69  js      short loc_180035D84
0x180035d6b  mov     rcx, [rsi]
0x180035d6e  mov     rax, [rcx]
0x180035d71  mov     rax, [rax+48h]
0x180035d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d7a  mov     ebx, eax
0x180035d7c  test    eax, eax
0x180035d7e  jz      loc_180035B8D
0x180035d84  mov     rcx, [rsi]
0x180035d87  test    rcx, rcx
0x180035d8a  jz      short loc_180035DA0
0x180035d8c  mov     qword ptr [rsi], 0
0x180035d93  mov     rax, [rcx]
0x180035d96  mov     rax, [rax+10h]
0x180035d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d9f  nop
0x180035da0  mov     eax, ebx
0x180035da2  add     rsp, 30h
0x180035da6  pop     r15
0x180035da8  pop     rdi
0x180035da9  pop     rsi
0x180035daa  pop     rbx
0x180035dab  pop     rbp
0x180035dac  retn
0x180035dad  lea     rdx, aSidtype; "sidType"
0x180035db4  mov     rcx, [rbp+arg_18]
0x180035db8  call    cs:__imp__o__wcsicmp
0x180035dbe  test    eax, eax
0x180035dc0  jnz     short loc_180035DF1
0x180035dc2  lea     rax, [rdi+30h]
0x180035dc6  mov     [rsp+30h+var_10], rax; unsigned int *
0x180035dcb  mov     r9, [rbp+lpSrc]; unsigned __int16 *
0x180035dcf  mov     r8d, 3; unsigned int
0x180035dd5  lea     rdx, qword_180066110; struct WaasMedic::_SERVICE_ATTRIBUTE *
0x180035ddc  call    ?ParseServiceAttribute@CServiceInformationFromXML@WaasMedic@@QEAAJQEBU_SERVICE_ATTRIBUTE@2@KPEBGPEAK@Z; WaasMedic::CServiceInformationFromXML::ParseServiceAttribute(WaasMedic::_SERVICE_ATTRIBUTE const * const,ulong,ushort const *,ulong *)
0x180035de1  test    eax, eax
0x180035de3  jns     short loc_180035D6B
0x180035de5  lea     rdx, aParseserviceat_2; "ParseServiceAttribute failed looking fo"...
0x180035dec  jmp     loc_180035D32
0x180035df1  lea     rdx, aStart; "start"
0x180035df8  mov     rcx, [rbp+arg_18]
0x180035dfc  call    cs:__imp__o__wcsicmp
0x180035e02  test    eax, eax
0x180035e04  jnz     short loc_180035E60
0x180035e06  lea     rdx, [rdi+40h]; unsigned __int16 *
0x180035e0a  mov     rcx, [rbp+lpSrc]; this
0x180035e0e  call    ?SafeAllocString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeAllocString(ushort const *,ushort * *)
0x180035e13  test    eax, eax
0x180035e15  jns     short loc_180035E2D
0x180035e17  mov     r9d, eax
0x180035e1a  mov     r8, [rbp+lpSrc]
0x180035e1e  lea     rdx, aParseserviceat_1; "ParseServiceAttribute failed to make a "...
0x180035e25  mov     ecx, r15d; unsigned __int8
0x180035e28  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180035e2d  lea     rax, [rdi+38h]
0x180035e31  mov     [rsp+30h+var_10], rax; unsigned int *
0x180035e36  mov     r9, [rbp+lpSrc]; unsigned __int16 *
0x180035e3a  mov     r8d, 6; unsigned int
0x180035e40  lea     rdx, qword_1800661A0; struct WaasMedic::_SERVICE_ATTRIBUTE *
0x180035e47  call    ?ParseServiceAttribute@CServiceInformationFromXML@WaasMedic@@QEAAJQEBU_SERVICE_ATTRIBUTE@2@KPEBGPEAK@Z; WaasMedic::CServiceInformationFromXML::ParseServiceAttribute(WaasMedic::_SERVICE_ATTRIBUTE const * const,ulong,ushort const *,ulong *)
0x180035e4c  test    eax, eax
0x180035e4e  jns     loc_180035D6B
0x180035e54  lea     rdx, aParseserviceat_0; "ParseServiceAttribute failed looking fo"...
0x180035e5b  jmp     loc_180035D32
0x180035e60  lea     rdx, aLaunchprotecte_0; "LaunchProtected"
0x180035e67  mov     rcx, [rbp+arg_18]
0x180035e6b  call    cs:__imp__o__wcsicmp
0x180035e71  test    eax, eax
0x180035e73  jnz     short loc_180035EA8
0x180035e75  lea     rax, [rdi+4Ch]
0x180035e79  mov     [rsp+30h+var_10], rax; unsigned int *
0x180035e7e  mov     r9, [rbp+lpSrc]; unsigned __int16 *
0x180035e82  mov     r8d, 4; unsigned int
0x180035e88  lea     rdx, qword_180066090; struct WaasMedic::_SERVICE_ATTRIBUTE *
0x180035e8f  call    ?ParseServiceAttribute@CServiceInformationFromXML@WaasMedic@@QEAAJQEBU_SERVICE_ATTRIBUTE@2@KPEBGPEAK@Z; WaasMedic::CServiceInformationFromXML::ParseServiceAttribute(WaasMedic::_SERVICE_ATTRIBUTE const * const,ulong,ushort const *,ulong *)
0x180035e94  test    eax, eax
0x180035e96  jns     loc_180035D6B
0x180035e9c  lea     rdx, aParseserviceat; "ParseServiceAttribute failed looking fo"...
0x180035ea3  jmp     loc_180035D32
0x180035ea8  lea     rdx, aType_0; "type"
0x180035eaf  mov     rcx, [rbp+arg_18]
0x180035eb3  call    cs:__imp__o__wcsicmp
0x180035eb9  test    eax, eax
0x180035ebb  jnz     loc_180035D67
0x180035ec1  lea     rax, [rdi+48h]
0x180035ec5  mov     [rsp+30h+var_10], rax; unsigned int *
0x180035eca  mov     r9, [rbp+lpSrc]; unsigned __int16 *
0x180035ece  mov     r8d, 6; unsigned int
0x180035ed4  lea     rdx, qword_180066140; struct WaasMedic::_SERVICE_ATTRIBUTE *
0x180035edb  call    ?ParseServiceAttribute@CServiceInformationFromXML@WaasMedic@@QEAAJQEBU_SERVICE_ATTRIBUTE@2@KPEBGPEAK@Z; WaasMedic::CServiceInformationFromXML::ParseServiceAttribute(WaasMedic::_SERVICE_ATTRIBUTE const * const,ulong,ushort const *,ulong *)
0x180035ee0  test    eax, eax
0x180035ee2  jns     loc_180035D6B
0x180035ee8  lea     rdx, aParseserviceat_4; "ParseServiceAttribute failed looking fo"...
0x180035eef  jmp     loc_180035D32
```
