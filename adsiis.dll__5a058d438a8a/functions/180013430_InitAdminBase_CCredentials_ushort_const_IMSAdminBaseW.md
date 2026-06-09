# InitAdminBase(CCredentials &,ushort const *,IMSAdminBaseW * *)

- ea: `0x180013430`
- end: `0x180013643`
- name: `?InitAdminBase@@YAJAEAVCCredentials@@PEBGPEAPEAUIMSAdminBaseW@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(struct CCredentials *this, const unsigned __int16 *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001364c`
- `0x18001441c`

## callees

- `0x180012cf8`
- `0x180013430`
- `0x180014544`
- `0x180019444`
- `0x180019648`
- `0x18001969c`
- `0x1800196f0`
- `0x180019768`
- `0x18001bf30`
- `0x18001bf94`
- `0x18001c0d4`
- `0x18001c2dc`
- `0x18001e010`

## import_xrefs

- `ole32!CoGetClassObject` at `0x1800134ea`
- `ole32!CoGetClassObject` at `0x1800134ea`
- `KERNEL32!GetCurrentThreadId` at `0x1800135b1`
- `KERNEL32!GetCurrentThreadId` at `0x1800135b1`

## pseudocode

```c
__int64 __fastcall InitAdminBase(struct CCredentials *this, const unsigned __int16 *a2, struct IUnknown **a3)
{
  int UserNameW; // ebx
  unsigned int v7; // edx
  struct _COSERVERINFO *ServerInfoStruct; // rbx
  int ClassObject; // edi
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  struct IUnknown *v13; // rbx
  LPVOID *ppv; // [rsp+20h] [rbp-29h]
  int v16; // [rsp+30h] [rbp-19h]
  OLECHAR *psz; // [rsp+40h] [rbp-9h] BYREF
  struct IUnknown *v18; // [rsp+48h] [rbp-1h] BYREF
  struct IUnknown *v19; // [rsp+50h] [rbp+7h] BYREF
  OLECHAR *v20; // [rsp+58h] [rbp+Fh] BYREF
  unsigned int v21; // [rsp+60h] [rbp+17h] BYREF
  _BYTE v22[40]; // [rsp+68h] [rbp+1Fh] BYREF
  IUnknown *pProxy; // [rsp+C8h] [rbp+7Fh] BYREF

  v19 = 0;
  v18 = 0;
  pProxy = 0;
  psz = 0;
  v20 = 0;
  v21 = 0;
  UserNameW = CCredentials::GetUserNameW(this, (struct CCredentials::UserName *)&psz);
  if ( UserNameW < 0
    || (UserNameW = CCredentials::GetPassword(this, (struct CCredentials::Password *)&v20), UserNameW < 0) )
  {
    CCredentials::FreePassword(&v20, &v21);
    CCredentials::FreeUserName(&psz);
    return (unsigned int)UserNameW;
  }
  else
  {
    CComAuthInfo2::CComAuthInfo2((CComAuthInfo2 *)v22, a2, psz, v20);
    ServerInfoStruct = CComAuthInfo2::CreateServerInfoStruct((CComAuthInfo2 *)v22, v7);
    ClassObject = CoGetClassObject(&CLSID_MSAdminBase_W, 0x15u, ServerInfoStruct, &IID_IClassFactory, (LPVOID *)&v19);
    if ( ClassObject >= 0 )
    {
      ClassObject = CComAuthInfo2::ApplyProxyBlanket((CComAuthInfo2 *)v22, v19, v10);
      if ( ClassObject >= 0 )
      {
        ClassObject = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, GUID *, IUnknown **))v19->lpVtbl[1].QueryInterface)(
                        v19,
                        0,
                        &IID_IMSAdminBase_W,
                        &pProxy);
        if ( ClassObject >= 0 )
        {
          ClassObject = SetProxyImpersonationLevel(pProxy);
          if ( ClassObject >= 0 )
          {
            ClassObject = CComAuthInfo2::ApplyProxyBlanket((CComAuthInfo2 *)v22, pProxy, v11);
            if ( ClassObject >= 0 )
            {
              ClassObject = ((__int64 (__fastcall *)(IUnknown *, struct IUnknown **))pProxy->lpVtbl[10].Release)(
                              pProxy,
                              &v18);
              ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
              pProxy = 0;
              if ( ClassObject >= 0 )
              {
                ClassObject = CComAuthInfo2::ApplyProxyBlanket((CComAuthInfo2 *)v22, v18, v12);
                if ( ClassObject >= 0 )
                {
                  *a3 = v18;
                  CComAuthInfo2::FreeServerInfoStruct(ServerInfoStruct);
                }
              }
            }
          }
        }
      }
    }
    v13 = v18;
    v16 = ClassObject;
    LODWORD(ppv) = GetCurrentThreadId();
    AdsiTrace(L"InitAdminBase: %s, [%s, %s] %lu -> ABO=%p, hr=%08x\n", a2, psz, v20, ppv, v13, v16);
    if ( v19 )
      ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->Release)(v19);
    CComAuthInfo2::~CComAuthInfo2((CComAuthInfo2 *)v22);
    CCredentials::FreePassword(&v20, &v21);
    CCredentials::FreeUserName(&psz);
    return (unsigned int)ClassObject;
  }
}

```

## disassembly

```asm
0x180013430  mov     [rsp-8+arg_0], rbx
0x180013435  mov     [rsp-8+arg_8], rsi
0x18001343a  push    rbp
0x18001343b  push    rdi
0x18001343c  push    r14
0x18001343e  lea     rbp, [rsp-47h]
0x180013443  sub     rsp, 90h
0x18001344a  mov     rsi, rdx
0x18001344d  mov     [rbp+57h+var_50], 0
0x180013455  lea     rdx, [rbp+57h+psz]; struct CCredentials::UserName *
0x180013459  mov     [rbp+57h+var_58], 0
0x180013461  mov     r14, r8
0x180013464  mov     [rbp+57h+pProxy], 0
0x18001346c  mov     rdi, rcx
0x18001346f  mov     [rbp+57h+psz], 0
0x180013477  mov     [rbp+57h+var_48], 0
0x18001347f  mov     [rbp+57h+var_40], 0
0x180013486  call    ?GetUserNameW@CCredentials@@QEBAJAEAVUserName@1@@Z; CCredentials::GetUserNameW(CCredentials::UserName &)
0x18001348b  mov     ebx, eax
0x18001348d  test    eax, eax
0x18001348f  js      loc_180013613
0x180013495  lea     rdx, [rbp+57h+var_48]; struct CCredentials::Password *
0x180013499  mov     rcx, rdi; this
0x18001349c  call    ?GetPassword@CCredentials@@QEBAJAEAVPassword@1@@Z; CCredentials::GetPassword(CCredentials::Password &)
0x1800134a1  mov     ebx, eax
0x1800134a3  test    eax, eax
0x1800134a5  js      loc_180013613
0x1800134ab  mov     r9, [rbp+57h+var_48]; OLECHAR *
0x1800134af  lea     rcx, [rbp+57h+var_38]; this
0x1800134b3  mov     r8, [rbp+57h+psz]; psz
0x1800134b7  mov     rdx, rsi; unsigned __int16 *
0x1800134ba  call    ??0CComAuthInfo2@@QEAA@PEBG00@Z; CComAuthInfo2::CComAuthInfo2(ushort const *,ushort const *,ushort const *)
0x1800134bf  lea     rcx, [rbp+57h+var_38]; this
0x1800134c3  call    ?CreateServerInfoStruct@CComAuthInfo2@@QEBAPEAU_COSERVERINFO@@K@Z; CComAuthInfo2::CreateServerInfoStruct(ulong)
0x1800134c8  mov     rbx, rax
0x1800134cb  lea     r9, IID_IClassFactory; riid
0x1800134d2  lea     rax, [rbp+57h+var_50]
0x1800134d6  mov     r8, rbx; pvReserved
0x1800134d9  mov     edx, 15h; dwClsContext
0x1800134de  mov     [rsp+0A0h+ppv], rax; ppv
0x1800134e3  lea     rcx, CLSID_MSAdminBase_W; rclsid
0x1800134ea  call    cs:__imp_CoGetClassObject
0x1800134f0  mov     edi, eax
0x1800134f2  test    eax, eax
0x1800134f4  js      loc_1800135AD
0x1800134fa  mov     rdx, [rbp+57h+var_50]; struct IUnknown *
0x1800134fe  lea     rcx, [rbp+57h+var_38]; this
0x180013502  call    ?ApplyProxyBlanket@CComAuthInfo2@@QEAAJPEAUIUnknown@@K@Z; CComAuthInfo2::ApplyProxyBlanket(IUnknown *,ulong)
0x180013507  mov     edi, eax
0x180013509  test    eax, eax
0x18001350b  js      loc_1800135AD
0x180013511  mov     rcx, [rbp+57h+var_50]
0x180013515  lea     r9, [rbp+57h+pProxy]
0x180013519  lea     r8, IID_IMSAdminBase_W
0x180013520  xor     edx, edx
0x180013522  mov     rax, [rcx]
0x180013525  mov     rax, [rax+18h]
0x180013529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001352e  mov     edi, eax
0x180013530  test    eax, eax
0x180013532  js      short loc_1800135AD
0x180013534  mov     rcx, [rbp+57h+pProxy]; pProxy
0x180013538  call    ?SetProxyImpersonationLevel@@YAJPEAUIUnknown@@K@Z; SetProxyImpersonationLevel(IUnknown *,ulong)
0x18001353d  mov     edi, eax
0x18001353f  test    eax, eax
0x180013541  js      short loc_1800135AD
0x180013543  mov     rdx, [rbp+57h+pProxy]; struct IUnknown *
0x180013547  lea     rcx, [rbp+57h+var_38]; this
0x18001354b  call    ?ApplyProxyBlanket@CComAuthInfo2@@QEAAJPEAUIUnknown@@K@Z; CComAuthInfo2::ApplyProxyBlanket(IUnknown *,ulong)
0x180013550  mov     edi, eax
0x180013552  test    eax, eax
0x180013554  js      short loc_1800135AD
0x180013556  mov     rcx, [rbp+57h+pProxy]
0x18001355a  lea     rdx, [rbp+57h+var_58]
0x18001355e  mov     rax, [rcx]
0x180013561  mov     rax, [rax+100h]
0x180013568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001356d  mov     rcx, [rbp+57h+pProxy]
0x180013571  mov     edi, eax
0x180013573  mov     rax, [rcx]
0x180013576  mov     rax, [rax+10h]
0x18001357a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001357f  mov     [rbp+57h+pProxy], 0
0x180013587  test    edi, edi
0x180013589  js      short loc_1800135AD
0x18001358b  mov     rdx, [rbp+57h+var_58]; struct IUnknown *
0x18001358f  lea     rcx, [rbp+57h+var_38]; this
0x180013593  call    ?ApplyProxyBlanket@CComAuthInfo2@@QEAAJPEAUIUnknown@@K@Z; CComAuthInfo2::ApplyProxyBlanket(IUnknown *,ulong)
0x180013598  mov     edi, eax
0x18001359a  test    eax, eax
0x18001359c  js      short loc_1800135AD
0x18001359e  mov     rax, [rbp+57h+var_58]
0x1800135a2  mov     rcx, rbx; Block
0x1800135a5  mov     [r14], rax
0x1800135a8  call    ?FreeServerInfoStruct@CComAuthInfo2@@SAXPEAU_COSERVERINFO@@@Z; CComAuthInfo2::FreeServerInfoStruct(_COSERVERINFO *)
0x1800135ad  mov     rbx, [rbp+57h+var_58]
0x1800135b1  call    cs:__imp_GetCurrentThreadId
0x1800135b7  mov     r9, [rbp+57h+var_48]
0x1800135bb  lea     rcx, aInitadminbaseS; "InitAdminBase: %s, [%s, %s] %lu -> ABO="...
0x1800135c2  mov     r8, [rbp+57h+psz]
0x1800135c6  mov     rdx, rsi
0x1800135c9  mov     [rsp+0A0h+var_70], edi
0x1800135cd  mov     [rsp+0A0h+var_78], rbx
0x1800135d2  mov     dword ptr [rsp+0A0h+ppv], eax
0x1800135d6  call    ?AdsiTrace@@YAXPEBGZZ; AdsiTrace(ushort const *,...)
0x1800135db  mov     rcx, [rbp+57h+var_50]
0x1800135df  test    rcx, rcx
0x1800135e2  jz      short loc_1800135F0
0x1800135e4  mov     rax, [rcx]
0x1800135e7  mov     rax, [rax+10h]
0x1800135eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135f0  lea     rcx, [rbp+57h+var_38]; this
0x1800135f4  call    ??1CComAuthInfo2@@QEAA@XZ; CComAuthInfo2::~CComAuthInfo2(void)
0x1800135f9  lea     rdx, [rbp+57h+var_40]; unsigned int *
0x1800135fd  lea     rcx, [rbp+57h+var_48]; unsigned __int16 **
0x180013601  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x180013606  lea     rcx, [rbp+57h+psz]; unsigned __int16 **
0x18001360a  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x18001360f  mov     eax, edi
0x180013611  jmp     short loc_18001362B
0x180013613  lea     rdx, [rbp+57h+var_40]; unsigned int *
0x180013617  lea     rcx, [rbp+57h+var_48]; unsigned __int16 **
0x18001361b  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x180013620  lea     rcx, [rbp+57h+psz]; unsigned __int16 **
0x180013624  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x180013629  mov     eax, ebx
0x18001362b  lea     r11, [rsp+0A0h+var_10]
0x180013633  mov     rbx, [r11+20h]
0x180013637  mov     rsi, [r11+28h]
0x18001363b  mov     rsp, r11
0x18001363e  pop     r14
0x180013640  pop     rdi
0x180013641  pop     rbp
0x180013642  retn
```
