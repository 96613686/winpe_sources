# UniDrvUI::GetXMLSnapshot(void *,UniDrvUI::_COMMONINFO *,IXMLDOMDocument2 * *,ushort *)

- ea: `0x180128a94`
- end: `0x180128d0a`
- name: `?GetXMLSnapshot@UniDrvUI@@YAJPEAXPEAU_COMMONINFO@1@PEAPEAUIXMLDOMDocument2@@PEAG@Z`
- size: `630`
- prototype: `__int64 __fastcall(UniDrvUI *this, _QWORD *, LPVOID *, struct IXMLDOMDocument2 **)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801276c8`
- `0x180127fc8`
- `0x180128d9c`

## callees

- `0x180003400`
- `0x180004558`
- `0x180107214`
- `0x180128a94`
- `0x18012acb4`
- `0x180157800`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180128c99`
- `KERNEL32!GetLastError` at `0x180128c99`
- `OLEAUT32!__imp_VariantInit` at `0x180128ae7`
- `OLEAUT32!__imp_VariantInit` at `0x180128af9`
- `OLEAUT32!__imp_VariantInit` at `0x180128ae7`
- `OLEAUT32!__imp_VariantInit` at `0x180128af9`
- `OLEAUT32!__imp_VariantClear` at `0x180128cda`
- `OLEAUT32!__imp_VariantClear` at `0x180128cda`
- `ole32!CoCreateInstance` at `0x180128b1e`
- `ole32!CoCreateInstance` at `0x180128b1e`

## string_xrefs

- `0x180128c39`: `Fail to expand loBidiQueryFileName to full path name.\n`
- `0x180128ca8`: `Failed to load XML file %d \n`
- `0x180128c40`: `UniDrvUI::GetXMLSnapshot`
- `0x180128caf`: `UniDrvUI::GetXMLSnapshot`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UniDrvUI::GetXMLSnapshot(UniDrvUI *this, _QWORD *a2, LPVOID *a3, struct IXMLDOMDocument2 **a4)
{
  LONGLONG v8; // rbx
  int Instance; // edi
  __int64 v10; // rax
  unsigned int v11; // ecx
  wchar_t *v12; // rsi
  LPVOID v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  DWORD LastError; // eax
  __int16 v18; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v19[4]; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h]
  VARIANTARG v22; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[264]; // [rsp+80h] [rbp-80h] BYREF

  v21 = -2;
  v8 = 0;
  *(_QWORD *)v19 = 0;
  v18 = 0;
  VariantInit(&pvarg);
  VariantInit(&pvarg);
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, a3);
  if ( Instance < 0 )
    goto LABEL_20;
  if ( a4 )
    goto LABEL_11;
  Instance = -2147467259;
  v10 = a2[9];
  v11 = *(_DWORD *)(v10 + 312);
  if ( v11 )
    v12 = (wchar_t *)(*(_QWORD *)(v10 + 320) + v11);
  else
    v12 = 0;
  if ( v12 )
  {
    memset_0(pszDest, 0, 0x208u);
    if ( (int)GetFullPathFromFilename(this, v12, pszDest, 0x104u) < 0 )
    {
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
        "UniDrvUI::GetXMLSnapshot",
        L"Fail to expand loBidiQueryFileName to full path name.\n");
    }
    else
    {
      Instance = UniDrvUI::GenerateSnapshotFromDevmode(this, 0, 0, pszDest, v19);
      v8 = *(_QWORD *)v19;
      if ( Instance >= 0 )
      {
        if ( *(_QWORD *)v19 )
        {
          pvarg.vt = 13;
          pvarg.llVal = *(_QWORD *)v19;
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v19 + 8LL))(*(_QWORD *)v19);
        }
LABEL_11:
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a3 + 504LL))(*a3, 0);
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a3 + 544LL))(*a3, 0);
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a3 + 560LL))(*a3, 0);
        v13 = *a3;
        v14 = *(_QWORD *)*a3;
        if ( a4 )
        {
          v15 = (*(__int64 (__fastcall **)(LPVOID, struct IXMLDOMDocument2 **, __int16 *))(v14 + 520))(v13, a4, &v18);
        }
        else
        {
          v22 = pvarg;
          v15 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v14 + 464))(v13, &v22, &v18);
        }
        Instance = v15;
        if ( v15 < 0 || v18 != -1 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
          *a3 = 0;
          LastError = GetLastError();
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "UniDrvUI::GetXMLSnapshot",
            L"Failed to load XML file %d \n",
            LastError);
          Instance = -2147467259;
        }
      }
    }
    if ( v8 )
      (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v8 + 16LL))(v8);
  }
LABEL_20:
  VariantClear(&pvarg);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180128a94  push    rbp
0x180128a96  push    rbx
0x180128a97  push    rsi
0x180128a98  push    rdi
0x180128a99  push    r12
0x180128a9b  push    r14
0x180128a9d  push    r15
0x180128a9f  lea     rbp, [rsp-1A0h]
0x180128aa7  sub     rsp, 2A0h
0x180128aae  mov     [rsp+2D0h+var_278], 0FFFFFFFFFFFFFFFEh
0x180128ab7  mov     rax, cs:__security_cookie
0x180128abe  xor     rax, rsp
0x180128ac1  mov     [rbp+1D0h+var_40], rax
0x180128ac8  mov     r15, r9
0x180128acb  mov     r14, r8
0x180128ace  mov     rsi, rdx
0x180128ad1  mov     r12, rcx
0x180128ad4  xor     ebx, ebx
0x180128ad6  mov     qword ptr [rsp+2D0h+var_298], rbx
0x180128adb  xor     eax, eax
0x180128add  mov     [rsp+2D0h+var_2A0], ax
0x180128ae2  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x180128ae7  call    cs:__imp_VariantInit
0x180128aee  nop     dword ptr [rax+rax+00h]
0x180128af3  nop
0x180128af4  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x180128af9  call    cs:__imp_VariantInit
0x180128b00  nop     dword ptr [rax+rax+00h]
0x180128b05  mov     [rsp+2D0h+ppv], r14; ppv
0x180128b0a  lea     r9, IID_IXMLDOMDocument2; riid
0x180128b11  xor     edx, edx; pUnkOuter
0x180128b13  lea     r8d, [rbx+1]; dwClsContext
0x180128b17  lea     rcx, CLSID_DOMDocument60; rclsid
0x180128b1e  call    cs:__imp_CoCreateInstance
0x180128b25  nop     dword ptr [rax+rax+00h]
0x180128b2a  mov     edi, eax
0x180128b2c  test    eax, eax
0x180128b2e  js      loc_180128CD5
0x180128b34  test    r15, r15
0x180128b37  jnz     loc_180128BE1
0x180128b3d  mov     edi, 80004005h
0x180128b42  mov     rax, [rsi+48h]
0x180128b46  mov     ecx, [rax+138h]
0x180128b4c  test    ecx, ecx
0x180128b4e  jz      short loc_180128B5B
0x180128b50  mov     esi, ecx
0x180128b52  add     rsi, [rax+140h]
0x180128b59  jmp     short loc_180128B5D
0x180128b5b  xor     esi, esi
0x180128b5d  test    rsi, rsi
0x180128b60  jz      loc_180128CD5
0x180128b66  xor     edx, edx; Val
0x180128b68  mov     r8d, 208h; Size
0x180128b6e  lea     rcx, [rbp+1D0h+pszDest]; void *
0x180128b72  call    memset_0
0x180128b77  mov     r9d, 104h; cchDest
0x180128b7d  lea     r8, [rbp+1D0h+pszDest]; pszDest
0x180128b81  mov     rdx, rsi; String
0x180128b84  mov     rcx, r12; void *
0x180128b87  call    GetFullPathFromFilename
0x180128b8c  test    eax, eax
0x180128b8e  js      loc_180128C39
0x180128b94  lea     rax, [rsp+2D0h+var_298]
0x180128b99  mov     [rsp+2D0h+ppv], rax; unsigned __int16 *
0x180128b9e  lea     r9, [rbp+1D0h+pszDest]; unsigned int
0x180128ba2  xor     r8d, r8d; struct _devicemodeW *
0x180128ba5  xor     edx, edx; void *
0x180128ba7  mov     rcx, r12; this
0x180128baa  call    ?GenerateSnapshotFromDevmode@UniDrvUI@@YAJPEAXPEAU_devicemodeW@@KPEBGPEAPEAUIStream@@@Z; UniDrvUI::GenerateSnapshotFromDevmode(void *,_devicemodeW *,ulong,ushort const *,IStream * *)
0x180128baf  mov     edi, eax
0x180128bb1  mov     rbx, qword ptr [rsp+2D0h+var_298]
0x180128bb6  test    eax, eax
0x180128bb8  js      loc_180128CC0
0x180128bbe  test    rbx, rbx
0x180128bc1  jz      short loc_180128BE1
0x180128bc3  mov     eax, 0Dh
0x180128bc8  mov     word ptr [rsp+2D0h+pvarg], ax
0x180128bcd  mov     qword ptr [rsp+2D0h+pvarg+8], rbx
0x180128bd2  mov     rax, [rbx]
0x180128bd5  mov     rcx, rbx
0x180128bd8  mov     rax, [rax+8]
0x180128bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128be1  mov     rcx, [r14]
0x180128be4  mov     rax, [rcx]
0x180128be7  xor     edx, edx
0x180128be9  mov     rax, [rax+1F8h]
0x180128bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128bf5  mov     rcx, [r14]
0x180128bf8  mov     rax, [rcx]
0x180128bfb  xor     edx, edx
0x180128bfd  mov     rax, [rax+220h]
0x180128c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128c09  mov     rcx, [r14]
0x180128c0c  mov     rax, [rcx]
0x180128c0f  xor     edx, edx
0x180128c11  mov     rax, [rax+230h]
0x180128c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128c1d  mov     rcx, [r14]
0x180128c20  mov     rax, [rcx]
0x180128c23  lea     r8, [rsp+2D0h+var_2A0]
0x180128c28  test    r15, r15
0x180128c2b  jz      short loc_180128C4E
0x180128c2d  mov     rdx, r15
0x180128c30  mov     rax, [rax+208h]
0x180128c37  jmp     short loc_180128C70
0x180128c39  lea     rdx, aFailToExpandLo; "Fail to expand loBidiQueryFileName to f"...
0x180128c40  lea     rcx, aUnidrvuiGetxml; "UniDrvUI::GetXMLSnapshot"
0x180128c47  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180128c4c  jmp     short loc_180128CC0
0x180128c4e  movups  xmm0, xmmword ptr [rsp+2D0h+pvarg]
0x180128c53  movaps  [rsp+2D0h+var_270], xmm0
0x180128c58  movsd   xmm1, qword ptr [rsp+2D0h+pvarg+10h]
0x180128c5e  movsd   [rsp+2D0h+var_260], xmm1
0x180128c64  lea     rdx, [rsp+2D0h+var_270]
0x180128c69  mov     rax, [rax+1D0h]
0x180128c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128c75  mov     edi, eax
0x180128c77  test    eax, eax
0x180128c79  js      short loc_180128C83
0x180128c7b  cmp     [rsp+2D0h+var_2A0], 0FFFFh
0x180128c81  jz      short loc_180128CC0
0x180128c83  mov     rcx, [r14]
0x180128c86  mov     rax, [rcx]
0x180128c89  mov     rax, [rax+10h]
0x180128c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128c92  mov     qword ptr [r14], 0
0x180128c99  call    cs:__imp_GetLastError
0x180128ca0  nop     dword ptr [rax+rax+00h]
0x180128ca5  mov     r8d, eax
0x180128ca8  lea     rdx, aFailedToLoadXm; "Failed to load XML file %d \n"
0x180128caf  lea     rcx, aUnidrvuiGetxml; "UniDrvUI::GetXMLSnapshot"
0x180128cb6  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180128cbb  mov     edi, 80004005h
0x180128cc0  test    rbx, rbx
0x180128cc3  jz      short loc_180128CD5
0x180128cc5  mov     rax, [rbx]
0x180128cc8  mov     rcx, rbx
0x180128ccb  mov     rax, [rax+10h]
0x180128ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128cd4  nop
0x180128cd5  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x180128cda  call    cs:__imp_VariantClear
0x180128ce1  nop     dword ptr [rax+rax+00h]
0x180128ce6  mov     eax, edi
0x180128ce8  mov     rcx, [rbp+1D0h+var_40]
0x180128cef  xor     rcx, rsp; StackCookie
0x180128cf2  call    __security_check_cookie
0x180128cf7  add     rsp, 2A0h
0x180128cfe  pop     r15
0x180128d00  pop     r14
0x180128d02  pop     r12
0x180128d04  pop     rdi
0x180128d05  pop     rsi
0x180128d06  pop     rbx
0x180128d07  pop     rbp
0x180128d08  retn
```
