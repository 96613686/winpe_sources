# CIdentityStore::CreateConnectedIdentity(ushort const *,ushort const *,_GUID const &)

- ea: `0x180013170`
- end: `0x1800132a6`
- name: `?CreateConnectedIdentity@CIdentityStore@@UEAAJPEBG0AEBU_GUID@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(CIdentityStore *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000dff0`
- `0x180013170`
- `0x180014430`
- `0x1800144b4`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800131e8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800131e8`

## pseudocode

```c
__int64 __fastcall CIdentityStore::CreateConnectedIdentity(
        CIdentityStore *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4)
{
  HRESULT v7; // ebx
  LPVOID ppv; // [rsp+40h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+48h] [rbp-30h] BYREF

  ppv = 0;
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((int)this, (int)&CreateConnectedIdentityStart, (int)a3, (int)a4, &v10);
  if ( a3 )
  {
    v7 = CoCreateInstance(
           &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
           0,
           0x17u,
           &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
           &ppv);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, _DWORD, _QWORD, _DWORD))(*(_QWORD *)ppv + 32LL))(
             ppv,
             a2,
             a3,
             a4,
             0,
             0,
             0);
      if ( v7 < 0 )
      {
        LODWORD(this) = (_DWORD)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            98,
            WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
            (unsigned int)v7);
        }
      }
    }
  }
  else
  {
    v7 = -2147467261;
  }
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((int)this, (int)&CreateConnectedIdentityStop, (int)a3, (int)a4, &v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180013170  mov     r11, rsp
0x180013173  mov     [r11+8], rbx
0x180013177  push    rbp
0x180013178  push    rsi
0x180013179  push    rdi
0x18001317a  sub     rsp, 60h
0x18001317e  mov     rax, cs:__security_cookie
0x180013185  xor     rax, rsp
0x180013188  mov     [rsp+78h+var_20], rax
0x18001318d  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180013194  mov     rbp, r9
0x180013197  mov     rdi, r8
0x18001319a  mov     qword ptr [r11-38h], 0
0x1800131a2  mov     rsi, rdx
0x1800131a5  jz      short loc_1800131BB
0x1800131a7  lea     rax, [r11-30h]
0x1800131ab  lea     rdx, CreateConnectedIdentityStart; int
0x1800131b2  mov     [r11-58h], rax
0x1800131b6  call    McGenEventWrite_EventWriteTransfer
0x1800131bb  test    rdi, rdi
0x1800131be  jnz     short loc_1800131CA
0x1800131c0  mov     ebx, 80004003h
0x1800131c5  jmp     loc_18001325E
0x1800131ca  xor     edx, edx; pUnkOuter
0x1800131cc  lea     rax, [rsp+78h+var_38]
0x1800131d1  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x1800131d8  mov     [rsp+78h+ppv], rax; ppv
0x1800131dd  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x1800131e4  lea     r8d, [rdx+17h]; dwClsContext
0x1800131e8  call    cs:__imp_CoCreateInstance
0x1800131ee  mov     ebx, eax
0x1800131f0  test    eax, eax
0x1800131f2  js      short loc_18001325E
0x1800131f4  mov     rcx, [rsp+78h+var_38]
0x1800131f9  mov     r9, rbp
0x1800131fc  mov     [rsp+78h+var_48], 0
0x180013204  mov     r8, rdi
0x180013207  mov     [rsp+78h+var_50], 0
0x180013210  mov     rdx, rsi
0x180013213  mov     dword ptr [rsp+78h+ppv], 0
0x18001321b  mov     rax, [rcx]
0x18001321e  mov     rax, [rax+20h]
0x180013222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013227  mov     ebx, eax
0x180013229  test    eax, eax
0x18001322b  jns     short loc_18001325E
0x18001322d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013234  lea     rax, WPP_GLOBAL_Control
0x18001323b  cmp     rcx, rax
0x18001323e  jz      short loc_18001325E
0x180013240  test    byte ptr [rcx+1Ch], 4
0x180013244  jz      short loc_18001325E
0x180013246  mov     rcx, [rcx+10h]
0x18001324a  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x180013251  mov     edx, 62h ; 'b'
0x180013256  mov     r9d, ebx
0x180013259  call    WPP_SF_d
0x18001325e  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180013265  jz      short loc_18001327D
0x180013267  lea     rax, [rsp+78h+var_30]
0x18001326c  lea     rdx, CreateConnectedIdentityStop; int
0x180013273  mov     [rsp+78h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x180013278  call    McGenEventWrite_EventWriteTransfer
0x18001327d  lea     rcx, [rsp+78h+var_38]
0x180013282  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013287  mov     eax, ebx
0x180013289  mov     rcx, [rsp+78h+var_20]
0x18001328e  xor     rcx, rsp; StackCookie
0x180013291  call    __security_check_cookie
0x180013296  mov     rbx, [rsp+78h+arg_0]
0x18001329e  add     rsp, 60h
0x1800132a2  pop     rdi
0x1800132a3  pop     rsi
0x1800132a4  pop     rbp
0x1800132a5  retn
```
