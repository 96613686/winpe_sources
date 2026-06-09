# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ITextVirtualizationKeyRouting>::GetIids(ulong *,_GUID * *)

- ea: `0x18000d3d0`
- end: `0x18000d43d`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UITextVirtualizationKeyRouting@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d3d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d3f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d3f2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ITextVirtualizationKeyRouting>::GetIids(
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
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  v5[1] = GUID_127c857e_8be3_4298_9e8e_106ca13dbc4d;
  v5[2] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000d3d0  mov     [rsp+arg_0], rbx
0x18000d3d5  push    rdi
0x18000d3d6  sub     rsp, 20h
0x18000d3da  mov     qword ptr [r8], 0
0x18000d3e1  mov     ecx, 30h ; '0'; cb
0x18000d3e6  mov     dword ptr [rdx], 0
0x18000d3ec  mov     rbx, r8
0x18000d3ef  mov     rdi, rdx
0x18000d3f2  call    cs:__imp_CoTaskMemAlloc
0x18000d3f8  test    rax, rax
0x18000d3fb  jnz     short loc_18000D404
0x18000d3fd  mov     eax, 8007000Eh
0x18000d402  jmp     short loc_18000D432
0x18000d404  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18000d40b  movdqu  xmmword ptr [rax], xmm0
0x18000d40f  movups  xmm1, xmmword ptr cs:_GUID_127c857e_8be3_4298_9e8e_106ca13dbc4d.Data1
0x18000d416  movdqu  xmmword ptr [rax+10h], xmm1
0x18000d41b  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18000d422  movdqu  xmmword ptr [rax+20h], xmm0
0x18000d427  mov     dword ptr [rdi], 3
0x18000d42d  mov     [rbx], rax
0x18000d430  xor     eax, eax
0x18000d432  mov     rbx, [rsp+28h+arg_0]
0x18000d437  add     rsp, 20h
0x18000d43b  pop     rdi
0x18000d43c  retn
```
