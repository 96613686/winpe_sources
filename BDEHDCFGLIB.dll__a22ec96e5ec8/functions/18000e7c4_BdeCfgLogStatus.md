# BdeCfgLogStatus

- ea: `0x18000e7c4`
- end: `0x18000e838`
- name: `BdeCfgLogStatus`
- size: `116`
- prototype: `signed int()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800101a0`

## callees

- `0x18000e7c4`

## import_xrefs

- `ntdll!WinSqmAddToStreamEx` at `0x18000e801`
- `ntdll!WinSqmAddToStreamEx` at `0x18000e801`
- `ADVAPI32!EventWrite` at `0x18000e81b`
- `ADVAPI32!EventWrite` at `0x18000e81b`

## pseudocode

```c
signed int BdeCfgLogStatus()
{
  signed int result; // eax
  _DWORD v1[5]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v2; // [rsp+44h] [rbp-14h]

  v1[0] = 16;
  v1[2] = 15;
  v1[1] = 1;
  v1[4] = 16;
  v2 = 1;
  WinSqmAddToStreamEx(0, 4464, 2, v1, 0);
  result = EventWrite(g_EventRegistrationHandle, &BDECFG_EVT_SUCCESS, 0, 0);
  if ( !result )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000e7c4  sub     rsp, 58h
0x18000e7c8  mov     eax, 10h
0x18000e7cd  mov     [rsp+58h+var_28], eax
0x18000e7d1  mov     [rsp+58h+var_20], 0Fh
0x18000e7d9  lea     ecx, [rax-0Fh]
0x18000e7dc  mov     [rsp+58h+var_24], ecx
0x18000e7e0  mov     [rsp+58h+var_18], eax
0x18000e7e4  mov     [rsp+58h+var_14], rcx
0x18000e7e9  mov     [rsp+58h+var_38], 0
0x18000e7f1  lea     r9, [rsp+58h+var_28]
0x18000e7f6  mov     edx, 1170h
0x18000e7fb  xor     ecx, ecx
0x18000e7fd  lea     r8d, [rax-0Eh]
0x18000e801  call    cs:__imp_WinSqmAddToStreamEx
0x18000e807  xor     r9d, r9d; UserData
0x18000e80a  xor     r8d, r8d; UserDataCount
0x18000e80d  lea     rdx, BDECFG_EVT_SUCCESS; EventDescriptor
0x18000e814  mov     rcx, cs:?g_EventRegistrationHandle@@3_KA; RegHandle
0x18000e81b  call    cs:__imp_EventWrite
0x18000e821  test    eax, eax
0x18000e823  jz      short loc_18000E831
0x18000e825  jle     short loc_18000E833
0x18000e827  movzx   eax, ax
0x18000e82a  or      eax, 80070000h
0x18000e82f  jmp     short loc_18000E833
0x18000e831  xor     eax, eax
0x18000e833  add     rsp, 58h
0x18000e837  retn
0x18001432c  push    rbp
0x18001432e  sub     rsp, 30h
0x180014332  mov     rbp, rdx
0x180014335  add     rsp, 30h
0x180014339  pop     rbp
0x18001433a  retn
```
