# Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::GetXmlReader(HSTRING__ *,IXmlReader * *)

- ea: `0x180061f74`
- end: `0x1800620e0`
- name: `?GetXmlReader@KnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@AEAAJPEAUHSTRING__@@PEAPEAUIXmlReader@@@Z`
- size: `364`
- prototype: `int(Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile *__hidden this, HSTRING, struct IXmlReader **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800633d8`

## callees

- `0x180006eac`
- `0x180011ffc`
- `0x180061f74`
- `0x18006c010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x18006201c`
- `XmlLite!CreateXmlReader` at `0x18006201c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061fae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061fae`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180061fd4`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180061fd4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::GetXmlReader(
        Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile *this,
        HSTRING a2,
        struct IXmlReader **a3)
{
  const WCHAR *StringRawBuffer; // rax
  HRESULT v6; // eax
  unsigned int v7; // ebx
  HRESULT v8; // eax
  __int64 v9; // rdx
  int pstmTemplate; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  void *ppvObject; // [rsp+40h] [rbp+10h] BYREF
  IStream *ppstm; // [rsp+50h] [rbp+20h] BYREF

  ppvObject = this;
  *a3 = 0;
  ppstm = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v6 = SHCreateStreamOnFileEx(StringRawBuffer, 0, 0x80u, 0, 0, &ppstm);
  v7 = v6;
  if ( v6 >= 0 )
  {
    ppvObject = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvObject);
    v8 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
      v7 = v8;
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppstm);
        v7 = v8;
        if ( v8 >= 0 )
        {
          v8 = (**(__int64 (__fastcall ***)(void *, GUID *, struct IXmlReader **))ppvObject)(
                 ppvObject,
                 &GUID_7279fc81_709d_4095_b63d_69fe4b0d9030,
                 a3);
          v7 = v8;
          if ( v8 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvObject);
            v7 = 0;
            goto LABEL_13;
          }
          v9 = 271;
        }
        else
        {
          v9 = 269;
        }
      }
      else
      {
        v9 = 268;
      }
    }
    else
    {
      v9 = 267;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\knownaccounttypesfile.cpp",
      (const char *)(unsigned int)v8,
      pstmTemplate);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvObject);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x108,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\knownaccounttypesfile.cpp",
      (const char *)(unsigned int)v6,
      pstmTemplate);
  }
LABEL_13:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
  return v7;
}

```

## disassembly

```asm
0x180061f74  mov     [rsp-8+arg_8], rbx
0x180061f79  mov     [rsp-8+arg_18], rdi
0x180061f7e  mov     [rsp-8+ppvObject], rcx
0x180061f83  push    rbp
0x180061f84  mov     rbp, rsp
0x180061f87  sub     rsp, 30h
0x180061f8b  mov     rdi, r8
0x180061f8e  mov     rbx, rdx
0x180061f91  mov     qword ptr [r8], 0
0x180061f98  mov     [rbp+arg_10], 0
0x180061fa0  lea     rcx, [rbp+arg_10]
0x180061fa4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180061fa9  xor     edx, edx; length
0x180061fab  mov     rcx, rbx; string
0x180061fae  call    cs:__imp_WindowsGetStringRawBuffer
0x180061fb4  lea     rcx, [rbp+arg_10]
0x180061fb8  mov     [rsp+30h+ppstm], rcx; ppstm
0x180061fbd  mov     [rsp+30h+pstmTemplate], 0; int
0x180061fc6  xor     r9d, r9d; fCreate
0x180061fc9  xor     edx, edx; grfMode
0x180061fcb  mov     r8d, 80h; dwAttributes
0x180061fd1  mov     rcx, rax; pszFile
0x180061fd4  call    cs:__imp_SHCreateStreamOnFileEx
0x180061fda  mov     ebx, eax
0x180061fdc  test    eax, eax
0x180061fde  jns     short loc_180061FFD
0x180061fe0  mov     rcx, [rbp+8]; this
0x180061fe4  mov     r9d, eax; char *
0x180061fe7  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\accountscontrol\\api"...
0x180061fee  mov     edx, 108h; void *
0x180061ff3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061ff8  jmp     loc_1800620C5
0x180061ffd  mov     [rbp+ppvObject], 0
0x180062005  lea     rcx, [rbp+ppvObject]
0x180062009  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006200e  xor     r8d, r8d; pMalloc
0x180062011  lea     rdx, [rbp+ppvObject]; ppvObject
0x180062015  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18006201c  call    cs:__imp_CreateXmlReader
0x180062022  mov     ebx, eax
0x180062024  test    eax, eax
0x180062026  jns     short loc_18006204C
0x180062028  mov     edx, 10Bh; void *
0x18006202d  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\accountscontrol\\api"...
0x180062034  mov     r9d, eax; char *
0x180062037  mov     rcx, [rbp+8]; this
0x18006203b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062040  nop
0x180062041  lea     rcx, [rbp+ppvObject]
0x180062045  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006204a  jmp     short loc_1800620C5
0x18006204c  mov     rcx, [rbp+ppvObject]
0x180062050  mov     rax, [rcx]
0x180062053  xor     r8d, r8d
0x180062056  lea     edx, [r8+4]
0x18006205a  mov     rax, [rax+28h]
0x18006205e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062063  mov     ebx, eax
0x180062065  test    eax, eax
0x180062067  jns     short loc_180062070
0x180062069  mov     edx, 10Ch
0x18006206e  jmp     short loc_18006202D
0x180062070  mov     rcx, [rbp+ppvObject]
0x180062074  mov     rax, [rcx]
0x180062077  mov     rdx, [rbp+arg_10]
0x18006207b  mov     rax, [rax+18h]
0x18006207f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062084  mov     ebx, eax
0x180062086  test    eax, eax
0x180062088  jns     short loc_180062091
0x18006208a  mov     edx, 10Dh
0x18006208f  jmp     short loc_18006202D
0x180062091  mov     rcx, [rbp+ppvObject]
0x180062095  mov     rax, [rcx]
0x180062098  mov     r8, rdi
0x18006209b  lea     rdx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030
0x1800620a2  mov     rax, [rax]
0x1800620a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620aa  mov     ebx, eax
0x1800620ac  test    eax, eax
0x1800620ae  jns     short loc_1800620BA
0x1800620b0  mov     edx, 10Fh
0x1800620b5  jmp     loc_18006202D
0x1800620ba  lea     rcx, [rbp+ppvObject]
0x1800620be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800620c3  xor     ebx, ebx
0x1800620c5  lea     rcx, [rbp+arg_10]
0x1800620c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800620ce  mov     eax, ebx
0x1800620d0  mov     rbx, [rsp+30h+arg_8]
0x1800620d5  mov     rdi, [rsp+30h+arg_18]
0x1800620da  add     rsp, 30h
0x1800620de  pop     rbp
0x1800620df  retn
```
