# DpspRaiseMisconfigurationEvent

- ea: `0x180012b74`
- end: `0x180012c49`
- name: `DpspRaiseMisconfigurationEvent`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e9d4`

## callees

- `0x180009090`
- `0x180009fb0`
- `0x180012b74`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180012bc0`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180012bc0`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180012bef`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180012bef`

## string_xrefs

- `0x180012c1c`: `DpspRaiseMisconfigurationEvent`

## pseudocode

```c
__int64 __fastcall DpspRaiseMisconfigurationEvent(ULONGLONG a1)
{
  signed int Args; // ebx
  signed int v3; // eax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-28h] BYREF

  UserData = 0;
  if ( a1 )
  {
    Args = 0;
    if ( EventEnabled(g_hETW, &WDI_DPS_EVENT_MISCONFIGURATION) )
    {
      UserData.Ptr = a1;
      *(_QWORD *)&UserData.Size = 16;
      v3 = EventWrite(g_hETW, &WDI_DPS_EVENT_MISCONFIGURATION, 1u, &UserData);
      Args = v3;
      if ( v3 > 0 )
        Args = (unsigned __int16)v3 | 0x80070000;
      if ( Args < 0 )
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsevents.cpp",
          (int)L"DpspRaiseMisconfigurationEvent",
          121,
          (int)L"Error = %d",
          Args);
    }
  }
  else
  {
    Args = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsevents.cpp",
      (int)L"DpspRaiseMisconfigurationEvent",
      107,
      (int)L"Error = %d",
      87);
  }
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x180012b74  mov     [rsp+arg_0], rbx
0x180012b79  push    rdi
0x180012b7a  sub     rsp, 50h
0x180012b7e  mov     rax, cs:__security_cookie
0x180012b85  xor     rax, rsp
0x180012b88  mov     [rsp+58h+var_18], rax
0x180012b8d  xorps   xmm0, xmm0
0x180012b90  mov     rdi, rcx
0x180012b93  movups  xmmword ptr [rsp+58h+UserData.Ptr], xmm0
0x180012b98  test    rcx, rcx
0x180012b9b  jnz     short loc_180012BB0
0x180012b9d  mov     ebx, 80070057h
0x180012ba2  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x180012baa  lea     r8d, [rcx+6Bh]
0x180012bae  jmp     short loc_180012C15
0x180012bb0  mov     rcx, cs:g_hETW; RegHandle
0x180012bb7  lea     rdx, WDI_DPS_EVENT_MISCONFIGURATION; EventDescriptor
0x180012bbe  xor     ebx, ebx
0x180012bc0  call    cs:__imp_EventEnabled
0x180012bc6  test    al, al
0x180012bc8  jz      short loc_180012C2F
0x180012bca  mov     rcx, cs:g_hETW; RegHandle
0x180012bd1  lea     r9, [rsp+58h+UserData]; UserData
0x180012bd6  lea     r8d, [rbx+1]; UserDataCount
0x180012bda  mov     [rsp+58h+UserData.Ptr], rdi
0x180012bdf  lea     rdx, WDI_DPS_EVENT_MISCONFIGURATION; EventDescriptor
0x180012be6  mov     qword ptr [rsp+58h+UserData.Size], 10h
0x180012bef  call    cs:__imp_EventWrite
0x180012bf5  mov     ebx, eax
0x180012bf7  test    eax, eax
0x180012bf9  jle     short loc_180012C04
0x180012bfb  movzx   ebx, ax
0x180012bfe  or      ebx, 80070000h
0x180012c04  test    ebx, ebx
0x180012c06  jns     short loc_180012C2F
0x180012c08  movzx   ecx, bx
0x180012c0b  mov     r8d, 79h ; 'y'; int
0x180012c11  mov     dword ptr [rsp+58h+Args], ecx; Args
0x180012c15  lea     r9, aErrorD; "Error = %d"
0x180012c1c  lea     rdx, aDpspraisemisco; "DpspRaiseMisconfigurationEvent"
0x180012c23  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180012c2a  call    WdipTraceError
0x180012c2f  mov     eax, ebx
0x180012c31  mov     rcx, [rsp+58h+var_18]
0x180012c36  xor     rcx, rsp; StackCookie
0x180012c39  call    __security_check_cookie
0x180012c3e  mov     rbx, [rsp+58h+arg_0]
0x180012c43  add     rsp, 50h
0x180012c47  pop     rdi
0x180012c48  retn
```
