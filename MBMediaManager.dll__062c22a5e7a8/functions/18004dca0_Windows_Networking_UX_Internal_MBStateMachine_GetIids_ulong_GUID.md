# Windows::Networking::UX::Internal::MBStateMachine::GetIids(ulong *,_GUID * *)

- ea: `0x18004dca0`
- end: `0x18004dd0d`
- name: `?GetIids@MBStateMachine@Internal@UX@Networking@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::MBStateMachine *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004dd20`

## callees

- `0x18004dca0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004dcc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004dcc2`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::MBStateMachine::GetIids(
        Windows::Networking::UX::Internal::MBStateMachine *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  struct _GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (struct _GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_3448b9cc_8e85_45eb_9bc8_b4d071caeca1;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_d74ebc89_72ab_4728_8291_3aae26edaa05;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18004dca0  mov     [rsp+arg_0], rbx
0x18004dca5  push    rdi
0x18004dca6  sub     rsp, 20h
0x18004dcaa  mov     qword ptr [r8], 0
0x18004dcb1  mov     ecx, 30h ; '0'; cb
0x18004dcb6  mov     dword ptr [rdx], 0
0x18004dcbc  mov     rbx, r8
0x18004dcbf  mov     rdi, rdx
0x18004dcc2  call    cs:__imp_CoTaskMemAlloc
0x18004dcc8  test    rax, rax
0x18004dccb  jnz     short loc_18004DCD4
0x18004dccd  mov     eax, 8007000Eh
0x18004dcd2  jmp     short loc_18004DD02
0x18004dcd4  movups  xmm0, xmmword ptr cs:_GUID_3448b9cc_8e85_45eb_9bc8_b4d071caeca1.Data1
0x18004dcdb  movdqu  xmmword ptr [rax], xmm0
0x18004dcdf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18004dce6  movdqu  xmmword ptr [rax+10h], xmm1
0x18004dceb  movups  xmm0, xmmword ptr cs:_GUID_d74ebc89_72ab_4728_8291_3aae26edaa05.Data1
0x18004dcf2  movdqu  xmmword ptr [rax+20h], xmm0
0x18004dcf7  mov     dword ptr [rdi], 3
0x18004dcfd  mov     [rbx], rax
0x18004dd00  xor     eax, eax
0x18004dd02  mov     rbx, [rsp+28h+arg_0]
0x18004dd07  add     rsp, 20h
0x18004dd0b  pop     rdi
0x18004dd0c  retn
```
