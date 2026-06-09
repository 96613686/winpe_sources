# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IAppMemoryReport,Windows::System::IAppMemoryReport2,IInspectable>::GetIids(ulong *,_GUID * *)

- ea: `0x180018310`
- end: `0x180018389`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAppMemoryReport@System@Windows@@UIAppMemoryReport2@56@UIInspectable@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018390`
- `0x1800183a0`

## callees

- `0x180018310`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018332`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018332`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IAppMemoryReport,Windows::System::IAppMemoryReport2,IInspectable>::GetIids(
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
  *v5 = GUID_6d65339b_4d6f_45bc_9c5e_e49b3ff2758d;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_5f7f3738_51b7_42dc_b7ed_79ba46d28857;
  v5[3] = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  *a2 = 4;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180018310  mov     [rsp+arg_0], rbx
0x180018315  push    rdi
0x180018316  sub     rsp, 20h
0x18001831a  mov     qword ptr [r8], 0
0x180018321  mov     ecx, 40h ; '@'; cb
0x180018326  mov     dword ptr [rdx], 0
0x18001832c  mov     rbx, r8
0x18001832f  mov     rdi, rdx
0x180018332  call    cs:__imp_CoTaskMemAlloc
0x180018338  test    rax, rax
0x18001833b  jnz     short loc_180018344
0x18001833d  mov     eax, 8007000Eh
0x180018342  jmp     short loc_18001837E
0x180018344  movups  xmm0, xmmword ptr cs:_GUID_6d65339b_4d6f_45bc_9c5e_e49b3ff2758d.Data1
0x18001834b  movdqu  xmmword ptr [rax], xmm0
0x18001834f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180018356  movdqu  xmmword ptr [rax+10h], xmm1
0x18001835b  movups  xmm0, xmmword ptr cs:_GUID_5f7f3738_51b7_42dc_b7ed_79ba46d28857.Data1
0x180018362  movdqu  xmmword ptr [rax+20h], xmm0
0x180018367  movups  xmm1, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18001836e  movdqu  xmmword ptr [rax+30h], xmm1
0x180018373  mov     dword ptr [rdi], 4
0x180018379  mov     [rbx], rax
0x18001837c  xor     eax, eax
0x18001837e  mov     rbx, [rsp+28h+arg_0]
0x180018383  add     rsp, 20h
0x180018387  pop     rdi
0x180018388  retn
```
