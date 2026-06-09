# CTSSession::OnPropertyValueChanged(ushort const *,_tagpropertykey)

- ea: `0x18003da60`
- end: `0x18003dcfa`
- name: `?OnPropertyValueChanged@CTSSession@@UEAAJPEBGU_tagpropertykey@@@Z`
- size: `666`
- prototype: `int(CTSSession *__hidden this, const unsigned __int16 *, struct _tagpropertykey *__struct_ptr)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180006b0c`
- `0x18000a950`
- `0x18000ab60`
- `0x18000fb60`
- `0x18001e0e0`
- `0x18002389c`
- `0x180027a10`
- `0x180029024`
- `0x180034c5c`
- `0x180035eb4`
- `0x18003da60`
- `0x18003dd00`
- `0x1800597b0`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dc77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dc77`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18003dc6d`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18003dc6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dce1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dce1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CTSSession::OnPropertyValueChanged(
        CTSSession *this,
        const unsigned __int16 *a2,
        struct _tagpropertykey *a3)
{
  unsigned __int16 *v6; // rbx
  const struct _tagpropertykey *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r10
  const unsigned __int16 *LocalEndpointIdForRemoteEndpointId; // r12
  __int64 v11; // r15
  __int64 (__fastcall *v12)(__int64, const unsigned __int16 *, struct IMMDevice **); // r13
  struct IMMDevice *v13; // rcx
  int v14; // eax
  int v15; // r8d
  int v16; // eax
  MMNotification_Event *v17; // rdi
  unsigned __int16 *v19; // [rsp+40h] [rbp-38h] BYREF
  ULONG_PTR dwCompletionKey; // [rsp+48h] [rbp-30h] BYREF
  struct _tagpropertykey v21; // [rsp+50h] [rbp-28h] BYREF
  struct IMMDevice *v22; // [rsp+D8h] [rbp+60h] BYREF

  dwCompletionKey = 0;
  v6 = 0;
  v19 = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dSDd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      (_DWORD)a3,
      *((_DWORD *)this + 2),
      (__int64)a2,
      a3->fmtid.Data1,
      a3->pid);
  }
  if ( (unsigned int)IsInterfaceProperty(a3) || (unsigned int)IsDevnodeProperty(v7) )
  {
    LocalEndpointIdForRemoteEndpointId = GetLocalEndpointIdForRemoteEndpointId(a2);
    v11 = *((_QWORD *)this + 2);
    v12 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, struct IMMDevice **))(*(_QWORD *)v11 + 40LL);
    v13 = v22;
    v22 = 0;
    if ( v13 )
      ((void (__fastcall *)(struct IMMDevice *))v13->lpVtbl->Release)(v13);
    v14 = v12(v11, LocalEndpointIdForRemoteEndpointId, &v22);
    if ( v14 >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v19,
        0);
      v16 = FixupRemoteEndpointId(v22, *((unsigned int *)this + 2), LocalEndpointIdForRemoteEndpointId, &v19);
      v6 = v19;
      if ( v16 >= 0 )
      {
        v21 = *a3;
        if ( (int)MMNotification_Event::CreateUpdateDeviceEvent(
                    *((struct CAudioDeviceManager **)this + 3),
                    v19,
                    &v21,
                    (struct MMNotification_Event **)&dwCompletionKey) < 0
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
        }
        v17 = (MMNotification_Event *)dwCompletionKey;
        if ( dwCompletionKey && !PostQueuedCompletionStatus(g_WorkerEventPort, 0, dwCompletionKey, 0) )
        {
          GetLastError();
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
          }
          if ( v17 )
            MMNotification_Event::`scalar deleting destructor'(v17, 1u);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, v15, (_DWORD)a2, v14);
    }
  }
  else if ( v9 != v8 && (*(_DWORD *)(v9 + 28) & 0x80000) != 0 && *(_BYTE *)(v9 + 25) >= 4u )
  {
    WPP_SF_(*(_QWORD *)(v9 + 16), 72, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
  if ( v6 )
    CoTaskMemFree(v6);
  return 0;
}

```

## disassembly

```asm
0x18003da60  push    rbp
0x18003da62  push    rbx
0x18003da63  push    rsi
0x18003da64  push    rdi
0x18003da65  push    r12
0x18003da67  push    r13
0x18003da69  push    r14
0x18003da6b  push    r15
0x18003da6d  mov     rbp, rsp
0x18003da70  sub     rsp, 78h
0x18003da74  mov     rdi, r8
0x18003da77  mov     r14, rdx
0x18003da7a  mov     rsi, rcx
0x18003da7d  mov     [rbp+dwCompletionKey], 0
0x18003da85  xor     ebx, ebx
0x18003da87  mov     [rbp+var_38], rbx
0x18003da8b  mov     [rbp+arg_18], rbx
0x18003da8f  lea     rdx, WPP_GLOBAL_Control
0x18003da96  mov     r10, cs:WPP_GLOBAL_Control
0x18003da9d  cmp     r10, rdx
0x18003daa0  jz      short loc_18003DAE2
0x18003daa2  test    dword ptr [r10+1Ch], 80000h
0x18003daaa  jz      short loc_18003DAE2
0x18003daac  cmp     byte ptr [r10+19h], 5
0x18003dab1  jb      short loc_18003DAE2
0x18003dab3  mov     eax, [r8+10h]
0x18003dab7  mov     [rsp+78h+var_48], eax
0x18003dabb  mov     eax, [r8]
0x18003dabe  mov     [rsp+78h+var_50], eax
0x18003dac2  mov     [rsp+78h+var_58], r14
0x18003dac7  mov     r9d, [rcx+8]
0x18003dacb  mov     rcx, [r10+10h]
0x18003dacf  call    WPP_SF_dSDd
0x18003dad4  mov     r10, cs:WPP_GLOBAL_Control
0x18003dadb  lea     rdx, WPP_GLOBAL_Control
0x18003dae2  mov     rcx, rdi; struct _tagpropertykey *
0x18003dae5  call    ?IsInterfaceProperty@@YAHPEBU_tagpropertykey@@@Z; IsInterfaceProperty(_tagpropertykey const *)
0x18003daea  test    eax, eax
0x18003daec  jnz     short loc_18003DB31
0x18003daee  call    ?IsDevnodeProperty@@YAHPEBU_tagpropertykey@@@Z; IsDevnodeProperty(_tagpropertykey const *)
0x18003daf3  test    eax, eax
0x18003daf5  jnz     short loc_18003DB31
0x18003daf7  cmp     r10, rdx
0x18003dafa  jz      loc_18003DCCF
0x18003db00  test    dword ptr [r10+1Ch], 80000h
0x18003db08  jz      loc_18003DCCF
0x18003db0e  cmp     byte ptr [r10+19h], 4
0x18003db13  jb      loc_18003DCCF
0x18003db19  lea     edx, [rax+48h]
0x18003db1c  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x18003db23  mov     rcx, [r10+10h]
0x18003db27  call    WPP_SF_
0x18003db2c  jmp     loc_18003DCCF
0x18003db31  mov     rcx, r14; unsigned __int16 *
0x18003db34  call    ?GetLocalEndpointIdForRemoteEndpointId@@YAPEBGPEBG@Z; GetLocalEndpointIdForRemoteEndpointId(ushort const *)
0x18003db39  mov     r12, rax
0x18003db3c  mov     r15, [rsi+10h]
0x18003db40  mov     rcx, [r15]
0x18003db43  mov     r13, [rcx+28h]
0x18003db47  mov     rcx, [rbp+arg_18]
0x18003db4b  mov     [rbp+arg_18], 0
0x18003db53  test    rcx, rcx
0x18003db56  jz      short loc_18003DB65
0x18003db58  mov     rdx, [rcx]
0x18003db5b  mov     rax, [rdx+10h]
0x18003db5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db64  nop
0x18003db65  lea     r8, [rbp+arg_18]
0x18003db69  mov     rdx, r12
0x18003db6c  mov     rcx, r15
0x18003db6f  mov     rax, r13
0x18003db72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db77  test    eax, eax
0x18003db79  jns     short loc_18003DBC3
0x18003db7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db82  lea     rsi, WPP_GLOBAL_Control
0x18003db89  cmp     rcx, rsi
0x18003db8c  jz      loc_18003DCCF
0x18003db92  test    dword ptr [rcx+1Ch], 80000h
0x18003db99  jz      loc_18003DCCF
0x18003db9f  cmp     byte ptr [rcx+19h], 2
0x18003dba3  jb      loc_18003DCCF
0x18003dba9  mov     edx, 49h ; 'I'
0x18003dbae  mov     dword ptr [rsp+78h+var_58], eax
0x18003dbb2  mov     r9, r14
0x18003dbb5  mov     rcx, [rcx+10h]
0x18003dbb9  call    WPP_SF_Sd
0x18003dbbe  jmp     loc_18003DCCF
0x18003dbc3  xor     edx, edx
0x18003dbc5  lea     rcx, [rbp+var_38]
0x18003dbc9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003dbce  lea     r9, [rbp+var_38]; unsigned __int16 **
0x18003dbd2  mov     r8, r12; unsigned __int16 *
0x18003dbd5  mov     edx, [rsi+8]; unsigned int
0x18003dbd8  mov     rcx, [rbp+arg_18]; struct IMMDevice *
0x18003dbdc  call    ?FixupRemoteEndpointId@@YAJPEAUIMMDevice@@KPEBGPEAPEAG@Z; FixupRemoteEndpointId(IMMDevice *,ulong,ushort const *,ushort * *)
0x18003dbe1  mov     rbx, [rbp+var_38]
0x18003dbe5  test    eax, eax
0x18003dbe7  js      loc_18003DCCF
0x18003dbed  movups  xmm0, xmmword ptr [rdi]
0x18003dbf0  movaps  xmmword ptr [rbp+var_28.fmtid.Data1], xmm0
0x18003dbf4  mov     eax, [rdi+10h]
0x18003dbf7  mov     [rbp+var_28.pid], eax
0x18003dbfa  lea     r9, [rbp+dwCompletionKey]; struct MMNotification_Event **
0x18003dbfe  lea     r8, [rbp+var_28]; struct _tagpropertykey
0x18003dc02  mov     rdx, rbx; unsigned __int16 *
0x18003dc05  mov     rcx, [rsi+18h]; struct CAudioDeviceManager *
0x18003dc09  call    ?CreateUpdateDeviceEvent@MMNotification_Event@@SAJPEAVCAudioDeviceManager@@PEBGU_tagpropertykey@@PEAPEAU1@@Z; MMNotification_Event::CreateUpdateDeviceEvent(CAudioDeviceManager *,ushort const *,_tagpropertykey,MMNotification_Event * *)
0x18003dc0e  test    eax, eax
0x18003dc10  jns     short loc_18003DC4E
0x18003dc12  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dc19  lea     rsi, WPP_GLOBAL_Control
0x18003dc20  cmp     rcx, rsi
0x18003dc23  jz      short loc_18003DC55
0x18003dc25  test    dword ptr [rcx+1Ch], 80000h
0x18003dc2c  jz      short loc_18003DC55
0x18003dc2e  cmp     byte ptr [rcx+19h], 2
0x18003dc32  jb      short loc_18003DC55
0x18003dc34  mov     edx, 4Ah ; 'J'
0x18003dc39  mov     r9d, eax
0x18003dc3c  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x18003dc43  mov     rcx, [rcx+10h]
0x18003dc47  call    WPP_SF_d
0x18003dc4c  jmp     short loc_18003DC55
0x18003dc4e  lea     rsi, WPP_GLOBAL_Control
0x18003dc55  mov     rdi, [rbp+dwCompletionKey]
0x18003dc59  test    rdi, rdi
0x18003dc5c  jz      short loc_18003DCCF
0x18003dc5e  xor     r9d, r9d; lpOverlapped
0x18003dc61  mov     r8, rdi; dwCompletionKey
0x18003dc64  xor     edx, edx; dwNumberOfBytesTransferred
0x18003dc66  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; CompletionPort
0x18003dc6d  call    cs:__imp_PostQueuedCompletionStatus
0x18003dc73  test    eax, eax
0x18003dc75  jnz     short loc_18003DCCF
0x18003dc77  call    cs:__imp_GetLastError
0x18003dc7d  test    eax, eax
0x18003dc7f  jle     short loc_18003DC89
0x18003dc81  movzx   eax, ax
0x18003dc84  or      eax, 80070000h
0x18003dc89  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dc90  cmp     rcx, rsi
0x18003dc93  jz      short loc_18003DCBC
0x18003dc95  test    dword ptr [rcx+1Ch], 80000h
0x18003dc9c  jz      short loc_18003DCBC
0x18003dc9e  cmp     byte ptr [rcx+19h], 2
0x18003dca2  jb      short loc_18003DCBC
0x18003dca4  mov     edx, 4Bh ; 'K'
0x18003dca9  mov     r9d, eax
0x18003dcac  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x18003dcb3  mov     rcx, [rcx+10h]
0x18003dcb7  call    WPP_SF_d
0x18003dcbc  test    rdi, rdi
0x18003dcbf  jz      short loc_18003DCCF
0x18003dcc1  mov     edx, 1; unsigned int
0x18003dcc6  mov     rcx, rdi; this
0x18003dcc9  call    ??_GMMNotification_Event@@UEAAPEAXI@Z; MMNotification_Event::`scalar deleting destructor'(uint)
0x18003dcce  nop
0x18003dccf  lea     rcx, [rbp+arg_18]
0x18003dcd3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003dcd8  nop
0x18003dcd9  test    rbx, rbx
0x18003dcdc  jz      short loc_18003DCE7
0x18003dcde  mov     rcx, rbx; pv
0x18003dce1  call    cs:__imp_CoTaskMemFree
0x18003dce7  xor     eax, eax
0x18003dce9  add     rsp, 78h
0x18003dced  pop     r15
0x18003dcef  pop     r14
0x18003dcf1  pop     r13
0x18003dcf3  pop     r12
0x18003dcf5  pop     rdi
0x18003dcf6  pop     rsi
0x18003dcf7  pop     rbx
0x18003dcf8  pop     rbp
0x18003dcf9  retn
```
