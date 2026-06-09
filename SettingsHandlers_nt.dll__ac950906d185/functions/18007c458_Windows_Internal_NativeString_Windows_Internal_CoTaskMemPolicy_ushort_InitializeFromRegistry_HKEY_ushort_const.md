# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x18007c458`
- end: `0x18007c64b`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `499`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007afc8`
- `0x18010f998`

## callees

- `0x18005019c`
- `0x18007c458`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c5be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c60f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c625`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c5be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c60f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c625`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c4f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c57a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c4f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c57a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007c4a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007c529`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007c4a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007c529`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18007c563`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18007c5a1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18007c563`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18007c5a1`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
        BYTE **a1,
        HKEY a2,
        const WCHAR *a3)
{
  BYTE *lpData; // rdi
  LSTATUS Value; // eax
  signed int v8; // ebx
  LSTATUS v9; // eax
  __int64 v10; // rsi
  DWORD v11; // eax
  DWORD v12; // ebp
  WCHAR *v13; // rax
  WCHAR *v14; // rsi
  DWORD v15; // eax
  DWORD v16; // r14d
  __int64 v17; // rax
  DWORD Type[14]; // [rsp+30h] [rbp-38h] BYREF
  SIZE_T cb; // [rsp+88h] [rbp+20h] BYREF

  Type[0] = 0;
  LODWORD(cb) = 0;
  lpData = 0;
  Value = RegQueryValueExW(a2, a3, 0, Type, 0, (LPDWORD)&cb);
  v8 = Value;
  if ( Value > 0 )
    v8 = (unsigned __int16)Value | 0x80070000;
  if ( v8 >= 0 )
  {
    if ( Type[0] - 1 > 1 || !(_DWORD)cb || (cb & 1) != 0 )
      goto LABEL_24;
    lpData = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
    if ( !lpData )
    {
LABEL_14:
      v8 = -2147024882;
      goto LABEL_25;
    }
    v9 = RegQueryValueExW(a2, a3, 0, Type, lpData, (LPDWORD)&cb);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 >= 0 )
    {
      v10 = ((unsigned int)cb >> 1) - 1;
      if ( Type[0] == 2 )
      {
        v11 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
        v12 = v11;
        if ( v11 )
        {
          v13 = (WCHAR *)CoTaskMemAlloc(2LL * v11);
          v14 = v13;
          if ( !v13 )
            goto LABEL_14;
          v15 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v13, v12);
          v16 = v15;
          if ( !v15 || v15 > v12 )
          {
            v8 = -2147024774;
            CoTaskMemFree(v14);
            goto LABEL_25;
          }
          v8 = 0;
          CoTaskMemFree(lpData);
          lpData = (BYTE *)v14;
          v10 = v16 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v10] )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
        if ( lpData )
        {
          v17 = (unsigned int)(v10 + 1);
          if ( (_DWORD)v10 != -1 )
          {
            *a1 = lpData;
            a1[1] = (BYTE *)(v17 - 1);
            a1[2] = (BYTE *)(unsigned int)v17;
            *(_WORD *)&lpData[2 * (unsigned int)v17 - 2] = 0;
          }
        }
        lpData = 0;
        goto LABEL_25;
      }
LABEL_24:
      v8 = -2147024883;
    }
  }
LABEL_25:
  CoTaskMemFree(lpData);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18007c458  mov     r11, rsp
0x18007c45b  mov     [r11+8], rbx
0x18007c45f  mov     [r11+10h], rbp
0x18007c463  mov     [r11+20h], r9b
0x18007c467  push    rsi
0x18007c468  push    rdi
0x18007c469  push    r12
0x18007c46b  push    r14
0x18007c46d  push    r15
0x18007c46f  sub     rsp, 40h
0x18007c473  xor     r12d, r12d
0x18007c476  lea     rax, [r11+20h]
0x18007c47a  mov     rsi, r8
0x18007c47d  mov     [r11-40h], rax
0x18007c481  mov     rbp, rdx
0x18007c484  mov     [r11-48h], r12
0x18007c488  mov     r15, rcx
0x18007c48b  mov     [r11-38h], r12d
0x18007c48f  mov     rdx, rsi; lpValueName
0x18007c492  mov     [r11+20h], r12d
0x18007c496  mov     rcx, rbp; hKey
0x18007c499  lea     r9, [r11-38h]; lpType
0x18007c49d  xor     r8d, r8d; lpReserved
0x18007c4a0  mov     edi, r12d
0x18007c4a3  call    cs:__imp_RegQueryValueExW
0x18007c4aa  nop     dword ptr [rax+rax+00h]
0x18007c4af  mov     ebx, eax
0x18007c4b1  mov     r14d, 80070000h
0x18007c4b7  test    eax, eax
0x18007c4b9  jle     short loc_18007C4C1
0x18007c4bb  movzx   ebx, ax
0x18007c4be  or      ebx, r14d
0x18007c4c1  test    ebx, ebx
0x18007c4c3  js      loc_18007C622
0x18007c4c9  mov     eax, [rsp+68h+Type]
0x18007c4cd  dec     eax
0x18007c4cf  cmp     eax, 1
0x18007c4d2  ja      loc_18007C61D
0x18007c4d8  mov     eax, dword ptr [rsp+68h+cb]
0x18007c4df  test    eax, eax
0x18007c4e1  jz      loc_18007C61D
0x18007c4e7  test    al, 1
0x18007c4e9  jnz     loc_18007C61D
0x18007c4ef  mov     ecx, eax; cb
0x18007c4f1  call    cs:__imp_CoTaskMemAlloc
0x18007c4f8  nop     dword ptr [rax+rax+00h]
0x18007c4fd  mov     rdi, rax
0x18007c500  test    rax, rax
0x18007c503  jz      loc_18007C58E
0x18007c509  lea     rax, [rsp+68h+cb]
0x18007c511  xor     r8d, r8d; lpReserved
0x18007c514  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18007c519  lea     r9, [rsp+68h+Type]; lpType
0x18007c51e  mov     rdx, rsi; lpValueName
0x18007c521  mov     [rsp+68h+lpData], rdi; lpData
0x18007c526  mov     rcx, rbp; hKey
0x18007c529  call    cs:__imp_RegQueryValueExW
0x18007c530  nop     dword ptr [rax+rax+00h]
0x18007c535  mov     ebx, eax
0x18007c537  test    eax, eax
0x18007c539  jle     short loc_18007C541
0x18007c53b  movzx   ebx, ax
0x18007c53e  or      ebx, r14d
0x18007c541  test    ebx, ebx
0x18007c543  js      loc_18007C622
0x18007c549  mov     esi, dword ptr [rsp+68h+cb]
0x18007c550  shr     esi, 1
0x18007c552  dec     esi
0x18007c554  cmp     [rsp+68h+Type], 2
0x18007c559  jnz     short loc_18007C5D1
0x18007c55b  xor     r8d, r8d; nSize
0x18007c55e  xor     edx, edx; lpDst
0x18007c560  mov     rcx, rdi; lpSrc
0x18007c563  call    cs:__imp_ExpandEnvironmentStringsW
0x18007c56a  nop     dword ptr [rax+rax+00h]
0x18007c56f  mov     ebp, eax
0x18007c571  test    eax, eax
0x18007c573  jz      short loc_18007C5D1
0x18007c575  mov     ecx, ebp
0x18007c577  add     rcx, rcx; cb
0x18007c57a  call    cs:__imp_CoTaskMemAlloc
0x18007c581  nop     dword ptr [rax+rax+00h]
0x18007c586  mov     rsi, rax
0x18007c589  test    rax, rax
0x18007c58c  jnz     short loc_18007C598
0x18007c58e  mov     ebx, 8007000Eh
0x18007c593  jmp     loc_18007C622
0x18007c598  mov     r8d, ebp; nSize
0x18007c59b  mov     rdx, rsi; lpDst
0x18007c59e  mov     rcx, rdi; lpSrc
0x18007c5a1  call    cs:__imp_ExpandEnvironmentStringsW
0x18007c5a8  nop     dword ptr [rax+rax+00h]
0x18007c5ad  mov     r14d, eax
0x18007c5b0  test    eax, eax
0x18007c5b2  jz      short loc_18007C607
0x18007c5b4  cmp     eax, ebp
0x18007c5b6  ja      short loc_18007C607
0x18007c5b8  mov     rcx, rdi; pv
0x18007c5bb  mov     ebx, r12d
0x18007c5be  call    cs:__imp_CoTaskMemFree
0x18007c5c5  nop     dword ptr [rax+rax+00h]
0x18007c5ca  mov     rdi, rsi
0x18007c5cd  lea     esi, [r14-1]
0x18007c5d1  cmp     [rdi+rsi*2], r12w
0x18007c5d6  jnz     short loc_18007C61D
0x18007c5d8  mov     rcx, r15
0x18007c5db  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18007c5e0  test    rdi, rdi
0x18007c5e3  jz      short loc_18007C602
0x18007c5e5  lea     eax, [rsi+1]
0x18007c5e8  mov     ecx, eax
0x18007c5ea  test    eax, eax
0x18007c5ec  jz      short loc_18007C602
0x18007c5ee  dec     rax
0x18007c5f1  mov     [r15], rdi
0x18007c5f4  mov     [r15+8], rax
0x18007c5f8  mov     [r15+10h], rcx
0x18007c5fc  mov     [rdi+rcx*2-2], r12w
0x18007c602  mov     rdi, r12
0x18007c605  jmp     short loc_18007C622
0x18007c607  mov     rcx, rsi; pv
0x18007c60a  mov     ebx, 8007007Ah
0x18007c60f  call    cs:__imp_CoTaskMemFree
0x18007c616  nop     dword ptr [rax+rax+00h]
0x18007c61b  jmp     short loc_18007C622
0x18007c61d  mov     ebx, 8007000Dh
0x18007c622  mov     rcx, rdi; pv
0x18007c625  call    cs:__imp_CoTaskMemFree
0x18007c62c  nop     dword ptr [rax+rax+00h]
0x18007c631  mov     rbp, [rsp+68h+arg_8]
0x18007c636  mov     eax, ebx
0x18007c638  mov     rbx, [rsp+68h+arg_0]
0x18007c63d  add     rsp, 40h
0x18007c641  pop     r15
0x18007c643  pop     r14
0x18007c645  pop     r12
0x18007c647  pop     rdi
0x18007c648  pop     rsi
0x18007c649  retn
```
