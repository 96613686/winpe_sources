# NLInternal::CVAEngineModelWrapper::EnsureInitialized(void)

- ea: `0x14001c5c8`
- end: `0x14001c642`
- name: `?EnsureInitialized@CVAEngineModelWrapper@NLInternal@@AEAAJXZ`
- size: `122`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001c470`
- `0x14001c51c`
- `0x14001c648`
- `0x14001c6fc`
- `0x14001c7b0`
- `0x14001c864`
- `0x14001c918`
- `0x14001c9cc`

## callees

- `0x14000c32c`
- `0x140011ea8`
- `0x14001c5c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001c5fa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001c5fa`

## pseudocode

```c
__int64 __fastcall NLInternal::CVAEngineModelWrapper::EnsureInitialized(LPVOID *ppv)
{
  unsigned int v1; // ebx
  HRESULT Instance; // eax

  v1 = 0;
  if ( !*ppv )
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(ppv);
    Instance = CoCreateInstance(&CLSID_SpVAEngineModel, 0, 0x17u, &GUID_1ef9e8e7_e32c_4466_9bba_a962ea1f0d94, ppv);
    v1 = Instance;
    if ( Instance < 0 )
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"NLInternal::CVAEngineModelWrapper::EnsureInitialized",
        L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\voiceactivation\\vaenginemodelwrapper.cpp(158)",
        Instance);
  }
  return v1;
}

```

## disassembly

```asm
0x14001c5c8  mov     [rsp+arg_0], rbx
0x14001c5cd  push    rdi
0x14001c5ce  sub     rsp, 30h
0x14001c5d2  xor     ebx, ebx
0x14001c5d4  mov     rdi, rcx
0x14001c5d7  cmp     [rcx], rbx
0x14001c5da  jnz     short loc_14001C635
0x14001c5dc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001c5e1  lea     r9, _GUID_1ef9e8e7_e32c_4466_9bba_a962ea1f0d94; riid
0x14001c5e8  mov     [rsp+38h+ppv], rdi; ppv
0x14001c5ed  xor     edx, edx; pUnkOuter
0x14001c5ef  lea     r8d, [rbx+17h]; dwClsContext
0x14001c5f3  lea     rcx, CLSID_SpVAEngineModel; rclsid
0x14001c5fa  call    cs:__imp_CoCreateInstance
0x14001c600  mov     ebx, eax
0x14001c602  test    eax, eax
0x14001c604  jns     short loc_14001C635
0x14001c606  mov     [rsp+38h+var_10], eax
0x14001c60a  lea     r9, aNlinternalCvae; "NLInternal::CVAEngineModelWrapper::Ensu"...
0x14001c611  lea     rax, aOnecoreuapEndu_100; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001c618  mov     ecx, 2; int
0x14001c61d  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14001c624  mov     [rsp+38h+ppv], rax
0x14001c629  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14001c630  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001c635  mov     eax, ebx
0x14001c637  mov     rbx, [rsp+38h+arg_0]
0x14001c63c  add     rsp, 30h
0x14001c640  pop     rdi
0x14001c641  retn
```
