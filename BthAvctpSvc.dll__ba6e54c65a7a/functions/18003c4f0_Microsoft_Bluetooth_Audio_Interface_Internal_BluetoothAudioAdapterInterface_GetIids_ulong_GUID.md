# Microsoft::Bluetooth::Audio::Interface::Internal::BluetoothAudioAdapterInterface::GetIids(ulong *,_GUID * *)

- ea: `0x18003c4f0`
- end: `0x18003c551`
- name: `?GetIids@BluetoothAudioAdapterInterface@Internal@Interface@Audio@Bluetooth@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Audio::Interface::Internal::BluetoothAudioAdapterInterface *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003c4f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c512`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c512`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Audio::Interface::Internal::BluetoothAudioAdapterInterface::GetIids(
        Microsoft::Bluetooth::Audio::Interface::Internal::BluetoothAudioAdapterInterface *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_79a07d12_a769_5da8_99ff_723b35d5ab4d;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18003c4f0  mov     [rsp+arg_0], rbx
0x18003c4f5  push    rdi
0x18003c4f6  sub     rsp, 20h
0x18003c4fa  mov     qword ptr [r8], 0
0x18003c501  mov     ecx, 20h ; ' '; cb
0x18003c506  mov     dword ptr [rdx], 0
0x18003c50c  mov     rbx, r8
0x18003c50f  mov     rdi, rdx
0x18003c512  call    cs:__imp_CoTaskMemAlloc
0x18003c518  test    rax, rax
0x18003c51b  jnz     short loc_18003C524
0x18003c51d  mov     eax, 8007000Eh
0x18003c522  jmp     short loc_18003C546
0x18003c524  movups  xmm0, xmmword ptr cs:_GUID_79a07d12_a769_5da8_99ff_723b35d5ab4d.Data1
0x18003c52b  movdqu  xmmword ptr [rax], xmm0
0x18003c52f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18003c536  movdqu  xmmword ptr [rax+10h], xmm1
0x18003c53b  mov     dword ptr [rdi], 2
0x18003c541  mov     [rbx], rax
0x18003c544  xor     eax, eax
0x18003c546  mov     rbx, [rsp+28h+arg_0]
0x18003c54b  add     rsp, 20h
0x18003c54f  pop     rdi
0x18003c550  retn
```
