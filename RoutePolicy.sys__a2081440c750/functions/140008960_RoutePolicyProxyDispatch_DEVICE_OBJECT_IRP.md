# RoutePolicyProxyDispatch(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140008960`
- end: `0x1400089bf`
- name: `?RoutePolicyProxyDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `95`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1400081ec`
- `0x140008960`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400089a5`
- `ntoskrnl!IofCompleteRequest` at `0x1400089a5`

## pseudocode

```c
__int64 __fastcall RoutePolicyProxyDispatch(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  unsigned int v3; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx

  v3 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( !CurrentStackLocation->MajorFunction
    || CurrentStackLocation->MajorFunction == 2
    || (unsigned int)CurrentStackLocation->MajorFunction - 14 > 1
    || (v3 = RoutePolicyProxy::DeviceControl(a2), v3 != 259) )
  {
    a2->IoStatus.Status = v3;
    IofCompleteRequest(a2, 2);
  }
  return v3;
}

```

## disassembly

```asm
0x140008960  mov     [rsp+arg_0], rbx
0x140008965  push    rdi
0x140008966  sub     rsp, 20h
0x14000896a  mov     rdi, rdx
0x14000896d  xor     ebx, ebx
0x14000896f  mov     rdx, [rdx+0B8h]
0x140008976  movzx   ecx, byte ptr [rdx]
0x140008979  test    ecx, ecx
0x14000897b  jz      short loc_14000899D
0x14000897d  sub     ecx, 2
0x140008980  jz      short loc_14000899D
0x140008982  sub     ecx, 0Ch
0x140008985  jz      short loc_14000898C
0x140008987  sub     ecx, 1
0x14000898a  jnz     short loc_14000899D
0x14000898c  mov     rcx, rdi
0x14000898f  call    RoutePolicyProxy__DeviceControl
0x140008994  mov     ebx, eax
0x140008996  cmp     eax, 103h
0x14000899b  jz      short loc_1400089B1
0x14000899d  mov     dl, 2; PriorityBoost
0x14000899f  mov     [rdi+30h], ebx
0x1400089a2  mov     rcx, rdi; Irp
0x1400089a5  call    cs:__imp_IofCompleteRequest
0x1400089ac  nop     dword ptr [rax+rax+00h]
0x1400089b1  mov     eax, ebx
0x1400089b3  mov     rbx, [rsp+28h+arg_0]
0x1400089b8  add     rsp, 20h
0x1400089bc  pop     rdi
0x1400089bd  retn
```
