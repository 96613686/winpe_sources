# Windows::UI::Input::Inking::CInkStrokeContainer::WriteDataToStream(tagVARIANT *,Windows::Storage::Streams::IOutputStream *,Windows::Foundation::IAsyncOperationWithProgress<uint,uint> * *)

- ea: `0x180036d60`
- end: `0x180036ea8`
- name: `?WriteDataToStream@CInkStrokeContainer@Inking@Input@UI@Windows@@EEAAJPEAUtagVARIANT@@PEAUIOutputStream@Streams@Storage@5@PEAPEAU?$IAsyncOperationWithProgress@II@Foundation@5@@Z`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800101bc`
- `0x18001ff0c`
- `0x180026c40`
- `0x180036d60`
- `0x1800f85e8`
- `0x1800fb010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180036e8d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180036e8d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180036db1`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180036db1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180036d8e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180036d8e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180036e84`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180036e84`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::CInkStrokeContainer::WriteDataToStream(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  SAFEARRAY *v4; // rdi
  HRESULT v7; // ebx
  HRESULT UBound; // eax
  struct Windows::Storage::Streams::IBuffer **v9; // r8
  unsigned int v11[2]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v12; // [rsp+28h] [rbp-18h] BYREF
  void *ppvData; // [rsp+30h] [rbp-10h] BYREF
  void *v14; // [rsp+38h] [rbp-8h] BYREF
  LONG plUbound; // [rsp+68h] [rbp+28h] BYREF

  v4 = *(SAFEARRAY **)(a2 + 8);
  ppvData = 0;
  v7 = SafeArrayAccessData(v4, &ppvData);
  if ( v7 >= 0 )
  {
    plUbound = 0;
    UBound = SafeArrayGetUBound(v4, 1u, &plUbound);
    ++plUbound;
    v7 = UBound;
    if ( UBound >= 0 )
    {
      *(_QWORD *)v11 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v11);
      if ( (int)Windows::Storage::Streams::CBuffer_Allocate(
                  (Windows::Storage::Streams *)(unsigned int)plUbound,
                  (unsigned int)v11,
                  v9) < 0 )
      {
        v7 = -2147024882;
      }
      else
      {
        v12 = 0;
        v7 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(
               v11,
               &v12);
        if ( v7 >= 0 )
        {
          v14 = 0;
          v7 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v12 + 24LL))(v12, &v14);
          if ( v7 >= 0 )
          {
            memcpy_0(v14, ppvData, plUbound);
            v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v11 + 64LL))(
                   *(_QWORD *)v11,
                   (unsigned int)plUbound);
            if ( v7 >= 0 )
              v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)a3 + 48LL))(a3, *(_QWORD *)v11, a4);
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v11);
    }
    SafeArrayUnaccessData(v4);
  }
  SafeArrayDestroy(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180036d60  mov     [rsp-18h+arg_0], rbx
0x180036d65  mov     [rsp-18h+arg_10], rsi
0x180036d6a  push    rbp
0x180036d6b  push    rdi
0x180036d6c  push    r14
0x180036d6e  mov     rbp, rsp
0x180036d71  sub     rsp, 40h
0x180036d75  mov     rdi, [rdx+8]
0x180036d79  mov     r14, r9
0x180036d7c  mov     rcx, rdi; psa
0x180036d7f  mov     [rbp+ppvData], 0
0x180036d87  lea     rdx, [rbp+ppvData]; ppvData
0x180036d8b  mov     rsi, r8
0x180036d8e  call    cs:__imp_SafeArrayAccessData
0x180036d94  mov     ebx, eax
0x180036d96  test    eax, eax
0x180036d98  js      loc_180036E8A
0x180036d9e  lea     r8, [rbp+plUbound]; plUbound
0x180036da2  mov     [rbp+plUbound], 0
0x180036da9  mov     edx, 1; nDim
0x180036dae  mov     rcx, rdi; psa
0x180036db1  call    cs:__imp_SafeArrayGetUBound
0x180036db7  inc     [rbp+plUbound]
0x180036dba  mov     ebx, eax
0x180036dbc  test    eax, eax
0x180036dbe  js      loc_180036E81
0x180036dc4  lea     rcx, [rbp+var_20]
0x180036dc8  mov     qword ptr [rbp+var_20], 0
0x180036dd0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180036dd5  mov     ecx, [rbp+plUbound]; this
0x180036dd8  lea     rdx, [rbp+var_20]; unsigned int
0x180036ddc  call    ?CBuffer_Allocate@Streams@Storage@Windows@@YAJIPEAPEAUIBuffer@123@@Z; Windows::Storage::Streams::CBuffer_Allocate(uint,Windows::Storage::Streams::IBuffer * *)
0x180036de1  test    eax, eax
0x180036de3  js      loc_180036E73
0x180036de9  lea     rdx, [rbp+var_18]
0x180036ded  mov     [rbp+var_18], 0
0x180036df5  lea     rcx, [rbp+var_20]
0x180036df9  call    ??$As@UIBufferByteAccess@Streams@Storage@Windows@@@?$ComPtr@UIBuffer@Streams@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIBufferByteAccess@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBufferByteAccess>>)
0x180036dfe  mov     ebx, eax
0x180036e00  test    eax, eax
0x180036e02  js      short loc_180036E68
0x180036e04  mov     rcx, [rbp+var_18]
0x180036e08  lea     rdx, [rbp+var_8]
0x180036e0c  mov     [rbp+var_8], 0
0x180036e14  mov     rax, [rcx]
0x180036e17  mov     rax, [rax+18h]
0x180036e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e20  mov     ebx, eax
0x180036e22  test    eax, eax
0x180036e24  js      short loc_180036E68
0x180036e26  movsxd  r8, [rbp+plUbound]; Size
0x180036e2a  mov     rdx, [rbp+ppvData]; Src
0x180036e2e  mov     rcx, [rbp+var_8]; void *
0x180036e32  call    memcpy_0
0x180036e37  mov     rcx, qword ptr [rbp+var_20]
0x180036e3b  mov     edx, [rbp+plUbound]
0x180036e3e  mov     rax, [rcx]
0x180036e41  mov     rax, [rax+40h]
0x180036e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e4a  mov     ebx, eax
0x180036e4c  test    eax, eax
0x180036e4e  js      short loc_180036E68
0x180036e50  mov     rax, [rsi]
0x180036e53  mov     r8, r14
0x180036e56  mov     rdx, qword ptr [rbp+var_20]
0x180036e5a  mov     rcx, rsi
0x180036e5d  mov     rax, [rax+30h]
0x180036e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e66  mov     ebx, eax
0x180036e68  lea     rcx, [rbp+var_18]
0x180036e6c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180036e71  jmp     short loc_180036E78
0x180036e73  mov     ebx, 8007000Eh
0x180036e78  lea     rcx, [rbp+var_20]
0x180036e7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180036e81  mov     rcx, rdi; psa
0x180036e84  call    cs:__imp_SafeArrayUnaccessData
0x180036e8a  mov     rcx, rdi; psa
0x180036e8d  call    cs:__imp_SafeArrayDestroy
0x180036e93  mov     rsi, [rsp+40h+arg_10]
0x180036e98  mov     eax, ebx
0x180036e9a  mov     rbx, [rsp+40h+arg_0]
0x180036e9f  add     rsp, 40h
0x180036ea3  pop     r14
0x180036ea5  pop     rdi
0x180036ea6  pop     rbp
0x180036ea7  retn
```
