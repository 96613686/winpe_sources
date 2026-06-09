# AppLaunchCapabilityAccessServer::GetIids(ulong *,_GUID * *)

- ea: `0x18001c090`
- end: `0x18001c0f1`
- name: `?GetIids@AppLaunchCapabilityAccessServer@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(AppLaunchCapabilityAccessServer *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001c090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c0b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c0b2`

## pseudocode

```c
__int64 __fastcall AppLaunchCapabilityAccessServer::GetIids(
        AppLaunchCapabilityAccessServer *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_e4166cd3_bf91_438a_9f23_a62d3be918cc;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001c090  mov     [rsp+arg_0], rbx
0x18001c095  push    rdi
0x18001c096  sub     rsp, 20h
0x18001c09a  mov     qword ptr [r8], 0
0x18001c0a1  mov     ecx, 20h ; ' '; cb
0x18001c0a6  mov     dword ptr [rdx], 0
0x18001c0ac  mov     rbx, r8
0x18001c0af  mov     rdi, rdx
0x18001c0b2  call    cs:__imp_CoTaskMemAlloc
0x18001c0b8  test    rax, rax
0x18001c0bb  jnz     short loc_18001C0C4
0x18001c0bd  mov     eax, 8007000Eh
0x18001c0c2  jmp     short loc_18001C0E6
0x18001c0c4  movups  xmm0, xmmword ptr cs:_GUID_e4166cd3_bf91_438a_9f23_a62d3be918cc.Data1
0x18001c0cb  movdqu  xmmword ptr [rax], xmm0
0x18001c0cf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001c0d6  movdqu  xmmword ptr [rax+10h], xmm1
0x18001c0db  mov     dword ptr [rdi], 2
0x18001c0e1  mov     [rbx], rax
0x18001c0e4  xor     eax, eax
0x18001c0e6  mov     rbx, [rsp+28h+arg_0]
0x18001c0eb  add     rsp, 20h
0x18001c0ef  pop     rdi
0x18001c0f0  retn
```
