# WsDeleteNetUseCredential

- ea: `0x18002eda0`
- end: `0x18002edf4`
- name: `WsDeleteNetUseCredential`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800012a0`
- `0x180001710`

## callees

- `0x18001e420`
- `0x18002ebd4`
- `0x18002eda0`

## import_xrefs

- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18002edd5`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18002edd5`

## pseudocode

```c
int __fastcall WsDeleteNetUseCredential(__int64 a1, DWORD a2)
{
  int result; // eax
  WCHAR TargetName[344]; // [rsp+20h] [rbp-2C8h] BYREF

  result = ComputeTargetNameFromUncName(a1, TargetName);
  if ( result )
    return CredDeleteW(TargetName, a2, 0);
  return result;
}

```

## disassembly

```asm
0x18002eda0  push    rbx
0x18002eda2  sub     rsp, 2E0h
0x18002eda9  mov     rax, cs:__security_cookie
0x18002edb0  xor     rax, rsp
0x18002edb3  mov     [rsp+2E8h+var_18], rax
0x18002edbb  mov     ebx, edx
0x18002edbd  lea     rdx, [rsp+2E8h+TargetName]
0x18002edc2  call    ComputeTargetNameFromUncName
0x18002edc7  test    eax, eax
0x18002edc9  jz      short loc_18002EDDB
0x18002edcb  xor     r8d, r8d; Flags
0x18002edce  lea     rcx, [rsp+2E8h+TargetName]; TargetName
0x18002edd3  mov     edx, ebx; Type
0x18002edd5  call    cs:__imp_CredDeleteW
0x18002eddb  mov     rcx, [rsp+2E8h+var_18]
0x18002ede3  xor     rcx, rsp; StackCookie
0x18002ede6  call    __security_check_cookie
0x18002edeb  add     rsp, 2E0h
0x18002edf2  pop     rbx
0x18002edf3  retn
```
