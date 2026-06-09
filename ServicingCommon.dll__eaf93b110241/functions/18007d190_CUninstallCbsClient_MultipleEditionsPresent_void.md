# CUninstallCbsClient::MultipleEditionsPresent(void)

- ea: `0x18007d190`
- end: `0x18007d45b`
- name: `?MultipleEditionsPresent@CUninstallCbsClient@@AEAA_NXZ`
- size: `715`
- prototype: `bool __fastcall(CUninstallCbsClient *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18007bdb0`

## callees

- `0x18001f708`
- `0x18001fd10`
- `0x1800293a0`
- `0x18003e810`
- `0x180044050`
- `0x18007c8f8`
- `0x18007d190`
- `0x18007d464`
- `0x1800a0020`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x18007d337`
- `OLE32!CoTaskMemFree` at `0x18007d35d`
- `OLE32!CoTaskMemFree` at `0x18007d41b`
- `OLE32!CoTaskMemFree` at `0x18007d337`
- `OLE32!CoTaskMemFree` at `0x18007d35d`
- `OLE32!CoTaskMemFree` at `0x18007d41b`

## string_xrefs

- `0x18007d3ec`: `Failed opening package {}`

## pseudocode

```c
char __fastcall CUninstallCbsClient::MultipleEditionsPresent(CUninstallCbsClient *this)
{
  __int64 v2; // rbx
  char v3; // r14
  __int64 v4; // rsi
  unsigned int (__fastcall *v5)(__int64, __int64, __int64, int *); // rdi
  __int64 InitPointer; // rax
  struct ICbsIdentity *v7; // rsi
  int (__fastcall *v8)(struct ICbsIdentity *, __int64); // rdi
  __int64 v9; // rax
  struct ICbsPackage **v10; // rax
  const char *v12; // r9
  __int64 v13; // [rsp+30h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-40h] BYREF
  struct ICbsIdentity *v15; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+48h] [rbp-30h] BYREF
  __int64 v17; // [rsp+50h] [rbp-28h] BYREF
  int v18; // [rsp+58h] [rbp-20h] BYREF
  int v19; // [rsp+5Ch] [rbp-1Ch] BYREF
  int v20; // [rsp+60h] [rbp-18h] BYREF

  v16 = 0;
  v15 = 0;
  v19 = 0;
  v2 = 0;
  CBSWdsLog(0x4000000, 0, 0, "Checking if there are multiple editions");
  if ( (*(int (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)this + 1) + 56LL))(
         *((_QWORD *)this + 1),
         2048,
         &v16) >= 0 )
  {
    v3 = 0;
    while ( 1 )
    {
      v4 = v16;
      v5 = *(unsigned int (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v16 + 24LL);
      InitPointer = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v15);
      if ( v5(v4, 1, InitPointer, &v19) || !v19 )
        goto LABEL_19;
      v7 = v15;
      pv = 0;
      v17 = 0;
      v18 = 0;
      v20 = 0;
      v8 = *(int (__fastcall **)(struct ICbsIdentity *, __int64))(*(_QWORD *)v15 + 64LL);
      v9 = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&pv);
      if ( v8(v7, v9) < 0 )
        break;
      v10 = (struct ICbsPackage **)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v17);
      if ( (int)CUninstallCbsClient::OpenPackage(this, v15, v10) < 0 )
      {
        v12 = "Failed opening package {}";
        goto LABEL_26;
      }
      if ( (*(int (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v17 + 96LL))(v17, &v18, &v20) < 0 )
      {
        v12 = "Failed getting package status";
        goto LABEL_26;
      }
      v13 = 0;
      if ( (int)GetPackageVersion(pv, &v13) < 0 )
      {
        v12 = "Failed getting version of the package {}";
        goto LABEL_26;
      }
      if ( v18 != -16 && v18 >= -17 )
      {
        if ( v2 )
        {
          if ( WORD1(v2) != WORD1(v13) )
          {
            v3 = 1;
            Windows::AutoComPtr<IClassFactory>::Close(&v17);
            if ( pv )
              CoTaskMemFree(pv);
LABEL_19:
            CBSWdsLog(0x4000000, 0, 0, "Multiple editions present: {}");
            Windows::AutoComPtr<IClassFactory>::Close(&v15);
            if ( v16 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
            return v3;
          }
        }
        else
        {
          v2 = v13;
        }
      }
      Windows::AutoComPtr<IClassFactory>::Close(&v15);
      Windows::AutoComPtr<IClassFactory>::Close(&v17);
      if ( pv )
        CoTaskMemFree(pv);
    }
    v12 = "Failed getting Identity as string";
LABEL_26:
    CBSWdsLog(0x4000000, 0, 0, v12);
    Windows::AutoComPtr<IClassFactory>::Close(&v17);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
  }
  else
  {
    CBSWdsLog(0x4000000, 0, 0, "Failed to get the edition packages");
  }
  Windows::AutoComPtr<IClassFactory>::Close(&v15);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return 0;
}

```

## disassembly

```asm
0x18007d190  push    rbp
0x18007d192  push    rbx
0x18007d193  push    rsi
0x18007d194  push    rdi
0x18007d195  push    r12
0x18007d197  push    r13
0x18007d199  push    r14
0x18007d19b  push    r15
0x18007d19d  mov     rbp, rsp
0x18007d1a0  sub     rsp, 78h
0x18007d1a4  mov     rax, cs:__security_cookie
0x18007d1ab  xor     rax, rsp
0x18007d1ae  mov     [rbp+var_10], rax
0x18007d1b2  xor     r12d, r12d
0x18007d1b5  lea     r9, aCheckingIfTher; "Checking if there are multiple editions"
0x18007d1bc  mov     r15, rcx
0x18007d1bf  mov     [rbp+var_30], r12
0x18007d1c3  mov     r13d, 4000000h
0x18007d1c9  mov     [rbp+var_38], r12
0x18007d1cd  mov     ecx, r13d
0x18007d1d0  mov     [rbp+var_1C], r12d
0x18007d1d4  xor     r8d, r8d
0x18007d1d7  xor     edx, edx
0x18007d1d9  mov     ebx, r12d
0x18007d1dc  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18007d1e1  cmp     [rbp+var_30], r12
0x18007d1e5  jnz     loc_18007D450
0x18007d1eb  mov     rcx, [r15+8]
0x18007d1ef  lea     r8, [rbp+var_30]
0x18007d1f3  mov     edx, 800h
0x18007d1f8  mov     rax, [rcx]
0x18007d1fb  mov     rax, [rax+38h]
0x18007d1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d204  test    eax, eax
0x18007d206  jns     short loc_18007D221
0x18007d208  lea     r9, aFailedToGetThe; "Failed to get the edition packages"
0x18007d20f  xor     r8d, r8d
0x18007d212  xor     edx, edx
0x18007d214  mov     ecx, r13d
0x18007d217  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18007d21c  jmp     loc_18007D42B
0x18007d221  mov     r14b, r12b
0x18007d224  mov     rsi, [rbp+var_30]
0x18007d228  lea     rcx, [rbp+var_38]
0x18007d22c  mov     rax, [rsi]
0x18007d22f  mov     rdi, [rax+18h]
0x18007d233  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007d238  mov     r8, rax
0x18007d23b  lea     r9, [rbp+var_1C]
0x18007d23f  mov     rax, rdi
0x18007d242  mov     edx, 1
0x18007d247  mov     rcx, rsi
0x18007d24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d24f  test    eax, eax
0x18007d251  jnz     loc_18007D369
0x18007d257  cmp     [rbp+var_1C], r12d
0x18007d25b  jbe     loc_18007D369
0x18007d261  mov     rsi, [rbp+var_38]
0x18007d265  lea     rcx, [rbp+pv]
0x18007d269  mov     [rbp+pv], r12
0x18007d26d  mov     [rbp+var_28], r12
0x18007d271  mov     [rbp+var_20], r12d
0x18007d275  mov     [rbp+var_18], r12d
0x18007d279  mov     rax, [rsi]
0x18007d27c  mov     rdi, [rax+40h]
0x18007d280  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007d285  mov     rdx, rax
0x18007d288  mov     rcx, rsi
0x18007d28b  mov     rax, rdi
0x18007d28e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d293  test    eax, eax
0x18007d295  js      loc_18007D3F5
0x18007d29b  lea     rcx, [rbp+var_28]
0x18007d29f  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007d2a4  mov     rdx, [rbp+var_38]; struct ICbsIdentity *
0x18007d2a8  mov     r8, rax; struct ICbsPackage **
0x18007d2ab  mov     rcx, r15; this
0x18007d2ae  call    ?OpenPackage@CUninstallCbsClient@@AEAAJPEAUICbsIdentity@@PEAPEAUICbsPackage@@@Z; CUninstallCbsClient::OpenPackage(ICbsIdentity *,ICbsPackage * *)
0x18007d2b3  test    eax, eax
0x18007d2b5  js      loc_18007D3EC
0x18007d2bb  mov     rcx, [rbp+var_28]
0x18007d2bf  lea     r8, [rbp+var_18]
0x18007d2c3  lea     rdx, [rbp+var_20]
0x18007d2c7  mov     rax, [rcx]
0x18007d2ca  mov     rax, [rax+60h]
0x18007d2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d2d3  test    eax, eax
0x18007d2d5  js      loc_18007D3E3
0x18007d2db  mov     rcx, [rbp+pv]
0x18007d2df  lea     rdx, [rbp+var_48]
0x18007d2e3  mov     [rbp+var_48], r12
0x18007d2e7  call    GetPackageVersion
0x18007d2ec  test    eax, eax
0x18007d2ee  js      loc_18007D3C4
0x18007d2f4  cmp     [rbp+var_20], 0FFFFFFF0h
0x18007d2f8  jz      short loc_18007D318
0x18007d2fa  cmp     [rbp+var_20], 0FFFFFFEFh
0x18007d2fe  jl      short loc_18007D318
0x18007d300  test    rbx, rbx
0x18007d303  jnz     short loc_18007D30B
0x18007d305  mov     rbx, [rbp+var_48]
0x18007d309  jmp     short loc_18007D318
0x18007d30b  mov     rax, rbx
0x18007d30e  shr     rax, 10h
0x18007d312  cmp     ax, word ptr [rbp+var_48+2]
0x18007d316  jnz     short loc_18007D348
0x18007d318  lea     rcx, [rbp+var_38]
0x18007d31c  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x18007d321  lea     rcx, [rbp+var_28]
0x18007d325  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x18007d32a  mov     rcx, [rbp+pv]; pv
0x18007d32e  test    rcx, rcx
0x18007d331  jz      loc_18007D224
0x18007d337  call    cs:__imp_CoTaskMemFree
0x18007d33e  nop     dword ptr [rax+rax+00h]
0x18007d343  jmp     loc_18007D224
0x18007d348  lea     rcx, [rbp+var_28]
0x18007d34c  mov     r14b, 1
0x18007d34f  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x18007d354  mov     rcx, [rbp+pv]; pv
0x18007d358  test    rcx, rcx
0x18007d35b  jz      short loc_18007D369
0x18007d35d  call    cs:__imp_CoTaskMemFree
0x18007d364  nop     dword ptr [rax+rax+00h]
0x18007d369  movzx   eax, r14b
0x18007d36d  lea     r9, aMultipleEditio; "Multiple editions present: {}"
0x18007d374  xor     r8d, r8d
0x18007d377  mov     dword ptr [rsp+78h+var_58], eax
0x18007d37b  xor     edx, edx
0x18007d37d  mov     ecx, r13d
0x18007d380  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18007d385  lea     rcx, [rbp+var_38]
0x18007d389  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x18007d38e  mov     rcx, [rbp+var_30]
0x18007d392  test    rcx, rcx
0x18007d395  jz      short loc_18007D3A3
0x18007d397  mov     rdx, [rcx]
0x18007d39a  mov     rax, [rdx+10h]
0x18007d39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d3a3  mov     al, r14b
0x18007d3a6  mov     rcx, [rbp+var_10]
0x18007d3aa  xor     rcx, rsp; StackCookie
0x18007d3ad  call    __security_check_cookie
0x18007d3b2  add     rsp, 78h
0x18007d3b6  pop     r15
0x18007d3b8  pop     r14
0x18007d3ba  pop     r13
0x18007d3bc  pop     r12
0x18007d3be  pop     rdi
0x18007d3bf  pop     rsi
0x18007d3c0  pop     rbx
0x18007d3c1  pop     rbp
0x18007d3c2  retn
0x18007d3c4  lea     r9, aFailedGettingV; "Failed getting version of the package {"...
0x18007d3cb  mov     rax, [rbp+pv]
0x18007d3cf  xor     r8d, r8d
0x18007d3d2  xor     edx, edx
0x18007d3d4  mov     [rsp+78h+var_58], rax
0x18007d3d9  mov     ecx, r13d
0x18007d3dc  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18007d3e1  jmp     short loc_18007D409
0x18007d3e3  lea     r9, aFailedGettingP; "Failed getting package status"
0x18007d3ea  jmp     short loc_18007D3FC
0x18007d3ec  lea     r9, aFailedOpeningP; "Failed opening package {}"
0x18007d3f3  jmp     short loc_18007D3CB
0x18007d3f5  lea     r9, aFailedGettingI; "Failed getting Identity as string"
0x18007d3fc  xor     r8d, r8d
0x18007d3ff  xor     edx, edx
0x18007d401  mov     ecx, r13d
0x18007d404  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18007d409  lea     rcx, [rbp+var_28]
0x18007d40d  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x18007d412  mov     rcx, [rbp+pv]; pv
0x18007d416  test    rcx, rcx
0x18007d419  jz      short loc_18007D42B
0x18007d41b  call    cs:__imp_CoTaskMemFree
0x18007d422  nop     dword ptr [rax+rax+00h]
0x18007d427  mov     [rbp+pv], r12
0x18007d42b  lea     rcx, [rbp+var_38]
0x18007d42f  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x18007d434  mov     rcx, [rbp+var_30]
0x18007d438  test    rcx, rcx
0x18007d43b  jz      short loc_18007D449
0x18007d43d  mov     rax, [rcx]
0x18007d440  mov     rax, [rax+10h]
0x18007d444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d449  xor     al, al
0x18007d44b  jmp     loc_18007D3A6
0x18007d450  mov     ecx, 0C00000E5h; int
0x18007d455  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
