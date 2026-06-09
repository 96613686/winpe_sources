# IEFavResolver::HandleFaviconData(ushort const *,ushort const *,ushort const *,uchar *,ulong)

- ea: `0x1800181d4`
- end: `0x180018520`
- name: `?HandleFaviconData@IEFavResolver@@AEAAJPEBG00PEAEK@Z`
- size: `844`
- prototype: `__int64 __fastcall(IEFavResolver *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180019b8c`

## callees

- `0x18000206c`
- `0x180002ce0`
- `0x180006cc4`
- `0x180016968`
- `0x180016e70`
- `0x180017854`
- `0x18001787c`
- `0x180017ba0`
- `0x180017e50`
- `0x1800181d4`
- `0x18002d010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001849c`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001849c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800182e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800182e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018321`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018321`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800182d1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800182d1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800182a1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800182a1`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001848d`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001848d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800183df`
- `OLEAUT32!__imp_SysAllocString` at `0x1800183df`
- `OLEAUT32!__imp_SysFreeString` at `0x180018445`
- `OLEAUT32!__imp_SysFreeString` at `0x18001844f`
- `OLEAUT32!__imp_SysFreeString` at `0x180018445`
- `OLEAUT32!__imp_SysFreeString` at `0x18001844f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall IEFavResolver::HandleFaviconData(
        IEFavResolver *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite)
{
  IEFavResolver *v10; // rcx
  HRESULT FullPathFromUnifiedPath; // esi
  IEFavResolver *v12; // rcx
  unsigned int v13; // r9d
  HANDLE FileW; // rax
  void *v15; // rbx
  OLECHAR *v16; // rdi
  BSTR v17; // rax
  int v18; // ecx
  OLECHAR *v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned int dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  char v25[8]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+68h] [rbp-98h] BYREF
  const WCHAR *v27; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  BSTR CLSID; // [rsp+80h] [rbp-80h] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h] BYREF
  BSTR v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  const WCHAR *v33; // [rsp+A0h] [rbp-60h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v34; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v35[264]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v36[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR FileName[264]; // [rsp+4D0h] [rbp+3D0h] BYREF

  FullPathFromUnifiedPath = IEFavResolver::GetFullPathFromUnifiedPath(this, a3, v36, (unsigned int)a4);
  if ( FullPathFromUnifiedPath >= 0 )
  {
    FullPathFromUnifiedPath = IEFavResolver::GetCompleteItemPathFromTitle(v10, v36, a2, 0, v35, dwFlagsAndAttributes);
    if ( FullPathFromUnifiedPath >= 0 )
    {
      FullPathFromUnifiedPath = IEFavResolver::BuildAlternateStreamFilename(v12, v35, FileName, v13);
      if ( FullPathFromUnifiedPath >= 0 )
      {
        IEFavResolver::AddToSyncList((HDPA *)this, v35);
        FullPathFromUnifiedPath = -2147467259;
        FileW = CreateFileW(FileName, 0x40000000u, 2u, 0, 2u, 0, 0);
        v15 = FileW;
        if ( FileW != (HANDLE)-1LL )
        {
          NumberOfBytesWritten[0] = 0;
          if ( WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, NumberOfBytesWritten, 0)
            && nNumberOfBytesToWrite == NumberOfBytesWritten[0] )
          {
            FullPathFromUnifiedPath = 0;
          }
          CloseHandle(v15);
          if ( FullPathFromUnifiedPath >= 0 )
          {
            *(_QWORD *)NumberOfBytesWritten = 0;
            FullPathFromUnifiedPath = CoCreateInstance(
                                        &CLSID_InternetShortcut,
                                        0,
                                        1u,
                                        &GUID_0000010b_0000_0000_c000_000000000046,
                                        (LPVOID *)NumberOfBytesWritten);
            if ( FullPathFromUnifiedPath >= 0 )
            {
              FullPathFromUnifiedPath = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64))(**(_QWORD **)NumberOfBytesWritten + 40LL))(
                                          *(_QWORD *)NumberOfBytesWritten,
                                          v35,
                                          2);
              if ( FullPathFromUnifiedPath >= 0 )
              {
                v27 = 0;
                FullPathFromUnifiedPath = (***(__int64 (__fastcall ****)(_QWORD, GUID *, const WCHAR **))NumberOfBytesWritten)(
                                            *(_QWORD *)NumberOfBytesWritten,
                                            &GUID_fb700430_952c_11d1_946f_000000000000,
                                            &v27);
                if ( FullPathFromUnifiedPath >= 0 )
                {
                  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a4);
                  v32 = 0;
                  v30 = 8;
                  v16 = bstrString;
                  v31 = bstrString;
                  FullPathFromUnifiedPath = (*(__int64 (__fastcall **)(const WCHAR *, const wchar_t *, const wchar_t *, __int64 *))(*(_QWORD *)v27 + 32LL))(
                                              v27,
                                              L"InternetShortcut",
                                              L"IconFile",
                                              &v30);
                  if ( FullPathFromUnifiedPath >= 0 )
                  {
                    v17 = SysAllocString(L"1");
                    v19 = v17;
                    CLSID = v17;
                    if ( !v17 )
                      ATL::AtlThrowImpl(v18);
                    LOWORD(v30) = 8;
                    v31 = v17;
                    FullPathFromUnifiedPath = (*(__int64 (__fastcall **)(const WCHAR *, const wchar_t *, const wchar_t *, __int64 *))(*(_QWORD *)v27 + 32LL))(
                                                v27,
                                                L"InternetShortcut",
                                                L"IconIndex",
                                                &v30);
                    if ( FullPathFromUnifiedPath >= 0 )
                      FullPathFromUnifiedPath = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)NumberOfBytesWritten + 48LL))(
                                                  *(_QWORD *)NumberOfBytesWritten,
                                                  0,
                                                  1);
                    SysFreeString(v19);
                  }
                  SysFreeString(v16);
                }
                ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&v27);
              }
            }
            ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)NumberOfBytesWritten);
          }
        }
      }
    }
  }
  if ( (unsigned int)dword_18003F000 > 5 )
  {
    NumberOfBytesWritten[0] = FullPathFromUnifiedPath;
    bstrString = a4;
    v27 = a3;
    v33 = a2;
    v25[0] = 1;
    v34 = GlobalThreadState();
    CLSID = (BSTR)IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v20,
      (__int64)byte_180035D4B,
      v21,
      v22,
      (__int64 *)&CLSID,
      (__int64 *)&v34,
      (__int64)v25,
      &v33,
      &v27,
      (const WCHAR **)&bstrString,
      (__int64)NumberOfBytesWritten);
  }
  return (unsigned int)FullPathFromUnifiedPath;
}

```

## disassembly

```asm
0x1800181d4  push    rbp
0x1800181d6  push    rbx
0x1800181d7  push    rsi
0x1800181d8  push    rdi
0x1800181d9  push    r12
0x1800181db  push    r13
0x1800181dd  push    r14
0x1800181df  push    r15
0x1800181e1  lea     rbp, [rsp-5F8h]
0x1800181e9  sub     rsp, 6F8h
0x1800181f0  mov     rax, cs:__security_cookie
0x1800181f7  xor     rax, rsp
0x1800181fa  mov     [rbp+630h+var_50], rax
0x180018201  mov     r13, r9
0x180018204  mov     r12, r8
0x180018207  mov     r15, rdx
0x18001820a  mov     rbx, rcx
0x18001820d  mov     r14, [rbp+630h+lpBuffer]
0x180018214  lea     r8, [rbp+630h+var_470]; unsigned __int16 *
0x18001821b  mov     rdx, r12; unsigned __int16 *
0x18001821e  call    ?GetFullPathFromUnifiedPath@IEFavResolver@@AEAAJPEBGPEAGI@Z; IEFavResolver::GetFullPathFromUnifiedPath(ushort const *,ushort *,uint)
0x180018223  mov     esi, eax
0x180018225  xor     edi, edi
0x180018227  test    eax, eax
0x180018229  js      loc_18001846B
0x18001822f  lea     rax, [rbp+630h+var_680]
0x180018233  mov     qword ptr [rsp+730h+dwCreationDisposition], rax; unsigned __int16 *
0x180018238  xor     r9d, r9d; bool
0x18001823b  mov     r8, r15; unsigned __int16 *
0x18001823e  lea     rdx, [rbp+630h+var_470]; unsigned __int16 *
0x180018245  call    ?GetCompleteItemPathFromTitle@IEFavResolver@@AEAAJPEBG0_NPEAGI@Z; IEFavResolver::GetCompleteItemPathFromTitle(ushort const *,ushort const *,bool,ushort *,uint)
0x18001824a  mov     esi, eax
0x18001824c  test    eax, eax
0x18001824e  js      loc_18001846B
0x180018254  lea     r8, [rbp+630h+FileName]; unsigned __int16 *
0x18001825b  lea     rdx, [rbp+630h+var_680]; unsigned __int16 *
0x18001825f  call    ?BuildAlternateStreamFilename@IEFavResolver@@AEAAJPEBGPEAGK@Z; IEFavResolver::BuildAlternateStreamFilename(ushort const *,ushort *,ulong)
0x180018264  mov     esi, eax
0x180018266  test    eax, eax
0x180018268  js      loc_18001846B
0x18001826e  lea     rdx, [rbp+630h+var_680]; unsigned __int16 *
0x180018272  mov     rcx, rbx; this
0x180018275  call    ?AddToSyncList@IEFavResolver@@AEAAJPEAG@Z; IEFavResolver::AddToSyncList(ushort *)
0x18001827a  mov     esi, 80004005h
0x18001827f  mov     [rsp+730h+hTemplateFile], rdi; hTemplateFile
0x180018284  mov     [rsp+730h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180018288  lea     eax, [rdi+2]
0x18001828b  mov     [rsp+730h+dwCreationDisposition], eax; dwCreationDisposition
0x18001828f  xor     r9d, r9d; lpSecurityAttributes
0x180018292  mov     r8d, eax; dwShareMode
0x180018295  mov     edx, 40000000h; dwDesiredAccess
0x18001829a  lea     rcx, [rbp+630h+FileName]; lpFileName
0x1800182a1  call    cs:__imp_CreateFileW
0x1800182a7  mov     rbx, rax
0x1800182aa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800182ae  jz      loc_18001846B
0x1800182b4  mov     [rsp+730h+NumberOfBytesWritten], edi
0x1800182b8  mov     qword ptr [rsp+730h+dwCreationDisposition], rdi; lpOverlapped
0x1800182bd  lea     r9, [rsp+730h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800182c2  mov     edi, [rbp+630h+nNumberOfBytesToWrite]
0x1800182c8  mov     r8d, edi; nNumberOfBytesToWrite
0x1800182cb  mov     rdx, r14; lpBuffer
0x1800182ce  mov     rcx, rax; hFile
0x1800182d1  call    cs:__imp_WriteFile
0x1800182d7  test    eax, eax
0x1800182d9  jz      short loc_1800182E4
0x1800182db  xor     eax, eax
0x1800182dd  cmp     edi, [rsp+730h+NumberOfBytesWritten]
0x1800182e1  cmovz   esi, eax
0x1800182e4  mov     rcx, rbx; hObject
0x1800182e7  call    cs:__imp_CloseHandle
0x1800182ed  test    esi, esi
0x1800182ef  js      loc_18001846B
0x1800182f5  mov     qword ptr [rsp+730h+NumberOfBytesWritten], 0
0x1800182fe  lea     rax, [rsp+730h+NumberOfBytesWritten]
0x180018303  mov     qword ptr [rsp+730h+dwCreationDisposition], rax; ppv
0x180018308  lea     r9, _GUID_0000010b_0000_0000_c000_000000000046; riid
0x18001830f  mov     r14d, 1
0x180018315  mov     r8d, r14d; dwClsContext
0x180018318  xor     edx, edx; pUnkOuter
0x18001831a  lea     rcx, CLSID_InternetShortcut; rclsid
0x180018321  call    cs:__imp_CoCreateInstance
0x180018327  mov     esi, eax
0x180018329  test    eax, eax
0x18001832b  js      loc_180018461
0x180018331  mov     rcx, qword ptr [rsp+730h+NumberOfBytesWritten]
0x180018336  mov     rax, [rcx]
0x180018339  lea     r8d, [r14+1]
0x18001833d  lea     rdx, [rbp+630h+var_680]
0x180018341  mov     rax, [rax+28h]
0x180018345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001834a  mov     esi, eax
0x18001834c  test    eax, eax
0x18001834e  js      loc_180018461
0x180018354  mov     [rsp+730h+var_6C0], 0
0x18001835d  mov     rcx, qword ptr [rsp+730h+NumberOfBytesWritten]
0x180018362  mov     rax, [rcx]
0x180018365  lea     r8, [rsp+730h+var_6C0]
0x18001836a  lea     rdx, _GUID_fb700430_952c_11d1_946f_000000000000
0x180018371  mov     rax, [rax]
0x180018374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018379  mov     esi, eax
0x18001837b  test    eax, eax
0x18001837d  js      loc_180018456
0x180018383  mov     rdx, r13; unsigned __int16 *
0x180018386  lea     rcx, [rsp+730h+bstrString]; this
0x18001838b  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180018390  nop
0x180018391  xorps   xmm0, xmm0
0x180018394  xor     eax, eax
0x180018396  movups  [rbp+630h+var_6A8], xmm0
0x18001839a  mov     [rbp+630h+var_698], rax
0x18001839e  lea     eax, [r14+7]
0x1800183a2  mov     word ptr [rbp+630h+var_6A8], ax
0x1800183a6  mov     rdi, [rsp+730h+bstrString]
0x1800183ab  mov     qword ptr [rbp+630h+var_6A8+8], rdi
0x1800183af  mov     rcx, [rsp+730h+var_6C0]
0x1800183b4  mov     rax, [rcx]
0x1800183b7  lea     r9, [rbp+630h+var_6A8]
0x1800183bb  lea     r8, aIconfile; "IconFile"
0x1800183c2  lea     rdx, aInternetshortc; "InternetShortcut"
0x1800183c9  mov     rax, [rax+20h]
0x1800183cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183d2  mov     esi, eax
0x1800183d4  test    eax, eax
0x1800183d6  js      short loc_18001844C
0x1800183d8  lea     rcx, psz; "1"
0x1800183df  call    cs:__imp_SysAllocString
0x1800183e5  mov     rbx, rax
0x1800183e8  mov     [rbp+630h+var_6B0], rax
0x1800183ec  test    rax, rax
0x1800183ef  jz      loc_18001851A
0x1800183f5  lea     eax, [r14+7]
0x1800183f9  mov     word ptr [rbp+630h+var_6A8], ax
0x1800183fd  mov     qword ptr [rbp+630h+var_6A8+8], rbx
0x180018401  mov     rcx, [rsp+730h+var_6C0]
0x180018406  mov     rax, [rcx]
0x180018409  lea     r9, [rbp+630h+var_6A8]
0x18001840d  lea     r8, aIconindex; "IconIndex"
0x180018414  lea     rdx, aInternetshortc; "InternetShortcut"
0x18001841b  mov     rax, [rax+20h]
0x18001841f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018424  mov     esi, eax
0x180018426  test    eax, eax
0x180018428  js      short loc_180018442
0x18001842a  mov     rcx, qword ptr [rsp+730h+NumberOfBytesWritten]
0x18001842f  mov     rax, [rcx]
0x180018432  mov     r8d, r14d
0x180018435  xor     edx, edx
0x180018437  mov     rax, [rax+30h]
0x18001843b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018440  mov     esi, eax
0x180018442  mov     rcx, rbx; bstrString
0x180018445  call    cs:__imp_SysFreeString
0x18001844b  nop
0x18001844c  mov     rcx, rdi; bstrString
0x18001844f  call    cs:__imp_SysFreeString
0x180018455  nop
0x180018456  lea     rcx, [rsp+730h+var_6C0]
0x18001845b  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180018460  nop
0x180018461  lea     rcx, [rsp+730h+NumberOfBytesWritten]
0x180018466  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x18001846b  mov     eax, cs:dword_18003F000
0x180018471  cmp     eax, 5
0x180018474  jbe     short loc_1800184F5
0x180018476  mov     [rsp+730h+NumberOfBytesWritten], esi
0x18001847a  mov     [rsp+730h+bstrString], r13
0x18001847f  mov     [rsp+730h+var_6C0], r12
0x180018484  mov     [rbp+630h+var_690], r15
0x180018488  mov     [rsp+730h+var_6D0], 1
0x18001848d  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180018493  mov     [rbp+630h+var_688], rax
0x180018497  mov     ecx, 10000003h
0x18001849c  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1800184a2  mov     [rbp+630h+var_6B0], rax
0x1800184a6  lea     rax, [rsp+730h+NumberOfBytesWritten]
0x1800184ab  mov     [rsp+730h+var_6E0], rax
0x1800184b0  lea     rax, [rsp+730h+bstrString]
0x1800184b5  mov     [rsp+730h+var_6E8], rax
0x1800184ba  lea     rax, [rsp+730h+var_6C0]
0x1800184bf  mov     [rsp+730h+var_6F0], rax
0x1800184c4  lea     rax, [rbp+630h+var_690]
0x1800184c8  mov     [rsp+730h+var_6F8], rax
0x1800184cd  lea     rax, [rsp+730h+var_6D0]
0x1800184d2  mov     [rsp+730h+hTemplateFile], rax
0x1800184d7  lea     rax, [rbp+630h+var_688]
0x1800184db  mov     qword ptr [rsp+730h+dwFlagsAndAttributes], rax
0x1800184e0  lea     rax, [rbp+630h+var_6B0]
0x1800184e4  mov     qword ptr [rsp+730h+dwCreationDisposition], rax
0x1800184e9  lea     rdx, byte_180035D4B
0x1800184f0  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U3@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@55AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800184f5  mov     eax, esi
0x1800184f7  mov     rcx, [rbp+630h+var_50]
0x1800184fe  xor     rcx, rsp; StackCookie
0x180018501  call    __security_check_cookie
0x180018506  add     rsp, 6F8h
0x18001850d  pop     r15
0x18001850f  pop     r14
0x180018511  pop     r13
0x180018513  pop     r12
0x180018515  pop     rdi
0x180018516  pop     rsi
0x180018517  pop     rbx
0x180018518  pop     rbp
0x180018519  retn
0x18001851a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
