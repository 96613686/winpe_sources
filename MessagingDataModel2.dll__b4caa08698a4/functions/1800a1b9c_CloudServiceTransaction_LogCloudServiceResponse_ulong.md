# CloudServiceTransaction::_LogCloudServiceResponse(ulong)

- ea: `0x1800a1b9c`
- end: `0x1800a1f70`
- name: `?_LogCloudServiceResponse@CloudServiceTransaction@@AEAAJK@Z`
- size: `980`
- prototype: `__int64 __fastcall(CloudServiceTransaction *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a17e0`
- `0x1800a1b60`

## callees

- `0x180001b58`
- `0x180008870`
- `0x18000b7d4`
- `0x18000b7fc`
- `0x180030bd0`
- `0x18009d8a8`
- `0x1800a15d8`
- `0x1800a1b9c`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1e02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1e02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1c0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1c3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1d2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1d9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1e5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1f3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1c0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1c3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1d2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1d9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1e5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1f3c`

## string_xrefs

- `0x1800a1f04`: `[MessagingCloudServices] CloudServiceTransaction HTTP failure`
- `0x1800a1cb3`: `Removed for PII protection`
- `0x1800a1e9c`: `[MessagingCloudServices] CloudServiceTransaction HTTP success`
- `0x1800a1eda`: `[MessagingCloudServices] CloudServiceTransaction HTTP success`

## pseudocode

```c
__int64 __fastcall CloudServiceTransaction::_LogCloudServiceResponse(CloudServiceTransaction *this, int a2)
{
  __int64 v4; // rcx
  int v5; // eax
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  int v12; // ecx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  void (*v19)(void); // rax
  int v20; // eax
  int (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rcx
  void (*v22)(void); // rax
  __int64 v23; // rcx
  int (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // rdi
  int (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // rcx
  PCWSTR StringRawBuffer; // rax
  int (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v28; // rcx
  int v29; // esi
  int v30; // esi
  int v31; // esi
  char *v32; // rdx
  const char *v33; // rax
  int v35; // [rsp+40h] [rbp-49h] BYREF
  const char *v36; // [rsp+48h] [rbp-41h] BYREF
  const char *v37; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v38[8]; // [rsp+58h] [rbp-31h] BYREF
  HSTRING string; // [rsp+60h] [rbp-29h] BYREF
  HSTRING v40; // [rsp+68h] [rbp-21h] BYREF
  __int64 v41; // [rsp+70h] [rbp-19h] BYREF
  int (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-11h] BYREF
  _QWORD v43[2]; // [rsp+80h] [rbp-9h] BYREF
  __int16 v44; // [rsp+90h] [rbp+7h] BYREF
  __int64 v45; // [rsp+92h] [rbp+9h]
  int v46; // [rsp+9Ah] [rbp+11h]
  __int16 v47; // [rsp+9Eh] [rbp+15h]
  __int64 v48; // [rsp+A0h] [rbp+17h] BYREF

  v4 = *((_QWORD *)this + 1);
  v48 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 96LL))(v4, &v48);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = v48;
    string = 0;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v48 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v9 = v8(v7, &string);
    v6 = v9;
    if ( v9 < 0 )
    {
      Log_HREvent_77(v9);
LABEL_5:
      WindowsDeleteString(string);
LABEL_48:
      string = 0;
      goto LABEL_49;
    }
    v10 = *((_QWORD *)this + 2);
    v43[0] = &v44;
    v45 = 0;
    v43[1] = &v44;
    v46 = 0;
    v47 = 0;
    v44 = 0;
    v38[0] = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v10 + 72LL))(v10, v38);
    v6 = v11;
    if ( v11 < 0 )
    {
      v12 = v11;
LABEL_8:
      Log_HREvent_77(v12);
LABEL_9:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v43);
      goto LABEL_5;
    }
    if ( v38[0] )
    {
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               v43,
                               L"Removed for PII protection",
                               26) )
      {
        v6 = -2147024882;
        v12 = -2147024882;
        goto LABEL_8;
      }
LABEL_36:
      v29 = a2 - 1;
      if ( v29 && (v30 = v29 - 1) != 0 && (v31 = v30 - 1) != 0 )
      {
        if ( v31 != 1 )
        {
          if ( (unsigned int)dword_1800FD5F0 > 5 )
          {
            v36 = (const char *)v43[0];
            v35 = *((_DWORD *)this + 6);
            v37 = "[MessagingCloudServices] CloudServiceTransaction HTTP success";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              v13,
              (int)&byte_1800F2D5F,
              v14,
              v15,
              (const unsigned __int16 **)&v37,
              (__int64)&v35,
              (const OLECHAR **)&v36);
          }
          goto LABEL_47;
        }
        if ( (unsigned int)dword_1800FD5F0 > 4 )
        {
          v32 = &byte_1800F2CF7;
          v37 = (const char *)v43[0];
          v35 = *((_DWORD *)this + 6);
          v33 = "[MessagingCloudServices] CloudServiceTransaction HTTP success";
LABEL_46:
          v36 = v33;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            v13,
            (int)v32,
            v14,
            v15,
            (const unsigned __int16 **)&v36,
            (__int64)&v35,
            (const OLECHAR **)&v37);
        }
      }
      else if ( (unsigned int)dword_1800FD5F0 > 2 )
      {
        v32 = &byte_1800F2DC7;
        v37 = (const char *)v43[0];
        v35 = *((_DWORD *)this + 6);
        v33 = "[MessagingCloudServices] CloudServiceTransaction HTTP failure";
        goto LABEL_46;
      }
LABEL_47:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v43);
      WindowsDeleteString(string);
      v6 = 0;
      goto LABEL_48;
    }
    v16 = *((_QWORD *)this + 2);
    v40 = 0;
    v41 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 48LL))(v16, &v41);
    v6 = v17;
    if ( v17 < 0 )
    {
      Log_HREvent_77(v17);
      v18 = v41;
      if ( !v41 )
      {
LABEL_17:
        WindowsDeleteString(v40);
        v40 = 0;
        goto LABEL_9;
      }
      v41 = 0;
      v19 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
LABEL_16:
      v19();
      goto LABEL_17;
    }
    v42 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v41 + 80LL))(
            v41,
            &v42);
    v6 = v20;
    if ( v20 >= 0 )
    {
      WindowsDeleteString(v40);
      v24 = v42;
      v40 = 0;
      v6 = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(v42);
      if ( v6 >= 0 )
        v6 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING *))(*v24)[10])(v24, &v40);
      if ( v6 >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v40, 0);
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                v43,
                                StringRawBuffer) )
        {
          v27 = v42;
          if ( v42 )
          {
            v42 = 0;
            ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v27)[2])(v27);
          }
          v28 = v41;
          if ( v41 )
          {
            v41 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          }
          WindowsDeleteString(v40);
          goto LABEL_36;
        }
        v6 = -2147024882;
      }
      Log_HREvent_77(v6);
      v25 = v42;
      if ( !v42 )
        goto LABEL_22;
      v42 = 0;
      v22 = (void (*)(void))(*v25)[2];
    }
    else
    {
      Log_HREvent_77(v20);
      v21 = v42;
      if ( !v42 )
      {
LABEL_22:
        v23 = v41;
        if ( !v41 )
          goto LABEL_17;
        v41 = 0;
        v19 = *(void (**)(void))(*(_QWORD *)v23 + 16LL);
        goto LABEL_16;
      }
      v42 = 0;
      v22 = (void (*)(void))(*v21)[2];
    }
    v22();
    goto LABEL_22;
  }
  Log_HREvent_77(v5);
LABEL_49:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800a1b9c  push    rbp
0x1800a1b9e  push    rbx
0x1800a1b9f  push    rsi
0x1800a1ba0  push    rdi
0x1800a1ba1  push    r14
0x1800a1ba3  push    r15
0x1800a1ba5  lea     rbp, [rsp-2Fh]
0x1800a1baa  sub     rsp, 0B8h
0x1800a1bb1  mov     rax, cs:__security_cookie
0x1800a1bb8  xor     rax, rsp
0x1800a1bbb  mov     [rbp+57h+var_38], rax
0x1800a1bbf  mov     r14, rcx
0x1800a1bc2  mov     esi, edx
0x1800a1bc4  mov     rcx, [rcx+8]
0x1800a1bc8  lea     rdx, [rbp+57h+var_40]
0x1800a1bcc  xor     r15d, r15d
0x1800a1bcf  mov     [rbp+57h+var_40], r15
0x1800a1bd3  mov     rax, [rcx]
0x1800a1bd6  mov     rax, [rax+60h]
0x1800a1bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1bdf  mov     ebx, eax
0x1800a1be1  test    eax, eax
0x1800a1be3  jns     short loc_1800A1BF9
0x1800a1be5  lea     edx, [r15+1]
0x1800a1be9  mov     ecx, eax; int
0x1800a1beb  lea     r9d, [r15+7Fh]
0x1800a1bef  call    Log_HREvent_77
0x1800a1bf4  jmp     loc_1800A1F49
0x1800a1bf9  mov     rdi, [rbp+57h+var_40]
0x1800a1bfd  xor     ecx, ecx; string
0x1800a1bff  mov     [rbp+57h+string], r15
0x1800a1c03  mov     rax, [rdi]
0x1800a1c06  mov     rbx, [rax+30h]
0x1800a1c0a  call    cs:__imp_WindowsDeleteString
0x1800a1c10  lea     rdx, [rbp+57h+string]
0x1800a1c14  mov     [rbp+57h+string], r15
0x1800a1c18  mov     rcx, rdi
0x1800a1c1b  mov     rax, rbx
0x1800a1c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1c23  mov     ebx, eax
0x1800a1c25  test    eax, eax
0x1800a1c27  jns     short loc_1800A1C4A
0x1800a1c29  mov     edx, 1
0x1800a1c2e  mov     r9d, 81h
0x1800a1c34  mov     ecx, eax; int
0x1800a1c36  call    Log_HREvent_77
0x1800a1c3b  mov     rcx, [rbp+57h+string]; string
0x1800a1c3f  call    cs:__imp_WindowsDeleteString
0x1800a1c45  jmp     loc_1800A1F45
0x1800a1c4a  mov     rcx, [r14+10h]
0x1800a1c4e  lea     rax, [rbp+57h+var_50]
0x1800a1c52  mov     [rbp+57h+var_60], rax
0x1800a1c56  lea     rdx, [rbp+57h+var_88]
0x1800a1c5a  lea     rax, [rbp+57h+var_50]
0x1800a1c5e  mov     [rbp+57h+var_4E], r15
0x1800a1c62  mov     [rbp+57h+var_58], rax
0x1800a1c66  mov     [rbp+57h+var_46], r15d
0x1800a1c6a  mov     [rbp+57h+var_42], r15w
0x1800a1c6f  mov     [rbp+57h+var_50], r15w
0x1800a1c74  mov     [rbp+57h+var_88], r15b
0x1800a1c78  mov     rax, [rcx]
0x1800a1c7b  mov     rax, [rax+48h]
0x1800a1c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1c84  mov     ebx, eax
0x1800a1c86  test    eax, eax
0x1800a1c88  jns     short loc_1800A1CA7
0x1800a1c8a  mov     edx, 1
0x1800a1c8f  mov     r9d, 85h
0x1800a1c95  mov     ecx, eax; int
0x1800a1c97  call    Log_HREvent_77
0x1800a1c9c  lea     rcx, [rbp+57h+var_60]
0x1800a1ca0  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a1ca5  jmp     short loc_1800A1C3B
0x1800a1ca7  cmp     [rbp+57h+var_88], r15b
0x1800a1cab  jz      short loc_1800A1CDC
0x1800a1cad  mov     r8d, 1Ah
0x1800a1cb3  lea     rdx, aRemovedForPiiP; "Removed for PII protection"
0x1800a1cba  lea     rcx, [rbp+57h+var_60]
0x1800a1cbe  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800a1cc3  test    al, al
0x1800a1cc5  jnz     loc_1800A1E63
0x1800a1ccb  mov     ebx, 8007000Eh
0x1800a1cd0  xor     edx, edx
0x1800a1cd2  mov     ecx, ebx
0x1800a1cd4  mov     r9d, 88h
0x1800a1cda  jmp     short loc_1800A1C97
0x1800a1cdc  mov     rcx, [r14+10h]
0x1800a1ce0  lea     rdx, [rbp+57h+var_70]
0x1800a1ce4  mov     [rbp+57h+var_78], r15
0x1800a1ce8  mov     [rbp+57h+var_70], r15
0x1800a1cec  mov     rax, [rcx]
0x1800a1cef  mov     rax, [rax+30h]
0x1800a1cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1cf8  mov     ebx, eax
0x1800a1cfa  test    eax, eax
0x1800a1cfc  jns     short loc_1800A1D3C
0x1800a1cfe  mov     edx, 1
0x1800a1d03  mov     r9d, 8Eh
0x1800a1d09  mov     ecx, eax; int
0x1800a1d0b  call    Log_HREvent_77
0x1800a1d10  mov     rcx, [rbp+57h+var_70]
0x1800a1d14  test    rcx, rcx
0x1800a1d17  jz      short loc_1800A1D29
0x1800a1d19  mov     [rbp+57h+var_70], r15
0x1800a1d1d  mov     rdx, [rcx]
0x1800a1d20  mov     rax, [rdx+10h]
0x1800a1d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1d29  mov     rcx, [rbp+57h+var_78]; string
0x1800a1d2d  call    cs:__imp_WindowsDeleteString
0x1800a1d33  mov     [rbp+57h+var_78], r15
0x1800a1d37  jmp     loc_1800A1C9C
0x1800a1d3c  mov     rcx, [rbp+57h+var_70]
0x1800a1d40  lea     rdx, [rbp+57h+var_68]
0x1800a1d44  mov     [rbp+57h+var_68], r15
0x1800a1d48  mov     rax, [rcx]
0x1800a1d4b  mov     rax, [rax+50h]
0x1800a1d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1d54  mov     ebx, eax
0x1800a1d56  test    eax, eax
0x1800a1d58  jns     short loc_1800A1D9B
0x1800a1d5a  mov     edx, 1
0x1800a1d5f  mov     r9d, 91h
0x1800a1d65  mov     ecx, eax; int
0x1800a1d67  call    Log_HREvent_77
0x1800a1d6c  mov     rcx, [rbp+57h+var_68]
0x1800a1d70  test    rcx, rcx
0x1800a1d73  jz      short loc_1800A1D85
0x1800a1d75  mov     [rbp+57h+var_68], r15
0x1800a1d79  mov     rdx, [rcx]
0x1800a1d7c  mov     rax, [rdx+10h]
0x1800a1d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1d85  mov     rcx, [rbp+57h+var_70]
0x1800a1d89  test    rcx, rcx
0x1800a1d8c  jz      short loc_1800A1D29
0x1800a1d8e  mov     [rbp+57h+var_70], r15
0x1800a1d92  mov     rax, [rcx]
0x1800a1d95  mov     rax, [rax+10h]
0x1800a1d99  jmp     short loc_1800A1D24
0x1800a1d9b  mov     rcx, [rbp+57h+var_78]; string
0x1800a1d9f  call    cs:__imp_WindowsDeleteString
0x1800a1da5  mov     rdi, [rbp+57h+var_68]
0x1800a1da9  mov     rcx, rdi
0x1800a1dac  mov     [rbp+57h+var_78], r15
0x1800a1db0  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)
0x1800a1db5  mov     ebx, eax
0x1800a1db7  test    eax, eax
0x1800a1db9  js      short loc_1800A1DD0
0x1800a1dbb  mov     rax, [rdi]
0x1800a1dbe  lea     rdx, [rbp+57h+var_78]
0x1800a1dc2  mov     rcx, rdi
0x1800a1dc5  mov     rax, [rax+50h]
0x1800a1dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1dce  mov     ebx, eax
0x1800a1dd0  test    ebx, ebx
0x1800a1dd2  jns     short loc_1800A1DFC
0x1800a1dd4  mov     edx, 1
0x1800a1dd9  mov     r9d, 93h
0x1800a1ddf  mov     ecx, ebx; int
0x1800a1de1  call    Log_HREvent_77
0x1800a1de6  mov     rcx, [rbp+57h+var_68]
0x1800a1dea  test    rcx, rcx
0x1800a1ded  jz      short loc_1800A1D85
0x1800a1def  mov     [rbp+57h+var_68], r15
0x1800a1df3  mov     rax, [rcx]
0x1800a1df6  mov     rax, [rax+10h]
0x1800a1dfa  jmp     short loc_1800A1D80
0x1800a1dfc  mov     rcx, [rbp+57h+var_78]; string
0x1800a1e00  xor     edx, edx; length
0x1800a1e02  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a1e08  mov     rdx, rax
0x1800a1e0b  lea     rcx, [rbp+57h+var_60]
0x1800a1e0f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800a1e14  test    al, al
0x1800a1e16  jnz     short loc_1800A1E27
0x1800a1e18  xor     edx, edx
0x1800a1e1a  mov     ebx, 8007000Eh
0x1800a1e1f  mov     r9d, 95h
0x1800a1e25  jmp     short loc_1800A1DDF
0x1800a1e27  mov     rcx, [rbp+57h+var_68]
0x1800a1e2b  test    rcx, rcx
0x1800a1e2e  jz      short loc_1800A1E40
0x1800a1e30  mov     [rbp+57h+var_68], r15
0x1800a1e34  mov     rax, [rcx]
0x1800a1e37  mov     rax, [rax+10h]
0x1800a1e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1e40  mov     rcx, [rbp+57h+var_70]
0x1800a1e44  test    rcx, rcx
0x1800a1e47  jz      short loc_1800A1E59
0x1800a1e49  mov     [rbp+57h+var_70], r15
0x1800a1e4d  mov     rax, [rcx]
0x1800a1e50  mov     rax, [rax+10h]
0x1800a1e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1e59  mov     rcx, [rbp+57h+var_78]; string
0x1800a1e5d  call    cs:__imp_WindowsDeleteString
0x1800a1e63  sub     esi, 1
0x1800a1e66  jz      short loc_1800A1EE3
0x1800a1e68  sub     esi, 1
0x1800a1e6b  jz      short loc_1800A1EE3
0x1800a1e6d  sub     esi, 1
0x1800a1e70  jz      short loc_1800A1EE3
0x1800a1e72  mov     eax, cs:dword_1800FD5F0
0x1800a1e78  cmp     esi, 1
0x1800a1e7b  jz      short loc_1800A1EBF
0x1800a1e7d  cmp     eax, 5
0x1800a1e80  jbe     loc_1800A1F2F
0x1800a1e86  mov     rax, [rbp+57h+var_60]
0x1800a1e8a  lea     rdx, byte_1800F2D5F
0x1800a1e91  mov     [rbp+57h+var_98], rax
0x1800a1e95  mov     eax, [r14+18h]
0x1800a1e99  mov     [rbp+57h+var_A0], eax
0x1800a1e9c  lea     rax, aMessagingcloud; "[MessagingCloudServices] CloudServiceTr"...
0x1800a1ea3  mov     [rbp+57h+var_90], rax
0x1800a1ea7  lea     rax, [rbp+57h+var_98]
0x1800a1eab  mov     [rsp+0E0h+var_B0], rax
0x1800a1eb0  lea     rax, [rbp+57h+var_A0]
0x1800a1eb4  mov     [rsp+0E0h+var_B8], rax
0x1800a1eb9  lea     rax, [rbp+57h+var_90]
0x1800a1ebd  jmp     short loc_1800A1F25
0x1800a1ebf  cmp     eax, 4
0x1800a1ec2  jbe     short loc_1800A1F2F
0x1800a1ec4  mov     rax, [rbp+57h+var_60]
0x1800a1ec8  lea     rdx, byte_1800F2CF7
0x1800a1ecf  mov     [rbp+57h+var_90], rax
0x1800a1ed3  mov     eax, [r14+18h]
0x1800a1ed7  mov     [rbp+57h+var_A0], eax
0x1800a1eda  lea     rax, aMessagingcloud; "[MessagingCloudServices] CloudServiceTr"...
0x1800a1ee1  jmp     short loc_1800A1F0B
0x1800a1ee3  mov     eax, cs:dword_1800FD5F0
0x1800a1ee9  cmp     eax, 2
0x1800a1eec  jbe     short loc_1800A1F2F
0x1800a1eee  mov     rax, [rbp+57h+var_60]
0x1800a1ef2  lea     rdx, byte_1800F2DC7
0x1800a1ef9  mov     [rbp+57h+var_90], rax
0x1800a1efd  mov     eax, [r14+18h]
0x1800a1f01  mov     [rbp+57h+var_A0], eax
0x1800a1f04  lea     rax, aMessagingcloud_1; "[MessagingCloudServices] CloudServiceTr"...
0x1800a1f0b  mov     [rbp+57h+var_98], rax
0x1800a1f0f  lea     rax, [rbp+57h+var_90]
0x1800a1f13  mov     [rsp+0E0h+var_B0], rax
0x1800a1f18  lea     rax, [rbp+57h+var_A0]
0x1800a1f1c  mov     [rsp+0E0h+var_B8], rax
0x1800a1f21  lea     rax, [rbp+57h+var_98]
0x1800a1f25  mov     [rsp+0E0h+var_C0], rax
0x1800a1f2a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800a1f2f  lea     rcx, [rbp+57h+var_60]
0x1800a1f33  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a1f38  mov     rcx, [rbp+57h+string]; string
0x1800a1f3c  call    cs:__imp_WindowsDeleteString
0x1800a1f42  mov     ebx, r15d
0x1800a1f45  mov     [rbp+57h+string], r15
0x1800a1f49  lea     rcx, [rbp+57h+var_40]
0x1800a1f4d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1f52  mov     eax, ebx
0x1800a1f54  mov     rcx, [rbp+57h+var_38]
0x1800a1f58  xor     rcx, rsp; StackCookie
0x1800a1f5b  call    __security_check_cookie
0x1800a1f60  add     rsp, 0B8h
0x1800a1f67  pop     r15
0x1800a1f69  pop     r14
0x1800a1f6b  pop     rdi
0x1800a1f6c  pop     rsi
0x1800a1f6d  pop     rbx
0x1800a1f6e  pop     rbp
0x1800a1f6f  retn
```
