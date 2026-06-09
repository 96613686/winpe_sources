# DdcDeviceInfoHelper::GetChassisType(int *)

- ea: `0x180015a4c`
- end: `0x180015d79`
- name: `?GetChassisType@DdcDeviceInfoHelper@@CAJPEAH@Z`
- size: `813`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180016aa4`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x180004db8`
- `0x1800050b8`
- `0x1800145e0`
- `0x180014868`
- `0x180014c44`
- `0x180015a4c`
- `0x18002893c`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180015a8c`
- `OLEAUT32!__imp_VariantInit` at `0x180015a8c`
- `OLEAUT32!__imp_VariantClear` at `0x180015c27`
- `OLEAUT32!__imp_VariantClear` at `0x180015c27`

## string_xrefs

- `0x180015ac1`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetChassisType(int *a1)
{
  int v2; // edx
  int v3; // ecx
  int v4; // ebx
  HRESULT v5; // eax
  int v6; // edx
  __m128i v7; // xmm1
  unsigned __int64 v8; // xmm1_8
  int *v9; // rax
  __int64 v10; // rcx
  char v12; // [rsp+20h] [rbp-79h]
  const char *v13; // [rsp+28h] [rbp-71h]
  int v14; // [rsp+40h] [rbp-59h] BYREF
  __int64 v15; // [rsp+48h] [rbp-51h] BYREF
  IUnknown *v16; // [rsp+50h] [rbp-49h] BYREF
  VARIANTARG v17; // [rsp+58h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v19[32]; // [rsp+88h] [rbp-11h] BYREF
  _BYTE v20[32]; // [rsp+A8h] [rbp+Fh] BYREF

  v16 = 0;
  v15 = 0;
  v14 = 0;
  memset(&v17, 0, sizeof(v17));
  VariantInit(&pvarg);
  if ( !a1 )
  {
    v4 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_33;
    v13 = "CPR(piChassisType)";
    v12 = 100;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      v3,
      v2,
      v4,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      v12,
      v13);
    goto LABEL_33;
  }
  *a1 = 0;
  std::wstring::wstring(v20, L"ROOT\\CIMV2");
  std::wstring::wstring(v19, L"select ChassisTypes from Win32_SystemEnclosure");
  v4 = DdcDeviceInfoHelper::ExecuteWmiQuery((int)v19, (int)v20, &v16);
  std::wstring::_Tidy_deallocate((__int64)v19);
  std::wstring::_Tidy_deallocate((__int64)v20);
  if ( v4 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_33;
    v13 = "CHR(ExecuteWmiQuery(L\"select ChassisTypes from Win32_SystemEnclosure\", L\"ROOT\\\\CIMV2\", pEnumerator.GetAddressOf()))";
    v12 = 104;
    goto LABEL_4;
  }
  v4 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64 *, int *))v16->lpVtbl[1].AddRef)(
         v16,
         5000,
         1,
         &v15,
         &v14);
  if ( v4 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_33;
    v13 = "CHR(pEnumerator->Next(5000, 1, pEnclosureInfo.GetAddressOf(), &cObjects))";
    v12 = 105;
    goto LABEL_4;
  }
  if ( v14 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v15 + 32LL))(
           v15,
           L"ChassisTypes",
           0,
           &v17,
           0,
           0);
    if ( v4 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_33;
      v13 = "CHR(pEnclosureInfo->Get(L\"ChassisTypes\", 0, &chassisTypesRawVariant, 0, 0))";
      v12 = 107;
      goto LABEL_4;
    }
    v5 = VariantClear(&pvarg);
    if ( v5 < 0 )
      _com_issue_error(v5);
    v7 = *(__m128i *)&v17.vt;
    pvarg = v17;
    v17.vt = 0;
    if ( (unsigned __int16)_mm_cvtsi128_si32(*(__m128i *)&pvarg.vt) == 8195 )
    {
      v8 = _mm_srli_si128(v7, 8).m128i_u64[0];
      if ( v8 )
      {
        if ( *(_WORD *)v8 )
        {
          v9 = *(int **)(v8 + 16);
          if ( v9 )
          {
            *a1 = *v9;
          }
          else
          {
            v4 = -2147418113;
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                8195,
                v6,
                -2147418113,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                114,
                "CBR(chassisTypesVariant.parray->pvData != nullptr)");
          }
        }
        else
        {
          v4 = -2147418113;
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              8195,
              v6,
              -2147418113,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              113,
              "CBR(chassisTypesVariant.parray->cDims > 0)");
        }
      }
      else
      {
        v4 = -2147418113;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            8195,
            v6,
            -2147418113,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
            112,
            "CBR(chassisTypesVariant.parray != nullptr)");
      }
    }
    else
    {
      v4 = -2147418113;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          8195,
          v6,
          -2147418113,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          111,
          "CBR(chassisTypesVariant.vt == (VT_ARRAY + VT_I4))");
    }
  }
  else
  {
    v4 = -2147418113;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v3,
        v2,
        -2147418113,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        106,
        "CBR(cObjects >= 1)");
  }
LABEL_33:
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  v10 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015a4c  push    rbp
0x180015a4e  push    rbx
0x180015a4f  push    rsi
0x180015a50  push    rdi
0x180015a51  lea     rbp, [rsp-3Fh]
0x180015a56  sub     rsp, 0D8h
0x180015a5d  mov     rax, cs:__security_cookie
0x180015a64  xor     rax, rsp
0x180015a67  mov     [rbp+57h+var_28], rax
0x180015a6b  mov     rdi, rcx
0x180015a6e  xor     esi, esi
0x180015a70  mov     [rbp+57h+var_A0], rsi
0x180015a74  mov     [rbp+57h+var_A8], rsi
0x180015a78  mov     [rbp+57h+var_B0], esi
0x180015a7b  xorps   xmm0, xmm0
0x180015a7e  xor     eax, eax
0x180015a80  movups  [rbp+57h+var_98], xmm0
0x180015a84  mov     [rbp+57h+var_88], rax
0x180015a88  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180015a8c  call    cs:__imp_VariantInit
0x180015a92  nop
0x180015a93  test    rdi, rdi
0x180015a96  jnz     short loc_180015AD2
0x180015a98  mov     ebx, 80070057h
0x180015a9d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015aa4  jz      loc_180015D32
0x180015aaa  lea     rax, aCprPichassisty; "CPR(piChassisType)"
0x180015ab1  mov     [rsp+0F0h+var_C8], rax
0x180015ab6  mov     dword ptr [rsp+0F0h+var_D0], 464h
0x180015abe  mov     r8d, ebx
0x180015ac1  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180015ac8  call    McTemplateU0dsqs_EventWriteTransfer
0x180015acd  jmp     loc_180015D32
0x180015ad2  mov     [rdi], esi
0x180015ad4  lea     rdx, aRootCimv2_0; "ROOT\\CIMV2"
0x180015adb  lea     rcx, [rbp+57h+var_48]
0x180015adf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015ae4  nop
0x180015ae5  lea     rdx, aSelectChassist; "select ChassisTypes from Win32_SystemEn"...
0x180015aec  lea     rcx, [rbp+57h+var_68]
0x180015af0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015af5  nop
0x180015af6  lea     r8, [rbp+57h+var_A0]
0x180015afa  lea     rdx, [rbp+57h+var_48]
0x180015afe  lea     rcx, [rbp+57h+var_68]
0x180015b02  call    ?ExecuteWmiQuery@DdcDeviceInfoHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAPEAUIEnumWbemClassObject@@@Z; DdcDeviceInfoHelper::ExecuteWmiQuery(std::wstring const &,std::wstring const &,IEnumWbemClassObject * *)
0x180015b07  mov     ebx, eax
0x180015b09  lea     rcx, [rbp+57h+var_68]
0x180015b0d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015b12  nop
0x180015b13  lea     rcx, [rbp+57h+var_48]
0x180015b17  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015b1c  test    ebx, ebx
0x180015b1e  jns     short loc_180015B46
0x180015b20  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015b27  jz      loc_180015D32
0x180015b2d  lea     rax, aChrExecutewmiq; "CHR(ExecuteWmiQuery(L\"select ChassisTy"...
0x180015b34  mov     [rsp+0F0h+var_C8], rax
0x180015b39  mov     dword ptr [rsp+0F0h+var_D0], 468h
0x180015b41  jmp     loc_180015ABE
0x180015b46  mov     rcx, [rbp+57h+var_A0]
0x180015b4a  mov     rax, [rcx]
0x180015b4d  lea     rdx, [rbp+57h+var_B0]
0x180015b51  mov     [rsp+0F0h+var_D0], rdx
0x180015b56  lea     r9, [rbp+57h+var_A8]
0x180015b5a  mov     edx, 1388h
0x180015b5f  mov     r8d, 1
0x180015b65  mov     rax, [rax+20h]
0x180015b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b6e  mov     ebx, eax
0x180015b70  test    eax, eax
0x180015b72  jns     short loc_180015B9A
0x180015b74  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015b7b  jz      loc_180015D32
0x180015b81  lea     rax, aChrPenumerator; "CHR(pEnumerator->Next(5000, 1, pEnclosu"...
0x180015b88  mov     [rsp+0F0h+var_C8], rax
0x180015b8d  mov     dword ptr [rsp+0F0h+var_D0], 469h
0x180015b95  jmp     loc_180015ABE
0x180015b9a  cmp     [rbp+57h+var_B0], 1
0x180015b9e  jnb     short loc_180015BCF
0x180015ba0  mov     r8d, 8000FFFFh
0x180015ba6  mov     ebx, r8d
0x180015ba9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015bb0  jz      loc_180015D32
0x180015bb6  lea     rax, aCbrCobjects1; "CBR(cObjects >= 1)"
0x180015bbd  mov     [rsp+0F0h+var_C8], rax
0x180015bc2  mov     dword ptr [rsp+0F0h+var_D0], 46Ah
0x180015bca  jmp     loc_180015AC1
0x180015bcf  mov     rcx, [rbp+57h+var_A8]
0x180015bd3  mov     rax, [rcx]
0x180015bd6  mov     [rsp+0F0h+var_C8], rsi
0x180015bdb  mov     [rsp+0F0h+var_D0], rsi
0x180015be0  lea     r9, [rbp+57h+var_98]
0x180015be4  xor     r8d, r8d
0x180015be7  lea     rdx, aChassistypes; "ChassisTypes"
0x180015bee  mov     rax, [rax+20h]
0x180015bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bf7  mov     ebx, eax
0x180015bf9  test    eax, eax
0x180015bfb  jns     short loc_180015C23
0x180015bfd  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015c04  jz      loc_180015D32
0x180015c0a  lea     rax, aChrPenclosurei; "CHR(pEnclosureInfo->Get(L\"ChassisTypes"...
0x180015c11  mov     [rsp+0F0h+var_C8], rax
0x180015c16  mov     dword ptr [rsp+0F0h+var_D0], 46Bh
0x180015c1e  jmp     loc_180015ABE
0x180015c23  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180015c27  call    cs:__imp_VariantClear
0x180015c2d  test    eax, eax
0x180015c2f  jns     short loc_180015C39
0x180015c31  mov     ecx, eax; int
0x180015c33  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180015c39  movups  xmm1, [rbp+57h+var_98]
0x180015c3d  movups  xmmword ptr [rbp+57h+pvarg], xmm1
0x180015c41  movsd   xmm0, [rbp+57h+var_88]
0x180015c46  movsd   qword ptr [rbp+57h+pvarg+10h], xmm0
0x180015c4b  mov     word ptr [rbp+57h+var_98], si
0x180015c4f  mov     ecx, 2003h
0x180015c54  movd    eax, xmm1
0x180015c58  cmp     ax, cx
0x180015c5b  jz      short loc_180015C8C
0x180015c5d  mov     r8d, 8000FFFFh
0x180015c63  mov     ebx, r8d
0x180015c66  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015c6d  jz      loc_180015D32
0x180015c73  lea     rax, aCbrChassistype_0; "CBR(chassisTypesVariant.vt == (VT_ARRAY"...
0x180015c7a  mov     [rsp+0F0h+var_C8], rax
0x180015c7f  mov     dword ptr [rsp+0F0h+var_D0], 46Fh
0x180015c87  jmp     loc_180015AC1
0x180015c8c  psrldq  xmm1, 8
0x180015c91  movq    rax, xmm1
0x180015c96  test    rax, rax
0x180015c99  jnz     short loc_180015CCA
0x180015c9b  mov     r8d, 8000FFFFh
0x180015ca1  mov     ebx, r8d
0x180015ca4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015cab  jz      loc_180015D32
0x180015cb1  lea     rax, aCbrChassistype_1; "CBR(chassisTypesVariant.parray != nullp"...
0x180015cb8  mov     [rsp+0F0h+var_C8], rax
0x180015cbd  mov     dword ptr [rsp+0F0h+var_D0], 470h
0x180015cc5  jmp     loc_180015AC1
0x180015cca  cmp     [rax], si
0x180015ccd  ja      short loc_180015CFA
0x180015ccf  mov     r8d, 8000FFFFh
0x180015cd5  mov     ebx, r8d
0x180015cd8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015cdf  jz      short loc_180015D32
0x180015ce1  lea     rax, aCbrChassistype; "CBR(chassisTypesVariant.parray->cDims >"...
0x180015ce8  mov     [rsp+0F0h+var_C8], rax
0x180015ced  mov     dword ptr [rsp+0F0h+var_D0], 471h
0x180015cf5  jmp     loc_180015AC1
0x180015cfa  mov     rax, [rax+10h]
0x180015cfe  test    rax, rax
0x180015d01  jnz     short loc_180015D2E
0x180015d03  mov     r8d, 8000FFFFh
0x180015d09  mov     ebx, r8d
0x180015d0c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015d13  jz      short loc_180015D32
0x180015d15  lea     rax, aCbrChassistype_2; "CBR(chassisTypesVariant.parray->pvData "...
0x180015d1c  mov     [rsp+0F0h+var_C8], rax
0x180015d21  mov     dword ptr [rsp+0F0h+var_D0], 472h
0x180015d29  jmp     loc_180015AC1
0x180015d2e  mov     eax, [rax]
0x180015d30  mov     [rdi], eax
0x180015d32  lea     rcx, [rbp+57h+pvarg]; this
0x180015d36  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180015d3b  nop
0x180015d3c  mov     rcx, [rbp+57h+var_A8]
0x180015d40  test    rcx, rcx
0x180015d43  jz      short loc_180015D56
0x180015d45  mov     [rbp+57h+var_A8], rsi
0x180015d49  mov     rax, [rcx]
0x180015d4c  mov     rax, [rax+10h]
0x180015d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d55  nop
0x180015d56  lea     rcx, [rbp+57h+var_A0]
0x180015d5a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015d5f  mov     eax, ebx
0x180015d61  mov     rcx, [rbp+57h+var_28]
0x180015d65  xor     rcx, rsp; StackCookie
0x180015d68  call    __security_check_cookie
0x180015d6d  add     rsp, 0D8h
0x180015d74  pop     rdi
0x180015d75  pop     rsi
0x180015d76  pop     rbx
0x180015d77  pop     rbp
0x180015d78  retn
```
