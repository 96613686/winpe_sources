# CRemoteTextAppIntegration::~CRemoteTextAppIntegration(void)

- ea: `0x18001a3b0`
- end: `0x18001a82f`
- name: `??1CRemoteTextAppIntegration@@UEAA@XZ`
- size: `1151`
- prototype: `void __fastcall(CRemoteTextAppIntegration *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001aa80`

## callees

- `0x180010140`
- `0x180014abc`
- `0x180017f2c`
- `0x18001a3b0`
- `0x180024b70`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a7b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a7cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a7b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a7cd`
- `ntdll!RtlDllShutdownInProgress` at `0x18001a3dd`
- `ntdll!RtlDllShutdownInProgress` at `0x18001a3dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRemoteTextAppIntegration::~CRemoteTextAppIntegration(CRemoteTextAppIntegration *this)
{
  MessageProxyReconnectAdapter *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  char *v41; // rcx
  char *v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx

  *(_QWORD *)this = &CRemoteTextAppIntegration::`vftable';
  *((_QWORD *)this + 1) = &CRemoteTextAppIntegration::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &CRemoteTextAppIntegration::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IRemoteAppIntegrationOwner>'};
  if ( !RtlDllShutdownInProgress() )
  {
    v2 = (MessageProxyReconnectAdapter *)*((_QWORD *)this + 110);
    if ( v2 )
    {
      MessageProxyReconnectAdapter::Dispose(v2);
      v3 = *((_QWORD *)this + 110);
      if ( v3 )
      {
        *((_QWORD *)this + 110) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      }
    }
    v4 = *((_QWORD *)this + 5);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 240LL))(v4);
  }
  v5 = *((_QWORD *)this + 110);
  if ( v5 )
  {
    *((_QWORD *)this + 110) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *((_QWORD *)this + 107);
  if ( v6 )
  {
    *((_QWORD *)this + 107) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v6);
  }
  v7 = *((_QWORD *)this + 104);
  if ( v7 )
  {
    *((_QWORD *)this + 104) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v7);
  }
  v8 = *((_QWORD *)this + 101);
  if ( v8 )
  {
    *((_QWORD *)this + 101) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v8);
  }
  v9 = *((_QWORD *)this + 98);
  if ( v9 )
  {
    *((_QWORD *)this + 98) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v9);
  }
  v10 = *((_QWORD *)this + 95);
  if ( v10 )
  {
    *((_QWORD *)this + 95) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v10);
  }
  v11 = *((_QWORD *)this + 92);
  if ( v11 )
  {
    *((_QWORD *)this + 92) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v11);
  }
  v12 = *((_QWORD *)this + 89);
  if ( v12 )
  {
    *((_QWORD *)this + 89) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v12);
  }
  v13 = *((_QWORD *)this + 86);
  if ( v13 )
  {
    *((_QWORD *)this + 86) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v13);
  }
  v14 = *((_QWORD *)this + 83);
  if ( v14 )
  {
    *((_QWORD *)this + 83) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v14);
  }
  v15 = *((_QWORD *)this + 80);
  if ( v15 )
  {
    *((_QWORD *)this + 80) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v15);
  }
  v16 = *((_QWORD *)this + 77);
  if ( v16 )
  {
    *((_QWORD *)this + 77) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v16);
  }
  v17 = *((_QWORD *)this + 74);
  if ( v17 )
  {
    *((_QWORD *)this + 74) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v17);
  }
  v18 = *((_QWORD *)this + 71);
  if ( v18 )
  {
    *((_QWORD *)this + 71) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v18);
  }
  v19 = *((_QWORD *)this + 68);
  if ( v19 )
  {
    *((_QWORD *)this + 68) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v19);
  }
  v20 = *((_QWORD *)this + 65);
  if ( v20 )
  {
    *((_QWORD *)this + 65) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v20);
  }
  v21 = *((_QWORD *)this + 62);
  if ( v21 )
  {
    *((_QWORD *)this + 62) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v21);
  }
  v22 = *((_QWORD *)this + 59);
  if ( v22 )
  {
    *((_QWORD *)this + 59) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v22);
  }
  v23 = *((_QWORD *)this + 56);
  if ( v23 )
  {
    *((_QWORD *)this + 56) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v23);
  }
  v24 = *((_QWORD *)this + 53);
  if ( v24 )
  {
    *((_QWORD *)this + 53) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v24);
  }
  v25 = *((_QWORD *)this + 50);
  if ( v25 )
  {
    *((_QWORD *)this + 50) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v25);
  }
  v26 = *((_QWORD *)this + 47);
  if ( v26 )
  {
    *((_QWORD *)this + 47) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v26);
  }
  v27 = *((_QWORD *)this + 44);
  if ( v27 )
  {
    *((_QWORD *)this + 44) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v27);
  }
  v28 = *((_QWORD *)this + 41);
  if ( v28 )
  {
    *((_QWORD *)this + 41) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v28);
  }
  v29 = *((_QWORD *)this + 38);
  if ( v29 )
  {
    *((_QWORD *)this + 38) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v29);
  }
  v30 = *((_QWORD *)this + 35);
  if ( v30 )
  {
    *((_QWORD *)this + 35) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v30);
  }
  v31 = *((_QWORD *)this + 32);
  if ( v31 )
  {
    *((_QWORD *)this + 32) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v31);
  }
  v32 = *((_QWORD *)this + 29);
  if ( v32 )
  {
    *((_QWORD *)this + 29) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v32);
  }
  v33 = *((_QWORD *)this + 26);
  if ( v33 )
  {
    *((_QWORD *)this + 26) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v33);
  }
  v34 = *((_QWORD *)this + 23);
  if ( v34 )
  {
    *((_QWORD *)this + 23) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v34);
  }
  v35 = *((_QWORD *)this + 20);
  if ( v35 )
  {
    *((_QWORD *)this + 20) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v35);
  }
  v36 = *((_QWORD *)this + 17);
  if ( v36 )
  {
    *((_QWORD *)this + 17) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v36);
  }
  v37 = *((_QWORD *)this + 16);
  if ( v37 )
  {
    *((_QWORD *)this + 16) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  v38 = *((_QWORD *)this + 15);
  if ( v38 )
  {
    *((_QWORD *)this + 15) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  v39 = *((_QWORD *)this + 14);
  if ( v39 )
  {
    *((_QWORD *)this + 14) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  v40 = *((_QWORD *)this + 13);
  if ( v40 )
  {
    *((_QWORD *)this + 13) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  v41 = (char *)*((_QWORD *)this + 11);
  if ( (unsigned __int64)(v41 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v41);
  v42 = (char *)*((_QWORD *)this + 10);
  if ( (unsigned __int64)(v42 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v42);
  SharedMessagePortRefPtr::Release((CRemoteTextAppIntegration *)((char *)this + 64));
  v43 = *((_QWORD *)this + 6);
  if ( v43 )
  {
    *((_QWORD *)this + 6) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = *((_QWORD *)this + 5);
  if ( v44 )
  {
    *((_QWORD *)this + 5) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = *((_QWORD *)this + 4);
  if ( v45 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextOccludingInputViewsChangedEventArgs *>>::Release(2 * v45);
}

```

## disassembly

```asm
0x18001a3b0  mov     [rsp+arg_0], rbx
0x18001a3b5  push    rdi
0x18001a3b6  sub     rsp, 20h
0x18001a3ba  mov     rbx, rcx
0x18001a3bd  lea     rax, ??_7CRemoteTextAppIntegration@@6B@; const CRemoteTextAppIntegration::`vftable'
0x18001a3c4  mov     [rcx], rax
0x18001a3c7  lea     rax, ??_7CRemoteTextAppIntegration@@6BIWeakReferenceSource@@@; const CRemoteTextAppIntegration::`vftable'{for `IWeakReferenceSource'}
0x18001a3ce  mov     [rcx+8], rax
0x18001a3d2  lea     rax, ??_7CRemoteTextAppIntegration@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIRemoteAppIntegrationOwner@@@Details@WRL@Microsoft@@@; const CRemoteTextAppIntegration::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IRemoteAppIntegrationOwner>'}
0x18001a3d9  mov     [rcx+10h], rax
0x18001a3dd  call    cs:__imp_RtlDllShutdownInProgress
0x18001a3e3  xor     edi, edi
0x18001a3e5  test    al, al
0x18001a3e7  jnz     short loc_18001A434
0x18001a3e9  mov     rcx, [rbx+370h]; this
0x18001a3f0  test    rcx, rcx
0x18001a3f3  jz      short loc_18001A41B
0x18001a3f5  call    ?Dispose@MessageProxyReconnectAdapter@@QEAAJXZ; MessageProxyReconnectAdapter::Dispose(void)
0x18001a3fa  nop
0x18001a3fb  mov     rcx, [rbx+370h]
0x18001a402  test    rcx, rcx
0x18001a405  jz      short loc_18001A41B
0x18001a407  mov     [rbx+370h], rdi
0x18001a40e  mov     rax, [rcx]
0x18001a411  mov     rax, [rax+10h]
0x18001a415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a41a  nop
0x18001a41b  mov     rcx, [rbx+28h]
0x18001a41f  test    rcx, rcx
0x18001a422  jz      short loc_18001A434
0x18001a424  mov     rax, [rcx]
0x18001a427  mov     rax, [rax+0F0h]
0x18001a42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a433  nop
0x18001a434  mov     rcx, [rbx+370h]
0x18001a43b  test    rcx, rcx
0x18001a43e  jz      short loc_18001A454
0x18001a440  mov     [rbx+370h], rdi
0x18001a447  mov     rax, [rcx]
0x18001a44a  mov     rax, [rax+10h]
0x18001a44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a453  nop
0x18001a454  mov     rcx, [rbx+358h]
0x18001a45b  test    rcx, rcx
0x18001a45e  jz      short loc_18001A46C
0x18001a460  mov     [rbx+358h], rdi
0x18001a467  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a46c  mov     rcx, [rbx+340h]
0x18001a473  test    rcx, rcx
0x18001a476  jz      short loc_18001A484
0x18001a478  mov     [rbx+340h], rdi
0x18001a47f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a484  mov     rcx, [rbx+328h]
0x18001a48b  test    rcx, rcx
0x18001a48e  jz      short loc_18001A49C
0x18001a490  mov     [rbx+328h], rdi
0x18001a497  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a49c  mov     rcx, [rbx+310h]
0x18001a4a3  test    rcx, rcx
0x18001a4a6  jz      short loc_18001A4B4
0x18001a4a8  mov     [rbx+310h], rdi
0x18001a4af  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a4b4  mov     rcx, [rbx+2F8h]
0x18001a4bb  test    rcx, rcx
0x18001a4be  jz      short loc_18001A4CC
0x18001a4c0  mov     [rbx+2F8h], rdi
0x18001a4c7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a4cc  mov     rcx, [rbx+2E0h]
0x18001a4d3  test    rcx, rcx
0x18001a4d6  jz      short loc_18001A4E4
0x18001a4d8  mov     [rbx+2E0h], rdi
0x18001a4df  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a4e4  mov     rcx, [rbx+2C8h]
0x18001a4eb  test    rcx, rcx
0x18001a4ee  jz      short loc_18001A4FC
0x18001a4f0  mov     [rbx+2C8h], rdi
0x18001a4f7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a4fc  mov     rcx, [rbx+2B0h]
0x18001a503  test    rcx, rcx
0x18001a506  jz      short loc_18001A514
0x18001a508  mov     [rbx+2B0h], rdi
0x18001a50f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a514  mov     rcx, [rbx+298h]
0x18001a51b  test    rcx, rcx
0x18001a51e  jz      short loc_18001A52C
0x18001a520  mov     [rbx+298h], rdi
0x18001a527  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a52c  mov     rcx, [rbx+280h]
0x18001a533  test    rcx, rcx
0x18001a536  jz      short loc_18001A544
0x18001a538  mov     [rbx+280h], rdi
0x18001a53f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a544  mov     rcx, [rbx+268h]
0x18001a54b  test    rcx, rcx
0x18001a54e  jz      short loc_18001A55C
0x18001a550  mov     [rbx+268h], rdi
0x18001a557  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a55c  mov     rcx, [rbx+250h]
0x18001a563  test    rcx, rcx
0x18001a566  jz      short loc_18001A574
0x18001a568  mov     [rbx+250h], rdi
0x18001a56f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a574  mov     rcx, [rbx+238h]
0x18001a57b  test    rcx, rcx
0x18001a57e  jz      short loc_18001A58C
0x18001a580  mov     [rbx+238h], rdi
0x18001a587  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a58c  mov     rcx, [rbx+220h]
0x18001a593  test    rcx, rcx
0x18001a596  jz      short loc_18001A5A4
0x18001a598  mov     [rbx+220h], rdi
0x18001a59f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a5a4  mov     rcx, [rbx+208h]
0x18001a5ab  test    rcx, rcx
0x18001a5ae  jz      short loc_18001A5BC
0x18001a5b0  mov     [rbx+208h], rdi
0x18001a5b7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a5bc  mov     rcx, [rbx+1F0h]
0x18001a5c3  test    rcx, rcx
0x18001a5c6  jz      short loc_18001A5D4
0x18001a5c8  mov     [rbx+1F0h], rdi
0x18001a5cf  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a5d4  mov     rcx, [rbx+1D8h]
0x18001a5db  test    rcx, rcx
0x18001a5de  jz      short loc_18001A5EC
0x18001a5e0  mov     [rbx+1D8h], rdi
0x18001a5e7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a5ec  mov     rcx, [rbx+1C0h]
0x18001a5f3  test    rcx, rcx
0x18001a5f6  jz      short loc_18001A604
0x18001a5f8  mov     [rbx+1C0h], rdi
0x18001a5ff  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a604  mov     rcx, [rbx+1A8h]
0x18001a60b  test    rcx, rcx
0x18001a60e  jz      short loc_18001A61C
0x18001a610  mov     [rbx+1A8h], rdi
0x18001a617  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a61c  mov     rcx, [rbx+190h]
0x18001a623  test    rcx, rcx
0x18001a626  jz      short loc_18001A634
0x18001a628  mov     [rbx+190h], rdi
0x18001a62f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a634  mov     rcx, [rbx+178h]
0x18001a63b  test    rcx, rcx
0x18001a63e  jz      short loc_18001A64C
0x18001a640  mov     [rbx+178h], rdi
0x18001a647  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a64c  mov     rcx, [rbx+160h]
0x18001a653  test    rcx, rcx
0x18001a656  jz      short loc_18001A664
0x18001a658  mov     [rbx+160h], rdi
0x18001a65f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a664  mov     rcx, [rbx+148h]
0x18001a66b  test    rcx, rcx
0x18001a66e  jz      short loc_18001A67C
0x18001a670  mov     [rbx+148h], rdi
0x18001a677  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a67c  mov     rcx, [rbx+130h]
0x18001a683  test    rcx, rcx
0x18001a686  jz      short loc_18001A694
0x18001a688  mov     [rbx+130h], rdi
0x18001a68f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a694  mov     rcx, [rbx+118h]
0x18001a69b  test    rcx, rcx
0x18001a69e  jz      short loc_18001A6AC
0x18001a6a0  mov     [rbx+118h], rdi
0x18001a6a7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a6ac  mov     rcx, [rbx+100h]
0x18001a6b3  test    rcx, rcx
0x18001a6b6  jz      short loc_18001A6C4
0x18001a6b8  mov     [rbx+100h], rdi
0x18001a6bf  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a6c4  mov     rcx, [rbx+0E8h]
0x18001a6cb  test    rcx, rcx
0x18001a6ce  jz      short loc_18001A6DC
0x18001a6d0  mov     [rbx+0E8h], rdi
0x18001a6d7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a6dc  mov     rcx, [rbx+0D0h]
0x18001a6e3  test    rcx, rcx
0x18001a6e6  jz      short loc_18001A6F4
0x18001a6e8  mov     [rbx+0D0h], rdi
0x18001a6ef  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a6f4  mov     rcx, [rbx+0B8h]
0x18001a6fb  test    rcx, rcx
0x18001a6fe  jz      short loc_18001A70C
0x18001a700  mov     [rbx+0B8h], rdi
0x18001a707  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a70c  mov     rcx, [rbx+0A0h]
0x18001a713  test    rcx, rcx
0x18001a716  jz      short loc_18001A724
0x18001a718  mov     [rbx+0A0h], rdi
0x18001a71f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a724  mov     rcx, [rbx+88h]
0x18001a72b  test    rcx, rcx
0x18001a72e  jz      short loc_18001A73D
0x18001a730  mov     [rbx+88h], rdi
0x18001a737  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001a73c  nop
0x18001a73d  mov     rcx, [rbx+80h]
0x18001a744  test    rcx, rcx
0x18001a747  jz      short loc_18001A75D
0x18001a749  mov     [rbx+80h], rdi
0x18001a750  mov     rax, [rcx]
0x18001a753  mov     rax, [rax+10h]
0x18001a757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a75c  nop
0x18001a75d  mov     rcx, [rbx+78h]
0x18001a761  test    rcx, rcx
0x18001a764  jz      short loc_18001A777
0x18001a766  mov     [rbx+78h], rdi
0x18001a76a  mov     rax, [rcx]
0x18001a76d  mov     rax, [rax+10h]
0x18001a771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a776  nop
0x18001a777  mov     rcx, [rbx+70h]
0x18001a77b  test    rcx, rcx
0x18001a77e  jz      short loc_18001A791
0x18001a780  mov     [rbx+70h], rdi
0x18001a784  mov     rax, [rcx]
0x18001a787  mov     rax, [rax+10h]
0x18001a78b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a790  nop
0x18001a791  mov     rcx, [rbx+68h]
0x18001a795  test    rcx, rcx
0x18001a798  jz      short loc_18001A7AB
0x18001a79a  mov     [rbx+68h], rdi
0x18001a79e  mov     rax, [rcx]
0x18001a7a1  mov     rax, [rax+10h]
0x18001a7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7aa  nop
0x18001a7ab  mov     rcx, [rbx+58h]; hObject
0x18001a7af  lea     rax, [rcx-1]
0x18001a7b3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a7b7  ja      short loc_18001A7BF
0x18001a7b9  call    cs:__imp_CloseHandle
0x18001a7bf  mov     rcx, [rbx+50h]; hObject
0x18001a7c3  lea     rax, [rcx-1]
0x18001a7c7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a7cb  ja      short loc_18001A7D4
0x18001a7cd  call    cs:__imp_CloseHandle
0x18001a7d3  nop
0x18001a7d4  lea     rcx, [rbx+40h]; this
0x18001a7d8  call    ?Release@SharedMessagePortRefPtr@@QEAAXXZ; SharedMessagePortRefPtr::Release(void)
0x18001a7dd  nop
0x18001a7de  mov     rcx, [rbx+30h]
0x18001a7e2  test    rcx, rcx
0x18001a7e5  jz      short loc_18001A7F8
0x18001a7e7  mov     [rbx+30h], rdi
0x18001a7eb  mov     rax, [rcx]
0x18001a7ee  mov     rax, [rax+10h]
0x18001a7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7f7  nop
0x18001a7f8  mov     rcx, [rbx+28h]
0x18001a7fc  test    rcx, rcx
0x18001a7ff  jz      short loc_18001A812
0x18001a801  mov     [rbx+28h], rdi
0x18001a805  mov     rax, [rcx]
0x18001a808  mov     rax, [rax+10h]
0x18001a80c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a811  nop
0x18001a812  mov     rcx, [rbx+20h]
0x18001a816  test    rcx, rcx
0x18001a819  jns     short loc_18001A824
0x18001a81b  add     rcx, rcx
0x18001a81e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextOccludingInputViewsChangedEventArgs@23456@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextOccludingInputViewsChangedEventArgs *>>::Release(void)
0x18001a823  nop
0x18001a824  mov     rbx, [rsp+28h+arg_0]
0x18001a829  add     rsp, 20h
0x18001a82d  pop     rdi
0x18001a82e  retn
```
