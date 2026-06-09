# RegSetKeyValueWithSSDL(ushort const *,HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)

- ea: `0x18001747c`
- end: `0x180017534`
- name: `?RegSetKeyValueWithSSDL@@YAKPEBGPEAUHKEY__@@00KPEBXK@Z`
- size: `184`
- prototype: `unsigned int(const unsigned __int16 *, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018954`
- `0x18001899c`
- `0x1800390a0`

## callees

- `0x18001747c`
- `0x180019fec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017518`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017518`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800174b5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800174b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001750d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001750d`

## pseudocode

```c
__int64 __fastcall RegSetKeyValueWithSSDL(
        const unsigned __int16 *a1,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD a5,
        BYTE *a6,
        DWORD a7)
{
  HKEY v9; // rcx
  unsigned int LastError; // eax
  unsigned int v11; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-20h] BYREF
  _SECURITY_ATTRIBUTES v14; // [rsp+48h] [rbp-18h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+78h] [rbp+18h] BYREF
  int v16; // [rsp+7Ch] [rbp+1Ch]

  v16 = HIDWORD(a2);
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(a1, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
  {
    v14.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&v14.nLength = 24;
    *(_QWORD *)&v14.bInheritHandle = 0;
    LastError = _RegSetKeyValueWithSDDL(v9, a3, a4, a5, a6, a7, &v14);
  }
  else
  {
    LastError = GetLastError();
  }
  v11 = LastError;
  if ( LocalFree(SecurityDescriptor) )
    return GetLastError();
  return v11;
}

```

## disassembly

```asm
0x18001747c  mov     [rsp-8+arg_0], rbx
0x180017481  mov     [rsp-8+arg_10], rdi
0x180017486  mov     qword ptr [rsp-8+SecurityDescriptorSize], rdx
0x18001748b  push    rbp
0x18001748c  mov     rbp, rsp
0x18001748f  sub     rsp, 60h
0x180017493  mov     rbx, r9
0x180017496  mov     [rbp+SecurityDescriptor], 0
0x18001749e  mov     rdi, r8
0x1800174a1  mov     [rbp+SecurityDescriptorSize], 0
0x1800174a8  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800174ac  mov     edx, 1; StringSDRevision
0x1800174b1  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800174b5  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800174bb  test    eax, eax
0x1800174bd  jz      short loc_180017501
0x1800174bf  mov     rax, [rbp+SecurityDescriptor]
0x1800174c3  mov     r8, rbx; unsigned __int16 *
0x1800174c6  mov     r9d, [rbp+arg_20]; unsigned int
0x1800174ca  mov     rdx, rdi; unsigned __int16 *
0x1800174cd  mov     [rbp+var_18.lpSecurityDescriptor], rax
0x1800174d1  lea     rax, [rbp+var_18]
0x1800174d5  mov     [rsp+60h+var_30], rax; struct _SECURITY_ATTRIBUTES *
0x1800174da  mov     eax, [rbp+arg_30]
0x1800174dd  mov     [rsp+60h+var_38], eax; unsigned int
0x1800174e1  mov     rax, [rbp+arg_28]
0x1800174e5  mov     [rsp+60h+var_40], rax; void *
0x1800174ea  mov     qword ptr [rbp+var_18.nLength], 18h
0x1800174f2  mov     qword ptr [rbp+var_18.bInheritHandle], 0
0x1800174fa  call    ?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z; _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)
0x1800174ff  jmp     short loc_180017507
0x180017501  call    cs:__imp_GetLastError
0x180017507  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18001750b  mov     ebx, eax
0x18001750d  call    cs:__imp_LocalFree
0x180017513  test    rax, rax
0x180017516  jz      short loc_180017520
0x180017518  call    cs:__imp_GetLastError
0x18001751e  mov     ebx, eax
0x180017520  lea     r11, [rsp+60h+var_s0]
0x180017525  mov     eax, ebx
0x180017527  mov     rbx, [r11+10h]
0x18001752b  mov     rdi, [r11+20h]
0x18001752f  mov     rsp, r11
0x180017532  pop     rbp
0x180017533  retn
```
