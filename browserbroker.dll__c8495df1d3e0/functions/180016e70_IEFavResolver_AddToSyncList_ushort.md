# IEFavResolver::AddToSyncList(ushort *)

- ea: `0x180016e70`
- end: `0x180016f9f`
- name: `?AddToSyncList@IEFavResolver@@AEAAJPEAG@Z`
- size: `303`
- prototype: `__int64 __fastcall(HDPA *this, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016a9c`
- `0x1800179f0`
- `0x1800181d4`
- `0x18001a308`
- `0x18001a80c`

## callees

- `0x1800023bc`
- `0x180002d3c`
- `0x1800037ac`
- `0x18000d17c`
- `0x180016e70`

## import_xrefs

- `iertutil!__imp_DPA_InsertPtr` at `0x180016ef2`
- `iertutil!__imp_DPA_InsertPtr` at `0x180016ef2`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180016f3c`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180016f3c`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x180016ec6`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x180016ec6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180016ed6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180016ed6`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180016f2c`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180016f2c`

## pseudocode

```c
__int64 __fastcall IEFavResolver::AddToSyncList(HDPA *this, unsigned __int16 *a2)
{
  _QWORD *v4; // rdi
  HRESULT v5; // ebx
  unsigned int v6; // r11d
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  const WCHAR *v11; // [rsp+50h] [rbp-28h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v12; // [rsp+58h] [rbp-20h] BYREF
  __int64 CLSID; // [rsp+60h] [rbp-18h] BYREF
  char v14; // [rsp+90h] [rbp+18h] BYREF
  __int64 v15; // [rsp+98h] [rbp+20h] BYREF

  v4 = operator new(0x210u);
  memset_0(v4, 0, 0x210u);
  v5 = StringCchCopyW((unsigned __int16 *)v4, 0x104u, a2);
  if ( v5 >= 0 )
  {
    v5 = PathCchRemoveBackslash((PWSTR)v4, v6);
    if ( v5 >= 0 )
    {
      v4[65] = GetTickCount64();
      v5 = 0;
      if ( DPA_InsertPtr(this[72], 0x7FFFFFFF, v4) == -1 )
        v5 = -2147024882;
      if ( (unsigned int)dword_18003F000 > 5 )
      {
        v15 = v4[65];
        v11 = (const WCHAR *)v4;
        v14 = 1;
        v12 = GlobalThreadState();
        CLSID = IEConfiguration_GetCLSID(268435459);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
          v7,
          (__int64)&byte_180035CD7,
          v8,
          v9,
          &CLSID,
          (__int64 *)&v12,
          (__int64)&v14,
          &v11,
          (__int64)&v15);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016e70  mov     [rsp+arg_0], rbx
0x180016e75  mov     [rsp+arg_8], rsi
0x180016e7a  push    rdi
0x180016e7b  sub     rsp, 70h
0x180016e7f  mov     rsi, rcx
0x180016e82  mov     rbx, rdx
0x180016e85  mov     ecx, 210h; Size
0x180016e8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016e8f  xor     edx, edx; Val
0x180016e91  mov     r8d, 210h; Size
0x180016e97  mov     rcx, rax; void *
0x180016e9a  mov     rdi, rax
0x180016e9d  call    memset_0
0x180016ea2  mov     r11d, 104h
0x180016ea8  mov     r8, rbx; unsigned __int16 *
0x180016eab  mov     edx, r11d; unsigned __int64
0x180016eae  mov     rcx, rdi; unsigned __int16 *
0x180016eb1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016eb6  mov     ebx, eax
0x180016eb8  test    eax, eax
0x180016eba  js      loc_180016F8B
0x180016ec0  mov     edx, r11d; cchPath
0x180016ec3  mov     rcx, rdi; pszPath
0x180016ec6  call    cs:__imp_PathCchRemoveBackslash
0x180016ecc  mov     ebx, eax
0x180016ece  test    eax, eax
0x180016ed0  js      loc_180016F8B
0x180016ed6  call    cs:__imp_GetTickCount64
0x180016edc  mov     [rdi+208h], rax
0x180016ee3  mov     r8, rdi; p
0x180016ee6  mov     rcx, [rsi+240h]; hdpa
0x180016eed  mov     edx, 7FFFFFFFh; i
0x180016ef2  call    cs:__imp_DPA_InsertPtr
0x180016ef8  xor     ebx, ebx
0x180016efa  mov     ecx, 8007000Eh
0x180016eff  cmp     eax, 0FFFFFFFFh
0x180016f02  mov     eax, cs:dword_18003F000
0x180016f08  cmovz   ebx, ecx
0x180016f0b  cmp     eax, 5
0x180016f0e  jbe     short loc_180016F8B
0x180016f10  mov     rax, [rdi+208h]
0x180016f17  mov     [rsp+78h+arg_18], rax
0x180016f1f  mov     [rsp+78h+var_28], rdi
0x180016f24  mov     [rsp+78h+arg_10], 1
0x180016f2c  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180016f32  mov     ecx, 10000003h
0x180016f37  mov     [rsp+78h+var_20], rax
0x180016f3c  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180016f42  mov     [rsp+78h+var_18], rax
0x180016f47  lea     rdx, byte_180035CD7
0x180016f4e  lea     rax, [rsp+78h+arg_18]
0x180016f56  mov     [rsp+78h+var_38], rax
0x180016f5b  lea     rax, [rsp+78h+var_28]
0x180016f60  mov     [rsp+78h+var_40], rax
0x180016f65  lea     rax, [rsp+78h+arg_10]
0x180016f6d  mov     [rsp+78h+var_48], rax
0x180016f72  lea     rax, [rsp+78h+var_20]
0x180016f77  mov     [rsp+78h+var_50], rax
0x180016f7c  lea     rax, [rsp+78h+var_18]
0x180016f81  mov     [rsp+78h+var_58], rax
0x180016f86  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180016f8b  lea     r11, [rsp+78h+var_8]
0x180016f90  mov     eax, ebx
0x180016f92  mov     rbx, [r11+10h]
0x180016f96  mov     rsi, [r11+18h]
0x180016f9a  mov     rsp, r11
0x180016f9d  pop     rdi
0x180016f9e  retn
```
