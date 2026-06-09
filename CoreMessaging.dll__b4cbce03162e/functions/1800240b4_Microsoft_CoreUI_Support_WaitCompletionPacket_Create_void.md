# Microsoft::CoreUI::Support::WaitCompletionPacket::Create(void)

- ea: `0x1800240b4`
- end: `0x1800240fc`
- name: `?Create@WaitCompletionPacket@Support@CoreUI@Microsoft@@SA?AU1234@XZ`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180023ed0`

## callees

- `0x1800240b4`
- `0x18008f3cc`

## import_xrefs

- `ntdll!NtCreateWaitCompletionPacket` at `0x1800240d9`
- `ntdll!NtCreateWaitCompletionPacket` at `0x1800240d9`

## pseudocode

```c
_QWORD *__fastcall Microsoft::CoreUI::Support::WaitCompletionPacket::Create(_QWORD *a1)
{
  int v2; // eax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = 0;
  v2 = NtCreateWaitCompletionPacket(&v4, 1);
  if ( v2 < 0 )
    Cn::FailFast::ForNtStatus(v2);
  *a1 = v4;
  return a1;
}

```

## disassembly

```asm
0x1800240b4  push    rbx
0x1800240b6  sub     rsp, 20h
0x1800240ba  xor     r8d, r8d
0x1800240bd  mov     qword ptr [rcx], 0
0x1800240c4  mov     rbx, rcx
0x1800240c7  mov     [rsp+28h+arg_0], 0
0x1800240d0  lea     rcx, [rsp+28h+arg_0]
0x1800240d5  lea     edx, [r8+1]
0x1800240d9  call    cs:__imp_NtCreateWaitCompletionPacket
0x1800240df  test    eax, eax
0x1800240e1  js      short loc_1800240F4
0x1800240e3  mov     rax, [rsp+28h+arg_0]
0x1800240e8  mov     [rbx], rax
0x1800240eb  mov     rax, rbx
0x1800240ee  add     rsp, 20h
0x1800240f2  pop     rbx
0x1800240f3  retn
0x1800240f4  mov     ecx, eax; int
0x1800240f6  call    ?ForNtStatus@FailFast@Cn@@SAXH@Z; Cn::FailFast::ForNtStatus(int)
```
