# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,CloudExperienceHostBroker::SyncEngine::IOOBEOneDriveOptin,CloudExperienceHostBroker::SyncEngine::IOneDriveKnownFolderManager,IKnownFolderMoveStatusChangedHandler,CloudExperienceHostBroker::SyncEngine::IOneDriveKnownFolderManager2>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18002d120`
- end: `0x18002d1a5`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIOOBEOneDriveOptin@SyncEngine@CloudExperienceHostBroker@@UIOneDriveKnownFolderManager@56@UIKnownFolderMoveStatusChangedHandler@@UIOneDriveKnownFolderManager2@56@@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `133`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002d1b0`
- `0x18002d1c0`
- `0x18002d1d0`
- `0x18002d3f0`

## callees

- `0x18002d120`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d142`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d142`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,CloudExperienceHostBroker::SyncEngine::IOOBEOneDriveOptin,CloudExperienceHostBroker::SyncEngine::IOneDriveKnownFolderManager,IKnownFolderMoveStatusChangedHandler,CloudExperienceHostBroker::SyncEngine::IOneDriveKnownFolderManager2>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x50u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  v5[1] = GUID_0e811d89_0a93_4c73_ad96_533f8af7b03d;
  v5[2] = GUID_82465af6_b49d_4f06_9959_a23fbd26cb0c;
  v5[3] = GUID_1740b424_4925_4730_8927_7657824ef171;
  v5[4] = GUID_9a5b6c3d_4d5e_4f8b_9c3d_2a6f8b7e3d4c;
  *a2 = 5;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18002d120  mov     [rsp+arg_0], rbx
0x18002d125  push    rdi
0x18002d126  sub     rsp, 20h
0x18002d12a  mov     qword ptr [r8], 0
0x18002d131  mov     ecx, 50h ; 'P'; cb
0x18002d136  mov     dword ptr [rdx], 0
0x18002d13c  mov     rbx, r8
0x18002d13f  mov     rdi, rdx
0x18002d142  call    cs:__imp_CoTaskMemAlloc
0x18002d148  test    rax, rax
0x18002d14b  jnz     short loc_18002D154
0x18002d14d  mov     eax, 8007000Eh
0x18002d152  jmp     short loc_18002D19A
0x18002d154  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18002d15b  movdqu  xmmword ptr [rax], xmm0
0x18002d15f  movups  xmm1, xmmword ptr cs:_GUID_0e811d89_0a93_4c73_ad96_533f8af7b03d.Data1
0x18002d166  movdqu  xmmword ptr [rax+10h], xmm1
0x18002d16b  movups  xmm0, xmmword ptr cs:_GUID_82465af6_b49d_4f06_9959_a23fbd26cb0c.Data1
0x18002d172  movdqu  xmmword ptr [rax+20h], xmm0
0x18002d177  movups  xmm1, xmmword ptr cs:_GUID_1740b424_4925_4730_8927_7657824ef171.Data1
0x18002d17e  movdqu  xmmword ptr [rax+30h], xmm1
0x18002d183  movups  xmm0, xmmword ptr cs:_GUID_9a5b6c3d_4d5e_4f8b_9c3d_2a6f8b7e3d4c.Data1
0x18002d18a  movdqu  xmmword ptr [rax+40h], xmm0
0x18002d18f  mov     dword ptr [rdi], 5
0x18002d195  mov     [rbx], rax
0x18002d198  xor     eax, eax
0x18002d19a  mov     rbx, [rsp+28h+arg_0]
0x18002d19f  add     rsp, 20h
0x18002d1a3  pop     rdi
0x18002d1a4  retn
```
