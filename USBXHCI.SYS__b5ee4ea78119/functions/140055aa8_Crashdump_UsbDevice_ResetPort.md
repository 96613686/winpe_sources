# Crashdump_UsbDevice_ResetPort

- ea: `0x140055aa8`
- end: `0x140055c97`
- name: `Crashdump_UsbDevice_ResetPort`
- size: `495`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140051fcc`
- `0x140052480`

## callees

- `0x140054b50`
- `0x140055484`
- `0x140055aa8`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140055ae3`
- `ntoskrnl!DbgPrintEx` at `0x140055b4b`
- `ntoskrnl!DbgPrintEx` at `0x140055c2f`
- `ntoskrnl!DbgPrintEx` at `0x140055c4d`
- `ntoskrnl!DbgPrintEx` at `0x140055c86`
- `ntoskrnl!DbgPrintEx` at `0x140055ae3`
- `ntoskrnl!DbgPrintEx` at `0x140055b4b`
- `ntoskrnl!DbgPrintEx` at `0x140055c2f`
- `ntoskrnl!DbgPrintEx` at `0x140055c4d`
- `ntoskrnl!DbgPrintEx` at `0x140055c86`
- `HAL!KeStallExecutionProcessor` at `0x140055b61`
- `HAL!KeStallExecutionProcessor` at `0x140055bad`
- `HAL!KeStallExecutionProcessor` at `0x140055bf7`
- `HAL!KeStallExecutionProcessor` at `0x140055b61`
- `HAL!KeStallExecutionProcessor` at `0x140055bad`
- `HAL!KeStallExecutionProcessor` at `0x140055bf7`

## string_xrefs

- `0x140055c19`: `XHCIDUMP: Port reset took %u retries and %u ms to complete\n`
- `0x140055c79`: `XHCIDUMP: Port reset did not complete after %u retries and %u ms\n`

## pseudocode

```c
__int64 __fastcall Crashdump_UsbDevice_ResetPort(__int64 a1, unsigned int a2, int a3)
{
  __int64 v6; // r9
  int v7; // edi
  int PortStatus; // ebx
  _BYTE *v9; // rbx
  int v10; // eax
  __int64 v11; // r8
  unsigned int i; // edi
  _BYTE *v14; // [rsp+88h] [rbp+20h] BYREF

  v14 = 0;
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_ResetPort: begin: port %u\n", a2);
  v7 = 0;
  if ( a3 == 20 )
  {
    while ( 1 )
    {
      PortStatus = Crashdump_UsbDevice_GetPortStatus(a1, a2, &v14);
      if ( PortStatus < 0 )
        break;
      v9 = v14;
      if ( (v14[2] & 1) != 0 )
      {
        LOBYTE(v6) = 1;
        v10 = Crashdump_UsbDevice_ChangePortFeature(a1, a2, 16, v6);
        if ( v10 < 0 )
          DbgPrintEx(0x93u, 3u, "XHCIDUMP: Clearing Connect Status Change failed with 0x%X\n", v10);
      }
      if ( (*v9 & 1) != 0 )
        goto LABEL_10;
      KeStallExecutionProcessor(0x186A0u);
      if ( (unsigned int)++v7 >= 5 )
      {
        if ( (*v9 & 1) == 0 )
          goto LABEL_9;
LABEL_10:
        v11 = 4;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v11 = 28;
LABEL_12:
    LOBYTE(v6) = 3;
    PortStatus = Crashdump_UsbDevice_ChangePortFeature(a1, a2, v11, v6);
    if ( PortStatus >= 0 )
    {
      KeStallExecutionProcessor(0x4E20u);
      for ( i = 0; i < 0x3E8; ++i )
      {
        PortStatus = Crashdump_UsbDevice_GetPortStatus(a1, a2, &v14);
        if ( PortStatus < 0 )
          goto LABEL_21;
        if ( (*v14 & 0x10) == 0 && (v14[2] & 0x10) != 0 )
        {
          DbgPrintEx(
            0x93u,
            3u,
            "XHCIDUMP: Port reset took %u retries and %u ms to complete\n",
            i + 1,
            20000 * (i + 1) / 0x3E8);
LABEL_20:
          PortStatus = 0;
          goto LABEL_21;
        }
        KeStallExecutionProcessor(0x4E20u);
      }
      if ( i != 1000 )
        goto LABEL_20;
      DbgPrintEx(0x93u, 3u, "XHCIDUMP: Port reset did not complete after %u retries and %u ms\n", 1000, 20000);
LABEL_9:
      PortStatus = -1073741630;
    }
  }
LABEL_21:
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_ResetPort: end 0x%X\n", PortStatus);
  return (unsigned int)PortStatus;
}

```

## disassembly

```asm
0x140055aa8  mov     rax, rsp
0x140055aab  push    rbx
0x140055aac  push    rbp
0x140055aad  push    rsi
0x140055aae  push    rdi
0x140055aaf  push    r13
0x140055ab1  push    r14
0x140055ab3  sub     rsp, 38h
0x140055ab7  mov     ebx, r8d
0x140055aba  mov     qword ptr [rax+20h], 0
0x140055ac2  mov     esi, edx
0x140055ac4  lea     r8, aXhcidumpCrashd_25; "XHCIDUMP: Crashdump_UsbDevice_ResetPort"...
0x140055acb  mov     rbp, rcx
0x140055ace  mov     r9d, edx
0x140055ad1  mov     r14d, 3
0x140055ad7  mov     r13d, 93h
0x140055add  mov     edx, r14d; Level
0x140055ae0  mov     ecx, r13d; ComponentId
0x140055ae3  call    cs:__imp_DbgPrintEx
0x140055aea  nop     dword ptr [rax+rax+00h]
0x140055aef  xor     edi, edi
0x140055af1  cmp     ebx, 14h
0x140055af4  jnz     loc_140055B8B
0x140055afa  lea     r8, [rsp+68h+arg_18]
0x140055b02  mov     edx, esi
0x140055b04  mov     rcx, rbp
0x140055b07  call    Crashdump_UsbDevice_GetPortStatus
0x140055b0c  mov     ebx, eax
0x140055b0e  test    eax, eax
0x140055b10  js      loc_140055C3D
0x140055b16  mov     rbx, [rsp+68h+arg_18]
0x140055b1e  test    byte ptr [rbx+2], 1
0x140055b22  jz      short loc_140055B57
0x140055b24  mov     r9b, 1
0x140055b27  mov     r8d, 10h
0x140055b2d  mov     edx, esi
0x140055b2f  mov     rcx, rbp
0x140055b32  call    Crashdump_UsbDevice_ChangePortFeature
0x140055b37  test    eax, eax
0x140055b39  jns     short loc_140055B57
0x140055b3b  mov     r9d, eax
0x140055b3e  lea     r8, aXhcidumpCleari; "XHCIDUMP: Clearing Connect Status Chang"...
0x140055b45  mov     edx, r14d; Level
0x140055b48  mov     ecx, r13d; ComponentId
0x140055b4b  call    cs:__imp_DbgPrintEx
0x140055b52  nop     dword ptr [rax+rax+00h]
0x140055b57  test    byte ptr [rbx], 1
0x140055b5a  jnz     short loc_140055B83
0x140055b5c  mov     ecx, 186A0h; MicroSeconds
0x140055b61  call    cs:__imp_KeStallExecutionProcessor
0x140055b68  nop     dword ptr [rax+rax+00h]
0x140055b6d  inc     edi
0x140055b6f  cmp     edi, 5
0x140055b72  jb      short loc_140055AFA
0x140055b74  test    byte ptr [rbx], 1
0x140055b77  jnz     short loc_140055B83
0x140055b79  mov     ebx, 0C00000C2h
0x140055b7e  jmp     loc_140055C3D
0x140055b83  mov     r8d, 4
0x140055b89  jmp     short loc_140055B91
0x140055b8b  mov     r8d, 1Ch
0x140055b91  mov     r9b, r14b
0x140055b94  mov     edx, esi
0x140055b96  mov     rcx, rbp
0x140055b99  call    Crashdump_UsbDevice_ChangePortFeature
0x140055b9e  mov     ebx, eax
0x140055ba0  test    eax, eax
0x140055ba2  js      loc_140055C3D
0x140055ba8  mov     ecx, 4E20h; MicroSeconds
0x140055bad  call    cs:__imp_KeStallExecutionProcessor
0x140055bb4  nop     dword ptr [rax+rax+00h]
0x140055bb9  xor     edi, edi
0x140055bbb  cmp     edi, 3E8h
0x140055bc1  jnb     loc_140055C69
0x140055bc7  lea     r8, [rsp+68h+arg_18]
0x140055bcf  mov     edx, esi
0x140055bd1  mov     rcx, rbp
0x140055bd4  call    Crashdump_UsbDevice_GetPortStatus
0x140055bd9  mov     ebx, eax
0x140055bdb  test    eax, eax
0x140055bdd  js      short loc_140055C3D
0x140055bdf  mov     rcx, [rsp+68h+arg_18]
0x140055be7  test    byte ptr [rcx], 10h
0x140055bea  jnz     short loc_140055BF2
0x140055bec  test    byte ptr [rcx+2], 10h
0x140055bf0  jnz     short loc_140055C07
0x140055bf2  mov     ecx, 4E20h; MicroSeconds
0x140055bf7  call    cs:__imp_KeStallExecutionProcessor
0x140055bfe  nop     dword ptr [rax+rax+00h]
0x140055c03  inc     edi
0x140055c05  jmp     short loc_140055BBB
0x140055c07  lea     eax, [rdi+1]
0x140055c0a  imul    ecx, eax, 4E20h
0x140055c10  lea     r9d, [rdi+1]
0x140055c14  mov     eax, 10624DD3h
0x140055c19  lea     r8, aXhcidumpPortRe_0; "XHCIDUMP: Port reset took %u retries an"...
0x140055c20  mul     ecx
0x140055c22  mov     ecx, r13d; ComponentId
0x140055c25  shr     edx, 6
0x140055c28  mov     [rsp+68h+var_48], edx
0x140055c2c  mov     edx, r14d; Level
0x140055c2f  call    cs:__imp_DbgPrintEx
0x140055c36  nop     dword ptr [rax+rax+00h]
0x140055c3b  xor     ebx, ebx
0x140055c3d  mov     r9d, ebx
0x140055c40  lea     r8, aXhcidumpCrashd_87; "XHCIDUMP: Crashdump_UsbDevice_ResetPort"...
0x140055c47  mov     edx, r14d; Level
0x140055c4a  mov     ecx, r13d; ComponentId
0x140055c4d  call    cs:__imp_DbgPrintEx
0x140055c54  nop     dword ptr [rax+rax+00h]
0x140055c59  mov     eax, ebx
0x140055c5b  add     rsp, 38h
0x140055c5f  pop     r14
0x140055c61  pop     r13
0x140055c63  pop     rdi
0x140055c64  pop     rsi
0x140055c65  pop     rbp
0x140055c66  pop     rbx
0x140055c67  retn
0x140055c69  jnz     short loc_140055C3B
0x140055c6b  mov     r9d, 3E8h
0x140055c71  mov     [rsp+68h+var_48], 4E20h
0x140055c79  lea     r8, aXhcidumpPortRe; "XHCIDUMP: Port reset did not complete a"...
0x140055c80  mov     edx, r14d; Level
0x140055c83  mov     ecx, r13d; ComponentId
0x140055c86  call    cs:__imp_DbgPrintEx
0x140055c8d  nop     dword ptr [rax+rax+00h]
0x140055c92  jmp     loc_140055B79
```
