# GetRegistryValue(ushort *,ulong *,_RAREGHIVE)

- ea: `0x140015600`
- end: `0x1400156c2`
- name: `?GetRegistryValue@@YAJPEAGPEAKW4_RAREGHIVE@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000dd80`

## callees

- `0x140015600`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140015654`
- `ADVAPI32!RegOpenKeyExW` at `0x140015654`
- `ADVAPI32!RegCloseKey` at `0x1400156b2`
- `ADVAPI32!RegCloseKey` at `0x1400156b2`
- `ADVAPI32!RegQueryValueExW` at `0x140015698`
- `ADVAPI32!RegQueryValueExW` at `0x140015698`

## string_xrefs

- `0x14001562a`: `Software\policies\Microsoft\Windows NT\Terminal Services`

## pseudocode

```c
__int64 __fastcall GetRegistryValue(__int64 a1, _DWORD *a2)
{
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  bool v5; // cc
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  int v9; // [rsp+64h] [rbp+24h]
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  v9 = HIDWORD(a1);
  hKey = 0;
  cbData = 0;
  Data = 0;
  Type = 4;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\policies\\Microsoft\\Windows NT\\Terminal Services", 0, 1u, &hKey);
  v4 = v3;
  v5 = v3 <= 0;
  if ( v3
    || (cbData = 4,
        v3 = RegQueryValueExW(hKey, L"fAllowUnsolicited", 0, &Type, (LPBYTE)&Data, &cbData),
        v4 = v3,
        v5 = v3 <= 0,
        v3) )
  {
    if ( !v5 )
      v4 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    *a2 = Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x140015600  mov     [rsp-18h+cbData], r8d
0x140015605  mov     qword ptr [rsp-18h+Data], rcx
0x14001560a  push    rbp
0x14001560b  push    rbx
0x14001560c  push    rdi
0x14001560d  mov     rbp, rsp
0x140015610  sub     rsp, 40h
0x140015614  mov     rdi, rdx
0x140015617  mov     [rbp+hKey], 0
0x14001561f  lea     rax, [rbp+hKey]
0x140015623  mov     [rbp+cbData], 0
0x14001562a  lea     rdx, aSoftwarePolici_0; "Software\\policies\\Microsoft\\Windows "...
0x140015631  mov     [rsp+40h+phkResult], rax; phkResult
0x140015636  mov     r9d, 1; samDesired
0x14001563c  mov     [rbp+Data], 0
0x140015643  xor     r8d, r8d; ulOptions
0x140015646  mov     [rbp+Type], 4
0x14001564d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140015654  call    cs:__imp_RegOpenKeyExW
0x14001565a  mov     ebx, eax
0x14001565c  test    eax, eax
0x14001565e  jz      short loc_14001566D
0x140015660  jle     short loc_1400156A9
0x140015662  movzx   ebx, ax
0x140015665  or      ebx, 80070000h
0x14001566b  jmp     short loc_1400156A9
0x14001566d  mov     rcx, [rbp+hKey]; hKey
0x140015671  lea     rax, [rbp+cbData]
0x140015675  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14001567a  lea     r9, [rbp+Type]; lpType
0x14001567e  lea     rax, [rbp+Data]
0x140015682  mov     [rbp+cbData], 4
0x140015689  xor     r8d, r8d; lpReserved
0x14001568c  mov     [rsp+40h+phkResult], rax; lpData
0x140015691  lea     rdx, aFallowunsolici; "fAllowUnsolicited"
0x140015698  call    cs:__imp_RegQueryValueExW
0x14001569e  mov     ebx, eax
0x1400156a0  test    eax, eax
0x1400156a2  jnz     short loc_140015660
0x1400156a4  mov     ecx, [rbp+Data]
0x1400156a7  mov     [rdi], ecx
0x1400156a9  mov     rcx, [rbp+hKey]; hKey
0x1400156ad  test    rcx, rcx
0x1400156b0  jz      short loc_1400156B8
0x1400156b2  call    cs:__imp_RegCloseKey
0x1400156b8  mov     eax, ebx
0x1400156ba  add     rsp, 40h
0x1400156be  pop     rdi
0x1400156bf  pop     rbx
0x1400156c0  pop     rbp
0x1400156c1  retn
```
