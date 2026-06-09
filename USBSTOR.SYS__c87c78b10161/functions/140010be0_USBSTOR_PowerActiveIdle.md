# USBSTOR_PowerActiveIdle

- ea: `0x140010be0`
- end: `0x140010c57`
- name: `USBSTOR_PowerActiveIdle`
- size: `119`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400226d0`

## callees

- `0x140010be0`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x140010c22`
- `ntoskrnl!PoFxIdleComponent` at `0x140010c22`
- `ntoskrnl!IofCompleteRequest` at `0x140010c3d`
- `ntoskrnl!IofCompleteRequest` at `0x140010c3d`
- `ntoskrnl!PoFxActivateComponent` at `0x140010c11`
- `ntoskrnl!PoFxActivateComponent` at `0x140010c11`

## pseudocode

```c
__int64 __fastcall USBSTOR_PowerActiveIdle(__int64 a1, IRP *a2, char a3)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx

  v4 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 16LL) + 64LL) + 1968LL);
  if ( v4 )
  {
    v5 = 0;
    if ( a3 )
      PoFxActivateComponent(v4, 0, 0);
    else
      PoFxIdleComponent(v4, 0, 0);
  }
  else
  {
    v5 = -1073741637;
  }
  a2->IoStatus.Status = v5;
  IofCompleteRequest(a2, 0);
  return v5;
}

```

## disassembly

```asm
0x140010be0  mov     [rsp+arg_0], rbx
0x140010be5  push    rdi
0x140010be6  sub     rsp, 20h
0x140010bea  mov     rax, [rcx+40h]
0x140010bee  mov     rdi, rdx
0x140010bf1  mov     rcx, [rax+10h]
0x140010bf5  mov     rax, [rcx+40h]
0x140010bf9  mov     rcx, [rax+7B0h]
0x140010c00  test    rcx, rcx
0x140010c03  jz      short loc_140010C30
0x140010c05  xor     ebx, ebx
0x140010c07  xor     edx, edx
0x140010c09  test    r8b, r8b
0x140010c0c  jz      short loc_140010C1F
0x140010c0e  xor     r8d, r8d
0x140010c11  call    cs:__imp_PoFxActivateComponent
0x140010c18  nop     dword ptr [rax+rax+00h]
0x140010c1d  jmp     short loc_140010C35
0x140010c1f  xor     r8d, r8d
0x140010c22  call    cs:__imp_PoFxIdleComponent
0x140010c29  nop     dword ptr [rax+rax+00h]
0x140010c2e  jmp     short loc_140010C35
0x140010c30  mov     ebx, 0C00000BBh
0x140010c35  xor     edx, edx; PriorityBoost
0x140010c37  mov     [rdi+30h], ebx
0x140010c3a  mov     rcx, rdi; Irp
0x140010c3d  call    cs:__imp_IofCompleteRequest
0x140010c44  nop     dword ptr [rax+rax+00h]
0x140010c49  mov     eax, ebx
0x140010c4b  mov     rbx, [rsp+28h+arg_0]
0x140010c50  add     rsp, 20h
0x140010c54  pop     rdi
0x140010c55  retn
```
