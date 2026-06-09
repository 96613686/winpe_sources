# Microsoft::WRL::Details::RuntimeClassBaseT<13>::GetImplementedIIDS<Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IShutdownManagerStatics>,Windows::System::IShutdownManagerStatics2,IInspectable,0>>(Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IShutdownManagerStatics>,Windows::System::IShutdownManagerStatics2,IInspectable,0> *,ulong *,_GUID * *)

- ea: `0x18000a1dc`
- end: `0x18000a274`
- name: `??$GetImplementedIIDS@V?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIShutdownManagerStatics@System@Windows@@@WRL@Microsoft@@UIShutdownManagerStatics2@System@Windows@@UIInspectable@@$0A@@WRL@Microsoft@@@?$RuntimeClassBaseT@$0N@@Details@WRL@Microsoft@@KAJPEAV?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIShutdownManagerStatics@System@Windows@@@WRL@Microsoft@@UIShutdownManagerStatics2@System@Windows@@UIInspectable@@$0A@@23@PEAKPEAPEAU_GUID@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000be80`

## callees

- `0x18000a1dc`
- `0x18000bb18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a203`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a203`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<13>::GetImplementedIIDS<Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IShutdownManagerStatics>,Windows::System::IShutdownManagerStatics2,IInspectable,0>>(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = a1;
  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  LODWORD(v10) = 1;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IShutdownManagerStatics>::FillArrayWithIid(
    v6,
    &v10,
    v5);
  v8 = 2LL * (unsigned int)(v10 + 1);
  *(GUID *)(v9 + 16LL * (unsigned int)v10) = GUID_0f69a02f_9c34_43c7_a8c3_70b30a7f7504;
  result = 0;
  *(GUID *)(v9 + 8 * v8) = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  *a2 = 4;
  *a3 = v9;
  return result;
}

```

## disassembly

```asm
0x18000a1dc  mov     [rsp+arg_8], rbx
0x18000a1e1  mov     [rsp+arg_0], rcx
0x18000a1e6  push    rdi
0x18000a1e7  sub     rsp, 20h
0x18000a1eb  mov     qword ptr [r8], 0
0x18000a1f2  mov     ecx, 40h ; '@'; cb
0x18000a1f7  mov     dword ptr [rdx], 0
0x18000a1fd  mov     rbx, r8
0x18000a200  mov     rdi, rdx
0x18000a203  call    cs:__imp_CoTaskMemAlloc
0x18000a209  mov     r8, rax
0x18000a20c  test    rax, rax
0x18000a20f  jnz     short loc_18000A218
0x18000a211  mov     eax, 8007000Eh
0x18000a216  jmp     short loc_18000A269
0x18000a218  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000a21f  lea     rdx, [rsp+28h+arg_0]
0x18000a224  mov     dword ptr [rsp+28h+arg_0], 1
0x18000a22c  movdqu  xmmword ptr [rax], xmm0
0x18000a230  call    ?FillArrayWithIid@?$Implements@VFtmBase@WRL@Microsoft@@UIShutdownManagerStatics@System@Windows@@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IShutdownManagerStatics>::FillArrayWithIid(ulong *,_GUID *)
0x18000a235  movups  xmm0, xmmword ptr cs:_GUID_0f69a02f_9c34_43c7_a8c3_70b30a7f7504.Data1
0x18000a23c  mov     edx, dword ptr [rsp+28h+arg_0]
0x18000a240  mov     eax, edx
0x18000a242  add     rax, rax
0x18000a245  lea     ecx, [rdx+1]
0x18000a248  add     rcx, rcx
0x18000a24b  movdqu  xmmword ptr [r8+rax*8], xmm0
0x18000a251  xor     eax, eax
0x18000a253  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18000a25a  movdqu  xmmword ptr [r8+rcx*8], xmm0
0x18000a260  mov     dword ptr [rdi], 4
0x18000a266  mov     [rbx], r8
0x18000a269  mov     rbx, [rsp+28h+arg_8]
0x18000a26e  add     rsp, 20h
0x18000a272  pop     rdi
0x18000a273  retn
```
