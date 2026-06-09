# PSUI::GetXMLSnapshot(void *,PSUI::_COMMONINFO *,IXMLDOMDocument2 * *,ushort *)

- ea: `0x18014ccdc`
- end: `0x18014cf4d`
- name: `?GetXMLSnapshot@PSUI@@YAJPEAXPEAU_COMMONINFO@1@PEAPEAUIXMLDOMDocument2@@PEAG@Z`
- size: `625`
- prototype: `__int64 __fastcall(PSUI *this, _QWORD *, LPVOID *, struct IXMLDOMDocument2 **)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18014bc20`
- `0x18014c370`
- `0x18014cfe0`

## callees

- `0x180003400`
- `0x180004558`
- `0x180107214`
- `0x18014ccdc`
- `0x18014e860`
- `0x180157800`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18014cedc`
- `KERNEL32!GetLastError` at `0x18014cedc`
- `OLEAUT32!__imp_VariantInit` at `0x18014cd2f`
- `OLEAUT32!__imp_VariantInit` at `0x18014cd41`
- `OLEAUT32!__imp_VariantInit` at `0x18014cd2f`
- `OLEAUT32!__imp_VariantInit` at `0x18014cd41`
- `OLEAUT32!__imp_VariantClear` at `0x18014cf1d`
- `OLEAUT32!__imp_VariantClear` at `0x18014cf1d`
- `ole32!CoCreateInstance` at `0x18014cd66`
- `ole32!CoCreateInstance` at `0x18014cd66`

## string_xrefs

- `0x18014ce7c`: `Fail to expand loBidiQueryFileName to full path name.\n`
- `0x18014ceeb`: `Failed to load XML file %d \n`
- `0x18014ce83`: `PSUI::GetXMLSnapshot`
- `0x18014cef2`: `PSUI::GetXMLSnapshot`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PSUI::GetXMLSnapshot(PSUI *this, _QWORD *a2, LPVOID *a3, struct IXMLDOMDocument2 **a4)
{
  LONGLONG v8; // rbx
  int Instance; // edi
  __int64 v10; // rax
  unsigned int v11; // ecx
  wchar_t *v12; // rsi
  void *v13; // rdx
  struct _devicemodeW *v14; // r8
  LPVOID v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  DWORD LastError; // eax
  __int16 v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v21[4]; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h]
  VARIANTARG v24; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[264]; // [rsp+80h] [rbp-80h] BYREF

  v23 = -2;
  v8 = 0;
  *(_QWORD *)v21 = 0;
  v20 = 0;
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
        "PSUI::GetXMLSnapshot",
        L"Fail to expand loBidiQueryFileName to full path name.\n");
    }
    else
    {
      Instance = PSUI::GenerateSnapshotFromDevmode(this, v13, v14, pszDest, v21);
      v8 = *(_QWORD *)v21;
      if ( Instance >= 0 )
      {
        if ( *(_QWORD *)v21 )
        {
          pvarg.vt = 13;
          pvarg.llVal = *(_QWORD *)v21;
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 8LL))(*(_QWORD *)v21);
        }
LABEL_11:
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a3 + 504LL))(*a3, 0);
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a3 + 544LL))(*a3, 0);
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a3 + 560LL))(*a3, 0);
        v15 = *a3;
        v16 = *(_QWORD *)*a3;
        if ( a4 )
        {
          v17 = (*(__int64 (__fastcall **)(LPVOID, struct IXMLDOMDocument2 **, __int16 *))(v16 + 520))(v15, a4, &v20);
        }
        else
        {
          v24 = pvarg;
          v17 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v16 + 464))(v15, &v24, &v20);
        }
        Instance = v17;
        if ( v17 < 0 || v20 != -1 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
          *a3 = 0;
          LastError = GetLastError();
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "PSUI::GetXMLSnapshot",
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
0x18014ccdc  push    rbp
0x18014ccde  push    rbx
0x18014ccdf  push    rsi
0x18014cce0  push    rdi
0x18014cce1  push    r12
0x18014cce3  push    r14
0x18014cce5  push    r15
0x18014cce7  lea     rbp, [rsp-1A0h]
0x18014ccef  sub     rsp, 2A0h
0x18014ccf6  mov     [rsp+2D0h+var_278], 0FFFFFFFFFFFFFFFEh
0x18014ccff  mov     rax, cs:__security_cookie
0x18014cd06  xor     rax, rsp
0x18014cd09  mov     [rbp+1D0h+var_40], rax
0x18014cd10  mov     r15, r9
0x18014cd13  mov     r14, r8
0x18014cd16  mov     rsi, rdx
0x18014cd19  mov     r12, rcx
0x18014cd1c  xor     ebx, ebx
0x18014cd1e  mov     qword ptr [rsp+2D0h+var_298], rbx
0x18014cd23  xor     eax, eax
0x18014cd25  mov     [rsp+2D0h+var_2A0], ax
0x18014cd2a  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x18014cd2f  call    cs:__imp_VariantInit
0x18014cd36  nop     dword ptr [rax+rax+00h]
0x18014cd3b  nop
0x18014cd3c  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x18014cd41  call    cs:__imp_VariantInit
0x18014cd48  nop     dword ptr [rax+rax+00h]
0x18014cd4d  mov     [rsp+2D0h+ppv], r14; ppv
0x18014cd52  lea     r9, IID_IXMLDOMDocument2; riid
0x18014cd59  xor     edx, edx; pUnkOuter
0x18014cd5b  lea     r8d, [rbx+1]; dwClsContext
0x18014cd5f  lea     rcx, CLSID_DOMDocument60; rclsid
0x18014cd66  call    cs:__imp_CoCreateInstance
0x18014cd6d  nop     dword ptr [rax+rax+00h]
0x18014cd72  mov     edi, eax
0x18014cd74  test    eax, eax
0x18014cd76  js      loc_18014CF18
0x18014cd7c  test    r15, r15
0x18014cd7f  jnz     loc_18014CE24
0x18014cd85  mov     edi, 80004005h
0x18014cd8a  mov     rax, [rsi+48h]
0x18014cd8e  mov     ecx, [rax+138h]
0x18014cd94  test    ecx, ecx
0x18014cd96  jz      short loc_18014CDA3
0x18014cd98  mov     esi, ecx
0x18014cd9a  add     rsi, [rax+140h]
0x18014cda1  jmp     short loc_18014CDA5
0x18014cda3  xor     esi, esi
0x18014cda5  test    rsi, rsi
0x18014cda8  jz      loc_18014CF18
0x18014cdae  xor     edx, edx; Val
0x18014cdb0  mov     r8d, 208h; Size
0x18014cdb6  lea     rcx, [rbp+1D0h+pszDest]; void *
0x18014cdba  call    memset_0
0x18014cdbf  mov     r9d, 104h; cchDest
0x18014cdc5  lea     r8, [rbp+1D0h+pszDest]; pszDest
0x18014cdc9  mov     rdx, rsi; String
0x18014cdcc  mov     rcx, r12; void *
0x18014cdcf  call    GetFullPathFromFilename
0x18014cdd4  test    eax, eax
0x18014cdd6  js      loc_18014CE7C
0x18014cddc  lea     rax, [rsp+2D0h+var_298]
0x18014cde1  mov     [rsp+2D0h+ppv], rax; unsigned __int16 *
0x18014cde6  lea     r9, [rbp+1D0h+pszDest]; unsigned int
0x18014cdea  mov     rcx, r12; this
0x18014cded  call    ?GenerateSnapshotFromDevmode@PSUI@@YAJPEAXPEAU_devicemodeW@@KPEBGPEAPEAUIStream@@@Z; PSUI::GenerateSnapshotFromDevmode(void *,_devicemodeW *,ulong,ushort const *,IStream * *)
0x18014cdf2  mov     edi, eax
0x18014cdf4  mov     rbx, qword ptr [rsp+2D0h+var_298]
0x18014cdf9  test    eax, eax
0x18014cdfb  js      loc_18014CF03
0x18014ce01  test    rbx, rbx
0x18014ce04  jz      short loc_18014CE24
0x18014ce06  mov     eax, 0Dh
0x18014ce0b  mov     word ptr [rsp+2D0h+pvarg], ax
0x18014ce10  mov     qword ptr [rsp+2D0h+pvarg+8], rbx
0x18014ce15  mov     rax, [rbx]
0x18014ce18  mov     rcx, rbx
0x18014ce1b  mov     rax, [rax+8]
0x18014ce1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ce24  mov     rcx, [r14]
0x18014ce27  mov     rax, [rcx]
0x18014ce2a  xor     edx, edx
0x18014ce2c  mov     rax, [rax+1F8h]
0x18014ce33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ce38  mov     rcx, [r14]
0x18014ce3b  mov     rax, [rcx]
0x18014ce3e  xor     edx, edx
0x18014ce40  mov     rax, [rax+220h]
0x18014ce47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ce4c  mov     rcx, [r14]
0x18014ce4f  mov     rax, [rcx]
0x18014ce52  xor     edx, edx
0x18014ce54  mov     rax, [rax+230h]
0x18014ce5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ce60  mov     rcx, [r14]
0x18014ce63  mov     rax, [rcx]
0x18014ce66  lea     r8, [rsp+2D0h+var_2A0]
0x18014ce6b  test    r15, r15
0x18014ce6e  jz      short loc_18014CE91
0x18014ce70  mov     rdx, r15
0x18014ce73  mov     rax, [rax+208h]
0x18014ce7a  jmp     short loc_18014CEB3
0x18014ce7c  lea     rdx, aFailToExpandLo; "Fail to expand loBidiQueryFileName to f"...
0x18014ce83  lea     rcx, aPsuiGetxmlsnap; "PSUI::GetXMLSnapshot"
0x18014ce8a  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18014ce8f  jmp     short loc_18014CF03
0x18014ce91  movups  xmm0, xmmword ptr [rsp+2D0h+pvarg]
0x18014ce96  movaps  [rsp+2D0h+var_270], xmm0
0x18014ce9b  movsd   xmm1, qword ptr [rsp+2D0h+pvarg+10h]
0x18014cea1  movsd   [rsp+2D0h+var_260], xmm1
0x18014cea7  lea     rdx, [rsp+2D0h+var_270]
0x18014ceac  mov     rax, [rax+1D0h]
0x18014ceb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ceb8  mov     edi, eax
0x18014ceba  test    eax, eax
0x18014cebc  js      short loc_18014CEC6
0x18014cebe  cmp     [rsp+2D0h+var_2A0], 0FFFFh
0x18014cec4  jz      short loc_18014CF03
0x18014cec6  mov     rcx, [r14]
0x18014cec9  mov     rax, [rcx]
0x18014cecc  mov     rax, [rax+10h]
0x18014ced0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ced5  mov     qword ptr [r14], 0
0x18014cedc  call    cs:__imp_GetLastError
0x18014cee3  nop     dword ptr [rax+rax+00h]
0x18014cee8  mov     r8d, eax
0x18014ceeb  lea     rdx, aFailedToLoadXm; "Failed to load XML file %d \n"
0x18014cef2  lea     rcx, aPsuiGetxmlsnap; "PSUI::GetXMLSnapshot"
0x18014cef9  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18014cefe  mov     edi, 80004005h
0x18014cf03  test    rbx, rbx
0x18014cf06  jz      short loc_18014CF18
0x18014cf08  mov     rax, [rbx]
0x18014cf0b  mov     rcx, rbx
0x18014cf0e  mov     rax, [rax+10h]
0x18014cf12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014cf17  nop
0x18014cf18  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x18014cf1d  call    cs:__imp_VariantClear
0x18014cf24  nop     dword ptr [rax+rax+00h]
0x18014cf29  mov     eax, edi
0x18014cf2b  mov     rcx, [rbp+1D0h+var_40]
0x18014cf32  xor     rcx, rsp; StackCookie
0x18014cf35  call    __security_check_cookie
0x18014cf3a  add     rsp, 2A0h
0x18014cf41  pop     r15
0x18014cf43  pop     r14
0x18014cf45  pop     r12
0x18014cf47  pop     rdi
0x18014cf48  pop     rsi
0x18014cf49  pop     rbx
0x18014cf4a  pop     rbp
0x18014cf4b  retn
```
