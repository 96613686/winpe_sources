# CDeviceStateNode::CaptureStateData(void)

- ea: `0x18000911c`
- end: `0x180009258`
- name: `?CaptureStateData@CDeviceStateNode@@KAJXZ`
- size: `316`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009560`

## callees

- `0x1800011a4`
- `0x180001b60`
- `0x18000911c`
- `0x180010230`
- `0x180010de0`

## import_xrefs

- `MdmDiagnostics!__imp_?CreateMdmEnterpriseDiagnosticReport@@YAJPEBG@Z` at `0x1800091ce`
- `MdmDiagnostics!__imp_?CreateMdmEnterpriseDiagnosticReport@@YAJPEBG@Z` at `0x1800091ce`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180009172`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180009172`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000921e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000922c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000921e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000922c`

## string_xrefs

- `0x1800091a1`: `MdmConfiguration`
- `0x18000917f`: `OSData\SOFTWARE\Microsoft\DiagnosticLogCSP\DeviceStateData\MdmConfiguration`
- `0x180009178`: `SOFTWARE\Microsoft\DiagnosticLogCSP\DeviceStateData\MdmConfiguration`

## pseudocode

```c
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
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v8 = Key;
    v9 = v0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)&unk_18003EC28,
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
0x18000911c  mov     [rsp-8+arg_0], rbx
0x180009121  mov     [rsp-8+arg_8], rdi
0x180009126  push    rbp
0x180009127  lea     rbp, [rsp-790h]
0x18000912f  sub     rsp, 890h
0x180009136  mov     rax, cs:__security_cookie
0x18000913d  xor     rax, rsp
0x180009140  mov     [rbp+790h+var_10], rax
0x180009147  xor     eax, eax
0x180009149  mov     [rsp+890h+var_820], ax
0x18000914e  xor     edi, edi
0x180009150  mov     [rsp+890h+var_830], rax
0x180009155  mov     [rsp+890h+var_828], rax
0x18000915a  mov     [rsp+890h+hKey], rdi
0x18000915f  mov     [rsp+890h+var_848], rdi
0x180009164  mov     [rsp+890h+var_840], rdi
0x180009169  mov     [rsp+890h+var_838], 0FFFFFFFF80000002h
0x180009172  call    cs:__imp_RtlIsStateSeparationEnabled
0x180009178  lea     rcx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\DiagnosticLogCSP\\"...
0x18000917f  lea     r8, aOsdataSoftware_3; "OSData\\SOFTWARE\\Microsoft\\Diagnostic"...
0x180009186  test    al, al
0x180009188  cmovz   r8, rcx; unsigned __int16 *
0x18000918c  lea     rdx, [rsp+890h+hKey]; struct ATL::CRegKey *
0x180009191  lea     rcx, [rsp+890h+var_838]; struct ATL::CRegKey *
0x180009196  call    ?CreateKey@CRegUtils@@SAJAEAVCRegKey@ATL@@0PEBG@Z; CRegUtils::CreateKey(ATL::CRegKey &,ATL::CRegKey &,ushort const *)
0x18000919b  mov     ebx, eax
0x18000919d  test    eax, eax
0x18000919f  js      short loc_1800091DF
0x1800091a1  lea     r8, aMdmconfigurati; "MdmConfiguration"
0x1800091a8  lea     edx, [rdi+2]
0x1800091ab  lea     rcx, [rsp+890h+var_820]
0x1800091b0  call    ?Initialize@CLogFileMgr@@QEAAJW4LogFileType@@PEBG@Z; CLogFileMgr::Initialize(LogFileType,ushort const *)
0x1800091b5  mov     ebx, eax
0x1800091b7  test    eax, eax
0x1800091b9  js      short loc_1800091DF
0x1800091bb  xor     eax, eax
0x1800091bd  cmp     ax, [rsp+890h+var_820]
0x1800091c2  jz      short loc_1800091D8
0x1800091c4  lea     rdi, [rsp+890h+var_820]
0x1800091c9  lea     rcx, [rsp+890h+var_820]
0x1800091ce  call    cs:__imp_?CreateMdmEnterpriseDiagnosticReport@@YAJPEBG@Z; CreateMdmEnterpriseDiagnosticReport(ushort const *)
0x1800091d4  mov     ebx, eax
0x1800091d6  jmp     short loc_1800091DF
0x1800091d8  xor     edi, edi
0x1800091da  mov     ebx, 80004005h
0x1800091df  mov     eax, cs:dword_180048E90
0x1800091e5  cmp     eax, 5
0x1800091e8  jbe     short loc_180009214
0x1800091ea  mov     [rsp+890h+var_860], ebx
0x1800091ee  mov     [rsp+890h+var_858], rdi
0x1800091f3  lea     rax, [rsp+890h+var_860]
0x1800091f8  mov     [rsp+890h+var_868], rax
0x1800091fd  lea     rax, [rsp+890h+var_858]
0x180009202  mov     [rsp+890h+var_870], rax
0x180009207  lea     rdx, unk_18003EC28
0x18000920e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180009213  nop
0x180009214  mov     rcx, [rsp+890h+hKey]; hKey
0x180009219  test    rcx, rcx
0x18000921c  jz      short loc_180009225
0x18000921e  call    cs:__imp_RegCloseKey
0x180009224  nop
0x180009225  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000922c  call    cs:__imp_RegCloseKey
0x180009232  mov     eax, ebx
0x180009234  mov     rcx, [rbp+790h+var_10]
0x18000923b  xor     rcx, rsp; StackCookie
0x18000923e  call    __security_check_cookie
0x180009243  lea     r11, [rsp+890h+var_s0]
0x18000924b  mov     rbx, [r11+10h]
0x18000924f  mov     rdi, [r11+18h]
0x180009253  mov     rsp, r11
0x180009256  pop     rbp
0x180009257  retn
```
