# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x18011a0d4`
- end: `0x18011a2de`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180119b44`

## callees

- `0x18011a0d4`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18011a1df`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18011a21d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18011a1df`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18011a21d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011a11f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011a1a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011a11f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011a1a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18011a16d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18011a1f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18011a16d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18011a1f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a23a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a25c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a2a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a2b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a23a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a25c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a2a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a2b8`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
        __int64 a1,
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
  DWORD v16; // r15d
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
      goto LABEL_26;
    lpData = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
    if ( !lpData )
    {
LABEL_14:
      v8 = -2147024882;
      goto LABEL_27;
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
            goto LABEL_27;
          }
          v8 = 0;
          CoTaskMemFree(lpData);
          lpData = (BYTE *)v14;
          v10 = v16 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v10] )
      {
        if ( *(_QWORD *)a1 )
        {
          CoTaskMemFree(*(LPVOID *)a1);
          *(_QWORD *)a1 = 0;
        }
        *(_QWORD *)(a1 + 8) = 0;
        *(_QWORD *)(a1 + 16) = 0;
        if ( lpData )
        {
          v17 = (unsigned int)(v10 + 1);
          if ( (_DWORD)v10 != -1 )
          {
            *(_QWORD *)a1 = lpData;
            *(_QWORD *)(a1 + 8) = v17 - 1;
            *(_QWORD *)(a1 + 16) = (unsigned int)v17;
            *(_WORD *)&lpData[2 * (unsigned int)v17 - 2] = 0;
          }
        }
        lpData = 0;
        goto LABEL_27;
      }
LABEL_26:
      v8 = -2147024883;
    }
  }
LABEL_27:
  CoTaskMemFree(lpData);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18011a0d4  mov     r11, rsp
0x18011a0d7  mov     [r11+8], rbx
0x18011a0db  mov     [r11+10h], rbp
0x18011a0df  mov     [r11+20h], r9b
0x18011a0e3  push    rsi
0x18011a0e4  push    rdi
0x18011a0e5  push    r12
0x18011a0e7  push    r14
0x18011a0e9  push    r15
0x18011a0eb  sub     rsp, 40h
0x18011a0ef  xor     r12d, r12d
0x18011a0f2  lea     rax, [r11+20h]
0x18011a0f6  mov     rsi, r8
0x18011a0f9  mov     [r11-40h], rax
0x18011a0fd  mov     rbp, rdx
0x18011a100  mov     [r11-48h], r12
0x18011a104  mov     r14, rcx
0x18011a107  mov     [r11-38h], r12d
0x18011a10b  mov     rdx, rsi; lpValueName
0x18011a10e  mov     [r11+20h], r12d
0x18011a112  mov     rcx, rbp; hKey
0x18011a115  lea     r9, [r11-38h]; lpType
0x18011a119  xor     r8d, r8d; lpReserved
0x18011a11c  mov     edi, r12d
0x18011a11f  call    cs:__imp_RegQueryValueExW
0x18011a126  nop     dword ptr [rax+rax+00h]
0x18011a12b  mov     ebx, eax
0x18011a12d  mov     r15d, 80070000h
0x18011a133  test    eax, eax
0x18011a135  jle     short loc_18011A13D
0x18011a137  movzx   ebx, ax
0x18011a13a  or      ebx, r15d
0x18011a13d  test    ebx, ebx
0x18011a13f  js      loc_18011A2B5
0x18011a145  mov     eax, [rsp+68h+Type]
0x18011a149  dec     eax
0x18011a14b  cmp     eax, 1
0x18011a14e  ja      loc_18011A2B0
0x18011a154  mov     eax, dword ptr [rsp+68h+cb]
0x18011a15b  test    eax, eax
0x18011a15d  jz      loc_18011A2B0
0x18011a163  test    al, 1
0x18011a165  jnz     loc_18011A2B0
0x18011a16b  mov     ecx, eax; cb
0x18011a16d  call    cs:__imp_CoTaskMemAlloc
0x18011a174  nop     dword ptr [rax+rax+00h]
0x18011a179  mov     rdi, rax
0x18011a17c  test    rax, rax
0x18011a17f  jz      loc_18011A20A
0x18011a185  lea     rax, [rsp+68h+cb]
0x18011a18d  xor     r8d, r8d; lpReserved
0x18011a190  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18011a195  lea     r9, [rsp+68h+Type]; lpType
0x18011a19a  mov     rdx, rsi; lpValueName
0x18011a19d  mov     [rsp+68h+lpData], rdi; lpData
0x18011a1a2  mov     rcx, rbp; hKey
0x18011a1a5  call    cs:__imp_RegQueryValueExW
0x18011a1ac  nop     dword ptr [rax+rax+00h]
0x18011a1b1  mov     ebx, eax
0x18011a1b3  test    eax, eax
0x18011a1b5  jle     short loc_18011A1BD
0x18011a1b7  movzx   ebx, ax
0x18011a1ba  or      ebx, r15d
0x18011a1bd  test    ebx, ebx
0x18011a1bf  js      loc_18011A2B5
0x18011a1c5  mov     esi, dword ptr [rsp+68h+cb]
0x18011a1cc  shr     esi, 1
0x18011a1ce  dec     esi
0x18011a1d0  cmp     [rsp+68h+Type], 2
0x18011a1d5  jnz     short loc_18011A24D
0x18011a1d7  xor     r8d, r8d; nSize
0x18011a1da  xor     edx, edx; lpDst
0x18011a1dc  mov     rcx, rdi; lpSrc
0x18011a1df  call    cs:__imp_ExpandEnvironmentStringsW
0x18011a1e6  nop     dword ptr [rax+rax+00h]
0x18011a1eb  mov     ebp, eax
0x18011a1ed  test    eax, eax
0x18011a1ef  jz      short loc_18011A24D
0x18011a1f1  mov     ecx, ebp
0x18011a1f3  add     rcx, rcx; cb
0x18011a1f6  call    cs:__imp_CoTaskMemAlloc
0x18011a1fd  nop     dword ptr [rax+rax+00h]
0x18011a202  mov     rsi, rax
0x18011a205  test    rax, rax
0x18011a208  jnz     short loc_18011A214
0x18011a20a  mov     ebx, 8007000Eh
0x18011a20f  jmp     loc_18011A2B5
0x18011a214  mov     r8d, ebp; nSize
0x18011a217  mov     rdx, rsi; lpDst
0x18011a21a  mov     rcx, rdi; lpSrc
0x18011a21d  call    cs:__imp_ExpandEnvironmentStringsW
0x18011a224  nop     dword ptr [rax+rax+00h]
0x18011a229  mov     r15d, eax
0x18011a22c  test    eax, eax
0x18011a22e  jz      short loc_18011A29A
0x18011a230  cmp     eax, ebp
0x18011a232  ja      short loc_18011A29A
0x18011a234  mov     rcx, rdi; pv
0x18011a237  mov     ebx, r12d
0x18011a23a  call    cs:__imp_CoTaskMemFree
0x18011a241  nop     dword ptr [rax+rax+00h]
0x18011a246  mov     rdi, rsi
0x18011a249  lea     esi, [r15-1]
0x18011a24d  cmp     [rdi+rsi*2], r12w
0x18011a252  jnz     short loc_18011A2B0
0x18011a254  mov     rcx, [r14]; pv
0x18011a257  test    rcx, rcx
0x18011a25a  jz      short loc_18011A26B
0x18011a25c  call    cs:__imp_CoTaskMemFree
0x18011a263  nop     dword ptr [rax+rax+00h]
0x18011a268  mov     [r14], r12
0x18011a26b  mov     [r14+8], r12
0x18011a26f  mov     [r14+10h], r12
0x18011a273  test    rdi, rdi
0x18011a276  jz      short loc_18011A295
0x18011a278  lea     eax, [rsi+1]
0x18011a27b  mov     ecx, eax
0x18011a27d  test    eax, eax
0x18011a27f  jz      short loc_18011A295
0x18011a281  dec     rax
0x18011a284  mov     [r14], rdi
0x18011a287  mov     [r14+8], rax
0x18011a28b  mov     [r14+10h], rcx
0x18011a28f  mov     [rdi+rcx*2-2], r12w
0x18011a295  mov     rdi, r12
0x18011a298  jmp     short loc_18011A2B5
0x18011a29a  mov     rcx, rsi; pv
0x18011a29d  mov     ebx, 8007007Ah
0x18011a2a2  call    cs:__imp_CoTaskMemFree
0x18011a2a9  nop     dword ptr [rax+rax+00h]
0x18011a2ae  jmp     short loc_18011A2B5
0x18011a2b0  mov     ebx, 8007000Dh
0x18011a2b5  mov     rcx, rdi; pv
0x18011a2b8  call    cs:__imp_CoTaskMemFree
0x18011a2bf  nop     dword ptr [rax+rax+00h]
0x18011a2c4  mov     rbp, [rsp+68h+arg_8]
0x18011a2c9  mov     eax, ebx
0x18011a2cb  mov     rbx, [rsp+68h+arg_0]
0x18011a2d0  add     rsp, 40h
0x18011a2d4  pop     r15
0x18011a2d6  pop     r14
0x18011a2d8  pop     r12
0x18011a2da  pop     rdi
0x18011a2db  pop     rsi
0x18011a2dc  retn
```
