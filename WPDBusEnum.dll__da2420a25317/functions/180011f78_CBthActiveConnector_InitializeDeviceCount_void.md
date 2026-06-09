# CBthActiveConnector::_InitializeDeviceCount(void)

- ea: `0x180011f78`
- end: `0x18001204f`
- name: `?_InitializeDeviceCount@CBthActiveConnector@@AEAAJXZ`
- size: `215`
- prototype: `__int64 __fastcall(CBthActiveConnector *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006360`

## callees

- `0x180007f28`
- `0x1800080e0`
- `0x180011f78`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011faa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011faa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CBthActiveConnector::_InitializeDeviceCount(CBthActiveConnector *this)
{
  HRESULT v2; // ebx
  int v3; // edi
  int v5; // [rsp+58h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+18h] BYREF
  __int64 v7; // [rsp+68h] [rbp+20h] BYREF

  ppv = 0;
  v2 = CoCreateInstance(&CLSID_EnumBthMtpConnectors, 0, 1u, &GUID_bfdef549_9247_454f_bd82_06fe80853faa, &ppv);
  if ( v2 >= 0 )
  {
    if ( !v2 )
    {
      *((_DWORD *)this + 10) = 0;
      do
      {
        v5 = 0;
        v7 = 0;
        v3 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *, int *))(*(_QWORD *)ppv + 24LL))(ppv, 1, &v7, &v5);
        if ( !v3 )
          ++*((_DWORD *)this + 10);
        ATL::CComPtrBase<IEnumPortableDeviceConnectors>::~CComPtrBase<IEnumPortableDeviceConnectors>(&v7);
      }
      while ( !v3 );
      if ( v3 < 0 )
        v2 = v3;
    }
  }
  else if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
      (unsigned int)v2);
  }
  ATL::CComPtrBase<IEnumPortableDeviceConnectors>::~CComPtrBase<IEnumPortableDeviceConnectors>(&ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180011f78  push    rbx
0x180011f7a  push    rsi
0x180011f7b  push    rdi
0x180011f7c  sub     rsp, 30h
0x180011f80  mov     rsi, rcx
0x180011f83  mov     [rsp+48h+arg_10], 0
0x180011f8c  lea     rax, [rsp+48h+arg_10]
0x180011f91  mov     [rsp+48h+ppv], rax; ppv
0x180011f96  lea     r9, _GUID_bfdef549_9247_454f_bd82_06fe80853faa; riid
0x180011f9d  xor     edx, edx; pUnkOuter
0x180011f9f  lea     r8d, [rdx+1]; dwClsContext
0x180011fa3  lea     rcx, CLSID_EnumBthMtpConnectors; rclsid
0x180011faa  call    cs:__imp_CoCreateInstance
0x180011fb0  mov     ebx, eax
0x180011fb2  test    eax, eax
0x180011fb4  jns     short loc_180011FE9
0x180011fb6  lea     rax, WPP_GLOBAL_Control
0x180011fbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fc4  cmp     rcx, rax
0x180011fc7  jz      short loc_18001203B
0x180011fc9  test    byte ptr [rcx+1Ch], 2
0x180011fcd  jz      short loc_18001203B
0x180011fcf  mov     edx, 1Dh
0x180011fd4  mov     r9d, ebx
0x180011fd7  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180011fde  mov     rcx, [rcx+10h]
0x180011fe2  call    WPP_SF_d
0x180011fe7  jmp     short loc_18001203B
0x180011fe9  test    ebx, ebx
0x180011feb  jnz     short loc_18001203B
0x180011fed  mov     [rsi+28h], ebx
0x180011ff0  mov     [rsp+48h+arg_8], 0
0x180011ff8  mov     [rsp+48h+arg_18], 0
0x180012001  mov     rcx, [rsp+48h+arg_10]
0x180012006  mov     rax, [rcx]
0x180012009  lea     r9, [rsp+48h+arg_8]
0x18001200e  lea     r8, [rsp+48h+arg_18]
0x180012013  mov     edx, 1
0x180012018  mov     rax, [rax+18h]
0x18001201c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012021  mov     edi, eax
0x180012023  test    eax, eax
0x180012025  jnz     short loc_18001202A
0x180012027  inc     dword ptr [rsi+28h]
0x18001202a  lea     rcx, [rsp+48h+arg_18]
0x18001202f  call    ??1?$CComPtrBase@UIEnumPortableDeviceConnectors@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumPortableDeviceConnectors>::~CComPtrBase<IEnumPortableDeviceConnectors>(void)
0x180012034  test    edi, edi
0x180012036  jz      short loc_180011FF0
0x180012038  cmovs   ebx, edi
0x18001203b  lea     rcx, [rsp+48h+arg_10]
0x180012040  call    ??1?$CComPtrBase@UIEnumPortableDeviceConnectors@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumPortableDeviceConnectors>::~CComPtrBase<IEnumPortableDeviceConnectors>(void)
0x180012045  mov     eax, ebx
0x180012047  add     rsp, 30h
0x18001204b  pop     rdi
0x18001204c  pop     rsi
0x18001204d  pop     rbx
0x18001204e  retn
```
