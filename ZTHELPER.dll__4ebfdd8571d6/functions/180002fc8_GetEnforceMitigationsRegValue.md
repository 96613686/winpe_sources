# GetEnforceMitigationsRegValue

- ea: `0x180002fc8`
- end: `0x18000313d`
- name: `GetEnforceMitigationsRegValue`
- size: `373`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180003150`

## callees

- `0x180002fc8`
- `0x18000f670`
- `0x180015008`
- `0x180015094`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003086`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003086`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003103`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003103`

## string_xrefs

- `0x180003038`: `SYSTEM\CurrentControlSet\Services\ZTHELPER`

## pseudocode

```c
__int64 __fastcall GetEnforceMitigationsRegValue(_DWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // eax
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  unsigned int v8; // r8d
  unsigned int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  Data = 0;
  hKey = 0;
  Type = 4;
  cbData = 4;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_q(1026, 18, WPP_fd30cb189484364f2633d135959507bb_Traceguids, a1);
  if ( a1 )
    *a1 = 0;
  v5 = CreatePersistedRegistryKeyHelper(
         (__int64)L"ZTHELPER",
         (__int64)L"SYSTEM\\CurrentControlSet\\Services\\ZTHELPER",
         (__int64)L"Parameters",
         a4,
         0x20019u,
         0,
         0,
         &hKey);
  v6 = v5;
  if ( v5 )
  {
    if ( (xmmword_18001F260 & 4) != 0 )
      WPP_SF_d(1026, 19, WPP_fd30cb189484364f2633d135959507bb_Traceguids, v5);
  }
  else
  {
    v7 = RegQueryValueExW(hKey, L"EnforceMitigations", 0, &Type, (LPBYTE)&Data, &cbData);
    v6 = v7;
    if ( v7 == 2 )
    {
      v8 = 0;
      Data = 0;
      v6 = 0;
    }
    else
    {
      if ( v7 )
        goto LABEL_15;
      v8 = Data;
    }
    if ( (xmmword_18001F260 & 4) != 0 )
    {
      WPP_SF_d(1026, 20, WPP_fd30cb189484364f2633d135959507bb_Traceguids, v8);
      v8 = Data;
    }
    *a1 = v8 != 0;
  }
LABEL_15:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 21, WPP_fd30cb189484364f2633d135959507bb_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180002fc8  push    rbp
0x180002fca  push    rbx
0x180002fcb  push    rdi
0x180002fcc  mov     rbp, rsp
0x180002fcf  sub     rsp, 40h
0x180002fd3  mov     rdi, rcx
0x180002fd6  mov     [rbp+Data], 0
0x180002fdd  mov     [rbp+hKey], 0
0x180002fe5  mov     [rbp+Type], 4
0x180002fec  mov     [rbp+cbData], 4
0x180002ff3  test    byte ptr cs:xmmword_18001F260, 4
0x180002ffa  jz      short loc_180003015
0x180002ffc  mov     edx, 12h
0x180003001  lea     r8, WPP_fd30cb189484364f2633d135959507bb_Traceguids
0x180003008  mov     ecx, 402h
0x18000300d  mov     r9, rdi
0x180003010  call    WPP_SF_q
0x180003015  test    rdi, rdi
0x180003018  jz      short loc_180003020
0x18000301a  mov     dword ptr [rdi], 0
0x180003020  lea     rax, [rbp+hKey]
0x180003024  mov     [rsp+40h+var_8], rax
0x180003029  lea     r8, aParameters; "Parameters"
0x180003030  mov     [rsp+40h+var_10], 0
0x180003038  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\ZT"...
0x18000303f  mov     [rsp+40h+lpcbData], 0
0x180003048  lea     rcx, ServiceName; "ZTHELPER"
0x18000304f  mov     dword ptr [rsp+40h+lpData], 20019h
0x180003057  call    CreatePersistedRegistryKeyHelper
0x18000305c  mov     ebx, eax
0x18000305e  test    eax, eax
0x180003060  jnz     short loc_1800030D8
0x180003062  mov     rcx, [rbp+hKey]; hKey
0x180003066  lea     rax, [rbp+cbData]
0x18000306a  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000306f  lea     r9, [rbp+Type]; lpType
0x180003073  lea     rax, [rbp+Data]
0x180003077  xor     r8d, r8d; lpReserved
0x18000307a  lea     rdx, ValueName; "EnforceMitigations"
0x180003081  mov     [rsp+40h+lpData], rax; lpData
0x180003086  call    cs:__imp_RegQueryValueExW
0x18000308c  mov     ebx, eax
0x18000308e  cmp     eax, 2
0x180003091  jnz     short loc_18000309E
0x180003093  xor     r8d, r8d
0x180003096  mov     [rbp+Data], r8d
0x18000309a  xor     ebx, ebx
0x18000309c  jmp     short loc_1800030A6
0x18000309e  test    eax, eax
0x1800030a0  jnz     short loc_1800030FA
0x1800030a2  mov     r8d, [rbp+Data]
0x1800030a6  test    byte ptr cs:xmmword_18001F260, 4
0x1800030ad  jz      short loc_1800030CC
0x1800030af  mov     r9d, r8d
0x1800030b2  mov     edx, 14h
0x1800030b7  lea     r8, WPP_fd30cb189484364f2633d135959507bb_Traceguids
0x1800030be  mov     ecx, 402h
0x1800030c3  call    WPP_SF_d
0x1800030c8  mov     r8d, [rbp+Data]
0x1800030cc  xor     eax, eax
0x1800030ce  test    r8d, r8d
0x1800030d1  setnz   al
0x1800030d4  mov     [rdi], eax
0x1800030d6  jmp     short loc_1800030FA
0x1800030d8  test    byte ptr cs:xmmword_18001F260, 4
0x1800030df  jz      short loc_1800030FA
0x1800030e1  mov     edx, 13h
0x1800030e6  lea     r8, WPP_fd30cb189484364f2633d135959507bb_Traceguids
0x1800030ed  mov     ecx, 402h
0x1800030f2  mov     r9d, eax
0x1800030f5  call    WPP_SF_d
0x1800030fa  mov     rcx, [rbp+hKey]; hKey
0x1800030fe  test    rcx, rcx
0x180003101  jz      short loc_180003111
0x180003103  call    cs:__imp_RegCloseKey
0x180003109  mov     [rbp+hKey], 0
0x180003111  test    byte ptr cs:xmmword_18001F260, 4
0x180003118  jz      short loc_180003133
0x18000311a  mov     edx, 15h
0x18000311f  lea     r8, WPP_fd30cb189484364f2633d135959507bb_Traceguids
0x180003126  mov     ecx, 402h
0x18000312b  mov     r9d, ebx
0x18000312e  call    WPP_SF_d
0x180003133  mov     eax, ebx
0x180003135  add     rsp, 40h
0x180003139  pop     rdi
0x18000313a  pop     rbx
0x18000313b  pop     rbp
0x18000313c  retn
```
