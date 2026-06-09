# BdeCfgRestart(int)

- ea: `0x180007e60`
- end: `0x180007ebf`
- name: `?BdeCfgRestart@@YAJH@Z`
- size: `95`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180007e60`
- `0x180008020`

## import_xrefs

- `ADVAPI32!InitiateShutdownW` at `0x180007e99`
- `ADVAPI32!InitiateShutdownW` at `0x180007e99`

## string_xrefs

- `0x180007e6c`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 __fastcall BdeCfgRestart(int a1)
{
  int v2; // ebx
  signed int v3; // eax

  v2 = BdeCfgpAcquireNamedPrivilege(L"SeShutdownPrivilege");
  if ( v2 >= 0 )
  {
    v3 = InitiateShutdownW(0, 0, 0, (a1 != 0) + 36, 0x80020007);
    if ( v3 )
    {
      if ( v3 > 0 )
        return (unsigned __int16)v3 | 0x80070000;
      else
        return (unsigned int)v3;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180007e60  mov     [rsp+arg_0], rbx
0x180007e65  push    rdi
0x180007e66  sub     rsp, 30h
0x180007e6a  mov     edi, ecx
0x180007e6c  lea     rcx, aSeshutdownpriv; "SeShutdownPrivilege"
0x180007e73  call    ?BdeCfgpAcquireNamedPrivilege@@YAJPEAG@Z; BdeCfgpAcquireNamedPrivilege(ushort *)
0x180007e78  mov     ebx, eax
0x180007e7a  test    eax, eax
0x180007e7c  js      short loc_180007EB2
0x180007e7e  neg     edi
0x180007e80  mov     [rsp+38h+dwReason], 80020007h; dwReason
0x180007e88  sbb     r9d, r9d
0x180007e8b  xor     r8d, r8d; dwGracePeriod
0x180007e8e  neg     r9d
0x180007e91  xor     edx, edx; lpMessage
0x180007e93  add     r9d, 24h ; '$'; dwShutdownFlags
0x180007e97  xor     ecx, ecx; lpMachineName
0x180007e99  call    cs:__imp_InitiateShutdownW
0x180007e9f  test    eax, eax
0x180007ea1  jz      short loc_180007EB2
0x180007ea3  jg      short loc_180007EA9
0x180007ea5  mov     ebx, eax
0x180007ea7  jmp     short loc_180007EB2
0x180007ea9  movzx   ebx, ax
0x180007eac  or      ebx, 80070000h
0x180007eb2  mov     eax, ebx
0x180007eb4  mov     rbx, [rsp+38h+arg_0]
0x180007eb9  add     rsp, 30h
0x180007ebd  pop     rdi
0x180007ebe  retn
```
