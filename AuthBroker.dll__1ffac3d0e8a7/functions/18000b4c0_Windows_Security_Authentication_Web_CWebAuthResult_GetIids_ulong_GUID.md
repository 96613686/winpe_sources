# Windows::Security::Authentication::Web::CWebAuthResult::GetIids(ulong *,_GUID * *)

- ea: `0x18000b4c0`
- end: `0x18000b52d`
- name: `?GetIids@CWebAuthResult@Web@Authentication@Security@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Security::Authentication::Web::CWebAuthResult *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b540`

## callees

- `0x18000b4c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b4e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b4e2`

## pseudocode

```c
__int64 __fastcall Windows::Security::Authentication::Web::CWebAuthResult::GetIids(
        Windows::Security::Authentication::Web::CWebAuthResult *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_64002b4b_ede9_470a_a5cd_0323faf6e262;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  *iidCount = 3;
  *iids = v5;
  return 0;
}

```

## disassembly

```asm
0x18000b4c0  mov     [rsp+arg_0], rbx
0x18000b4c5  push    rdi
0x18000b4c6  sub     rsp, 20h
0x18000b4ca  mov     qword ptr [iids], 0
0x18000b4d1  mov     ecx, 30h ; '0'; cb
0x18000b4d6  mov     dword ptr [iidCount], 0
0x18000b4dc  mov     rbx, iids
0x18000b4df  mov     rdi, iidCount
0x18000b4e2  call    cs:__imp_CoTaskMemAlloc
0x18000b4e8  test    rax, rax
0x18000b4eb  jnz     short loc_18000B4F4
0x18000b4ed  mov     eax, 8007000Eh
0x18000b4f2  jmp     short loc_18000B522
0x18000b4f4  movups  xmm0, xmmword ptr cs:_GUID_64002b4b_ede9_470a_a5cd_0323faf6e262.Data1
0x18000b4fb  movdqu  xmmword ptr [rax], xmm0
0x18000b4ff  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18000b506  movdqu  xmmword ptr [rax+10h], xmm1
0x18000b50b  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18000b512  movdqu  xmmword ptr [rax+20h], xmm0
0x18000b517  mov     dword ptr [rdi], 3
0x18000b51d  mov     [rbx], rax
0x18000b520  xor     eax, eax
0x18000b522  mov     rbx, [rsp+28h+arg_0]
0x18000b527  add     rsp, 20h
0x18000b52b  pop     rdi
0x18000b52c  retn
```
