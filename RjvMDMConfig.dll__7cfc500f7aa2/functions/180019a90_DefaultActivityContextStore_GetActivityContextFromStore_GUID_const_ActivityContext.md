# DefaultActivityContextStore::GetActivityContextFromStore(_GUID const &,ActivityContext * *)

- ea: `0x180019a90`
- end: `0x180019dca`
- name: `?GetActivityContextFromStore@DefaultActivityContextStore@@UEAAJAEBU_GUID@@PEAPEAVActivityContext@@@Z`
- size: `826`
- prototype: `int(DefaultActivityContextStore *__hidden this, const struct _GUID *, struct ActivityContext **)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001c60`
- `0x180002808`
- `0x180003874`
- `0x1800051d8`
- `0x1800075e8`
- `0x180008428`
- `0x18000ff80`
- `0x180011828`
- `0x180017e2c`
- `0x1800188f8`
- `0x180018c14`
- `0x180019a90`
- `0x18001b2a0`
- `0x18001b71c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019c3c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019cad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019d05`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019d5e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019c3c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019cad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019d05`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019d5e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180019b09`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180019b09`

## string_xrefs

- `0x180019cf9`: `AttemptCounter`
- `0x180019d52`: `Rollback`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DefaultActivityContextStore::GetActivityContextFromStore(
        DefaultActivityContextStore *this,
        const struct _GUID *a2,
        struct IUnknown **a3)
{
  LSTATUS v5; // edi
  const unsigned __int16 *EnrollmentsRootKey; // rax
  __int64 v7; // rdx
  ActivityContext *v8; // rax
  struct IUnknown *v9; // rax
  struct IUnknown *v10; // rsi
  HKEY v11; // rbx
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+44h] [rbp-BCh] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown *v16; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v18; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD v19; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v20; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hkey; // [rsp+68h] [rbp-98h] BYREF
  HKEY v22[2]; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v24[40]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR SubKey[264]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 pvData[264]; // [rsp+330h] [rbp+230h] BYREF

  v16 = 0;
  hkey = 0;
  v22[0] = 0;
  SubKey[0] = 0;
  v24[0] = 0;
  sz[0] = 0;
  if ( a3 )
  {
    if ( StringFromGUID2(a2, sz, 39) == 39 )
    {
      v5 = EEDBTrimGuidBracket(sz, v24);
      if ( v5 >= 0 )
      {
        EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
        v5 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s", EnrollmentsRootKey, L"Context", v24);
        if ( v5 >= 0 )
        {
          v5 = EEDBManager::OpenHKEY(SubKey, v7, v22);
          if ( v5 >= 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &hkey,
              v22[0]);
            v8 = (ActivityContext *)operator new(0x3D8u, (const struct std::nothrow_t *)&std::nothrow);
            v22[1] = (HKEY)v8;
            if ( v8
              && (v9 = (struct IUnknown *)ActivityContext::ActivityContext(v8)) != 0
              && (ATL::AtlComPtrAssign(&v16, v9), (v10 = v16) != 0) )
            {
              v5 = ActivityContext::set_Key((ActivityContext *)v16, a2);
              if ( v5 >= 0 )
              {
                pcbData = 520;
                v11 = hkey;
                if ( RegGetValueW(hkey, 0, L"OrchestratorType", 2u, 0, pvData, &pcbData)
                  || (v5 = StringCchCopyW((unsigned __int16 *)&v10[56], 0x104u, pvData), v5 >= 0) )
                {
                  v13 = 0;
                  v18 = 4;
                  if ( !RegGetValueW(v11, 0, L"ActivityType", 0x10u, 0, &v13, &v18) )
                  {
                    LODWORD(v10[4].lpVtbl) = v13;
                    v5 = 0;
                  }
                  v14 = 0;
                  v19 = 4;
                  if ( !RegGetValueW(v11, 0, L"AttemptCounter", 0x10u, 0, &v14, &v19) )
                    LODWORD(v10[121].lpVtbl) = v14;
                  v15 = 0;
                  v20 = 4;
                  if ( !RegGetValueW(v11, 0, L"Rollback", 0x10u, 0, &v15, &v20) )
                    LODWORD(v10[54].lpVtbl) = v15;
                  v16 = 0;
                  *a3 = v10;
                }
              }
            }
            else
            {
              v5 = -2147024882;
            }
          }
        }
      }
    }
    else
    {
      v5 = -2147418113;
    }
  }
  else
  {
    v5 = -2147024809;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  ATL::CComPtrBase<Enrollment>::~CComPtrBase<Enrollment>(&v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180019a90  mov     [rsp-8+arg_0], rbx
0x180019a95  mov     [rsp-8+arg_18], rsi
0x180019a9a  push    rbp
0x180019a9b  push    rdi
0x180019a9c  push    r14
0x180019a9e  lea     rbp, [rsp-450h]
0x180019aa6  sub     rsp, 550h
0x180019aad  mov     rax, cs:__security_cookie
0x180019ab4  xor     rax, rsp
0x180019ab7  mov     [rbp+460h+var_20], rax
0x180019abe  mov     r14, r8
0x180019ac1  mov     rbx, rdx
0x180019ac4  mov     [rsp+560h+var_510], 0
0x180019acd  mov     [rsp+560h+hkey], 0
0x180019ad6  mov     [rsp+560h+var_4F0], 0
0x180019adf  xor     eax, eax
0x180019ae1  mov     [rbp+460h+SubKey], ax
0x180019ae5  mov     [rbp+460h+var_490], ax
0x180019ae9  mov     [rbp+460h+sz], ax
0x180019aed  test    r8, r8
0x180019af0  jnz     short loc_180019AFC
0x180019af2  mov     edi, 80070057h
0x180019af7  jmp     loc_180019D8B
0x180019afc  mov     r8d, 27h ; '''; cchMax
0x180019b02  lea     rdx, [rbp+460h+sz]; lpsz
0x180019b06  mov     rcx, rbx; rguid
0x180019b09  call    cs:__imp_StringFromGUID2
0x180019b10  nop     dword ptr [rax+rax+00h]
0x180019b15  cmp     eax, 27h ; '''
0x180019b18  jz      short loc_180019B24
0x180019b1a  mov     edi, 8000FFFFh
0x180019b1f  jmp     loc_180019D8B
0x180019b24  lea     rdx, [rbp+460h+var_490]; unsigned __int16 *
0x180019b28  lea     rcx, [rbp+460h+sz]; unsigned __int16 *
0x180019b2c  call    ?EEDBTrimGuidBracket@@YAJPEBGPEAG@Z; EEDBTrimGuidBracket(ushort const *,ushort *)
0x180019b31  mov     edi, eax
0x180019b33  test    eax, eax
0x180019b35  js      loc_180019D8B
0x180019b3b  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x180019b40  lea     rcx, [rbp+460h+var_490]
0x180019b44  mov     [rsp+560h+pvData], rcx
0x180019b49  lea     rcx, aContext; "Context"
0x180019b50  mov     [rsp+560h+pdwType], rcx
0x180019b55  mov     r9, rax
0x180019b58  lea     r8, aSSS; "%s\\%s\\%s"
0x180019b5f  mov     edx, 104h; unsigned __int64
0x180019b64  lea     rcx, [rbp+460h+SubKey]; unsigned __int16 *
0x180019b68  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019b6d  mov     edi, eax
0x180019b6f  test    eax, eax
0x180019b71  js      loc_180019D8B
0x180019b77  lea     r8, [rsp+560h+var_4F0]; HKEY *
0x180019b7c  lea     rcx, [rbp+460h+SubKey]; lpSubKey
0x180019b80  call    ?OpenHKEY@EEDBManager@@SAJPEBGKPEAPEAUHKEY__@@@Z; EEDBManager::OpenHKEY(ushort const *,ulong,HKEY__ * *)
0x180019b85  mov     edi, eax
0x180019b87  test    eax, eax
0x180019b89  js      loc_180019D8B
0x180019b8f  mov     rdx, [rsp+560h+var_4F0]
0x180019b94  lea     rcx, [rsp+560h+hkey]
0x180019b99  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180019b9e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019ba5  mov     ecx, 3D8h; unsigned __int64
0x180019baa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180019baf  mov     [rsp+560h+var_4E8], rax
0x180019bb4  test    rax, rax
0x180019bb7  jz      loc_180019D86
0x180019bbd  mov     rcx, rax; this
0x180019bc0  call    ??0ActivityContext@@QEAA@XZ; ActivityContext::ActivityContext(void)
0x180019bc5  test    rax, rax
0x180019bc8  jz      loc_180019D86
0x180019bce  mov     rdx, rax; struct IUnknown *
0x180019bd1  lea     rcx, [rsp+560h+var_510]; struct IUnknown **
0x180019bd6  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180019bdb  mov     rsi, [rsp+560h+var_510]
0x180019be0  test    rsi, rsi
0x180019be3  jz      loc_180019D86
0x180019be9  mov     rdx, rbx; struct _GUID *
0x180019bec  mov     rcx, rsi; this
0x180019bef  call    ?set_Key@ActivityContext@@QEAAJAEBU_GUID@@@Z; ActivityContext::set_Key(_GUID const &)
0x180019bf4  mov     edi, eax
0x180019bf6  test    eax, eax
0x180019bf8  js      loc_180019D8B
0x180019bfe  mov     [rsp+560h+var_508], 208h
0x180019c06  lea     rax, [rsp+560h+var_508]
0x180019c0b  mov     [rsp+560h+pcbData], rax; pcbData
0x180019c10  lea     rax, [rbp+460h+var_230]
0x180019c17  mov     [rsp+560h+pvData], rax; pvData
0x180019c1c  mov     [rsp+560h+pdwType], 0; pdwType
0x180019c25  mov     r9d, 2; dwFlags
0x180019c2b  lea     r8, aOrchestratorty; "OrchestratorType"
0x180019c32  xor     edx, edx; lpSubKey
0x180019c34  mov     rbx, [rsp+560h+hkey]
0x180019c39  mov     rcx, rbx; hkey
0x180019c3c  call    cs:__imp_RegGetValueW
0x180019c43  nop     dword ptr [rax+rax+00h]
0x180019c48  test    eax, eax
0x180019c4a  jnz     short loc_180019C6E
0x180019c4c  lea     rcx, [rsi+1C0h]; unsigned __int16 *
0x180019c53  lea     r8, [rbp+460h+var_230]; unsigned __int16 *
0x180019c5a  mov     edx, 104h; unsigned __int64
0x180019c5f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019c64  mov     edi, eax
0x180019c66  test    eax, eax
0x180019c68  js      loc_180019D8B
0x180019c6e  mov     [rsp+560h+var_520], 0
0x180019c76  mov     [rsp+560h+var_504], 4
0x180019c7e  lea     rax, [rsp+560h+var_504]
0x180019c83  mov     [rsp+560h+pcbData], rax; pcbData
0x180019c88  lea     rax, [rsp+560h+var_520]
0x180019c8d  mov     [rsp+560h+pvData], rax; pvData
0x180019c92  mov     [rsp+560h+pdwType], 0; pdwType
0x180019c9b  mov     r9d, 10h; dwFlags
0x180019ca1  lea     r8, aActivitytype; "ActivityType"
0x180019ca8  xor     edx, edx; lpSubKey
0x180019caa  mov     rcx, rbx; hkey
0x180019cad  call    cs:__imp_RegGetValueW
0x180019cb4  nop     dword ptr [rax+rax+00h]
0x180019cb9  test    eax, eax
0x180019cbb  jnz     short loc_180019CC6
0x180019cbd  mov     eax, [rsp+560h+var_520]
0x180019cc1  mov     [rsi+20h], eax
0x180019cc4  xor     edi, edi
0x180019cc6  mov     [rsp+560h+var_51C], 0
0x180019cce  mov     [rsp+560h+var_500], 4
0x180019cd6  lea     rax, [rsp+560h+var_500]
0x180019cdb  mov     [rsp+560h+pcbData], rax; pcbData
0x180019ce0  lea     rax, [rsp+560h+var_51C]
0x180019ce5  mov     [rsp+560h+pvData], rax; pvData
0x180019cea  mov     [rsp+560h+pdwType], 0; pdwType
0x180019cf3  mov     r9d, 10h; dwFlags
0x180019cf9  lea     r8, aAttemptcounter; "AttemptCounter"
0x180019d00  xor     edx, edx; lpSubKey
0x180019d02  mov     rcx, rbx; hkey
0x180019d05  call    cs:__imp_RegGetValueW
0x180019d0c  nop     dword ptr [rax+rax+00h]
0x180019d11  test    eax, eax
0x180019d13  jnz     short loc_180019D1F
0x180019d15  mov     eax, [rsp+560h+var_51C]
0x180019d19  mov     [rsi+3C8h], eax
0x180019d1f  mov     [rsp+560h+var_518], 0
0x180019d27  mov     [rsp+560h+var_4FC], 4
0x180019d2f  lea     rax, [rsp+560h+var_4FC]
0x180019d34  mov     [rsp+560h+pcbData], rax; pcbData
0x180019d39  lea     rax, [rsp+560h+var_518]
0x180019d3e  mov     [rsp+560h+pvData], rax; pvData
0x180019d43  mov     [rsp+560h+pdwType], 0; pdwType
0x180019d4c  mov     r9d, 10h; dwFlags
0x180019d52  lea     r8, aRollback; "Rollback"
0x180019d59  xor     edx, edx; lpSubKey
0x180019d5b  mov     rcx, rbx; hkey
0x180019d5e  call    cs:__imp_RegGetValueW
0x180019d65  nop     dword ptr [rax+rax+00h]
0x180019d6a  test    eax, eax
0x180019d6c  jnz     short loc_180019D78
0x180019d6e  mov     eax, [rsp+560h+var_518]
0x180019d72  mov     [rsi+1B0h], eax
0x180019d78  mov     [rsp+560h+var_510], 0
0x180019d81  mov     [r14], rsi
0x180019d84  jmp     short loc_180019D8B
0x180019d86  mov     edi, 8007000Eh
0x180019d8b  lea     rcx, [rsp+560h+hkey]
0x180019d90  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180019d95  nop
0x180019d96  lea     rcx, [rsp+560h+var_510]
0x180019d9b  call    ??1?$CComPtrBase@VEnrollment@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Enrollment>::~CComPtrBase<Enrollment>(void)
0x180019da0  mov     eax, edi
0x180019da2  mov     rcx, [rbp+460h+var_20]
0x180019da9  xor     rcx, rsp; StackCookie
0x180019dac  call    __security_check_cookie
0x180019db1  lea     r11, [rsp+560h+var_10]
0x180019db9  mov     rbx, [r11+20h]
0x180019dbd  mov     rsi, [r11+38h]
0x180019dc1  mov     rsp, r11
0x180019dc4  pop     r14
0x180019dc6  pop     rdi
0x180019dc7  pop     rbp
0x180019dc8  retn
```
