# CDeviceHandler::_SuppressUX(_GUID *)

- ea: `0x180009f44`
- end: `0x18000a0ba`
- name: `?_SuppressUX@CDeviceHandler@@AEAAXPEAU_GUID@@@Z`
- size: `374`
- prototype: `void __fastcall(CDeviceHandler *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008c5c`

## callees

- `0x180009f44`
- `0x18000a644`
- `0x18000a778`
- `0x18001380e`
- `0x180013840`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a000`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a000`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009fc8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009fc8`

## pseudocode

```c
void __fastcall CDeviceHandler::_SuppressUX(CDeviceHandler *this, struct _GUID *a2)
{
  _QWORD *v3; // rcx
  HRESULT v4; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-68h] BYREF

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    memset_0(sz, 0, 0x4Eu);
    if ( StringFromGUID2(a2, sz, 39) > 0 )
    {
      ppv = 0;
      v4 = CoCreateInstance(
             &GUID_e4785230_0e43_47dc_826a_07dbc3aa63d8,
             0,
             1u,
             &GUID_46147e3d_0380_450d_b48e_cca7f77d1c69,
             &ppv);
      if ( v4 >= 0 )
        v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, OLECHAR *))(*(_QWORD *)ppv + 88LL))(ppv, 1, sz);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( v4 >= 0 )
        goto LABEL_15;
    }
    v3 = WPP_GLOBAL_Control;
  }
  if ( v3 == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)v3 + 28) & 2) != 0 )
  {
    WPP_SF_d(v3[2], 61, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
LABEL_15:
    v3 = WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x20) != 0 )
    WPP_SF_(v3[2], 62, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
}

```

## disassembly

```asm
0x180009f44  mov     [rsp+arg_0], rbx
0x180009f49  push    rdi
0x180009f4a  sub     rsp, 0A0h
0x180009f51  mov     rax, cs:__security_cookie
0x180009f58  xor     rax, rsp
0x180009f5b  mov     [rsp+0A8h+var_18], rax
0x180009f63  mov     rbx, rdx
0x180009f66  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f6d  lea     rdi, WPP_GLOBAL_Control
0x180009f74  cmp     rcx, rdi
0x180009f77  jz      short loc_180009F9B
0x180009f79  test    byte ptr [rcx+1Ch], 20h
0x180009f7d  jz      short loc_180009F9B
0x180009f7f  mov     rcx, [rcx+10h]
0x180009f83  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x180009f8a  mov     edx, 3Ch ; '<'
0x180009f8f  call    WPP_SF_
0x180009f94  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f9b  test    rbx, rbx
0x180009f9e  jnz     short loc_180009FAA
0x180009fa0  mov     ebx, 80004003h
0x180009fa5  jmp     loc_18000A04F
0x180009faa  xor     edx, edx; Val
0x180009fac  lea     rcx, [rsp+0A8h+sz]; void *
0x180009fb1  lea     r8d, [rdx+4Eh]; Size
0x180009fb5  call    memset_0
0x180009fba  mov     r8d, 27h ; '''; cchMax
0x180009fc0  lea     rdx, [rsp+0A8h+sz]; lpsz
0x180009fc5  mov     rcx, rbx; rguid
0x180009fc8  call    cs:__imp_StringFromGUID2
0x180009fce  test    eax, eax
0x180009fd0  jg      short loc_180009FD9
0x180009fd2  mov     ebx, 80004005h
0x180009fd7  jmp     short loc_18000A048
0x180009fd9  xor     edx, edx; pUnkOuter
0x180009fdb  mov     [rsp+0A8h+var_78], 0
0x180009fe4  lea     rax, [rsp+0A8h+var_78]
0x180009fe9  lea     r9, _GUID_46147e3d_0380_450d_b48e_cca7f77d1c69; riid
0x180009ff0  mov     [rsp+0A8h+ppv], rax; ppv
0x180009ff5  lea     rcx, _GUID_e4785230_0e43_47dc_826a_07dbc3aa63d8; rclsid
0x180009ffc  lea     r8d, [rdx+1]; dwClsContext
0x18000a000  call    cs:__imp_CoCreateInstance
0x18000a006  mov     ebx, eax
0x18000a008  test    eax, eax
0x18000a00a  js      short loc_18000A02E
0x18000a00c  mov     rcx, [rsp+0A8h+var_78]
0x18000a011  lea     r8, [rsp+0A8h+sz]
0x18000a016  mov     r9d, 7
0x18000a01c  mov     rax, [rcx]
0x18000a01f  lea     edx, [r9-6]
0x18000a023  mov     rax, [rax+58h]
0x18000a027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a02c  mov     ebx, eax
0x18000a02e  mov     rcx, [rsp+0A8h+var_78]
0x18000a033  test    rcx, rcx
0x18000a036  jz      short loc_18000A044
0x18000a038  mov     rax, [rcx]
0x18000a03b  mov     rax, [rax+10h]
0x18000a03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a044  test    ebx, ebx
0x18000a046  jns     short loc_18000A072
0x18000a048  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a04f  cmp     rcx, rdi
0x18000a052  jz      short loc_18000A099
0x18000a054  test    byte ptr [rcx+1Ch], 2
0x18000a058  jz      short loc_18000A079
0x18000a05a  mov     rcx, [rcx+10h]
0x18000a05e  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x18000a065  mov     edx, 3Dh ; '='
0x18000a06a  mov     r9d, ebx
0x18000a06d  call    WPP_SF_d
0x18000a072  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a079  cmp     rcx, rdi
0x18000a07c  jz      short loc_18000A099
0x18000a07e  test    byte ptr [rcx+1Ch], 20h
0x18000a082  jz      short loc_18000A099
0x18000a084  mov     rcx, [rcx+10h]
0x18000a088  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x18000a08f  mov     edx, 3Eh ; '>'
0x18000a094  call    WPP_SF_
0x18000a099  mov     rcx, [rsp+0A8h+var_18]
0x18000a0a1  xor     rcx, rsp; StackCookie
0x18000a0a4  call    __security_check_cookie
0x18000a0a9  mov     rbx, [rsp+0A8h+arg_0]
0x18000a0b1  add     rsp, 0A0h
0x18000a0b8  pop     rdi
0x18000a0b9  retn
```
