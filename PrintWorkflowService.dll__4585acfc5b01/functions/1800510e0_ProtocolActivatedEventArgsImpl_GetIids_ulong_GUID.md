# ProtocolActivatedEventArgsImpl::GetIids(ulong *,_GUID * *)

- ea: `0x1800510e0`
- end: `0x180051165`
- name: `?GetIids@ProtocolActivatedEventArgsImpl@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(ProtocolActivatedEventArgsImpl *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180051170`
- `0x180051180`
- `0x180051190`
- `0x1800511a0`
- `0x1800511c0`

## callees

- `0x1800510e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051102`

## pseudocode

```c
__int64 __fastcall ProtocolActivatedEventArgsImpl::GetIids(
        ProtocolActivatedEventArgsImpl *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x50u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_cf651713_cd08_4fd8_b697_a281b6544e2e;
  v5[1] = GUID_1cf09b9e_9962_4936_80ff_afc8e8ae5c8c;
  v5[2] = GUID_00000038_0000_0000_c000_000000000046;
  v5[3] = GUID_6095f4dd_b7c0_46ab_81fe_d90f36d00d24;
  v5[4] = GUID_d84a0c12_5c8f_438c_83cb_c28fcc0b2fdb;
  *a2 = 5;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800510e0  mov     [rsp+arg_0], rbx
0x1800510e5  push    rdi
0x1800510e6  sub     rsp, 20h
0x1800510ea  mov     qword ptr [r8], 0
0x1800510f1  mov     ecx, 50h ; 'P'; cb
0x1800510f6  mov     dword ptr [rdx], 0
0x1800510fc  mov     rbx, r8
0x1800510ff  mov     rdi, rdx
0x180051102  call    cs:__imp_CoTaskMemAlloc
0x180051108  test    rax, rax
0x18005110b  jnz     short loc_180051114
0x18005110d  mov     eax, 8007000Eh
0x180051112  jmp     short loc_18005115A
0x180051114  movups  xmm0, xmmword ptr cs:_GUID_cf651713_cd08_4fd8_b697_a281b6544e2e.Data1
0x18005111b  movdqu  xmmword ptr [rax], xmm0
0x18005111f  movups  xmm1, xmmword ptr cs:_GUID_1cf09b9e_9962_4936_80ff_afc8e8ae5c8c.Data1
0x180051126  movdqu  xmmword ptr [rax+10h], xmm1
0x18005112b  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180051132  movdqu  xmmword ptr [rax+20h], xmm0
0x180051137  movups  xmm1, xmmword ptr cs:_GUID_6095f4dd_b7c0_46ab_81fe_d90f36d00d24.Data1
0x18005113e  movdqu  xmmword ptr [rax+30h], xmm1
0x180051143  movups  xmm0, xmmword ptr cs:_GUID_d84a0c12_5c8f_438c_83cb_c28fcc0b2fdb.Data1
0x18005114a  movdqu  xmmword ptr [rax+40h], xmm0
0x18005114f  mov     dword ptr [rdi], 5
0x180051155  mov     [rbx], rax
0x180051158  xor     eax, eax
0x18005115a  mov     rbx, [rsp+28h+arg_0]
0x18005115f  add     rsp, 20h
0x180051163  pop     rdi
0x180051164  retn
```
