# AipCleanupDispatch

- ea: `0x1400328e0`
- end: `0x140032979`
- name: `AipCleanupDispatch`
- size: `153`
- prototype: `__int64 __fastcall(PVOID, IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400016a8`
- `0x140025f90`
- `0x1400328e0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14003291f`
- `ntoskrnl!IofCompleteRequest` at `0x14003291f`

## pseudocode

```c
__int64 __fastcall AipCleanupDispatch(PVOID a1, IRP *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
  if ( WPP_MAIN_CB.DeviceExtension == a1
    && (int)AiServiceStopped(a2->Tail.Overlay.CurrentStackLocation->FileObject) >= 0 )
  {
    WPP_MAIN_CB.Dpc.SystemArgument2 = 0;
  }
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x1400328e0  mov     [rsp+arg_0], rbx
0x1400328e5  mov     [rsp+arg_8], rsi
0x1400328ea  push    rdi
0x1400328eb  sub     rsp, 20h
0x1400328ef  mov     rbx, rdx
0x1400328f2  mov     rdi, rcx
0x1400328f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400328fc  lea     rax, WPP_GLOBAL_Control
0x140032903  cmp     rcx, rax
0x140032906  jnz     short loc_14003293E
0x140032908  xor     esi, esi
0x14003290a  cmp     cs:WPP_MAIN_CB.DeviceExtension, rdi
0x140032911  jz      short loc_14003295C
0x140032913  xor     edx, edx; PriorityBoost
0x140032915  mov     [rbx+38h], rsi
0x140032919  mov     rcx, rbx; Irp
0x14003291c  mov     [rbx+30h], esi
0x14003291f  call    cs:__imp_IofCompleteRequest
0x140032926  nop     dword ptr [rax+rax+00h]
0x14003292b  mov     rbx, [rsp+28h+arg_0]
0x140032930  xor     eax, eax
0x140032932  mov     rsi, [rsp+28h+arg_8]
0x140032937  add     rsp, 20h
0x14003293b  pop     rdi
0x14003293c  retn
0x14003293e  mov     eax, [rcx+2Ch]
0x140032941  test    al, 2
0x140032943  jz      short loc_140032908
0x140032945  mov     rcx, [rcx+18h]
0x140032949  lea     r8, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x140032950  mov     edx, 13h
0x140032955  call    WPP_SF_
0x14003295a  jmp     short loc_140032908
0x14003295c  mov     rcx, [rbx+0B8h]
0x140032963  mov     rcx, [rcx+30h]
0x140032967  call    AiServiceStopped
0x14003296c  test    eax, eax
0x14003296e  js      short loc_140032913
0x140032970  mov     cs:WPP_MAIN_CB.Dpc.SystemArgument2, rsi
0x140032977  jmp     short loc_140032913
```
