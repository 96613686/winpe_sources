# USBSTOR_EnableIdlePower

- ea: `0x14000b420`
- end: `0x14000b499`
- name: `USBSTOR_EnableIdlePower`
- size: `121`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400226d0`

## callees

- `0x14000b420`
- `0x14000b4a0`

## import_xrefs

- `ntoskrnl!PoFxSetDeviceIdleTimeout` at `0x14000b464`
- `ntoskrnl!PoFxSetDeviceIdleTimeout` at `0x14000b464`
- `ntoskrnl!IofCompleteRequest` at `0x14000b47f`
- `ntoskrnl!IofCompleteRequest` at `0x14000b47f`

## pseudocode

```c
__int64 __fastcall USBSTOR_EnableIdlePower(__int64 a1, IRP *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  unsigned __int64 v7; // rdx

  if ( (unsigned __int8)USBSTOR_IsSelectiveSuspendEnabled(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 16LL) + 64LL)) )
  {
    v5 = 0;
    v6 = *(_QWORD *)(v4 + 1968);
    v7 = *(unsigned int *)(*(_QWORD *)(v3 + 24) + 12LL);
    if ( v7 < 0x1388 )
      v7 = 5000;
    PoFxSetDeviceIdleTimeout(v6, 10000 * v7);
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
0x14000b420  mov     [rsp+arg_0], rbx
0x14000b425  push    rdi
0x14000b426  sub     rsp, 20h
0x14000b42a  mov     rax, [rcx+40h]
0x14000b42e  mov     rdi, rdx
0x14000b431  mov     rcx, [rax+10h]
0x14000b435  mov     rcx, [rcx+40h]
0x14000b439  call    USBSTOR_IsSelectiveSuspendEnabled
0x14000b43e  test    al, al
0x14000b440  jz      short loc_14000B472
0x14000b442  mov     rax, [rdx+18h]
0x14000b446  xor     ebx, ebx
0x14000b448  mov     rcx, [rcx+7B0h]
0x14000b44f  mov     edx, [rax+0Ch]
0x14000b452  mov     eax, 1388h
0x14000b457  cmp     rdx, rax
0x14000b45a  cmovb   edx, eax
0x14000b45d  imul    rdx, 2710h
0x14000b464  call    cs:__imp_PoFxSetDeviceIdleTimeout
0x14000b46b  nop     dword ptr [rax+rax+00h]
0x14000b470  jmp     short loc_14000B477
0x14000b472  mov     ebx, 0C00000BBh
0x14000b477  xor     edx, edx; PriorityBoost
0x14000b479  mov     [rdi+30h], ebx
0x14000b47c  mov     rcx, rdi; Irp
0x14000b47f  call    cs:__imp_IofCompleteRequest
0x14000b486  nop     dword ptr [rax+rax+00h]
0x14000b48b  mov     eax, ebx
0x14000b48d  mov     rbx, [rsp+28h+arg_0]
0x14000b492  add     rsp, 20h
0x14000b496  pop     rdi
0x14000b497  retn
```
