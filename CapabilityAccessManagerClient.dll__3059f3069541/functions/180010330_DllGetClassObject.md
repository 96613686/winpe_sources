# DllGetClassObject

- ea: `0x180010330`
- end: `0x1800103d6`
- name: `DllGetClassObject`
- size: `166`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800097fc`
- `0x18000b2d4`
- `0x180010330`
- `0x180010500`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800103a4`
- `RPCRT4!NdrDllGetClassObject` at `0x1800103a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  Microsoft::WRL::Details *v7; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_ab2a37ee401e36afdf29befd01c4c394_Traceguids);
  }
  result = NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  if ( result )
  {
    v7 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
    return Microsoft::WRL::Details::GetClassObject<1>(v7, ppv);
  }
  return result;
}

```

## disassembly

```asm
0x180010330  mov     [rsp+arg_0], rbx
0x180010335  mov     [rsp+arg_8], rsi
0x18001033a  push    rdi
0x18001033b  sub     rsp, 30h
0x18001033f  mov     rbx, r8
0x180010342  mov     rdi, rdx
0x180010345  mov     rsi, rcx
0x180010348  mov     rcx, cs:WPP_GLOBAL_Control
0x18001034f  lea     rax, WPP_GLOBAL_Control
0x180010356  cmp     rcx, rax
0x180010359  jz      short loc_18001037C
0x18001035b  test    byte ptr [rcx+1Ch], 1
0x18001035f  jz      short loc_18001037C
0x180010361  cmp     byte ptr [rcx+19h], 5
0x180010365  jb      short loc_18001037C
0x180010367  mov     rcx, [rcx+10h]
0x18001036b  lea     r8, WPP_ab2a37ee401e36afdf29befd01c4c394_Traceguids
0x180010372  mov     edx, 0Dh
0x180010377  call    WPP_SF_
0x18001037c  lea     rax, gPFactory
0x180010383  mov     r8, rbx; ppv
0x180010386  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18001038b  lea     r9, aProxyFileList; pProxyFileList
0x180010392  lea     rax, CLSID_PSFactoryBuffer
0x180010399  mov     rdx, rdi; riid
0x18001039c  mov     rcx, rsi; rclsid
0x18001039f  mov     [rsp+38h+pclsid], rax; pclsid
0x1800103a4  call    cs:__imp_NdrDllGetClassObject
0x1800103aa  test    eax, eax
0x1800103ac  jz      short loc_1800103C6
0x1800103ae  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800103b3  mov     r9, rdi
0x1800103b6  mov     [rsp+38h+pclsid], rbx; PVOID
0x1800103bb  mov     r8, rsi
0x1800103be  mov     rcx, rax; this
0x1800103c1  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x1800103c6  mov     rbx, [rsp+38h+arg_0]
0x1800103cb  mov     rsi, [rsp+38h+arg_8]
0x1800103d0  add     rsp, 30h
0x1800103d4  pop     rdi
0x1800103d5  retn
```
