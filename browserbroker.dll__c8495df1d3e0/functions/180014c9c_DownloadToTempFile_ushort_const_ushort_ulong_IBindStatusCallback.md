# DownloadToTempFile(ushort const *,ushort *,ulong,IBindStatusCallback *)

- ea: `0x180014c9c`
- end: `0x180014e67`
- name: `?DownloadToTempFile@@YAJPEBGPEAGKPEAUIBindStatusCallback@@@Z`
- size: `459`
- prototype: `__int64 __fastcall(LPCWSTR, unsigned __int16 *, unsigned int, struct IBindStatusCallback *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000fad8`
- `0x180015350`

## callees

- `0x180001010`
- `0x180001358`
- `0x18000187c`
- `0x180006c90`
- `0x18000d17c`
- `0x180014c9c`
- `0x180015140`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180014d1a`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180014e05`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180014d1a`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180014e05`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180014db1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180014db1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014dc9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180014dc9`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180014d0b`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180014df6`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180014d0b`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180014df6`
- `urlmon!URLDownloadToFileW` at `0x180014d9d`
- `urlmon!URLDownloadToFileW` at `0x180014d9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DownloadToTempFile(LPCWSTR a1, unsigned __int16 *a2, int a3, struct IBindStatusCallback *a4)
{
  __int64 v7; // rcx
  HRESULT TempFileName; // edi
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  const WCHAR *v12; // rbx
  unsigned __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  HRESULT v18; // [rsp+68h] [rbp-9h] BYREF
  LPCWSTR lpFileName; // [rsp+70h] [rbp-1h] BYREF
  struct IBindStatusCallback *v20; // [rsp+78h] [rbp+7h] BYREF
  const WCHAR *v21; // [rsp+80h] [rbp+Fh] BYREF
  const WCHAR *v22; // [rsp+88h] [rbp+17h] BYREF
  struct IE_GLOBAL_THREAD_STATE *CLSID; // [rsp+90h] [rbp+1Fh] BYREF
  __int64 v24[2]; // [rsp+98h] [rbp+27h] BYREF
  int v25; // [rsp+E8h] [rbp+77h] BYREF

  v25 = a3;
  lpFileName = 0;
  TempFileName = GetTempFileName(a1);
  if ( (unsigned int)dword_18003F000 > 5 && (unsigned __int8)tlgKeywordOn(v7, 0x10000000) )
  {
    v18 = TempFileName;
    v20 = a4;
    v21 = a2;
    v22 = a1;
    LOBYTE(v25) = 1;
    CLSID = GlobalThreadState();
    v24[0] = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v9,
      (__int64)&unk_1800357F0,
      v10,
      v11,
      v24,
      (__int64 *)&CLSID,
      (__int64)&v25,
      &v22,
      &v21,
      (__int64)&v20,
      (__int64)&v18);
  }
  if ( TempFileName >= 0 )
  {
    v12 = lpFileName;
    v13 = -1;
    do
      ++v13;
    while ( lpFileName[v13] );
    if ( v13 >= 0x104 )
    {
      TempFileName = -2147024774;
    }
    else
    {
      TempFileName = URLDownloadToFileW(0, a1, lpFileName, 0, a4);
      if ( TempFileName < 0 )
      {
        DeleteFileW(v12);
      }
      else
      {
        SetFileAttributesW(v12, 0x80u);
        StringCchCopyW(a2, 0x104u, v12);
      }
    }
  }
  if ( (unsigned int)dword_18003F000 > 5 && (unsigned __int8)tlgKeywordOn(v7, 0x10000000) )
  {
    v18 = TempFileName;
    LOBYTE(v25) = 1;
    v24[0] = (__int64)GlobalThreadState();
    CLSID = (struct IE_GLOBAL_THREAD_STATE *)IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
      v14,
      (__int64)byte_180035783,
      v15,
      v16,
      &CLSID,
      v24,
      (__int64)&v25,
      (__int64)&v18);
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&lpFileName);
  return (unsigned int)TempFileName;
}

```

## disassembly

```asm
0x180014c9c  mov     rax, rsp
0x180014c9f  mov     [rax+8], rbx
0x180014ca3  mov     [rax+10h], rsi
0x180014ca7  mov     [rax+18h], r8d
0x180014cab  push    rbp
0x180014cac  push    rdi
0x180014cad  push    r12
0x180014caf  push    r14
0x180014cb1  push    r15
0x180014cb3  lea     rbp, [rax-5Fh]
0x180014cb7  sub     rsp, 0A0h
0x180014cbe  mov     r14, r9
0x180014cc1  mov     r15, rdx
0x180014cc4  mov     rsi, rcx
0x180014cc7  xor     r12d, r12d
0x180014cca  mov     [rbp+57h+lpFileName], r12
0x180014cce  lea     rdx, [rbp+57h+lpFileName]
0x180014cd2  call    _GetTempFileName
0x180014cd7  mov     edi, eax
0x180014cd9  mov     r8d, cs:dword_18003F000
0x180014ce0  cmp     r8d, 5
0x180014ce4  jbe     loc_180014D6F
0x180014cea  mov     edx, 10000000h
0x180014cef  call    _tlgKeywordOn
0x180014cf4  test    al, al
0x180014cf6  jz      short loc_180014D6F
0x180014cf8  mov     [rbp+57h+var_60], edi
0x180014cfb  mov     [rbp+57h+var_50], r14
0x180014cff  mov     [rbp+57h+var_48], r15
0x180014d03  mov     [rbp+57h+var_40], rsi
0x180014d07  mov     byte ptr [rbp+57h+arg_10], 1
0x180014d0b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180014d11  mov     [rbp+57h+var_38], rax
0x180014d15  mov     ecx, 10000003h
0x180014d1a  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180014d20  mov     [rbp+57h+var_30], rax
0x180014d24  lea     rax, [rbp+57h+var_60]
0x180014d28  mov     [rsp+0C0h+var_70], rax
0x180014d2d  lea     rax, [rbp+57h+var_50]
0x180014d31  mov     [rsp+0C0h+var_78], rax
0x180014d36  lea     rax, [rbp+57h+var_48]
0x180014d3a  mov     [rsp+0C0h+var_80], rax
0x180014d3f  lea     rax, [rbp+57h+var_40]
0x180014d43  mov     [rsp+0C0h+var_88], rax
0x180014d48  lea     rax, [rbp+57h+arg_10]
0x180014d4c  mov     [rsp+0C0h+var_90], rax
0x180014d51  lea     rax, [rbp+57h+var_38]
0x180014d55  mov     [rsp+0C0h+var_98], rax
0x180014d5a  lea     rax, [rbp+57h+var_30]
0x180014d5e  mov     [rsp+0C0h+var_A0], rax
0x180014d63  lea     rdx, unk_1800357F0
0x180014d6a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180014d6f  test    edi, edi
0x180014d71  js      short loc_180014DD6
0x180014d73  mov     rbx, [rbp+57h+lpFileName]
0x180014d77  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014d7b  inc     rax
0x180014d7e  cmp     [rbx+rax*2], r12w
0x180014d83  jnz     short loc_180014D7B
0x180014d85  cmp     rax, 104h
0x180014d8b  jnb     short loc_180014DD1
0x180014d8d  mov     [rsp+0C0h+var_A0], r14; LPBINDSTATUSCALLBACK
0x180014d92  xor     r9d, r9d; DWORD
0x180014d95  mov     r8, rbx; LPCWSTR
0x180014d98  mov     rdx, rsi; LPCWSTR
0x180014d9b  xor     ecx, ecx; LPUNKNOWN
0x180014d9d  call    cs:__imp_URLDownloadToFileW
0x180014da3  mov     edi, eax
0x180014da5  mov     rcx, rbx; lpFileName
0x180014da8  test    eax, eax
0x180014daa  js      short loc_180014DC9
0x180014dac  mov     edx, 80h; dwFileAttributes
0x180014db1  call    cs:__imp_SetFileAttributesW
0x180014db7  mov     r8, rbx; unsigned __int16 *
0x180014dba  mov     edx, 104h; unsigned __int64
0x180014dbf  mov     rcx, r15; unsigned __int16 *
0x180014dc2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014dc7  jmp     short loc_180014DD6
0x180014dc9  call    cs:__imp_DeleteFileW
0x180014dcf  jmp     short loc_180014DD6
0x180014dd1  mov     edi, 8007007Ah
0x180014dd6  mov     eax, cs:dword_18003F000
0x180014ddc  cmp     eax, 5
0x180014ddf  jbe     short loc_180014E40
0x180014de1  mov     edx, 10000000h
0x180014de6  call    _tlgKeywordOn
0x180014deb  test    al, al
0x180014ded  jz      short loc_180014E40
0x180014def  mov     [rbp+57h+var_60], edi
0x180014df2  mov     byte ptr [rbp+57h+arg_10], 1
0x180014df6  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180014dfc  mov     [rbp+57h+var_30], rax
0x180014e00  mov     ecx, 10000003h
0x180014e05  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180014e0b  mov     [rbp+57h+var_38], rax
0x180014e0f  lea     rax, [rbp+57h+var_60]
0x180014e13  mov     [rsp+0C0h+var_88], rax
0x180014e18  lea     rax, [rbp+57h+arg_10]
0x180014e1c  mov     [rsp+0C0h+var_90], rax
0x180014e21  lea     rax, [rbp+57h+var_30]
0x180014e25  mov     [rsp+0C0h+var_98], rax
0x180014e2a  lea     rax, [rbp+57h+var_38]
0x180014e2e  mov     [rsp+0C0h+var_A0], rax
0x180014e33  lea     rdx, byte_180035783
0x180014e3a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x180014e3f  nop
0x180014e40  lea     rcx, [rbp+57h+lpFileName]
0x180014e44  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180014e49  mov     eax, edi
0x180014e4b  lea     r11, [rsp+0C0h+var_20]
0x180014e53  mov     rbx, [r11+30h]
0x180014e57  mov     rsi, [r11+38h]
0x180014e5b  mov     rsp, r11
0x180014e5e  pop     r15
0x180014e60  pop     r14
0x180014e62  pop     r12
0x180014e64  pop     rdi
0x180014e65  pop     rbp
0x180014e66  retn
```
