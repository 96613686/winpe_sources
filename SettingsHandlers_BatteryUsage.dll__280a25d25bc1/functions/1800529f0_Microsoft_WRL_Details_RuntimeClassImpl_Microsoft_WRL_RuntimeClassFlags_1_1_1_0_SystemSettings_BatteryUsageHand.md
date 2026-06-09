# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::BatteryUsageHandlers::IExecutableInfo>::GetIids(ulong *,_GUID * *)

- ea: `0x1800529f0`
- end: `0x180052a51`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIExecutableInfo@BatteryUsageHandlers@SystemSettings@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800529f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052a12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052a12`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::BatteryUsageHandlers::IExecutableInfo>::GetIids(
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
  *v5 = GUID_fa62b361_fdfb_43c9_a80a_ce00dfa6e43d;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800529f0  mov     [rsp+arg_0], rbx
0x1800529f5  push    rdi
0x1800529f6  sub     rsp, 20h
0x1800529fa  mov     qword ptr [r8], 0
0x180052a01  mov     ecx, 20h ; ' '; cb
0x180052a06  mov     dword ptr [rdx], 0
0x180052a0c  mov     rbx, r8
0x180052a0f  mov     rdi, rdx
0x180052a12  call    cs:__imp_CoTaskMemAlloc
0x180052a18  test    rax, rax
0x180052a1b  jnz     short loc_180052A24
0x180052a1d  mov     eax, 8007000Eh
0x180052a22  jmp     short loc_180052A46
0x180052a24  movups  xmm0, xmmword ptr cs:_GUID_fa62b361_fdfb_43c9_a80a_ce00dfa6e43d.Data1
0x180052a2b  movdqu  xmmword ptr [rax], xmm0
0x180052a2f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180052a36  movdqu  xmmword ptr [rax+10h], xmm1
0x180052a3b  mov     dword ptr [rdi], 2
0x180052a41  mov     [rbx], rax
0x180052a44  xor     eax, eax
0x180052a46  mov     rbx, [rsp+28h+arg_0]
0x180052a4b  add     rsp, 20h
0x180052a4f  pop     rdi
0x180052a50  retn
```
