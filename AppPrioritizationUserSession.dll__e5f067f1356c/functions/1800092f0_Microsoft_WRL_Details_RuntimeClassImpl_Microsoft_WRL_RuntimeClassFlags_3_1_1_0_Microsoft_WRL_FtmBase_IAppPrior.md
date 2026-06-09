# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::GetIids(ulong *,_GUID * *)

- ea: `0x1800092f0`
- end: `0x180009369`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIAppPrioritizationUserSessionInternal@@UIAppPrioritizationUserSession@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009370`
- `0x180009380`
- `0x180009390`

## callees

- `0x1800092f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009312`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009312`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::GetIids(
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
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_ca9ef94a_1e31_4de6_87ce_74c22fab5a86;
  v5[3] = GUID_88ebe726_dd14_4dc4_9d3d_172cf4473404;
  *a2 = 4;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800092f0  mov     [rsp+arg_0], rbx
0x1800092f5  push    rdi
0x1800092f6  sub     rsp, 20h
0x1800092fa  mov     qword ptr [r8], 0
0x180009301  mov     ecx, 40h ; '@'; cb
0x180009306  mov     dword ptr [rdx], 0
0x18000930c  mov     rbx, r8
0x18000930f  mov     rdi, rdx
0x180009312  call    cs:__imp_CoTaskMemAlloc
0x180009318  test    rax, rax
0x18000931b  jnz     short loc_180009324
0x18000931d  mov     eax, 8007000Eh
0x180009322  jmp     short loc_18000935E
0x180009324  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18000932b  movdqu  xmmword ptr [rax], xmm0
0x18000932f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180009336  movdqu  xmmword ptr [rax+10h], xmm1
0x18000933b  movups  xmm0, xmmword ptr cs:_GUID_ca9ef94a_1e31_4de6_87ce_74c22fab5a86.Data1
0x180009342  movdqu  xmmword ptr [rax+20h], xmm0
0x180009347  movups  xmm1, xmmword ptr cs:_GUID_88ebe726_dd14_4dc4_9d3d_172cf4473404.Data1
0x18000934e  movdqu  xmmword ptr [rax+30h], xmm1
0x180009353  mov     dword ptr [rdi], 4
0x180009359  mov     [rbx], rax
0x18000935c  xor     eax, eax
0x18000935e  mov     rbx, [rsp+28h+arg_0]
0x180009363  add     rsp, 20h
0x180009367  pop     rdi
0x180009368  retn
```
