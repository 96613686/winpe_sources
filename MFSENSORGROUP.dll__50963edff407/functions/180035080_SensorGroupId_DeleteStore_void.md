# SensorGroupId::DeleteStore(void)

- ea: `0x180035080`
- end: `0x18003514c`
- name: `?DeleteStore@SensorGroupId@@UEAAXXZ`
- size: `204`
- prototype: `void __fastcall(SensorGroupId *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000c8b0`
- `0x18000ec30`
- `0x180035080`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035145`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035091`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035091`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800350cd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800350cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035131`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035131`

## pseudocode

```c
void __fastcall SensorGroupId::DeleteStore(SensorGroupId *this)
{
  LSTATUS v2; // eax
  char v3; // cl
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  hKey = 0;
  if ( (int)OpenSensorGroupRegistryKey(0, 131334, 0, &hKey) >= 0 )
  {
    v2 = RegDeleteKeyExW(hKey, *((LPCWSTR *)this + 140), 0x100u, 0);
    v3 = v2;
    if ( v2 )
    {
      if ( v2 > 0 )
        v3 = v2;
    }
    else
    {
      v3 = 0;
    }
    if ( (unsigned __int8)byte_18008D62D >= 8u )
      WPP_SF_qDS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        90,
        (unsigned int)&WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
        (_DWORD)this - 8,
        v3,
        *((_QWORD *)this + 140));
  }
  if ( hKey )
    RegCloseKey(hKey);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180035080  mov     [rsp+arg_8], rsi
0x180035085  push    rdi
0x180035086  sub     rsp, 30h
0x18003508a  mov     rdi, rcx
0x18003508d  add     rcx, 10h; lpCriticalSection
0x180035091  call    cs:__imp_EnterCriticalSection
0x180035097  lea     r9, [rsp+38h+hKey]; HKEY *
0x18003509c  mov     [rsp+38h+hKey], 0
0x1800350a5  xor     r8d, r8d; bool *
0x1800350a8  mov     edx, 20106h; unsigned int
0x1800350ad  xor     ecx, ecx; unsigned __int16 *
0x1800350af  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x1800350b4  test    eax, eax
0x1800350b6  js      short loc_180035124
0x1800350b8  mov     rdx, [rdi+460h]; lpSubKey
0x1800350bf  xor     r9d, r9d; Reserved
0x1800350c2  mov     rcx, [rsp+38h+hKey]; hKey
0x1800350c7  mov     r8d, 100h; samDesired
0x1800350cd  call    cs:__imp_RegDeleteKeyExW
0x1800350d3  mov     ecx, eax
0x1800350d5  test    eax, eax
0x1800350d7  jz      short loc_1800350E6
0x1800350d9  jle     short loc_1800350E8
0x1800350db  movzx   ecx, ax
0x1800350de  or      ecx, 80070000h
0x1800350e4  jmp     short loc_1800350E8
0x1800350e6  xor     ecx, ecx
0x1800350e8  cmp     cs:byte_18008D62D, 8
0x1800350ef  jb      short loc_180035124
0x1800350f1  mov     rax, [rdi+460h]
0x1800350f8  lea     r9, [rdi-8]
0x1800350fc  mov     [rsp+38h+var_10], rax
0x180035101  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x180035108  mov     [rsp+38h+var_18], ecx
0x18003510c  mov     edx, 5Ah ; 'Z'
0x180035111  mov     rcx, cs:WPP_GLOBAL_Control
0x180035118  mov     rcx, [rcx+0D8h]
0x18003511f  call    WPP_SF_qDS
0x180035124  cmp     [rsp+38h+hKey], 0
0x18003512a  jz      short loc_180035137
0x18003512c  mov     rcx, [rsp+38h+hKey]; hKey
0x180035131  call    cs:__imp_RegCloseKey
0x180035137  lea     rcx, [rdi+10h]
0x18003513b  mov     rsi, [rsp+38h+arg_8]
0x180035140  add     rsp, 30h
0x180035144  pop     rdi
0x180035145  jmp     cs:__imp_LeaveCriticalSection
```
