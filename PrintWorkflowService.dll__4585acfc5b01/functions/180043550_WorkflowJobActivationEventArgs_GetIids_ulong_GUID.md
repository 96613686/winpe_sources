# WorkflowJobActivationEventArgs::GetIids(ulong *,_GUID * *)

- ea: `0x180043550`
- end: `0x1800435bd`
- name: `?GetIids@WorkflowJobActivationEventArgs@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(WorkflowJobActivationEventArgs *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800435d0`
- `0x1800435e0`

## callees

- `0x180043550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043572`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043572`

## pseudocode

```c
__int64 __fastcall WorkflowJobActivationEventArgs::GetIids(
        WorkflowJobActivationEventArgs *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_d4bd5e6d_034e_5e00_a616_f961a033dcc8;
  v5[1] = GUID_cf651713_cd08_4fd8_b697_a281b6544e2e;
  v5[2] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180043550  mov     [rsp+arg_0], rbx
0x180043555  push    rdi
0x180043556  sub     rsp, 20h
0x18004355a  mov     qword ptr [r8], 0
0x180043561  mov     ecx, 30h ; '0'; cb
0x180043566  mov     dword ptr [rdx], 0
0x18004356c  mov     rbx, r8
0x18004356f  mov     rdi, rdx
0x180043572  call    cs:__imp_CoTaskMemAlloc
0x180043578  test    rax, rax
0x18004357b  jnz     short loc_180043584
0x18004357d  mov     eax, 8007000Eh
0x180043582  jmp     short loc_1800435B2
0x180043584  movups  xmm0, xmmword ptr cs:_GUID_d4bd5e6d_034e_5e00_a616_f961a033dcc8.Data1
0x18004358b  movdqu  xmmword ptr [rax], xmm0
0x18004358f  movups  xmm1, xmmword ptr cs:_GUID_cf651713_cd08_4fd8_b697_a281b6544e2e.Data1
0x180043596  movdqu  xmmword ptr [rax+10h], xmm1
0x18004359b  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800435a2  movdqu  xmmword ptr [rax+20h], xmm0
0x1800435a7  mov     dword ptr [rdi], 3
0x1800435ad  mov     [rbx], rax
0x1800435b0  xor     eax, eax
0x1800435b2  mov     rbx, [rsp+28h+arg_0]
0x1800435b7  add     rsp, 20h
0x1800435bb  pop     rdi
0x1800435bc  retn
```
