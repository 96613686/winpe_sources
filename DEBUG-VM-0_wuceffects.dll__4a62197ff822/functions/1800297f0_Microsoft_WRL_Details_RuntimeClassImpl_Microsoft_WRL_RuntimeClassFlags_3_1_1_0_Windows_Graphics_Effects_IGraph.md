# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IBlendEffect>::GetIids(ulong *,_GUID * *)

- ea: `0x1800297f0`
- end: `0x180029875`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIGraphicsEffect@Effects@Graphics@Windows@@UIGraphicsEffectSource@567@UIGraphicsEffectD2D1Interop@567@UIBlendEffect@5Composition@UI@Internal@3@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029880`
- `0x180029890`

## callees

- `0x1800297f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029812`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029812`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IBlendEffect>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x50u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_cb51c0ce_8fe6_4636_b202_861faa07d8f3;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_2d8f9ddc_4339_4eb9_9216_f9deb75658a2;
  v5[3] = GUID_2fc57384_a068_44d7_a331_30982fcf7177;
  v5[4] = GUID_5673248e_7266_5e49_b2ab_2589d5d875c3;
  *a2 = 5;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800297f0  mov     [rsp+arg_0], rbx
0x1800297f5  push    rdi
0x1800297f6  sub     rsp, 20h
0x1800297fa  mov     qword ptr [r8], 0
0x180029801  mov     ecx, 50h ; 'P'; cb
0x180029806  mov     dword ptr [rdx], 0
0x18002980c  mov     rbx, r8
0x18002980f  mov     rdi, rdx
0x180029812  call    cs:__imp_CoTaskMemAlloc
0x180029818  test    rax, rax
0x18002981b  jnz     short loc_180029824
0x18002981d  mov     eax, 8007000Eh
0x180029822  jmp     short loc_18002986A
0x180029824  movups  xmm0, xmmword ptr cs:_GUID_cb51c0ce_8fe6_4636_b202_861faa07d8f3.Data1
0x18002982b  movdqu  xmmword ptr [rax], xmm0
0x18002982f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180029836  movdqu  xmmword ptr [rax+10h], xmm1
0x18002983b  movups  xmm0, xmmword ptr cs:_GUID_2d8f9ddc_4339_4eb9_9216_f9deb75658a2.Data1
0x180029842  movdqu  xmmword ptr [rax+20h], xmm0
0x180029847  movups  xmm1, xmmword ptr cs:_GUID_2fc57384_a068_44d7_a331_30982fcf7177.Data1
0x18002984e  movdqu  xmmword ptr [rax+30h], xmm1
0x180029853  movups  xmm0, xmmword ptr cs:_GUID_5673248e_7266_5e49_b2ab_2589d5d875c3.Data1
0x18002985a  movdqu  xmmword ptr [rax+40h], xmm0
0x18002985f  mov     dword ptr [rdi], 5
0x180029865  mov     [rbx], rax
0x180029868  xor     eax, eax
0x18002986a  mov     rbx, [rsp+28h+arg_0]
0x18002986f  add     rsp, 20h
0x180029873  pop     rdi
0x180029874  retn
```
