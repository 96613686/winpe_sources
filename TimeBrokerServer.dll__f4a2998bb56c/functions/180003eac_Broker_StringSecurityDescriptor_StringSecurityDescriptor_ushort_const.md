# Broker::StringSecurityDescriptor::StringSecurityDescriptor(ushort const *)

- ea: `0x180003eac`
- end: `0x180003f65`
- name: `??0StringSecurityDescriptor@Broker@@QEAA@PEBG@Z`
- size: `185`
- prototype: `PSECURITY_DESCRIPTOR *__fastcall(PSECURITY_DESCRIPTOR *SecurityDescriptor, LPCWSTR StringSecurityDescriptor)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003cac`
- `0x18000e8c4`
- `0x180019538`

## callees

- `0x180003800`
- `0x180003eac`
- `0x180011240`
- `0x18001181c`
- `0x180013978`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003edc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003edc`

## pseudocode

```c
PSECURITY_DESCRIPTOR *__fastcall Broker::StringSecurityDescriptor::StringSecurityDescriptor(
        PSECURITY_DESCRIPTOR *SecurityDescriptor,
        LPCWSTR StringSecurityDescriptor)
{
  _BYTE v4[24]; // [rsp+20h] [rbp-50h] BYREF
  int v5; // [rsp+38h] [rbp-38h]
  unsigned int v6; // [rsp+40h] [rbp-30h]
  _QWORD pExceptionObject[3]; // [rsp+48h] [rbp-28h] BYREF
  int v8; // [rsp+60h] [rbp-10h]
  unsigned int v9; // [rsp+68h] [rbp-8h]
  ULONG SecurityDescriptorSize; // [rsp+80h] [rbp+10h] BYREF

  SecurityDescriptorSize = 0;
  *SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          StringSecurityDescriptor,
          1u,
          SecurityDescriptor,
          &SecurityDescriptorSize) )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)v4);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_a9458e0debc7300a47110d600cc51ede_Traceguids, v6);
    std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)v4);
    v8 = v5;
    pExceptionObject[0] = &Broker::Win32Error::`vftable';
    v9 = v6;
    throw (Broker::Win32Error *)pExceptionObject;
  }
  return SecurityDescriptor;
}

```

## disassembly

```asm
0x180003eac  mov     [rsp-8+arg_8], rbx
0x180003eb1  push    rbp
0x180003eb2  mov     rbp, rsp
0x180003eb5  sub     rsp, 70h
0x180003eb9  mov     rax, rdx
0x180003ebc  mov     rbx, rcx
0x180003ebf  mov     [rbp+SecurityDescriptorSize], 0
0x180003ec6  mov     qword ptr [rcx], 0
0x180003ecd  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x180003ed1  mov     r8, rcx; SecurityDescriptor
0x180003ed4  mov     edx, 1; StringSDRevision
0x180003ed9  mov     rcx, rax; StringSecurityDescriptor
0x180003edc  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180003ee2  test    eax, eax
0x180003ee4  jnz     short loc_180003F54
0x180003ee6  lea     rcx, [rbp+var_50]; this
0x180003eea  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180003eef  nop
0x180003ef0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ef7  test    dword ptr [rcx+1Ch], 400h
0x180003efe  jz      short loc_180003F1F
0x180003f00  cmp     byte ptr [rcx+19h], 2
0x180003f04  jb      short loc_180003F1F
0x180003f06  mov     edx, 0Ah
0x180003f0b  mov     r9d, [rbp+var_30]
0x180003f0f  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x180003f16  mov     rcx, [rcx+10h]
0x180003f1a  call    WPP_SF_d
0x180003f1f  lea     rdx, [rbp+var_50]; struct std::exception *
0x180003f23  lea     rcx, [rbp+pExceptionObject]; this
0x180003f27  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180003f2c  mov     eax, [rbp+var_38]
0x180003f2f  mov     [rbp+var_10], eax
0x180003f32  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180003f39  mov     [rbp+pExceptionObject], rax
0x180003f3d  mov     eax, [rbp+var_30]
0x180003f40  mov     [rbp+var_8], eax
0x180003f43  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180003f4a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003f4e  call    _CxxThrowException_0
0x180003f54  mov     rax, rbx
0x180003f57  mov     rbx, [rsp+70h+arg_8]
0x180003f5f  add     rsp, 70h
0x180003f63  pop     rbp
0x180003f64  retn
```
