# CDeviceStateNode::ClearStateData(void)

- ea: `0x180009260`
- end: `0x18000939a`
- name: `?ClearStateData@CDeviceStateNode@@KAJXZ`
- size: `314`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009560`

## callees

- `0x180001104`
- `0x180001b60`
- `0x180009260`
- `0x1800101f4`
- `0x180010230`
- `0x18001107c`
- `0x180011208`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18000929c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000929c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009372`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009372`

## string_xrefs

- `0x1800092c6`: `MdmConfiguration`
- `0x1800092ec`: `MdmConfiguration`

## pseudocode

```c
__int64 CDeviceStateNode::ClearStateData(void)
{
  char IsStateSeparationEnabled; // al
  const WCHAR *v1; // rcx
  int v2; // ebx
  int v3; // eax
  int v5; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey[3]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v7[1032]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v8[32]; // [rsp+860h] [rbp+760h] BYREF
  int *v9; // [rsp+880h] [rbp+780h]
  __int64 v10; // [rsp+888h] [rbp+788h]

  v7[0] = 0;
  memset(hKey, 0, sizeof(hKey));
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v1 = L"OSData\\SOFTWARE\\Microsoft\\DiagnosticLogCSP\\DeviceStateData";
  if ( !IsStateSeparationEnabled )
    v1 = L"SOFTWARE\\Microsoft\\DiagnosticLogCSP\\DeviceStateData";
  v2 = CRegUtils::OpenKey(v1, (struct ATL::CRegKey *)hKey);
  if ( v2 >= 0 )
  {
    v3 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, L"MdmConfiguration");
    v2 = v3;
    if ( !v3 )
      goto LABEL_8;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_8:
      v2 = CLogFileMgr::Initialize(v7, 2, L"MdmConfiguration");
      if ( v2 >= 0 )
        v2 = CLogFileMgr::Delete((CLogFileMgr *)v7);
    }
  }
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v9 = &v5;
    v10 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180048E90, &unk_18003EC70, 0, 0, 3, v8, v2);
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180009260  mov     [rsp-8+arg_0], rbx
0x180009265  push    rbp
0x180009266  lea     rbp, [rsp-7A0h]
0x18000926e  sub     rsp, 8A0h
0x180009275  mov     rax, cs:__security_cookie
0x18000927c  xor     rax, rsp
0x18000927f  mov     [rbp+7A0h+var_10], rax
0x180009286  xor     eax, eax
0x180009288  mov     [rsp+8A0h+var_850], ax
0x18000928d  mov     [rsp+8A0h+hKey], rax
0x180009292  mov     [rsp+8A0h+var_860], rax
0x180009297  mov     [rsp+8A0h+var_858], rax
0x18000929c  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800092a2  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\DiagnosticLogCSP\\"...
0x1800092a9  lea     rcx, aOsdataSoftware; "OSData\\SOFTWARE\\Microsoft\\Diagnostic"...
0x1800092b0  test    al, al
0x1800092b2  cmovz   rcx, rdx; lpSubKey
0x1800092b6  lea     rdx, [rsp+8A0h+hKey]; struct ATL::CRegKey *
0x1800092bb  call    ?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@@Z; CRegUtils::OpenKey(ushort const *,ATL::CRegKey &)
0x1800092c0  mov     ebx, eax
0x1800092c2  test    eax, eax
0x1800092c4  js      short loc_180009314
0x1800092c6  lea     rdx, aMdmconfigurati; "MdmConfiguration"
0x1800092cd  lea     rcx, [rsp+8A0h+hKey]; this
0x1800092d2  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800092d7  mov     ebx, eax
0x1800092d9  test    eax, eax
0x1800092db  jz      short loc_1800092EC
0x1800092dd  jle     short loc_1800092E8
0x1800092df  movzx   ebx, ax
0x1800092e2  or      ebx, 80070000h
0x1800092e8  test    ebx, ebx
0x1800092ea  js      short loc_180009314
0x1800092ec  lea     r8, aMdmconfigurati; "MdmConfiguration"
0x1800092f3  mov     edx, 2
0x1800092f8  lea     rcx, [rsp+8A0h+var_850]
0x1800092fd  call    ?Initialize@CLogFileMgr@@QEAAJW4LogFileType@@PEBG@Z; CLogFileMgr::Initialize(LogFileType,ushort const *)
0x180009302  mov     ebx, eax
0x180009304  test    eax, eax
0x180009306  js      short loc_180009314
0x180009308  lea     rcx, [rsp+8A0h+var_850]; this
0x18000930d  call    ?Delete@CLogFileMgr@@QEAAJXZ; CLogFileMgr::Delete(void)
0x180009312  mov     ebx, eax
0x180009314  mov     eax, cs:dword_180048E90
0x18000931a  cmp     eax, 5
0x18000931d  jbe     short loc_180009368
0x18000931f  mov     [rsp+8A0h+var_870], ebx
0x180009323  lea     rax, [rsp+8A0h+var_870]
0x180009328  mov     [rbp+7A0h+var_20], rax
0x18000932f  mov     [rbp+7A0h+var_18], 4
0x18000933a  lea     rax, [rbp+7A0h+var_40]
0x180009341  mov     [rsp+8A0h+var_878], rax
0x180009346  mov     [rsp+8A0h+var_880], 3
0x18000934e  xor     r9d, r9d
0x180009351  xor     r8d, r8d
0x180009354  lea     rdx, unk_18003EC70
0x18000935b  lea     rcx, dword_180048E90
0x180009362  call    _tlgWriteTransfer_EventWriteTransfer
0x180009367  nop
0x180009368  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18000936d  test    rcx, rcx
0x180009370  jz      short loc_180009378
0x180009372  call    cs:__imp_RegCloseKey
0x180009378  mov     eax, ebx
0x18000937a  mov     rcx, [rbp+7A0h+var_10]
0x180009381  xor     rcx, rsp; StackCookie
0x180009384  call    __security_check_cookie
0x180009389  mov     rbx, [rsp+8A0h+arg_0]
0x180009391  add     rsp, 8A0h
0x180009398  pop     rbp
0x180009399  retn
```
