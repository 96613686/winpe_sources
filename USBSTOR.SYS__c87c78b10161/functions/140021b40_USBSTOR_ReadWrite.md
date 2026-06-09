# USBSTOR_ReadWrite

- ea: `0x140021b40`
- end: `0x140021c1a`
- name: `USBSTOR_ReadWrite`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140003630`
- `0x1400105e8`
- `0x140010664`
- `0x140021b40`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140021bb4`
- `ntoskrnl!IofCompleteRequest` at `0x140021bb4`

## pseudocode

```c
__int64 __fastcall USBSTOR_ReadWrite(__int64 a1, IRP *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_83961903f8913993eee34094953b83c3_Traceguids);
  }
  USBSTOR_LogEntry(538990418, a1, a2, 0);
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = -1073741811;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_83961903f8913993eee34094953b83c3_Traceguids);
  }
  USBSTOR_LogEntry(538998642, -1073741811, 0, 0);
  return 3221225485LL;
}

```

## disassembly

```asm
0x140021b40  mov     [rsp+arg_0], rbx
0x140021b45  mov     [rsp+arg_8], rsi
0x140021b4a  push    rdi
0x140021b4b  sub     rsp, 20h
0x140021b4f  mov     rbx, rdx
0x140021b52  mov     rdi, rcx
0x140021b55  mov     rcx, cs:WPP_GLOBAL_Control
0x140021b5c  lea     rsi, WPP_GLOBAL_Control
0x140021b63  cmp     rcx, rsi
0x140021b66  jz      short loc_140021B8A
0x140021b68  mov     eax, [rcx+2Ch]
0x140021b6b  test    al, 8
0x140021b6d  jz      short loc_140021B8A
0x140021b6f  cmp     byte ptr [rcx+29h], 5
0x140021b73  jb      short loc_140021B8A
0x140021b75  mov     rcx, [rcx+18h]
0x140021b79  lea     r8, WPP_83961903f8913993eee34094953b83c3_Traceguids
0x140021b80  mov     edx, 0Eh
0x140021b85  call    WPP_SF_
0x140021b8a  xor     r9d, r9d
0x140021b8d  mov     r8, rbx
0x140021b90  mov     rdx, rdi
0x140021b93  mov     ecx, 20205752h
0x140021b98  call    USBSTOR_LogEntry
0x140021b9d  mov     rdi, 0FFFFFFFFC000000Dh
0x140021ba4  mov     qword ptr [rbx+38h], 0
0x140021bac  xor     edx, edx; PriorityBoost
0x140021bae  mov     [rbx+30h], edi
0x140021bb1  mov     rcx, rbx; Irp
0x140021bb4  call    cs:__imp_IofCompleteRequest
0x140021bbb  nop     dword ptr [rax+rax+00h]
0x140021bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x140021bc7  cmp     rcx, rsi
0x140021bca  jz      short loc_140021BF4
0x140021bcc  mov     eax, [rcx+2Ch]
0x140021bcf  test    al, 8
0x140021bd1  jz      short loc_140021BF4
0x140021bd3  cmp     byte ptr [rcx+29h], 4
0x140021bd7  jb      short loc_140021BF4
0x140021bd9  mov     rcx, [rcx+18h]
0x140021bdd  lea     r8, WPP_83961903f8913993eee34094953b83c3_Traceguids
0x140021be4  mov     edx, 0Fh
0x140021be9  mov     r9d, 0C000000Dh
0x140021bef  call    WPP_SF_d
0x140021bf4  xor     r9d, r9d
0x140021bf7  xor     r8d, r8d
0x140021bfa  mov     rdx, rdi
0x140021bfd  mov     ecx, 20207772h
0x140021c02  call    USBSTOR_LogEntry
0x140021c07  mov     rbx, [rsp+28h+arg_0]
0x140021c0c  mov     eax, edi
0x140021c0e  mov     rsi, [rsp+28h+arg_8]
0x140021c13  add     rsp, 20h
0x140021c17  pop     rdi
0x140021c18  retn
```
