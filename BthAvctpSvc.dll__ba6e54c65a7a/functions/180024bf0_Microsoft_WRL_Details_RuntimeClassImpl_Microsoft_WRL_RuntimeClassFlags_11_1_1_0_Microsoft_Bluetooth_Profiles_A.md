# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,Microsoft::Bluetooth::Profiles::A2dp::Private::IA2dpSinkPlaybackConnection,Windows::Foundation::IClosable,IFastRundown>::GetIids(ulong *,_GUID * *)

- ea: `0x180024bf0`
- end: `0x180024c69`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00$00$0A@UIA2dpSinkPlaybackConnection@Private@A2dp@Profiles@Bluetooth@3@UIClosable@Foundation@Windows@@UIFastRundown@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024c70`

## callees

- `0x180024bf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024c12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024c12`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,Microsoft::Bluetooth::Profiles::A2dp::Private::IA2dpSinkPlaybackConnection,Windows::Foundation::IClosable,IFastRundown>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_e90ebbc0_6f82_5db1_ad4f_ed8ff2a3ddbc;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e;
  v5[3] = GUID_00000040_0000_0000_c000_000000000046;
  *a2 = 4;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180024bf0  mov     [rsp+arg_0], rbx
0x180024bf5  push    rdi
0x180024bf6  sub     rsp, 20h
0x180024bfa  mov     qword ptr [r8], 0
0x180024c01  mov     ecx, 40h ; '@'; cb
0x180024c06  mov     dword ptr [rdx], 0
0x180024c0c  mov     rbx, r8
0x180024c0f  mov     rdi, rdx
0x180024c12  call    cs:__imp_CoTaskMemAlloc
0x180024c18  test    rax, rax
0x180024c1b  jnz     short loc_180024C24
0x180024c1d  mov     eax, 8007000Eh
0x180024c22  jmp     short loc_180024C5E
0x180024c24  movups  xmm0, xmmword ptr cs:_GUID_e90ebbc0_6f82_5db1_ad4f_ed8ff2a3ddbc.Data1
0x180024c2b  movdqu  xmmword ptr [rax], xmm0
0x180024c2f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180024c36  movdqu  xmmword ptr [rax+10h], xmm1
0x180024c3b  movups  xmm0, xmmword ptr cs:_GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e.Data1
0x180024c42  movdqu  xmmword ptr [rax+20h], xmm0
0x180024c47  movups  xmm1, xmmword ptr cs:_GUID_00000040_0000_0000_c000_000000000046.Data1
0x180024c4e  movdqu  xmmword ptr [rax+30h], xmm1
0x180024c53  mov     dword ptr [rdi], 4
0x180024c59  mov     [rbx], rax
0x180024c5c  xor     eax, eax
0x180024c5e  mov     rbx, [rsp+28h+arg_0]
0x180024c63  add     rsp, 20h
0x180024c67  pop     rdi
0x180024c68  retn
```
