# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IMBPinUIPrompt>::GetIids(ulong *,_GUID * *)

- ea: `0x180050180`
- end: `0x1800501ed`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCUserInputType@Internal@UX@Networking@Windows@@UIMBPinUIPrompt@678@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050200`

## callees

- `0x180050180`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800501a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800501a2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CUserInputType,Windows::Networking::UX::IMBPinUIPrompt>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_70dba485_cd56_4f15_9f82_86b1460e09a8;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_a58268c7_2d42_468f_a438_0c8a984115c9;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180050180  mov     [rsp+arg_0], rbx
0x180050185  push    rdi
0x180050186  sub     rsp, 20h
0x18005018a  mov     qword ptr [r8], 0
0x180050191  mov     ecx, 30h ; '0'; cb
0x180050196  mov     dword ptr [rdx], 0
0x18005019c  mov     rbx, r8
0x18005019f  mov     rdi, rdx
0x1800501a2  call    cs:__imp_CoTaskMemAlloc
0x1800501a8  test    rax, rax
0x1800501ab  jnz     short loc_1800501B4
0x1800501ad  mov     eax, 8007000Eh
0x1800501b2  jmp     short loc_1800501E2
0x1800501b4  movups  xmm0, xmmword ptr cs:_GUID_70dba485_cd56_4f15_9f82_86b1460e09a8.Data1
0x1800501bb  movdqu  xmmword ptr [rax], xmm0
0x1800501bf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800501c6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800501cb  movups  xmm0, xmmword ptr cs:_GUID_a58268c7_2d42_468f_a438_0c8a984115c9.Data1
0x1800501d2  movdqu  xmmword ptr [rax+20h], xmm0
0x1800501d7  mov     dword ptr [rdi], 3
0x1800501dd  mov     [rbx], rax
0x1800501e0  xor     eax, eax
0x1800501e2  mov     rbx, [rsp+28h+arg_0]
0x1800501e7  add     rsp, 20h
0x1800501eb  pop     rdi
0x1800501ec  retn
```
