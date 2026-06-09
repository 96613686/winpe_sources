# CUninstallCbsClient::MultipleEditionsPresent(void)

- ea: `0x180024600`
- end: `0x1800248c4`
- name: `?MultipleEditionsPresent@CUninstallCbsClient@@AEAA_NXZ`
- size: `708`
- prototype: `bool __fastcall(CUninstallCbsClient *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007ba20`

## callees

- `0x1800218c0`
- `0x180024600`
- `0x180024c80`
- `0x18002d2b0`
- `0x180042bac`
- `0x18007c0ac`
- `0x18007c504`
- `0x18009e020`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18002465d`
- `ntdll!RtlRaiseStatus` at `0x18002465d`
- `OLE32!CoTaskMemFree` at `0x1800247c5`
- `OLE32!CoTaskMemFree` at `0x1800247eb`
- `OLE32!CoTaskMemFree` at `0x1800248b3`
- `OLE32!CoTaskMemFree` at `0x1800247c5`
- `OLE32!CoTaskMemFree` at `0x1800247eb`
- `OLE32!CoTaskMemFree` at `0x1800248b3`

## string_xrefs

- `0x180024862`: `Failed opening package %ws`

## pseudocode

```c
unsigned __int8 __fastcall CUninstallCbsClient::MultipleEditionsPresent(CUninstallCbsClient *this)
{
  __int64 v2; // rbx
  unsigned __int8 v3; // r15
  int v4; // eax
  __int64 v5; // rsi
  unsigned int (__fastcall *v6)(__int64, __int64, __int64, int *); // rdi
  __int64 InitPointer; // rax
  struct ICbsIdentity *v8; // rsi
  __int64 (__fastcall *v9)(struct ICbsIdentity *, __int64); // rdi
  __int64 v10; // rax
  int v11; // eax
  struct ICbsPackage **v12; // rax
  int v13; // eax
  int v14; // eax
  int PackageVersion; // eax
  __int64 v17; // [rsp+30h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-40h] BYREF
  __int64 v19; // [rsp+40h] [rbp-38h] BYREF
  int v20; // [rsp+48h] [rbp-30h] BYREF
  int v21; // [rsp+4Ch] [rbp-2Ch] BYREF
  struct ICbsIdentity *v22; // [rsp+50h] [rbp-28h] BYREF
  __int64 v23; // [rsp+58h] [rbp-20h] BYREF
  int v24; // [rsp+60h] [rbp-18h] BYREF

  v23 = 0;
  v22 = 0;
  v21 = 0;
  v2 = 0;
  CBSWdsLog(0x4000000, 0, 0, "Checking if there are multiple editions");
  v3 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)this + 1) + 56LL))(
         *((_QWORD *)this + 1),
         2048,
         &v23);
  if ( v4 >= 0 )
  {
    while ( 1 )
    {
      v5 = v23;
      v6 = *(unsigned int (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v23 + 24LL);
      InitPointer = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v22);
      if ( v6(v5, 1, InitPointer, &v21) || !v21 )
        goto LABEL_18;
      v8 = v22;
      pv = 0;
      v19 = 0;
      v20 = 0;
      v24 = 0;
      v9 = *(__int64 (__fastcall **)(struct ICbsIdentity *, __int64))(*(_QWORD *)v22 + 64LL);
      v10 = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&pv);
      v11 = v9(v8, v10);
      if ( v11 < 0 )
        break;
      v12 = (struct ICbsPackage **)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v19);
      v13 = CUninstallCbsClient::OpenPackage(this, v22, v12);
      if ( v13 < 0 )
      {
        CBSWdsLog(0x4000000, (unsigned int)v13, 1, "Failed opening package %ws", pv);
        goto LABEL_26;
      }
      v14 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v19 + 96LL))(v19, &v20, &v24);
      if ( v14 < 0 )
      {
        CBSWdsLog(0x4000000, (unsigned int)v14, 1, "Failed getting package status");
        goto LABEL_26;
      }
      v17 = 0;
      PackageVersion = GetPackageVersion(pv, &v17);
      if ( PackageVersion < 0 )
      {
        CBSWdsLog(0x4000000, (unsigned int)PackageVersion, 1, "Failed getting version of the package %ws", pv);
        goto LABEL_26;
      }
      if ( v20 != -16 && v20 >= -17 )
      {
        if ( v2 )
        {
          if ( WORD1(v2) != WORD1(v17) )
          {
            v3 = 1;
            Windows::AutoComPtr<IClassFactory>::Close(&v19);
            if ( pv )
              CoTaskMemFree(pv);
LABEL_18:
            CBSWdsLog(0x4000000, 0, 0, "Multiple editions present: %d", v3);
            goto LABEL_19;
          }
        }
        else
        {
          v2 = v17;
        }
      }
      Windows::AutoComPtr<IClassFactory>::Close(&v22);
      Windows::AutoComPtr<IClassFactory>::Close(&v19);
      if ( pv )
        CoTaskMemFree(pv);
    }
    CBSWdsLog(0x4000000, (unsigned int)v11, 1, "Failed getting Identity as string");
LABEL_26:
    Windows::AutoComPtr<IClassFactory>::Close(&v19);
    if ( pv )
      CoTaskMemFree(pv);
  }
  else
  {
    CBSWdsLog(0x4000000, (unsigned int)v4, 1, "Failed to get the edition packages");
  }
LABEL_19:
  Windows::AutoComPtr<IClassFactory>::Close(&v22);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  return v3;
}

```

## disassembly

```asm
0x180024600  push    rbp
0x180024602  push    rbx
0x180024603  push    rsi
0x180024604  push    rdi
0x180024605  push    r13
0x180024607  push    r15
0x180024609  mov     rbp, rsp
0x18002460c  sub     rsp, 78h
0x180024610  mov     rax, cs:__security_cookie
0x180024617  xor     rax, rsp
0x18002461a  mov     [rbp+var_10], rax
0x18002461e  mov     r13, rcx
0x180024621  mov     [rbp+var_20], 0
0x180024629  mov     edi, 4000000h
0x18002462e  mov     [rbp+var_28], 0
0x180024636  mov     ecx, edi
0x180024638  mov     [rbp+var_2C], 0
0x18002463f  lea     r9, aCheckingIfTher; "Checking if there are multiple editions"
0x180024646  xor     r8d, r8d
0x180024649  xor     edx, edx
0x18002464b  xor     ebx, ebx
0x18002464d  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x180024652  cmp     [rbp+var_20], rbx
0x180024656  jz      short loc_18002466A
0x180024658  mov     ecx, 0C00000E5h; Status
0x18002465d  call    cs:__imp_RtlRaiseStatus
0x180024664  nop     dword ptr [rax+rax+00h]
0x180024669  int     3; Trap to Debugger
0x18002466a  mov     rcx, [r13+8]
0x18002466e  lea     r8, [rbp+var_20]
0x180024672  mov     edx, 800h
0x180024677  xor     r15b, r15b
0x18002467a  mov     rax, [rcx]
0x18002467d  mov     rax, [rax+38h]
0x180024681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024686  test    eax, eax
0x180024688  jns     short loc_1800246A5
0x18002468a  lea     r9, aFailedToGetThe; "Failed to get the edition packages"
0x180024691  mov     r8d, 1
0x180024697  mov     edx, eax
0x180024699  mov     ecx, edi
0x18002469b  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1800246a0  jmp     loc_180024815
0x1800246a5  mov     rsi, [rbp+var_20]
0x1800246a9  lea     rcx, [rbp+var_28]
0x1800246ad  mov     rax, [rsi]
0x1800246b0  mov     rdi, [rax+18h]
0x1800246b4  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x1800246b9  mov     r8, rax
0x1800246bc  lea     r9, [rbp+var_2C]
0x1800246c0  mov     rax, rdi
0x1800246c3  mov     edx, 1
0x1800246c8  mov     rcx, rsi
0x1800246cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246d0  test    eax, eax
0x1800246d2  jnz     loc_1800247F7
0x1800246d8  cmp     [rbp+var_2C], eax
0x1800246db  jbe     loc_1800247F7
0x1800246e1  mov     rsi, [rbp+var_28]
0x1800246e5  lea     rcx, [rbp+pv]
0x1800246e9  mov     [rbp+pv], 0
0x1800246f1  mov     [rbp+var_38], 0
0x1800246f9  mov     [rbp+var_30], eax
0x1800246fc  mov     [rbp+var_18], eax
0x1800246ff  mov     rax, [rsi]
0x180024702  mov     rdi, [rax+40h]
0x180024706  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18002470b  mov     rdx, rax
0x18002470e  mov     rcx, rsi
0x180024711  mov     rax, rdi
0x180024714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024719  test    eax, eax
0x18002471b  js      loc_180024884
0x180024721  lea     rcx, [rbp+var_38]
0x180024725  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18002472a  mov     rdx, [rbp+var_28]; struct ICbsIdentity *
0x18002472e  mov     r8, rax; struct ICbsPackage **
0x180024731  mov     rcx, r13; this
0x180024734  call    ?OpenPackage@CUninstallCbsClient@@AEAAJPEAUICbsIdentity@@PEAPEAUICbsPackage@@@Z; CUninstallCbsClient::OpenPackage(ICbsIdentity *,ICbsPackage * *)
0x180024739  mov     edx, eax
0x18002473b  test    eax, eax
0x18002473d  js      loc_180024862
0x180024743  mov     rcx, [rbp+var_38]
0x180024747  lea     r8, [rbp+var_18]
0x18002474b  lea     rdx, [rbp+var_30]
0x18002474f  mov     rax, [rcx]
0x180024752  mov     rax, [rax+60h]
0x180024756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002475b  test    eax, eax
0x18002475d  js      loc_180024859
0x180024763  mov     rcx, [rbp+pv]
0x180024767  lea     rdx, [rbp+var_48]
0x18002476b  mov     [rbp+var_48], 0
0x180024773  call    GetPackageVersion
0x180024778  mov     edx, eax
0x18002477a  test    eax, eax
0x18002477c  js      loc_180024850
0x180024782  cmp     [rbp+var_30], 0FFFFFFF0h
0x180024786  jz      short loc_1800247A6
0x180024788  cmp     [rbp+var_30], 0FFFFFFEFh
0x18002478c  jl      short loc_1800247A6
0x18002478e  test    rbx, rbx
0x180024791  jnz     short loc_180024799
0x180024793  mov     rbx, [rbp+var_48]
0x180024797  jmp     short loc_1800247A6
0x180024799  mov     rax, rbx
0x18002479c  shr     rax, 10h
0x1800247a0  cmp     ax, word ptr [rbp+var_48+2]
0x1800247a4  jnz     short loc_1800247D6
0x1800247a6  lea     rcx, [rbp+var_28]
0x1800247aa  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x1800247af  lea     rcx, [rbp+var_38]
0x1800247b3  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x1800247b8  mov     rcx, [rbp+pv]; pv
0x1800247bc  test    rcx, rcx
0x1800247bf  jz      loc_1800246A5
0x1800247c5  call    cs:__imp_CoTaskMemFree
0x1800247cc  nop     dword ptr [rax+rax+00h]
0x1800247d1  jmp     loc_1800246A5
0x1800247d6  lea     rcx, [rbp+var_38]
0x1800247da  mov     r15b, 1
0x1800247dd  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x1800247e2  mov     rcx, [rbp+pv]; pv
0x1800247e6  test    rcx, rcx
0x1800247e9  jz      short loc_1800247F7
0x1800247eb  call    cs:__imp_CoTaskMemFree
0x1800247f2  nop     dword ptr [rax+rax+00h]
0x1800247f7  movzx   eax, r15b
0x1800247fb  lea     r9, aMultipleEditio; "Multiple editions present: %d"
0x180024802  xor     r8d, r8d
0x180024805  mov     dword ptr [rsp+78h+var_58], eax
0x180024809  xor     edx, edx
0x18002480b  mov     ecx, 4000000h
0x180024810  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x180024815  lea     rcx, [rbp+var_28]
0x180024819  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x18002481e  mov     rcx, [rbp+var_20]
0x180024822  test    rcx, rcx
0x180024825  jz      short loc_180024833
0x180024827  mov     rdx, [rcx]
0x18002482a  mov     rax, [rdx+10h]
0x18002482e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024833  mov     al, r15b
0x180024836  mov     rcx, [rbp+var_10]
0x18002483a  xor     rcx, rsp; StackCookie
0x18002483d  call    __security_check_cookie
0x180024842  add     rsp, 78h
0x180024846  pop     r15
0x180024848  pop     r13
0x18002484a  pop     rdi
0x18002484b  pop     rsi
0x18002484c  pop     rbx
0x18002484d  pop     rbp
0x18002484e  retn
0x180024850  lea     r9, aFailedGettingV; "Failed getting version of the package %"...
0x180024857  jmp     short loc_180024869
0x180024859  lea     r9, aFailedGettingP; "Failed getting package status"
0x180024860  jmp     short loc_18002488B
0x180024862  lea     r9, aFailedOpeningP_0; "Failed opening package %ws"
0x180024869  mov     rax, [rbp+pv]
0x18002486d  mov     ecx, 4000000h
0x180024872  mov     r8d, 1
0x180024878  mov     [rsp+78h+var_58], rax
0x18002487d  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x180024882  jmp     short loc_18002489D
0x180024884  lea     r9, aFailedGettingI; "Failed getting Identity as string"
0x18002488b  mov     r8d, 1
0x180024891  mov     edx, eax
0x180024893  mov     ecx, 4000000h
0x180024898  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18002489d  lea     rcx, [rbp+var_38]
0x1800248a1  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x1800248a6  mov     rcx, [rbp+pv]; pv
0x1800248aa  test    rcx, rcx
0x1800248ad  jz      loc_180024815
0x1800248b3  call    cs:__imp_CoTaskMemFree
0x1800248ba  nop     dword ptr [rax+rax+00h]
0x1800248bf  jmp     loc_180024815
```
