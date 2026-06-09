# SystemSettings::WorkplaceHandlers::CorpDeviceEmailDialog::SetProperty(HSTRING__ *,IInspectable *)

- ea: `0x1801ad740`
- end: `0x1801ad9f0`
- name: `?SetProperty@CorpDeviceEmailDialog@WorkplaceHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `688`
- prototype: `int(SystemSettings::WorkplaceHandlers::CorpDeviceEmailDialog *__hidden this, HSTRING, struct IInspectable *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180011bb0`
- `0x180021398`
- `0x18006617c`
- `0x1801ad740`
- `0x1801ade48`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ad7b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ad83d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ad8b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ad92a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ad97a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ad7b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ad83d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ad8b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ad92a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ad97a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ad7eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ad868`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ad8e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ad955`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ad7eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ad868`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ad8e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ad955`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::WorkplaceHandlers::CorpDeviceEmailDialog::SetProperty(
        SystemSettings::WorkplaceHandlers::CorpDeviceEmailDialog *this,
        SystemSettings::DataModel *a2,
        struct IInspectable *a3)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v7; // edi
  const unsigned __int16 *v8; // r8
  const unsigned __int16 *v9; // r8
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  const unsigned __int16 *v13; // r8
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  PCWSTR v16; // rax
  const unsigned __int16 *v17; // r8
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  PCWSTR v20; // rax
  const unsigned __int16 *v21; // r8
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING *); // rbx
  PCWSTR v24; // rax
  __int64 v26; // [rsp+60h] [rbp+40h] BYREF
  HSTRING string; // [rsp+68h] [rbp+48h] BYREF

  v26 = 0;
  QueryInterface = a3->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  v7 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
         a3,
         &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
         &v26);
  if ( v7 >= 0 )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031CAA8, v8) )
    {
      string = 0;
      v10 = v26;
      v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 152LL);
      WindowsDeleteString(0);
      string = 0;
      v7 = v11(v10, &string);
      if ( v7 >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
               (char *)this + 264,
               StringRawBuffer,
               -1);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::TrimWhitespace((char *)this + 264);
      }
LABEL_17:
      WindowsDeleteString(string);
      goto LABEL_20;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031CAF0, v9) )
    {
      string = 0;
      v14 = v26;
      v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 152LL);
      WindowsDeleteString(0);
      string = 0;
      v7 = v15(v14, &string);
      if ( v7 >= 0 )
      {
        v16 = WindowsGetStringRawBuffer(string, 0);
        v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
               (char *)this + 288,
               v16,
               -1);
      }
      goto LABEL_17;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031CB40, v13) )
    {
      string = 0;
      v18 = v26;
      v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 152LL);
      WindowsDeleteString(0);
      string = 0;
      v7 = v19(v18, &string);
      if ( v7 >= 0 )
      {
        v20 = WindowsGetStringRawBuffer(string, 0);
        v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
               (char *)this + 352,
               v20,
               -1);
      }
      goto LABEL_17;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031CD40, v17) )
    {
      string = 0;
      v22 = v26;
      v23 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 152LL);
      WindowsDeleteString(0);
      string = 0;
      v7 = v23(v22, &string);
      if ( v7 >= 0 )
      {
        v24 = WindowsGetStringRawBuffer(string, 0);
        v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
               (char *)this + 376,
               v24,
               -1);
      }
      goto LABEL_17;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802EDE08, v21) )
    {
      *(_WORD *)((char *)this + 331) = 256;
      *((_DWORD *)this + 78) = 16842752;
      *(_WORD *)((char *)this + 317) = 0;
      *((_BYTE *)this + 316) = 0;
      *((_QWORD *)this + 40) = 0;
      *((_WORD *)this + 164) = 0;
      *((_BYTE *)this + 330) = 0;
    }
  }
LABEL_20:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801ad740  mov     [rsp-28h+arg_0], rbx
0x1801ad745  push    rbp
0x1801ad746  push    rsi
0x1801ad747  push    rdi
0x1801ad748  push    r14
0x1801ad74a  push    r15
0x1801ad74c  mov     rbp, rsp
0x1801ad74f  sub     rsp, 20h
0x1801ad753  mov     rdi, r8
0x1801ad756  mov     r14, rdx
0x1801ad759  mov     rsi, rcx
0x1801ad75c  xor     r15d, r15d
0x1801ad75f  mov     [rbp+arg_10], r15
0x1801ad763  mov     rax, [r8]
0x1801ad766  mov     rbx, [rax]
0x1801ad769  lea     rcx, [rbp+arg_10]
0x1801ad76d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ad772  lea     r8, [rbp+arg_10]
0x1801ad776  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1801ad77d  mov     rcx, rdi
0x1801ad780  mov     rax, rbx
0x1801ad783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad788  mov     edi, eax
0x1801ad78a  test    eax, eax
0x1801ad78c  js      loc_1801AD9D3
0x1801ad792  lea     rdx, stru_18031CAA8; HSTRING
0x1801ad799  mov     rcx, r14; this
0x1801ad79c  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801ad7a1  test    al, al
0x1801ad7a3  jz      short loc_1801AD816
0x1801ad7a5  mov     [rbp+string], r15
0x1801ad7a9  mov     rdi, [rbp+arg_10]
0x1801ad7ad  mov     rax, [rdi]
0x1801ad7b0  mov     rbx, [rax+98h]
0x1801ad7b7  xor     ecx, ecx; string
0x1801ad7b9  call    cs:__imp_WindowsDeleteString
0x1801ad7c0  nop     dword ptr [rax+rax+00h]
0x1801ad7c5  mov     [rbp+string], r15
0x1801ad7c9  lea     rdx, [rbp+string]
0x1801ad7cd  mov     rcx, rdi
0x1801ad7d0  mov     rax, rbx
0x1801ad7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad7d8  mov     edi, eax
0x1801ad7da  test    eax, eax
0x1801ad7dc  js      short loc_1801AD811
0x1801ad7de  lea     rbx, [rsi+108h]
0x1801ad7e5  xor     edx, edx; length
0x1801ad7e7  mov     rcx, [rbp+string]; string
0x1801ad7eb  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ad7f2  nop     dword ptr [rax+rax+00h]
0x1801ad7f7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801ad7fb  mov     rdx, rax
0x1801ad7fe  mov     rcx, rbx
0x1801ad801  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1801ad806  mov     edi, eax
0x1801ad808  mov     rcx, rbx
0x1801ad80b  call    ?TrimWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::TrimWhitespace(void)
0x1801ad810  nop
0x1801ad811  jmp     loc_1801AD976
0x1801ad816  lea     rdx, stru_18031CAF0; HSTRING
0x1801ad81d  mov     rcx, r14; this
0x1801ad820  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801ad825  test    al, al
0x1801ad827  jz      short loc_1801AD88E
0x1801ad829  mov     [rbp+string], r15
0x1801ad82d  mov     rdi, [rbp+arg_10]
0x1801ad831  mov     rax, [rdi]
0x1801ad834  mov     rbx, [rax+98h]
0x1801ad83b  xor     ecx, ecx; string
0x1801ad83d  call    cs:__imp_WindowsDeleteString
0x1801ad844  nop     dword ptr [rax+rax+00h]
0x1801ad849  mov     [rbp+string], r15
0x1801ad84d  lea     rdx, [rbp+string]
0x1801ad851  mov     rcx, rdi
0x1801ad854  mov     rax, rbx
0x1801ad857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad85c  mov     edi, eax
0x1801ad85e  test    eax, eax
0x1801ad860  js      short loc_1801AD889
0x1801ad862  xor     edx, edx; length
0x1801ad864  mov     rcx, [rbp+string]; string
0x1801ad868  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ad86f  nop     dword ptr [rax+rax+00h]
0x1801ad874  lea     rcx, [rsi+120h]
0x1801ad87b  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801ad87f  mov     rdx, rax
0x1801ad882  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1801ad887  mov     edi, eax
0x1801ad889  jmp     loc_1801AD976
0x1801ad88e  lea     rdx, stru_18031CB40; HSTRING
0x1801ad895  mov     rcx, r14; this
0x1801ad898  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801ad89d  test    al, al
0x1801ad89f  jz      short loc_1801AD903
0x1801ad8a1  mov     [rbp+string], r15
0x1801ad8a5  mov     rdi, [rbp+arg_10]
0x1801ad8a9  mov     rax, [rdi]
0x1801ad8ac  mov     rbx, [rax+98h]
0x1801ad8b3  xor     ecx, ecx; string
0x1801ad8b5  call    cs:__imp_WindowsDeleteString
0x1801ad8bc  nop     dword ptr [rax+rax+00h]
0x1801ad8c1  mov     [rbp+string], r15
0x1801ad8c5  lea     rdx, [rbp+string]
0x1801ad8c9  mov     rcx, rdi
0x1801ad8cc  mov     rax, rbx
0x1801ad8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad8d4  mov     edi, eax
0x1801ad8d6  test    eax, eax
0x1801ad8d8  js      short loc_1801AD901
0x1801ad8da  xor     edx, edx; length
0x1801ad8dc  mov     rcx, [rbp+string]; string
0x1801ad8e0  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ad8e7  nop     dword ptr [rax+rax+00h]
0x1801ad8ec  lea     rcx, [rsi+160h]
0x1801ad8f3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801ad8f7  mov     rdx, rax
0x1801ad8fa  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1801ad8ff  mov     edi, eax
0x1801ad901  jmp     short loc_1801AD976
0x1801ad903  lea     rdx, stru_18031CD40; HSTRING
0x1801ad90a  mov     rcx, r14; this
0x1801ad90d  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801ad912  test    al, al
0x1801ad914  jz      short loc_1801AD988
0x1801ad916  mov     [rbp+string], r15
0x1801ad91a  mov     rdi, [rbp+arg_10]
0x1801ad91e  mov     rax, [rdi]
0x1801ad921  mov     rbx, [rax+98h]
0x1801ad928  xor     ecx, ecx; string
0x1801ad92a  call    cs:__imp_WindowsDeleteString
0x1801ad931  nop     dword ptr [rax+rax+00h]
0x1801ad936  mov     [rbp+string], r15
0x1801ad93a  lea     rdx, [rbp+string]
0x1801ad93e  mov     rcx, rdi
0x1801ad941  mov     rax, rbx
0x1801ad944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad949  mov     edi, eax
0x1801ad94b  test    eax, eax
0x1801ad94d  js      short loc_1801AD976
0x1801ad94f  xor     edx, edx; length
0x1801ad951  mov     rcx, [rbp+string]; string
0x1801ad955  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ad95c  nop     dword ptr [rax+rax+00h]
0x1801ad961  lea     rcx, [rsi+178h]
0x1801ad968  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801ad96c  mov     rdx, rax
0x1801ad96f  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1801ad974  mov     edi, eax
0x1801ad976  mov     rcx, [rbp+string]; string
0x1801ad97a  call    cs:__imp_WindowsDeleteString
0x1801ad981  nop     dword ptr [rax+rax+00h]
0x1801ad986  jmp     short loc_1801AD9D3
0x1801ad988  lea     rdx, stru_1802EDE08; HSTRING
0x1801ad98f  mov     rcx, r14; this
0x1801ad992  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801ad997  test    al, al
0x1801ad999  jz      short loc_1801AD9D3
0x1801ad99b  mov     word ptr [rsi+14Bh], 100h
0x1801ad9a4  mov     dword ptr [rsi+138h], 1010000h
0x1801ad9ae  mov     [rsi+13Dh], r15w
0x1801ad9b6  mov     [rsi+13Ch], r15b
0x1801ad9bd  mov     [rsi+140h], r15
0x1801ad9c4  mov     [rsi+148h], r15w
0x1801ad9cc  mov     [rsi+14Ah], r15b
0x1801ad9d3  lea     rcx, [rbp+arg_10]
0x1801ad9d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ad9dc  mov     eax, edi
0x1801ad9de  mov     rbx, [rsp+20h+arg_0]
0x1801ad9e3  add     rsp, 20h
0x1801ad9e7  pop     r15
0x1801ad9e9  pop     r14
0x1801ad9eb  pop     rdi
0x1801ad9ec  pop     rsi
0x1801ad9ed  pop     rbp
0x1801ad9ee  retn
```
