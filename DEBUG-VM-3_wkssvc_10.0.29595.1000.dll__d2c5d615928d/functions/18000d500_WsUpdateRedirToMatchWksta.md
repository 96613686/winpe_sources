# WsUpdateRedirToMatchWksta

- ea: `0x18000d500`
- end: `0x18000d5db`
- name: `WsUpdateRedirToMatchWksta`
- size: `219`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18002a810`
- `0x18002d960`
- `0x18002d9b0`

## callees

- `0x180005a60`
- `0x18000d500`
- `0x18001e420`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18000d59c`
- `ntdll!NtFsControlFile` at `0x18000d59c`

## pseudocode

```c
__int64 __fastcall WsUpdateRedirToMatchWksta(int a1, _DWORD *a2)
{
  NTSTATUS Status; // eax
  __int64 result; // rax
  struct _IO_STATUS_BLOCK v5; // [rsp+58h] [rbp+17h] BYREF
  _DWORD v6[3]; // [rsp+68h] [rbp+27h] BYREF
  __int64 v7; // [rsp+74h] [rbp+33h]
  int v8; // [rsp+7Ch] [rbp+3Bh]
  __int64 v9; // [rsp+80h] [rbp+3Fh]
  int v10; // [rsp+88h] [rbp+47h]

  v8 = a1;
  v7 = 0;
  v9 = 0;
  v10 = 0;
  v6[1] = 6;
  v6[2] = 502;
  v6[0] = 0;
  v5 = 0;
  Status = NtFsControlFile(WsRedirDeviceHandle, 0, 0, 0, &v5, 0x140199u, v6, 0x24u, &xmmword_18004EF80, 0x8Cu);
  if ( Status >= 0 )
    Status = v5.Status;
  result = WsMapStatus((unsigned int)Status);
  if ( (_DWORD)result == 87 )
  {
    if ( a2 )
      *a2 = v8;
  }
  return result;
}

```

## disassembly

```asm
0x18000d500  mov     r11, rsp
0x18000d503  mov     [r11+18h], rbx
0x18000d507  push    rbp
0x18000d508  lea     rbp, [r11-5Fh]
0x18000d50c  sub     rsp, 90h
0x18000d513  mov     rax, cs:__security_cookie
0x18000d51a  xor     rax, rsp
0x18000d51d  mov     [rbp+57h+var_8], rax
0x18000d521  mov     dword ptr [rsp+48h], 8Ch; OutputBufferLength
0x18000d529  lea     rax, xmmword_18004EF80
0x18000d530  mov     [r11-58h], rax
0x18000d534  mov     rbx, rdx
0x18000d537  mov     dword ptr [rsp+38h], 24h ; '$'; InputBufferLength
0x18000d53f  lea     rax, [rbp+57h+var_30]
0x18000d543  mov     [r11-68h], rax
0x18000d547  xorps   xmm0, xmm0
0x18000d54a  lea     rax, [rbp+57h+var_40]
0x18000d54e  mov     [rbp+57h+var_1C], ecx
0x18000d551  mov     rcx, cs:WsRedirDeviceHandle; FileHandle
0x18000d558  xor     r9d, r9d; ApcContext
0x18000d55b  mov     dword ptr [rsp+28h], 140199h; FsControlCode
0x18000d563  xor     r8d, r8d; ApcRoutine
0x18000d566  xor     edx, edx; Event
0x18000d568  mov     [r11-78h], rax
0x18000d56c  mov     [rbp+57h+var_24], 0
0x18000d574  mov     [rbp+57h+var_18], 0
0x18000d57c  mov     [rbp+57h+var_10], 0
0x18000d583  mov     [rbp+57h+var_2C], 6
0x18000d58a  mov     [rbp+57h+var_28], 1F6h
0x18000d591  mov     [rbp+57h+var_30], 0
0x18000d598  movups  [rbp+57h+var_40], xmm0
0x18000d59c  call    cs:__imp_NtFsControlFile
0x18000d5a2  test    eax, eax
0x18000d5a4  cmovns  eax, dword ptr [rbp+57h+var_40]
0x18000d5a8  mov     ecx, eax
0x18000d5aa  call    WsMapStatus
0x18000d5af  cmp     eax, 57h ; 'W'
0x18000d5b2  jnz     short loc_18000D5BE
0x18000d5b4  test    rbx, rbx
0x18000d5b7  jz      short loc_18000D5BE
0x18000d5b9  mov     ecx, [rbp+57h+var_1C]
0x18000d5bc  mov     [rbx], ecx
0x18000d5be  mov     rcx, [rbp+57h+var_8]
0x18000d5c2  xor     rcx, rsp; StackCookie
0x18000d5c5  call    __security_check_cookie
0x18000d5ca  mov     rbx, [rsp+90h+arg_10]
0x18000d5d2  add     rsp, 90h
0x18000d5d9  pop     rbp
0x18000d5da  retn
```
