# CCbsTiSession::CreateWindowsUpdatePackage(uint,wchar_t const *,_GUID,uint,_CbsPackageType,wchar_t const *,wchar_t const *,uint,tagCbsPackageDecryptionData * const,tagCBS_PACKAGE_ENCRYPTION_ENUM,IUnknown * *)

- ea: `0x14000f484`
- end: `0x14000f60d`
- name: `?CreateWindowsUpdatePackage@CCbsTiSession@@UEAAJIPEB_WU_GUID@@IW4_CbsPackageType@@00IQEAUtagCbsPackageDecryptionData@@W4tagCBS_PACKAGE_ENCRYPTION_ENUM@@PEAPEAUIUnknown@@@Z`
- size: `393`
- prototype: `__int64 __fastcall(__int64, unsigned int, const wchar_t *, const IID *, int, unsigned int, __int64, __int64, int, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14000f470`

## callees

- `0x1400023e0`
- `0x14000f238`
- `0x14000f484`
- `0x140017658`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000f5e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000f5e1`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x14000f508`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x14000f508`

## string_xrefs

- `0x14000f519`: `Failed to convert updateID`
- `0x14000f52f`: `WU creates the package, AppID:%S, UpdateID:%S, revision: %u`
- `0x14000f5bb`: `Failed to create package.`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::CreateWindowsUpdatePackage(
        __int64 a1,
        unsigned int a2,
        const wchar_t *a3,
        const IID *a4,
        int a5,
        unsigned int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        __int64 a10,
        int a11,
        __int64 a12)
{
  unsigned int v16; // ebx
  const char *v17; // r9
  __int64 v18; // rdx
  HRESULT v19; // eax
  int v20; // eax
  IID v22; // [rsp+70h] [rbp-68h] BYREF
  LPOLESTR lpsz; // [rsp+80h] [rbp-58h] BYREF

  lpsz = 0;
  if ( !a12 )
  {
    v16 = -2147467261;
    v17 = "Invalid argument: ppPackage.";
    v18 = 2147500035LL;
LABEL_7:
    CBSWdsLogLight(0x4000000, v18, 1, v17);
    goto LABEL_8;
  }
  v19 = StringFromCLSID(a4, &lpsz);
  v16 = v19;
  if ( v19 < 0 )
  {
    CBSWdsLogLight(0x4000000, (unsigned int)v19, 1, "Failed to convert updateID");
    goto LABEL_8;
  }
  CBSWdsLogLight(0x4000000, 0, 0, "WU creates the package, AppID:%S, UpdateID:%S, revision: %u", a3, lpsz, a5);
  v22 = *a4;
  v20 = CCbsTiSession::CreatePublicCbsPackage(a1 - 256, a2, a6, a7, a8, a3, &v22, a5, a9, a10, a11, a12);
  v16 = v20;
  if ( v20 < 0 )
  {
    v17 = "Failed to create package.";
    v18 = (unsigned int)v20;
    goto LABEL_7;
  }
LABEL_8:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return v16;
}

```

## disassembly

```asm
0x14000f484  mov     r11, rsp
0x14000f487  push    rbx
0x14000f488  push    rbp
0x14000f489  push    rsi
0x14000f48a  push    rdi
0x14000f48b  push    r12
0x14000f48d  push    r13
0x14000f48f  push    r14
0x14000f491  push    r15
0x14000f493  sub     rsp, 98h
0x14000f49a  mov     rax, cs:__security_cookie
0x14000f4a1  xor     rax, rsp
0x14000f4a4  mov     [rsp+0D8h+var_50], rax
0x14000f4ac  mov     rax, [rsp+0D8h+arg_48]
0x14000f4b4  mov     rdi, r9
0x14000f4b7  mov     r12, [rsp+0D8h+arg_30]
0x14000f4bf  mov     rbp, r8
0x14000f4c2  mov     r13, [rsp+0D8h+arg_38]
0x14000f4ca  mov     r15d, edx
0x14000f4cd  mov     rsi, [rsp+0D8h+arg_58]
0x14000f4d5  mov     r14, rcx
0x14000f4d8  mov     [rsp+0D8h+var_78], rax
0x14000f4dd  mov     qword ptr [r11-58h], 0
0x14000f4e5  test    rsi, rsi
0x14000f4e8  jnz     short loc_14000F4FD
0x14000f4ea  mov     ebx, 80004003h
0x14000f4ef  lea     r9, aInvalidArgumen_26; "Invalid argument: ppPackage."
0x14000f4f6  mov     edx, ebx
0x14000f4f8  jmp     loc_14000F5C4
0x14000f4fd  lea     rdx, [rsp+0D8h+lpsz]; lplpsz
0x14000f505  mov     rcx, rdi; rclsid
0x14000f508  call    cs:__imp_StringFromCLSID
0x14000f50e  mov     ebx, eax
0x14000f510  mov     ecx, 4000000h
0x14000f515  test    eax, eax
0x14000f517  jns     short loc_14000F527
0x14000f519  lea     r9, aFailedToConver; "Failed to convert updateID"
0x14000f520  mov     edx, eax
0x14000f522  jmp     loc_14000F5C9
0x14000f527  mov     rax, [rsp+0D8h+lpsz]
0x14000f52f  lea     r9, aWuCreatesThePa; "WU creates the package, AppID:%S, Updat"...
0x14000f536  mov     ebx, [rsp+0D8h+arg_20]
0x14000f53d  xor     r8d, r8d
0x14000f540  mov     dword ptr [rsp+0D8h+var_A8], ebx
0x14000f544  xor     edx, edx
0x14000f546  mov     [rsp+0D8h+var_B0], rax
0x14000f54b  mov     [rsp+0D8h+var_B8], rbp
0x14000f550  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000f555  mov     eax, [rsp+0D8h+arg_50]
0x14000f55c  lea     rcx, [r14-100h]
0x14000f563  movups  xmm0, xmmword ptr [rdi]
0x14000f566  mov     r8d, [rsp+0D8h+arg_28]
0x14000f56e  mov     r9, r12
0x14000f571  mov     [rsp+0D8h+var_80], rsi
0x14000f576  mov     edx, r15d
0x14000f579  mov     [rsp+0D8h+var_88], eax
0x14000f57d  mov     rax, [rsp+0D8h+var_78]
0x14000f582  mov     [rsp+0D8h+var_90], rax
0x14000f587  mov     eax, [rsp+0D8h+arg_40]
0x14000f58e  mov     [rsp+0D8h+var_98], eax
0x14000f592  lea     rax, [rsp+0D8h+var_68]
0x14000f597  mov     [rsp+0D8h+var_A0], ebx
0x14000f59b  mov     [rsp+0D8h+var_A8], rax
0x14000f5a0  mov     [rsp+0D8h+var_B0], rbp
0x14000f5a5  mov     [rsp+0D8h+var_B8], r13
0x14000f5aa  movdqu  [rsp+0D8h+var_68], xmm0
0x14000f5b0  call    ?CreatePublicCbsPackage@CCbsTiSession@@QEAAJIW4_CbsPackageType@@PEB_W11U_GUID@@IIQEAUtagCbsPackageDecryptionData@@W4tagCBS_PACKAGE_ENCRYPTION_ENUM@@PEAPEAUIUnknown@@@Z; CCbsTiSession::CreatePublicCbsPackage(uint,_CbsPackageType,wchar_t const *,wchar_t const *,wchar_t const *,_GUID,uint,uint,tagCbsPackageDecryptionData * const,tagCBS_PACKAGE_ENCRYPTION_ENUM,IUnknown * *)
0x14000f5b5  mov     ebx, eax
0x14000f5b7  test    eax, eax
0x14000f5b9  jns     short loc_14000F5D4
0x14000f5bb  lea     r9, aFailedToCreate_7; "Failed to create package."
0x14000f5c2  mov     edx, eax
0x14000f5c4  mov     ecx, 4000000h
0x14000f5c9  mov     r8d, 1
0x14000f5cf  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000f5d4  mov     rcx, [rsp+0D8h+lpsz]; pv
0x14000f5dc  test    rcx, rcx
0x14000f5df  jz      short loc_14000F5E7
0x14000f5e1  call    cs:__imp_CoTaskMemFree
0x14000f5e7  mov     eax, ebx
0x14000f5e9  mov     rcx, [rsp+0D8h+var_50]
0x14000f5f1  xor     rcx, rsp; StackCookie
0x14000f5f4  call    __security_check_cookie
0x14000f5f9  add     rsp, 98h
0x14000f600  pop     r15
0x14000f602  pop     r14
0x14000f604  pop     r13
0x14000f606  pop     r12
0x14000f608  pop     rdi
0x14000f609  pop     rsi
0x14000f60a  pop     rbp
0x14000f60b  pop     rbx
0x14000f60c  retn
```
