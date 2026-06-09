# AppReadiness::Tasks::Store::StoreMetadata::Parse(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x18006863c`
- end: `0x1800688bd`
- name: `?Parse@StoreMetadata@Store@Tasks@AppReadiness@@AEAAXAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `641`
- prototype: `__int64 __fastcall(IUnknown *this, struct IUnknownVtbl **, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180067d6c`
- `0x180067f58`

## callees

- `0x180002958`
- `0x180027a4c`
- `0x18002eefc`
- `0x18003ecb4`
- `0x1800490d0`
- `0x18006863c`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006880b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006880b`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x180068707`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x180068707`
- `XmlLite!CreateXmlReader` at `0x18006868a`
- `XmlLite!CreateXmlReader` at `0x18006868a`

## string_xrefs

- `0x18006869c`: `onecoreuap\shell\appreadiness\src\tasks\storemetadata.cpp`
- `0x180068719`: `onecoreuap\shell\appreadiness\src\tasks\storemetadata.cpp`
- `0x18006876f`: `onecoreuap\shell\appreadiness\src\tasks\storemetadata.cpp`
- `0x18006882c`: `onecoreuap\shell\appreadiness\src\tasks\storemetadata.cpp`
- `0x18006886d`: `onecoreuap\shell\appreadiness\src\tasks\storemetadata.cpp`
- `0x1800686af`: `CreateXmlReader(IID_PPV_ARGS(&reader), nullptr)`
- `0x1800686a8`: `AppReadiness::Tasks::Store::StoreMetadata::Parse`
- `0x180068725`: `AppReadiness::Tasks::Store::StoreMetadata::Parse`
- `0x18006877b`: `AppReadiness::Tasks::Store::StoreMetadata::Parse`
- `0x180068838`: `AppReadiness::Tasks::Store::StoreMetadata::Parse`
- `0x180068879`: `AppReadiness::Tasks::Store::StoreMetadata::Parse`
- `0x180068880`: `reader->GetLocalName(&localName, nullptr)`
- `0x18006872c`: `CreateXmlReaderInputWithEncodingName(reinterpret_cast<ISequentialStream*>(this), nullptr, L"utf-16", true, nullptr, &readerInput)`
- `0x180068782`: `reader->SetInput(readerInput.Get())`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall AppReadiness::Tasks::Store::StoreMetadata::Parse(
        IUnknown *this,
        struct IUnknownVtbl **a2,
        __int64 a3)
{
  __int64 v4; // rcx
  HRESULT v5; // eax
  HRESULT v6; // eax
  int v7; // eax
  int v8; // eax
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  int v11; // [rsp+80h] [rbp+18h] BYREF
  void *ppvObject; // [rsp+88h] [rbp+20h] BYREF
  IXmlReaderInput *ppInput; // [rsp+90h] [rbp+28h] BYREF
  LPCWCH lpString2; // [rsp+98h] [rbp+30h] BYREF

  this[2].lpVtbl = *a2;
  this[3].lpVtbl = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a2, a2, a3, a2);
  this[4].lpVtbl = *(struct IUnknownVtbl **)(v4 + 8);
  ppvObject = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
  v5 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v5 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v5,
      "CreateXmlReader(IID_PPV_ARGS(&reader), nullptr)",
      "AppReadiness::Tasks::Store::StoreMetadata::Parse",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\storemetadata.cpp",
      76);
    throw (Windows::HResultException *)pExceptionObject;
  }
  ppInput = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
  v6 = CreateXmlReaderInputWithEncodingName(this, 0, L"utf-16", 1, 0, &ppInput);
  if ( v6 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v6,
      "CreateXmlReaderInputWithEncodingName(reinterpret_cast<ISequentialStream*>(this), nullptr, L\"utf-16\", true, nullp"
      "tr, &readerInput)",
      "AppReadiness::Tasks::Store::StoreMetadata::Parse",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\storemetadata.cpp",
      78);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v7 = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppInput);
  if ( v7 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v7,
      "reader->SetInput(readerInput.Get())",
      "AppReadiness::Tasks::Store::StoreMetadata::Parse",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\storemetadata.cpp",
      79);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v11 = 0;
  while ( !(*(unsigned int (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v11) )
  {
    lpString2 = 0;
    if ( v11 == 1 )
    {
      v8 = (*(__int64 (__fastcall **)(void *, LPCWCH *, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
             ppvObject,
             &lpString2,
             0);
      if ( v8 < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          v8,
          "reader->GetLocalName(&localName, nullptr)",
          "AppReadiness::Tasks::Store::StoreMetadata::Parse",
          "onecoreuap\\shell\\appreadiness\\src\\tasks\\storemetadata.cpp",
          88);
        throw (Windows::HResultException *)pExceptionObject;
      }
      if ( CompareStringOrdinal(L"Ptl", -1, lpString2, -1, 1) != 2 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          -1072894406,
          "WC_E_ROOTELEMENT",
          "AppReadiness::Tasks::Store::StoreMetadata::Parse",
          "onecoreuap\\shell\\appreadiness\\src\\tasks\\storemetadata.cpp",
          96);
        throw (Windows::HResultException *)pExceptionObject;
      }
      AppReadiness::Tasks::Store::StoreMetadata::ReadPtl(
        (AppReadiness::Tasks::Store::StoreMetadata *)this,
        (struct IXmlReader *)ppvObject);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
}

```

## disassembly

```asm
0x18006863c  push    rbp
0x18006863e  push    rbx
0x18006863f  mov     rbp, rsp
0x180068642  sub     rsp, 68h
0x180068646  mov     r9, rdx
0x180068649  mov     rbx, rcx
0x18006864c  mov     rax, [rdx]
0x18006864f  mov     [rcx+10h], rax
0x180068653  mov     qword ptr [rcx+18h], 0
0x18006865b  mov     rcx, rdx
0x18006865e  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180068663  mov     r9, [rcx+8]
0x180068667  mov     [rbx+20h], r9
0x18006866b  mov     [rbp+ppvObject], 0
0x180068673  lea     rcx, [rbp+ppvObject]
0x180068677  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006867c  xor     r8d, r8d; pMalloc
0x18006867f  lea     rdx, [rbp+ppvObject]; ppvObject
0x180068683  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18006868a  call    cs:__imp_CreateXmlReader
0x180068690  test    eax, eax
0x180068692  jns     short loc_1800686D2
0x180068694  mov     dword ptr [rsp+68h+ppInput], 4Ch ; 'L'; int
0x18006869c  lea     rcx, aOnecoreuapShel_37; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x1800686a3  mov     [rsp+68h+pwszBaseUri], rcx; char *
0x1800686a8  lea     r9, aAppreadinessTa_35; "AppReadiness::Tasks::Store::StoreMetada"...
0x1800686af  lea     r8, aCreatexmlreade_1; "CreateXmlReader(IID_PPV_ARGS(&reader), "...
0x1800686b6  mov     edx, eax; int
0x1800686b8  lea     rcx, [rbp+pExceptionObject]; this
0x1800686bc  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800686c1  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800686c8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800686cc  call    _CxxThrowException_0
0x1800686d2  mov     [rbp+arg_10], 0
0x1800686da  lea     rcx, [rbp+arg_10]
0x1800686de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800686e3  lea     rax, [rbp+arg_10]
0x1800686e7  mov     [rsp+68h+ppInput], rax; ppInput
0x1800686ec  mov     [rsp+68h+pwszBaseUri], 0; pwszBaseUri
0x1800686f5  mov     r9d, 1; fEncodingHint
0x1800686fb  lea     r8, pwszEncodingName; "utf-16"
0x180068702  xor     edx, edx; pMalloc
0x180068704  mov     rcx, rbx; pInputStream
0x180068707  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x18006870d  test    eax, eax
0x18006870f  jns     short loc_18006874F
0x180068711  mov     dword ptr [rsp+68h+ppInput], 4Eh ; 'N'; int
0x180068719  lea     rcx, aOnecoreuapShel_37; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x180068720  mov     [rsp+68h+pwszBaseUri], rcx; char *
0x180068725  lea     r9, aAppreadinessTa_35; "AppReadiness::Tasks::Store::StoreMetada"...
0x18006872c  lea     r8, aCreatexmlreade_2; "CreateXmlReaderInputWithEncodingName(re"...
0x180068733  mov     edx, eax; int
0x180068735  lea     rcx, [rbp+pExceptionObject]; this
0x180068739  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18006873e  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180068745  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180068749  call    _CxxThrowException_0
0x18006874f  mov     rcx, [rbp+ppvObject]
0x180068753  mov     rax, [rcx]
0x180068756  mov     rdx, [rbp+arg_10]
0x18006875a  mov     rax, [rax+18h]
0x18006875e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068763  test    eax, eax
0x180068765  jns     short loc_1800687A5
0x180068767  mov     dword ptr [rsp+68h+ppInput], 4Fh ; 'O'; int
0x18006876f  lea     rcx, aOnecoreuapShel_37; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x180068776  mov     [rsp+68h+pwszBaseUri], rcx; char *
0x18006877b  lea     r9, aAppreadinessTa_35; "AppReadiness::Tasks::Store::StoreMetada"...
0x180068782  lea     r8, aReaderSetinput; "reader->SetInput(readerInput.Get())"
0x180068789  mov     edx, eax; int
0x18006878b  lea     rcx, [rbp+pExceptionObject]; this
0x18006878f  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180068794  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18006879b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18006879f  call    _CxxThrowException_0
0x1800687a5  mov     [rbp+arg_0], 0
0x1800687ac  mov     rcx, [rbp+ppvObject]
0x1800687b0  mov     rax, [rcx]
0x1800687b3  lea     rdx, [rbp+arg_0]
0x1800687b7  mov     rax, [rax+30h]
0x1800687bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800687c0  test    eax, eax
0x1800687c2  jnz     loc_1800688A3
0x1800687c8  mov     [rbp+lpString2], 0
0x1800687d0  cmp     [rbp+arg_0], 1
0x1800687d4  jnz     short loc_1800687AC
0x1800687d6  mov     rcx, [rbp+ppvObject]
0x1800687da  mov     rax, [rcx]
0x1800687dd  xor     r8d, r8d
0x1800687e0  lea     rdx, [rbp+lpString2]
0x1800687e4  mov     rax, [rax+70h]
0x1800687e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800687ed  test    eax, eax
0x1800687ef  js      short loc_180068865
0x1800687f1  mov     dword ptr [rsp+68h+pwszBaseUri], 1; bIgnoreCase
0x1800687f9  or      r9d, 0FFFFFFFFh; cchCount2
0x1800687fd  mov     r8, [rbp+lpString2]; lpString2
0x180068801  or      edx, r9d; cchCount1
0x180068804  lea     rcx, aPtl_0; "Ptl"
0x18006880b  call    cs:__imp_CompareStringOrdinal
0x180068811  cmp     eax, 2
0x180068814  jnz     short loc_180068824
0x180068816  mov     rdx, [rbp+ppvObject]; struct IXmlReader *
0x18006881a  mov     rcx, rbx; this
0x18006881d  call    ?ReadPtl@StoreMetadata@Store@Tasks@AppReadiness@@AEAAXPEAUIXmlReader@@@Z; AppReadiness::Tasks::Store::StoreMetadata::ReadPtl(IXmlReader *)
0x180068822  jmp     short loc_1800687AC
0x180068824  mov     dword ptr [rsp+68h+ppInput], 60h ; '`'; int
0x18006882c  lea     rcx, aOnecoreuapShel_37; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x180068833  mov     [rsp+68h+pwszBaseUri], rcx; char *
0x180068838  lea     r9, aAppreadinessTa_35; "AppReadiness::Tasks::Store::StoreMetada"...
0x18006883f  lea     r8, aWcERootelement; "WC_E_ROOTELEMENT"
0x180068846  mov     edx, 0C00CEE3Ah; int
0x18006884b  lea     rcx, [rbp+pExceptionObject]; this
0x18006884f  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180068854  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18006885b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18006885f  call    _CxxThrowException_0
0x180068865  mov     dword ptr [rsp+68h+ppInput], 58h ; 'X'; int
0x18006886d  lea     rcx, aOnecoreuapShel_37; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x180068874  mov     [rsp+68h+pwszBaseUri], rcx; char *
0x180068879  lea     r9, aAppreadinessTa_35; "AppReadiness::Tasks::Store::StoreMetada"...
0x180068880  lea     r8, aReaderGetlocal; "reader->GetLocalName(&localName, nullpt"...
0x180068887  mov     edx, eax; int
0x180068889  lea     rcx, [rbp+pExceptionObject]; this
0x18006888d  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180068892  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180068899  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18006889d  call    _CxxThrowException_0
0x1800688a3  lea     rcx, [rbp+arg_10]
0x1800688a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800688ac  nop
0x1800688ad  lea     rcx, [rbp+ppvObject]
0x1800688b1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800688b6  add     rsp, 68h
0x1800688ba  pop     rbx
0x1800688bb  pop     rbp
0x1800688bc  retn
```
