# CImmersiveWindowFactory::v_CreateSplashScreen(SPLASHSCREEN_FLAGS,ISplashScreen * *)

- ea: `0x180044670`
- end: `0x18004477c`
- name: `?v_CreateSplashScreen@CImmersiveWindowFactory@@EEAAJW4SPLASHSCREEN_FLAGS@@PEAPEAUISplashScreen@@@Z`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180044350`
- `0x180044670`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800446fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800446fd`
- `ole32!CoAllowSetForegroundWindow` at `0x180044744`
- `ole32!CoAllowSetForegroundWindow` at `0x180044744`

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
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v12);
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
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&pUnk);
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
0x180044670  mov     [rsp-18h+arg_8], rbx
0x180044675  mov     [rsp-18h+arg_18], rsi
0x18004467a  push    rbp
0x18004467b  push    rdi
0x18004467c  push    r14
0x18004467e  mov     rbp, rsp
0x180044681  sub     rsp, 30h
0x180044685  mov     qword ptr [r8], 0
0x18004468c  mov     rsi, r8
0x18004468f  cmp     byte ptr [rcx+68h], 0
0x180044693  mov     r14d, edx
0x180044696  mov     rdi, rcx
0x180044699  mov     ebx, 80070005h
0x18004469e  jz      loc_180044767
0x1800446a4  mov     rbx, [rcx+0A0h]
0x1800446ab  mov     [rbp+pUnk], 0
0x1800446b3  test    rbx, rbx
0x1800446b6  jz      short loc_1800446E0
0x1800446b8  lea     rcx, [rbp+arg_10]
0x1800446bc  mov     [rbp+arg_10], rbx
0x1800446c0  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800446c5  mov     rcx, [rbp+pUnk]
0x1800446c9  mov     [rbp+pUnk], rbx
0x1800446cd  test    rcx, rcx
0x1800446d0  jz      short loc_18004472A
0x1800446d2  mov     rax, [rcx]
0x1800446d5  mov     rax, [rax+10h]
0x1800446d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446de  jmp     short loc_18004472A
0x1800446e0  xor     edx, edx; pUnkOuter
0x1800446e2  lea     rax, [rbp+pUnk]
0x1800446e6  lea     r9, _GUID_0e0da070_2224_4934_8090_041f7ff223eb; riid
0x1800446ed  mov     [rsp+30h+ppv], rax; ppv
0x1800446f2  lea     rcx, _GUID_329b80ec_2230_47b8_905d_a2dcf5171c6f; rclsid
0x1800446f9  lea     r8d, [rdx+4]; dwClsContext
0x1800446fd  call    cs:__imp_CoCreateInstance
0x180044703  mov     ebx, eax
0x180044705  test    eax, eax
0x180044707  js      short loc_18004474A
0x180044709  mov     rcx, [rbp+pUnk]
0x18004470d  lea     r8, [rdi+74h]
0x180044711  mov     rdx, [rdi+88h]
0x180044718  mov     rax, [rcx]
0x18004471b  mov     rax, [rax+18h]
0x18004471f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044724  mov     ebx, eax
0x180044726  test    eax, eax
0x180044728  js      short loc_18004474A
0x18004472a  lea     rcx, [rbp+pUnk]
0x18004472e  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180044733  mov     rcx, [rbp+pUnk]; pUnk
0x180044737  xor     ebx, ebx
0x180044739  mov     [rsi], rcx
0x18004473c  test    r14b, 20h
0x180044740  jnz     short loc_18004474E
0x180044742  xor     edx, edx; lpvReserved
0x180044744  call    cs:__imp_CoAllowSetForegroundWindow
0x18004474a  mov     rcx, [rbp+pUnk]
0x18004474e  test    rcx, rcx
0x180044751  jz      short loc_180044767
0x180044753  mov     [rbp+pUnk], 0
0x18004475b  mov     rax, [rcx]
0x18004475e  mov     rax, [rax+10h]
0x180044762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044767  mov     rsi, [rsp+30h+arg_18]
0x18004476c  mov     eax, ebx
0x18004476e  mov     rbx, [rsp+30h+arg_8]
0x180044773  add     rsp, 30h
0x180044777  pop     r14
0x180044779  pop     rdi
0x18004477a  pop     rbp
0x18004477b  retn
```
