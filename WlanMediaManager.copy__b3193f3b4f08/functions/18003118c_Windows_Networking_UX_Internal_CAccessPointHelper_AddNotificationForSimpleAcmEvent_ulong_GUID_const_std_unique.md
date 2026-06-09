# Windows::Networking::UX::Internal::CAccessPointHelper::_AddNotificationForSimpleAcmEvent(ulong,_GUID const &,std::unique_ptr<Windows::Networking::UX::Internal::CWlanNotificationList,std::default_delete<Windows::Networking::UX::Internal::CWlanNotificationList>> &)

- ea: `0x18003118c`
- end: `0x180031287`
- name: `?_AddNotificationForSimpleAcmEvent@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJKAEBU_GUID@@AEAV?$unique_ptr@VCWlanNotificationList@Internal@UX@Networking@Windows@@U?$default_delete@VCWlanNotificationList@Internal@UX@Networking@Windows@@@std@@@std@@@Z`
- size: `251`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031050`
- `0x180031d3c`
- `0x18003275c`

## callees

- `0x1800097b4`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18002f0dc`
- `0x18003118c`
- `0x18003160c`
- `0x180057c3c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003126e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003126e`

## string_xrefs

- `0x1800311f6`: `onecoreuap\net\ux\wlanmediamanager\lib\accesspointhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::CAccessPointHelper::_AddNotificationForSimpleAcmEvent(
        void *a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4)
{
  PVOID v7; // rcx
  int v8; // eax
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 result; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  const char *v14; // r9
  int v15[14]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID pv; // [rsp+60h] [rbp+8h] BYREF

  pv = a1;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids);
  pv = 0;
  v8 = Windows::Networking::UX::Internal::CAccessPointHelper::_AllocSimpleAcmNotificationData(v7, a2, a3, &pv);
  v10 = v8;
  if ( v8 >= 0 )
  {
    v12 = wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
            v15,
            &pv,
            *a4,
            v9);
    try
    {
      Windows::Networking::UX::Internal::CWlanNotificationList::Add(v13, v12);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids, 0);
      if ( pv )
        CoTaskMemFree(pv);
      result = 0;
    }
    catch ( ... )
    {
      LODWORD(pv) = wil::details::in1diag3::Return_CaughtException(
                      retaddr,
                      (void *)0x68B,
                      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\accesspointhelpers.cpp",
                      v14);
      return (unsigned int)pv;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x686,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\accesspointhelpers.cpp",
      (const char *)(unsigned int)v8,
      v15[0]);
    if ( pv )
      CoTaskMemFree(pv);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x18003118c  mov     [rsp+pv], rcx
0x180031191  push    rbx
0x180031192  push    rsi
0x180031193  push    rdi
0x180031194  push    r14
0x180031196  sub     rsp, 38h
0x18003119a  mov     rsi, r9
0x18003119d  mov     rbx, r8
0x1800311a0  mov     edi, edx
0x1800311a2  lea     r14, WPP_GLOBAL_Control
0x1800311a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800311b0  cmp     rcx, r14
0x1800311b3  jz      short loc_1800311D0
0x1800311b5  test    byte ptr [rcx+1Ch], 40h
0x1800311b9  jz      short loc_1800311D0
0x1800311bb  mov     edx, 9Ah
0x1800311c0  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x1800311c7  mov     rcx, [rcx+10h]
0x1800311cb  call    WPP_SF_
0x1800311d0  mov     [rsp+58h+pv], 0
0x1800311d9  lea     r9, [rsp+58h+pv]
0x1800311de  mov     r8, rbx
0x1800311e1  mov     edx, edi
0x1800311e3  call    ?_AllocSimpleAcmNotificationData@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJKAEBU_GUID@@AEAV?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; Windows::Networking::UX::Internal::CAccessPointHelper::_AllocSimpleAcmNotificationData(ulong,_GUID const &,wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x1800311e8  mov     ebx, eax
0x1800311ea  test    eax, eax
0x1800311ec  jns     short loc_18003121C
0x1800311ee  mov     rcx, [rsp+58h]; this
0x1800311f3  mov     r9d, eax; char *
0x1800311f6  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800311fd  mov     edx, 686h; void *
0x180031202  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031207  nop
0x180031208  mov     rcx, [rsp+58h+pv]; pv
0x18003120d  test    rcx, rcx
0x180031210  jz      short loc_180031218
0x180031212  call    cs:__imp_CoTaskMemFree
0x180031218  mov     eax, ebx
0x18003121a  jmp     short loc_18003127C
0x18003121c  mov     r8, [rsi]
0x18003121f  lea     rdx, [rsp+58h+pv]
0x180031224  lea     rcx, [rsp+58h+var_38]
0x180031229  call    ??0?$unique_ptr@U_L2_UI_REQUEST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18003122e  mov     rdx, rax
0x180031231  mov     rcx, r8
0x180031234  call    ?Add@CWlanNotificationList@Internal@UX@Networking@Windows@@QEAAXV?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; Windows::Networking::UX::Internal::CWlanNotificationList::Add(wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>)
0x180031239  mov     rcx, cs:WPP_GLOBAL_Control
0x180031240  cmp     rcx, r14
0x180031243  jz      short loc_180031264
0x180031245  test    byte ptr [rcx+1Ch], 40h
0x180031249  jz      short loc_180031264
0x18003124b  mov     edx, 9Bh
0x180031250  xor     r9d, r9d
0x180031253  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x18003125a  mov     rcx, [rcx+10h]
0x18003125e  call    WPP_SF_d
0x180031263  nop
0x180031264  mov     rcx, [rsp+58h+pv]; pv
0x180031269  test    rcx, rcx
0x18003126c  jz      short loc_180031274
0x18003126e  call    cs:__imp_CoTaskMemFree
0x180031274  xor     eax, eax
0x180031276  jmp     short loc_18003127C
0x180031278  mov     eax, dword ptr [rsp+58h+pv]
0x18003127c  add     rsp, 38h
0x180031280  pop     r14
0x180031282  pop     rdi
0x180031283  pop     rsi
0x180031284  pop     rbx
0x180031285  retn
```
