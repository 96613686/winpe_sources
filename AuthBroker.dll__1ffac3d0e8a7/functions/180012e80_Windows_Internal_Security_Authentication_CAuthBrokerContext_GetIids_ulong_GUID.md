# Windows::Internal::Security::Authentication::CAuthBrokerContext::GetIids(ulong *,_GUID * *)

- ea: `0x180012e80`
- end: `0x180012eed`
- name: `?GetIids@CAuthBrokerContext@Authentication@Security@Internal@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::CAuthBrokerContext *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012e80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012ea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012ea2`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::CAuthBrokerContext::GetIids(
        Windows::Internal::Security::Authentication::CAuthBrokerContext *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_4c5f12ce_190e_4440_be55_c08745612dd0;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_aa97a7a3_b26e_4e88_9453_409af067634e;
  *iidCount = 3;
  *iids = v5;
  return 0;
}

```

## disassembly

```asm
0x180012e80  mov     [rsp+arg_0], rbx
0x180012e85  push    rdi
0x180012e86  sub     rsp, 20h
0x180012e8a  mov     qword ptr [iids], 0
0x180012e91  mov     ecx, 30h ; '0'; cb
0x180012e96  mov     dword ptr [iidCount], 0
0x180012e9c  mov     rbx, iids
0x180012e9f  mov     rdi, iidCount
0x180012ea2  call    cs:__imp_CoTaskMemAlloc
0x180012ea8  test    rax, rax
0x180012eab  jnz     short loc_180012EB4
0x180012ead  mov     eax, 8007000Eh
0x180012eb2  jmp     short loc_180012EE2
0x180012eb4  movups  xmm0, xmmword ptr cs:_GUID_4c5f12ce_190e_4440_be55_c08745612dd0.Data1
0x180012ebb  movdqu  xmmword ptr [rax], xmm0
0x180012ebf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180012ec6  movdqu  xmmword ptr [rax+10h], xmm1
0x180012ecb  movups  xmm0, xmmword ptr cs:_GUID_aa97a7a3_b26e_4e88_9453_409af067634e.Data1
0x180012ed2  movdqu  xmmword ptr [rax+20h], xmm0
0x180012ed7  mov     dword ptr [rdi], 3
0x180012edd  mov     [rbx], rax
0x180012ee0  xor     eax, eax
0x180012ee2  mov     rbx, [rsp+28h+arg_0]
0x180012ee7  add     rsp, 20h
0x180012eeb  pop     rdi
0x180012eec  retn
```
