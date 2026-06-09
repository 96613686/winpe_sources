# FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)

- ea: `0x1800261a8`
- end: `0x180026314`
- name: `?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z`
- size: `364`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, DWORD, unsigned int *, unsigned int *Type)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006230`
- `0x18000694c`
- `0x18001ce24`
- `0x1800260a0`
- `0x180026170`
- `0x180036284`
- `0x180049b00`
- `0x18004fbb0`
- `0x1800544c4`
- `0x1800553d8`

## callees

- `0x1800261a8`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x180026213`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x180026213`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180026284`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180026284`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026244`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800262c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026244`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800262c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026268`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026268`

## pseudocode

```c
__int64 __fastcall FSGetDeviceInterfaceRegistryEntry2(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        DWORD a4,
        unsigned int *a5,
        unsigned int *Type)
{
  unsigned int *v9; // rdi
  CONFIGRET v10; // eax
  LSTATUS v11; // eax
  signed int v12; // ebx
  signed int v14; // eax
  DWORD v15; // eax
  LSTATUS v16; // eax
  HKEY phkDeviceInterface; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+38h] BYREF

  cbData = 0;
  LODWORD(Type) = 0;
  if ( !a1 || !a2 )
    return (unsigned int)-2147024809;
  v9 = a5;
  if ( !a5 )
    return (unsigned int)-2147467261;
  *a5 = 0;
  phkDeviceInterface = 0;
  v10 = CM_Open_Device_Interface_KeyW(a1, 0x20019u, 1u, &phkDeviceInterface, 0);
  if ( !v10 )
    goto LABEL_8;
  v14 = CM_MapCrToWin32Err(v10, 0xDu);
  v12 = v14;
  if ( v14 > 0 )
    v12 = (unsigned __int16)v14 | 0x80070000;
  if ( v12 >= 0 )
  {
LABEL_8:
    cbData = 0;
    v11 = RegQueryValueExW(phkDeviceInterface, a2, 0, (LPDWORD)&Type, 0, &cbData);
    v12 = v11;
    if ( !v11 )
      goto LABEL_16;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    if ( v12 >= 0 )
    {
LABEL_16:
      v15 = cbData;
      *v9 = cbData;
      if ( v15 > a4 )
      {
        v12 = -1072860816;
      }
      else
      {
        cbData = a4;
        v16 = RegQueryValueExW(phkDeviceInterface, a2, 0, (LPDWORD)&Type, a3, &cbData);
        v12 = v16;
        if ( v16 )
        {
          if ( v16 > 0 )
            v12 = (unsigned __int16)v16 | 0x80070000;
          if ( v12 < 0 )
            goto LABEL_9;
        }
        else
        {
          v12 = 0;
        }
        *v9 = cbData;
      }
    }
  }
LABEL_9:
  if ( phkDeviceInterface )
    RegCloseKey(phkDeviceInterface);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800261a8  push    rbp
0x1800261aa  push    rbx
0x1800261ab  push    rsi
0x1800261ac  push    rdi
0x1800261ad  push    r14
0x1800261af  push    r15
0x1800261b1  mov     rbp, rsp
0x1800261b4  sub     rsp, 48h
0x1800261b8  mov     [rbp+cbData], 0
0x1800261bf  mov     r14d, r9d
0x1800261c2  mov     [rbp+Type], 0
0x1800261c9  mov     r15, r8
0x1800261cc  mov     rsi, rdx
0x1800261cf  test    rcx, rcx
0x1800261d2  jz      loc_180026300
0x1800261d8  test    rdx, rdx
0x1800261db  jz      loc_180026300
0x1800261e1  mov     rdi, [rbp+arg_20]
0x1800261e5  test    rdi, rdi
0x1800261e8  jz      loc_18002630A
0x1800261ee  lea     r9, [rbp+phkDeviceInterface]; phkDeviceInterface
0x1800261f2  mov     dword ptr [rdi], 0
0x1800261f8  mov     edx, 20019h; samDesired
0x1800261fd  mov     [rbp+phkDeviceInterface], 0
0x180026205  mov     r8d, 1; Disposition
0x18002620b  mov     [rsp+48h+ulFlags], 0; ulFlags
0x180026213  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x180026219  test    eax, eax
0x18002621b  jnz     short loc_18002627D
0x18002621d  mov     rcx, [rbp+phkDeviceInterface]; hKey
0x180026221  lea     rax, [rbp+cbData]
0x180026225  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002622a  lea     r9, [rbp+Type]; lpType
0x18002622e  xor     r8d, r8d; lpReserved
0x180026231  mov     qword ptr [rsp+48h+ulFlags], 0; lpData
0x18002623a  mov     rdx, rsi; lpValueName
0x18002623d  mov     [rbp+cbData], 0
0x180026244  call    cs:__imp_RegQueryValueExW
0x18002624a  mov     ebx, eax
0x18002624c  test    eax, eax
0x18002624e  jz      short loc_18002629F
0x180026250  jle     short loc_18002625B
0x180026252  movzx   ebx, ax
0x180026255  or      ebx, 80070000h
0x18002625b  test    ebx, ebx
0x18002625d  jns     short loc_18002629F
0x18002625f  mov     rcx, [rbp+phkDeviceInterface]; hKey
0x180026263  test    rcx, rcx
0x180026266  jz      short loc_18002626E
0x180026268  call    cs:__imp_RegCloseKey
0x18002626e  mov     eax, ebx
0x180026270  add     rsp, 48h
0x180026274  pop     r15
0x180026276  pop     r14
0x180026278  pop     rdi
0x180026279  pop     rsi
0x18002627a  pop     rbx
0x18002627b  pop     rbp
0x18002627c  retn
0x18002627d  mov     edx, 0Dh; DefaultErr
0x180026282  mov     ecx, eax; CmReturnCode
0x180026284  call    cs:__imp_CM_MapCrToWin32Err
0x18002628a  mov     ebx, eax
0x18002628c  test    eax, eax
0x18002628e  jle     short loc_180026299
0x180026290  movzx   ebx, ax
0x180026293  or      ebx, 80070000h
0x180026299  test    ebx, ebx
0x18002629b  jns     short loc_18002621D
0x18002629d  jmp     short loc_18002625F
0x18002629f  mov     eax, [rbp+cbData]
0x1800262a2  mov     [rdi], eax
0x1800262a4  cmp     eax, r14d
0x1800262a7  ja      short loc_1800262F6
0x1800262a9  mov     rcx, [rbp+phkDeviceInterface]; hKey
0x1800262ad  lea     rax, [rbp+cbData]
0x1800262b1  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800262b6  lea     r9, [rbp+Type]; lpType
0x1800262ba  xor     r8d, r8d; lpReserved
0x1800262bd  mov     qword ptr [rsp+48h+ulFlags], r15; lpData
0x1800262c2  mov     rdx, rsi; lpValueName
0x1800262c5  mov     [rbp+cbData], r14d
0x1800262c9  call    cs:__imp_RegQueryValueExW
0x1800262cf  mov     ebx, eax
0x1800262d1  test    eax, eax
0x1800262d3  jz      short loc_1800262EA
0x1800262d5  jle     short loc_1800262E0
0x1800262d7  movzx   ebx, ax
0x1800262da  or      ebx, 80070000h
0x1800262e0  test    ebx, ebx
0x1800262e2  js      loc_18002625F
0x1800262e8  jmp     short loc_1800262EC
0x1800262ea  xor     ebx, ebx
0x1800262ec  mov     ecx, [rbp+cbData]
0x1800262ef  mov     [rdi], ecx
0x1800262f1  jmp     loc_18002625F
0x1800262f6  mov     ebx, 0C00D7170h
0x1800262fb  jmp     loc_18002625F
0x180026300  mov     ebx, 80070057h
0x180026305  jmp     loc_18002626E
0x18002630a  mov     ebx, 80004003h
0x18002630f  jmp     loc_18002626E
```
