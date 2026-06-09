# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IInspectable>::GetIids(ulong *,_GUID * *)

- ea: `0x1800524b0`
- end: `0x180052511`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInspectable@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800524b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800524d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800524d2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IInspectable>::GetIids(
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
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800524b0  mov     [rsp+arg_0], rbx
0x1800524b5  push    rdi
0x1800524b6  sub     rsp, 20h
0x1800524ba  mov     qword ptr [r8], 0
0x1800524c1  mov     ecx, 20h ; ' '; cb
0x1800524c6  mov     dword ptr [rdx], 0
0x1800524cc  mov     rbx, r8
0x1800524cf  mov     rdi, rdx
0x1800524d2  call    cs:__imp_CoTaskMemAlloc
0x1800524d8  test    rax, rax
0x1800524db  jnz     short loc_1800524E4
0x1800524dd  mov     eax, 8007000Eh
0x1800524e2  jmp     short loc_180052506
0x1800524e4  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x1800524eb  movdqu  xmmword ptr [rax], xmm0
0x1800524ef  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800524f6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800524fb  mov     dword ptr [rdi], 2
0x180052501  mov     [rbx], rax
0x180052504  xor     eax, eax
0x180052506  mov     rbx, [rsp+28h+arg_0]
0x18005250b  add     rsp, 20h
0x18005250f  pop     rdi
0x180052510  retn
```
