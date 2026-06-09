# SyncActionProtocolSettings(ushort const *)

- ea: `0x18015c7ac`
- end: `0x18015cbcc`
- name: `?SyncActionProtocolSettings@@YAXPEBG@Z`
- size: `1056`
- prototype: `void __fastcall(LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180156c00`

## callees

- `0x180009dd0`
- `0x180041f54`
- `0x180055128`
- `0x180125b24`
- `0x18015b4a8`
- `0x18015c7ac`
- `0x18036cf88`
- `0x180376a68`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015c863`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015c8c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015c98a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015ca34`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015caa9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015cb52`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015c863`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015c8c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015c98a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015ca34`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015caa9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015cb52`
- `SHELL32!SHCreateAssociationRegistration` at `0x18015c7e8`
- `SHELL32!SHCreateAssociationRegistration` at `0x18015c7e8`

## pseudocode

```c
void __fastcall SyncActionProtocolSettings(LPCWCH lpString2)
{
  GUID **v2; // rbx
  LPCWCH *i; // rdi
  GUID *v4; // rdx
  int DefaultAppId; // eax
  const unsigned __int16 *v6; // rdx
  unsigned __int16 **v7; // r9
  int (* near **v8)(void); // rdi
  wchar_t **v9; // rbx
  WCHAR *v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned __int16 *v13; // rbx
  unsigned __int16 **v14; // r9
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  const unsigned __int16 *v18; // rbx
  unsigned __int16 **v19; // r9
  HKEY v20; // rcx
  bool v21; // r8
  int v22; // eax
  LPCWCH lpString2a; // [rsp+30h] [rbp-49h] BYREF
  __int64 v24; // [rsp+38h] [rbp-41h]
  __int64 v25; // [rsp+40h] [rbp-39h]
  unsigned __int16 *v26; // [rsp+48h] [rbp-31h] BYREF
  __int64 v27; // [rsp+50h] [rbp-29h]
  __int64 v28; // [rsp+58h] [rbp-21h]
  LPCWCH v29; // [rsp+60h] [rbp-19h] BYREF
  __int64 v30; // [rsp+68h] [rbp-11h]
  __int64 v31; // [rsp+70h] [rbp-9h]
  LPCWCH lpString1; // [rsp+78h] [rbp-1h] BYREF
  __int64 v33; // [rsp+80h] [rbp+7h]
  __int64 v34; // [rsp+88h] [rbp+Fh]
  unsigned __int16 *v35; // [rsp+90h] [rbp+17h] BYREF
  __int64 v36; // [rsp+98h] [rbp+1Fh]
  __int64 v37; // [rsp+A0h] [rbp+27h]
  void *ppv; // [rsp+E8h] [rbp+6Fh] BYREF

  ppv = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  if ( SHCreateAssociationRegistration(&GUID_a357134e_8c1e_4edd_8474_40a80546f54f, &ppv) >= 0 )
  {
    lpString1 = 0;
    v33 = 0;
    v34 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    v33 = -1;
    v34 = -1;
    if ( (int)anonymous_namespace_::GetDefaultAppId(ppv, lpString2, &lpString1) >= 0 )
    {
      v2 = (GUID **)off_1803F9370;
      for ( i = (LPCWCH *)off_1803F9370; i != (LPCWCH *)&`CRunnableTask::QueryInterface'::`2'::qit; ++i )
      {
        if ( CompareStringOrdinal(*i, -1, lpString2, -1, 1) == 2 )
        {
          do
          {
            lpString2a = 0;
            v24 = 0;
            v25 = 0;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2a);
            v4 = *v2;
            v24 = -1;
            v25 = -1;
            DefaultAppId = anonymous_namespace_::GetDefaultAppId(ppv, v4, &lpString2a);
            if ( DefaultAppId == -2147023741
              || DefaultAppId >= 0 && CompareStringOrdinal(lpString1, -1, lpString2a, -1, 0) != 2 )
            {
              v26 = 0;
              v27 = 0;
              v28 = 0;
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
              v6 = (const unsigned __int16 *)*v2;
              v27 = -1;
              v28 = -1;
              if ( (int)ImmersiveAssociationHelpers::GetAppProgIdForProtocol(
                          (ImmersiveAssociationHelpers *)lpString1,
                          v6,
                          (void **)&v26,
                          v7) >= 0 )
                SetDefaultAssociation(v26);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2a);
            ++v2;
          }
          while ( v2 != &`CRunnableTask::QueryInterface'::`2'::qit );
          goto LABEL_41;
        }
      }
      v26 = 0;
      v27 = 0;
      v28 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
      v8 = (int (* near **)(void))off_1804C0000;
      v27 = -1;
      v9 = off_1804C0000;
      v28 = -1;
      v26 = 0;
      while ( 1 )
      {
        v10 = (WCHAR *)lpString1;
        if ( v9 == (wchar_t **)&g_appCrashUIRegisterProc )
          break;
        if ( CompareStringOrdinal(*v9, -1, lpString2, -1, 1) == 2 )
        {
          if ( (int)_AllocString<CTCoAllocPolicy>(v12, v11, v9[1], &v26) >= 0 )
          {
            v29 = 0;
            v30 = 0;
            v31 = 0;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v29);
            v13 = v26;
            v30 = -1;
            v31 = -1;
            if ( (int)ImmersiveAssociationHelpers::GetAppProgIdForProtocol(
                        (ImmersiveAssociationHelpers *)v10,
                        v26,
                        (void **)&v29,
                        v14) >= 0 )
            {
              lpString2a = 0;
              v24 = 0;
              v25 = 0;
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2a);
              v24 = -1;
              v25 = -1;
              v15 = anonymous_namespace_::GetDefaultAppId(ppv, v13, &lpString2a);
              if ( v15 == -2147023741 || v15 >= 0 && CompareStringOrdinal(v10, -1, lpString2a, -1, 0) != 2 )
                SetDefaultAssociation((unsigned __int16 *)v29);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2a);
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v29);
          }
          break;
        }
        v9 += 4;
      }
      lpString2a = 0;
      v24 = 0;
      v25 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2a);
      v24 = -1;
      v25 = -1;
      lpString2a = 0;
      while ( v8 != &g_appCrashUIRegisterProc )
      {
        if ( CompareStringOrdinal((LPCWCH)v8[1], -1, lpString2, -1, 1) == 2 )
        {
          if ( (int)_AllocString<CTCoAllocPolicy>(v17, v16, *v8, &lpString2a) >= 0 )
          {
            v35 = 0;
            v36 = 0;
            v37 = 0;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v35);
            v18 = lpString2a;
            v36 = -1;
            v37 = -1;
            if ( (int)ImmersiveAssociationHelpers::GetAppProgIdForProtocol(
                        (ImmersiveAssociationHelpers *)v10,
                        lpString2a,
                        (void **)&v35,
                        v19) < 0 )
            {
              ClearUserChoice(v20, v18, v21);
            }
            else
            {
              v29 = 0;
              v30 = 0;
              v31 = 0;
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v29);
              v30 = -1;
              v31 = -1;
              v22 = anonymous_namespace_::GetDefaultAppId(ppv, v18, &v29);
              if ( v22 == -2147023741 || v22 >= 0 && CompareStringOrdinal(v10, -1, v29, -1, 0) != 2 )
                SetDefaultAssociation(v35);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v29);
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v35);
          }
          break;
        }
        v8 += 4;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2a);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
    }
LABEL_41:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
}

```

## disassembly

```asm
0x18015c7ac  mov     [rsp-8+arg_0], rbx
0x18015c7b1  mov     [rsp-8+arg_10], rsi
0x18015c7b6  push    rbp
0x18015c7b7  push    rdi
0x18015c7b8  push    r12
0x18015c7ba  push    r13
0x18015c7bc  push    r14
0x18015c7be  lea     rbp, [rsp-37h]
0x18015c7c3  sub     rsp, 0B0h
0x18015c7ca  mov     r14, rcx
0x18015c7cd  xor     r12d, r12d
0x18015c7d0  lea     rcx, [rbp+57h+ppv]
0x18015c7d4  mov     [rbp+57h+ppv], r12
0x18015c7d8  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18015c7dd  lea     rdx, [rbp+57h+ppv]; ppv
0x18015c7e1  lea     rcx, _GUID_a357134e_8c1e_4edd_8474_40a80546f54f; riid
0x18015c7e8  call    cs:__imp_SHCreateAssociationRegistration
0x18015c7ef  nop     dword ptr [rax+rax+00h]
0x18015c7f4  test    eax, eax
0x18015c7f6  js      loc_18015CBA6
0x18015c7fc  lea     rcx, [rbp+57h+lpString1]
0x18015c800  mov     [rbp+57h+lpString1], r12
0x18015c804  mov     [rbp+57h+var_50], r12
0x18015c808  mov     [rbp+57h+var_48], r12
0x18015c80c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015c811  mov     rcx, [rbp+57h+ppv]
0x18015c815  lea     r8, [rbp+57h+lpString1]
0x18015c819  or      r13, 0FFFFFFFFFFFFFFFFh
0x18015c81d  mov     rdx, r14
0x18015c820  mov     [rbp+57h+var_50], r13
0x18015c824  mov     [rbp+57h+var_48], r13
0x18015c828  call    _anonymous_namespace___GetDefaultAppId
0x18015c82d  test    eax, eax
0x18015c82f  js      loc_18015CB9D
0x18015c835  lea     rbx, off_1803F9370; "Windows.AppointmentsProvider.AddAppoint"...
0x18015c83c  mov     rdi, rbx
0x18015c83f  lea     rsi, ?qit@?1??QueryInterface@CRunnableTask@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; QITAB const near * const `CRunnableTask::QueryInterface(_GUID const &,void * *)'::`2'::qit
0x18015c846  cmp     rdi, rsi
0x18015c849  jz      loc_18015C937
0x18015c84f  mov     rcx, [rdi]; lpString1
0x18015c852  mov     r9d, r13d; cchCount2
0x18015c855  mov     r8, r14; lpString2
0x18015c858  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x18015c860  mov     edx, r13d; cchCount1
0x18015c863  call    cs:__imp_CompareStringOrdinal
0x18015c86a  nop     dword ptr [rax+rax+00h]
0x18015c86f  cmp     eax, 2
0x18015c872  jz      short loc_18015C87A
0x18015c874  add     rdi, 8
0x18015c878  jmp     short loc_18015C846
0x18015c87a  lea     rcx, [rbp+57h+lpString2]
0x18015c87e  mov     [rbp+57h+lpString2], r12
0x18015c882  mov     [rbp+57h+var_98], r12
0x18015c886  mov     [rbp+57h+var_90], r12
0x18015c88a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015c88f  mov     rdx, [rbx]
0x18015c892  lea     r8, [rbp+57h+lpString2]
0x18015c896  mov     rcx, [rbp+57h+ppv]
0x18015c89a  mov     [rbp+57h+var_98], r13
0x18015c89e  mov     [rbp+57h+var_90], r13
0x18015c8a2  call    _anonymous_namespace___GetDefaultAppId
0x18015c8a7  cmp     eax, 80070483h
0x18015c8ac  jz      short loc_18015C8D6
0x18015c8ae  test    eax, eax
0x18015c8b0  js      short loc_18015C91C
0x18015c8b2  mov     r8, [rbp+57h+lpString2]; lpString2
0x18015c8b6  mov     r9d, r13d; cchCount2
0x18015c8b9  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18015c8bd  mov     edx, r13d; cchCount1
0x18015c8c0  mov     [rsp+0D0h+bIgnoreCase], r12d; bIgnoreCase
0x18015c8c5  call    cs:__imp_CompareStringOrdinal
0x18015c8cc  nop     dword ptr [rax+rax+00h]
0x18015c8d1  cmp     eax, 2
0x18015c8d4  jz      short loc_18015C91C
0x18015c8d6  lea     rcx, [rbp+57h+var_88]
0x18015c8da  mov     [rbp+57h+var_88], r12
0x18015c8de  mov     [rbp+57h+var_80], r12
0x18015c8e2  mov     [rbp+57h+var_78], r12
0x18015c8e6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015c8eb  mov     rdx, [rbx]; unsigned __int16 *
0x18015c8ee  lea     r8, [rbp+57h+var_88]; void **
0x18015c8f2  mov     rcx, [rbp+57h+lpString1]; this
0x18015c8f6  mov     [rbp+57h+var_80], r13
0x18015c8fa  mov     [rbp+57h+var_78], r13
0x18015c8fe  call    ?GetAppProgIdForProtocol@ImmersiveAssociationHelpers@@YAJPEBG0PEAPEAG@Z; ImmersiveAssociationHelpers::GetAppProgIdForProtocol(ushort const *,ushort const *,ushort * *)
0x18015c903  test    eax, eax
0x18015c905  js      short loc_18015C913
0x18015c907  mov     rdx, [rbx]
0x18015c90a  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x18015c90e  call    SetDefaultAssociation
0x18015c913  lea     rcx, [rbp+57h+var_88]
0x18015c917  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015c91c  lea     rcx, [rbp+57h+lpString2]
0x18015c920  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015c925  add     rbx, 8
0x18015c929  cmp     rbx, rsi
0x18015c92c  jnz     loc_18015C87A
0x18015c932  jmp     loc_18015CB9D
0x18015c937  lea     rcx, [rbp+57h+var_88]
0x18015c93b  mov     [rbp+57h+var_88], r12
0x18015c93f  mov     [rbp+57h+var_80], r12
0x18015c943  mov     [rbp+57h+var_78], r12
0x18015c947  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015c94c  lea     rdi, off_1804C0000; "Windows.Contact.Call+telephone"
0x18015c953  mov     [rbp+57h+var_80], r13
0x18015c957  mov     rbx, rdi
0x18015c95a  mov     [rbp+57h+var_78], r13
0x18015c95e  mov     [rbp+57h+var_88], r12
0x18015c962  mov     rsi, [rbp+57h+lpString1]
0x18015c966  lea     rax, ?g_appCrashUIRegisterProc@@3PAP6AJXZA; long (*near * g_appCrashUIRegisterProc)(void)
0x18015c96d  cmp     rbx, rax
0x18015c970  jz      loc_18015CA63
0x18015c976  mov     rcx, [rbx]; lpString1
0x18015c979  mov     r9d, r13d; cchCount2
0x18015c97c  mov     r8, r14; lpString2
0x18015c97f  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x18015c987  mov     edx, r13d; cchCount1
0x18015c98a  call    cs:__imp_CompareStringOrdinal
0x18015c991  nop     dword ptr [rax+rax+00h]
0x18015c996  cmp     eax, 2
0x18015c999  jz      short loc_18015C9A1
0x18015c99b  add     rbx, 20h ; ' '
0x18015c99f  jmp     short loc_18015C962
0x18015c9a1  mov     r8, [rbx+8]
0x18015c9a5  lea     r9, [rbp+57h+var_88]
0x18015c9a9  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18015c9ae  test    eax, eax
0x18015c9b0  js      loc_18015CA63
0x18015c9b6  lea     rcx, [rbp+57h+var_70]
0x18015c9ba  mov     [rbp+57h+var_70], r12
0x18015c9be  mov     [rbp+57h+var_68], r12
0x18015c9c2  mov     [rbp+57h+var_60], r12
0x18015c9c6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015c9cb  mov     rbx, [rbp+57h+var_88]
0x18015c9cf  lea     r8, [rbp+57h+var_70]; void **
0x18015c9d3  mov     rdx, rbx; unsigned __int16 *
0x18015c9d6  mov     [rbp+57h+var_68], r13
0x18015c9da  mov     rcx, rsi; this
0x18015c9dd  mov     [rbp+57h+var_60], r13
0x18015c9e1  call    ?GetAppProgIdForProtocol@ImmersiveAssociationHelpers@@YAJPEBG0PEAPEAG@Z; ImmersiveAssociationHelpers::GetAppProgIdForProtocol(ushort const *,ushort const *,ushort * *)
0x18015c9e6  test    eax, eax
0x18015c9e8  js      short loc_18015CA5A
0x18015c9ea  lea     rcx, [rbp+57h+lpString2]
0x18015c9ee  mov     [rbp+57h+lpString2], r12
0x18015c9f2  mov     [rbp+57h+var_98], r12
0x18015c9f6  mov     [rbp+57h+var_90], r12
0x18015c9fa  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015c9ff  mov     rcx, [rbp+57h+ppv]
0x18015ca03  lea     r8, [rbp+57h+lpString2]
0x18015ca07  mov     rdx, rbx
0x18015ca0a  mov     [rbp+57h+var_98], r13
0x18015ca0e  mov     [rbp+57h+var_90], r13
0x18015ca12  call    _anonymous_namespace___GetDefaultAppId
0x18015ca17  cmp     eax, 80070483h
0x18015ca1c  jz      short loc_18015CA45
0x18015ca1e  test    eax, eax
0x18015ca20  js      short loc_18015CA51
0x18015ca22  mov     r8, [rbp+57h+lpString2]; lpString2
0x18015ca26  mov     r9d, r13d; cchCount2
0x18015ca29  mov     edx, r13d; cchCount1
0x18015ca2c  mov     [rsp+0D0h+bIgnoreCase], r12d; bIgnoreCase
0x18015ca31  mov     rcx, rsi; lpString1
0x18015ca34  call    cs:__imp_CompareStringOrdinal
0x18015ca3b  nop     dword ptr [rax+rax+00h]
0x18015ca40  cmp     eax, 2
0x18015ca43  jz      short loc_18015CA51
0x18015ca45  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x18015ca49  mov     rdx, rbx
0x18015ca4c  call    SetDefaultAssociation
0x18015ca51  lea     rcx, [rbp+57h+lpString2]
0x18015ca55  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015ca5a  lea     rcx, [rbp+57h+var_70]
0x18015ca5e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015ca63  lea     rcx, [rbp+57h+lpString2]
0x18015ca67  mov     [rbp+57h+lpString2], r12
0x18015ca6b  mov     [rbp+57h+var_98], r12
0x18015ca6f  mov     [rbp+57h+var_90], r12
0x18015ca73  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015ca78  mov     [rbp+57h+var_98], r13
0x18015ca7c  lea     rbx, ?g_appCrashUIRegisterProc@@3PAP6AJXZA; long (*near * g_appCrashUIRegisterProc)(void)
0x18015ca83  mov     [rbp+57h+var_90], r13
0x18015ca87  mov     [rbp+57h+lpString2], r12
0x18015ca8b  cmp     rdi, rbx
0x18015ca8e  jz      loc_18015CB8B
0x18015ca94  mov     rcx, [rdi+8]; lpString1
0x18015ca98  mov     r9d, r13d; cchCount2
0x18015ca9b  mov     r8, r14; lpString2
0x18015ca9e  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x18015caa6  mov     edx, r13d; cchCount1
0x18015caa9  call    cs:__imp_CompareStringOrdinal
0x18015cab0  nop     dword ptr [rax+rax+00h]
0x18015cab5  cmp     eax, 2
0x18015cab8  jz      short loc_18015CAC0
0x18015caba  add     rdi, 20h ; ' '
0x18015cabe  jmp     short loc_18015CA8B
0x18015cac0  mov     r8, [rdi]
0x18015cac3  lea     r9, [rbp+57h+lpString2]
0x18015cac7  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18015cacc  test    eax, eax
0x18015cace  js      loc_18015CB8B
0x18015cad4  lea     rcx, [rbp+57h+var_40]
0x18015cad8  mov     [rbp+57h+var_40], r12
0x18015cadc  mov     [rbp+57h+var_38], r12
0x18015cae0  mov     [rbp+57h+var_30], r12
0x18015cae4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015cae9  mov     rbx, [rbp+57h+lpString2]
0x18015caed  lea     r8, [rbp+57h+var_40]; void **
0x18015caf1  mov     rdx, rbx; unsigned __int16 *
0x18015caf4  mov     [rbp+57h+var_38], r13
0x18015caf8  mov     rcx, rsi; this
0x18015cafb  mov     [rbp+57h+var_30], r13
0x18015caff  call    ?GetAppProgIdForProtocol@ImmersiveAssociationHelpers@@YAJPEBG0PEAPEAG@Z; ImmersiveAssociationHelpers::GetAppProgIdForProtocol(ushort const *,ushort const *,ushort * *)
0x18015cb04  test    eax, eax
0x18015cb06  js      short loc_18015CB7A
0x18015cb08  lea     rcx, [rbp+57h+var_70]
0x18015cb0c  mov     [rbp+57h+var_70], r12
0x18015cb10  mov     [rbp+57h+var_68], r12
0x18015cb14  mov     [rbp+57h+var_60], r12
0x18015cb18  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015cb1d  mov     rcx, [rbp+57h+ppv]
0x18015cb21  lea     r8, [rbp+57h+var_70]
0x18015cb25  mov     rdx, rbx
0x18015cb28  mov     [rbp+57h+var_68], r13
0x18015cb2c  mov     [rbp+57h+var_60], r13
0x18015cb30  call    _anonymous_namespace___GetDefaultAppId
0x18015cb35  cmp     eax, 80070483h
0x18015cb3a  jz      short loc_18015CB63
0x18015cb3c  test    eax, eax
0x18015cb3e  js      short loc_18015CB6F
0x18015cb40  mov     r8, [rbp+57h+var_70]; lpString2
0x18015cb44  mov     r9d, r13d; cchCount2
0x18015cb47  mov     edx, r13d; cchCount1
0x18015cb4a  mov     [rsp+0D0h+bIgnoreCase], r12d; bIgnoreCase
0x18015cb4f  mov     rcx, rsi; lpString1
0x18015cb52  call    cs:__imp_CompareStringOrdinal
0x18015cb59  nop     dword ptr [rax+rax+00h]
0x18015cb5e  cmp     eax, 2
0x18015cb61  jz      short loc_18015CB6F
0x18015cb63  mov     rcx, [rbp+57h+var_40]; unsigned __int16 *
0x18015cb67  mov     rdx, rbx
0x18015cb6a  call    SetDefaultAssociation
0x18015cb6f  lea     rcx, [rbp+57h+var_70]
0x18015cb73  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015cb78  jmp     short loc_18015CB82
0x18015cb7a  mov     rdx, rbx; unsigned __int16 *
0x18015cb7d  call    ?ClearUserChoice@@YAXPEAUHKEY__@@PEBG_N@Z; ClearUserChoice(HKEY__ *,ushort const *,bool)
0x18015cb82  lea     rcx, [rbp+57h+var_40]
0x18015cb86  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015cb8b  lea     rcx, [rbp+57h+lpString2]
0x18015cb8f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015cb94  lea     rcx, [rbp+57h+var_88]
0x18015cb98  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015cb9d  lea     rcx, [rbp+57h+lpString1]
0x18015cba1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18015cba6  lea     rcx, [rbp+57h+ppv]
0x18015cbaa  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18015cbaf  lea     r11, [rsp+0D0h+var_20]
0x18015cbb7  mov     rbx, [r11+30h]
0x18015cbbb  mov     rsi, [r11+40h]
0x18015cbbf  mov     rsp, r11
0x18015cbc2  pop     r14
0x18015cbc4  pop     r13
0x18015cbc6  pop     r12
0x18015cbc8  pop     rdi
0x18015cbc9  pop     rbp
0x18015cbca  retn
```
