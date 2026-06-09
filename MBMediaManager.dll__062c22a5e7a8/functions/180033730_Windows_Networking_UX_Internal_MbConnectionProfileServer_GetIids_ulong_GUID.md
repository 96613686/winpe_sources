# Windows::Networking::UX::Internal::MbConnectionProfileServer::GetIids(ulong *,_GUID * *)

- ea: `0x180033730`
- end: `0x180033791`
- name: `?GetIids@MbConnectionProfileServer@Internal@UX@Networking@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::MbConnectionProfileServer *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180033730`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033752`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033752`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::MbConnectionProfileServer::GetIids(
        Windows::Networking::UX::Internal::MbConnectionProfileServer *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_b1b90ba5_86e9_5ff6_94da_e301912a6510;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180033730  mov     [rsp+arg_0], rbx
0x180033735  push    rdi
0x180033736  sub     rsp, 20h
0x18003373a  mov     qword ptr [r8], 0
0x180033741  mov     ecx, 20h ; ' '; cb
0x180033746  mov     dword ptr [rdx], 0
0x18003374c  mov     rbx, r8
0x18003374f  mov     rdi, rdx
0x180033752  call    cs:__imp_CoTaskMemAlloc
0x180033758  test    rax, rax
0x18003375b  jnz     short loc_180033764
0x18003375d  mov     eax, 8007000Eh
0x180033762  jmp     short loc_180033786
0x180033764  movups  xmm0, xmmword ptr cs:_GUID_b1b90ba5_86e9_5ff6_94da_e301912a6510.Data1
0x18003376b  movdqu  xmmword ptr [rax], xmm0
0x18003376f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180033776  movdqu  xmmword ptr [rax+10h], xmm1
0x18003377b  mov     dword ptr [rdi], 2
0x180033781  mov     [rbx], rax
0x180033784  xor     eax, eax
0x180033786  mov     rbx, [rsp+28h+arg_0]
0x18003378b  add     rsp, 20h
0x18003378f  pop     rdi
0x180033790  retn
```
