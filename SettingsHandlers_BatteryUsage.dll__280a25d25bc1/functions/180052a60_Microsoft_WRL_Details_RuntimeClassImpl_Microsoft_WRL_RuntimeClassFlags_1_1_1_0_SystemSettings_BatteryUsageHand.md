# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::BatteryUsageHandlers::IPackageInfo>::GetIids(ulong *,_GUID * *)

- ea: `0x180052a60`
- end: `0x180052ac1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180052a60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052a82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052a82`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::BatteryUsageHandlers::IPackageInfo>::GetIids(
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
  *v5 = GUID_4c2e66c9_5aa2_4510_9616_1513dae7edab;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180052a60  mov     [rsp+arg_0], rbx
0x180052a65  push    rdi
0x180052a66  sub     rsp, 20h
0x180052a6a  mov     qword ptr [r8], 0
0x180052a71  mov     ecx, 20h ; ' '; cb
0x180052a76  mov     dword ptr [rdx], 0
0x180052a7c  mov     rbx, r8
0x180052a7f  mov     rdi, rdx
0x180052a82  call    cs:__imp_CoTaskMemAlloc
0x180052a88  test    rax, rax
0x180052a8b  jnz     short loc_180052A94
0x180052a8d  mov     eax, 8007000Eh
0x180052a92  jmp     short loc_180052AB6
0x180052a94  movups  xmm0, xmmword ptr cs:_GUID_4c2e66c9_5aa2_4510_9616_1513dae7edab.Data1
0x180052a9b  movdqu  xmmword ptr [rax], xmm0
0x180052a9f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180052aa6  movdqu  xmmword ptr [rax+10h], xmm1
0x180052aab  mov     dword ptr [rdi], 2
0x180052ab1  mov     [rbx], rax
0x180052ab4  xor     eax, eax
0x180052ab6  mov     rbx, [rsp+28h+arg_0]
0x180052abb  add     rsp, 20h
0x180052abf  pop     rdi
0x180052ac0  retn
```
