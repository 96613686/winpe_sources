# CBusNode::_Create(ushort const *,ushort const *,ushort const *,CBusNode::CCreateContext *)

- ea: `0x180009274`
- end: `0x180009488`
- name: `?_Create@CBusNode@@AEAAJPEBG00PEAUCCreateContext@1@@Z`
- size: `532`
- prototype: `__int64 __fastcall(CBusNode *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CBusNode::CCreateContext *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180008c14`

## callees

- `0x180006d40`
- `0x1800071d4`
- `0x180008484`
- `0x180008608`
- `0x18000880c`
- `0x180008bbc`
- `0x180009274`
- `0x180009b0c`
- `0x18001dfe2`
- `0x18001e020`

## import_xrefs

- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x1800093c4`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x1800093c4`

## string_xrefs

- `0x1800092a3`: `CBusNode::_Create`

## pseudocode

```c
__int64 __fastcall CBusNode::_Create(
        CBusNode *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct CBusNode::CCreateContext *a5)
{
  __int64 v8; // rax
  __int64 v9; // rcx
  PVOID v10; // rcx
  unsigned int v11; // ebx
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+44h] [rbp-BCh] BYREF
  const unsigned __int16 *v15; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v17; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v18[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v20; // [rsp+88h] [rbp-78h]
  int v21; // [rsp+A8h] [rbp-58h]
  const unsigned __int16 *v22; // [rsp+B0h] [rbp-50h]
  DEVPROPKEY v23; // [rsp+D0h] [rbp-30h] BYREF
  int v24; // [rsp+E4h] [rbp-1Ch]
  __int64 v25; // [rsp+E8h] [rbp-18h]
  int v26; // [rsp+F0h] [rbp-10h]
  int v27; // [rsp+F4h] [rbp-Ch]
  const unsigned __int16 *v28; // [rsp+F8h] [rbp-8h]
  char v29[24]; // [rsp+100h] [rbp+0h] BYREF

  v13 = 0;
  v18[0] = v29;
  v14 = 0;
  v18[1] = &v14;
  v18[2] = &v13;
  strcpy(v29, "CBusNode::_Create");
  lambda_6fe71a88461e3ffa853763801d365ffd_::operator()(v18, a2);
  v14 = 1;
  v17 = v18;
  *((_QWORD *)a5 + 2) = this;
  memset_0(&v19, 0, 0x48u);
  v23 = DEVPKEY_Device_FriendlyName;
  v8 = -1;
  v19 = 72;
  v20 = a3;
  v22 = a4;
  v21 = 6;
  v25 = 0;
  v24 = 0;
  v26 = 18;
  do
    ++v8;
  while ( a4[v8] );
  v28 = a4;
  v27 = 2 * v8 + 2;
  v15 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable';
  v16 = 0;
  Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(&v15);
  v13 = SwDeviceCreate(L"ScDeviceEnumBus", L"HTREE\\ROOT\\0", &v19, 1, &v23, CBusNode::_CreateCallback, a5, &v16);
  if ( v13 >= 0 )
  {
    Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::operator=(this, &v15);
  }
  else
  {
    WppTraceIndent(v9, 2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)&WPP_6cda2a62f3993c60960f64b829dda9e7_Traceguids,
        (_DWORD)WPP_pszIndent,
        v13);
    }
    if ( (Microsoft_Windows_SmartCard_DeviceEnumEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v10, SCDEVICEENUM_CREATE_FAILURE, a4, (unsigned int)v13);
  }
  v11 = v13;
  v15 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(&v15);
  WppTraceUnwinder__lambda_6fe71a88461e3ffa853763801d365ffd____::_WppTraceUnwinder__lambda_6fe71a88461e3ffa853763801d365ffd____(&v17);
  return v11;
}

```

## disassembly

```asm
0x180009274  push    rbp
0x180009276  push    rbx
0x180009277  push    rsi
0x180009278  push    rdi
0x180009279  push    r13
0x18000927b  push    r14
0x18000927d  push    r15
0x18000927f  lea     rbp, [rsp-20h]
0x180009284  sub     rsp, 120h
0x18000928b  mov     rax, cs:__security_cookie
0x180009292  xor     rax, rsp
0x180009295  mov     [rbp+50h+var_38], rax
0x180009299  movzx   eax, word ptr cs:aCbusnodeCreate_0+10h; "e"
0x1800092a0  mov     rsi, rcx
0x1800092a3  movups  xmm0, xmmword ptr cs:aCbusnodeCreate_0; "CBusNode::_Create"
0x1800092aa  mov     r14, [rbp+50h+arg_20]
0x1800092b1  lea     rcx, [rsp+150h+var_F0]
0x1800092b6  mov     word ptr [rbp+50h+var_50+10h], ax
0x1800092ba  xor     r13d, r13d
0x1800092bd  lea     rax, [rbp+50h+var_50]
0x1800092c1  mov     [rsp+150h+var_110], r13d
0x1800092c6  mov     [rsp+150h+var_F0], rax
0x1800092cb  mov     rdi, r9
0x1800092ce  lea     rax, [rsp+150h+var_10C]
0x1800092d3  mov     [rsp+150h+var_10C], r13d
0x1800092d8  mov     [rsp+150h+var_E8], rax
0x1800092dd  mov     rbx, r8
0x1800092e0  lea     rax, [rsp+150h+var_110]
0x1800092e5  mov     [rsp+150h+var_E0], rax
0x1800092ea  movups  xmmword ptr [rbp+50h+var_50], xmm0
0x1800092ee  call    _lambda_6fe71a88461e3ffa853763801d365ffd___operator__
0x1800092f3  lea     rax, [rsp+150h+var_F0]
0x1800092f8  mov     [rsp+150h+var_10C], 1
0x180009300  lea     r15d, [r13+48h]
0x180009304  mov     [rsp+150h+var_F8], rax
0x180009309  mov     r8d, r15d; Size
0x18000930c  mov     [r14+10h], rsi
0x180009310  xor     edx, edx; Val
0x180009312  lea     rcx, [rbp+50h+var_D0]; void *
0x180009316  call    memset_0
0x18000931b  mov     eax, cs:DEVPKEY_Device_FriendlyName.pid
0x180009321  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x180009328  mov     [rbp+50h+var_70], eax
0x18000932b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000932f  mov     [rbp+50h+var_D0], r15d
0x180009333  movups  [rbp+50h+var_80], xmm0
0x180009337  mov     [rbp+50h+var_C8], rbx
0x18000933b  mov     [rbp+50h+var_A0], rdi
0x18000933f  mov     [rbp+50h+var_A8], 6
0x180009346  mov     [rbp+50h+var_68], r13
0x18000934a  mov     [rbp+50h+var_6C], r13d
0x18000934e  mov     [rbp+50h+var_60], 12h
0x180009355  inc     rax
0x180009358  cmp     [rdi+rax*2], r13w
0x18000935d  jnz     short loc_180009355
0x18000935f  lea     eax, ds:2[rax*2]
0x180009366  mov     [rbp+50h+var_58], rdi
0x18000936a  lea     r15, ??_7?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable'
0x180009371  mov     [rbp+50h+var_5C], eax
0x180009374  lea     rcx, [rsp+150h+var_108]
0x180009379  mov     [rsp+150h+var_108], r15
0x18000937e  mov     [rsp+150h+var_100], r13
0x180009383  call    ?Close@?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(void)
0x180009388  lea     rax, [rsp+150h+var_100]
0x18000938d  mov     r9d, 1
0x180009393  mov     [rsp+150h+var_118], rax
0x180009398  lea     r8, [rbp+50h+var_D0]
0x18000939c  lea     rax, ?_CreateCallback@CBusNode@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; CBusNode::_CreateCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x1800093a3  mov     [rsp+150h+var_120], r14
0x1800093a8  mov     [rsp+150h+var_128], rax
0x1800093ad  lea     rdx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x1800093b4  lea     rax, [rbp+50h+var_80]
0x1800093b8  lea     rcx, aScdeviceenumbu; "ScDeviceEnumBus"
0x1800093bf  mov     [rsp+150h+var_130], rax
0x1800093c4  call    cs:__imp_SwDeviceCreate
0x1800093ca  mov     [rsp+150h+var_110], eax
0x1800093ce  test    eax, eax
0x1800093d0  jns     short loc_18000943E
0x1800093d2  mov     edx, 2
0x1800093d7  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800093dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093e3  lea     rax, WPP_GLOBAL_Control
0x1800093ea  cmp     rcx, rax
0x1800093ed  jz      short loc_18000941F
0x1800093ef  test    byte ptr [rcx+1Ch], 1
0x1800093f3  jz      short loc_18000941F
0x1800093f5  cmp     byte ptr [rcx+19h], 2
0x1800093f9  jb      short loc_18000941F
0x1800093fb  mov     eax, [rsp+150h+var_110]
0x1800093ff  lea     r8, WPP_6cda2a62f3993c60960f64b829dda9e7_Traceguids
0x180009406  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000940d  mov     edx, 14h
0x180009412  mov     rcx, [rcx+10h]
0x180009416  mov     dword ptr [rsp+150h+var_130], eax
0x18000941a  call    WPP_SF_sd
0x18000941f  test    cs:Microsoft_Windows_SmartCard_DeviceEnumEnableBits, 1
0x180009426  jz      short loc_18000944B
0x180009428  mov     r9d, [rsp+150h+var_110]
0x18000942d  lea     rdx, SCDEVICEENUM_CREATE_FAILURE
0x180009434  mov     r8, rdi
0x180009437  call    McTemplateU0zq_EventWriteTransfer
0x18000943c  jmp     short loc_18000944B
0x18000943e  lea     rdx, [rsp+150h+var_108]
0x180009443  mov     rcx, rsi
0x180009446  call    ??4?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@QEAAAEAV0123@$$QEAV0123@@Z; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::operator=(Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits> &&)
0x18000944b  mov     ebx, [rsp+150h+var_110]
0x18000944f  lea     rcx, [rsp+150h+var_108]
0x180009454  mov     [rsp+150h+var_108], r15
0x180009459  call    ?Close@?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(void)
0x18000945e  lea     rcx, [rsp+150h+var_F8]
0x180009463  call    WppTraceUnwinder__lambda_6fe71a88461e3ffa853763801d365ffd_______WppTraceUnwinder__lambda_6fe71a88461e3ffa853763801d365ffd____
0x180009468  mov     eax, ebx
0x18000946a  mov     rcx, [rbp+50h+var_38]
0x18000946e  xor     rcx, rsp; StackCookie
0x180009471  call    __security_check_cookie
0x180009476  add     rsp, 120h
0x18000947d  pop     r15
0x18000947f  pop     r14
0x180009481  pop     r13
0x180009483  pop     rdi
0x180009484  pop     rsi
0x180009485  pop     rbx
0x180009486  pop     rbp
0x180009487  retn
```
