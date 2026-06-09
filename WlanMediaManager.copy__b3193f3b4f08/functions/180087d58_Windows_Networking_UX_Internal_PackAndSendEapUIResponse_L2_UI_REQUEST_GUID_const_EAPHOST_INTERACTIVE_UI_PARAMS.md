# Windows::Networking::UX::Internal::PackAndSendEapUIResponse(_L2_UI_REQUEST *,_GUID const &,_EAPHOST_INTERACTIVE_UI_PARAMS *)

- ea: `0x180087d58`
- end: `0x180087f1c`
- name: `?PackAndSendEapUIResponse@Internal@UX@Networking@Windows@@YAJPEAU_L2_UI_REQUEST@@AEBU_GUID@@PEAU_EAPHOST_INTERACTIVE_UI_PARAMS@@@Z`
- size: `452`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal *__hidden this, struct _L2_UI_REQUEST *, const struct _GUID *, struct _EAPHOST_INTERACTIVE_UI_PARAMS *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180072930`

## callees

- `0x18000de4c`
- `0x18001d4d4`
- `0x18003a070`
- `0x180087c38`
- `0x180087d58`
- `0x180087f24`
- `0x180088cb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087ebc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087ebc`
- `MobileNetworking!FreeMemory` at `0x180087ee1`
- `MobileNetworking!FreeMemory` at `0x180087ee1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Networking::UX::Internal::PackAndSendEapUIResponse(
        Windows::Networking::UX::Internal *this,
        struct _L2_UI_REQUEST *a2,
        const struct _GUID *a3,
        struct _EAPHOST_INTERACTIVE_UI_PARAMS *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  PVOID *v9; // rcx
  struct _WLAN_UI_RESPONSE *v10; // r9
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  void *v14; // rax
  unsigned int *v16; // [rsp+30h] [rbp-28h] BYREF
  LPVOID *p_pv; // [rsp+38h] [rbp-20h] BYREF
  __int64 v18; // [rsp+40h] [rbp-18h] BYREF
  char v19; // [rsp+48h] [rbp-10h]
  LPVOID pv; // [rsp+A8h] [rbp+50h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ba28dae9eeea3c6b09312a4c5a49e1a6_Traceguids);
  v16 = 0;
  v7 = OneXMapEAPHostInteractiveUIToOneXUIResponse(a3, &v16, a3, a4);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( (v8 & 0x80000000) == 0 )
  {
    pv = 0;
    p_pv = &pv;
    v18 = 0;
    v19 = 1;
    v8 = Windows::Networking::UX::Internal::MSMSecUIResultHelper(*((unsigned int *)this + 161), 3, *v16, v16, &v18);
    wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
    if ( (v8 & 0x80000000) == 0 )
    {
      v13 = Windows::Networking::UX::Internal::PackAndSendWlanUIResponse(this, a2, (const struct _GUID *)pv, v10);
      v8 = v13;
      if ( v13 >= 0 )
      {
LABEL_19:
        v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
        v14 = pv;
        pv = 0;
        if ( !v14 )
          goto LABEL_23;
        CoTaskMemFree(v14);
        goto LABEL_22;
      }
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_20;
      v11 = 19;
      v12 = (unsigned int)v13;
    }
    else
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_20;
      v11 = 18;
      v12 = v8;
    }
    WPP_SF_d(v9[2], v11, WPP_ba28dae9eeea3c6b09312a4c5a49e1a6_Traceguids, v12);
    goto LABEL_19;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_ba28dae9eeea3c6b09312a4c5a49e1a6_Traceguids, v8);
LABEL_22:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_23:
  if ( v16 )
  {
    FreeMemory(&v16, "Windows::Networking::UX::Internal::PackAndSendEapUIResponse", 141);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 )
    WPP_SF_d(v9[2], 20, WPP_ba28dae9eeea3c6b09312a4c5a49e1a6_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180087d58  push    rbp
0x180087d5a  push    rbx
0x180087d5b  push    rsi
0x180087d5c  push    rdi
0x180087d5d  push    r12
0x180087d5f  push    r15
0x180087d61  mov     rbp, rsp
0x180087d64  sub     rsp, 58h
0x180087d68  mov     rbx, r8
0x180087d6b  mov     rsi, rdx
0x180087d6e  mov     rdi, rcx
0x180087d71  lea     r15, WPP_GLOBAL_Control
0x180087d78  lea     r12, WPP_ba28dae9eeea3c6b09312a4c5a49e1a6_Traceguids
0x180087d7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180087d86  cmp     rcx, r15
0x180087d89  jz      short loc_180087DA2
0x180087d8b  test    byte ptr [rcx+1Ch], 40h
0x180087d8f  jz      short loc_180087DA2
0x180087d91  mov     edx, 10h
0x180087d96  mov     r8, r12
0x180087d99  mov     rcx, [rcx+10h]
0x180087d9d  call    WPP_SF_
0x180087da2  mov     [rbp+var_28], 0
0x180087daa  lea     rdx, [rbp+var_28]
0x180087dae  mov     rcx, rbx
0x180087db1  call    OneXMapEAPHostInteractiveUIToOneXUIResponse
0x180087db6  mov     ebx, eax
0x180087db8  test    eax, eax
0x180087dba  jle     short loc_180087DC5
0x180087dbc  movzx   ebx, ax
0x180087dbf  or      ebx, 80070000h
0x180087dc5  test    ebx, ebx
0x180087dc7  jns     short loc_180087DFC
0x180087dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180087dd0  cmp     rcx, r15
0x180087dd3  jz      loc_180087EC9
0x180087dd9  test    byte ptr [rcx+1Ch], 2
0x180087ddd  jz      loc_180087EC9
0x180087de3  mov     edx, 11h
0x180087de8  mov     r9d, ebx
0x180087deb  mov     r8, r12
0x180087dee  mov     rcx, [rcx+10h]
0x180087df2  call    WPP_SF_d
0x180087df7  jmp     loc_180087EC2
0x180087dfc  mov     [rbp+pv], 0
0x180087e04  lea     rax, [rbp+pv]
0x180087e08  mov     [rbp+var_20], rax
0x180087e0c  mov     [rbp+var_18], 0
0x180087e14  mov     [rbp+var_10], 1
0x180087e18  mov     r8, [rbp+var_28]
0x180087e1c  lea     rax, [rbp+var_18]
0x180087e20  mov     [rsp+58h+var_38], rax
0x180087e25  mov     r9, r8
0x180087e28  mov     r8d, [r8]
0x180087e2b  mov     edx, 3
0x180087e30  mov     ecx, [rdi+284h]
0x180087e36  call    ?MSMSecUIResultHelper@Internal@UX@Networking@Windows@@YAJW4_WLAN_UI_REQUEST_TYPE@@W4_MSMSEC_UI_RESPONSE_TYPE@@KPEAEPEAPEAU_WLAN_UI_RESPONSE@@@Z; Windows::Networking::UX::Internal::MSMSecUIResultHelper(_WLAN_UI_REQUEST_TYPE,_MSMSEC_UI_RESPONSE_TYPE,ulong,uchar *,_WLAN_UI_RESPONSE * *)
0x180087e3b  mov     ebx, eax
0x180087e3d  lea     rcx, [rbp+var_20]
0x180087e41  call    ??1?$out_param_t@V?$unique_ptr@U_L2_UI_RESPONSE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180087e46  test    ebx, ebx
0x180087e48  jns     short loc_180087E66
0x180087e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180087e51  cmp     rcx, r15
0x180087e54  jz      short loc_180087EA8
0x180087e56  test    byte ptr [rcx+1Ch], 2
0x180087e5a  jz      short loc_180087EA8
0x180087e5c  mov     edx, 12h
0x180087e61  mov     r9d, ebx
0x180087e64  jmp     short loc_180087E95
0x180087e66  mov     r8, [rbp+pv]; struct _GUID *
0x180087e6a  mov     rdx, rsi; struct _L2_UI_REQUEST *
0x180087e6d  mov     rcx, rdi; this
0x180087e70  call    ?PackAndSendWlanUIResponse@Internal@UX@Networking@Windows@@YAJPEAU_L2_UI_REQUEST@@AEBU_GUID@@PEAU_WLAN_UI_RESPONSE@@@Z; Windows::Networking::UX::Internal::PackAndSendWlanUIResponse(_L2_UI_REQUEST *,_GUID const &,_WLAN_UI_RESPONSE *)
0x180087e75  mov     ebx, eax
0x180087e77  test    eax, eax
0x180087e79  jns     short loc_180087EA1
0x180087e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180087e82  cmp     rcx, r15
0x180087e85  jz      short loc_180087EA8
0x180087e87  test    byte ptr [rcx+1Ch], 2
0x180087e8b  jz      short loc_180087EA8
0x180087e8d  mov     edx, 13h
0x180087e92  mov     r9d, eax
0x180087e95  mov     r8, r12
0x180087e98  mov     rcx, [rcx+10h]
0x180087e9c  call    WPP_SF_d
0x180087ea1  mov     rcx, cs:WPP_GLOBAL_Control
0x180087ea8  mov     rax, [rbp+pv]
0x180087eac  mov     [rbp+pv], 0
0x180087eb4  test    rax, rax
0x180087eb7  jz      short loc_180087EC9
0x180087eb9  mov     rcx, rax; pv
0x180087ebc  call    cs:__imp_CoTaskMemFree
0x180087ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x180087ec9  cmp     [rbp+var_28], 0
0x180087ece  jz      short loc_180087EEE
0x180087ed0  mov     r8d, 8Dh
0x180087ed6  lea     rdx, aWindowsNetwork_2; "Windows::Networking::UX::Internal::Pack"...
0x180087edd  lea     rcx, [rbp+var_28]
0x180087ee1  call    cs:__imp_FreeMemory
0x180087ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x180087eee  cmp     rcx, r15
0x180087ef1  jz      short loc_180087F0D
0x180087ef3  test    byte ptr [rcx+1Ch], 40h
0x180087ef7  jz      short loc_180087F0D
0x180087ef9  mov     edx, 14h
0x180087efe  mov     r9d, ebx
0x180087f01  mov     r8, r12
0x180087f04  mov     rcx, [rcx+10h]
0x180087f08  call    WPP_SF_d
0x180087f0d  mov     eax, ebx
0x180087f0f  add     rsp, 58h
0x180087f13  pop     r15
0x180087f15  pop     r12
0x180087f17  pop     rdi
0x180087f18  pop     rsi
0x180087f19  pop     rbx
0x180087f1a  pop     rbp
0x180087f1b  retn
```
