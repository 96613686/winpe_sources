# CTSSession::OnDeviceStateChanged(ushort const *,ulong)

- ea: `0x18003d7a0`
- end: `0x18003da55`
- name: `?OnDeviceStateChanged@CTSSession@@UEAAJPEBGK@Z`
- size: `693`
- prototype: `__int64 __fastcall(CTSSession *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005358`
- `0x180006b0c`
- `0x180009c80`
- `0x18000ab60`
- `0x18000fb60`
- `0x180026530`
- `0x180027a10`
- `0x180029024`
- `0x180035eb4`
- `0x18003d7a0`
- `0x18003dd00`
- `0x180059864`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d9cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d9cb`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18003d9c1`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18003d9c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da35`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CTSSession::OnDeviceStateChanged(CTSSession *this, const unsigned __int16 *a2, int a3)
{
  MMNotification_Event *v6; // rsi
  unsigned __int16 *v7; // rbx
  const unsigned __int16 *LocalEndpointIdForRemoteEndpointId; // r13
  __int64 v9; // r12
  __int64 (__fastcall *v10)(_QWORD, _QWORD, _QWORD); // rax
  struct IMMDevice *v11; // rcx
  int v12; // eax
  int v13; // r8d
  int v14; // eax
  int v15; // edi
  int v16; // edi
  int v17; // edi
  int DisableDeviceEvent; // r14d
  int v19; // r15d
  struct IMMDevice *v20; // r12
  __int64 v21; // r14
  _DWORD *v22; // rdi
  ULONG_PTR dwCompletionKey; // [rsp+30h] [rbp-10h] BYREF
  __int64 (__fastcall *v25)(_QWORD, _QWORD, _QWORD); // [rsp+38h] [rbp-8h]
  struct IMMDevice *v26; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int16 *v27; // [rsp+98h] [rbp+58h] BYREF

  v6 = 0;
  dwCompletionKey = 0;
  v7 = 0;
  v27 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, a3, *((_DWORD *)this + 2), (__int64)a2, a3);
  }
  LocalEndpointIdForRemoteEndpointId = GetLocalEndpointIdForRemoteEndpointId(a2);
  v9 = *((_QWORD *)this + 2);
  v10 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v9 + 40LL);
  v25 = v10;
  v11 = v26;
  v26 = 0;
  if ( v11 )
  {
    ((void (__fastcall *)(struct IMMDevice *))v11->lpVtbl->Release)(v11);
    v10 = v25;
  }
  v12 = v10(v9, LocalEndpointIdForRemoteEndpointId, &v26);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, v13, (_DWORD)a2, v12);
    }
    goto LABEL_33;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v27,
    0);
  v14 = FixupRemoteEndpointId(v26, *((unsigned int *)this + 2), LocalEndpointIdForRemoteEndpointId, &v27);
  v7 = v27;
  if ( v14 < 0 )
    goto LABEL_33;
  v15 = a3 - 1;
  if ( !v15 )
  {
    v19 = *((_DWORD *)this + 2);
    v20 = v26;
    v21 = *((_QWORD *)this + 3);
    v22 = operator new(0x58u);
    if ( v22 )
    {
      *(_QWORD *)v22 = &MMNotification_Event::`vftable';
      v22[2] = 2;
      *((_QWORD *)v22 + 2) = 0;
      *((_QWORD *)v22 + 3) = 0;
      *((_QWORD *)v22 + 6) = 0;
      *((_QWORD *)v22 + 10) = v21;
      DisableDeviceEvent = 0;
      ATL::CComPtr<IMMDevice>::operator=(v22 + 12, v20);
      v22[19] = v19;
      v6 = (MMNotification_Event *)v22;
    }
    else
    {
      DisableDeviceEvent = -2147024882;
    }
LABEL_21:
    if ( DisableDeviceEvent < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
    }
    goto LABEL_26;
  }
  v16 = v15 - 1;
  if ( !v16 || (v17 = v16 - 2) == 0 || v17 == 4 )
  {
    DisableDeviceEvent = MMNotification_Event::CreateDisableDeviceEvent(
                           *((struct CAudioDeviceManager **)this + 3),
                           v27,
                           (struct MMNotification_Event **)&dwCompletionKey);
    v6 = (MMNotification_Event *)dwCompletionKey;
    goto LABEL_21;
  }
LABEL_26:
  if ( v6 && !PostQueuedCompletionStatus(g_WorkerEventPort, 0, (ULONG_PTR)v6, 0) )
  {
    GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
    }
    MMNotification_Event::`scalar deleting destructor'(v6, 1u);
  }
LABEL_33:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  if ( v7 )
    CoTaskMemFree(v7);
  return 0;
}

```

## disassembly

```asm
0x18003d7a0  mov     [rsp-38h+arg_8], rbx
0x18003d7a5  push    rbp
0x18003d7a6  push    rsi
0x18003d7a7  push    rdi
0x18003d7a8  push    r12
0x18003d7aa  push    r13
0x18003d7ac  push    r14
0x18003d7ae  push    r15
0x18003d7b0  mov     rbp, rsp
0x18003d7b3  sub     rsp, 40h
0x18003d7b7  mov     edi, r8d
0x18003d7ba  mov     r15, rdx
0x18003d7bd  mov     r14, rcx
0x18003d7c0  xor     esi, esi
0x18003d7c2  mov     [rbp+dwCompletionKey], rsi
0x18003d7c6  xor     ebx, ebx
0x18003d7c8  mov     [rbp+arg_18], rbx
0x18003d7cc  mov     [rbp+arg_0], rbx
0x18003d7d0  lea     rax, WPP_GLOBAL_Control
0x18003d7d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d7de  cmp     rcx, rax
0x18003d7e1  jz      short loc_18003D809
0x18003d7e3  test    dword ptr [rcx+1Ch], 80000h
0x18003d7ea  jz      short loc_18003D809
0x18003d7ec  cmp     byte ptr [rcx+19h], 5
0x18003d7f0  jb      short loc_18003D809
0x18003d7f2  mov     [rsp+40h+var_18], r8d
0x18003d7f7  mov     [rsp+40h+var_20], rdx
0x18003d7fc  mov     r9d, [r14+8]
0x18003d800  mov     rcx, [rcx+10h]
0x18003d804  call    WPP_SF_dSd
0x18003d809  mov     rcx, r15; unsigned __int16 *
0x18003d80c  call    ?GetLocalEndpointIdForRemoteEndpointId@@YAPEBGPEBG@Z; GetLocalEndpointIdForRemoteEndpointId(ushort const *)
0x18003d811  mov     r13, rax
0x18003d814  mov     r12, [r14+10h]
0x18003d818  mov     rcx, [r12]
0x18003d81c  mov     rax, [rcx+28h]
0x18003d820  mov     [rbp+var_8], rax
0x18003d824  mov     rcx, [rbp+arg_0]
0x18003d828  mov     [rbp+arg_0], 0
0x18003d830  test    rcx, rcx
0x18003d833  jz      short loc_18003D845
0x18003d835  mov     rdx, [rcx]
0x18003d838  mov     rax, [rdx+10h]
0x18003d83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d841  mov     rax, [rbp+var_8]
0x18003d845  lea     r8, [rbp+arg_0]
0x18003d849  mov     rdx, r13
0x18003d84c  mov     rcx, r12
0x18003d84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d854  test    eax, eax
0x18003d856  jns     short loc_18003D8A0
0x18003d858  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d85f  lea     rdi, WPP_GLOBAL_Control
0x18003d866  cmp     rcx, rdi
0x18003d869  jz      loc_18003DA23
0x18003d86f  test    dword ptr [rcx+1Ch], 80000h
0x18003d876  jz      loc_18003DA23
0x18003d87c  cmp     byte ptr [rcx+19h], 2
0x18003d880  jb      loc_18003DA23
0x18003d886  mov     edx, 44h ; 'D'
0x18003d88b  mov     dword ptr [rsp+40h+var_20], eax
0x18003d88f  mov     r9, r15
0x18003d892  mov     rcx, [rcx+10h]
0x18003d896  call    WPP_SF_Sd
0x18003d89b  jmp     loc_18003DA23
0x18003d8a0  xor     edx, edx
0x18003d8a2  lea     rcx, [rbp+arg_18]
0x18003d8a6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003d8ab  lea     r9, [rbp+arg_18]; unsigned __int16 **
0x18003d8af  mov     r8, r13; unsigned __int16 *
0x18003d8b2  mov     edx, [r14+8]; unsigned int
0x18003d8b6  mov     rcx, [rbp+arg_0]; struct IMMDevice *
0x18003d8ba  call    ?FixupRemoteEndpointId@@YAJPEAUIMMDevice@@KPEBGPEAPEAG@Z; FixupRemoteEndpointId(IMMDevice *,ulong,ushort const *,ushort * *)
0x18003d8bf  mov     rbx, [rbp+arg_18]
0x18003d8c3  test    eax, eax
0x18003d8c5  js      loc_18003DA23
0x18003d8cb  sub     edi, 1
0x18003d8ce  jz      short loc_18003D8FC
0x18003d8d0  sub     edi, 1
0x18003d8d3  jz      short loc_18003D8E3
0x18003d8d5  sub     edi, 2
0x18003d8d8  jz      short loc_18003D8E3
0x18003d8da  cmp     edi, 4
0x18003d8dd  jnz     loc_18003D9A6
0x18003d8e3  lea     r8, [rbp+dwCompletionKey]; struct MMNotification_Event **
0x18003d8e7  mov     rdx, rbx; unsigned __int16 *
0x18003d8ea  mov     rcx, [r14+18h]; struct CAudioDeviceManager *
0x18003d8ee  call    ?CreateDisableDeviceEvent@MMNotification_Event@@SAJPEAVCAudioDeviceManager@@PEBGPEAPEAU1@@Z; MMNotification_Event::CreateDisableDeviceEvent(CAudioDeviceManager *,ushort const *,MMNotification_Event * *)
0x18003d8f3  mov     r14d, eax
0x18003d8f6  mov     rsi, [rbp+dwCompletionKey]
0x18003d8fa  jmp     short loc_18003D965
0x18003d8fc  mov     r15d, [r14+8]
0x18003d900  mov     r12, [rbp+arg_0]
0x18003d904  mov     r14, [r14+18h]
0x18003d908  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003d90d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d912  mov     rdi, rax
0x18003d915  test    rax, rax
0x18003d918  jz      short loc_18003D95F
0x18003d91a  lea     rax, ??_7MMNotification_Event@@6B@; const MMNotification_Event::`vftable'
0x18003d921  mov     [rdi], rax
0x18003d924  mov     dword ptr [rdi+8], 2
0x18003d92b  mov     qword ptr [rdi+10h], 0
0x18003d933  mov     qword ptr [rdi+18h], 0
0x18003d93b  mov     qword ptr [rdi+30h], 0
0x18003d943  mov     [rdi+50h], r14
0x18003d947  xor     r14d, r14d
0x18003d94a  lea     rcx, [rdi+30h]
0x18003d94e  mov     rdx, r12
0x18003d951  call    ??4?$CComPtr@UIMMDevice@@@ATL@@QEAAPEAUIMMDevice@@PEAU2@@Z; ATL::CComPtr<IMMDevice>::operator=(IMMDevice *)
0x18003d956  mov     [rdi+4Ch], r15d
0x18003d95a  mov     rsi, rdi
0x18003d95d  jmp     short loc_18003D965
0x18003d95f  mov     r14d, 8007000Eh
0x18003d965  test    r14d, r14d
0x18003d968  jns     short loc_18003D9A6
0x18003d96a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d971  lea     rdi, WPP_GLOBAL_Control
0x18003d978  cmp     rcx, rdi
0x18003d97b  jz      short loc_18003D9AD
0x18003d97d  test    dword ptr [rcx+1Ch], 80000h
0x18003d984  jz      short loc_18003D9AD
0x18003d986  cmp     byte ptr [rcx+19h], 2
0x18003d98a  jb      short loc_18003D9AD
0x18003d98c  mov     edx, 45h ; 'E'
0x18003d991  mov     r9d, r14d
0x18003d994  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x18003d99b  mov     rcx, [rcx+10h]
0x18003d99f  call    WPP_SF_d
0x18003d9a4  jmp     short loc_18003D9AD
0x18003d9a6  lea     rdi, WPP_GLOBAL_Control
0x18003d9ad  test    rsi, rsi
0x18003d9b0  jz      short loc_18003DA23
0x18003d9b2  xor     r9d, r9d; lpOverlapped
0x18003d9b5  mov     r8, rsi; dwCompletionKey
0x18003d9b8  xor     edx, edx; dwNumberOfBytesTransferred
0x18003d9ba  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; CompletionPort
0x18003d9c1  call    cs:__imp_PostQueuedCompletionStatus
0x18003d9c7  test    eax, eax
0x18003d9c9  jnz     short loc_18003DA23
0x18003d9cb  call    cs:__imp_GetLastError
0x18003d9d1  test    eax, eax
0x18003d9d3  jle     short loc_18003D9DD
0x18003d9d5  movzx   eax, ax
0x18003d9d8  or      eax, 80070000h
0x18003d9dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d9e4  cmp     rcx, rdi
0x18003d9e7  jz      short loc_18003DA10
0x18003d9e9  test    dword ptr [rcx+1Ch], 80000h
0x18003d9f0  jz      short loc_18003DA10
0x18003d9f2  cmp     byte ptr [rcx+19h], 2
0x18003d9f6  jb      short loc_18003DA10
0x18003d9f8  mov     edx, 46h ; 'F'
0x18003d9fd  mov     r9d, eax
0x18003da00  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x18003da07  mov     rcx, [rcx+10h]
0x18003da0b  call    WPP_SF_d
0x18003da10  test    rsi, rsi
0x18003da13  jz      short loc_18003DA23
0x18003da15  mov     edx, 1; unsigned int
0x18003da1a  mov     rcx, rsi; this
0x18003da1d  call    ??_GMMNotification_Event@@UEAAPEAXI@Z; MMNotification_Event::`scalar deleting destructor'(uint)
0x18003da22  nop
0x18003da23  lea     rcx, [rbp+arg_0]
0x18003da27  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003da2c  nop
0x18003da2d  test    rbx, rbx
0x18003da30  jz      short loc_18003DA3B
0x18003da32  mov     rcx, rbx; pv
0x18003da35  call    cs:__imp_CoTaskMemFree
0x18003da3b  xor     eax, eax
0x18003da3d  mov     rbx, [rsp+40h+arg_8]
0x18003da45  add     rsp, 40h
0x18003da49  pop     r15
0x18003da4b  pop     r14
0x18003da4d  pop     r13
0x18003da4f  pop     r12
0x18003da51  pop     rdi
0x18003da52  pop     rsi
0x18003da53  pop     rbp
0x18003da54  retn
```
