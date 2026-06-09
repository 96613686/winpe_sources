# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,Microsoft::Bluetooth::Audio::Interface::Internal::IBluetoothAudioService,Microsoft::WRL::CloakedIid<IFastRundown>>::GetIids(ulong *,_GUID * *)

- ea: `0x18003cd20`
- end: `0x18003cd81`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00$00$0A@UIBluetoothAudioService@Internal@Interface@Audio@Bluetooth@3@U?$CloakedIid@UIFastRundown@@@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003cd20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cd42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cd42`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,Microsoft::Bluetooth::Audio::Interface::Internal::IBluetoothAudioService,Microsoft::WRL::CloakedIid<IFastRundown>>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_680a9aa7_3263_5195_859e_9fe4e4c4e830;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18003cd20  mov     [rsp+arg_0], rbx
0x18003cd25  push    rdi
0x18003cd26  sub     rsp, 20h
0x18003cd2a  mov     qword ptr [r8], 0
0x18003cd31  mov     ecx, 20h ; ' '; cb
0x18003cd36  mov     dword ptr [rdx], 0
0x18003cd3c  mov     rbx, r8
0x18003cd3f  mov     rdi, rdx
0x18003cd42  call    cs:__imp_CoTaskMemAlloc
0x18003cd48  test    rax, rax
0x18003cd4b  jnz     short loc_18003CD54
0x18003cd4d  mov     eax, 8007000Eh
0x18003cd52  jmp     short loc_18003CD76
0x18003cd54  movups  xmm0, xmmword ptr cs:_GUID_680a9aa7_3263_5195_859e_9fe4e4c4e830.Data1
0x18003cd5b  movdqu  xmmword ptr [rax], xmm0
0x18003cd5f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18003cd66  movdqu  xmmword ptr [rax+10h], xmm1
0x18003cd6b  mov     dword ptr [rdi], 2
0x18003cd71  mov     [rbx], rax
0x18003cd74  xor     eax, eax
0x18003cd76  mov     rbx, [rsp+28h+arg_0]
0x18003cd7b  add     rsp, 20h
0x18003cd7f  pop     rdi
0x18003cd80  retn
```
