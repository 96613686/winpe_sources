# CDevice::WatchForDeveloperModeDisableAndRemoveDevice(void)

- ea: `0x1800602dc`
- end: `0x180060452`
- name: `?WatchForDeveloperModeDisableAndRemoveDevice@CDevice@@QEAAXXZ`
- size: `374`
- prototype: `void __fastcall(CDevice *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060000`
- `0x1800f1af0`

## callees

- `0x18000b920`
- `0x18000d560`
- `0x18000d770`
- `0x1800602dc`
- `0x1800c334c`
- `0x1800cc0fc`
- `0x1800e84cc`
- `0x18015497c`
- `0x180224e94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800603d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800603d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800603c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800603c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDevice::WatchForDeveloperModeDisableAndRemoveDevice(CDevice *this)
{
  CRegistryWatcher **v2; // rdi
  CRegistryWatcher **v3; // r14
  unsigned __int64 v4; // rsi
  HKEY v5; // rax
  const char *v6; // r9
  HKEY v7; // rdx
  int v8; // edi
  __int64 v9; // rax
  const char *v10; // r9
  HKEY v11; // rdx
  bool phkResult; // [rsp+20h] [rbp-40h]
  bool phkResulta; // [rsp+20h] [rbp-40h]
  void (*v14)(bool, unsigned int, void *); // [rsp+28h] [rbp-38h]
  void (*v15)(bool, unsigned int, void *); // [rsp+28h] [rbp-38h]
  void **pExceptionObject; // [rsp+40h] [rbp-20h] BYREF
  int v17; // [rsp+48h] [rbp-18h]
  __int128 v18; // [rsp+50h] [rbp-10h]
  HKEY hKey; // [rsp+90h] [rbp+30h] BYREF
  HKEY v20; // [rsp+98h] [rbp+38h] BYREF
  unsigned __int64 v21; // [rsp+A0h] [rbp+40h]

  v2 = (CRegistryWatcher **)((char *)this + 2944);
  if ( !*((_QWORD *)this + 368) )
  {
    v3 = (CRegistryWatcher **)((char *)this + 2952);
    if ( !*((_QWORD *)this + 369) )
    {
      v4 = ((unsigned __int64)this + 688) & -(__int64)(this != 0);
      CLockOwnerChild<CDevice,0>::UCAddUse(v4);
      v21 = v4;
      v5 = (HKEY)operator new(0x130u);
      if ( v5 )
      {
        *(_QWORD *)v5 = 0;
        *((_QWORD *)v5 + 1) = 0;
        *((_QWORD *)v5 + 2) = 0;
        *((_QWORD *)v5 + 3) = 0;
        *((_QWORD *)v5 + 4) = 0;
      }
      hKey = v5;
      std::unique_ptr<CRegistryWatcher>::operator=<std::default_delete<CRegistryWatcher>,0>(v2, &hKey);
      v7 = hKey;
      if ( hKey )
        std::default_delete<CRegistryWatcher>::operator()();
      v8 = CRegistryWatcher::SetDWORDWatch(
             *v2,
             v7,
             "SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModelUnlock",
             v6,
             phkResult,
             v14,
             this);
      if ( v8 < 0 )
        goto LABEL_15;
      hKey = 0;
      if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Policies\\Microsoft\\Windows\\Appx", 0, 0x111u, &hKey) )
      {
        RegCloseKey(hKey);
        v9 = std::make_unique<CRegistryWatcher,,0>(&v20);
        std::unique_ptr<CRegistryWatcher>::operator=<std::default_delete<CRegistryWatcher>,0>(v3, v9);
        v11 = v20;
        if ( v20 )
          std::default_delete<CRegistryWatcher>::operator()();
        v8 = CRegistryWatcher::SetDWORDWatch(
               *v3,
               v11,
               "SOFTWARE\\Policies\\Microsoft\\Windows\\Appx",
               v10,
               phkResulta,
               v15,
               this);
      }
      if ( v8 < 0 )
      {
LABEL_15:
        pExceptionObject = &_com_error::`vftable';
        v17 = v8;
        v18 = 0;
        throw (_com_error *)&pExceptionObject;
      }
      CLockOwnerChild<CDevice,0>::UCReleaseUse(v4);
    }
  }
}

```

## disassembly

```asm
0x1800602dc  push    rbp
0x1800602de  push    rbx
0x1800602df  push    rsi
0x1800602e0  push    rdi
0x1800602e1  push    r14
0x1800602e3  mov     rbp, rsp
0x1800602e6  sub     rsp, 60h
0x1800602ea  mov     rbx, rcx
0x1800602ed  lea     rdi, [rcx+0B80h]
0x1800602f4  cmp     qword ptr [rdi], 0
0x1800602f8  jnz     loc_180060420
0x1800602fe  lea     r14, [rcx+0B88h]
0x180060305  cmp     qword ptr [r14], 0
0x180060309  jnz     loc_180060420
0x18006030f  mov     rax, rcx
0x180060312  lea     rdx, [rcx+2B0h]
0x180060319  neg     rax
0x18006031c  sbb     rsi, rsi
0x18006031f  and     rsi, rdx
0x180060322  mov     rcx, rsi
0x180060325  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x18006032a  mov     [rbp+arg_10], rsi
0x18006032e  mov     ecx, 130h; dwBytes
0x180060333  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180060338  test    rax, rax
0x18006033b  jz      short loc_180060364
0x18006033d  mov     qword ptr [rax], 0
0x180060344  mov     qword ptr [rax+8], 0
0x18006034c  mov     qword ptr [rax+10h], 0
0x180060354  mov     qword ptr [rax+18h], 0
0x18006035c  mov     qword ptr [rax+20h], 0
0x180060364  mov     [rbp+hKey], rax
0x180060368  lea     rdx, [rbp+hKey]
0x18006036c  mov     rcx, rdi
0x18006036f  call    ??$?4U?$default_delete@VCRegistryWatcher@@@std@@$0A@@?$unique_ptr@VCRegistryWatcher@@U?$default_delete@VCRegistryWatcher@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CRegistryWatcher>::operator=<std::default_delete<CRegistryWatcher>,0>(std::unique_ptr<CRegistryWatcher> &&)
0x180060374  mov     rdx, [rbp+hKey]
0x180060378  test    rdx, rdx
0x18006037b  jz      short loc_180060382
0x18006037d  call    ??R?$default_delete@VCRegistryWatcher@@@std@@QEBAXPEAVCRegistryWatcher@@@Z; std::default_delete<CRegistryWatcher>::operator()(CRegistryWatcher *)
0x180060382  mov     [rsp+60h+var_30], rbx; void *
0x180060387  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006038e  mov     rcx, [rdi]; this
0x180060391  call    ?SetDWORDWatch@CRegistryWatcher@@QEAAJPEAUHKEY__@@PEBD1_NP6AX2KPEAX@Z3@Z; CRegistryWatcher::SetDWORDWatch(HKEY__ *,char const *,char const *,bool,void (*)(bool,ulong,void *),void *)
0x180060396  mov     edi, eax
0x180060398  test    eax, eax
0x18006039a  js      loc_18006042B
0x1800603a0  mov     [rbp+hKey], 0
0x1800603a8  lea     rax, [rbp+hKey]
0x1800603ac  mov     [rsp+60h+phkResult], rax; bool
0x1800603b1  mov     r9d, 111h; samDesired
0x1800603b7  xor     r8d, r8d; ulOptions
0x1800603ba  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800603c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800603c8  call    cs:__imp_RegOpenKeyExA
0x1800603ce  test    eax, eax
0x1800603d0  jnz     short loc_180060414
0x1800603d2  mov     rcx, [rbp+hKey]; hKey
0x1800603d6  call    cs:__imp_RegCloseKey
0x1800603dc  lea     rcx, [rbp+arg_8]
0x1800603e0  call    ??$make_unique@VCRegistryWatcher@@$$V$0A@@std@@YA?AV?$unique_ptr@VCRegistryWatcher@@U?$default_delete@VCRegistryWatcher@@@std@@@0@XZ; std::make_unique<CRegistryWatcher,,0>(void)
0x1800603e5  mov     rdx, rax
0x1800603e8  mov     rcx, r14
0x1800603eb  call    ??$?4U?$default_delete@VCRegistryWatcher@@@std@@$0A@@?$unique_ptr@VCRegistryWatcher@@U?$default_delete@VCRegistryWatcher@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CRegistryWatcher>::operator=<std::default_delete<CRegistryWatcher>,0>(std::unique_ptr<CRegistryWatcher> &&)
0x1800603f0  mov     rdx, [rbp+arg_8]
0x1800603f4  test    rdx, rdx
0x1800603f7  jz      short loc_1800603FE
0x1800603f9  call    ??R?$default_delete@VCRegistryWatcher@@@std@@QEBAXPEAVCRegistryWatcher@@@Z; std::default_delete<CRegistryWatcher>::operator()(CRegistryWatcher *)
0x1800603fe  mov     [rsp+60h+var_30], rbx; void *
0x180060403  lea     r8, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18006040a  mov     rcx, [r14]; this
0x18006040d  call    ?SetDWORDWatch@CRegistryWatcher@@QEAAJPEAUHKEY__@@PEBD1_NP6AX2KPEAX@Z3@Z; CRegistryWatcher::SetDWORDWatch(HKEY__ *,char const *,char const *,bool,void (*)(bool,ulong,void *),void *)
0x180060412  mov     edi, eax
0x180060414  test    edi, edi
0x180060416  js      short loc_18006042B
0x180060418  mov     rcx, rsi
0x18006041b  call    ?UCReleaseUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCReleaseUse(void)
0x180060420  add     rsp, 60h
0x180060424  pop     r14
0x180060426  pop     rdi
0x180060427  pop     rsi
0x180060428  pop     rbx
0x180060429  pop     rbp
0x18006042a  retn
0x18006042b  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180060432  mov     [rbp+pExceptionObject], rax
0x180060436  mov     [rbp+var_18], edi
0x180060439  xorps   xmm0, xmm0
0x18006043c  movdqu  [rbp+var_10], xmm0
0x180060441  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180060448  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18006044c  call    _CxxThrowException_0
```
