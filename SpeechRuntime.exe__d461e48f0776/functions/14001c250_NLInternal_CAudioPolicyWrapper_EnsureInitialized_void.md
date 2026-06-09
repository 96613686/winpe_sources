# NLInternal::CAudioPolicyWrapper::EnsureInitialized(void)

- ea: `0x14001c250`
- end: `0x14001c2ca`
- name: `?EnsureInitialized@CAudioPolicyWrapper@NLInternal@@AEAAJXZ`
- size: `122`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001c2d0`
- `0x14001c3a8`

## callees

- `0x14000c32c`
- `0x140011ea8`
- `0x14001c250`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001c282`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001c282`

## pseudocode

```c
__int64 __fastcall NLInternal::CAudioPolicyWrapper::EnsureInitialized(LPVOID *ppv)
{
  unsigned int v1; // ebx
  HRESULT Instance; // eax

  v1 = 0;
  if ( !*ppv )
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(ppv);
    Instance = CoCreateInstance(
                 &CLSID_SpAudioOrchestratorPolicy,
                 0,
                 1u,
                 &GUID_2aa915a3_492f_4649_85cb_668ca5e7c643,
                 ppv);
    v1 = Instance;
    if ( Instance < 0 )
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"NLInternal::CAudioPolicyWrapper::EnsureInitialized",
        L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\voiceactivation\\audiopolicywrapper.cpp(59)",
        Instance);
  }
  return v1;
}

```

## disassembly

```asm
0x14001c250  mov     [rsp+arg_0], rbx
0x14001c255  push    rdi
0x14001c256  sub     rsp, 30h
0x14001c25a  xor     ebx, ebx
0x14001c25c  mov     rdi, rcx
0x14001c25f  cmp     [rcx], rbx
0x14001c262  jnz     short loc_14001C2BD
0x14001c264  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001c269  lea     r9, _GUID_2aa915a3_492f_4649_85cb_668ca5e7c643; riid
0x14001c270  mov     [rsp+38h+ppv], rdi; ppv
0x14001c275  xor     edx, edx; pUnkOuter
0x14001c277  lea     r8d, [rbx+1]; dwClsContext
0x14001c27b  lea     rcx, CLSID_SpAudioOrchestratorPolicy; rclsid
0x14001c282  call    cs:__imp_CoCreateInstance
0x14001c288  mov     ebx, eax
0x14001c28a  test    eax, eax
0x14001c28c  jns     short loc_14001C2BD
0x14001c28e  mov     [rsp+38h+var_10], eax
0x14001c292  lea     r9, aNlinternalCaud_1; "NLInternal::CAudioPolicyWrapper::Ensure"...
0x14001c299  lea     rax, aOnecoreuapEndu_46; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001c2a0  mov     ecx, 2; int
0x14001c2a5  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14001c2ac  mov     [rsp+38h+ppv], rax
0x14001c2b1  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14001c2b8  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001c2bd  mov     eax, ebx
0x14001c2bf  mov     rbx, [rsp+38h+arg_0]
0x14001c2c4  add     rsp, 30h
0x14001c2c8  pop     rdi
0x14001c2c9  retn
```
