# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener> *,ulong *,_GUID * *)

- ea: `0x18003958c`
- end: `0x180039629`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCategoryBase@Internal@UX@Networking@Windows@@UIMBCategory@5678@UIMBUXCategory@678@UIMBConnectionFlowCallback@5678@UIInspectableInterfaceNlmChangeListener@5678@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCategoryBase@Internal@UX@Networking@Windows@@UIMBCategory@5678@UIMBUXCategory@678@UIMBConnectionFlowCallback@5678@UIInspectableInterfaceNlmChangeListener@5678@@123@PEAKPEAPEAU_GUID@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d8f0`

## callees

- `0x18003958c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800395ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800395ae`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::CategoryBase,Windows::Networking::UX::Internal::IMBCategory,Windows::Networking::UX::IMBUXCategory,Windows::Networking::UX::Internal::IMBConnectionFlowCallback,Windows::Networking::UX::Internal::IInspectableInterfaceNlmChangeListener>>(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x70u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_91e76f1b_9eef_4592_b3aa_630094a37d41;
  v5[1] = GUID_358557e0_0195_4365_99a6_748b9b74adbf;
  v5[2] = GUID_00000038_0000_0000_c000_000000000046;
  v5[3] = GUID_d1eaf48c_849a_470e_85ba_851de7808d20;
  v5[4] = GUID_a6f7deca_199e_43cc_b675_d539a933109f;
  v5[5] = GUID_39145be5_c859_4f44_a343_50e03542e860;
  v5[6] = GUID_8637bd24_3c2f_448e_8108_07c05bfa0ca2;
  *a2 = 7;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18003958c  mov     [rsp+arg_0], rbx
0x180039591  push    rdi
0x180039592  sub     rsp, 20h
0x180039596  mov     qword ptr [r8], 0
0x18003959d  mov     ecx, 70h ; 'p'; cb
0x1800395a2  mov     dword ptr [rdx], 0
0x1800395a8  mov     rbx, r8
0x1800395ab  mov     rdi, rdx
0x1800395ae  call    cs:__imp_CoTaskMemAlloc
0x1800395b4  test    rax, rax
0x1800395b7  jnz     short loc_1800395C0
0x1800395b9  mov     eax, 8007000Eh
0x1800395be  jmp     short loc_18003961E
0x1800395c0  movups  xmm0, xmmword ptr cs:_GUID_91e76f1b_9eef_4592_b3aa_630094a37d41.Data1
0x1800395c7  movdqu  xmmword ptr [rax], xmm0
0x1800395cb  movups  xmm1, xmmword ptr cs:_GUID_358557e0_0195_4365_99a6_748b9b74adbf.Data1
0x1800395d2  movdqu  xmmword ptr [rax+10h], xmm1
0x1800395d7  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800395de  movdqu  xmmword ptr [rax+20h], xmm0
0x1800395e3  movups  xmm1, xmmword ptr cs:_GUID_d1eaf48c_849a_470e_85ba_851de7808d20.Data1
0x1800395ea  movdqu  xmmword ptr [rax+30h], xmm1
0x1800395ef  movups  xmm0, xmmword ptr cs:_GUID_a6f7deca_199e_43cc_b675_d539a933109f.Data1
0x1800395f6  movdqu  xmmword ptr [rax+40h], xmm0
0x1800395fb  movups  xmm1, xmmword ptr cs:_GUID_39145be5_c859_4f44_a343_50e03542e860.Data1
0x180039602  movdqu  xmmword ptr [rax+50h], xmm1
0x180039607  movups  xmm0, xmmword ptr cs:_GUID_8637bd24_3c2f_448e_8108_07c05bfa0ca2.Data1
0x18003960e  movdqu  xmmword ptr [rax+60h], xmm0
0x180039613  mov     dword ptr [rdi], 7
0x180039619  mov     [rbx], rax
0x18003961c  xor     eax, eax
0x18003961e  mov     rbx, [rsp+28h+arg_0]
0x180039623  add     rsp, 20h
0x180039627  pop     rdi
0x180039628  retn
```
