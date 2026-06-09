# RegSetKeyValueWithSSDL(ushort const *,HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)

- ea: `0x180090758`
- end: `0x1800907ed`
- name: `?RegSetKeyValueWithSSDL@@YAKPEBGPEAUHKEY__@@00KPEBXK@Z`
- size: `149`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, HKEY, const unsigned __int16 *, const unsigned __int16 *, ULONG SecurityDescriptorSize, BYTE *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180090a20`

## callees

- `0x180090758`
- `0x180090918`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800907c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800907d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800907c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800907d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800907cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800907cd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180090786`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180090786`

## pseudocode

```c
__int64 __fastcall RegSetKeyValueWithSSDL(
        const unsigned __int16 *a1,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        ULONG SecurityDescriptorSize,
        BYTE *lpData)
{
  const unsigned __int16 *v6; // rdx
  HKEY v7; // rcx
  const unsigned __int16 *v8; // r8
  __int64 v9; // r9
  unsigned int LastError; // eax
  unsigned int v11; // ebx
  unsigned int v13; // [rsp+28h] [rbp-38h]
  _SECURITY_ATTRIBUTES v14; // [rsp+40h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+88h] [rbp+28h] BYREF

  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(a1, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
  {
    v14.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&v14.nLength = 24;
    *(_QWORD *)&v14.bInheritHandle = 0;
    LastError = _RegSetKeyValueWithSDDL(v7, v6, v8, v9, lpData, v13, &v14);
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
0x180090758  mov     [rsp-8+arg_0], rbx
0x18009075d  mov     [rsp-8+SecurityDescriptor], r9
0x180090762  push    rbp
0x180090763  mov     rbp, rsp
0x180090766  sub     rsp, 60h
0x18009076a  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x18009076e  mov     [rbp+SecurityDescriptor], 0
0x180090776  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18009077a  mov     [rbp+SecurityDescriptorSize], 0
0x180090781  mov     edx, 1; StringSDRevision
0x180090786  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18009078c  test    eax, eax
0x18009078e  jz      short loc_1800907C1
0x180090790  mov     rax, [rbp+SecurityDescriptor]
0x180090794  mov     [rbp+var_20.lpSecurityDescriptor], rax
0x180090798  lea     rax, [rbp+var_20]
0x18009079c  mov     [rsp+60h+var_30], rax; struct _SECURITY_ATTRIBUTES *
0x1800907a1  mov     rax, [rbp+arg_28]
0x1800907a5  mov     [rsp+60h+lpData], rax; lpData
0x1800907aa  mov     qword ptr [rbp+var_20.nLength], 18h
0x1800907b2  mov     qword ptr [rbp+var_20.bInheritHandle], 0
0x1800907ba  call    ?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z; _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)
0x1800907bf  jmp     short loc_1800907C7
0x1800907c1  call    cs:__imp_GetLastError
0x1800907c7  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800907cb  mov     ebx, eax
0x1800907cd  call    cs:__imp_LocalFree
0x1800907d3  test    rax, rax
0x1800907d6  jz      short loc_1800907E0
0x1800907d8  call    cs:__imp_GetLastError
0x1800907de  mov     ebx, eax
0x1800907e0  mov     eax, ebx
0x1800907e2  mov     rbx, [rsp+60h+arg_0]
0x1800907e7  add     rsp, 60h
0x1800907eb  pop     rbp
0x1800907ec  retn
```
