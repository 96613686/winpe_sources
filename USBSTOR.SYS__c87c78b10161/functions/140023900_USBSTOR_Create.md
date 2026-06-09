# USBSTOR_Create

- ea: `0x140023900`
- end: `0x1400239d9`
- name: `USBSTOR_Create`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003630`
- `0x140010664`
- `0x140023900`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140023954`
- `ntoskrnl!IofCompleteRequest` at `0x140023954`

## pseudocode

```c
__int64 __fastcall USBSTOR_Create(__int64 a1, IRP *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_83961903f8913993eee34094953b83c3_Traceguids);
  }
  USBSTOR_LogEntry(1095062083, a1, a2, 0);
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_83961903f8913993eee34094953b83c3_Traceguids);
  }
  USBSTOR_LogEntry(1634038371, 0, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140023900  mov     [rsp+arg_0], rbx
0x140023905  mov     [rsp+arg_8], rsi
0x14002390a  push    rdi
0x14002390b  sub     rsp, 20h
0x14002390f  mov     rbx, rdx
0x140023912  mov     rdi, rcx
0x140023915  mov     rcx, cs:WPP_GLOBAL_Control
0x14002391c  lea     rsi, WPP_GLOBAL_Control
0x140023923  cmp     rcx, rsi
0x140023926  jz      short loc_140023933
0x140023928  mov     eax, [rcx+2Ch]
0x14002392b  test    al, 1
0x14002392d  jnz     loc_1400239B5
0x140023933  xor     r9d, r9d
0x140023936  mov     r8, rbx
0x140023939  mov     rdx, rdi
0x14002393c  mov     ecx, 41455243h
0x140023941  call    USBSTOR_LogEntry
0x140023946  xor     eax, eax
0x140023948  xor     edx, edx; PriorityBoost
0x14002394a  mov     rcx, rbx; Irp
0x14002394d  mov     [rbx+30h], eax
0x140023950  mov     [rbx+38h], rax
0x140023954  call    cs:__imp_IofCompleteRequest
0x14002395b  nop     dword ptr [rax+rax+00h]
0x140023960  mov     rcx, cs:WPP_GLOBAL_Control
0x140023967  cmp     rcx, rsi
0x14002396a  jnz     short loc_140023991
0x14002396c  xor     r9d, r9d
0x14002396f  xor     r8d, r8d
0x140023972  xor     edx, edx
0x140023974  mov     ecx, 61657263h
0x140023979  call    USBSTOR_LogEntry
0x14002397e  mov     rbx, [rsp+28h+arg_0]
0x140023983  xor     eax, eax
0x140023985  mov     rsi, [rsp+28h+arg_8]
0x14002398a  add     rsp, 20h
0x14002398e  pop     rdi
0x14002398f  retn
0x140023991  mov     eax, [rcx+2Ch]
0x140023994  test    al, 1
0x140023996  jz      short loc_14002396C
0x140023998  cmp     byte ptr [rcx+29h], 4
0x14002399c  jb      short loc_14002396C
0x14002399e  mov     rcx, [rcx+18h]
0x1400239a2  lea     r8, WPP_83961903f8913993eee34094953b83c3_Traceguids
0x1400239a9  mov     edx, 0Bh
0x1400239ae  call    WPP_SF_
0x1400239b3  jmp     short loc_14002396C
0x1400239b5  cmp     byte ptr [rcx+29h], 5
0x1400239b9  jb      loc_140023933
0x1400239bf  mov     rcx, [rcx+18h]
0x1400239c3  lea     r8, WPP_83961903f8913993eee34094953b83c3_Traceguids
0x1400239ca  mov     edx, 0Ah
0x1400239cf  call    WPP_SF_
0x1400239d4  jmp     loc_140023933
```
