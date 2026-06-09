# AipCloseDispatch

- ea: `0x140033d50`
- end: `0x140033dad`
- name: `AipCloseDispatch`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400016a8`
- `0x140033d50`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140033d7a`
- `ntoskrnl!IofCompleteRequest` at `0x140033d7a`

## pseudocode

```c
__int64 __fastcall AipCloseDispatch(__int64 a1, IRP *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x140033d50  push    rbx
0x140033d52  sub     rsp, 20h
0x140033d56  mov     rbx, rdx
0x140033d59  mov     rcx, cs:WPP_GLOBAL_Control
0x140033d60  lea     rax, WPP_GLOBAL_Control
0x140033d67  cmp     rcx, rax
0x140033d6a  jnz     short loc_140033D8F
0x140033d6c  xor     eax, eax
0x140033d6e  xor     edx, edx; PriorityBoost
0x140033d70  mov     rcx, rbx; Irp
0x140033d73  mov     [rbx+38h], rax
0x140033d77  mov     [rbx+30h], eax
0x140033d7a  call    cs:__imp_IofCompleteRequest
0x140033d81  nop     dword ptr [rax+rax+00h]
0x140033d86  xor     eax, eax
0x140033d88  add     rsp, 20h
0x140033d8c  pop     rbx
0x140033d8d  retn
0x140033d8f  mov     eax, [rcx+2Ch]
0x140033d92  test    al, 2
0x140033d94  jz      short loc_140033D6C
0x140033d96  mov     rcx, [rcx+18h]
0x140033d9a  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x140033da1  mov     edx, 12h
0x140033da6  call    WPP_SF_
0x140033dab  jmp     short loc_140033D6C
```
