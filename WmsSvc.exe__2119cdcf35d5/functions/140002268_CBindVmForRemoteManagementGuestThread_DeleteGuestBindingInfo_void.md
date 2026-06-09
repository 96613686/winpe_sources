# CBindVmForRemoteManagementGuestThread::DeleteGuestBindingInfo(void)

- ea: `0x140002268`
- end: `0x14000244b`
- name: `?DeleteGuestBindingInfo@CBindVmForRemoteManagementGuestThread@@IEAAJXZ`
- size: `483`
- prototype: `__int64 __fastcall(CBindVmForRemoteManagementGuestThread *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140002a0c`
- `0x140003480`

## callees

- `0x140002268`
- `0x14002c1b8`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400022c8`
- `ADVAPI32!RegOpenKeyExW` at `0x1400022c8`
- `ADVAPI32!RegCloseKey` at `0x14000242e`
- `ADVAPI32!RegCloseKey` at `0x14000242e`
- `ADVAPI32!RegDeleteValueW` at `0x1400023a3`
- `ADVAPI32!RegDeleteValueW` at `0x1400023ba`
- `ADVAPI32!RegDeleteValueW` at `0x1400023d1`
- `ADVAPI32!RegDeleteValueW` at `0x1400023e8`
- `ADVAPI32!RegDeleteValueW` at `0x1400023ff`
- `ADVAPI32!RegDeleteValueW` at `0x140002416`
- `ADVAPI32!RegDeleteValueW` at `0x1400023a3`
- `ADVAPI32!RegDeleteValueW` at `0x1400023ba`
- `ADVAPI32!RegDeleteValueW` at `0x1400023d1`
- `ADVAPI32!RegDeleteValueW` at `0x1400023e8`
- `ADVAPI32!RegDeleteValueW` at `0x1400023ff`
- `ADVAPI32!RegDeleteValueW` at `0x140002416`
- `KERNEL32!IsDebuggerPresent` at `0x140002327`
- `KERNEL32!IsDebuggerPresent` at `0x140002327`

## string_xrefs

- `0x14000231b`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140002335`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140002368`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x1400022fb`: `CBindVmForRemoteManagementGuestThread::DeleteGuestBindingInfo`

## pseudocode

```c
__int64 __fastcall CBindVmForRemoteManagementGuestThread::DeleteGuestBindingInfo(
        CBindVmForRemoteManagementGuestThread *this)
{
  signed int v1; // ebx
  LSTATUS v3; // eax
  signed int v5; // [rsp+30h] [rbp-28h]
  signed int v6; // [rsp+38h] [rbp-20h]
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  hKey = 0;
  if ( *((_DWORD *)this + 88) )
  {
    v1 = CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline();
    if ( v1 < 0 )
      goto LABEL_20;
    *((_DWORD *)this + 88) = 0;
  }
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine\\Guest", 0, 0x20006u, &hKey);
  if ( v3 )
  {
    if ( v3 != 2 )
    {
      if ( v3 > 0 )
        v1 = (unsigned __int16)v3 | 0x80070000;
      else
        v1 = v3;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        0x1BEu,
        L"CBindVmForRemoteManagementGuestThread::DeleteGuestBindingInfo",
        L"CBRAEx",
        L"lr == 0L || lr == 2L",
        v1);
      if ( IsDebuggerPresent() )
      {
        v6 = v1;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          446,
          L"CBindVmForRemoteManagementGuestThread::DeleteGuestBindingInfo",
          L"CBRAEx",
          L"lr == 0L || lr == 2L",
          v6);
      }
      else
      {
        v5 = v1;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          446,
          L"CBindVmForRemoteManagementGuestThread::DeleteGuestBindingInfo",
          L"CBRAEx",
          L"lr == 0L || lr == 2L",
          v5);
      }
      goto LABEL_20;
    }
    goto LABEL_12;
  }
  if ( RegDeleteValueW(hKey, L"MultiPointGuestSslPort") == 2
    || RegDeleteValueW(hKey, L"MultiPointGuestSslThumbprint") == 2
    || RegDeleteValueW(hKey, L"MultiPointGuestSslCertificate-1") == 2
    || RegDeleteValueW(hKey, L"MultiPointGuestSslCertificate-2") == 2
    || RegDeleteValueW(hKey, L"MultiPointGuestControlPassword") == 2 )
  {
LABEL_12:
    v1 = 0;
    goto LABEL_20;
  }
  if ( RegDeleteValueW(hKey, L"MultiPointGuestRemoteFqdn") == 2 )
    v1 = 0;
LABEL_20:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140002268  mov     [rsp+arg_8], rbx
0x14000226d  mov     [rsp+arg_10], rdi
0x140002272  push    r12
0x140002274  push    r14
0x140002276  push    r15
0x140002278  sub     rsp, 40h
0x14000227c  xor     ebx, ebx
0x14000227e  mov     rdi, rcx
0x140002281  mov     [rsp+58h+hKey], rbx
0x140002286  cmp     [rcx+160h], ebx
0x14000228c  jz      short loc_1400022A7
0x14000228e  call    ?s_WmsSvcNotifyWmsSystemOnline@CManagedServerNotificationThread@@SAJXZ; CManagedServerNotificationThread::s_WmsSvcNotifyWmsSystemOnline(void)
0x140002293  mov     ebx, eax
0x140002295  test    eax, eax
0x140002297  js      loc_140002424
0x14000229d  mov     dword ptr [rdi+160h], 0
0x1400022a7  lea     rax, [rsp+58h+hKey]
0x1400022ac  mov     r9d, 20006h; samDesired
0x1400022b2  xor     r8d, r8d; ulOptions
0x1400022b5  mov     [rsp+58h+phkResult], rax; phkResult
0x1400022ba  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Virtual Machine\\G"...
0x1400022c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400022c8  call    cs:__imp_RegOpenKeyExW
0x1400022ce  test    eax, eax
0x1400022d0  jz      loc_140002397
0x1400022d6  cmp     eax, 2
0x1400022d9  jz      loc_140002390
0x1400022df  test    eax, eax
0x1400022e1  jg      short loc_1400022E7
0x1400022e3  mov     ebx, eax
0x1400022e5  jmp     short loc_1400022F0
0x1400022e7  movzx   ebx, ax
0x1400022ea  or      ebx, 80070000h
0x1400022f0  lea     r12, aCbraex; "CBRAEx"
0x1400022f7  mov     [rsp+58h+var_30], ebx; int
0x1400022fb  lea     r14, aCbindvmforremo_13; "CBindVmForRemoteManagementGuestThread::"...
0x140002302  mov     edi, 1BEh
0x140002307  lea     r15, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x14000230e  mov     r9, r12; unsigned __int16 *
0x140002311  mov     r8, r14; unsigned __int16 *
0x140002314  mov     [rsp+58h+phkResult], r15; unsigned __int16 *
0x140002319  mov     edx, edi; unsigned int
0x14000231b  lea     rcx, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140002322  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140002327  call    cs:__imp_IsDebuggerPresent
0x14000232d  test    eax, eax
0x14000232f  jz      short loc_140002364
0x140002331  mov     [rsp+58h+var_20], ebx
0x140002335  lea     r8, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x14000233c  mov     [rsp+58h+var_28], r15
0x140002341  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140002348  mov     qword ptr [rsp+58h+var_30], r12
0x14000234d  mov     r9d, edi
0x140002350  mov     ecx, 2; unsigned __int8
0x140002355  mov     [rsp+58h+phkResult], r14
0x14000235a  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000235f  jmp     loc_140002424
0x140002364  mov     dword ptr [rsp+58h+var_28], ebx
0x140002368  lea     rdx, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x14000236f  mov     qword ptr [rsp+58h+var_30], r15
0x140002374  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000237b  mov     r9, r14
0x14000237e  mov     [rsp+58h+phkResult], r12
0x140002383  mov     r8d, edi
0x140002386  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000238b  jmp     loc_140002424
0x140002390  xor     ebx, ebx
0x140002392  jmp     loc_140002424
0x140002397  mov     rcx, [rsp+58h+hKey]; hKey
0x14000239c  lea     rdx, ValueName; "MultiPointGuestSslPort"
0x1400023a3  call    cs:__imp_RegDeleteValueW
0x1400023a9  cmp     eax, 2
0x1400023ac  jz      short loc_140002390
0x1400023ae  mov     rcx, [rsp+58h+hKey]; hKey
0x1400023b3  lea     rdx, aMultipointgues_0; "MultiPointGuestSslThumbprint"
0x1400023ba  call    cs:__imp_RegDeleteValueW
0x1400023c0  cmp     eax, 2
0x1400023c3  jz      short loc_140002390
0x1400023c5  mov     rcx, [rsp+58h+hKey]; hKey
0x1400023ca  lea     rdx, aMultipointgues_1; "MultiPointGuestSslCertificate-1"
0x1400023d1  call    cs:__imp_RegDeleteValueW
0x1400023d7  cmp     eax, 2
0x1400023da  jz      short loc_140002390
0x1400023dc  mov     rcx, [rsp+58h+hKey]; hKey
0x1400023e1  lea     rdx, aMultipointgues_2; "MultiPointGuestSslCertificate-2"
0x1400023e8  call    cs:__imp_RegDeleteValueW
0x1400023ee  cmp     eax, 2
0x1400023f1  jz      short loc_140002390
0x1400023f3  mov     rcx, [rsp+58h+hKey]; hKey
0x1400023f8  lea     rdx, aMultipointgues_3; "MultiPointGuestControlPassword"
0x1400023ff  call    cs:__imp_RegDeleteValueW
0x140002405  cmp     eax, 2
0x140002408  jz      short loc_140002390
0x14000240a  mov     rcx, [rsp+58h+hKey]; hKey
0x14000240f  lea     rdx, aMultipointgues_4; "MultiPointGuestRemoteFqdn"
0x140002416  call    cs:__imp_RegDeleteValueW
0x14000241c  xor     ecx, ecx
0x14000241e  cmp     eax, 2
0x140002421  cmovz   ebx, ecx
0x140002424  mov     rcx, [rsp+58h+hKey]; hKey
0x140002429  test    rcx, rcx
0x14000242c  jz      short loc_140002434
0x14000242e  call    cs:__imp_RegCloseKey
0x140002434  mov     rdi, [rsp+58h+arg_10]
0x140002439  mov     eax, ebx
0x14000243b  mov     rbx, [rsp+58h+arg_8]
0x140002440  add     rsp, 40h
0x140002444  pop     r15
0x140002446  pop     r14
0x140002448  pop     r12
0x14000244a  retn
```
