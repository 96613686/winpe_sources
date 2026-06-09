# BthCleanUpFakePdoExtensions(DEVICE_EXTENSION *)

- ea: `0x14012e3e0`
- end: `0x14012e612`
- name: `?BthCleanUpFakePdoExtensions@@YAXPEAUDEVICE_EXTENSION@@@Z`
- size: `562`
- prototype: `void __fastcall(struct DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1401bba28`

## callees

- `0x1400043d0`
- `0x140005504`
- `0x140005b4c`
- `0x14001f3f8`
- `0x140035f74`
- `0x140050f5c`
- `0x14012e3e0`
- `0x14014284c`
- `0x1401b9344`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x14012e58b`
- `ntoskrnl!RtlRbRemoveNode` at `0x14012e58b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012e52c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012e52c`

## pseudocode

```c
void __fastcall BthCleanUpFakePdoExtensions(struct DEVICE_EXTENSION *a1)
{
  unsigned __int64 *p_AllChildPdoLock; // r14
  struct DEVICE_EXTENSION *Flink; // rax
  struct DEVICE_EXTENSION *MiniportContext; // rcx
  _DEVICE_OBJECT *FunctionalDeviceObject; // rdx
  struct DEVICE_EXTENSION **v6; // rdx
  int v7; // r8d
  __int64 *v8; // rax
  __int64 *v9; // rcx
  __int64 **v10; // rdx
  struct PDO_EXTENSION *v11; // rbx
  char v12; // r15
  _RTL_RB_TREE *p_ClientRbTree; // rbx
  __int16 v14; // r12
  int v15; // r13d
  _RTL_BALANCED_NODE *Root; // rdi
  unsigned __int64 v17; // rax
  __int64 v18; // rax
  __int64 *v19; // [rsp+50h] [rbp-29h] BYREF
  struct DEVICE_EXTENSION *v20; // [rsp+58h] [rbp-21h]
  __int64 v21; // [rsp+60h] [rbp-19h] BYREF
  char v22; // [rsp+68h] [rbp-11h]
  int v23; // [rsp+69h] [rbp-10h]
  __int16 v24; // [rsp+6Dh] [rbp-Ch]
  char v25; // [rsp+6Fh] [rbp-Ah]
  _BYTE v26[9]; // [rsp+70h] [rbp-9h] BYREF
  int v27; // [rsp+79h] [rbp+0h]
  __int16 v28; // [rsp+7Dh] [rbp+4h]
  char v29; // [rsp+7Fh] [rbp+6h]
  _BYTE v30[80]; // [rsp+80h] [rbp+7h] BYREF

  p_AllChildPdoLock = &a1->AllChildPdoLock;
  v20 = (struct DEVICE_EXTENSION *)&v19;
  v19 = (__int64 *)&v19;
  wil::acquire_kspin_lock(v26, &a1->AllChildPdoLock);
  Flink = (struct DEVICE_EXTENSION *)a1->AllChildPdoList.Flink;
  if ( Flink != (struct DEVICE_EXTENSION *)&a1->AllChildPdoList )
  {
    while ( 1 )
    {
      MiniportContext = (struct DEVICE_EXTENSION *)Flink->BtDevice.MiniportContext;
      if ( Flink->RemoveLock.Common.RemoveEvent.Header.Type )
      {
        if ( (struct DEVICE_EXTENSION *)MiniportContext->BtDevice.FunctionalDeviceObject != Flink
          || (FunctionalDeviceObject = Flink->BtDevice.FunctionalDeviceObject,
              *(struct DEVICE_EXTENSION **)&FunctionalDeviceObject->Type != Flink)
          || (*(_QWORD *)&FunctionalDeviceObject->Type = MiniportContext,
              MiniportContext->BtDevice.FunctionalDeviceObject = FunctionalDeviceObject,
              v6 = (struct DEVICE_EXTENSION **)v20,
              v20->BtDevice.MiniportContext != &v19) )
        {
LABEL_18:
          __fastfail(3u);
        }
        Flink->BtDevice.FunctionalDeviceObject = (_DEVICE_OBJECT *)v20;
        Flink->BtDevice.MiniportContext = &v19;
        *v6 = Flink;
        v20 = Flink;
      }
      if ( MiniportContext == (struct DEVICE_EXTENSION *)&a1->AllChildPdoList )
        break;
      Flink = MiniportContext;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v26);
  while ( 1 )
  {
    v8 = v19;
    if ( v19 == (__int64 *)&v19 )
      break;
    if ( (__int64 **)v19[1] != &v19 )
      goto LABEL_18;
    v9 = (__int64 *)*v19;
    if ( *(__int64 **)(*v19 + 8) != v19 )
      goto LABEL_18;
    v19 = (__int64 *)*v19;
    v10 = &v19;
    v9[1] = (__int64)&v19;
    v11 = (struct PDO_EXTENSION *)(v8 - 1);
    v8[1] = (__int64)v8;
    *v8 = (__int64)v8;
    LOBYTE(v10) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v7) = 1;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v10,
      v7,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      6,
      11,
      (__int64)WPP_d8e0dd4691373d406f8051a14848d93d_Traceguids,
      v11);
    BthPdoDestroyExtension(v11, 0);
    ExFreePoolWithTag(v11, 0);
  }
  wil::acquire_kspin_lock(v26, p_AllChildPdoLock);
  v12 = v29;
  p_ClientRbTree = &a1->ClientRbTree;
  v14 = v28;
  v15 = v27;
  while ( 1 )
  {
    if ( (*(_BYTE *)&a1->ClientRbTree.0 & 1) != 0 )
    {
      Root = p_ClientRbTree->Root;
      if ( !p_ClientRbTree->Root )
        break;
      v17 = (unsigned __int64)p_ClientRbTree ^ (unsigned __int64)Root;
    }
    else
    {
      v17 = (unsigned __int64)p_ClientRbTree->Root;
      Root = p_ClientRbTree->Root;
    }
    if ( !v17 )
      break;
    RtlRbRemoveNode(&a1->ClientRbTree, Root);
    v21 = 0;
    v22 = 0;
    v23 = v15;
    v24 = v14;
    v25 = v12;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::reset(
      v26,
      &v21);
    BthSynchFreeL2capServerInfo((L2CAP_SERVER_INFO *)&Root[-4].16);
    v18 = wil::acquire_kspin_lock(v30, p_AllChildPdoLock);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>>::operator=(
      v26,
      v18);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v30);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v26);
  ScoServer_CleanupInfo(a1);
}

```

## disassembly

```asm
0x14012e3e0  push    rbp
0x14012e3e2  push    rbx
0x14012e3e3  push    rsi
0x14012e3e4  push    rdi
0x14012e3e5  push    r12
0x14012e3e7  push    r13
0x14012e3e9  push    r14
0x14012e3eb  push    r15
0x14012e3ed  lea     rbp, [rsp-1Fh]
0x14012e3f2  sub     rsp, 98h
0x14012e3f9  lea     r14, [rcx+110h]
0x14012e400  mov     rsi, rcx
0x14012e403  lea     rax, [rbp+57h+var_80]
0x14012e407  mov     rdx, r14
0x14012e40a  mov     [rbp+57h+var_78], rax
0x14012e40e  lea     rcx, [rbp+57h+var_60]
0x14012e412  lea     rax, [rbp+57h+var_80]
0x14012e416  mov     [rbp+57h+var_80], rax
0x14012e41a  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14012e41f  lea     r8, [rsi+100h]
0x14012e426  mov     rax, [r8]
0x14012e429  cmp     rax, r8
0x14012e42c  jz      short loc_14012E482
0x14012e42e  cmp     byte ptr [rax+40h], 0
0x14012e432  mov     rcx, [rax]
0x14012e435  jz      short loc_14012E478
0x14012e437  cmp     [rcx+8], rax
0x14012e43b  jnz     loc_14012E53D
0x14012e441  mov     rdx, [rax+8]
0x14012e445  cmp     [rdx], rax
0x14012e448  jnz     loc_14012E53D
0x14012e44e  mov     [rdx], rcx
0x14012e451  lea     r9, [rbp+57h+var_80]
0x14012e455  mov     [rcx+8], rdx
0x14012e459  mov     rdx, [rbp+57h+var_78]
0x14012e45d  cmp     [rdx], r9
0x14012e460  jnz     loc_14012E53D
0x14012e466  mov     [rax+8], rdx
0x14012e46a  lea     r9, [rbp+57h+var_80]
0x14012e46e  mov     [rax], r9
0x14012e471  mov     [rdx], rax
0x14012e474  mov     [rbp+57h+var_78], rax
0x14012e478  cmp     rcx, r8
0x14012e47b  jz      short loc_14012E482
0x14012e47d  mov     rax, rcx
0x14012e480  jmp     short loc_14012E42E
0x14012e482  lea     rcx, [rbp+57h+var_60]
0x14012e486  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14012e48b  mov     rax, [rbp+57h+var_80]
0x14012e48f  lea     rcx, [rbp+57h+var_80]
0x14012e493  cmp     rax, rcx
0x14012e496  jz      loc_14012E544
0x14012e49c  lea     rcx, [rbp+57h+var_80]
0x14012e4a0  cmp     [rax+8], rcx
0x14012e4a4  jnz     loc_14012E53D
0x14012e4aa  mov     rcx, [rax]
0x14012e4ad  cmp     [rcx+8], rax
0x14012e4b1  jnz     loc_14012E53D
0x14012e4b7  mov     [rbp+57h+var_80], rcx
0x14012e4bb  lea     rdx, [rbp+57h+var_80]
0x14012e4bf  mov     [rcx+8], rdx
0x14012e4c3  lea     rbx, [rax-8]
0x14012e4c7  mov     [rax+8], rax
0x14012e4cb  mov     [rax], rax
0x14012e4ce  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14012e4d5  mov     eax, [rcx+2Ch]
0x14012e4d8  test    al, 20h
0x14012e4da  jz      short loc_14012E4E6
0x14012e4dc  cmp     byte ptr [rcx+29h], 4
0x14012e4e0  jb      short loc_14012E4E6
0x14012e4e2  mov     dl, 1
0x14012e4e4  jmp     short loc_14012E4E8
0x14012e4e6  xor     dl, dl
0x14012e4e8  mov     r9, [rcx+40h]
0x14012e4ec  lea     rax, WPP_d8e0dd4691373d406f8051a14848d93d_Traceguids
0x14012e4f3  mov     rcx, [rcx+18h]
0x14012e4f7  mov     r8b, 1
0x14012e4fa  mov     [rsp+0D0h+var_90], rbx
0x14012e4ff  mov     [rsp+0D0h+var_98], rax
0x14012e504  mov     [rsp+0D0h+var_A0], 0Bh
0x14012e50b  mov     [rsp+0D0h+var_A8], 6
0x14012e513  mov     [rsp+0D0h+var_B0], 4
0x14012e518  call    WPP_RECORDER_AND_TRACE_SF_q
0x14012e51d  xor     edx, edx; unsigned __int8
0x14012e51f  mov     rcx, rbx; struct PDO_EXTENSION *
0x14012e522  call    ?BthPdoDestroyExtension@@YAXPEAUPDO_EXTENSION@@E@Z; BthPdoDestroyExtension(PDO_EXTENSION *,uchar)
0x14012e527  xor     edx, edx; Tag
0x14012e529  mov     rcx, rbx; P
0x14012e52c  call    cs:__imp_ExFreePoolWithTag
0x14012e533  nop     dword ptr [rax+rax+00h]
0x14012e538  jmp     loc_14012E48B
0x14012e53d  mov     ecx, 3
0x14012e542  int     29h; Win8: RtlFailFast(ecx)
0x14012e544  mov     rdx, r14
0x14012e547  lea     rcx, [rbp+57h+var_60]
0x14012e54b  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14012e550  mov     r15b, [rbp+57h+var_51]
0x14012e554  lea     rbx, [rsi+0E0h]
0x14012e55b  movzx   r12d, [rbp+57h+var_53]
0x14012e560  mov     r13d, [rbp+57h+var_57]
0x14012e564  test    byte ptr [rbx+8], 1
0x14012e568  jz      short loc_14012E57A
0x14012e56a  mov     rdi, [rbx]
0x14012e56d  test    rdi, rdi
0x14012e570  jz      short loc_14012E5EC
0x14012e572  mov     rax, rdi
0x14012e575  xor     rax, rbx
0x14012e578  jmp     short loc_14012E580
0x14012e57a  mov     rax, [rbx]
0x14012e57d  mov     rdi, rax
0x14012e580  test    rax, rax
0x14012e583  jz      short loc_14012E5EC
0x14012e585  mov     rdx, rdi
0x14012e588  mov     rcx, rbx
0x14012e58b  call    cs:__imp_RtlRbRemoveNode
0x14012e592  nop     dword ptr [rax+rax+00h]
0x14012e597  lea     rdx, [rbp+57h+var_70]
0x14012e59b  mov     [rbp+57h+var_70], 0
0x14012e5a3  lea     rcx, [rbp+57h+var_60]
0x14012e5a7  mov     [rbp+57h+var_68], 0
0x14012e5ab  mov     [rbp+57h+var_67], r13d
0x14012e5af  mov     [rbp+57h+var_63], r12w
0x14012e5b4  mov     [rbp+57h+var_61], r15b
0x14012e5b8  call    ?reset@?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAAXUkspin_lock_saved_irql@23@@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::reset(wil::details::kspin_lock_saved_irql)
0x14012e5bd  lea     rcx, [rdi-50h]; this
0x14012e5c1  call    ?BthSynchFreeL2capServerInfo@@YAXPEAUL2CAP_SERVER_INFO@@@Z; BthSynchFreeL2capServerInfo(L2CAP_SERVER_INFO *)
0x14012e5c6  mov     rdx, r14
0x14012e5c9  lea     rcx, [rbp+57h+var_50]
0x14012e5cd  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14012e5d2  mov     rdx, rax
0x14012e5d5  lea     rcx, [rbp+57h+var_60]
0x14012e5d9  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>> &&)
0x14012e5de  lea     rcx, [rbp+57h+var_50]
0x14012e5e2  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14012e5e7  jmp     loc_14012E564
0x14012e5ec  lea     rcx, [rbp+57h+var_60]
0x14012e5f0  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14012e5f5  mov     rcx, rsi; struct DEVICE_EXTENSION *
0x14012e5f8  call    ?ScoServer_CleanupInfo@@YAXPEAUDEVICE_EXTENSION@@@Z; ScoServer_CleanupInfo(DEVICE_EXTENSION *)
0x14012e5fd  add     rsp, 98h
0x14012e604  pop     r15
0x14012e606  pop     r14
0x14012e608  pop     r13
0x14012e60a  pop     r12
0x14012e60c  pop     rdi
0x14012e60d  pop     rsi
0x14012e60e  pop     rbx
0x14012e60f  pop     rbp
0x14012e610  retn
```
