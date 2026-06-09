# CIISGenObject::Delete(ushort *,ushort *)

- ea: `0x180005830`
- end: `0x1800059fa`
- name: `?Delete@CIISGenObject@@UEAAJPEAG0@Z`
- size: `458`
- prototype: `__int64 __fastcall(CIISGenObject *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000474c`
- `0x180005830`
- `0x180012ffc`
- `0x18001441c`
- `0x180014544`
- `0x18001e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000589b`
- `msvcrt!_wcsicmp` at `0x1800058c4`
- `msvcrt!_wcsicmp` at `0x18000589b`
- `msvcrt!_wcsicmp` at `0x1800058c4`
- `ole32!CoGetClassObject` at `0x1800058fc`
- `ole32!CoGetClassObject` at `0x1800058fc`

## pseudocode

```c
__int64 __fastcall CIISGenObject::Delete(CIISGenObject *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int v6; // esi
  const wchar_t *v7; // r14
  int ClassObject; // ebx
  const wchar_t *v9; // rcx
  unsigned int v10; // edx
  int v11; // eax
  struct IMSAdminBaseW *v12; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-30h] BYREF
  __int128 pvReserved; // [rsp+38h] [rbp-28h] BYREF
  __int128 v15; // [rsp+48h] [rbp-18h]
  unsigned int v16; // [rsp+A0h] [rbp+40h] BYREF
  IUnknown *pProxy; // [rsp+A8h] [rbp+48h] BYREF

  if ( !a3 )
    return 2147500035LL;
  v6 = 0;
  v7 = &psz;
  v16 = 0;
  ppv = 0;
  pvReserved = 0;
  if ( a2 )
    v7 = a2;
  pProxy = 0;
  v15 = 0;
  ClassObject = CIISGenObject::CacheMetaDataPath((CIISGenObject *)((char *)this - 72));
  if ( ClassObject >= 0 )
  {
    if ( _wcsicmp(v7, L"IIsApplicationPool") )
    {
      ClassObject = OpenAdminBaseKey(
                      (CIISGenObject *)((char *)this + 104),
                      *((unsigned __int16 **)this + 8),
                      *((unsigned __int16 **)this + 9),
                      2u,
                      (struct IMSAdminBaseW **)this + 16,
                      &v16);
      if ( ClassObject < 0 )
      {
        v6 = v16;
        goto LABEL_19;
      }
      v6 = v16;
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 16) + 32LL))(
              *((_QWORD *)this + 16),
              v16,
              a3);
    }
    else
    {
      v9 = (const wchar_t *)*((_QWORD *)this + 8);
      pvReserved = 0;
      v15 = 0;
      if ( v9 && _wcsicmp(v9, L"localhost") )
        *((_QWORD *)&pvReserved + 1) = *((_QWORD *)this + 8);
      else
        *((_QWORD *)&pvReserved + 1) = 0;
      ClassObject = CoGetClassObject(&CLSID_WamAdmin, 0x15u, &pvReserved, &IID_IClassFactory, &ppv);
      if ( ClassObject < 0 )
        goto LABEL_19;
      ClassObject = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, IUnknown **))(*(_QWORD *)ppv + 24LL))(
                      ppv,
                      0,
                      &IID_IIISApplicationAdmin,
                      &pProxy);
      if ( ClassObject < 0 )
        goto LABEL_19;
      ClassObject = SetProxyImpersonationLevel(pProxy, v10);
      if ( ClassObject < 0 )
        goto LABEL_19;
      v11 = ((__int64 (__fastcall *)(IUnknown *, unsigned __int16 *))pProxy->lpVtbl[2].QueryInterface)(pProxy, a3);
    }
    ClassObject = v11;
  }
LABEL_19:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  v12 = (struct IMSAdminBaseW *)*((_QWORD *)this + 16);
  if ( v12 )
  {
    if ( v6 )
      CloseAdminBaseKey(v12, v6);
  }
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x180005830  mov     [rsp-28h+arg_0], rbx
0x180005835  push    rbp
0x180005836  push    rsi
0x180005837  push    rdi
0x180005838  push    r14
0x18000583a  push    r15
0x18000583c  mov     rbp, rsp
0x18000583f  sub     rsp, 60h
0x180005843  mov     r15, r8
0x180005846  mov     rdi, rcx
0x180005849  test    r8, r8
0x18000584c  jnz     short loc_180005858
0x18000584e  mov     eax, 80004003h
0x180005853  jmp     loc_1800059E6
0x180005858  xor     esi, esi
0x18000585a  lea     r14, psz
0x180005861  xorps   xmm0, xmm0
0x180005864  mov     [rbp+arg_10], esi
0x180005867  test    rdx, rdx
0x18000586a  mov     [rbp+var_30], rsi
0x18000586e  movups  [rbp+pvReserved], xmm0
0x180005872  cmovnz  r14, rdx
0x180005876  mov     [rbp+pProxy], rsi
0x18000587a  add     rcx, 0FFFFFFFFFFFFFFB8h; this
0x18000587e  movups  [rbp+var_18], xmm0
0x180005882  call    ?CacheMetaDataPath@CIISGenObject@@QEAAJXZ; CIISGenObject::CacheMetaDataPath(void)
0x180005887  mov     ebx, eax
0x180005889  test    eax, eax
0x18000588b  js      loc_1800059A3
0x180005891  lea     rdx, aIisapplication_1; "IIsApplicationPool"
0x180005898  mov     rcx, r14; String1
0x18000589b  call    cs:__imp__wcsicmp
0x1800058a1  test    eax, eax
0x1800058a3  jnz     loc_180005955
0x1800058a9  mov     rcx, [rdi+40h]; String1
0x1800058ad  xorps   xmm0, xmm0
0x1800058b0  movups  [rbp+pvReserved], xmm0
0x1800058b4  movups  [rbp+var_18], xmm0
0x1800058b8  test    rcx, rcx
0x1800058bb  jz      short loc_1800058D8
0x1800058bd  lea     rdx, aLocalhost_0; "localhost"
0x1800058c4  call    cs:__imp__wcsicmp
0x1800058ca  test    eax, eax
0x1800058cc  jz      short loc_1800058D8
0x1800058ce  mov     rax, [rdi+40h]
0x1800058d2  mov     qword ptr [rbp+pvReserved+8], rax
0x1800058d6  jmp     short loc_1800058DC
0x1800058d8  mov     qword ptr [rbp+pvReserved+8], rsi
0x1800058dc  lea     rax, [rbp+var_30]
0x1800058e0  mov     edx, 15h; dwClsContext
0x1800058e5  lea     r9, IID_IClassFactory; riid
0x1800058ec  mov     [rsp+60h+ppv], rax; ppv
0x1800058f1  lea     r8, [rbp+pvReserved]; pvReserved
0x1800058f5  lea     rcx, CLSID_WamAdmin; rclsid
0x1800058fc  call    cs:__imp_CoGetClassObject
0x180005902  mov     ebx, eax
0x180005904  test    eax, eax
0x180005906  js      loc_1800059A3
0x18000590c  mov     rcx, [rbp+var_30]
0x180005910  lea     r9, [rbp+pProxy]
0x180005914  lea     r8, IID_IIISApplicationAdmin
0x18000591b  xor     edx, edx
0x18000591d  mov     rax, [rcx]
0x180005920  mov     rax, [rax+18h]
0x180005924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005929  mov     ebx, eax
0x18000592b  test    eax, eax
0x18000592d  js      short loc_1800059A3
0x18000592f  mov     rcx, [rbp+pProxy]; pProxy
0x180005933  call    ?SetProxyImpersonationLevel@@YAJPEAUIUnknown@@K@Z; SetProxyImpersonationLevel(IUnknown *,ulong)
0x180005938  mov     ebx, eax
0x18000593a  test    eax, eax
0x18000593c  js      short loc_1800059A3
0x18000593e  mov     rcx, [rbp+pProxy]
0x180005942  mov     rdx, r15
0x180005945  mov     rax, [rcx]
0x180005948  mov     rax, [rax+30h]
0x18000594c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005951  mov     ebx, eax
0x180005953  jmp     short loc_1800059A3
0x180005955  mov     r8, [rdi+48h]; unsigned __int16 *
0x180005959  lea     rax, [rbp+arg_10]
0x18000595d  mov     rdx, [rdi+40h]; unsigned __int16 *
0x180005961  lea     rsi, [rdi+80h]
0x180005968  mov     [rsp+60h+var_38], rax; unsigned int *
0x18000596d  lea     rcx, [rdi+68h]; this
0x180005971  mov     r9d, 2; unsigned int
0x180005977  mov     [rsp+60h+ppv], rsi; struct IMSAdminBaseW **
0x18000597c  call    ?OpenAdminBaseKey@@YAJAEAVCCredentials@@PEAG1KPEAPEAUIMSAdminBaseW@@PEAK@Z; OpenAdminBaseKey(CCredentials &,ushort *,ushort *,ulong,IMSAdminBaseW * *,ulong *)
0x180005981  mov     ebx, eax
0x180005983  test    eax, eax
0x180005985  js      short loc_1800059A0
0x180005987  mov     rcx, [rsi]
0x18000598a  mov     r8, r15
0x18000598d  mov     esi, [rbp+arg_10]
0x180005990  mov     edx, esi
0x180005992  mov     rax, [rcx]
0x180005995  mov     rax, [rax+20h]
0x180005999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000599e  jmp     short loc_180005951
0x1800059a0  mov     esi, [rbp+arg_10]
0x1800059a3  mov     rcx, [rbp+var_30]
0x1800059a7  test    rcx, rcx
0x1800059aa  jz      short loc_1800059B8
0x1800059ac  mov     rax, [rcx]
0x1800059af  mov     rax, [rax+10h]
0x1800059b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b8  mov     rcx, [rbp+pProxy]
0x1800059bc  test    rcx, rcx
0x1800059bf  jz      short loc_1800059CD
0x1800059c1  mov     rax, [rcx]
0x1800059c4  mov     rax, [rax+10h]
0x1800059c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059cd  mov     rcx, [rdi+80h]; struct IMSAdminBaseW *
0x1800059d4  test    rcx, rcx
0x1800059d7  jz      short loc_1800059E4
0x1800059d9  test    esi, esi
0x1800059db  jz      short loc_1800059E4
0x1800059dd  mov     edx, esi; unsigned int
0x1800059df  call    ?CloseAdminBaseKey@@YAXPEAUIMSAdminBaseW@@K@Z; CloseAdminBaseKey(IMSAdminBaseW *,ulong)
0x1800059e4  mov     eax, ebx
0x1800059e6  mov     rbx, [rsp+60h+arg_0]
0x1800059ee  add     rsp, 60h
0x1800059f2  pop     r15
0x1800059f4  pop     r14
0x1800059f6  pop     rdi
0x1800059f7  pop     rsi
0x1800059f8  pop     rbp
0x1800059f9  retn
```
