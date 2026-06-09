# AsyncMediaServiceDownloadContentTransaction::_HandleSuccessResponse(void)

- ea: `0x1800abbf0`
- end: `0x1800ac08e`
- name: `?_HandleSuccessResponse@AsyncMediaServiceDownloadContentTransaction@@EEAAJXZ`
- size: `1182`
- prototype: `__int64 __fastcall(AsyncMediaServiceDownloadContentTransaction *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b7d4`
- `0x18002cf18`
- `0x1800a1b60`
- `0x1800ab5b0`
- `0x1800ab9c0`
- `0x1800abbf0`
- `0x1800b1f5c`
- `0x1800b1f8c`
- `0x1800c50ec`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800abd59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800abd59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800abd19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800abd95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800abf71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac013`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800abd19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800abd95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800abf71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac013`

## pseudocode

```c
__int64 __fastcall AsyncMediaServiceDownloadContentTransaction::_HandleSuccessResponse(
        AsyncMediaServiceDownloadContentTransaction *this)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  __int64 v12; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  int (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rdx
  int (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // rdi
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  void (*v26)(void); // rax
  __int64 v27; // rcx
  int (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v33; // rcx
  int (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // [rsp+30h] [rbp-50h] BYREF
  __int64 v39; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v40[8]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v41; // [rsp+48h] [rbp-38h] BYREF
  __int64 v42; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  int (__fastcall ***v44)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-20h] BYREF
  __int64 v45; // [rsp+68h] [rbp-18h] BYREF
  __int64 v46; // [rsp+70h] [rbp-10h] BYREF

  v2 = *((_QWORD *)this + 2);
  v39 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 48LL))(v2, &v39);
  v4 = v3;
  if ( v3 < 0 )
  {
    Log_HREvent_87(v3);
LABEL_3:
    v5 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    return (unsigned int)v4;
  }
  v41 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 48LL))(v39, &v41);
  v4 = v6;
  if ( v6 < 0 )
  {
    Log_HREvent_87(v6);
    v7 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
LABEL_56:
    v37 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    return (unsigned int)v4;
  }
  v42 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 144LL))(v41, &v42);
  v4 = v8;
  if ( v8 < 0 )
  {
    Log_HREvent_87(v8);
    v9 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
LABEL_54:
    v36 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    goto LABEL_56;
  }
  v10 = v42;
  string = 0;
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v42 + 64LL);
  WindowsDeleteString(0);
  string = 0;
  v4 = v11(v10, &string);
  if ( v4 < 0 )
    goto LABEL_12;
  v12 = *((_QWORD *)this + 11);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v12 + 56,
                           StringRawBuffer) )
  {
    v4 = -2147024882;
    Log_HREvent_93(-2147024882);
LABEL_15:
    Log_HREvent_87(v4);
    WindowsDeleteString(string);
    v14 = v42;
    string = 0;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    goto LABEL_3;
  }
  v46 = 0;
  v40[0] = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *, _BYTE *))(*(_QWORD *)v39 + 88LL))(v39, &v46, v40);
  if ( v4 < 0 )
  {
LABEL_12:
    Log_HREvent_87(v4);
LABEL_52:
    WindowsDeleteString(string);
    v35 = v42;
    string = 0;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    goto LABEL_54;
  }
  if ( !v40[0] )
  {
    v4 = -2147418113;
    goto LABEL_15;
  }
  *(_DWORD *)(*((_QWORD *)this + 11) + 88LL) = v46;
  v44 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v39 + 72LL))(
          v39,
          &v44);
  v4 = v16;
  if ( v16 < 0 )
  {
    Log_HREvent_87(v16);
    v17 = v44;
    if ( v44 )
    {
      v44 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v17)[2])(v17);
    }
    goto LABEL_52;
  }
  v18 = v44;
  v45 = 0;
  v4 = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,unsigned __int64>>(v44);
  if ( v4 < 0
    || (v4 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v18)[10])(v18, &v45),
        v4 < 0) )
  {
    Log_HREvent_87(v4);
    v33 = v45;
    if ( !v45 )
      goto LABEL_50;
    v45 = 0;
    v26 = *(void (**)(void))(*(_QWORD *)v33 + 16LL);
LABEL_49:
    v26();
LABEL_50:
    v34 = v44;
    if ( v44 )
    {
      v44 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v34)[2])(v34);
    }
    goto LABEL_52;
  }
  v21 = *((_QWORD *)this + 11);
  v22 = v45;
  if ( *(_QWORD *)(v21 + 96) )
  {
    Log_AssertionEvent_55(v20, v19, 93);
    if ( *(_QWORD *)(v21 + 96) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( *(_QWORD *)(v21 + 96) != v22 )
  {
    v38 = v22;
    Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher>::InternalAddRef(&v38);
    v23 = *(_QWORD *)(v21 + 96);
    *(_QWORD *)(v21 + 96) = v22;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = CloudServiceTransaction::_HandleSuccessResponse(this);
  v4 = v24;
  if ( v24 < 0 )
  {
    Log_HREvent_87(v24);
    v25 = v45;
    if ( !v45 )
      goto LABEL_50;
    v45 = 0;
    v26 = *(void (**)(void))(*(_QWORD *)v25 + 16LL);
    goto LABEL_49;
  }
  v27 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = v44;
  if ( v44 )
  {
    v44 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v28)[2])(v28);
  }
  WindowsDeleteString(string);
  v29 = v42;
  string = 0;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  return 0;
}

```

## disassembly

```asm
0x1800abbf0  mov     [rsp-18h+arg_8], rbx
0x1800abbf5  mov     [rsp-18h+arg_10], rsi
0x1800abbfa  push    rbp
0x1800abbfb  push    rdi
0x1800abbfc  push    r14
0x1800abbfe  mov     rbp, rsp
0x1800abc01  sub     rsp, 80h
0x1800abc08  mov     rax, cs:__security_cookie
0x1800abc0f  xor     rax, rsp
0x1800abc12  mov     [rbp+var_8], rax
0x1800abc16  mov     rsi, rcx
0x1800abc19  lea     rdx, [rbp+var_48]
0x1800abc1d  mov     rcx, [rcx+10h]
0x1800abc21  xor     r14d, r14d
0x1800abc24  mov     [rbp+var_48], r14
0x1800abc28  mov     rax, [rcx]
0x1800abc2b  mov     rax, [rax+30h]
0x1800abc2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abc34  mov     ebx, eax
0x1800abc36  test    eax, eax
0x1800abc38  jns     short loc_1800ABC69
0x1800abc3a  lea     edx, [r14+1]
0x1800abc3e  mov     ecx, eax; int
0x1800abc40  lea     r9d, [r14+62h]
0x1800abc44  call    Log_HREvent_87
0x1800abc49  mov     rdx, [rbp+var_48]
0x1800abc4d  test    rdx, rdx
0x1800abc50  jz      loc_1800AC068
0x1800abc56  mov     [rbp+var_48], r14
0x1800abc5a  mov     rcx, [rdx]
0x1800abc5d  mov     rax, [rcx+10h]
0x1800abc61  mov     rcx, rdx
0x1800abc64  jmp     loc_1800AC063
0x1800abc69  mov     rcx, [rbp+var_48]
0x1800abc6d  lea     rdx, [rbp+var_38]
0x1800abc71  mov     [rbp+var_38], r14
0x1800abc75  mov     rax, [rcx]
0x1800abc78  mov     rax, [rax+30h]
0x1800abc7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abc81  mov     ebx, eax
0x1800abc83  test    eax, eax
0x1800abc85  jns     short loc_1800ABCB7
0x1800abc87  mov     edx, 1
0x1800abc8c  mov     ecx, eax; int
0x1800abc8e  lea     r9d, [rdx+65h]
0x1800abc92  call    Log_HREvent_87
0x1800abc97  mov     rdx, [rbp+var_38]
0x1800abc9b  test    rdx, rdx
0x1800abc9e  jz      loc_1800AC04F
0x1800abca4  mov     [rbp+var_38], r14
0x1800abca8  mov     rcx, [rdx]
0x1800abcab  mov     rax, [rcx+10h]
0x1800abcaf  mov     rcx, rdx
0x1800abcb2  jmp     loc_1800AC04A
0x1800abcb7  mov     rcx, [rbp+var_38]
0x1800abcbb  lea     rdx, [rbp+var_30]
0x1800abcbf  mov     [rbp+var_30], r14
0x1800abcc3  mov     rax, [rcx]
0x1800abcc6  mov     rax, [rax+90h]
0x1800abccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abcd2  mov     ebx, eax
0x1800abcd4  test    eax, eax
0x1800abcd6  jns     short loc_1800ABD08
0x1800abcd8  mov     edx, 1
0x1800abcdd  mov     ecx, eax; int
0x1800abcdf  lea     r9d, [rdx+67h]
0x1800abce3  call    Log_HREvent_87
0x1800abce8  mov     rdx, [rbp+var_30]
0x1800abcec  test    rdx, rdx
0x1800abcef  jz      loc_1800AC036
0x1800abcf5  mov     [rbp+var_30], r14
0x1800abcf9  mov     rcx, [rdx]
0x1800abcfc  mov     rax, [rcx+10h]
0x1800abd00  mov     rcx, rdx
0x1800abd03  jmp     loc_1800AC031
0x1800abd08  mov     rdi, [rbp+var_30]
0x1800abd0c  xor     ecx, ecx; string
0x1800abd0e  mov     [rbp+string], r14
0x1800abd12  mov     rax, [rdi]
0x1800abd15  mov     rbx, [rax+40h]
0x1800abd19  call    cs:__imp_WindowsDeleteString
0x1800abd1f  lea     rdx, [rbp+string]
0x1800abd23  mov     [rbp+string], r14
0x1800abd27  mov     rcx, rdi
0x1800abd2a  mov     rax, rbx
0x1800abd2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abd32  mov     ebx, eax
0x1800abd34  test    eax, eax
0x1800abd36  jns     short loc_1800ABD4F
0x1800abd38  mov     r9d, 6Ah ; 'j'
0x1800abd3e  mov     edx, 1
0x1800abd43  mov     ecx, ebx; int
0x1800abd45  call    Log_HREvent_87
0x1800abd4a  jmp     loc_1800AC00F
0x1800abd4f  mov     rcx, [rbp+string]; string
0x1800abd53  xor     edx, edx; length
0x1800abd55  mov     rbx, [rsi+58h]
0x1800abd59  call    cs:__imp_WindowsGetStringRawBuffer
0x1800abd5f  mov     rdx, rax
0x1800abd62  lea     rcx, [rbx+38h]
0x1800abd66  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800abd6b  test    al, al
0x1800abd6d  jnz     short loc_1800ABDDA
0x1800abd6f  xor     edx, edx
0x1800abd71  mov     ebx, 8007000Eh
0x1800abd76  mov     ecx, ebx; int
0x1800abd78  lea     r9d, [rdx+48h]
0x1800abd7c  call    Log_HREvent_93
0x1800abd81  mov     edx, 1
0x1800abd86  lea     r9d, [rdx+6Ah]
0x1800abd8a  mov     ecx, ebx; int
0x1800abd8c  call    Log_HREvent_87
0x1800abd91  mov     rcx, [rbp+string]; string
0x1800abd95  call    cs:__imp_WindowsDeleteString
0x1800abd9b  mov     rcx, [rbp+var_30]
0x1800abd9f  mov     [rbp+string], r14
0x1800abda3  test    rcx, rcx
0x1800abda6  jz      short loc_1800ABDB8
0x1800abda8  mov     [rbp+var_30], r14
0x1800abdac  mov     rax, [rcx]
0x1800abdaf  mov     rax, [rax+10h]
0x1800abdb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abdb8  mov     rcx, [rbp+var_38]
0x1800abdbc  test    rcx, rcx
0x1800abdbf  jz      loc_1800ABC49
0x1800abdc5  mov     [rbp+var_38], r14
0x1800abdc9  mov     rax, [rcx]
0x1800abdcc  mov     rax, [rax+10h]
0x1800abdd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abdd5  jmp     loc_1800ABC49
0x1800abdda  mov     rcx, [rbp+var_48]
0x1800abdde  lea     r8, [rbp+var_40]
0x1800abde2  mov     [rbp+var_10], r14
0x1800abde6  lea     rdx, [rbp+var_10]
0x1800abdea  mov     [rbp+var_40], r14b
0x1800abdee  mov     rax, [rcx]
0x1800abdf1  mov     rax, [rax+58h]
0x1800abdf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abdfa  mov     ebx, eax
0x1800abdfc  test    eax, eax
0x1800abdfe  jns     short loc_1800ABE0B
0x1800abe00  mov     r9d, 70h ; 'p'
0x1800abe06  jmp     loc_1800ABD3E
0x1800abe0b  cmp     [rbp+var_40], r14b
0x1800abe0f  jnz     short loc_1800ABE21
0x1800abe11  xor     edx, edx
0x1800abe13  mov     ebx, 8000FFFFh
0x1800abe18  lea     r9d, [rdx+72h]
0x1800abe1c  jmp     loc_1800ABD8A
0x1800abe21  mov     rcx, [rsi+58h]
0x1800abe25  lea     rdx, [rbp+var_20]
0x1800abe29  mov     eax, dword ptr [rbp+var_10]
0x1800abe2c  mov     [rcx+58h], eax
0x1800abe2f  mov     rcx, [rbp+var_48]
0x1800abe33  mov     [rbp+var_20], r14
0x1800abe37  mov     rax, [rcx]
0x1800abe3a  mov     rax, [rax+48h]
0x1800abe3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abe43  mov     ebx, eax
0x1800abe45  test    eax, eax
0x1800abe47  jns     short loc_1800ABE79
0x1800abe49  mov     edx, 1
0x1800abe4e  mov     ecx, eax; int
0x1800abe50  lea     r9d, [rdx+77h]
0x1800abe54  call    Log_HREvent_87
0x1800abe59  mov     rdx, [rbp+var_20]
0x1800abe5d  test    rdx, rdx
0x1800abe60  jz      loc_1800AC00F
0x1800abe66  mov     [rbp+var_20], r14
0x1800abe6a  mov     rcx, [rdx]
0x1800abe6d  mov     rax, [rcx+10h]
0x1800abe71  mov     rcx, rdx
0x1800abe74  jmp     loc_1800AC00A
0x1800abe79  mov     rdi, [rbp+var_20]
0x1800abe7d  mov     rcx, rdi
0x1800abe80  mov     [rbp+var_18], r14
0x1800abe84  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)
0x1800abe89  mov     ebx, eax
0x1800abe8b  test    eax, eax
0x1800abe8d  js      loc_1800ABFCD
0x1800abe93  mov     rax, [rdi]
0x1800abe96  lea     rdx, [rbp+var_18]
0x1800abe9a  mov     rcx, rdi
0x1800abe9d  mov     rax, [rax+50h]
0x1800abea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abea6  mov     ebx, eax
0x1800abea8  test    eax, eax
0x1800abeaa  js      loc_1800ABFCD
0x1800abeb0  mov     rbx, [rsi+58h]
0x1800abeb4  mov     rdi, [rbp+var_18]
0x1800abeb8  cmp     [rbx+60h], r14
0x1800abebc  jz      short loc_1800ABED4
0x1800abebe  mov     r8d, 5Dh ; ']'
0x1800abec4  call    Log_AssertionEvent_55
0x1800abec9  cmp     [rbx+60h], r14
0x1800abecd  jz      short loc_1800ABED4
0x1800abecf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800abed4  cmp     [rbx+60h], rdi
0x1800abed8  jz      short loc_1800ABF00
0x1800abeda  lea     rcx, [rbp+var_50]
0x1800abede  mov     [rbp+var_50], rdi
0x1800abee2  call    ?InternalAddRef@?$ComPtr@UIImsClientWatcher@Rcs@Cellular@Restricted@Phone@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher>::InternalAddRef(void)
0x1800abee7  mov     rcx, [rbx+60h]
0x1800abeeb  mov     [rbx+60h], rdi
0x1800abeef  test    rcx, rcx
0x1800abef2  jz      short loc_1800ABF00
0x1800abef4  mov     rax, [rcx]
0x1800abef7  mov     rax, [rax+10h]
0x1800abefb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf00  mov     rcx, rsi; this
0x1800abf03  call    ?_HandleSuccessResponse@CloudServiceTransaction@@MEAAJXZ; CloudServiceTransaction::_HandleSuccessResponse(void)
0x1800abf08  mov     ebx, eax
0x1800abf0a  test    eax, eax
0x1800abf0c  jns     short loc_1800ABF3B
0x1800abf0e  mov     edx, 1
0x1800abf13  mov     ecx, eax; int
0x1800abf15  lea     r9d, [rdx+7Fh]
0x1800abf19  call    Log_HREvent_87
0x1800abf1e  mov     rcx, [rbp+var_18]
0x1800abf22  test    rcx, rcx
0x1800abf25  jz      loc_1800ABFF6
0x1800abf2b  mov     [rbp+var_18], r14
0x1800abf2f  mov     rdx, [rcx]
0x1800abf32  mov     rax, [rdx+10h]
0x1800abf36  jmp     loc_1800ABFF1
0x1800abf3b  mov     rcx, [rbp+var_18]
0x1800abf3f  test    rcx, rcx
0x1800abf42  jz      short loc_1800ABF54
0x1800abf44  mov     [rbp+var_18], r14
0x1800abf48  mov     rax, [rcx]
0x1800abf4b  mov     rax, [rax+10h]
0x1800abf4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf54  mov     rcx, [rbp+var_20]
0x1800abf58  test    rcx, rcx
0x1800abf5b  jz      short loc_1800ABF6D
0x1800abf5d  mov     [rbp+var_20], r14
0x1800abf61  mov     rax, [rcx]
0x1800abf64  mov     rax, [rax+10h]
0x1800abf68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf6d  mov     rcx, [rbp+string]; string
0x1800abf71  call    cs:__imp_WindowsDeleteString
0x1800abf77  mov     rcx, [rbp+var_30]
0x1800abf7b  mov     [rbp+string], r14
0x1800abf7f  test    rcx, rcx
0x1800abf82  jz      short loc_1800ABF94
0x1800abf84  mov     [rbp+var_30], r14
0x1800abf88  mov     rax, [rcx]
0x1800abf8b  mov     rax, [rax+10h]
0x1800abf8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf94  mov     rcx, [rbp+var_38]
0x1800abf98  test    rcx, rcx
0x1800abf9b  jz      short loc_1800ABFAD
0x1800abf9d  mov     [rbp+var_38], r14
0x1800abfa1  mov     rax, [rcx]
0x1800abfa4  mov     rax, [rax+10h]
0x1800abfa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abfad  mov     rcx, [rbp+var_48]
0x1800abfb1  test    rcx, rcx
0x1800abfb4  jz      short loc_1800ABFC6
0x1800abfb6  mov     [rbp+var_48], r14
0x1800abfba  mov     rax, [rcx]
0x1800abfbd  mov     rax, [rax+10h]
0x1800abfc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abfc6  xor     eax, eax
0x1800abfc8  jmp     loc_1800AC06A
0x1800abfcd  mov     edx, 1
0x1800abfd2  mov     ecx, ebx; int
0x1800abfd4  lea     r9d, [rdx+7Ah]
0x1800abfd8  call    Log_HREvent_87
0x1800abfdd  mov     rcx, [rbp+var_18]
0x1800abfe1  test    rcx, rcx
0x1800abfe4  jz      short loc_1800ABFF6
0x1800abfe6  mov     [rbp+var_18], r14
0x1800abfea  mov     rax, [rcx]
0x1800abfed  mov     rax, [rax+10h]
0x1800abff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abff6  mov     rcx, [rbp+var_20]
0x1800abffa  test    rcx, rcx
0x1800abffd  jz      short loc_1800AC00F
0x1800abfff  mov     [rbp+var_20], r14
0x1800ac003  mov     rax, [rcx]
0x1800ac006  mov     rax, [rax+10h]
0x1800ac00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac00f  mov     rcx, [rbp+string]; string
0x1800ac013  call    cs:__imp_WindowsDeleteString
0x1800ac019  mov     rcx, [rbp+var_30]
0x1800ac01d  mov     [rbp+string], r14
0x1800ac021  test    rcx, rcx
0x1800ac024  jz      short loc_1800AC036
0x1800ac026  mov     [rbp+var_30], r14
0x1800ac02a  mov     rax, [rcx]
0x1800ac02d  mov     rax, [rax+10h]
0x1800ac031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac036  mov     rcx, [rbp+var_38]
0x1800ac03a  test    rcx, rcx
0x1800ac03d  jz      short loc_1800AC04F
0x1800ac03f  mov     [rbp+var_38], r14
0x1800ac043  mov     rax, [rcx]
0x1800ac046  mov     rax, [rax+10h]
0x1800ac04a  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
