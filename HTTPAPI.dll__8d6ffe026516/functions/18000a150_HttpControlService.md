# HttpControlService

- ea: `0x18000a150`
- end: `0x18000a1ed`
- name: `HttpControlService`
- size: `157`
- prototype: `__int64 __fastcall(PVOID InputBuffer, ULONG InputBufferLength, PVOID, ULONG, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002b40`
- `0x18000a150`
- `0x18000b424`
- `0x18000c7e8`

## pseudocode

```c
__int64 __fastcall HttpControlService(PVOID InputBuffer, ULONG InputBufferLength, PVOID a3, ULONG a4, unsigned int *a5)
{
  ULONG v9; // eax
  ULONG v10; // edi

  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_qLqLq(
      (_DWORD)InputBuffer,
      InputBufferLength,
      (_DWORD)a3,
      (_DWORD)InputBuffer,
      InputBufferLength,
      (char)a3,
      a4,
      a5);
  *a5 = 0;
  v9 = HttpApiSynchronousDeviceControl(
         g_ServiceCommChannelHandle,
         0x124096u,
         InputBuffer,
         InputBufferLength,
         a3,
         a4,
         a5);
  v10 = v9;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_dL(*a5, 11, WPP_ad0900ad5f723157976909bc130b25bb_Traceguids, v9, *a5);
  return v10;
}

```

## disassembly

```asm
0x18000a150  mov     rax, rsp
0x18000a153  push    rbx
0x18000a154  push    rbp
0x18000a155  push    rsi
0x18000a156  push    rdi
0x18000a157  push    r14
0x18000a159  sub     rsp, 40h
0x18000a15d  mov     edi, r9d
0x18000a160  mov     rsi, r8
0x18000a163  mov     ebp, edx
0x18000a165  mov     r14, rcx
0x18000a168  test    cs:byte_1800126A3, 4
0x18000a16f  mov     rbx, [rsp+68h+arg_20]
0x18000a177  jz      short loc_18000A190
0x18000a179  mov     [rax-30h], rbx
0x18000a17d  mov     [rax-38h], r9d
0x18000a181  mov     r9, rcx
0x18000a184  mov     [rax-40h], r8
0x18000a188  mov     [rax-48h], edx
0x18000a18b  call    WPP_SF_qLqLq
0x18000a190  mov     dword ptr [rbx], 0
0x18000a196  mov     r9d, ebp; InputBufferLength
0x18000a199  mov     rcx, cs:g_ServiceCommChannelHandle; FileHandle
0x18000a1a0  mov     r8, r14; InputBuffer
0x18000a1a3  mov     [rsp+68h+var_38], rbx; __int64
0x18000a1a8  mov     edx, 124096h; IoControlCode
0x18000a1ad  mov     [rsp+68h+var_40], edi; ULONG
0x18000a1b1  mov     [rsp+68h+var_48], rsi; PVOID
0x18000a1b6  call    HttpApiSynchronousDeviceControl
0x18000a1bb  mov     edi, eax
0x18000a1bd  test    cs:byte_1800126A3, 4
0x18000a1c4  jz      short loc_18000A1E0
0x18000a1c6  mov     ecx, [rbx]
0x18000a1c8  lea     r8, WPP_ad0900ad5f723157976909bc130b25bb_Traceguids
0x18000a1cf  mov     edx, 0Bh
0x18000a1d4  mov     dword ptr [rsp+68h+var_48], ecx
0x18000a1d8  mov     r9d, eax
0x18000a1db  call    WPP_SF_dL
0x18000a1e0  mov     eax, edi
0x18000a1e2  add     rsp, 40h
0x18000a1e6  pop     r14
0x18000a1e8  pop     rdi
0x18000a1e9  pop     rsi
0x18000a1ea  pop     rbp
0x18000a1eb  pop     rbx
0x18000a1ec  retn
```
