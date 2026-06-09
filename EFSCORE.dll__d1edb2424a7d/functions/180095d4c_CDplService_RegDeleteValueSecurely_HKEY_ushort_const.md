# CDplService::RegDeleteValueSecurely(HKEY__ *,ushort const *)

- ea: `0x180095d4c`
- end: `0x180095f4f`
- name: `?RegDeleteValueSecurely@CDplService@@SAJPEAUHKEY__@@PEBG@Z`
- size: `515`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bbae0`
- `0x1800bc2ec`
- `0x1800bc65c`

## callees

- `0x180005045`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800805c4`
- `0x180095d4c`
- `0x1800d6064`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180095ea5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180095ea5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180095f27`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180095f27`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095daf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095daf`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180095ecd`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180095f34`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180095ecd`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180095f34`
- `bcrypt!BCryptGenRandom` at `0x180095e70`
- `bcrypt!BCryptGenRandom` at `0x180095e70`

## pseudocode

```c
__int64 __fastcall CDplService::RegDeleteValueSecurely(HKEY hKey, LPCWSTR lpValueName)
{
  PUCHAR v2; // rbp
  LSTATUS v5; // edi
  unsigned int v6; // ebx
  LSTATUS ValueW; // eax
  int v8; // ecx
  int v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  char pdwType; // [rsp+20h] [rbp-38h]
  DWORD cbBuffer; // [rsp+60h] [rbp+8h] BYREF
  PUCHAR pbBuffer; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  cbBuffer = 0;
  pbBuffer = 0;
  if ( hKey )
  {
    ValueW = RegGetValueW(hKey, 0, lpValueName, 0xFFFFu, 0, 0, &cbBuffer);
    v5 = ValueW;
    if ( ValueW )
    {
      if ( (unsigned int)(ValueW - 2) <= 1 )
      {
        v6 = 1;
        goto LABEL_24;
      }
      if ( ValueW > 0 )
        v6 = (unsigned __int16)ValueW | 0x80070000;
      else
        v6 = ValueW;
      pdwType = -65;
    }
    else
    {
      fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 194);
      v6 = DplibpMemAllocEx(cbBuffer, 0, 0, &pbBuffer);
      v9 = fnEfsLogTrace1String1Dword(
             g_hPublisher,
             (unsigned int)EFS_TRACE_COMPLETE_EVENT,
             (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
             (unsigned int)&sourceString,
             v6,
             37,
             194);
      v2 = pbBuffer;
      if ( v9 < 0 )
        goto LABEL_24;
      if ( BCryptGenRandom(0, pbBuffer, cbBuffer, 2u) )
        memset_0(v2, 0, cbBuffer);
      v10 = RegSetValueExW(hKey, lpValueName, 0, 3u, v2, cbBuffer);
      v5 = v10;
      if ( v10 )
      {
        if ( v10 > 0 )
          v6 = (unsigned __int16)v10 | 0x80070000;
        else
          v6 = v10;
        pdwType = -48;
      }
      else
      {
        v11 = RegFlushKey(hKey);
        v5 = v11;
        if ( !v11 )
          goto LABEL_24;
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
        else
          v6 = v11;
        pdwType = -41;
      }
    }
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v6, 37, pdwType);
    goto LABEL_24;
  }
  v5 = 0;
  v6 = -2147024809;
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 37, 172);
LABEL_24:
  CDplService::MemFreeIf<unsigned short>(v2);
  if ( (unsigned int)(v5 - 2) > 1 && hKey && !RegDeleteValueW(hKey, lpValueName) )
    RegFlushKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180095d4c  mov     rax, rsp
0x180095d4f  mov     [rax+10h], rbx
0x180095d53  mov     [rax+20h], rbp
0x180095d57  push    rsi
0x180095d58  push    rdi
0x180095d59  push    r15
0x180095d5b  sub     rsp, 40h
0x180095d5f  xor     ebp, ebp
0x180095d61  mov     dword ptr [rax+8], 0
0x180095d68  mov     [rax+18h], rbp
0x180095d6c  mov     r15, rdx
0x180095d6f  mov     rsi, rcx
0x180095d72  test    rcx, rcx
0x180095d75  jnz     short loc_180095D90
0x180095d77  xor     edi, edi
0x180095d79  mov     dword ptr [rax-38h], 2AACh
0x180095d80  mov     ebx, 80070057h
0x180095d85  mov     r8d, 80070057h
0x180095d8b  jmp     loc_180095EF3
0x180095d90  lea     rax, [rsp+58h+cbBuffer]
0x180095d95  mov     r9d, 0FFFFh; dwFlags
0x180095d9b  mov     [rsp+58h+pcbData], rax; pcbData
0x180095da0  mov     r8, r15; lpValue
0x180095da3  mov     [rsp+58h+pvData], rbp; pvData
0x180095da8  xor     edx, edx; lpSubKey
0x180095daa  mov     [rsp+58h+pdwType], rbp; pdwType
0x180095daf  call    cs:__imp_RegGetValueW
0x180095db5  mov     edi, eax
0x180095db7  test    eax, eax
0x180095db9  jz      short loc_180095DEB
0x180095dbb  lea     ecx, [rax-2]
0x180095dbe  cmp     ecx, 1
0x180095dc1  jbe     short loc_180095DE1
0x180095dc3  test    eax, eax
0x180095dc5  jg      short loc_180095DCB
0x180095dc7  mov     ebx, eax
0x180095dc9  jmp     short loc_180095DD4
0x180095dcb  movzx   ebx, ax
0x180095dce  or      ebx, 80070000h
0x180095dd4  mov     dword ptr [rsp+58h+pdwType], 2ABFh
0x180095ddc  jmp     loc_180095EF0
0x180095de1  mov     ebx, 1
0x180095de6  jmp     loc_180095F0C
0x180095deb  mov     ebp, 2AC2h
0x180095df0  lea     r8, sourceString
0x180095df7  mov     r9d, 25h ; '%'
0x180095dfd  mov     dword ptr [rsp+58h+pdwType], ebp
0x180095e01  lea     rdx, EFS_TRACE_START_EVENT
0x180095e08  call    fnEfsLogTrace1Strings
0x180095e0d  mov     ecx, [rsp+58h+cbBuffer]
0x180095e11  lea     r9, [rsp+58h+pbBuffer]
0x180095e16  xor     r8d, r8d
0x180095e19  xor     edx, edx
0x180095e1b  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x180095e20  mov     rcx, cs:g_hPublisher
0x180095e27  lea     r9, sourceString
0x180095e2e  mov     dword ptr [rsp+58h+pcbData], ebp
0x180095e32  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180095e39  mov     dword ptr [rsp+58h+pvData], 25h ; '%'
0x180095e41  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180095e48  mov     dword ptr [rsp+58h+pdwType], eax
0x180095e4c  mov     ebx, eax
0x180095e4e  call    fnEfsLogTrace1String1Dword
0x180095e53  mov     rbp, [rsp+58h+pbBuffer]
0x180095e58  test    eax, eax
0x180095e5a  js      loc_180095F0C
0x180095e60  mov     r8d, [rsp+58h+cbBuffer]; cbBuffer
0x180095e65  mov     r9d, 2; dwFlags
0x180095e6b  mov     rdx, rbp; pbBuffer
0x180095e6e  xor     ecx, ecx; hAlgorithm
0x180095e70  call    cs:__imp_BCryptGenRandom
0x180095e76  test    eax, eax
0x180095e78  jz      short loc_180095E89
0x180095e7a  mov     r8d, [rsp+58h+cbBuffer]; Size
0x180095e7f  xor     edx, edx; Val
0x180095e81  mov     rcx, rbp; void *
0x180095e84  call    memset_0
0x180095e89  mov     eax, [rsp+58h+cbBuffer]
0x180095e8d  mov     r9d, 3; dwType
0x180095e93  mov     dword ptr [rsp+58h+pvData], eax; cbData
0x180095e97  xor     r8d, r8d; Reserved
0x180095e9a  mov     rdx, r15; lpValueName
0x180095e9d  mov     [rsp+58h+pdwType], rbp; lpData
0x180095ea2  mov     rcx, rsi; hKey
0x180095ea5  call    cs:__imp_RegSetValueExW
0x180095eab  mov     edi, eax
0x180095ead  test    eax, eax
0x180095eaf  jz      short loc_180095ECA
0x180095eb1  jg      short loc_180095EB7
0x180095eb3  mov     ebx, eax
0x180095eb5  jmp     short loc_180095EC0
0x180095eb7  movzx   ebx, ax
0x180095eba  or      ebx, 80070000h
0x180095ec0  mov     dword ptr [rsp+58h+pdwType], 2AD0h
0x180095ec8  jmp     short loc_180095EF0
0x180095eca  mov     rcx, rsi; hKey
0x180095ecd  call    cs:__imp_RegFlushKey
0x180095ed3  mov     edi, eax
0x180095ed5  test    eax, eax
0x180095ed7  jz      short loc_180095F0C
0x180095ed9  jg      short loc_180095EDF
0x180095edb  mov     ebx, eax
0x180095edd  jmp     short loc_180095EE8
0x180095edf  movzx   ebx, ax
0x180095ee2  or      ebx, 80070000h
0x180095ee8  mov     dword ptr [rsp+58h+pdwType], 2AD7h
0x180095ef0  mov     r8d, ebx
0x180095ef3  mov     rcx, cs:g_hPublisher
0x180095efa  lea     rdx, EFS_TRACE_ERROR
0x180095f01  mov     r9d, 25h ; '%'
0x180095f07  call    fnEfsLogTrace1
0x180095f0c  mov     rcx, rbp
0x180095f0f  call    ??$MemFreeIf@G@CDplService@@SAPEAGPEAG@Z; CDplService::MemFreeIf<ushort>(ushort *)
0x180095f14  lea     eax, [rdi-2]
0x180095f17  cmp     eax, 1
0x180095f1a  jbe     short loc_180095F3A
0x180095f1c  test    rsi, rsi
0x180095f1f  jz      short loc_180095F3A
0x180095f21  mov     rdx, r15; lpValueName
0x180095f24  mov     rcx, rsi; hKey
0x180095f27  call    cs:__imp_RegDeleteValueW
0x180095f2d  test    eax, eax
0x180095f2f  jnz     short loc_180095F3A
0x180095f31  mov     rcx, rsi; hKey
0x180095f34  call    cs:__imp_RegFlushKey
0x180095f3a  mov     rbp, [rsp+58h+arg_18]
0x180095f3f  mov     eax, ebx
0x180095f41  mov     rbx, [rsp+58h+arg_8]
0x180095f46  add     rsp, 40h
0x180095f4a  pop     r15
0x180095f4c  pop     rdi
0x180095f4d  pop     rsi
0x180095f4e  retn
```
