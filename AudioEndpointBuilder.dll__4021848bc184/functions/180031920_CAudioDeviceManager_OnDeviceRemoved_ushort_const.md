# CAudioDeviceManager::OnDeviceRemoved(ushort const *)

- ea: `0x180031920`
- end: `0x180031ab5`
- name: `?OnDeviceRemoved@CAudioDeviceManager@@UEAAJPEBG@Z`
- size: `405`
- prototype: `__int64 __fastcall(CAudioDeviceManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180058cac`

## callees

- `0x1800035d0`
- `0x180006b0c`
- `0x18000dacc`
- `0x18000fb60`
- `0x180010da8`
- `0x180031920`
- `0x180031abc`
- `0x180033444`
- `0x1800582d0`
- `0x180058824`
- `0x180058b44`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180031a47`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180031a47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031a70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031a88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031a70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031a88`

## string_xrefs

- `0x180031a24`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x180031a55`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CAudioDeviceManager::OnDeviceRemoved(CAudioDeviceManager *this, const unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rbx
  struct IUnknownVtbl *lpVtbl; // rax
  int LastError; // edi
  const char *v7; // r9
  int v9; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v10; // [rsp+30h] [rbp-30h] BYREF
  struct _GUID v11; // [rsp+38h] [rbp-28h] BYREF
  ULONG_PTR *p_dwCompletionKey; // [rsp+48h] [rbp-18h] BYREF
  struct MMNotification_Event *v13; // [rsp+50h] [rbp-10h] BYREF
  char v14; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  struct IMMDevice *v16; // [rsp+90h] [rbp+30h] BYREF
  ULONG_PTR dwCompletionKey; // [rsp+98h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids, a2);
  }
  dwCompletionKey = 0;
  v16 = 0;
  v4 = 0;
  v10 = 0;
  v11 = 0;
  lpVtbl = g_DeviceEnumerator->lpVtbl;
  v16 = 0;
  if ( ((int (__fastcall *)(struct IUnknown *, const unsigned __int16 *, struct IMMDevice **))lpVtbl[1].Release)(
         g_DeviceEnumerator,
         a2,
         &v16) >= 0 )
  {
    v11 = *GetDeviceInterfaceClassForEndpoint(&v11, v16);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v10,
      0);
    GetDeviceInstanceIdForEndpoint(v16, &v10);
    v4 = v10;
  }
  p_dwCompletionKey = &dwCompletionKey;
  v13 = 0;
  v14 = 1;
  LastError = MMNotification_Event::CreateRemoveDeviceEvent(this, a2, v4, &v11, &v13);
  wil::details::out_param_t<std::unique_ptr<MMNotification_Event>>::~out_param_t<std::unique_ptr<MMNotification_Event>>(&p_dwCompletionKey);
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5CF,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)(unsigned int)LastError,
      v9);
    goto LABEL_11;
  }
  if ( !PostQueuedCompletionStatus(g_WorkerEventPort, 0, dwCompletionKey, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x5D0,
                  (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
                  v7);
LABEL_11:
    if ( v4 )
      CoTaskMemFree(v4);
    goto LABEL_16;
  }
  dwCompletionKey = 0;
  if ( v4 )
    CoTaskMemFree(v4);
  LastError = 0;
LABEL_16:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  std::unique_ptr<MMNotification_Event>::~unique_ptr<MMNotification_Event>(&dwCompletionKey);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180031920  mov     [rsp-18h+arg_0], rbx
0x180031925  push    rbp
0x180031926  push    rsi
0x180031927  push    rdi
0x180031928  mov     rbp, rsp
0x18003192b  sub     rsp, 60h
0x18003192f  mov     rdi, rdx
0x180031932  mov     rsi, rcx
0x180031935  lea     rax, WPP_GLOBAL_Control
0x18003193c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031943  cmp     rcx, rax
0x180031946  jz      short loc_18003196F
0x180031948  test    dword ptr [rcx+1Ch], 80000h
0x18003194f  jz      short loc_18003196F
0x180031951  cmp     byte ptr [rcx+19h], 5
0x180031955  jb      short loc_18003196F
0x180031957  mov     edx, 20h ; ' '
0x18003195c  mov     r9, rdi
0x18003195f  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x180031966  mov     rcx, [rcx+10h]
0x18003196a  call    WPP_SF_S
0x18003196f  mov     [rbp+dwCompletionKey], 0
0x180031977  mov     [rbp+arg_10], 0
0x18003197f  xor     ebx, ebx
0x180031981  mov     [rbp+var_30], rbx
0x180031985  xorps   xmm0, xmm0
0x180031988  movups  xmmword ptr [rbp+var_28.Data1], xmm0
0x18003198c  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180031993  mov     rax, [rcx]
0x180031996  mov     [rbp+arg_10], rbx
0x18003199a  lea     r8, [rbp+arg_10]
0x18003199e  mov     rdx, rdi
0x1800319a1  mov     rax, [rax+28h]
0x1800319a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800319aa  test    eax, eax
0x1800319ac  js      short loc_1800319DF
0x1800319ae  mov     rdx, [rbp+arg_10]; struct IMMDevice *
0x1800319b2  lea     rcx, [rbp+var_28]; retstr
0x1800319b6  call    ?GetDeviceInterfaceClassForEndpoint@@YA?BU_GUID@@PEAUIMMDevice@@@Z; GetDeviceInterfaceClassForEndpoint(IMMDevice *)
0x1800319bb  movups  xmm0, xmmword ptr [rax]
0x1800319be  movdqu  xmmword ptr [rbp+var_28.Data1], xmm0
0x1800319c3  xor     edx, edx
0x1800319c5  lea     rcx, [rbp+var_30]
0x1800319c9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800319ce  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x1800319d2  mov     rcx, [rbp+arg_10]; struct IMMDevice *
0x1800319d6  call    ?GetDeviceInstanceIdForEndpoint@@YAJPEAUIMMDevice@@PEAPEAG@Z; GetDeviceInstanceIdForEndpoint(IMMDevice *,ushort * *)
0x1800319db  mov     rbx, [rbp+var_30]
0x1800319df  lea     rax, [rbp+dwCompletionKey]
0x1800319e3  mov     [rbp+var_18], rax
0x1800319e7  mov     [rbp+var_10], 0
0x1800319ef  mov     [rbp+var_8], 1
0x1800319f3  lea     rax, [rbp+var_10]
0x1800319f7  mov     qword ptr [rsp+60h+var_40], rax; int
0x1800319fc  lea     r9, [rbp+var_28]; struct _GUID *
0x180031a00  mov     r8, rbx; unsigned __int16 *
0x180031a03  mov     rdx, rdi; unsigned __int16 *
0x180031a06  mov     rcx, rsi; struct CAudioDeviceManager *
0x180031a09  call    ?CreateRemoveDeviceEvent@MMNotification_Event@@SAJPEAVCAudioDeviceManager@@PEBG1PEBU_GUID@@PEAPEAU1@@Z; MMNotification_Event::CreateRemoveDeviceEvent(CAudioDeviceManager *,ushort const *,ushort const *,_GUID const *,MMNotification_Event * *)
0x180031a0e  mov     edi, eax
0x180031a10  lea     rcx, [rbp+var_18]
0x180031a14  call    ??1?$out_param_t@V?$unique_ptr@UMMNotification_Event@@U?$default_delete@UMMNotification_Event@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<MMNotification_Event>>::~out_param_t<std::unique_ptr<MMNotification_Event>>(void)
0x180031a19  test    edi, edi
0x180031a1b  jns     short loc_180031A37
0x180031a1d  mov     rcx, [rbp+18h]; this
0x180031a21  mov     r9d, edi; char *
0x180031a24  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180031a2b  mov     edx, 5CFh; void *
0x180031a30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031a35  jmp     short loc_180031A68
0x180031a37  xor     r9d, r9d; lpOverlapped
0x180031a3a  mov     r8, [rbp+dwCompletionKey]; dwCompletionKey
0x180031a3e  xor     edx, edx; dwNumberOfBytesTransferred
0x180031a40  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; CompletionPort
0x180031a47  call    cs:__imp_PostQueuedCompletionStatus
0x180031a4d  test    eax, eax
0x180031a4f  jnz     short loc_180031A78
0x180031a51  mov     rcx, [rbp+18h]; this
0x180031a55  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180031a5c  mov     edx, 5D0h; void *
0x180031a61  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031a66  mov     edi, eax
0x180031a68  test    rbx, rbx
0x180031a6b  jz      short loc_180031A90
0x180031a6d  mov     rcx, rbx; pv
0x180031a70  call    cs:__imp_CoTaskMemFree
0x180031a76  jmp     short loc_180031A90
0x180031a78  mov     [rbp+dwCompletionKey], 0
0x180031a80  test    rbx, rbx
0x180031a83  jz      short loc_180031A8E
0x180031a85  mov     rcx, rbx; pv
0x180031a88  call    cs:__imp_CoTaskMemFree
0x180031a8e  xor     edi, edi
0x180031a90  lea     rcx, [rbp+arg_10]
0x180031a94  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180031a99  nop
0x180031a9a  lea     rcx, [rbp+dwCompletionKey]
0x180031a9e  call    ??1?$unique_ptr@UMMNotification_Event@@U?$default_delete@UMMNotification_Event@@@std@@@std@@QEAA@XZ; std::unique_ptr<MMNotification_Event>::~unique_ptr<MMNotification_Event>(void)
0x180031aa3  mov     eax, edi
0x180031aa5  mov     rbx, [rsp+60h+arg_0]
0x180031aad  add     rsp, 60h
0x180031ab1  pop     rdi
0x180031ab2  pop     rsi
0x180031ab3  pop     rbp
0x180031ab4  retn
```
