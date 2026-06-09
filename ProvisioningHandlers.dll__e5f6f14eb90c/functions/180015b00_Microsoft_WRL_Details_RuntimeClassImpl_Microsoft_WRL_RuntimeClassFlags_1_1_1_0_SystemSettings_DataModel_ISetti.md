# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingsDatabase>::GetIids(ulong *,_GUID * *)

- ea: `0x180015b00`
- end: `0x180015b68`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingsDatabase@DataModel@SystemSettings@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180015b00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015b22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015b22`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingsDatabase>::GetIids(
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
  *v5 = GUID_d68a97b7_4f47_4cb6_9e1f_a01c1232f755;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180015b00  mov     [rsp+arg_0], rbx
0x180015b05  push    rdi
0x180015b06  sub     rsp, 20h
0x180015b0a  mov     qword ptr [r8], 0
0x180015b11  mov     ecx, 20h ; ' '; cb
0x180015b16  mov     dword ptr [rdx], 0
0x180015b1c  mov     rbx, r8
0x180015b1f  mov     rdi, rdx
0x180015b22  call    cs:__imp_CoTaskMemAlloc
0x180015b29  nop     dword ptr [rax+rax+00h]
0x180015b2e  test    rax, rax
0x180015b31  jnz     short loc_180015B3A
0x180015b33  mov     eax, 8007000Eh
0x180015b38  jmp     short loc_180015B5C
0x180015b3a  movups  xmm0, xmmword ptr cs:_GUID_d68a97b7_4f47_4cb6_9e1f_a01c1232f755.Data1
0x180015b41  movdqu  xmmword ptr [rax], xmm0
0x180015b45  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180015b4c  movdqu  xmmword ptr [rax+10h], xmm1
0x180015b51  mov     dword ptr [rdi], 2
0x180015b57  mov     [rbx], rax
0x180015b5a  xor     eax, eax
0x180015b5c  mov     rbx, [rsp+28h+arg_0]
0x180015b61  add     rsp, 20h
0x180015b65  pop     rdi
0x180015b66  retn
```
