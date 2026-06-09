# CAutoplayDialog::_UpdateConsent(IAutoplayHandler *)

- ea: `0x180113304`
- end: `0x18011367c`
- name: `?_UpdateConsent@CAutoplayDialog@@AEAAJPEAUIAutoplayHandler@@@Z`
- size: `888`
- prototype: `__int64 __fastcall(CAutoplayDialog *__hidden this, struct IAutoplayHandler *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180199174`

## callees

- `0x180009dd0`
- `0x180025710`
- `0x180113304`
- `0x180142e10`
- `0x180144f2c`
- `0x180144f94`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113419`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801135fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011360d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801135fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011360d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011361e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011361e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180113544`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180113544`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180113584`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180113584`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180113409`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180113409`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1801135ec`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1801135ec`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1801134de`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1801134de`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1801133b6`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1801133b6`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1801133e5`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1801133e5`

## pseudocode

```c
__int64 __fastcall CAutoplayDialog::_UpdateConsent(CAutoplayDialog *this, struct IAutoplayHandler *a2, __int64 a3)
{
  __int64 v5; // rax
  int ObjectProperties; // ebx
  __int64 v7; // r8
  LONG v8; // eax
  signed int LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  PCWSTR packageFullName; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR *v20; // [rsp+70h] [rbp-90h] BYREF
  int v21; // [rsp+78h] [rbp-88h]
  __int64 v22; // [rsp+7Ch] [rbp-84h]
  int v23; // [rsp+84h] [rbp-7Ch]
  __int64 v24; // [rsp+88h] [rbp-78h]
  PSID Sid[2]; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+F0h] [rbp-10h] BYREF

  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_TWINUI_PUBLISHER_Context, AutoPlay_Broker_Device_Start, a3, 1, Sid);
  v5 = *(_QWORD *)a2;
  packageFullName = 0;
  ObjectProperties = (*(__int64 (__fastcall **)(struct IAutoplayHandler *, PCWSTR *))(v5 + 200))(a2, &packageFullName);
  if ( ObjectProperties >= 0 && packageFullName && *packageFullName )
  {
    packageFamilyNameLength = 65;
    v8 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName);
    ObjectProperties = v8;
    if ( v8 > 0 )
      ObjectProperties = (unsigned __int16)v8 | 0x80070000;
    if ( ObjectProperties >= 0 )
    {
      Sid[0] = 0;
      ObjectProperties = AppContainerDeriveSidFromMoniker(packageFamilyName, Sid);
      if ( ObjectProperties >= 0 )
      {
        StringSid = 0;
        if ( ConvertSidToStringSidW(Sid[0], &StringSid) )
        {
          if ( dword_1804CF250 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + (unsigned int)tls_index)
                                           + 4LL) )
          {
            Init_thread_header(&dword_1804CF250);
            if ( dword_1804CF250 == -1 )
            {
              *(DEVPROPKEY *)byte_1804CD4C0 = DEVPKEY_DeviceInterface_ClassGuid;
              dword_1804CD4D4 = 0;
              qword_1804CD4D8 = 0;
              Init_thread_footer(&dword_1804CF250);
            }
          }
          v10 = *((_QWORD *)this + 2);
          v14 = 0;
          v15 = 0;
          ObjectProperties = DevGetObjectProperties(1, v10, 0, 1, byte_1804CD4C0, &v14, &v15);
          if ( ObjectProperties >= 0 )
          {
            v11 = v15;
            if ( v14 == 1 && *(_DWORD *)(v15 + 16) == 4 )
            {
              v12 = *(_QWORD *)v15 - *(_QWORD *)&DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1;
              if ( *(_QWORD *)v15 == *(_QWORD *)&DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1 )
                v12 = *(_QWORD *)(v15 + 8) - *(_QWORD *)DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data4;
              if ( !v12 && *(_DWORD *)(v15 + 32) == 13 )
              {
                if ( StringFromGUID2(*(const GUID *const *)(v15 + 40), sz, 39) )
                {
                  ppv = 0;
                  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
                  ObjectProperties = CoCreateInstance(
                                       &CLSID_DeviceAccessPolicyManager,
                                       0,
                                       1u,
                                       &GUID_02a175a2_f59b_4490_8008_da0592239633,
                                       &ppv);
                  if ( ObjectProperties >= 0 )
                  {
                    v20 = sz;
                    v22 = 0;
                    v23 = 0;
                    v24 = 1;
                    v21 = 0;
                    ObjectProperties = (*(__int64 (__fastcall **)(LPVOID, LPWSTR, OLECHAR **, __int64))(*(_QWORD *)ppv + 64LL))(
                                         ppv,
                                         StringSid,
                                         &v20,
                                         1);
                  }
                  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
                }
                else
                {
                  ObjectProperties = -2147418113;
                }
                v11 = v15;
              }
            }
            DevFreeObjectProperties(v14, v11);
          }
          LocalFree(StringSid);
        }
        else
        {
          LastError = GetLastError();
          ObjectProperties = LastError;
          if ( LastError > 0 )
            ObjectProperties = (unsigned __int16)LastError | 0x80070000;
        }
        LocalFree(Sid[0]);
      }
    }
    CoTaskMemFree((LPVOID)packageFullName);
  }
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_TWINUI_PUBLISHER_Context, AutoPlay_Broker_Device_Stop, v7, 1, Sid);
  return (unsigned int)ObjectProperties;
}

```

## disassembly

```asm
0x180113304  mov     [rsp-8+arg_10], rbx
0x180113309  mov     [rsp-8+arg_18], rsi
0x18011330e  push    rbp
0x18011330f  push    rdi
0x180113310  push    r14
0x180113312  lea     rbp, [rsp-90h]
0x18011331a  sub     rsp, 190h
0x180113321  mov     rax, cs:__security_cookie
0x180113328  xor     rax, rsp
0x18011332b  mov     [rbp+0A0h+var_20], rax
0x180113332  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x180113339  mov     rbx, rdx
0x18011333c  mov     rdi, rcx
0x18011333f  mov     r14d, 1
0x180113345  jz      short loc_180113366
0x180113347  lea     rax, [rbp+0A0h+Sid]
0x18011334b  mov     r9d, r14d
0x18011334e  lea     rdx, AutoPlay_Broker_Device_Start
0x180113355  mov     [rsp+1A0h+ppv], rax
0x18011335a  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x180113361  call    McGenEventWrite_EventWriteTransfer
0x180113366  mov     rax, [rbx]
0x180113369  lea     rdx, [rsp+1A0h+packageFullName]
0x18011336e  xor     esi, esi
0x180113370  mov     rcx, rbx
0x180113373  mov     [rsp+1A0h+packageFullName], rsi
0x180113378  mov     rax, [rax+0C8h]
0x18011337f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113384  mov     ebx, eax
0x180113386  test    eax, eax
0x180113388  js      loc_18011362A
0x18011338e  mov     rcx, [rsp+1A0h+packageFullName]; packageFullName
0x180113393  test    rcx, rcx
0x180113396  jz      loc_18011362A
0x18011339c  cmp     [rcx], si
0x18011339f  jz      loc_18011362A
0x1801133a5  lea     r8, [rbp+0A0h+packageFamilyName]; packageFamilyName
0x1801133a9  mov     [rsp+1A0h+packageFamilyNameLength], 41h ; 'A'
0x1801133b1  lea     rdx, [rsp+1A0h+packageFamilyNameLength]; packageFamilyNameLength
0x1801133b6  call    cs:__imp_PackageFamilyNameFromFullName
0x1801133bd  nop     dword ptr [rax+rax+00h]
0x1801133c2  mov     ebx, eax
0x1801133c4  test    eax, eax
0x1801133c6  jle     short loc_1801133D1
0x1801133c8  movzx   ebx, ax
0x1801133cb  or      ebx, 80070000h
0x1801133d1  test    ebx, ebx
0x1801133d3  js      loc_180113619
0x1801133d9  lea     rdx, [rbp+0A0h+Sid]
0x1801133dd  mov     [rbp+0A0h+Sid], rsi
0x1801133e1  lea     rcx, [rbp+0A0h+packageFamilyName]
0x1801133e5  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x1801133ec  nop     dword ptr [rax+rax+00h]
0x1801133f1  mov     ebx, eax
0x1801133f3  test    eax, eax
0x1801133f5  js      loc_180113619
0x1801133fb  mov     rcx, [rbp+0A0h+Sid]; Sid
0x1801133ff  lea     rdx, [rsp+1A0h+StringSid]; StringSid
0x180113404  mov     [rsp+1A0h+StringSid], rsi
0x180113409  call    cs:__imp_ConvertSidToStringSidW
0x180113410  nop     dword ptr [rax+rax+00h]
0x180113415  test    eax, eax
0x180113417  jnz     short loc_18011343D
0x180113419  call    cs:__imp_GetLastError
0x180113420  nop     dword ptr [rax+rax+00h]
0x180113425  mov     ebx, eax
0x180113427  test    eax, eax
0x180113429  jle     loc_180113609
0x18011342f  movzx   ebx, ax
0x180113432  or      ebx, 80070000h
0x180113438  jmp     loc_180113609
0x18011343d  mov     ecx, cs:_tls_index
0x180113443  mov     rax, gs:58h
0x18011344c  mov     edx, 4
0x180113451  mov     rax, [rax+rcx*8]
0x180113455  mov     ecx, [rdx+rax]
0x180113458  cmp     cs:dword_1804CF250, ecx
0x18011345e  jle     short loc_1801134A8
0x180113460  lea     rcx, dword_1804CF250
0x180113467  call    _Init_thread_header
0x18011346c  cmp     cs:dword_1804CF250, 0FFFFFFFFh
0x180113473  jnz     short loc_1801134A8
0x180113475  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x18011347c  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x180113482  lea     rcx, dword_1804CF250
0x180113489  mov     dword ptr cs:byte_1804CD4C0+10h, eax
0x18011348f  movups  xmmword ptr cs:byte_1804CD4C0, xmm0
0x180113496  mov     cs:dword_1804CD4D4, esi
0x18011349c  mov     cs:qword_1804CD4D8, rsi
0x1801134a3  call    _Init_thread_footer
0x1801134a8  mov     rdx, [rdi+10h]
0x1801134ac  lea     rax, [rsp+1A0h+var_158]
0x1801134b1  mov     [rsp+1A0h+var_170], rax
0x1801134b6  mov     r9d, r14d
0x1801134b9  lea     rax, [rsp+1A0h+var_160]
0x1801134be  mov     [rsp+1A0h+var_160], esi
0x1801134c2  mov     [rsp+1A0h+var_178], rax
0x1801134c7  xor     r8d, r8d
0x1801134ca  lea     rax, byte_1804CD4C0
0x1801134d1  mov     [rsp+1A0h+var_158], rsi
0x1801134d6  mov     ecx, r14d
0x1801134d9  mov     [rsp+1A0h+ppv], rax
0x1801134de  call    cs:__imp_DevGetObjectProperties
0x1801134e5  nop     dword ptr [rax+rax+00h]
0x1801134ea  mov     ebx, eax
0x1801134ec  test    eax, eax
0x1801134ee  js      loc_1801135F8
0x1801134f4  mov     rax, [rsp+1A0h+var_158]
0x1801134f9  cmp     [rsp+1A0h+var_160], r14d
0x1801134fe  jnz     loc_1801135E5
0x180113504  cmp     dword ptr [rax+10h], 4
0x180113508  jnz     loc_1801135E5
0x18011350e  mov     rcx, [rax]
0x180113511  sub     rcx, qword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x180113518  jnz     short loc_180113525
0x18011351a  mov     rcx, [rax+8]
0x18011351e  sub     rcx, qword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data4
0x180113525  test    rcx, rcx
0x180113528  jnz     loc_1801135E5
0x18011352e  cmp     dword ptr [rax+20h], 0Dh
0x180113532  jnz     loc_1801135E5
0x180113538  lea     r8d, [rcx+27h]; cchMax
0x18011353c  mov     rcx, [rax+28h]; rguid
0x180113540  lea     rdx, [rbp+0A0h+sz]; lpsz
0x180113544  call    cs:__imp_StringFromGUID2
0x18011354b  nop     dword ptr [rax+rax+00h]
0x180113550  test    eax, eax
0x180113552  jz      loc_1801135DB
0x180113558  lea     rcx, [rsp+1A0h+var_150]
0x18011355d  mov     [rsp+1A0h+var_150], rsi
0x180113562  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180113567  lea     rax, [rsp+1A0h+var_150]
0x18011356c  mov     r8d, r14d; dwClsContext
0x18011356f  lea     r9, _GUID_02a175a2_f59b_4490_8008_da0592239633; riid
0x180113576  mov     [rsp+1A0h+ppv], rax; ppv
0x18011357b  xor     edx, edx; pUnkOuter
0x18011357d  lea     rcx, CLSID_DeviceAccessPolicyManager; rclsid
0x180113584  call    cs:__imp_CoCreateInstance
0x18011358b  nop     dword ptr [rax+rax+00h]
0x180113590  mov     ebx, eax
0x180113592  test    eax, eax
0x180113594  js      short loc_1801135CF
0x180113596  mov     rcx, [rsp+1A0h+var_150]
0x18011359b  lea     rax, [rbp+0A0h+sz]
0x18011359f  mov     rdx, [rsp+1A0h+StringSid]
0x1801135a4  lea     r8, [rsp+1A0h+var_130]
0x1801135a9  mov     [rsp+1A0h+var_130], rax
0x1801135ae  mov     r9d, r14d
0x1801135b1  mov     [rsp+1A0h+var_124], rsi
0x1801135b6  mov     [rbp+0A0h+var_11C], esi
0x1801135b9  mov     [rbp+0A0h+var_118], r14
0x1801135bd  mov     [rsp+1A0h+var_128], esi
0x1801135c1  mov     rax, [rcx]
0x1801135c4  mov     rax, [rax+40h]
0x1801135c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801135cd  mov     ebx, eax
0x1801135cf  lea     rcx, [rsp+1A0h+var_150]
0x1801135d4  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801135d9  jmp     short loc_1801135E0
0x1801135db  mov     ebx, 8000FFFFh
0x1801135e0  mov     rax, [rsp+1A0h+var_158]
0x1801135e5  mov     ecx, [rsp+1A0h+var_160]
0x1801135e9  mov     rdx, rax
0x1801135ec  call    cs:__imp_DevFreeObjectProperties
0x1801135f3  nop     dword ptr [rax+rax+00h]
0x1801135f8  mov     rcx, [rsp+1A0h+StringSid]; hMem
0x1801135fd  call    cs:__imp_LocalFree
0x180113604  nop     dword ptr [rax+rax+00h]
0x180113609  mov     rcx, [rbp+0A0h+Sid]; hMem
0x18011360d  call    cs:__imp_LocalFree
0x180113614  nop     dword ptr [rax+rax+00h]
0x180113619  mov     rcx, [rsp+1A0h+packageFullName]; pv
0x18011361e  call    cs:__imp_CoTaskMemFree
0x180113625  nop     dword ptr [rax+rax+00h]
0x18011362a  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x180113631  jz      short loc_180113652
0x180113633  lea     rax, [rbp+0A0h+Sid]
0x180113637  mov     r9d, r14d
0x18011363a  lea     rdx, AutoPlay_Broker_Device_Stop
0x180113641  mov     [rsp+1A0h+ppv], rax
0x180113646  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x18011364d  call    McGenEventWrite_EventWriteTransfer
0x180113652  mov     eax, ebx
0x180113654  mov     rcx, [rbp+0A0h+var_20]
0x18011365b  xor     rcx, rsp; StackCookie
0x18011365e  call    __security_check_cookie
0x180113663  lea     r11, [rsp+1A0h+var_10]
0x18011366b  mov     rbx, [r11+30h]
0x18011366f  mov     rsi, [r11+38h]
0x180113673  mov     rsp, r11
0x180113676  pop     r14
0x180113678  pop     rdi
0x180113679  pop     rbp
0x18011367a  retn
```
