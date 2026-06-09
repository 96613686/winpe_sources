# ConfigureRootDevices

- ea: `0x140012c2c`
- end: `0x140012ce2`
- name: `ConfigureRootDevices`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x140013220`

## callees

- `0x140012c2c`
- `0x140013f6c`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140012c8c`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140012c8c`
- `DEVRTL!DevRtlWriteTextLog` at `0x140012c77`
- `DEVRTL!DevRtlWriteTextLog` at `0x140012cac`
- `DEVRTL!DevRtlWriteTextLog` at `0x140012c77`
- `DEVRTL!DevRtlWriteTextLog` at `0x140012cac`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140012c41`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140012c41`
- `drvstore!DriverStoreReflectW` at `0x140012c56`
- `drvstore!DriverStoreReflectW` at `0x140012c56`

## string_xrefs

- `0x140012c63`: `Unable to configure driver package. Error = 0x%08X`

## pseudocode

```c
int __fastcall ConfigureRootDevices(__int64 a1, WCHAR *a2)
{
  __int64 ThreadLogToken; // rsi
  int v5; // eax
  __int64 v6; // rax
  DEVNODE pdnDevInst; // [rsp+70h] [rbp+18h] BYREF

  pdnDevInst = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  v5 = DriverStoreReflectW(0, a1, 32, 0);
  if ( v5 )
    DevRtlWriteTextLog(ThreadLogToken, 1, 2, "Unable to configure driver package. Error = 0x%08X", v5);
  LODWORD(v6) = CM_Locate_DevNodeW(&pdnDevInst, (DEVINSTID_W)L"HTREE\\ROOT\\0", 0);
  if ( (_DWORD)v6 )
  {
    LODWORD(v6) = DevRtlWriteTextLog(ThreadLogToken, 1, 2, "Unable to locate root device. cr = 0x%02X", v6);
  }
  else
  {
    while ( *a2 )
    {
      InstallRootDevice(a2, pdnDevInst);
      v6 = -1;
      do
        ++v6;
      while ( a2[v6] );
      a2 += v6 + 1;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140012c2c  push    rbx
0x140012c2e  push    rbp
0x140012c2f  push    rsi
0x140012c30  push    rdi
0x140012c31  sub     rsp, 38h
0x140012c35  xor     ebp, ebp
0x140012c37  mov     rdi, rdx
0x140012c3a  mov     [rsp+58h+pdnDevInst], ebp
0x140012c3e  mov     rbx, rcx
0x140012c41  call    cs:__imp_DevRtlGetThreadLogToken
0x140012c47  xor     r9d, r9d
0x140012c4a  lea     r8d, [rbp+20h]
0x140012c4e  mov     rdx, rbx
0x140012c51  xor     ecx, ecx
0x140012c53  mov     rsi, rax
0x140012c56  call    cs:__imp_DriverStoreReflectW
0x140012c5c  lea     ebx, [rbp+2]
0x140012c5f  test    eax, eax
0x140012c61  jz      short loc_140012C7D
0x140012c63  lea     r9, aUnableToConfig_0; "Unable to configure driver package. Err"...
0x140012c6a  mov     [rsp+58h+var_38], eax
0x140012c6e  mov     r8d, ebx
0x140012c71  lea     edx, [rbp+1]
0x140012c74  mov     rcx, rsi
0x140012c77  call    cs:__imp_DevRtlWriteTextLog
0x140012c7d  xor     r8d, r8d; ulFlags
0x140012c80  lea     rdx, pDeviceID; "HTREE\\ROOT\\0"
0x140012c87  lea     rcx, [rsp+58h+pdnDevInst]; pdnDevInst
0x140012c8c  call    cs:__imp_CM_Locate_DevNodeW
0x140012c92  test    eax, eax
0x140012c94  jz      short loc_140012CD4
0x140012c96  lea     r9, aUnableToLocate_0; "Unable to locate root device. cr = 0x%0"...
0x140012c9d  mov     [rsp+58h+var_38], eax
0x140012ca1  mov     r8d, ebx
0x140012ca4  mov     edx, 1
0x140012ca9  mov     rcx, rsi
0x140012cac  call    cs:__imp_DevRtlWriteTextLog
0x140012cb2  jmp     short loc_140012CD9
0x140012cb4  mov     edx, [rsp+58h+pdnDevInst]; dnParent
0x140012cb8  mov     rcx, rdi; int
0x140012cbb  call    InstallRootDevice
0x140012cc0  or      rax, 0FFFFFFFFFFFFFFFFh
0x140012cc4  inc     rax
0x140012cc7  cmp     [rdi+rax*2], bp
0x140012ccb  jnz     short loc_140012CC4
0x140012ccd  lea     rdi, [rdi+rax*2]
0x140012cd1  add     rdi, rbx
0x140012cd4  cmp     [rdi], bp
0x140012cd7  jnz     short loc_140012CB4
0x140012cd9  add     rsp, 38h
0x140012cdd  pop     rdi
0x140012cde  pop     rsi
0x140012cdf  pop     rbp
0x140012ce0  pop     rbx
0x140012ce1  retn
```
