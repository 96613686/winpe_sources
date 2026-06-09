# Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache::ExtractIconStream(Windows::Storage::IStorageFile *,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x18001db98`
- end: `0x18001dd44`
- name: `?ExtractIconStream@AccountsControlIconCache@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUIStorageFile@Storage@5@PEAPEAUIRandomAccessStream@Streams@75@@Z`
- size: `428`
- prototype: `int(Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache *__hidden this, struct Windows::Storage::IStorageFile *, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e2b0`

## callees

- `0x180006eac`
- `0x180011ffc`
- `0x18001db98`
- `0x18001ebfc`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dc6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dcac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dd0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dc6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dcac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dd0d`

## string_xrefs

- `0x18001dbe7`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontroliconcache.cpp`
- `0x18001dc37`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontroliconcache.cpp`
- `0x18001dc9b`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontroliconcache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache::ExtractIconStream(
        Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache *this,
        struct Windows::Storage::IStorageFile *a2,
        struct Windows::Storage::Streams::IRandomAccessStream **a3)
{
  Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache *v6; // rcx
  int StreamFromStorageFile; // eax
  unsigned int v8; // ebx
  __int64 (__fastcall *v9)(struct Windows::Storage::IStorageFile *, GUID *, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  __int64 v14; // rdx
  int v16; // [rsp+20h] [rbp-20h]
  __int64 v17; // [rsp+30h] [rbp-10h] BYREF
  struct Windows::Storage::Streams::IRandomAccessStream *v18; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  char v20; // [rsp+70h] [rbp+30h] BYREF
  HSTRING string; // [rsp+78h] [rbp+38h] BYREF

  *a3 = 0;
  v18 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  StreamFromStorageFile = Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache::GetStreamFromStorageFile(
                            v6,
                            a2,
                            &v18);
  v8 = StreamFromStorageFile;
  if ( StreamFromStorageFile >= 0 )
  {
    v17 = 0;
    v9 = **(__int64 (__fastcall ***)(struct Windows::Storage::IStorageFile *, GUID *, __int64 *))a2;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
    v10 = v9(a2, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v17);
    v8 = v10;
    if ( v10 >= 0 )
    {
      string = 0;
      v11 = v17;
      v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 96LL);
      WindowsDeleteString(0);
      string = 0;
      v13 = v12(v11, &string);
      v8 = v13;
      if ( v13 >= 0 )
      {
        v20 = 0;
        v13 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Storage::Streams::IRandomAccessStream *, char *))(**((_QWORD **)this + 8) + 80LL))(
                *((_QWORD *)this + 8),
                string,
                v18,
                &v20);
        v8 = v13;
        if ( v13 >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *, struct Windows::Storage::Streams::IRandomAccessStream **))(*(_QWORD *)v18 + 96LL))(
                  v18,
                  a3);
          v8 = v13;
          if ( v13 >= 0 )
          {
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
            v8 = 0;
            goto LABEL_14;
          }
          v14 = 132;
        }
        else
        {
          v14 = 130;
        }
      }
      else
      {
        v14 = 127;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontroliconcache.cpp",
        (const char *)(unsigned int)v13,
        v16);
      WindowsDeleteString(string);
      string = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontroliconcache.cpp",
        (const char *)(unsigned int)v10,
        v16);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontroliconcache.cpp",
      (const char *)(unsigned int)StreamFromStorageFile,
      v16);
  }
LABEL_14:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  return v8;
}

```

## disassembly

```asm
0x18001db98  mov     [rsp-18h+arg_0], rbx
0x18001db9d  mov     [rsp-18h+arg_8], rsi
0x18001dba2  push    rbp
0x18001dba3  push    rdi
0x18001dba4  push    r14
0x18001dba6  mov     rbp, rsp
0x18001dba9  sub     rsp, 40h
0x18001dbad  mov     rsi, r8
0x18001dbb0  mov     rdi, rdx
0x18001dbb3  mov     r14, rcx
0x18001dbb6  mov     qword ptr [r8], 0
0x18001dbbd  mov     [rbp+var_8], 0
0x18001dbc5  lea     rcx, [rbp+var_8]
0x18001dbc9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001dbce  lea     r8, [rbp+var_8]; struct Windows::Storage::Streams::IRandomAccessStream **
0x18001dbd2  mov     rdx, rdi; struct Windows::Storage::IStorageFile *
0x18001dbd5  call    ?GetStreamFromStorageFile@AccountsControlIconCache@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUIStorageFile@Storage@5@PEAPEAUIRandomAccessStream@Streams@75@@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache::GetStreamFromStorageFile(Windows::Storage::IStorageFile *,Windows::Storage::Streams::IRandomAccessStream * *)
0x18001dbda  mov     ebx, eax
0x18001dbdc  test    eax, eax
0x18001dbde  jns     short loc_18001DBFD
0x18001dbe0  mov     rcx, [rbp+18h]; this
0x18001dbe4  mov     r9d, eax; char *
0x18001dbe7  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001dbee  mov     edx, 79h ; 'y'; void *
0x18001dbf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dbf8  jmp     loc_18001DD26
0x18001dbfd  mov     [rbp+var_10], 0
0x18001dc05  mov     rax, [rdi]
0x18001dc08  mov     rbx, [rax]
0x18001dc0b  lea     rcx, [rbp+var_10]
0x18001dc0f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001dc14  lea     r8, [rbp+var_10]
0x18001dc18  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x18001dc1f  mov     rcx, rdi
0x18001dc22  mov     rax, rbx
0x18001dc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc2a  mov     ebx, eax
0x18001dc2c  test    eax, eax
0x18001dc2e  jns     short loc_18001DC57
0x18001dc30  mov     rcx, [rbp+18h]; this
0x18001dc34  mov     r9d, eax; char *
0x18001dc37  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001dc3e  mov     edx, 7Ch ; '|'; void *
0x18001dc43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dc48  nop
0x18001dc49  lea     rcx, [rbp+var_10]
0x18001dc4d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001dc52  jmp     loc_18001DD26
0x18001dc57  mov     [rbp+string], 0
0x18001dc5f  mov     rdi, [rbp+var_10]
0x18001dc63  mov     rax, [rdi]
0x18001dc66  mov     rbx, [rax+60h]
0x18001dc6a  xor     ecx, ecx; string
0x18001dc6c  call    cs:__imp_WindowsDeleteString
0x18001dc72  mov     [rbp+string], 0
0x18001dc7a  lea     rdx, [rbp+string]
0x18001dc7e  mov     rcx, rdi
0x18001dc81  mov     rax, rbx
0x18001dc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc89  mov     ebx, eax
0x18001dc8b  test    eax, eax
0x18001dc8d  jns     short loc_18001DCBC
0x18001dc8f  mov     edx, 7Fh; void *
0x18001dc94  mov     rcx, [rbp+18h]; this
0x18001dc98  mov     r9d, eax; char *
0x18001dc9b  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001dca2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dca7  nop
0x18001dca8  mov     rcx, [rbp+string]; string
0x18001dcac  call    cs:__imp_WindowsDeleteString
0x18001dcb2  mov     [rbp+string], 0
0x18001dcba  jmp     short loc_18001DC49
0x18001dcbc  mov     [rbp+arg_10], 0
0x18001dcc0  mov     rcx, [r14+40h]
0x18001dcc4  mov     rax, [rcx]
0x18001dcc7  lea     r9, [rbp+arg_10]
0x18001dccb  mov     r8, [rbp+var_8]
0x18001dccf  mov     rdx, [rbp+string]
0x18001dcd3  mov     rax, [rax+50h]
0x18001dcd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcdc  mov     ebx, eax
0x18001dcde  test    eax, eax
0x18001dce0  jns     short loc_18001DCE9
0x18001dce2  mov     edx, 82h
0x18001dce7  jmp     short loc_18001DC94
0x18001dce9  mov     rcx, [rbp+var_8]
0x18001dced  mov     rax, [rcx]
0x18001dcf0  mov     rdx, rsi
0x18001dcf3  mov     rax, [rax+60h]
0x18001dcf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcfc  mov     ebx, eax
0x18001dcfe  test    eax, eax
0x18001dd00  jns     short loc_18001DD09
0x18001dd02  mov     edx, 84h
0x18001dd07  jmp     short loc_18001DC94
0x18001dd09  mov     rcx, [rbp+string]; string
0x18001dd0d  call    cs:__imp_WindowsDeleteString
0x18001dd13  mov     [rbp+string], 0
0x18001dd1b  lea     rcx, [rbp+var_10]
0x18001dd1f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001dd24  xor     ebx, ebx
0x18001dd26  lea     rcx, [rbp+var_8]
0x18001dd2a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001dd2f  mov     eax, ebx
0x18001dd31  mov     rbx, [rsp+40h+arg_0]
0x18001dd36  mov     rsi, [rsp+40h+arg_8]
0x18001dd3b  add     rsp, 40h
0x18001dd3f  pop     r14
0x18001dd41  pop     rdi
0x18001dd42  pop     rbp
0x18001dd43  retn
```
