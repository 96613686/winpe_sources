# CImmersiveWindowFactory::v_CreateSplashScreen(SPLASHSCREEN_FLAGS,ISplashScreen * *)

- ea: `0x18003fec0`
- end: `0x18003ffcc`
- name: `?v_CreateSplashScreen@CImmersiveWindowFactory@@EEAAJW4SPLASHSCREEN_FLAGS@@PEAPEAUISplashScreen@@@Z`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003ed0c`
- `0x18003fec0`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ff4d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ff4d`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x18003ff94`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x18003ff94`

## pseudocode

```c
__int64 __fastcall CImmersiveWindowFactory::v_CreateSplashScreen(__int64 a1, char a2, IUnknown **a3)
{
  HRESULT Instance; // ebx
  IUnknown *v7; // rbx
  IUnknown *v8; // rcx
  IUnknown *v9; // rcx
  IUnknown *pUnk; // [rsp+50h] [rbp+20h] BYREF
  IUnknown *v12; // [rsp+60h] [rbp+30h] BYREF

  *a3 = 0;
  Instance = -2147024891;
  if ( !*(_BYTE *)(a1 + 104) )
    return (unsigned int)Instance;
  v7 = *(IUnknown **)(a1 + 160);
  pUnk = 0;
  if ( v7 )
  {
    v12 = v7;
    Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(&v12);
    v8 = pUnk;
    pUnk = v7;
    if ( v8 )
      ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
  }
  else
  {
    Instance = CoCreateInstance(
                 &GUID_329b80ec_2230_47b8_905d_a2dcf5171c6f,
                 0,
                 4u,
                 &GUID_0e0da070_2224_4934_8090_041f7ff223eb,
                 (LPVOID *)&pUnk);
    if ( Instance < 0 )
      goto LABEL_9;
    Instance = ((__int64 (__fastcall *)(IUnknown *, _QWORD, __int64))pUnk->lpVtbl[1].QueryInterface)(
                 pUnk,
                 *(_QWORD *)(a1 + 136),
                 a1 + 116);
    if ( Instance < 0 )
      goto LABEL_9;
  }
  Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(&pUnk);
  v9 = pUnk;
  Instance = 0;
  *a3 = pUnk;
  if ( (a2 & 0x20) != 0 )
    goto LABEL_10;
  CoAllowSetForegroundWindow(v9, 0);
LABEL_9:
  v9 = pUnk;
LABEL_10:
  if ( v9 )
  {
    pUnk = 0;
    ((void (__fastcall *)(IUnknown *))v9->lpVtbl->Release)(v9);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003fec0  mov     [rsp-18h+arg_8], rbx
0x18003fec5  mov     [rsp-18h+arg_18], rsi
0x18003feca  push    rbp
0x18003fecb  push    rdi
0x18003fecc  push    r14
0x18003fece  mov     rbp, rsp
0x18003fed1  sub     rsp, 30h
0x18003fed5  mov     qword ptr [r8], 0
0x18003fedc  mov     rsi, r8
0x18003fedf  cmp     byte ptr [rcx+68h], 0
0x18003fee3  mov     r14d, edx
0x18003fee6  mov     rdi, rcx
0x18003fee9  mov     ebx, 80070005h
0x18003feee  jz      loc_18003FFB7
0x18003fef4  mov     rbx, [rcx+0A0h]
0x18003fefb  mov     [rbp+pUnk], 0
0x18003ff03  test    rbx, rbx
0x18003ff06  jz      short loc_18003FF30
0x18003ff08  lea     rcx, [rbp+arg_10]
0x18003ff0c  mov     [rbp+arg_10], rbx
0x18003ff10  call    ?InternalAddRef@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(void)
0x18003ff15  mov     rcx, [rbp+pUnk]
0x18003ff19  mov     [rbp+pUnk], rbx
0x18003ff1d  test    rcx, rcx
0x18003ff20  jz      short loc_18003FF7A
0x18003ff22  mov     rax, [rcx]
0x18003ff25  mov     rax, [rax+10h]
0x18003ff29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff2e  jmp     short loc_18003FF7A
0x18003ff30  xor     edx, edx; pUnkOuter
0x18003ff32  lea     rax, [rbp+pUnk]
0x18003ff36  lea     r9, _GUID_0e0da070_2224_4934_8090_041f7ff223eb; riid
0x18003ff3d  mov     [rsp+30h+ppv], rax; ppv
0x18003ff42  lea     rcx, _GUID_329b80ec_2230_47b8_905d_a2dcf5171c6f; rclsid
0x18003ff49  lea     r8d, [rdx+4]; dwClsContext
0x18003ff4d  call    cs:__imp_CoCreateInstance
0x18003ff53  mov     ebx, eax
0x18003ff55  test    eax, eax
0x18003ff57  js      short loc_18003FF9A
0x18003ff59  mov     rcx, [rbp+pUnk]
0x18003ff5d  lea     r8, [rdi+74h]
0x18003ff61  mov     rdx, [rdi+88h]
0x18003ff68  mov     rax, [rcx]
0x18003ff6b  mov     rax, [rax+18h]
0x18003ff6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff74  mov     ebx, eax
0x18003ff76  test    eax, eax
0x18003ff78  js      short loc_18003FF9A
0x18003ff7a  lea     rcx, [rbp+pUnk]
0x18003ff7e  call    ?InternalAddRef@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(void)
0x18003ff83  mov     rcx, [rbp+pUnk]; pUnk
0x18003ff87  xor     ebx, ebx
0x18003ff89  mov     [rsi], rcx
0x18003ff8c  test    r14b, 20h
0x18003ff90  jnz     short loc_18003FF9E
0x18003ff92  xor     edx, edx; lpvReserved
0x18003ff94  call    cs:__imp_CoAllowSetForegroundWindow
0x18003ff9a  mov     rcx, [rbp+pUnk]
0x18003ff9e  test    rcx, rcx
0x18003ffa1  jz      short loc_18003FFB7
0x18003ffa3  mov     [rbp+pUnk], 0
0x18003ffab  mov     rax, [rcx]
0x18003ffae  mov     rax, [rax+10h]
0x18003ffb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffb7  mov     rsi, [rsp+30h+arg_18]
0x18003ffbc  mov     eax, ebx
0x18003ffbe  mov     rbx, [rsp+30h+arg_8]
0x18003ffc3  add     rsp, 30h
0x18003ffc7  pop     r14
0x18003ffc9  pop     rdi
0x18003ffca  pop     rbp
0x18003ffcb  retn
```
