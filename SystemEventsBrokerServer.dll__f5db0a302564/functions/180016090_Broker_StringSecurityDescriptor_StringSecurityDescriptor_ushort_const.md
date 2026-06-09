# Broker::StringSecurityDescriptor::StringSecurityDescriptor(ushort const *)

- ea: `0x180016090`
- end: `0x180016141`
- name: `??0StringSecurityDescriptor@Broker@@QEAA@PEBG@Z`
- size: `177`
- prototype: `PSECURITY_DESCRIPTOR *__fastcall(PSECURITY_DESCRIPTOR *SecurityDescriptor, LPCWSTR StringSecurityDescriptor)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020eb4`
- `0x180020fc4`

## callees

- `0x1800030e0`
- `0x180016090`
- `0x18001732c`
- `0x1800195e0`
- `0x18001d9ac`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800160b6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800160b6`

## pseudocode

```c
PSECURITY_DESCRIPTOR *__fastcall Broker::StringSecurityDescriptor::StringSecurityDescriptor(
        PSECURITY_DESCRIPTOR *SecurityDescriptor,
        LPCWSTR StringSecurityDescriptor)
{
  _BYTE v4[24]; // [rsp+20h] [rbp-58h] BYREF
  int v5; // [rsp+38h] [rbp-40h]
  unsigned int v6; // [rsp+40h] [rbp-38h]
  _QWORD pExceptionObject[3]; // [rsp+48h] [rbp-30h] BYREF
  int v8; // [rsp+60h] [rbp-18h]
  unsigned int v9; // [rsp+68h] [rbp-10h]
  ULONG v10; // [rsp+80h] [rbp+8h] BYREF

  v10 = 0;
  *SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, SecurityDescriptor, &v10) )
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
0x180016090  mov     r11, rsp
0x180016093  push    rbx
0x180016094  sub     rsp, 70h
0x180016098  mov     rax, rdx
0x18001609b  mov     rbx, rcx
0x18001609e  xor     ecx, ecx
0x1800160a0  mov     [r11+8], ecx
0x1800160a4  mov     [rbx], rcx
0x1800160a7  lea     r9, [r11+8]; SecurityDescriptorSize
0x1800160ab  mov     r8, rbx; SecurityDescriptor
0x1800160ae  mov     edx, 1; StringSDRevision
0x1800160b3  mov     rcx, rax; StringSecurityDescriptor
0x1800160b6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800160bc  test    eax, eax
0x1800160be  jz      short loc_1800160C9
0x1800160c0  mov     rax, rbx
0x1800160c3  add     rsp, 70h
0x1800160c7  pop     rbx
0x1800160c8  retn
0x1800160c9  lea     rcx, [rsp+78h+var_58]; this
0x1800160ce  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x1800160d3  nop
0x1800160d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160db  test    dword ptr [rcx+1Ch], 400h
0x1800160e2  jz      short loc_180016104
0x1800160e4  cmp     byte ptr [rcx+19h], 2
0x1800160e8  jb      short loc_180016104
0x1800160ea  mov     edx, 0Ah
0x1800160ef  mov     r9d, [rsp+78h+var_38]
0x1800160f4  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x1800160fb  mov     rcx, [rcx+10h]
0x1800160ff  call    WPP_SF_d
0x180016104  lea     rdx, [rsp+78h+var_58]; struct std::exception *
0x180016109  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18001610e  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180016113  mov     eax, [rsp+78h+var_40]
0x180016117  mov     [rsp+78h+var_18], eax
0x18001611b  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180016122  mov     [rsp+78h+pExceptionObject], rax
0x180016127  mov     eax, [rsp+78h+var_38]
0x18001612b  mov     [rsp+78h+var_10], eax
0x18001612f  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180016136  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001613b  call    _CxxThrowException_0
```
