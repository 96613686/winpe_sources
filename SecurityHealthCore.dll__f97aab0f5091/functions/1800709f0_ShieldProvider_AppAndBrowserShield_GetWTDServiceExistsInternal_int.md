# ShieldProvider::AppAndBrowserShield::GetWTDServiceExistsInternal(int *)

- ea: `0x1800709f0`
- end: `0x180070b63`
- name: `?GetWTDServiceExistsInternal@AppAndBrowserShield@ShieldProvider@@AEAAJPEAH@Z`
- size: `371`
- prototype: `int(ShieldProvider::AppAndBrowserShield *__hidden this, int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180070930`
- `0x180071ff0`
- `0x180072800`

## callees

- `0x18000d7fc`
- `0x1800709f0`
- `0x180070b6c`
- `0x180075730`
- `0x1800e1a1c`
- `0x1800e1a88`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180070a8e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180070b15`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180070b23`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180070b3d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180070b4b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180070a8e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180070b15`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180070b23`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180070b3d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180070b4b`

## pseudocode

```c
__int64 __fastcall ShieldProvider::AppAndBrowserShield::GetWTDServiceExistsInternal(
        ShieldProvider::AppAndBrowserShield *this,
        int *a2)
{
  struct SC_HANDLE__ **v4; // rdx
  unsigned int v5; // r8d
  const unsigned __int16 *v6; // r9
  int v7; // ebx
  SC_HANDLE v8; // rbx
  int v9; // esi
  const unsigned __int16 *v10; // [rsp+20h] [rbp-8h]
  unsigned int v11; // [rsp+20h] [rbp-8h]
  SC_HANDLE hSCObject; // [rsp+30h] [rbp+8h] BYREF
  SC_HANDLE v13; // [rsp+38h] [rbp+10h] BYREF

  hSCObject = (SC_HANDLE)this;
  if ( !a2 )
    return 2147942487LL;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::GetImpl'::`2'::impl)
    && !IsActiveSessionCountLimited() )
  {
    *a2 = 0;
    return 0;
  }
  hSCObject = 0;
  v7 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCObject, v4, v5, v6, v10);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        133,
        WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
        (unsigned int)v7);
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    return (unsigned int)v7;
  }
  v8 = hSCObject;
  v13 = 0;
  v9 = CommonUtil::HrOpenService(
         (CommonUtil *)&v13,
         (struct SC_HANDLE__ **)hSCObject,
         (struct SC_HANDLE__ *)&stru_1800FD090,
         (const unsigned __int16 *)4,
         v11);
  if ( v9 == -2147023836 )
  {
    *a2 = 0;
    goto LABEL_26;
  }
  if ( !v9 )
  {
    *a2 = 1;
    goto LABEL_26;
  }
  if ( v9 >= 0 )
  {
LABEL_26:
    if ( v13 )
      CloseServiceHandle(v13);
    if ( v8 )
      CloseServiceHandle(v8);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      134,
      WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
      (unsigned int)v9);
  if ( v13 )
    CloseServiceHandle(v13);
  if ( v8 )
    CloseServiceHandle(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800709f0  mov     [rsp+arg_10], rbx
0x1800709f5  mov     [rsp+arg_18], rsi
0x1800709fa  mov     [rsp+hSCObject], rcx
0x1800709ff  push    rdi; unsigned int
0x180070a00  sub     rsp, 20h
0x180070a04  mov     rdi, rdx
0x180070a07  test    rdx, rdx
0x180070a0a  jnz     short loc_180070A16
0x180070a0c  mov     eax, 80070057h
0x180070a11  jmp     loc_180070B53
0x180070a16  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WSA_Multisession_Fix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WSA_Multisession_Fix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WSA_Multisession_Fix> `wil::Feature<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::GetImpl(void)'::`2'::impl
0x180070a1d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WSA_Multisession_Fix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WSA_Multisession_Fix>::__private_IsEnabled(void)
0x180070a22  test    al, al
0x180070a24  jz      short loc_180070A3A
0x180070a26  call    ?IsActiveSessionCountLimited@@YA_NXZ; IsActiveSessionCountLimited(void)
0x180070a2b  test    al, al
0x180070a2d  jnz     short loc_180070A3A
0x180070a2f  mov     dword ptr [rdi], 0
0x180070a35  jmp     loc_180070B51
0x180070a3a  lea     rcx, [rsp+28h+hSCObject]; this
0x180070a3f  mov     [rsp+28h+hSCObject], 0
0x180070a48  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEBG1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,ushort const *,ushort const *)
0x180070a4d  mov     ebx, eax
0x180070a4f  test    eax, eax
0x180070a51  jns     short loc_180070A9B
0x180070a53  mov     rcx, cs:WPP_GLOBAL_Control
0x180070a5a  lea     rax, WPP_GLOBAL_Control
0x180070a61  cmp     rcx, rax
0x180070a64  jz      short loc_180070A84
0x180070a66  test    byte ptr [rcx+1Ch], 1
0x180070a6a  jz      short loc_180070A84
0x180070a6c  mov     rcx, [rcx+10h]
0x180070a70  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x180070a77  mov     edx, 85h
0x180070a7c  mov     r9d, ebx
0x180070a7f  call    WPP_SF_d
0x180070a84  mov     rcx, [rsp+28h+hSCObject]; hSCObject
0x180070a89  test    rcx, rcx
0x180070a8c  jz      short loc_180070A94
0x180070a8e  call    cs:__imp_CloseServiceHandle
0x180070a94  mov     eax, ebx
0x180070a96  jmp     loc_180070B53
0x180070a9b  mov     rbx, [rsp+28h+hSCObject]
0x180070aa0  lea     r8, stru_1800FD090; struct SC_HANDLE__ *
0x180070aa7  mov     rdx, rbx; struct SC_HANDLE__ **
0x180070aaa  mov     [rsp+28h+arg_8], 0
0x180070ab3  mov     r9d, 4; unsigned __int16 *
0x180070ab9  lea     rcx, [rsp+28h+arg_8]; this
0x180070abe  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEBGK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,ushort const *,ulong)
0x180070ac3  mov     esi, eax
0x180070ac5  cmp     eax, 80070424h
0x180070aca  jnz     short loc_180070AD4
0x180070acc  mov     dword ptr [rdi], 0
0x180070ad2  jmp     short loc_180070B33
0x180070ad4  test    esi, esi
0x180070ad6  jz      short loc_180070B2D
0x180070ad8  jns     short loc_180070B33
0x180070ada  mov     rcx, cs:WPP_GLOBAL_Control
0x180070ae1  lea     rax, WPP_GLOBAL_Control
0x180070ae8  cmp     rcx, rax
0x180070aeb  jz      short loc_180070B0B
0x180070aed  test    byte ptr [rcx+1Ch], 1
0x180070af1  jz      short loc_180070B0B
0x180070af3  mov     rcx, [rcx+10h]
0x180070af7  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x180070afe  mov     edx, 86h
0x180070b03  mov     r9d, esi
0x180070b06  call    WPP_SF_d
0x180070b0b  mov     rcx, [rsp+28h+arg_8]; hSCObject
0x180070b10  test    rcx, rcx
0x180070b13  jz      short loc_180070B1B
0x180070b15  call    cs:__imp_CloseServiceHandle
0x180070b1b  test    rbx, rbx
0x180070b1e  jz      short loc_180070B29
0x180070b20  mov     rcx, rbx; hSCObject
0x180070b23  call    cs:__imp_CloseServiceHandle
0x180070b29  mov     eax, esi
0x180070b2b  jmp     short loc_180070B53
0x180070b2d  mov     dword ptr [rdi], 1
0x180070b33  mov     rcx, [rsp+28h+arg_8]; hSCObject
0x180070b38  test    rcx, rcx
0x180070b3b  jz      short loc_180070B43
0x180070b3d  call    cs:__imp_CloseServiceHandle
0x180070b43  test    rbx, rbx
0x180070b46  jz      short loc_180070B51
0x180070b48  mov     rcx, rbx; hSCObject
0x180070b4b  call    cs:__imp_CloseServiceHandle
0x180070b51  xor     eax, eax
0x180070b53  mov     rbx, [rsp+28h+arg_10]
0x180070b58  mov     rsi, [rsp+28h+arg_18]
0x180070b5d  add     rsp, 20h
0x180070b61  pop     rdi
0x180070b62  retn
```
