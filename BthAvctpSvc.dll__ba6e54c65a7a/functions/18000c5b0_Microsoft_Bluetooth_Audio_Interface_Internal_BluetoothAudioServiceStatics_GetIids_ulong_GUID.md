# Microsoft::Bluetooth::Audio::Interface::Internal::BluetoothAudioServiceStatics::GetIids(ulong *,_GUID * *)

- ea: `0x18000c5b0`
- end: `0x18000c611`
- name: `?GetIids@BluetoothAudioServiceStatics@Internal@Interface@Audio@Bluetooth@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Audio::Interface::Internal::BluetoothAudioServiceStatics *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c620`

## callees

- `0x18000c5b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c5d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c5d2`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Audio::Interface::Internal::BluetoothAudioServiceStatics::GetIids(
        Microsoft::Bluetooth::Audio::Interface::Internal::BluetoothAudioServiceStatics *this,
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
  v5[1] = GUID_aad2a511_7689_5a94_b5bb_dc600290a493;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000c5b0  mov     [rsp+arg_0], rbx
0x18000c5b5  push    rdi
0x18000c5b6  sub     rsp, 20h
0x18000c5ba  mov     qword ptr [r8], 0
0x18000c5c1  mov     ecx, 20h ; ' '; cb
0x18000c5c6  mov     dword ptr [rdx], 0
0x18000c5cc  mov     rbx, r8
0x18000c5cf  mov     rdi, rdx
0x18000c5d2  call    cs:__imp_CoTaskMemAlloc
0x18000c5d8  test    rax, rax
0x18000c5db  jnz     short loc_18000C5E4
0x18000c5dd  mov     eax, 8007000Eh
0x18000c5e2  jmp     short loc_18000C606
0x18000c5e4  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000c5eb  movdqu  xmmword ptr [rax], xmm0
0x18000c5ef  movups  xmm1, xmmword ptr cs:_GUID_aad2a511_7689_5a94_b5bb_dc600290a493.Data1
0x18000c5f6  movdqu  xmmword ptr [rax+10h], xmm1
0x18000c5fb  mov     dword ptr [rdi], 2
0x18000c601  mov     [rbx], rax
0x18000c604  xor     eax, eax
0x18000c606  mov     rbx, [rsp+28h+arg_0]
0x18000c60b  add     rsp, 20h
0x18000c60f  pop     rdi
0x18000c610  retn
```
