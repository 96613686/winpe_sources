# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x18001ca98`
- end: `0x18001cc1a`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `386`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016fe8`
- `0x1800346c0`
- `0x180057248`

## callees

- `0x18001ca98`
- `0x180037780`
- `0x1800386f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cb1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cb1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cbff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cbff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cc0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cc0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cbb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cbb2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cb0e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cbe5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cb0e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cbe5`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, DWORD a4, void **a5)
{
  LSTATUS ValueW; // ebx
  int v8; // esi
  void *pvData; // rax
  LSTATUS v11; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  phkResult = a1;
  if ( a2 && *a2 )
  {
    v8 = 1;
    v11 = RegOpenKeyExW(a1, a2, 0, 1u, &phkResult);
    a1 = phkResult;
    ValueW = v11;
  }
  else
  {
    ValueW = 0;
    v8 = 0;
  }
  if ( ValueW )
    goto LABEL_12;
  pcbData = 256;
  ValueW = RegGetValueW(a1, 0, a3, a4, 0, Src, &pcbData);
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( ValueW )
      {
        if ( RegGetValueW(phkResult, 0, a3, a4, 0, pvData, &pcbData) )
        {
          ValueW = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          ValueW = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      ValueW = 14;
    }
  }
  if ( v8 )
    RegCloseKey(phkResult);
  if ( ValueW )
  {
LABEL_12:
    *a5 = 0;
    if ( ValueW > 0 )
      return (unsigned __int16)ValueW | 0x80070000;
  }
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x18001ca98  push    rbp
0x18001ca9a  push    rbx
0x18001ca9b  push    rsi
0x18001ca9c  push    rdi
0x18001ca9d  push    r12
0x18001ca9f  push    r14
0x18001caa1  push    r15
0x18001caa3  lea     rbp, [rsp-60h]
0x18001caa8  sub     rsp, 160h
0x18001caaf  mov     rax, cs:__security_cookie
0x18001cab6  xor     rax, rsp
0x18001cab9  mov     [rbp+90h+var_40], rax
0x18001cabd  mov     rdi, [rbp+90h+arg_20]
0x18001cac4  xor     r12d, r12d
0x18001cac7  mov     [rsp+190h+phkResult], rcx
0x18001cacc  mov     r15d, r9d
0x18001cacf  mov     r14, r8
0x18001cad2  test    rdx, rdx
0x18001cad5  jnz     loc_18001CB93
0x18001cadb  mov     ebx, r12d
0x18001cade  mov     esi, r12d
0x18001cae1  test    ebx, ebx
0x18001cae3  jnz     short loc_18001CB5C
0x18001cae5  lea     rax, [rsp+190h+var_150]
0x18001caea  mov     [rsp+190h+var_150], 100h
0x18001caf2  mov     [rsp+190h+pcbData], rax; pcbData
0x18001caf7  mov     r9d, r15d; dwFlags
0x18001cafa  lea     rax, [rsp+190h+Src]
0x18001caff  mov     r8, r14; lpValue
0x18001cb02  mov     [rsp+190h+pvData], rax; pvData
0x18001cb07  xor     edx, edx; lpSubKey
0x18001cb09  mov     [rsp+190h+pdwType], r12; pdwType
0x18001cb0e  call    cs:__imp_RegGetValueW
0x18001cb14  mov     ebx, eax
0x18001cb16  test    eax, eax
0x18001cb18  jnz     short loc_18001CB48
0x18001cb1a  mov     ecx, [rsp+190h+var_150]; cb
0x18001cb1e  call    cs:__imp_CoTaskMemAlloc
0x18001cb24  mov     [rdi], rax
0x18001cb27  test    rax, rax
0x18001cb2a  jz      short loc_18001CB8C
0x18001cb2c  test    ebx, ebx
0x18001cb2e  jnz     loc_18001CBC4
0x18001cb34  mov     r8d, [rsp+190h+var_150]; Size
0x18001cb39  lea     rdx, [rsp+190h+Src]; Src
0x18001cb3e  mov     rcx, rax; void *
0x18001cb41  call    memcpy_0
0x18001cb46  jmp     short loc_18001CB50
0x18001cb48  cmp     ebx, 0EAh
0x18001cb4e  jz      short loc_18001CB1A
0x18001cb50  test    esi, esi
0x18001cb52  jnz     loc_18001CC0A
0x18001cb58  test    ebx, ebx
0x18001cb5a  jz      short loc_18001CB6C
0x18001cb5c  mov     [rdi], r12
0x18001cb5f  test    ebx, ebx
0x18001cb61  jle     short loc_18001CB6C
0x18001cb63  movzx   ebx, bx
0x18001cb66  or      ebx, 80070000h
0x18001cb6c  mov     eax, ebx
0x18001cb6e  mov     rcx, [rbp+90h+var_40]
0x18001cb72  xor     rcx, rsp; StackCookie
0x18001cb75  call    __security_check_cookie
0x18001cb7a  add     rsp, 160h
0x18001cb81  pop     r15
0x18001cb83  pop     r14
0x18001cb85  pop     r12
0x18001cb87  pop     rdi
0x18001cb88  pop     rsi
0x18001cb89  pop     rbx
0x18001cb8a  pop     rbp
0x18001cb8b  retn
0x18001cb8c  mov     ebx, 0Eh
0x18001cb91  jmp     short loc_18001CB50
0x18001cb93  cmp     [rdx], r12w
0x18001cb97  jz      loc_18001CADB
0x18001cb9d  lea     rax, [rsp+190h+phkResult]
0x18001cba2  mov     esi, 1
0x18001cba7  mov     r9d, esi; samDesired
0x18001cbaa  mov     [rsp+190h+pdwType], rax; phkResult
0x18001cbaf  xor     r8d, r8d; ulOptions
0x18001cbb2  call    cs:__imp_RegOpenKeyExW
0x18001cbb8  mov     rcx, [rsp+190h+phkResult]
0x18001cbbd  mov     ebx, eax
0x18001cbbf  jmp     loc_18001CAE1
0x18001cbc4  lea     rcx, [rsp+190h+var_150]
0x18001cbc9  mov     r9d, r15d; dwFlags
0x18001cbcc  mov     [rsp+190h+pcbData], rcx; pcbData
0x18001cbd1  mov     r8, r14; lpValue
0x18001cbd4  mov     rcx, [rsp+190h+phkResult]; hkey
0x18001cbd9  xor     edx, edx; lpSubKey
0x18001cbdb  mov     [rsp+190h+pvData], rax; pvData
0x18001cbe0  mov     [rsp+190h+pdwType], r12; pdwType
0x18001cbe5  call    cs:__imp_RegGetValueW
0x18001cbeb  test    eax, eax
0x18001cbed  jnz     short loc_18001CBF7
0x18001cbef  mov     ebx, r12d
0x18001cbf2  jmp     loc_18001CB50
0x18001cbf7  mov     rcx, [rdi]; pv
0x18001cbfa  mov     ebx, 3EBh
0x18001cbff  call    cs:__imp_CoTaskMemFree
0x18001cc05  jmp     loc_18001CB50
0x18001cc0a  mov     rcx, [rsp+190h+phkResult]; hKey
0x18001cc0f  call    cs:__imp_RegCloseKey
0x18001cc15  jmp     loc_18001CB58
```
