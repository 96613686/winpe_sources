# AipCreateDispatch

- ea: `0x140030f30`
- end: `0x140030f8d`
- name: `AipCreateDispatch`
- size: `93`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400016a8`
- `0x140030f30`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140030f61`
- `ntoskrnl!IofCompleteRequest` at `0x140030f61`

## pseudocode

```c
__int64 __fastcall AipCreateDispatch(__int64 a1, IRP *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x140030f30  push    rbx
0x140030f32  sub     rsp, 20h
0x140030f36  mov     rbx, rdx
0x140030f39  mov     rcx, cs:WPP_GLOBAL_Control
0x140030f40  lea     rax, WPP_GLOBAL_Control
0x140030f47  cmp     rcx, rax
0x140030f4a  jz      short loc_140030F53
0x140030f4c  mov     eax, [rcx+2Ch]
0x140030f4f  test    al, 2
0x140030f51  jnz     short loc_140030F76
0x140030f53  xor     eax, eax
0x140030f55  xor     edx, edx; PriorityBoost
0x140030f57  mov     rcx, rbx; Irp
0x140030f5a  mov     [rbx+38h], rax
0x140030f5e  mov     [rbx+30h], eax
0x140030f61  call    cs:__imp_IofCompleteRequest
0x140030f68  nop     dword ptr [rax+rax+00h]
0x140030f6d  xor     eax, eax
0x140030f6f  add     rsp, 20h
0x140030f73  pop     rbx
0x140030f74  retn
0x140030f76  mov     rcx, [rcx+18h]
0x140030f7a  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x140030f81  mov     edx, 11h
0x140030f86  call    WPP_SF_
0x140030f8b  jmp     short loc_140030F53
```
