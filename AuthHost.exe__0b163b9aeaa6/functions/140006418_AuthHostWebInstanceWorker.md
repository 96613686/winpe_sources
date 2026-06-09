# _AuthHostWebInstanceWorker

- ea: `0x140006418`
- end: `0x1400066d4`
- name: `_AuthHostWebInstanceWorker`
- size: `700`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140006340`

## callees

- `0x140002c70`
- `0x140002c98`
- `0x140003a8c`
- `0x1400044c0`
- `0x1400054e0`
- `0x140005940`
- `0x140006418`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000651e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000651e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140006643`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140006643`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000650c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000650c`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x140006469`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1400064ba`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x140006469`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1400064ba`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x140006454`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x140006454`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall AuthHostWebInstanceWorker(__int64 a1)
{
  AuthHostWebInstance *v2; // rbx
  int InterfaceAndReleaseStream; // edi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  signed int LastError; // eax
  char *v7; // rax
  __int64 v8; // rcx
  struct IInspectable *v9; // rcx
  char v11; // [rsp+30h] [rbp-48h] BYREF
  struct tagMSG Msg; // [rsp+38h] [rbp-40h] BYREF
  struct IInspectable *v13; // [rsp+A0h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+A8h] [rbp+30h] BYREF
  __int64 v15; // [rsp+B0h] [rbp+38h] BYREF
  AuthHostWebInstance *v16; // [rsp+B8h] [rbp+40h]

  v2 = 0;
  v16 = 0;
  ppv = 0;
  v13 = 0;
  memset(&Msg, 0, sizeof(Msg));
  PeekMessageW(&Msg, 0, 0, 0, 0);
  InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                *(LPSTREAM *)(a1 + 8),
                                &GUID_00000000_0000_0000_c000_000000000046,
                                &ppv);
  *(_QWORD *)(a1 + 8) = 0;
  if ( InterfaceAndReleaseStream < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
    {
      goto LABEL_34;
    }
    v5 = 10;
LABEL_33:
    WPP_SF_d(v4[7], v5, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids, (unsigned int)InterfaceAndReleaseStream);
LABEL_34:
    *(_DWORD *)(a1 + 24) = InterfaceAndReleaseStream;
    goto LABEL_41;
  }
  InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                *(LPSTREAM *)a1,
                                &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                                (LPVOID *)&v13);
  *(_QWORD *)a1 = 0;
  if ( InterfaceAndReleaseStream < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
    {
      goto LABEL_34;
    }
    v5 = 11;
    goto LABEL_33;
  }
  StartNavigationEvent = CreateEventW(0, 0, 0, 0);
  if ( !StartNavigationEvent )
  {
    LastError = GetLastError();
    InterfaceAndReleaseStream = LastError;
    if ( LastError > 0 )
      InterfaceAndReleaseStream = (unsigned __int16)LastError | 0x80070000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
    {
      goto LABEL_34;
    }
    v5 = 12;
    goto LABEL_33;
  }
  v7 = (char *)Microsoft::WRL::Details::Make<AuthHostWebInstance,>(&v15);
  v2 = 0;
  if ( &v11 != v7 )
  {
    v2 = *(AuthHostWebInstance **)v7;
    *(_QWORD *)v7 = 0;
  }
  v16 = v2;
  v8 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids);
    }
    InterfaceAndReleaseStream = -2147024882;
    goto LABEL_34;
  }
  InterfaceAndReleaseStream = AuthHostWebInstance::Initialize(v2, v13, (struct IUnknown *)ppv);
  if ( InterfaceAndReleaseStream < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
    {
      goto LABEL_34;
    }
    v5 = 14;
    goto LABEL_33;
  }
  *(_DWORD *)(a1 + 24) = 0;
  if ( SetEvent(*(HANDLE *)(a1 + 16)) )
  {
    AuthHostWebInstance::Run(v2);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids);
  }
LABEL_41:
  v9 = v13;
  if ( v13 )
  {
    v13 = 0;
    ((void (__fastcall *)(struct IInspectable *))v9->lpVtbl->Release)(v9);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  if ( v2 )
    (*(void (__fastcall **)(AuthHostWebInstance *))(*(_QWORD *)v2 + 16LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x140006418  push    rbp
0x14000641a  push    rbx
0x14000641b  push    rsi
0x14000641c  push    rdi
0x14000641d  mov     rbp, rsp
0x140006420  sub     rsp, 78h
0x140006424  mov     rsi, rcx
0x140006427  xor     ebx, ebx
0x140006429  mov     [rbp+arg_18], rbx
0x14000642d  mov     [rbp+ppv], rbx
0x140006431  mov     [rbp+arg_0], rbx
0x140006435  xorps   xmm0, xmm0
0x140006438  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x14000643c  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x140006440  movups  xmmword ptr [rbp+Msg.time], xmm0
0x140006444  mov     [rsp+78h+wRemoveMsg], ebx; wRemoveMsg
0x140006448  xor     r9d, r9d; wMsgFilterMax
0x14000644b  xor     r8d, r8d; wMsgFilterMin
0x14000644e  xor     edx, edx; hWnd
0x140006450  lea     rcx, [rbp+Msg]; lpMsg
0x140006454  call    cs:__imp_PeekMessageW
0x14000645a  lea     r8, [rbp+ppv]; ppv
0x14000645e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x140006465  mov     rcx, [rsi+8]; pStm
0x140006469  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x14000646f  mov     edi, eax
0x140006471  mov     [rsi+8], rbx
0x140006475  test    eax, eax
0x140006477  jns     short loc_1400064AC
0x140006479  lea     rax, WPP_GLOBAL_Control
0x140006480  mov     rcx, cs:WPP_GLOBAL_Control
0x140006487  cmp     rcx, rax
0x14000648a  jz      loc_140006633
0x140006490  test    byte ptr [rcx+44h], 2
0x140006494  jz      loc_140006633
0x14000649a  cmp     byte ptr [rcx+41h], 2
0x14000649e  jb      loc_140006633
0x1400064a4  lea     edx, [rbx+0Ah]
0x1400064a7  jmp     loc_140006620
0x1400064ac  lea     r8, [rbp+arg_0]; ppv
0x1400064b0  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; iid
0x1400064b7  mov     rcx, [rsi]; pStm
0x1400064ba  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x1400064c0  mov     edi, eax
0x1400064c2  mov     qword ptr [rsi], 0
0x1400064c9  test    eax, eax
0x1400064cb  jns     short loc_140006502
0x1400064cd  lea     rax, WPP_GLOBAL_Control
0x1400064d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400064db  cmp     rcx, rax
0x1400064de  jz      loc_140006633
0x1400064e4  test    byte ptr [rcx+44h], 2
0x1400064e8  jz      loc_140006633
0x1400064ee  cmp     byte ptr [rcx+41h], 2
0x1400064f2  jb      loc_140006633
0x1400064f8  mov     edx, 0Bh
0x1400064fd  jmp     loc_140006620
0x140006502  xor     r9d, r9d; lpName
0x140006505  xor     r8d, r8d; bInitialState
0x140006508  xor     edx, edx; bManualReset
0x14000650a  xor     ecx, ecx; lpEventAttributes
0x14000650c  call    cs:__imp_CreateEventW
0x140006512  mov     cs:?StartNavigationEvent@@3PEAXEA, rax; void * StartNavigationEvent
0x140006519  test    rax, rax
0x14000651c  jnz     short loc_140006568
0x14000651e  call    cs:__imp_GetLastError
0x140006524  mov     edi, eax
0x140006526  test    eax, eax
0x140006528  jle     short loc_140006533
0x14000652a  movzx   edi, ax
0x14000652d  or      edi, 80070000h
0x140006533  lea     rax, WPP_GLOBAL_Control
0x14000653a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006541  cmp     rcx, rax
0x140006544  jz      loc_140006633
0x14000654a  test    byte ptr [rcx+44h], 2
0x14000654e  jz      loc_140006633
0x140006554  cmp     byte ptr [rcx+41h], 2
0x140006558  jb      loc_140006633
0x14000655e  mov     edx, 0Ch
0x140006563  jmp     loc_140006620
0x140006568  lea     rcx, [rbp+arg_10]
0x14000656c  call    ??$Make@VAuthHostWebInstance@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAuthHostWebInstance@@@12@XZ; Microsoft::WRL::Details::Make<AuthHostWebInstance,>(void)
0x140006571  xor     ebx, ebx
0x140006573  lea     rcx, [rbp+var_48]
0x140006577  cmp     rcx, rax
0x14000657a  jz      short loc_140006586
0x14000657c  mov     rbx, [rax]
0x14000657f  mov     qword ptr [rax], 0
0x140006586  mov     [rbp+arg_18], rbx
0x14000658a  mov     rcx, [rbp+arg_10]
0x14000658e  test    rcx, rcx
0x140006591  jz      short loc_1400065A8
0x140006593  mov     [rbp+arg_10], 0
0x14000659b  mov     rax, [rcx]
0x14000659e  mov     rax, [rax+10h]
0x1400065a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400065a7  nop
0x1400065a8  test    rbx, rbx
0x1400065ab  jnz     short loc_1400065E6
0x1400065ad  lea     rax, WPP_GLOBAL_Control
0x1400065b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400065bb  cmp     rcx, rax
0x1400065be  jz      short loc_1400065DF
0x1400065c0  test    byte ptr [rcx+44h], 2
0x1400065c4  jz      short loc_1400065DF
0x1400065c6  cmp     byte ptr [rcx+41h], 2
0x1400065ca  jb      short loc_1400065DF
0x1400065cc  lea     edx, [rbx+0Dh]
0x1400065cf  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x1400065d6  mov     rcx, [rcx+38h]
0x1400065da  call    WPP_SF_
0x1400065df  mov     edi, 8007000Eh
0x1400065e4  jmp     short loc_140006633
0x1400065e6  mov     r8, [rbp+ppv]; struct IUnknown *
0x1400065ea  mov     rdx, [rbp+arg_0]; struct IInspectable *
0x1400065ee  mov     rcx, rbx; this
0x1400065f1  call    ?Initialize@AuthHostWebInstance@@QEAAJPEAUIInspectable@@PEAUIUnknown@@@Z; AuthHostWebInstance::Initialize(IInspectable *,IUnknown *)
0x1400065f6  mov     edi, eax
0x1400065f8  test    eax, eax
0x1400065fa  jns     short loc_140006638
0x1400065fc  lea     rax, WPP_GLOBAL_Control
0x140006603  mov     rcx, cs:WPP_GLOBAL_Control
0x14000660a  cmp     rcx, rax
0x14000660d  jz      short loc_140006633
0x14000660f  test    byte ptr [rcx+44h], 2
0x140006613  jz      short loc_140006633
0x140006615  cmp     byte ptr [rcx+41h], 2
0x140006619  jb      short loc_140006633
0x14000661b  mov     edx, 0Eh
0x140006620  mov     r9d, edi
0x140006623  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x14000662a  mov     rcx, [rcx+38h]
0x14000662e  call    WPP_SF_d
0x140006633  mov     [rsi+18h], edi
0x140006636  jmp     short loc_14000668C
0x140006638  mov     dword ptr [rsi+18h], 0
0x14000663f  mov     rcx, [rsi+10h]; hEvent
0x140006643  call    cs:__imp_SetEvent
0x140006649  test    eax, eax
0x14000664b  jnz     short loc_140006683
0x14000664d  lea     rax, WPP_GLOBAL_Control
0x140006654  mov     rcx, cs:WPP_GLOBAL_Control
0x14000665b  cmp     rcx, rax
0x14000665e  jz      short loc_14000668C
0x140006660  test    byte ptr [rcx+44h], 2
0x140006664  jz      short loc_14000668C
0x140006666  cmp     byte ptr [rcx+41h], 2
0x14000666a  jb      short loc_14000668C
0x14000666c  mov     edx, 0Fh
0x140006671  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x140006678  mov     rcx, [rcx+38h]
0x14000667c  call    WPP_SF_
0x140006681  jmp     short loc_14000668C
0x140006683  mov     rcx, rbx; this
0x140006686  call    ?Run@AuthHostWebInstance@@QEAAJXZ; AuthHostWebInstance::Run(void)
0x14000668b  nop
0x14000668c  mov     rcx, [rbp+arg_0]
0x140006690  test    rcx, rcx
0x140006693  jz      short loc_1400066AA
0x140006695  mov     [rbp+arg_0], 0
0x14000669d  mov     rax, [rcx]
0x1400066a0  mov     rax, [rax+10h]
0x1400066a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066a9  nop
0x1400066aa  lea     rcx, [rbp+ppv]
0x1400066ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400066b3  nop
0x1400066b4  test    rbx, rbx
0x1400066b7  jz      short loc_1400066C9
0x1400066b9  mov     rax, [rbx]
0x1400066bc  mov     rcx, rbx
0x1400066bf  mov     rax, [rax+10h]
0x1400066c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066c8  nop
0x1400066c9  xor     eax, eax
0x1400066cb  add     rsp, 78h
0x1400066cf  pop     rdi
0x1400066d0  pop     rsi
0x1400066d1  pop     rbx
0x1400066d2  pop     rbp
0x1400066d3  retn
```
