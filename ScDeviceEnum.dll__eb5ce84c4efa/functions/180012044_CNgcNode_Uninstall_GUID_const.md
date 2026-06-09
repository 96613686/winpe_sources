# CNgcNode::Uninstall(_GUID const &)

- ea: `0x180012044`
- end: `0x1800122fc`
- name: `?Uninstall@CNgcNode@@SAJAEBU_GUID@@@Z`
- size: `696`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000fc60`

## callees

- `0x180006d40`
- `0x180007178`
- `0x1800071d4`
- `0x180008bbc`
- `0x180009840`
- `0x1800119fc`
- `0x180011b9c`
- `0x180011dcc`
- `0x180012044`
- `0x180012304`
- `0x180012a68`
- `0x180012d48`
- `0x18001e020`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x180012156`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x180012156`

## string_xrefs

- `0x180012071`: `CNgcNode::Uninstall`

## pseudocode

```c
__int64 __fastcall CNgcNode::Uninstall(GUID *rguid)
{
  __int64 v2; // rcx
  int Node; // ebx
  __int64 v4; // rdx
  const unsigned __int16 *v5; // rcx
  int Objects; // [rsp+40h] [rbp-C0h] BYREF
  int v8; // [rsp+44h] [rbp-BCh] BYREF
  int v9; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v10; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v11; // [rsp+58h] [rbp-A8h]
  __int64 v12; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v13[2]; // [rsp+68h] [rbp-98h] BYREF
  __int16 v14; // [rsp+78h] [rbp-88h]
  _QWORD *v15; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v16[3]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v17[3]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v18; // [rsp+B8h] [rbp-48h]
  int v19; // [rsp+C0h] [rbp-40h] BYREF
  DEVPROPKEY v20; // [rsp+C8h] [rbp-38h]
  int v21; // [rsp+DCh] [rbp-24h]
  __int64 v22; // [rsp+E0h] [rbp-20h]
  int v23; // [rsp+E8h] [rbp-18h]
  int v24; // [rsp+ECh] [rbp-14h]
  GUID *v25; // [rsp+F0h] [rbp-10h]
  int v26; // [rsp+F8h] [rbp-8h]
  __int128 v27; // [rsp+100h] [rbp+0h]
  int v28; // [rsp+110h] [rbp+10h]
  int v29; // [rsp+114h] [rbp+14h]
  __int64 v30; // [rsp+118h] [rbp+18h]
  int v31; // [rsp+120h] [rbp+20h]
  int v32; // [rsp+124h] [rbp+24h]
  GUID *v33; // [rsp+128h] [rbp+28h]
  char v34[24]; // [rsp+130h] [rbp+30h] BYREF

  Objects = 0;
  v9 = 0;
  strcpy(v34, "CNgcNode::Uninstall");
  v16[0] = v34;
  v16[1] = &v9;
  v16[2] = &Objects;
  lambda_842321e91a56fa77c6ee6a375ceaa14c_::operator()(v16);
  v9 = 1;
  v15 = v16;
  v19 = 2;
  v20 = DEVPKEY_DeviceInterface_ClassGuid;
  v21 = 0;
  v22 = 0;
  v23 = 13;
  v24 = 16;
  v25 = &GUID_DEVINTERFACE_NGC_CONTAINER;
  v26 = 2;
  v27 = DEVPKEY_Device_NgcContainerId;
  v28 = 2;
  v29 = 0;
  v30 = 0;
  v31 = 13;
  v32 = 16;
  v33 = rguid;
  v12 = 0;
  v8 = 0;
  Objects = DevGetObjects(1, 0, 0, 0, 2, &v19, &v8, &v12);
  if ( Objects >= 0 )
  {
    v13[0] = &v12;
    v13[1] = &v8;
    v14 = 256;
    if ( v8 )
    {
      v10 = (__int64)&Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable';
      v11 = 0;
      v18 = 7;
      v17[2] = 0;
      LOWORD(v17[0]) = 0;
      Node = CNgcNode::_CreateNode(rguid, (__int64)&v10, (__int64)v17);
      Objects = Node;
      if ( Node >= 0 )
      {
        Node = CNgcNode::_SetLifetime(v11, 0);
        Objects = Node;
        if ( Node >= 0 )
        {
          Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(&v10);
          v5 = (const unsigned __int16 *)v17;
          if ( v18 >= 8 )
            v5 = v17[0];
          Node = CNgcNode::_UninstallNode(v5);
          Objects = Node;
        }
      }
      LOBYTE(v4) = 1;
      std::wstring::_Tidy(v17, v4, 0);
      v10 = (__int64)&Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(&v10);
    }
    else
    {
      Objects = 0;
      WppTraceIndent(v2, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids,
          WPP_pszIndent);
      }
      Node = Objects;
    }
    wil::details::ScopeExitFnGuard__lambda_07b0745ddc92eb413bee6b1b57a85b42___::operator()(v13);
  }
  else
  {
    WppTraceIndent(v2, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)&WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids,
        (_DWORD)WPP_pszIndent,
        Objects);
    }
    Node = Objects;
  }
  WppTraceUnwinder__lambda_842321e91a56fa77c6ee6a375ceaa14c____::_WppTraceUnwinder__lambda_842321e91a56fa77c6ee6a375ceaa14c____(&v15);
  return (unsigned int)Node;
}

```

## disassembly

```asm
0x180012044  push    rbp
0x180012046  push    rbx
0x180012047  push    rdi
0x180012048  push    r14
0x18001204a  lea     rbp, [rsp-58h]
0x18001204f  sub     rsp, 158h
0x180012056  mov     rax, cs:__security_cookie
0x18001205d  xor     rax, rsp
0x180012060  mov     [rbp+70h+var_28], rax
0x180012064  mov     rbx, rcx
0x180012067  xor     edi, edi
0x180012069  mov     [rsp+170h+var_130], edi
0x18001206d  mov     [rsp+170h+var_128], edi
0x180012071  movups  xmm0, xmmword ptr cs:aCngcnodeUninst; "CNgcNode::Uninstall"
0x180012078  movups  xmmword ptr [rbp+70h+var_40], xmm0
0x18001207c  mov     eax, dword ptr cs:aCngcnodeUninst+10h; "all"
0x180012082  mov     dword ptr [rbp+70h+var_40+10h], eax
0x180012085  lea     rax, [rbp+70h+var_40]
0x180012089  mov     [rbp+70h+var_E8], rax
0x18001208d  lea     rax, [rsp+170h+var_128]
0x180012092  mov     [rbp+70h+var_E0], rax
0x180012096  lea     rax, [rsp+170h+var_130]
0x18001209b  mov     [rbp+70h+var_D8], rax
0x18001209f  lea     rcx, [rbp+70h+var_E8]
0x1800120a3  call    _lambda_842321e91a56fa77c6ee6a375ceaa14c___operator__
0x1800120a8  mov     [rsp+170h+var_128], 1
0x1800120b0  lea     rax, [rbp+70h+var_E8]
0x1800120b4  mov     [rbp+70h+var_F0], rax
0x1800120b8  lea     r14d, [rdi+2]
0x1800120bc  mov     [rbp+70h+var_B0], r14d
0x1800120c0  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x1800120c7  movups  [rbp+70h+var_A8], xmm0
0x1800120cb  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x1800120d1  mov     [rbp+70h+var_98], eax
0x1800120d4  mov     [rbp+70h+var_94], edi
0x1800120d7  mov     [rbp+70h+var_90], rdi
0x1800120db  mov     [rbp+70h+var_88], 0Dh
0x1800120e2  lea     ecx, [rdi+10h]
0x1800120e5  mov     [rbp+70h+var_84], ecx
0x1800120e8  lea     rax, GUID_DEVINTERFACE_NGC_CONTAINER
0x1800120ef  mov     [rbp+70h+var_80], rax
0x1800120f3  mov     [rbp+70h+var_78], r14d
0x1800120f7  movups  xmm0, cs:DEVPKEY_Device_NgcContainerId
0x1800120fe  movaps  [rbp+70h+var_70], xmm0
0x180012102  mov     eax, cs:dword_180024718
0x180012108  mov     [rbp+70h+var_60], eax
0x18001210b  mov     [rbp+70h+var_5C], edi
0x18001210e  mov     [rbp+70h+var_58], rdi
0x180012112  mov     [rbp+70h+var_50], 0Dh
0x180012119  mov     [rbp+70h+var_4C], ecx
0x18001211c  mov     [rbp+70h+var_48], rbx
0x180012120  mov     [rsp+170h+var_110], rdi
0x180012125  mov     [rsp+170h+var_12C], edi
0x180012129  lea     rax, [rsp+170h+var_110]
0x18001212e  mov     [rsp+170h+var_138], rax
0x180012133  lea     rax, [rsp+170h+var_12C]
0x180012138  mov     [rsp+170h+var_140], rax
0x18001213d  lea     rax, [rbp+70h+var_B0]
0x180012141  mov     [rsp+170h+var_148], rax
0x180012146  mov     dword ptr [rsp+170h+var_150], r14d
0x18001214b  xor     r9d, r9d
0x18001214e  xor     r8d, r8d
0x180012151  xor     edx, edx
0x180012153  lea     ecx, [rdi+1]
0x180012156  call    cs:__imp_DevGetObjects
0x18001215c  mov     [rsp+170h+var_130], eax
0x180012160  test    eax, eax
0x180012162  jns     short loc_1800121B6
0x180012164  mov     edx, r14d
0x180012167  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001216c  lea     rax, WPP_GLOBAL_Control
0x180012173  mov     rcx, cs:WPP_GLOBAL_Control
0x18001217a  cmp     rcx, rax
0x18001217d  jz      short loc_1800121AD
0x18001217f  test    byte ptr [rcx+1Ch], 1
0x180012183  jz      short loc_1800121AD
0x180012185  cmp     [rcx+19h], r14b
0x180012189  jb      short loc_1800121AD
0x18001218b  lea     edx, [rdi+0Ch]
0x18001218e  mov     eax, [rsp+170h+var_130]
0x180012192  mov     dword ptr [rsp+170h+var_150], eax
0x180012196  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001219d  lea     r8, WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids
0x1800121a4  mov     rcx, [rcx+10h]
0x1800121a8  call    WPP_SF_sd
0x1800121ad  mov     ebx, [rsp+170h+var_130]
0x1800121b1  jmp     loc_1800122D8
0x1800121b6  lea     rax, [rsp+170h+var_110]
0x1800121bb  mov     [rsp+170h+var_108], rax
0x1800121c0  lea     rax, [rsp+170h+var_12C]
0x1800121c5  mov     [rsp+170h+var_100], rax
0x1800121ca  mov     [rsp+170h+var_F8], 100h
0x1800121d1  cmp     [rsp+170h+var_12C], edi
0x1800121d5  jnz     short loc_180012227
0x1800121d7  mov     [rsp+170h+var_130], edi
0x1800121db  mov     edx, r14d
0x1800121de  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800121e3  lea     rax, WPP_GLOBAL_Control
0x1800121ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121f1  cmp     rcx, rax
0x1800121f4  jz      short loc_18001221E
0x1800121f6  test    byte ptr [rcx+1Ch], 1
0x1800121fa  jz      short loc_18001221E
0x1800121fc  cmp     byte ptr [rcx+19h], 3
0x180012200  jb      short loc_18001221E
0x180012202  mov     edx, 0Dh
0x180012207  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001220e  lea     r8, WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids
0x180012215  mov     rcx, [rcx+10h]
0x180012219  call    WPP_SF_s
0x18001221e  mov     ebx, [rsp+170h+var_130]
0x180012222  jmp     loc_1800122CD
0x180012227  lea     r14, ??_7?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable'
0x18001222e  mov     [rsp+170h+var_120], r14
0x180012233  mov     [rsp+170h+var_118], rdi
0x180012238  mov     [rbp+70h+var_B8], 7
0x180012240  mov     [rbp+70h+var_C0], rdi
0x180012244  mov     word ptr [rbp+70h+var_D0], di
0x180012248  lea     rax, [rbp+70h+var_D0]
0x18001224c  mov     [rsp+170h+var_148], rax; __int64
0x180012251  lea     rax, [rsp+170h+var_120]
0x180012256  mov     [rsp+170h+var_150], rax; __int64
0x18001225b  xor     r9d, r9d
0x18001225e  xor     r8d, r8d
0x180012261  xor     edx, edx
0x180012263  mov     rcx, rbx; rguid
0x180012266  call    ?_CreateNode@CNgcNode@@CAJAEBU_GUID@@PEBG11PEAV?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CNgcNode::_CreateNode(_GUID const &,ushort const *,ushort const *,ushort const *,Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits> *,std::wstring *)
0x18001226b  mov     ebx, eax
0x18001226d  mov     [rsp+170h+var_130], eax
0x180012271  test    eax, eax
0x180012273  js      short loc_1800122AE
0x180012275  xor     edx, edx
0x180012277  mov     rcx, [rsp+170h+var_118]
0x18001227c  call    ?_SetLifetime@CNgcNode@@CAJPEAUHSWDEVICE__@@W4_SW_DEVICE_LIFETIME@@@Z; CNgcNode::_SetLifetime(HSWDEVICE__ *,_SW_DEVICE_LIFETIME)
0x180012281  mov     ebx, eax
0x180012283  mov     [rsp+170h+var_130], eax
0x180012287  test    eax, eax
0x180012289  js      short loc_1800122AE
0x18001228b  lea     rcx, [rsp+170h+var_120]
0x180012290  call    ?Close@?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(void)
0x180012295  lea     rcx, [rbp+70h+var_D0]
0x180012299  cmp     [rbp+70h+var_B8], 8
0x18001229e  cmovnb  rcx, [rbp+70h+var_D0]; unsigned __int16 *
0x1800122a3  call    ?_UninstallNode@CNgcNode@@CAJPEBG@Z; CNgcNode::_UninstallNode(ushort const *)
0x1800122a8  mov     ebx, eax
0x1800122aa  mov     [rsp+170h+var_130], eax
0x1800122ae  xor     r8d, r8d
0x1800122b1  mov     dl, 1
0x1800122b3  lea     rcx, [rbp+70h+var_D0]
0x1800122b7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800122bc  nop
0x1800122bd  mov     [rsp+170h+var_120], r14
0x1800122c2  lea     rcx, [rsp+170h+var_120]
0x1800122c7  call    ?Close@?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(void)
0x1800122cc  nop
0x1800122cd  lea     rcx, [rsp+170h+var_108]
0x1800122d2  call    wil__details__ScopeExitFnGuard__lambda_07b0745ddc92eb413bee6b1b57a85b42_____operator__
0x1800122d7  nop
0x1800122d8  lea     rcx, [rbp+70h+var_F0]
0x1800122dc  call    WppTraceUnwinder__lambda_842321e91a56fa77c6ee6a375ceaa14c_______WppTraceUnwinder__lambda_842321e91a56fa77c6ee6a375ceaa14c____
0x1800122e1  mov     eax, ebx
0x1800122e3  mov     rcx, [rbp+70h+var_28]
0x1800122e7  xor     rcx, rsp; StackCookie
0x1800122ea  call    __security_check_cookie
0x1800122ef  add     rsp, 158h
0x1800122f6  pop     r14
0x1800122f8  pop     rdi
0x1800122f9  pop     rbx
0x1800122fa  pop     rbp
0x1800122fb  retn
```
