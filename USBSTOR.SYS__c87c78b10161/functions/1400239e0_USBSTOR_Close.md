# USBSTOR_Close

- ea: `0x1400239e0`
- end: `0x140023ab1`
- name: `USBSTOR_Close`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003630`
- `0x140010664`
- `0x1400239e0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140023a30`
- `ntoskrnl!IofCompleteRequest` at `0x140023a30`

## pseudocode

```c
__int64 __fastcall USBSTOR_Close(__int64 a1, IRP *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_83961903f8913993eee34094953b83c3_Traceguids);
  }
  USBSTOR_LogEntry(1397705795, a1, a2, 0);
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_83961903f8913993eee34094953b83c3_Traceguids);
  }
  USBSTOR_LogEntry(1936682083, 0, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x1400239e0  mov     [rsp+arg_0], rbx
0x1400239e5  mov     [rsp+arg_8], rsi
0x1400239ea  push    rdi
0x1400239eb  sub     rsp, 20h
0x1400239ef  mov     rbx, rdx
0x1400239f2  mov     rdi, rcx
0x1400239f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400239fc  lea     rsi, WPP_GLOBAL_Control
0x140023a03  cmp     rcx, rsi
0x140023a06  jz      short loc_140023A0F
0x140023a08  mov     eax, [rcx+2Ch]
0x140023a0b  test    al, 1
0x140023a0d  jnz     short loc_140023A74
0x140023a0f  xor     r9d, r9d
0x140023a12  mov     r8, rbx
0x140023a15  mov     rdx, rdi
0x140023a18  mov     ecx, 534F4C43h
0x140023a1d  call    USBSTOR_LogEntry
0x140023a22  xor     eax, eax
0x140023a24  xor     edx, edx; PriorityBoost
0x140023a26  mov     rcx, rbx; Irp
0x140023a29  mov     [rbx+30h], eax
0x140023a2c  mov     [rbx+38h], rax
0x140023a30  call    cs:__imp_IofCompleteRequest
0x140023a37  nop     dword ptr [rax+rax+00h]
0x140023a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140023a43  cmp     rcx, rsi
0x140023a46  jz      short loc_140023A4F
0x140023a48  mov     eax, [rcx+2Ch]
0x140023a4b  test    al, 1
0x140023a4d  jnz     short loc_140023A94
0x140023a4f  xor     r9d, r9d
0x140023a52  xor     r8d, r8d
0x140023a55  xor     edx, edx
0x140023a57  mov     ecx, 736F6C63h
0x140023a5c  call    USBSTOR_LogEntry
0x140023a61  mov     rbx, [rsp+28h+arg_0]
0x140023a66  xor     eax, eax
0x140023a68  mov     rsi, [rsp+28h+arg_8]
0x140023a6d  add     rsp, 20h
0x140023a71  pop     rdi
0x140023a72  retn
0x140023a74  cmp     byte ptr [rcx+29h], 5
0x140023a78  jb      short loc_140023A0F
0x140023a7a  mov     rcx, [rcx+18h]
0x140023a7e  lea     r8, WPP_83961903f8913993eee34094953b83c3_Traceguids
0x140023a85  mov     edx, 0Ch
0x140023a8a  call    WPP_SF_
0x140023a8f  jmp     loc_140023A0F
0x140023a94  cmp     byte ptr [rcx+29h], 4
0x140023a98  jb      short loc_140023A4F
0x140023a9a  mov     rcx, [rcx+18h]
0x140023a9e  lea     r8, WPP_83961903f8913993eee34094953b83c3_Traceguids
0x140023aa5  mov     edx, 0Dh
0x140023aaa  call    WPP_SF_
0x140023aaf  jmp     short loc_140023A4F
```
