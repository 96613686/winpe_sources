# CImmersiveWindowFactory::v_CreateSplashScreen(SPLASHSCREEN_FLAGS,ISplashScreen * *)

- ea: `0x1800547c0`
- end: `0x1800548cc`
- name: `?v_CreateSplashScreen@CImmersiveWindowFactory@@EEAAJW4SPLASHSCREEN_FLAGS@@PEAPEAUISplashScreen@@@Z`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180012940`
- `0x1800547c0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005484d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005484d`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x180054894`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x180054894`

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
0x1800547c0  mov     [rsp-18h+arg_8], rbx
0x1800547c5  mov     [rsp-18h+arg_18], rsi
0x1800547ca  push    rbp
0x1800547cb  push    rdi
0x1800547cc  push    r14
0x1800547ce  mov     rbp, rsp
0x1800547d1  sub     rsp, 30h
0x1800547d5  mov     qword ptr [r8], 0
0x1800547dc  mov     rsi, r8
0x1800547df  cmp     byte ptr [rcx+68h], 0
0x1800547e3  mov     r14d, edx
0x1800547e6  mov     rdi, rcx
0x1800547e9  mov     ebx, 80070005h
0x1800547ee  jz      loc_1800548B7
0x1800547f4  mov     rbx, [rcx+0A0h]
0x1800547fb  mov     [rbp+pUnk], 0
0x180054803  test    rbx, rbx
0x180054806  jz      short loc_180054830
0x180054808  lea     rcx, [rbp+arg_10]
0x18005480c  mov     [rbp+arg_10], rbx
0x180054810  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180054815  mov     rcx, [rbp+pUnk]
0x180054819  mov     [rbp+pUnk], rbx
0x18005481d  test    rcx, rcx
0x180054820  jz      short loc_18005487A
0x180054822  mov     rax, [rcx]
0x180054825  mov     rax, [rax+10h]
0x180054829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005482e  jmp     short loc_18005487A
0x180054830  xor     edx, edx; pUnkOuter
0x180054832  lea     rax, [rbp+pUnk]
0x180054836  lea     r9, _GUID_0e0da070_2224_4934_8090_041f7ff223eb; riid
0x18005483d  mov     [rsp+30h+ppv], rax; ppv
0x180054842  lea     rcx, _GUID_329b80ec_2230_47b8_905d_a2dcf5171c6f; rclsid
0x180054849  lea     r8d, [rdx+4]; dwClsContext
0x18005484d  call    cs:__imp_CoCreateInstance
0x180054853  mov     ebx, eax
0x180054855  test    eax, eax
0x180054857  js      short loc_18005489A
0x180054859  mov     rcx, [rbp+pUnk]
0x18005485d  lea     r8, [rdi+74h]
0x180054861  mov     rdx, [rdi+88h]
0x180054868  mov     rax, [rcx]
0x18005486b  mov     rax, [rax+18h]
0x18005486f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054874  mov     ebx, eax
0x180054876  test    eax, eax
0x180054878  js      short loc_18005489A
0x18005487a  lea     rcx, [rbp+pUnk]
0x18005487e  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180054883  mov     rcx, [rbp+pUnk]; pUnk
0x180054887  xor     ebx, ebx
0x180054889  mov     [rsi], rcx
0x18005488c  test    r14b, 20h
0x180054890  jnz     short loc_18005489E
0x180054892  xor     edx, edx; lpvReserved
0x180054894  call    cs:__imp_CoAllowSetForegroundWindow
0x18005489a  mov     rcx, [rbp+pUnk]
0x18005489e  test    rcx, rcx
0x1800548a1  jz      short loc_1800548B7
0x1800548a3  mov     [rbp+pUnk], 0
0x1800548ab  mov     rax, [rcx]
0x1800548ae  mov     rax, [rax+10h]
0x1800548b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548b7  mov     rsi, [rsp+30h+arg_18]
0x1800548bc  mov     eax, ebx
0x1800548be  mov     rbx, [rsp+30h+arg_8]
0x1800548c3  add     rsp, 30h
0x1800548c7  pop     r14
0x1800548c9  pop     rdi
0x1800548ca  pop     rbp
0x1800548cb  retn
```
