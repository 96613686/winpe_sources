# CIdentityStore::DeleteConnectedIdentity(ushort const *,_GUID const &)

- ea: `0x1800132b0`
- end: `0x180013425`
- name: `?DeleteConnectedIdentity@CIdentityStore@@UEAAJPEBGAEBU_GUID@@@Z`
- size: `373`
- prototype: `__int64 __fastcall(CIdentityStore *this, const unsigned __int16 *, const struct _GUID *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000dff0`
- `0x1800132b0`
- `0x180014430`
- `0x1800144b4`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001332f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001332f`

## pseudocode

```c
__int64 __fastcall CIdentityStore::DeleteConnectedIdentity(
        CIdentityStore *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        int a4)
{
  HRESULT v6; // ebx
  __int64 v7; // rdx
  __int64 v9; // [rsp+30h] [rbp-38h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-28h] BYREF

  ppv = 0;
  v9 = 0;
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((int)this, (int)&DeleteConnectedIdentityStart, (int)a3, a4, &v11);
  if ( !a2 )
  {
    v6 = -2147467261;
    goto LABEL_15;
  }
  v6 = CoCreateInstance(
         &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
         0,
         0x17u,
         &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
         &ppv);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, _QWORD, const struct _GUID *, __int64 *))(*(_QWORD *)ppv + 48LL))(
           ppv,
           a2,
           0,
           a3,
           &v9);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 32LL))(v9);
      if ( v6 < 0 )
      {
        this = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v7 = 100;
          goto LABEL_14;
        }
      }
    }
    else
    {
      this = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v7 = 99;
LABEL_14:
        WPP_SF_d(*((_QWORD *)this + 2), v7, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, (unsigned int)v6);
      }
    }
  }
LABEL_15:
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((int)this, (int)&DeleteConnectedIdentityStop, (int)a3, a4, &v11);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800132b0  mov     r11, rsp
0x1800132b3  mov     [r11+8], rbx
0x1800132b7  mov     [r11+20h], rsi
0x1800132bb  push    rdi
0x1800132bc  sub     rsp, 60h
0x1800132c0  mov     rax, cs:__security_cookie
0x1800132c7  xor     rax, rsp
0x1800132ca  mov     [rsp+68h+var_18], rax
0x1800132cf  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x1800132d6  mov     rsi, r8
0x1800132d9  mov     rdi, rdx
0x1800132dc  mov     qword ptr [r11-30h], 0
0x1800132e4  mov     qword ptr [r11-38h], 0
0x1800132ec  jz      short loc_180013302
0x1800132ee  lea     rax, [r11-28h]
0x1800132f2  lea     rdx, DeleteConnectedIdentityStart; int
0x1800132f9  mov     [r11-48h], rax
0x1800132fd  call    McGenEventWrite_EventWriteTransfer
0x180013302  test    rdi, rdi
0x180013305  jnz     short loc_180013311
0x180013307  mov     ebx, 80004003h
0x18001330c  jmp     loc_1800133D1
0x180013311  xor     edx, edx; pUnkOuter
0x180013313  lea     rax, [rsp+68h+var_30]
0x180013318  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x18001331f  mov     [rsp+68h+ppv], rax; ppv
0x180013324  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x18001332b  lea     r8d, [rdx+17h]; dwClsContext
0x18001332f  call    cs:__imp_CoCreateInstance
0x180013335  mov     ebx, eax
0x180013337  test    eax, eax
0x180013339  js      loc_1800133D1
0x18001333f  mov     rcx, [rsp+68h+var_30]
0x180013344  lea     rdx, [rsp+68h+var_38]
0x180013349  mov     [rsp+68h+ppv], rdx
0x18001334e  mov     r9, rsi
0x180013351  xor     r8d, r8d
0x180013354  mov     rdx, rdi
0x180013357  mov     rax, [rcx]
0x18001335a  mov     rax, [rax+30h]
0x18001335e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013363  mov     ebx, eax
0x180013365  test    eax, eax
0x180013367  jns     short loc_180013389
0x180013369  mov     rcx, cs:WPP_GLOBAL_Control
0x180013370  lea     rax, WPP_GLOBAL_Control
0x180013377  cmp     rcx, rax
0x18001337a  jz      short loc_1800133D1
0x18001337c  test    byte ptr [rcx+1Ch], 4
0x180013380  jz      short loc_1800133D1
0x180013382  mov     edx, 63h ; 'c'
0x180013387  jmp     short loc_1800133BE
0x180013389  mov     rcx, [rsp+68h+var_38]
0x18001338e  mov     rax, [rcx]
0x180013391  mov     rax, [rax+20h]
0x180013395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001339a  mov     ebx, eax
0x18001339c  test    eax, eax
0x18001339e  jns     short loc_1800133D1
0x1800133a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133a7  lea     rax, WPP_GLOBAL_Control
0x1800133ae  cmp     rcx, rax
0x1800133b1  jz      short loc_1800133D1
0x1800133b3  test    byte ptr [rcx+1Ch], 4
0x1800133b7  jz      short loc_1800133D1
0x1800133b9  mov     edx, 64h ; 'd'
0x1800133be  mov     rcx, [rcx+10h]
0x1800133c2  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x1800133c9  mov     r9d, ebx
0x1800133cc  call    WPP_SF_d
0x1800133d1  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x1800133d8  jz      short loc_1800133F0
0x1800133da  lea     rax, [rsp+68h+var_28]
0x1800133df  lea     rdx, DeleteConnectedIdentityStop; int
0x1800133e6  mov     [rsp+68h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x1800133eb  call    McGenEventWrite_EventWriteTransfer
0x1800133f0  lea     rcx, [rsp+68h+var_38]
0x1800133f5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800133fa  lea     rcx, [rsp+68h+var_30]
0x1800133ff  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013404  mov     eax, ebx
0x180013406  mov     rcx, [rsp+68h+var_18]
0x18001340b  xor     rcx, rsp; StackCookie
0x18001340e  call    __security_check_cookie
0x180013413  lea     r11, [rsp+68h+var_8]
0x180013418  mov     rbx, [r11+10h]
0x18001341c  mov     rsi, [r11+28h]
0x180013420  mov     rsp, r11
0x180013423  pop     rdi
0x180013424  retn
```
