# Broker::StringSecurityDescriptor::StringSecurityDescriptor(ushort const *)

- ea: `0x180010fd8`
- end: `0x180011097`
- name: `??0StringSecurityDescriptor@Broker@@QEAA@PEBG@Z`
- size: `191`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *SecurityDescriptor, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010c54`
- `0x180010d68`

## callees

- `0x180009e94`
- `0x180010fd8`
- `0x1800139f8`
- `0x180014a40`
- `0x1800165da`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001100e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001100e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PSECURITY_DESCRIPTOR *__fastcall Broker::StringSecurityDescriptor::StringSecurityDescriptor(
        PSECURITY_DESCRIPTOR *SecurityDescriptor,
        const unsigned __int16 *a2)
{
  _BYTE v4[24]; // [rsp+20h] [rbp-50h] BYREF
  int v5; // [rsp+38h] [rbp-38h]
  unsigned int v6; // [rsp+40h] [rbp-30h]
  _QWORD pExceptionObject[3]; // [rsp+48h] [rbp-28h] BYREF
  int v8; // [rsp+60h] [rbp-10h]
  unsigned int v9; // [rsp+68h] [rbp-8h]
  ULONG SecurityDescriptorSize; // [rsp+88h] [rbp+18h] BYREF
  int v11; // [rsp+8Ch] [rbp+1Ch]

  v11 = HIDWORD(a2);
  SecurityDescriptorSize = 0;
  *SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GR;;;SY)(A;;GR;;;S-1-5-80-1988685059-1921232356-378231328-2704142597-890457928)(A;;GR;;;S-1-5-80-4125092"
           "361-1567024937-842823819-2091237918-836075745)(A;;GR;;;WD)(A;;GR;;;AC)",
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
0x180010fd8  mov     [rsp-8+arg_0], rbx
0x180010fdd  mov     qword ptr [rsp-8+SecurityDescriptorSize], rdx
0x180010fe2  push    rbp
0x180010fe3  mov     rbp, rsp
0x180010fe6  sub     rsp, 70h
0x180010fea  mov     rbx, rcx
0x180010fed  mov     [rbp+SecurityDescriptorSize], 0
0x180010ff4  mov     qword ptr [rcx], 0
0x180010ffb  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x180010fff  mov     r8, rcx; SecurityDescriptor
0x180011002  mov     edx, 1; StringSDRevision
0x180011007  lea     rcx, StringSecurityDescriptor; "D:(A;;GR;;;SY)(A;;GR;;;S-1-5-80-1988685"...
0x18001100e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180011014  test    eax, eax
0x180011016  jnz     short loc_180011086
0x180011018  lea     rcx, [rbp+var_50]; this
0x18001101c  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180011021  nop
0x180011022  mov     rcx, cs:WPP_GLOBAL_Control
0x180011029  test    dword ptr [rcx+1Ch], 400h
0x180011030  jz      short loc_180011051
0x180011032  cmp     byte ptr [rcx+19h], 2
0x180011036  jb      short loc_180011051
0x180011038  mov     edx, 0Ah
0x18001103d  mov     r9d, [rbp+var_30]
0x180011041  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x180011048  mov     rcx, [rcx+10h]
0x18001104c  call    WPP_SF_d
0x180011051  lea     rdx, [rbp+var_50]; struct std::exception *
0x180011055  lea     rcx, [rbp+pExceptionObject]; this
0x180011059  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x18001105e  mov     eax, [rbp+var_38]
0x180011061  mov     [rbp+var_10], eax
0x180011064  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001106b  mov     [rbp+pExceptionObject], rax
0x18001106f  mov     eax, [rbp+var_30]
0x180011072  mov     [rbp+var_8], eax
0x180011075  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001107c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011080  call    _CxxThrowException_0
0x180011086  mov     rax, rbx
0x180011089  mov     rbx, [rsp+70h+arg_0]
0x180011091  add     rsp, 70h
0x180011095  pop     rbp
0x180011096  retn
```
