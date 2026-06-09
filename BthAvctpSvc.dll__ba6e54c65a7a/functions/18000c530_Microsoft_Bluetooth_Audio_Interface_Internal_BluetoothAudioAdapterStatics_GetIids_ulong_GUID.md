# Microsoft::Bluetooth::Audio::Interface::Internal::BluetoothAudioAdapterStatics::GetIids(ulong *,_GUID * *)

- ea: `0x18000c530`
- end: `0x18000c591`
- name: `?GetIids@BluetoothAudioAdapterStatics@Internal@Interface@Audio@Bluetooth@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Audio::Interface::Internal::BluetoothAudioAdapterStatics *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c5a0`

## callees

- `0x18000c530`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c552`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Audio::Interface::Internal::BluetoothAudioAdapterStatics::GetIids(
        Microsoft::Bluetooth::Audio::Interface::Internal::BluetoothAudioAdapterStatics *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  v5[1] = GUID_7b6acd5a_aa83_5976_a9c4_a82ab1005528;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000c530  mov     [rsp+arg_0], rbx
0x18000c535  push    rdi
0x18000c536  sub     rsp, 20h
0x18000c53a  mov     qword ptr [r8], 0
0x18000c541  mov     ecx, 20h ; ' '; cb
0x18000c546  mov     dword ptr [rdx], 0
0x18000c54c  mov     rbx, r8
0x18000c54f  mov     rdi, rdx
0x18000c552  call    cs:__imp_CoTaskMemAlloc
0x18000c558  test    rax, rax
0x18000c55b  jnz     short loc_18000C564
0x18000c55d  mov     eax, 8007000Eh
0x18000c562  jmp     short loc_18000C586
0x18000c564  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000c56b  movdqu  xmmword ptr [rax], xmm0
0x18000c56f  movups  xmm1, xmmword ptr cs:_GUID_7b6acd5a_aa83_5976_a9c4_a82ab1005528.Data1
0x18000c576  movdqu  xmmword ptr [rax+10h], xmm1
0x18000c57b  mov     dword ptr [rdi], 2
0x18000c581  mov     [rbx], rax
0x18000c584  xor     eax, eax
0x18000c586  mov     rbx, [rsp+28h+arg_0]
0x18000c58b  add     rsp, 20h
0x18000c58f  pop     rdi
0x18000c590  retn
```
