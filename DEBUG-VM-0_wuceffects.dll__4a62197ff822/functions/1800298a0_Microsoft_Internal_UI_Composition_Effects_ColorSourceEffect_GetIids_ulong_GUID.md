# Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect::GetIids(ulong *,_GUID * *)

- ea: `0x1800298a0`
- end: `0x180029925`
- name: `?GetIids@ColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029930`
- `0x180029940`

## callees

- `0x1800298a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800298c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800298c2`

## pseudocode

```c
__int64 __fastcall Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect::GetIids(
        Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x50u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_cb51c0ce_8fe6_4636_b202_861faa07d8f3;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_2d8f9ddc_4339_4eb9_9216_f9deb75658a2;
  v5[3] = GUID_2fc57384_a068_44d7_a331_30982fcf7177;
  v5[4] = GUID_25f942c7_7fee_518a_ba7b_22a0060af7f6;
  *a2 = 5;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800298a0  mov     [rsp+arg_0], rbx
0x1800298a5  push    rdi
0x1800298a6  sub     rsp, 20h
0x1800298aa  mov     qword ptr [r8], 0
0x1800298b1  mov     ecx, 50h ; 'P'; cb
0x1800298b6  mov     dword ptr [rdx], 0
0x1800298bc  mov     rbx, r8
0x1800298bf  mov     rdi, rdx
0x1800298c2  call    cs:__imp_CoTaskMemAlloc
0x1800298c8  test    rax, rax
0x1800298cb  jnz     short loc_1800298D4
0x1800298cd  mov     eax, 8007000Eh
0x1800298d2  jmp     short loc_18002991A
0x1800298d4  movups  xmm0, xmmword ptr cs:_GUID_cb51c0ce_8fe6_4636_b202_861faa07d8f3.Data1
0x1800298db  movdqu  xmmword ptr [rax], xmm0
0x1800298df  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800298e6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800298eb  movups  xmm0, xmmword ptr cs:_GUID_2d8f9ddc_4339_4eb9_9216_f9deb75658a2.Data1
0x1800298f2  movdqu  xmmword ptr [rax+20h], xmm0
0x1800298f7  movups  xmm1, xmmword ptr cs:_GUID_2fc57384_a068_44d7_a331_30982fcf7177.Data1
0x1800298fe  movdqu  xmmword ptr [rax+30h], xmm1
0x180029903  movups  xmm0, xmmword ptr cs:_GUID_25f942c7_7fee_518a_ba7b_22a0060af7f6.Data1
0x18002990a  movdqu  xmmword ptr [rax+40h], xmm0
0x18002990f  mov     dword ptr [rdi], 5
0x180029915  mov     [rbx], rax
0x180029918  xor     eax, eax
0x18002991a  mov     rbx, [rsp+28h+arg_0]
0x18002991f  add     rsp, 20h
0x180029923  pop     rdi
0x180029924  retn
```
