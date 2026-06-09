# DriverJob::_RunDriverJobLocal(void)

- ea: `0x1800346e8`
- end: `0x180034936`
- name: `?_RunDriverJobLocal@DriverJob@@AEAAJXZ`
- size: `590`
- prototype: `__int64 __fastcall(DriverJob *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003493c`

## callees

- `0x180007dc0`
- `0x180009f20`
- `0x18000e33c`
- `0x1800112a4`
- `0x180011fdc`
- `0x1800128ac`
- `0x18001370c`
- `0x180017ed0`
- `0x180018170`
- `0x180018678`
- `0x1800346e8`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034801`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034801`

## string_xrefs

- `0x180034814`: `onecoreuap\base\devices\setup\dsm\service\job.cpp`
- `0x180034858`: `onecoreuap\base\devices\setup\dsm\service\job.cpp`

## pseudocode

```c
__int64 __fastcall DriverJob::_RunDriverJobLocal(DriverJob *this)
{
  CPnpDeviceInfo *v2; // rdi
  _QWORD *v3; // rax
  _QWORD *v5; // rax
  HRESULT v6; // eax
  unsigned int v7; // edi
  char *v8; // rdi
  char *v9; // rdx
  int v10; // esi
  __int64 v11; // rdx
  int ppv; // [rsp+20h] [rbp-30h]
  __int64 v13; // [rsp+30h] [rbp-20h] BYREF
  std::_Ref_count_base *v14; // [rsp+38h] [rbp-18h]
  __int64 v15; // [rsp+40h] [rbp-10h] BYREF
  std::_Ref_count_base *v16; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v18; // [rsp+70h] [rbp+20h] BYREF
  LPVOID v19; // [rsp+78h] [rbp+28h] BYREF

  if ( (*((_DWORD *)this + 6) & 0x10000) != 0
    || (v2 = (DriverJob *)((char *)this + 128),
        !(unsigned int)CPnpDeviceInfo::HasDriverInstalled((DriverJob *)((char *)this + 128)))
    || !(unsigned int)CPnpDeviceInfo::InstalledDriverIsBasicDriverOk(v2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v5 = (_QWORD *)((char *)this + 40);
      if ( *((_QWORD *)this + 8) > 7u )
        v5 = (_QWORD *)*v5;
      WPP_SF__guid_LS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)&WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids,
        (_DWORD)this + 8,
        *((_DWORD *)this + 7),
        (__int64)v5);
    }
    v19 = 0;
    Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v19);
    v6 = CoCreateInstance(
           &GUID_6d93c83d_31c1_490e_b5f9_068a80e3d7cb,
           0,
           1u,
           &GUID_612118c1_b1d3_4d55_80f2_4488b55cf623,
           &v19);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v8 = (char *)this + 40;
      if ( *((_QWORD *)this + 8) <= 7u )
        v9 = (char *)this + 40;
      else
        v9 = *(char **)v8;
      v10 = (*(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)v19 + 24LL))(v19, v9);
      if ( v10 >= 0 )
      {
        v18 = 0;
        v10 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v19 + 32LL))(v19, &v18);
        if ( v10 >= 0 )
        {
          if ( v18 && (byte_180059BC1 & 1) != 0 )
          {
            if ( *((_QWORD *)this + 8) > 7u )
              v8 = *(char **)v8;
            McTemplateU0z_EventWriteTransfer(userpnp_Context, PNP_REBOOT_REQUIRED, v8);
          }
          Job::GetOwningContainer(this, &v15);
          Container::GetContainerSetupTask(v15, &v13);
          if ( (*((_DWORD *)this + 6) & 0x10000) == 0 )
            CDsmTask::SetConfigFlags(v13, 2, 3);
          if ( v14 )
            std::_Ref_count_base::_Decref(v14);
          if ( v16 )
            std::_Ref_count_base::_Decref(v16);
          v7 = 0;
          goto LABEL_39;
        }
        v11 = 502;
      }
      else
      {
        v11 = 497;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\job.cpp",
        (const char *)(unsigned int)v10,
        ppv);
      v7 = v10;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EF,
        (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\job.cpp",
        (const char *)(unsigned int)v6,
        ppv);
    }
LABEL_39:
    Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v19);
    return v7;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v3 = (_QWORD *)((char *)this + 40);
    if ( *((_QWORD *)this + 8) > 7u )
      v3 = (_QWORD *)*v3;
    WPP_SF__guid_LS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)&WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids,
      (_DWORD)this + 8,
      *((_DWORD *)this + 7),
      (__int64)v3);
  }
  return 0;
}

```

## disassembly

```asm
0x1800346e8  mov     [rsp-18h+arg_10], rbx
0x1800346ed  push    rbp
0x1800346ee  push    rsi
0x1800346ef  push    rdi
0x1800346f0  mov     rbp, rsp
0x1800346f3  sub     rsp, 50h
0x1800346f7  mov     rbx, rcx
0x1800346fa  test    dword ptr [rcx+18h], 10000h
0x180034701  jnz     short loc_18003477E
0x180034703  lea     rdi, [rcx+80h]
0x18003470a  mov     rcx, rdi; this
0x18003470d  call    ?HasDriverInstalled@CPnpDeviceInfo@@QEAAHXZ; CPnpDeviceInfo::HasDriverInstalled(void)
0x180034712  test    eax, eax
0x180034714  jz      short loc_18003477E
0x180034716  mov     rcx, rdi; this
0x180034719  call    ?InstalledDriverIsBasicDriverOk@CPnpDeviceInfo@@QEAAHXZ; CPnpDeviceInfo::InstalledDriverIsBasicDriverOk(void)
0x18003471e  test    eax, eax
0x180034720  jz      short loc_18003477E
0x180034722  lea     rax, WPP_GLOBAL_Control
0x180034729  mov     rcx, cs:WPP_GLOBAL_Control
0x180034730  cmp     rcx, rax
0x180034733  jz      short loc_180034777
0x180034735  test    dword ptr [rcx+1Ch], 200h
0x18003473c  jz      short loc_180034777
0x18003473e  cmp     byte ptr [rcx+19h], 4
0x180034742  jb      short loc_180034777
0x180034744  lea     rax, [rbx+28h]
0x180034748  cmp     qword ptr [rax+18h], 7
0x18003474d  jbe     short loc_180034752
0x18003474f  mov     rax, [rax]
0x180034752  lea     r9, [rbx+8]
0x180034756  mov     edx, 1Ah
0x18003475b  mov     [rsp+50h+var_28], rax
0x180034760  mov     eax, [rbx+1Ch]
0x180034763  mov     dword ptr [rsp+50h+ppv], eax
0x180034767  lea     r8, WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids
0x18003476e  mov     rcx, [rcx+10h]
0x180034772  call    WPP_SF__guid_LS
0x180034777  xor     eax, eax
0x180034779  jmp     loc_180034926
0x18003477e  lea     rax, WPP_GLOBAL_Control
0x180034785  mov     rcx, cs:WPP_GLOBAL_Control
0x18003478c  cmp     rcx, rax
0x18003478f  jz      short loc_1800347D3
0x180034791  test    dword ptr [rcx+1Ch], 200h
0x180034798  jz      short loc_1800347D3
0x18003479a  cmp     byte ptr [rcx+19h], 4
0x18003479e  jb      short loc_1800347D3
0x1800347a0  lea     rax, [rbx+28h]
0x1800347a4  cmp     qword ptr [rax+18h], 7
0x1800347a9  jbe     short loc_1800347AE
0x1800347ab  mov     rax, [rax]
0x1800347ae  lea     r9, [rbx+8]
0x1800347b2  mov     edx, 1Bh
0x1800347b7  mov     [rsp+50h+var_28], rax
0x1800347bc  mov     eax, [rbx+1Ch]
0x1800347bf  mov     dword ptr [rsp+50h+ppv], eax
0x1800347c3  lea     r8, WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids
0x1800347ca  mov     rcx, [rcx+10h]
0x1800347ce  call    WPP_SF__guid_LS
0x1800347d3  mov     [rbp+arg_8], 0
0x1800347db  lea     rcx, [rbp+arg_8]
0x1800347df  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x1800347e4  lea     rax, [rbp+arg_8]
0x1800347e8  mov     [rsp+50h+ppv], rax; int
0x1800347ed  lea     r9, _GUID_612118c1_b1d3_4d55_80f2_4488b55cf623; riid
0x1800347f4  xor     edx, edx; pUnkOuter
0x1800347f6  lea     r8d, [rdx+1]; dwClsContext
0x1800347fa  lea     rcx, _GUID_6d93c83d_31c1_490e_b5f9_068a80e3d7cb; rclsid
0x180034801  call    cs:__imp_CoCreateInstance
0x180034807  mov     edi, eax
0x180034809  test    eax, eax
0x18003480b  jns     short loc_18003482A
0x18003480d  mov     rcx, [rbp+18h]; this
0x180034811  mov     r9d, eax; char *
0x180034814  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18003481b  mov     edx, 1EFh; void *
0x180034820  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034825  jmp     loc_18003491B
0x18003482a  mov     rcx, [rbp+arg_8]
0x18003482e  mov     rax, [rcx]
0x180034831  lea     rdi, [rbx+28h]
0x180034835  cmp     qword ptr [rdi+18h], 7
0x18003483a  jbe     short loc_180034841
0x18003483c  mov     rdx, [rdi]
0x18003483f  jmp     short loc_180034844
0x180034841  mov     rdx, rdi
0x180034844  mov     rax, [rax+18h]
0x180034848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003484d  mov     esi, eax
0x18003484f  test    eax, eax
0x180034851  jns     short loc_180034872
0x180034853  mov     edx, 1F1h; void *
0x180034858  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18003485f  mov     r9d, esi; char *
0x180034862  mov     rcx, [rbp+18h]; this
0x180034866  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003486b  mov     edi, esi
0x18003486d  jmp     loc_18003491B
0x180034872  mov     [rbp+arg_0], 0
0x180034879  mov     rcx, [rbp+arg_8]
0x18003487d  mov     rax, [rcx]
0x180034880  lea     rdx, [rbp+arg_0]
0x180034884  mov     rax, [rax+20h]
0x180034888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003488d  mov     esi, eax
0x18003488f  test    eax, eax
0x180034891  jns     short loc_18003489A
0x180034893  mov     edx, 1F6h
0x180034898  jmp     short loc_180034858
0x18003489a  cmp     [rbp+arg_0], 0
0x18003489e  jz      short loc_1800348C9
0x1800348a0  test    cs:byte_180059BC1, 1
0x1800348a7  jz      short loc_1800348C9
0x1800348a9  cmp     qword ptr [rdi+18h], 7
0x1800348ae  jbe     short loc_1800348B3
0x1800348b0  mov     rdi, [rdi]
0x1800348b3  mov     r8, rdi
0x1800348b6  lea     rdx, PNP_REBOOT_REQUIRED
0x1800348bd  lea     rcx, userpnp_Context
0x1800348c4  call    McTemplateU0z_EventWriteTransfer
0x1800348c9  lea     rdx, [rbp+var_10]
0x1800348cd  mov     rcx, rbx
0x1800348d0  call    ?GetOwningContainer@Job@@QEAA?AV?$shared_ptr@VContainer@@@std@@XZ; Job::GetOwningContainer(void)
0x1800348d5  lea     rdx, [rbp+var_20]
0x1800348d9  mov     rcx, [rbp+var_10]
0x1800348dd  call    ?GetContainerSetupTask@Container@@QEAA?AV?$shared_ptr@VCDsmTask@@@std@@XZ; Container::GetContainerSetupTask(void)
0x1800348e2  test    dword ptr [rbx+18h], 10000h
0x1800348e9  jnz     short loc_1800348FD
0x1800348eb  mov     edx, 2
0x1800348f0  lea     r8d, [rdx+1]
0x1800348f4  mov     rcx, [rbp+var_20]
0x1800348f8  call    ?SetConfigFlags@CDsmTask@@QEAAXW4TASK_CFGFLAGS_TYPE@@W4TASK_CFGFLAGS_STATE@@@Z; CDsmTask::SetConfigFlags(TASK_CFGFLAGS_TYPE,TASK_CFGFLAGS_STATE)
0x1800348fd  mov     rcx, [rbp+var_18]; this
0x180034901  test    rcx, rcx
0x180034904  jz      short loc_18003490B
0x180034906  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003490b  mov     rcx, [rbp+var_8]; this
0x18003490f  test    rcx, rcx
0x180034912  jz      short loc_180034919
0x180034914  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180034919  xor     edi, edi
0x18003491b  lea     rcx, [rbp+arg_8]
0x18003491f  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x180034924  mov     eax, edi
0x180034926  mov     rbx, [rsp+50h+arg_10]
0x18003492e  add     rsp, 50h
0x180034932  pop     rdi
0x180034933  pop     rsi
0x180034934  pop     rbp
0x180034935  retn
```
