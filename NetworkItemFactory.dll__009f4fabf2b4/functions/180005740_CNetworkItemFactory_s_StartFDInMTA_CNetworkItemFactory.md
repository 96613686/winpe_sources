# CNetworkItemFactory::s_StartFDInMTA(CNetworkItemFactory *)

- ea: `0x180005740`
- end: `0x180005894`
- name: `?s_StartFDInMTA@CNetworkItemFactory@@SAXPEAV1@@Z`
- size: `340`
- prototype: `void __fastcall(struct CNetworkItemFactory *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800033c0`

## callees

- `0x180005150`
- `0x180005740`
- `0x18000589c`
- `0x18000b010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000583a`
- `KERNEL32!WaitForSingleObject` at `0x18000583a`
- `KERNEL32!CloseHandle` at `0x180005843`
- `KERNEL32!CloseHandle` at `0x180005843`
- `KERNEL32!SetEvent` at `0x18000582e`
- `KERNEL32!SetEvent` at `0x18000582e`
- `ole32!CoCreateInstance` at `0x18000577d`
- `ole32!CoCreateInstance` at `0x18000577d`

## pseudocode

```c
void __fastcall CNetworkItemFactory::s_StartFDInMTA(HANDLE *this)
{
  struct IFunctionInstanceCollectionQuery *v1; // rdi
  struct IFunctionInstanceCollectionQuery *v3; // rsi
  HANDLE v4; // rbx
  struct IFunctionDiscovery *v5; // [rsp+50h] [rbp+8h] BYREF
  struct IFunctionInstanceCollectionQuery *v6; // [rsp+58h] [rbp+10h] BYREF
  struct IFunctionInstanceCollectionQuery *v7; // [rsp+60h] [rbp+18h] BYREF

  v1 = 0;
  v6 = 0;
  v3 = 0;
  v7 = 0;
  v5 = 0;
  if ( CoCreateInstance(&CLSID_FunctionDiscovery, 0, 1u, &GUID_4df99b70_e148_4432_b004_4c9eeb535a5e, (LPVOID *)&v5) >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_182dd27e7f09338048566614cf2976f3_Traceguids);
    }
    CNetworkItemFactory::_StartFDQuery((CNetworkItemFactory *)this, v5, L"Layered\\Microsoft.Networking.Devices", &v7);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_182dd27e7f09338048566614cf2976f3_Traceguids);
    }
    CNetworkItemFactory::_StartFDQuery((CNetworkItemFactory *)this, v5, L"Provider\\Microsoft.Networking.Netbios", &v6);
    v1 = v6;
    v3 = v7;
  }
  v4 = this[13];
  SetEvent(this[14]);
  WaitForSingleObject(v4, 0xFFFFFFFF);
  CloseHandle(v4);
  if ( v3 )
    ((void (__fastcall *)(struct IFunctionInstanceCollectionQuery *))v3->lpVtbl->Release)(v3);
  if ( v1 )
    ((void (__fastcall *)(struct IFunctionInstanceCollectionQuery *))v1->lpVtbl->Release)(v1);
  if ( v5 )
    ((void (__fastcall *)(struct IFunctionDiscovery *))v5->lpVtbl->Release)(v5);
}

```

## disassembly

```asm
0x180005740  mov     r11, rsp
0x180005743  mov     [r11+20h], rbx
0x180005747  push    rbp
0x180005748  push    rsi
0x180005749  push    rdi
0x18000574a  sub     rsp, 30h
0x18000574e  xor     edi, edi
0x180005750  lea     rax, [r11+8]
0x180005754  mov     rbp, rcx
0x180005757  mov     [r11+10h], rdi
0x18000575b  xor     esi, esi
0x18000575d  mov     [r11-28h], rax
0x180005761  lea     r9, _GUID_4df99b70_e148_4432_b004_4c9eeb535a5e; riid
0x180005768  mov     [r11+18h], rsi
0x18000576c  lea     r8d, [rdi+1]; dwClsContext
0x180005770  mov     [r11+8], rsi
0x180005774  xor     edx, edx; pUnkOuter
0x180005776  lea     rcx, CLSID_FunctionDiscovery; rclsid
0x18000577d  call    cs:__imp_CoCreateInstance
0x180005783  test    eax, eax
0x180005785  js      loc_180005826
0x18000578b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005792  lea     rbx, WPP_GLOBAL_Control
0x180005799  cmp     rcx, rbx
0x18000579c  jz      short loc_1800057BD
0x18000579e  cmp     byte ptr [rcx+19h], 4
0x1800057a2  jb      short loc_1800057BD
0x1800057a4  test    byte ptr [rcx+1Ch], 2
0x1800057a8  jz      short loc_1800057BD
0x1800057aa  mov     rcx, [rcx+10h]
0x1800057ae  lea     edx, [rdi+13h]
0x1800057b1  lea     r8, WPP_182dd27e7f09338048566614cf2976f3_Traceguids
0x1800057b8  call    WPP_SF_
0x1800057bd  mov     rdx, [rsp+48h+arg_0]; struct IFunctionDiscovery *
0x1800057c2  lea     r9, [rsp+48h+arg_10]; struct IFunctionInstanceCollectionQuery **
0x1800057c7  lea     r8, aLayeredMicroso; "Layered\\Microsoft.Networking.Devices"
0x1800057ce  mov     rcx, rbp; this
0x1800057d1  call    ?_StartFDQuery@CNetworkItemFactory@@AEAAJPEAUIFunctionDiscovery@@PEBGPEAPEAUIFunctionInstanceCollectionQuery@@@Z; CNetworkItemFactory::_StartFDQuery(IFunctionDiscovery *,ushort const *,IFunctionInstanceCollectionQuery * *)
0x1800057d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057dd  cmp     rcx, rbx
0x1800057e0  jz      short loc_180005803
0x1800057e2  cmp     byte ptr [rcx+19h], 4
0x1800057e6  jb      short loc_180005803
0x1800057e8  test    byte ptr [rcx+1Ch], 2
0x1800057ec  jz      short loc_180005803
0x1800057ee  mov     rcx, [rcx+10h]
0x1800057f2  lea     r8, WPP_182dd27e7f09338048566614cf2976f3_Traceguids
0x1800057f9  mov     edx, 14h
0x1800057fe  call    WPP_SF_
0x180005803  mov     rdx, [rsp+48h+arg_0]; struct IFunctionDiscovery *
0x180005808  lea     r9, [rsp+48h+arg_8]; struct IFunctionInstanceCollectionQuery **
0x18000580d  lea     r8, aProviderMicros_0; "Provider\\Microsoft.Networking.Netbios"
0x180005814  mov     rcx, rbp; this
0x180005817  call    ?_StartFDQuery@CNetworkItemFactory@@AEAAJPEAUIFunctionDiscovery@@PEBGPEAPEAUIFunctionInstanceCollectionQuery@@@Z; CNetworkItemFactory::_StartFDQuery(IFunctionDiscovery *,ushort const *,IFunctionInstanceCollectionQuery * *)
0x18000581c  mov     rdi, [rsp+48h+arg_8]
0x180005821  mov     rsi, [rsp+48h+arg_10]
0x180005826  mov     rcx, [rbp+70h]; hEvent
0x18000582a  mov     rbx, [rbp+68h]
0x18000582e  call    cs:__imp_SetEvent
0x180005834  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005837  mov     rcx, rbx; hHandle
0x18000583a  call    cs:__imp_WaitForSingleObject
0x180005840  mov     rcx, rbx; hObject
0x180005843  call    cs:__imp_CloseHandle
0x180005849  test    rsi, rsi
0x18000584c  jz      short loc_18000585D
0x18000584e  mov     rax, [rsi]
0x180005851  mov     rcx, rsi
0x180005854  mov     rax, [rax+10h]
0x180005858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000585d  test    rdi, rdi
0x180005860  jz      short loc_180005871
0x180005862  mov     rax, [rdi]
0x180005865  mov     rcx, rdi
0x180005868  mov     rax, [rax+10h]
0x18000586c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005871  mov     rcx, [rsp+48h+arg_0]
0x180005876  test    rcx, rcx
0x180005879  jz      short loc_180005887
0x18000587b  mov     rax, [rcx]
0x18000587e  mov     rax, [rax+10h]
0x180005882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005887  mov     rbx, [rsp+48h+arg_18]
0x18000588c  add     rsp, 30h
0x180005890  pop     rdi
0x180005891  pop     rsi
0x180005892  pop     rbp
0x180005893  retn
```
