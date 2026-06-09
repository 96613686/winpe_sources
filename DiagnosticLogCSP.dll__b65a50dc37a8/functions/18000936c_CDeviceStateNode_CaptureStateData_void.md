# CDeviceStateNode::CaptureStateData(void)

- ea: `0x18000936c`
- end: `0x1800094c1`
- name: `?CaptureStateData@CDeviceStateNode@@KAJXZ`
- size: `341`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800097e0`

## callees

- `0x1800011ac`
- `0x180001b90`
- `0x18000936c`
- `0x180010a7c`
- `0x180011670`

## import_xrefs

- `MdmDiagnostics!__imp_?CreateMdmEnterpriseDiagnosticReport@@YAJPEBG@Z` at `0x180009424`
- `MdmDiagnostics!__imp_?CreateMdmEnterpriseDiagnosticReport@@YAJPEBG@Z` at `0x180009424`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800093c2`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800093c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000947a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000948e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000947a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000948e`

## string_xrefs

- `0x1800093f7`: `MdmConfiguration`
- `0x1800093d5`: `OSData\SOFTWARE\Microsoft\DiagnosticLogCSP\DeviceStateData\MdmConfiguration`
- `0x1800093ce`: `SOFTWARE\Microsoft\DiagnosticLogCSP\DeviceStateData\MdmConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 CDeviceStateNode::CaptureStateData(void)
{
  unsigned __int16 *v0; // rdi
  char IsStateSeparationEnabled; // al
  const unsigned __int16 *v2; // r8
  int v3; // ecx
  int Key; // ebx
  int v5; // r8d
  int v6; // r9d
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v9; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey[3]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v11[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v12[1032]; // [rsp+70h] [rbp-90h] BYREF

  v12[0] = 0;
  v0 = 0;
  v11[1] = 0;
  v11[2] = 0;
  memset(hKey, 0, sizeof(hKey));
  v11[0] = -2147483646;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v2 = L"OSData\\SOFTWARE\\Microsoft\\DiagnosticLogCSP\\DeviceStateData\\MdmConfiguration";
  if ( !IsStateSeparationEnabled )
    v2 = L"SOFTWARE\\Microsoft\\DiagnosticLogCSP\\DeviceStateData\\MdmConfiguration";
  Key = CRegUtils::CreateKey((struct ATL::CRegKey *)v11, (struct ATL::CRegKey *)hKey, v2);
  if ( Key >= 0 )
  {
    Key = CLogFileMgr::Initialize(v12, 2, L"MdmConfiguration");
    if ( Key >= 0 )
    {
      if ( v12[0] )
      {
        v0 = v12;
        Key = CreateMdmEnterpriseDiagnosticReport(v12);
      }
      else
      {
        v0 = 0;
        Key = -2147467259;
      }
    }
  }
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v8 = Key;
    v9 = v0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)&unk_180040C28,
      v5,
      v6,
      (__int64)&v9,
      (__int64)&v8);
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  RegCloseKey(HKEY_LOCAL_MACHINE);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x18000936c  mov     [rsp-8+arg_0], rbx
0x180009371  mov     [rsp-8+arg_8], rdi
0x180009376  push    rbp
0x180009377  lea     rbp, [rsp-790h]
0x18000937f  sub     rsp, 890h
0x180009386  mov     rax, cs:__security_cookie
0x18000938d  xor     rax, rsp
0x180009390  mov     [rbp+790h+var_10], rax
0x180009397  xor     eax, eax
0x180009399  mov     [rsp+890h+var_820], ax
0x18000939e  xor     edi, edi
0x1800093a0  mov     [rsp+890h+var_830], rax
0x1800093a5  mov     [rsp+890h+var_828], rax
0x1800093aa  mov     [rsp+890h+hKey], rdi
0x1800093af  mov     [rsp+890h+var_848], rdi
0x1800093b4  mov     [rsp+890h+var_840], rdi
0x1800093b9  mov     [rsp+890h+var_838], 0FFFFFFFF80000002h
0x1800093c2  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800093c9  nop     dword ptr [rax+rax+00h]
0x1800093ce  lea     rcx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\DiagnosticLogCSP\\"...
0x1800093d5  lea     r8, aOsdataSoftware_3; "OSData\\SOFTWARE\\Microsoft\\Diagnostic"...
0x1800093dc  test    al, al
0x1800093de  cmovz   r8, rcx; unsigned __int16 *
0x1800093e2  lea     rdx, [rsp+890h+hKey]; struct ATL::CRegKey *
0x1800093e7  lea     rcx, [rsp+890h+var_838]; struct ATL::CRegKey *
0x1800093ec  call    ?CreateKey@CRegUtils@@SAJAEAVCRegKey@ATL@@0PEBG@Z; CRegUtils::CreateKey(ATL::CRegKey &,ATL::CRegKey &,ushort const *)
0x1800093f1  mov     ebx, eax
0x1800093f3  test    eax, eax
0x1800093f5  js      short loc_18000943B
0x1800093f7  lea     r8, aMdmconfigurati; "MdmConfiguration"
0x1800093fe  lea     edx, [rdi+2]
0x180009401  lea     rcx, [rsp+890h+var_820]
0x180009406  call    ?Initialize@CLogFileMgr@@QEAAJW4LogFileType@@PEBG@Z; CLogFileMgr::Initialize(LogFileType,ushort const *)
0x18000940b  mov     ebx, eax
0x18000940d  test    eax, eax
0x18000940f  js      short loc_18000943B
0x180009411  xor     eax, eax
0x180009413  cmp     ax, [rsp+890h+var_820]
0x180009418  jz      short loc_180009434
0x18000941a  lea     rdi, [rsp+890h+var_820]
0x18000941f  lea     rcx, [rsp+890h+var_820]
0x180009424  call    cs:__imp_?CreateMdmEnterpriseDiagnosticReport@@YAJPEBG@Z; CreateMdmEnterpriseDiagnosticReport(ushort const *)
0x18000942b  nop     dword ptr [rax+rax+00h]
0x180009430  mov     ebx, eax
0x180009432  jmp     short loc_18000943B
0x180009434  xor     edi, edi
0x180009436  mov     ebx, 80004005h
0x18000943b  mov     eax, cs:dword_18004AE90
0x180009441  cmp     eax, 5
0x180009444  jbe     short loc_180009470
0x180009446  mov     [rsp+890h+var_860], ebx
0x18000944a  mov     [rsp+890h+var_858], rdi
0x18000944f  lea     rax, [rsp+890h+var_860]
0x180009454  mov     [rsp+890h+var_868], rax
0x180009459  lea     rax, [rsp+890h+var_858]
0x18000945e  mov     [rsp+890h+var_870], rax
0x180009463  lea     rdx, unk_180040C28
0x18000946a  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000946f  nop
0x180009470  mov     rcx, [rsp+890h+hKey]; hKey
0x180009475  test    rcx, rcx
0x180009478  jz      short loc_180009487
0x18000947a  call    cs:__imp_RegCloseKey
0x180009481  nop     dword ptr [rax+rax+00h]
0x180009486  nop
0x180009487  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000948e  call    cs:__imp_RegCloseKey
0x180009495  nop     dword ptr [rax+rax+00h]
0x18000949a  mov     eax, ebx
0x18000949c  mov     rcx, [rbp+790h+var_10]
0x1800094a3  xor     rcx, rsp; StackCookie
0x1800094a6  call    __security_check_cookie
0x1800094ab  lea     r11, [rsp+890h+var_s0]
0x1800094b3  mov     rbx, [r11+10h]
0x1800094b7  mov     rdi, [r11+18h]
0x1800094bb  mov     rsp, r11
0x1800094be  pop     rbp
0x1800094bf  retn
```
