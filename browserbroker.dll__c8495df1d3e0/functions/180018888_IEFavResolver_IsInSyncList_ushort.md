# IEFavResolver::IsInSyncList(ushort *)

- ea: `0x180018888`
- end: `0x180018aa5`
- name: `?IsInSyncList@IEFavResolver@@AEAA_NPEAG@Z`
- size: `541`
- prototype: `bool(IEFavResolver *__hidden this, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018c10`
- `0x180018d94`
- `0x180018f0c`
- `0x180019088`
- `0x1800192f8`

## callees

- `0x1800023bc`
- `0x180002ce0`
- `0x180002d04`
- `0x18000d17c`
- `0x180018888`

## import_xrefs

- `iertutil!__imp_DPA_DeletePtr` at `0x180018a5c`
- `iertutil!__imp_DPA_DeletePtr` at `0x180018a5c`
- `iertutil!__imp_DPA_GetPtr` at `0x18001891c`
- `iertutil!__imp_DPA_GetPtr` at `0x18001891c`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001898e`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180018a0a`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001898e`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180018a0a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001894f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001894f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x1800188ee`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x1800188ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800188c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800188c1`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001897e`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800189fa`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001897e`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800189fa`

## pseudocode

```c
char __fastcall IEFavResolver::IsInSyncList(IEFavResolver *this, unsigned __int16 *a2)
{
  char v4; // r15
  ULONGLONG TickCount64; // r12
  unsigned int v6; // r11d
  unsigned int *v7; // rbx
  unsigned int v8; // ebx
  _QWORD *Ptr; // rsi
  ULONGLONG v10; // rax
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  char v19[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 CLSID; // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *v21; // [rsp+60h] [rbp-A0h] BYREF
  const WCHAR *v22; // [rsp+68h] [rbp-98h] BYREF
  __int64 v23[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszPath[264]; // [rsp+80h] [rbp-80h] BYREF

  v4 = 0;
  TickCount64 = GetTickCount64();
  if ( StringCchCopyW(pszPath, 0x104u, a2) >= 0 && PathCchRemoveBackslash(pszPath, v6) >= 0 )
  {
    v7 = (unsigned int *)*((_QWORD *)this + 72);
    if ( v7 )
    {
      v8 = *v7;
      while ( 1 )
      {
        while ( 1 )
        {
          if ( (--v8 & 0x80000000) != 0 )
            return v4;
          Ptr = DPA_GetPtr(*((HDPA *)this + 72), v8);
          v10 = Ptr[65];
          if ( TickCount64 >= v10 )
            break;
          v11 = -1;
LABEL_11:
          if ( (unsigned int)dword_18003F000 > 5 )
          {
            v23[0] = v11;
            v22 = a2;
            v19[0] = 1;
            v21 = (const WCHAR *)GlobalThreadState();
            CLSID = IEConfiguration_GetCLSID(268435459);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
              v15,
              (__int64)&unk_180035BD0,
              v16,
              v17,
              &CLSID,
              (__int64 *)&v21,
              (__int64)v19,
              &v22,
              (__int64)v23);
          }
          DPA_DeletePtr(*((HDPA *)this + 72), v8);
          operator delete(Ptr);
        }
        v11 = TickCount64 - v10;
        if ( TickCount64 - v10 >= 0x7D0 )
          goto LABEL_11;
        if ( !StrCmpICW(pszPath, (LPCWSTR)Ptr) )
        {
          v4 = 1;
          if ( (unsigned int)dword_18003F000 > 5 )
          {
            CLSID = v11;
            v21 = a2;
            v19[0] = 1;
            v22 = (const WCHAR *)GlobalThreadState();
            v23[0] = IEConfiguration_GetCLSID(268435459);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
              v12,
              (__int64)&word_180035C56,
              v13,
              v14,
              v23,
              (__int64 *)&v22,
              (__int64)v19,
              &v21,
              (__int64)&CLSID);
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180018888  mov     [rsp-8+arg_10], rbx
0x18001888d  push    rbp
0x18001888e  push    rsi
0x18001888f  push    rdi
0x180018890  push    r12
0x180018892  push    r13
0x180018894  push    r14
0x180018896  push    r15
0x180018898  lea     rbp, [rsp-1A0h]
0x1800188a0  sub     rsp, 2A0h
0x1800188a7  mov     rax, cs:__security_cookie
0x1800188ae  xor     rax, rsp
0x1800188b1  mov     [rbp+1D0h+var_40], rax
0x1800188b8  mov     r13, rdx
0x1800188bb  mov     r14, rcx
0x1800188be  xor     r15b, r15b
0x1800188c1  call    cs:__imp_GetTickCount64
0x1800188c7  mov     r11d, 104h
0x1800188cd  lea     rcx, [rbp+1D0h+pszPath]; unsigned __int16 *
0x1800188d1  mov     edx, r11d; unsigned __int64
0x1800188d4  mov     r8, r13; unsigned __int16 *
0x1800188d7  mov     r12, rax
0x1800188da  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800188df  test    eax, eax
0x1800188e1  js      loc_180018A78
0x1800188e7  mov     edx, r11d; cchPath
0x1800188ea  lea     rcx, [rbp+1D0h+pszPath]; pszPath
0x1800188ee  call    cs:__imp_PathCchRemoveBackslash
0x1800188f4  test    eax, eax
0x1800188f6  js      loc_180018A78
0x1800188fc  mov     rbx, [r14+240h]
0x180018903  test    rbx, rbx
0x180018906  jz      loc_180018A78
0x18001890c  mov     ebx, [rbx]
0x18001890e  jmp     loc_180018A6F
0x180018913  mov     rcx, [r14+240h]; hdpa
0x18001891a  mov     edx, ebx; i
0x18001891c  call    cs:__imp_DPA_GetPtr
0x180018922  mov     rsi, rax
0x180018925  mov     rax, [rax+208h]
0x18001892c  cmp     r12, rax
0x18001892f  jb      loc_1800189DC
0x180018935  mov     rdi, r12
0x180018938  sub     rdi, rax
0x18001893b  cmp     rdi, 7D0h
0x180018942  jnb     loc_1800189E0
0x180018948  mov     rdx, rsi; pszStr2
0x18001894b  lea     rcx, [rbp+1D0h+pszPath]; pszStr1
0x18001894f  call    cs:__imp_StrCmpICW
0x180018955  test    eax, eax
0x180018957  jnz     loc_180018A6F
0x18001895d  mov     eax, cs:dword_18003F000
0x180018963  mov     r15b, 1
0x180018966  cmp     eax, 5
0x180018969  jbe     loc_180018A6F
0x18001896f  mov     [rsp+2D0h+var_278], rdi
0x180018974  mov     [rsp+2D0h+var_270], r13
0x180018979  mov     [rsp+2D0h+var_280], r15b
0x18001897e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180018984  mov     ecx, 10000003h
0x180018989  mov     [rsp+2D0h+var_268], rax
0x18001898e  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180018994  mov     [rsp+2D0h+var_260], rax
0x180018999  lea     rdx, word_180035C56
0x1800189a0  lea     rax, [rsp+2D0h+var_278]
0x1800189a5  mov     [rsp+2D0h+var_290], rax
0x1800189aa  lea     rax, [rsp+2D0h+var_270]
0x1800189af  mov     [rsp+2D0h+var_298], rax
0x1800189b4  lea     rax, [rsp+2D0h+var_280]
0x1800189b9  mov     [rsp+2D0h+var_2A0], rax
0x1800189be  lea     rax, [rsp+2D0h+var_268]
0x1800189c3  mov     [rsp+2D0h+var_2A8], rax
0x1800189c8  lea     rax, [rsp+2D0h+var_260]
0x1800189cd  mov     [rsp+2D0h+var_2B0], rax
0x1800189d2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800189d7  jmp     loc_180018A6F
0x1800189dc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800189e0  mov     eax, cs:dword_18003F000
0x1800189e6  cmp     eax, 5
0x1800189e9  jbe     short loc_180018A53
0x1800189eb  mov     [rsp+2D0h+var_260], rdi
0x1800189f0  mov     [rsp+2D0h+var_268], r13
0x1800189f5  mov     [rsp+2D0h+var_280], 1
0x1800189fa  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180018a00  mov     ecx, 10000003h
0x180018a05  mov     [rsp+2D0h+var_270], rax
0x180018a0a  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180018a10  mov     [rsp+2D0h+var_278], rax
0x180018a15  lea     rdx, unk_180035BD0
0x180018a1c  lea     rax, [rsp+2D0h+var_260]
0x180018a21  mov     [rsp+2D0h+var_290], rax
0x180018a26  lea     rax, [rsp+2D0h+var_268]
0x180018a2b  mov     [rsp+2D0h+var_298], rax
0x180018a30  lea     rax, [rsp+2D0h+var_280]
0x180018a35  mov     [rsp+2D0h+var_2A0], rax
0x180018a3a  lea     rax, [rsp+2D0h+var_270]
0x180018a3f  mov     [rsp+2D0h+var_2A8], rax
0x180018a44  lea     rax, [rsp+2D0h+var_278]
0x180018a49  mov     [rsp+2D0h+var_2B0], rax
0x180018a4e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180018a53  mov     rcx, [r14+240h]; hdpa
0x180018a5a  mov     edx, ebx; i
0x180018a5c  call    cs:__imp_DPA_DeletePtr
0x180018a62  mov     edx, 210h
0x180018a67  mov     rcx, rsi; Block
0x180018a6a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018a6f  sub     ebx, 1
0x180018a72  jns     loc_180018913
0x180018a78  mov     al, r15b
0x180018a7b  mov     rcx, [rbp+1D0h+var_40]
0x180018a82  xor     rcx, rsp; StackCookie
0x180018a85  call    __security_check_cookie
0x180018a8a  mov     rbx, [rsp+2D0h+arg_10]
0x180018a92  add     rsp, 2A0h
0x180018a99  pop     r15
0x180018a9b  pop     r14
0x180018a9d  pop     r13
0x180018a9f  pop     r12
0x180018aa1  pop     rdi
0x180018aa2  pop     rsi
0x180018aa3  pop     rbp
0x180018aa4  retn
```
