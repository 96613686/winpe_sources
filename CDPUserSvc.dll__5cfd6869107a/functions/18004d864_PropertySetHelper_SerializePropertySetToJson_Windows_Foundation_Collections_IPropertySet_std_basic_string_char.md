# PropertySetHelper::SerializePropertySetToJson(Windows::Foundation::Collections::IPropertySet *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x18004d864`
- end: `0x18004def2`
- name: `?SerializePropertySetToJson@PropertySetHelper@@SAJPEAUIPropertySet@Collections@Foundation@Windows@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1678`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004d5bc`

## callees

- `0x180003678`
- `0x180004a58`
- `0x18001e798`
- `0x180027fd4`
- `0x18002c570`
- `0x18002dcc0`
- `0x18002dd40`
- `0x18002e030`
- `0x18002e0f0`
- `0x18002e230`
- `0x180034b60`
- `0x180036710`
- `0x18003ff10`
- `0x18004bc10`
- `0x18004d864`
- `0x18005c0fc`
- `0x180064010`

## string_xrefs

- `0x18004d8cb`: `onecoreuap\windows\cdp\service\cdpusersvc\PropertySetHelper.h`
- `0x18004d934`: `onecoreuap\windows\cdp\service\cdpusersvc\PropertySetHelper.h`
- `0x18004d9a2`: `onecoreuap\windows\cdp\service\cdpusersvc\PropertySetHelper.h`
- `0x18004da14`: `onecoreuap\windows\cdp\service\cdpusersvc\PropertySetHelper.h`
- `0x18004daa3`: `onecoreuap\windows\cdp\service\cdpusersvc\PropertySetHelper.h`
- `0x18004db1c`: `onecoreuap\windows\cdp\service\cdpusersvc\PropertySetHelper.h`
- `0x18004db9b`: `onecoreuap\windows\cdp\service\cdpusersvc\PropertySetHelper.h`
- `0x18004dc1e`: `onecoreuap\windows\cdp\service\cdpusersvc\PropertySetHelper.h`
- `0x18004dcb0`: `onecoreuap\windows\cdp\service\cdpusersvc\PropertySetHelper.h`
- `0x18004ddc0`: `onecoreuap\windows\cdp\service\cdpusersvc\PropertySetHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall PropertySetHelper::SerializePropertySetToJson(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, _QWORD),
        __int64 a2)
{
  __int64 (__fastcall *v4)(_QWORD, GUID *, _QWORD); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rdi
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 *); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rbx
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // ebx
  int v26; // eax
  unsigned int v27; // ebx
  int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rax
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // eax
  unsigned int v35; // ebx
  __int64 v36; // rax
  int v37; // [rsp+20h] [rbp-178h] BYREF
  __int64 v38; // [rsp+28h] [rbp-170h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-168h] BYREF
  __int64 v40; // [rsp+38h] [rbp-160h] BYREF
  __int64 v41; // [rsp+40h] [rbp-158h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-150h] BYREF
  __int64 v43; // [rsp+50h] [rbp-148h] BYREF
  _BYTE v44[40]; // [rsp+58h] [rbp-140h] BYREF
  __int64 v45; // [rsp+80h] [rbp-118h] BYREF
  _QWORD v46[2]; // [rsp+88h] [rbp-110h] BYREF
  _BYTE v47[40]; // [rsp+98h] [rbp-100h] BYREF
  _BYTE v48[32]; // [rsp+C0h] [rbp-D8h] BYREF
  _BYTE v49[32]; // [rsp+E0h] [rbp-B8h] BYREF
  _BYTE v50[112]; // [rsp+100h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v39 = 0;
  v4 = **a1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  v5 = v4(a1, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v39);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v40 = 0;
    v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v39;
    v9 = **v39;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    v10 = v9(v8, &GUID_fe2f3d47_5d47_5499_8374_430c7cda0204, &v40);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v38 = 0;
      v12 = v40;
      v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      v14 = v13(v12, &v38);
      v15 = v14;
      if ( v14 >= 0 )
      {
        Json::Value::Value(v44, 0);
        LOBYTE(v37) = 0;
        v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 56LL))(v38, &v37);
        v17 = v16;
        if ( v16 >= 0 )
        {
          while ( (_BYTE)v37 )
          {
            v41 = 0;
            v18 = v38;
            v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 48LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
            v20 = v19(v18, &v41);
            v21 = v20;
            if ( v20 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC3,
                (unsigned int)"onecoreuap\\windows\\cdp\\service\\cdpusersvc\\PropertySetHelper.h",
                (const char *)(unsigned int)v20,
                v37);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
              Json::Value::~Value((Json::Value *)v44);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
              return v21;
            }
            v22 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v41 + 48LL))(v41, v46);
            v23 = v22;
            if ( v22 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC6,
                (unsigned int)"onecoreuap\\windows\\cdp\\service\\cdpusersvc\\PropertySetHelper.h",
                (const char *)(unsigned int)v22,
                v37);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
              Json::Value::~Value((Json::Value *)v44);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
              return v23;
            }
            v42 = 0;
            v24 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v41 + 56LL))(
                    v41,
                    &v42);
            v25 = v24;
            if ( v24 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC9,
                (unsigned int)"onecoreuap\\windows\\cdp\\service\\cdpusersvc\\PropertySetHelper.h",
                (const char *)(unsigned int)v24,
                v37);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
              Json::Value::~Value((Json::Value *)v44);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
              return v25;
            }
            v43 = 0;
            v26 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v42, (__int64)&v43);
            v27 = v26;
            if ( v26 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xCC,
                (unsigned int)"onecoreuap\\windows\\cdp\\service\\cdpusersvc\\PropertySetHelper.h",
                (const char *)(unsigned int)v26,
                v37);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
              Json::Value::~Value((Json::Value *)v44);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
              return v27;
            }
            v28 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 152LL))(v43, &v45);
            v29 = v28;
            if ( v28 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xCF,
                (unsigned int)"onecoreuap\\windows\\cdp\\service\\cdpusersvc\\PropertySetHelper.h",
                (const char *)(unsigned int)v28,
                v37);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
              Json::Value::~Value((Json::Value *)v44);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
              return v29;
            }
            v46[1] = v47;
            v30 = cdp::HSTRINGtoUTF8(v48, v45);
            v31 = Json::Value::Value(v47, v30);
            v32 = cdp::HSTRINGtoUTF8(v49, v46[0]);
            v33 = Json::Value::operator[](v44, v32);
            Json::Value::operator=(v33, v31);
            std::string::_Tidy_deallocate(v49);
            std::string::_Tidy_deallocate(v48);
            v34 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 64LL))(v38, &v37);
            v35 = v34;
            if ( v34 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xD3,
                (unsigned int)"onecoreuap\\windows\\cdp\\service\\cdpusersvc\\PropertySetHelper.h",
                (const char *)(unsigned int)v34,
                v37);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
              Json::Value::~Value((Json::Value *)v44);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
              return v35;
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
          }
          Json::StyledWriter::StyledWriter((Json::StyledWriter *)v50);
          v36 = Json::StyledWriter::write((Json::StyledWriter *)v50);
          std::string::operator=(a2, v36);
          std::string::_Tidy_deallocate(v48);
          Json::StyledWriter::~StyledWriter((Json::StyledWriter *)v50);
          Json::Value::~Value((Json::Value *)v44);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBE,
            (unsigned int)"onecoreuap\\windows\\cdp\\service\\cdpusersvc\\PropertySetHelper.h",
            (const char *)(unsigned int)v16,
            v37);
          Json::Value::~Value((Json::Value *)v44);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
          return v17;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB9,
          (unsigned int)"onecoreuap\\windows\\cdp\\service\\cdpusersvc\\PropertySetHelper.h",
          (const char *)(unsigned int)v14,
          v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
        return v15;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB6,
        (unsigned int)"onecoreuap\\windows\\cdp\\service\\cdpusersvc\\PropertySetHelper.h",
        (const char *)(unsigned int)v10,
        v37);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecoreuap\\windows\\cdp\\service\\cdpusersvc\\PropertySetHelper.h",
      (const char *)(unsigned int)v5,
      v37);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    return v6;
  }
}

```

## disassembly

```asm
0x18004d864  mov     [rsp+arg_10], rbx
0x18004d869  push    rsi
0x18004d86a  push    rdi
0x18004d86b  push    r14
0x18004d86d  sub     rsp, 180h
0x18004d874  mov     rax, cs:__security_cookie
0x18004d87b  xor     rax, rsp
0x18004d87e  mov     [rsp+198h+var_28], rax
0x18004d886  mov     r14, rdx
0x18004d889  mov     rdi, rcx
0x18004d88c  xor     esi, esi
0x18004d88e  mov     [rsp+198h+var_168], rsi
0x18004d893  mov     rax, [rcx]
0x18004d896  mov     rbx, [rax]
0x18004d899  lea     rcx, [rsp+198h+var_168]
0x18004d89e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d8a3  lea     r8, [rsp+198h+var_168]
0x18004d8a8  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18004d8af  mov     rcx, rdi
0x18004d8b2  mov     rax, rbx
0x18004d8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8ba  mov     ebx, eax
0x18004d8bc  test    eax, eax
0x18004d8be  jns     short loc_18004D8EE
0x18004d8c0  mov     rcx, [rsp+198h]; this
0x18004d8c8  mov     r9d, eax; char *
0x18004d8cb  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\cdp\\service\\cdpu"...
0x18004d8d2  mov     edx, 0B3h; void *
0x18004d8d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d8dc  nop
0x18004d8dd  lea     rcx, [rsp+198h+var_168]
0x18004d8e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d8e7  mov     eax, ebx
0x18004d8e9  jmp     loc_18004DECD
0x18004d8ee  mov     [rsp+198h+var_160], 0
0x18004d8f7  mov     rbx, [rsp+198h+var_168]
0x18004d8fc  mov     rax, [rbx]
0x18004d8ff  mov     rdi, [rax]
0x18004d902  lea     rcx, [rsp+198h+var_160]
0x18004d907  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d90c  lea     r8, [rsp+198h+var_160]
0x18004d911  lea     rdx, _GUID_fe2f3d47_5d47_5499_8374_430c7cda0204
0x18004d918  mov     rcx, rbx
0x18004d91b  mov     rax, rdi
0x18004d91e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d923  mov     ebx, eax
0x18004d925  test    eax, eax
0x18004d927  jns     short loc_18004D962
0x18004d929  mov     rcx, [rsp+198h]; this
0x18004d931  mov     r9d, eax; char *
0x18004d934  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\cdp\\service\\cdpu"...
0x18004d93b  mov     edx, 0B6h; void *
0x18004d940  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d945  nop
0x18004d946  lea     rcx, [rsp+198h+var_160]
0x18004d94b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d950  nop
0x18004d951  lea     rcx, [rsp+198h+var_168]
0x18004d956  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d95b  mov     eax, ebx
0x18004d95d  jmp     loc_18004DECD
0x18004d962  mov     [rsp+198h+var_170], 0
0x18004d96b  mov     rdi, [rsp+198h+var_160]
0x18004d970  mov     rax, [rdi]
0x18004d973  mov     rbx, [rax+30h]
0x18004d977  lea     rcx, [rsp+198h+var_170]
0x18004d97c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d981  lea     rdx, [rsp+198h+var_170]
0x18004d986  mov     rcx, rdi
0x18004d989  mov     rax, rbx
0x18004d98c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d991  mov     ebx, eax
0x18004d993  test    eax, eax
0x18004d995  jns     short loc_18004D9DB
0x18004d997  mov     rcx, [rsp+198h]; this
0x18004d99f  mov     r9d, eax; char *
0x18004d9a2  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\cdp\\service\\cdpu"...
0x18004d9a9  mov     edx, 0B9h; void *
0x18004d9ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d9b3  nop
0x18004d9b4  lea     rcx, [rsp+198h+var_170]
0x18004d9b9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d9be  nop
0x18004d9bf  lea     rcx, [rsp+198h+var_160]
0x18004d9c4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d9c9  nop
0x18004d9ca  lea     rcx, [rsp+198h+var_168]
0x18004d9cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d9d4  mov     eax, ebx
0x18004d9d6  jmp     loc_18004DECD
0x18004d9db  xor     edx, edx
0x18004d9dd  lea     rcx, [rsp+198h+var_140]
0x18004d9e2  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x18004d9e7  nop
0x18004d9e8  mov     byte ptr [rsp+198h+var_178], 0; int
0x18004d9ed  mov     rcx, [rsp+198h+var_170]
0x18004d9f2  mov     rax, [rcx]
0x18004d9f5  lea     rdx, [rsp+198h+var_178]
0x18004d9fa  mov     rax, [rax+38h]
0x18004d9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da03  mov     ebx, eax
0x18004da05  test    eax, eax
0x18004da07  jns     short loc_18004DA58
0x18004da09  mov     rcx, [rsp+198h]; this
0x18004da11  mov     r9d, eax; char *
0x18004da14  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\cdp\\service\\cdpu"...
0x18004da1b  mov     edx, 0BEh; void *
0x18004da20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004da25  nop
0x18004da26  lea     rcx, [rsp+198h+var_140]; this
0x18004da2b  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x18004da30  nop
0x18004da31  lea     rcx, [rsp+198h+var_170]
0x18004da36  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004da3b  nop
0x18004da3c  lea     rcx, [rsp+198h+var_160]
0x18004da41  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004da46  nop
0x18004da47  lea     rcx, [rsp+198h+var_168]
0x18004da4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004da51  mov     eax, ebx
0x18004da53  jmp     loc_18004DECD
0x18004da58  cmp     byte ptr [rsp+198h+var_178], 0
0x18004da5d  jz      loc_18004DE4A
0x18004da63  mov     [rsp+198h+var_158], 0
0x18004da6c  mov     rdi, [rsp+198h+var_170]
0x18004da71  mov     rax, [rdi]
0x18004da74  mov     rbx, [rax+30h]
0x18004da78  lea     rcx, [rsp+198h+var_158]
0x18004da7d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004da82  lea     rdx, [rsp+198h+var_158]
0x18004da87  mov     rcx, rdi
0x18004da8a  mov     rax, rbx
0x18004da8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da92  mov     ebx, eax
0x18004da94  test    eax, eax
0x18004da96  jns     short loc_18004DAF2
0x18004da98  mov     rcx, [rsp+198h]; this
0x18004daa0  mov     r9d, eax; char *
0x18004daa3  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\cdp\\service\\cdpu"...
0x18004daaa  mov     edx, 0C3h; void *
0x18004daaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dab4  nop
0x18004dab5  lea     rcx, [rsp+198h+var_158]
0x18004daba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dabf  nop
0x18004dac0  lea     rcx, [rsp+198h+var_140]; this
0x18004dac5  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x18004daca  nop
0x18004dacb  lea     rcx, [rsp+198h+var_170]
0x18004dad0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dad5  nop
0x18004dad6  lea     rcx, [rsp+198h+var_160]
0x18004dadb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dae0  nop
0x18004dae1  lea     rcx, [rsp+198h+var_168]
0x18004dae6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004daeb  mov     eax, ebx
0x18004daed  jmp     loc_18004DECD
0x18004daf2  mov     rcx, [rsp+198h+var_158]
0x18004daf7  mov     rax, [rcx]
0x18004dafa  lea     rdx, [rsp+198h+var_110]
0x18004db02  mov     rax, [rax+30h]
0x18004db06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db0b  mov     ebx, eax
0x18004db0d  test    eax, eax
0x18004db0f  jns     short loc_18004DB6B
0x18004db11  mov     rcx, [rsp+198h]; this
0x18004db19  mov     r9d, eax; char *
0x18004db1c  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\cdp\\service\\cdpu"...
0x18004db23  mov     edx, 0C6h; void *
0x18004db28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004db2d  nop
0x18004db2e  lea     rcx, [rsp+198h+var_158]
0x18004db33  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004db38  nop
0x18004db39  lea     rcx, [rsp+198h+var_140]; this
0x18004db3e  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x18004db43  nop
0x18004db44  lea     rcx, [rsp+198h+var_170]
0x18004db49  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004db4e  nop
0x18004db4f  lea     rcx, [rsp+198h+var_160]
0x18004db54  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004db59  nop
0x18004db5a  lea     rcx, [rsp+198h+var_168]
0x18004db5f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004db64  mov     eax, ebx
0x18004db66  jmp     loc_18004DECD
0x18004db6b  mov     [rsp+198h+var_150], 0
0x18004db74  mov     rcx, [rsp+198h+var_158]
0x18004db79  mov     rax, [rcx]
0x18004db7c  lea     rdx, [rsp+198h+var_150]
0x18004db81  mov     rax, [rax+38h]
0x18004db85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db8a  mov     ebx, eax
0x18004db8c  test    eax, eax
0x18004db8e  jns     short loc_18004DBF5
0x18004db90  mov     rcx, [rsp+198h]; this
0x18004db98  mov     r9d, eax; char *
0x18004db9b  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\cdp\\service\\cdpu"...
0x18004dba2  mov     edx, 0C9h; void *
0x18004dba7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dbac  nop
0x18004dbad  lea     rcx, [rsp+198h+var_150]
0x18004dbb2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dbb7  nop
0x18004dbb8  lea     rcx, [rsp+198h+var_158]
0x18004dbbd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dbc2  nop
0x18004dbc3  lea     rcx, [rsp+198h+var_140]; this
0x18004dbc8  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x18004dbcd  nop
0x18004dbce  lea     rcx, [rsp+198h+var_170]
0x18004dbd3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dbd8  nop
0x18004dbd9  lea     rcx, [rsp+198h+var_160]
0x18004dbde  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dbe3  nop
0x18004dbe4  lea     rcx, [rsp+198h+var_168]
0x18004dbe9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dbee  mov     eax, ebx
0x18004dbf0  jmp     loc_18004DECD
0x18004dbf5  mov     [rsp+198h+var_148], 0
0x18004dbfe  lea     rdx, [rsp+198h+var_148]
0x18004dc03  lea     rcx, [rsp+198h+var_150]
0x18004dc08  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x18004dc0d  mov     ebx, eax
0x18004dc0f  test    eax, eax
0x18004dc11  jns     short loc_18004DC83
0x18004dc13  mov     rcx, [rsp+198h]; this
0x18004dc1b  mov     r9d, eax; char *
0x18004dc1e  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\cdp\\service\\cdpu"...
0x18004dc25  mov     edx, 0CCh; void *
0x18004dc2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dc2f  nop
0x18004dc30  lea     rcx, [rsp+198h+var_148]
0x18004dc35  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dc3a  nop
0x18004dc3b  lea     rcx, [rsp+198h+var_150]
0x18004dc40  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dc45  nop
0x18004dc46  lea     rcx, [rsp+198h+var_158]
0x18004dc4b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dc50  nop
0x18004dc51  lea     rcx, [rsp+198h+var_140]; this
0x18004dc56  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x18004dc5b  nop
0x18004dc5c  lea     rcx, [rsp+198h+var_170]
0x18004dc61  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dc66  nop
0x18004dc67  lea     rcx, [rsp+198h+var_160]
0x18004dc6c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dc71  nop
0x18004dc72  lea     rcx, [rsp+198h+var_168]
0x18004dc77  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dc7c  mov     eax, ebx
0x18004dc7e  jmp     loc_18004DECD
0x18004dc83  mov     rcx, [rsp+198h+var_148]
0x18004dc88  mov     rax, [rcx]
0x18004dc8b  lea     rdx, [rsp+198h+var_118]
0x18004dc93  mov     rax, [rax+98h]
0x18004dc9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc9f  mov     ebx, eax
0x18004dca1  test    eax, eax
0x18004dca3  jns     short loc_18004DD15
0x18004dca5  mov     rcx, [rsp+198h]; this
0x18004dcad  mov     r9d, eax; char *
0x18004dcb0  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\cdp\\service\\cdpu"...
0x18004dcb7  mov     edx, 0CFh; void *
0x18004dcbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dcc1  nop
0x18004dcc2  lea     rcx, [rsp+198h+var_148]
0x18004dcc7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dccc  nop
0x18004dccd  lea     rcx, [rsp+198h+var_150]
0x18004dcd2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dcd7  nop
0x18004dcd8  lea     rcx, [rsp+198h+var_158]
0x18004dcdd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dce2  nop
0x18004dce3  lea     rcx, [rsp+198h+var_140]; this
0x18004dce8  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x18004dced  nop
0x18004dcee  lea     rcx, [rsp+198h+var_170]
0x18004dcf3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dcf8  nop
0x18004dcf9  lea     rcx, [rsp+198h+var_160]
0x18004dcfe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dd03  nop
0x18004dd04  lea     rcx, [rsp+198h+var_168]
0x18004dd09  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dd0e  mov     eax, ebx
0x18004dd10  jmp     loc_18004DECD
0x18004dd15  lea     rax, [rsp+198h+var_100]
0x18004dd1d  mov     [rsp+198h+var_108], rax
0x18004dd25  mov     rdx, [rsp+198h+var_118]
0x18004dd2d  lea     rcx, [rsp+198h+var_D8]
0x18004dd35  call    ?HSTRINGtoUTF8@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAUHSTRING__@@@Z; cdp::HSTRINGtoUTF8(HSTRING__ * const)
0x18004dd3a  nop
  ... truncated ...
```
