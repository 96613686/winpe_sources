# NetrWkstaTransportAdd

- ea: `0x18002aa00`
- end: `0x18002aa8b`
- name: `NetrWkstaTransportAdd`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180005a60`
- `0x180009a40`
- `0x18002aa00`

## string_xrefs

- `0x18002aa2d`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetrWkstaTransportAdd(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  int v6; // esi

  v6 = a2;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  if ( v6 )
    return 124;
  if ( *(_QWORD *)(a3 + 8) )
    return WsMapStatus(3221225488LL);
  if ( a4 )
    *a4 = 202;
  return 87;
}

```

## disassembly

```asm
0x18002aa00  mov     r11, rsp
0x18002aa03  mov     [r11+8], rbx
0x18002aa07  mov     [r11+10h], rsi
0x18002aa0b  push    rdi
0x18002aa0c  sub     rsp, 40h
0x18002aa10  mov     rax, cs:ConfigurationInfoSd
0x18002aa17  lea     rcx, WsConfigInfoMapping
0x18002aa1e  mov     [r11-18h], rcx
0x18002aa22  mov     rdi, r8
0x18002aa25  mov     [rsp+48h+var_20], 8
0x18002aa2d  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x18002aa34  mov     [r11-28h], rax
0x18002aa38  mov     rbx, r9
0x18002aa3b  mov     esi, edx
0x18002aa3d  call    NetpAccessCheckAndAuditEx
0x18002aa42  test    eax, eax
0x18002aa44  jz      short loc_18002AA4D
0x18002aa46  mov     eax, 5
0x18002aa4b  jmp     short loc_18002AA7B
0x18002aa4d  test    esi, esi
0x18002aa4f  jz      short loc_18002AA58
0x18002aa51  mov     eax, 7Ch ; '|'
0x18002aa56  jmp     short loc_18002AA7B
0x18002aa58  cmp     qword ptr [rdi+8], 0
0x18002aa5d  jnz     short loc_18002AA71
0x18002aa5f  test    rbx, rbx
0x18002aa62  jz      short loc_18002AA6A
0x18002aa64  mov     dword ptr [rbx], 0CAh
0x18002aa6a  mov     eax, 57h ; 'W'
0x18002aa6f  jmp     short loc_18002AA7B
0x18002aa71  mov     ecx, 0C0000010h
0x18002aa76  call    WsMapStatus
0x18002aa7b  mov     rbx, [rsp+48h+arg_0]
0x18002aa80  mov     rsi, [rsp+48h+arg_8]
0x18002aa85  add     rsp, 40h
0x18002aa89  pop     rdi
0x18002aa8a  retn
```
