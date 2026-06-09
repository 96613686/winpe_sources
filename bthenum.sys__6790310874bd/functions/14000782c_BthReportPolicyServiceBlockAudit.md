# BthReportPolicyServiceBlockAudit

- ea: `0x14000782c`
- end: `0x14000787d`
- name: `BthReportPolicyServiceBlockAudit`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140019058`

## callees

- `0x14000782c`
- `0x140007a78`

## string_xrefs

- `0x14000783c`: `ServicesAllowedList`

## pseudocode

```c
__int64 __fastcall BthReportPolicyServiceBlockAudit(char a1, __int64 a2, int a3)
{
  const wchar_t *v3; // r9

  if ( (Microsoft_Windows_Bluetooth_PolicyEnableBits & 1) == 0 )
    return 0;
  v3 = L"accepted";
  if ( !a1 )
    v3 = L"blocked";
  return McTemplateK0zjxzz_EtwWriteTransfer(
           a1,
           a2,
           a3,
           (_DWORD)v3,
           a2,
           a3,
           (__int64)L"Bluetooth",
           (__int64)L"ServicesAllowedList");
}

```

## disassembly

```asm
0x14000782c  mov     r11, rsp
0x14000782f  sub     rsp, 48h
0x140007833  test    cs:Microsoft_Windows_Bluetooth_PolicyEnableBits, 1
0x14000783a  jz      short loc_140007875
0x14000783c  lea     rax, aServicesallowe; "ServicesAllowedList"
0x140007843  test    cl, cl
0x140007845  mov     [r11-10h], rax
0x140007849  lea     r10, aBlocked; "blocked"
0x140007850  lea     rax, aBluetooth; "Bluetooth"
0x140007857  mov     [r11-18h], rax
0x14000785b  lea     r9, aAccepted; "accepted"
0x140007862  mov     [r11-20h], r8
0x140007866  cmovz   r9, r10
0x14000786a  mov     [r11-28h], rdx
0x14000786e  call    McTemplateK0zjxzz_EtwWriteTransfer
0x140007873  jmp     short loc_140007877
0x140007875  xor     eax, eax
0x140007877  add     rsp, 48h
0x14000787b  retn
```
