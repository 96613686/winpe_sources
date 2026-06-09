# ConfigurationManagerAdapter::GetIids(ulong *,_GUID * *)

- ea: `0x18000be50`
- end: `0x18000beb1`
- name: `?GetIids@ConfigurationManagerAdapter@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(ConfigurationManagerAdapter *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000be50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000be72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000be72`

## pseudocode

```c
__int64 __fastcall ConfigurationManagerAdapter::GetIids(
        ConfigurationManagerAdapter *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_7891c740_e2e2_4dd1_9ef8_fe0e9d4a6747;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000be50  mov     [rsp+arg_0], rbx
0x18000be55  push    rdi
0x18000be56  sub     rsp, 20h
0x18000be5a  mov     qword ptr [r8], 0
0x18000be61  mov     ecx, 20h ; ' '; cb
0x18000be66  mov     dword ptr [rdx], 0
0x18000be6c  mov     rbx, r8
0x18000be6f  mov     rdi, rdx
0x18000be72  call    cs:__imp_CoTaskMemAlloc
0x18000be78  test    rax, rax
0x18000be7b  jnz     short loc_18000BE84
0x18000be7d  mov     eax, 8007000Eh
0x18000be82  jmp     short loc_18000BEA6
0x18000be84  movups  xmm0, xmmword ptr cs:_GUID_7891c740_e2e2_4dd1_9ef8_fe0e9d4a6747.Data1
0x18000be8b  movdqu  xmmword ptr [rax], xmm0
0x18000be8f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18000be96  movdqu  xmmword ptr [rax+10h], xmm1
0x18000be9b  mov     dword ptr [rdi], 2
0x18000bea1  mov     [rbx], rax
0x18000bea4  xor     eax, eax
0x18000bea6  mov     rbx, [rsp+28h+arg_0]
0x18000beab  add     rsp, 20h
0x18000beaf  pop     rdi
0x18000beb0  retn
```
