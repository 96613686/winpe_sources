# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x18012ac2c`
- end: `0x18012ad9e`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `370`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18011b160`
- `0x1801bcf88`

## callees

- `0x1801201a0`
- `0x180123882`
- `0x18012ac2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012ac8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012ac8a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012acd1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012ad32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012acd1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012ad32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012ad5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012ad5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012ad49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012ad49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18012ace8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18012ace8`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  HKEY v5; // rcx
  int v7; // esi
  LSTATUS v8; // eax
  int v9; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  v5 = HKEY_CURRENT_USER;
  hkey = HKEY_CURRENT_USER;
  if ( a2 && *a2 )
  {
    v7 = 1;
    v8 = RegOpenKeyExW(HKEY_CURRENT_USER, a2, 0, 1u, &hkey);
    v5 = hkey;
    v9 = v8;
  }
  else
  {
    v9 = 0;
    v7 = 0;
  }
  if ( v9 )
    goto LABEL_18;
  pcbData = 256;
  ValueW = RegGetValueW(v5, 0, a3, 2u, 0, Src, &pcbData);
  v9 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v9 )
      {
        if ( RegGetValueW(hkey, 0, a3, 2u, 0, pvData, &pcbData) )
        {
          v9 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          v9 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v9 = 14;
    }
  }
  if ( v7 )
    RegCloseKey(hkey);
  if ( v9 )
  {
LABEL_18:
    *a5 = 0;
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18012ac2c  mov     [rsp-8+arg_0], rbx
0x18012ac31  push    rbp
0x18012ac32  push    rsi
0x18012ac33  push    rdi
0x18012ac34  push    r14
0x18012ac36  push    r15
0x18012ac38  lea     rbp, [rsp-60h]
0x18012ac3d  sub     rsp, 160h
0x18012ac44  mov     rax, cs:__security_cookie
0x18012ac4b  xor     rax, rsp
0x18012ac4e  mov     [rbp+80h+var_30], rax
0x18012ac52  mov     rdi, [rbp+80h+arg_20]
0x18012ac59  xor     r15d, r15d
0x18012ac5c  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18012ac63  mov     r14, r8
0x18012ac66  mov     [rsp+180h+hkey], rcx
0x18012ac6b  test    rdx, rdx
0x18012ac6e  jz      short loc_18012AC99
0x18012ac70  cmp     [rdx], r15w
0x18012ac74  jz      short loc_18012AC99
0x18012ac76  lea     rax, [rsp+180h+hkey]
0x18012ac7b  xor     r8d, r8d; ulOptions
0x18012ac7e  lea     esi, [r15+1]
0x18012ac82  mov     [rsp+180h+phkResult], rax; phkResult
0x18012ac87  mov     r9d, esi; samDesired
0x18012ac8a  call    cs:__imp_RegOpenKeyExW
0x18012ac90  mov     rcx, [rsp+180h+hkey]
0x18012ac95  mov     ebx, eax
0x18012ac97  jmp     short loc_18012AC9F
0x18012ac99  mov     ebx, r15d
0x18012ac9c  mov     esi, r15d
0x18012ac9f  test    ebx, ebx
0x18012aca1  jnz     loc_18012AD69
0x18012aca7  lea     rax, [rsp+180h+var_140]
0x18012acac  mov     [rsp+180h+var_140], 100h
0x18012acb4  mov     [rsp+180h+pcbData], rax; pcbData
0x18012acb9  lea     r9d, [rbx+2]; dwFlags
0x18012acbd  lea     rax, [rsp+180h+Src]
0x18012acc2  mov     r8, r14; lpValue
0x18012acc5  mov     [rsp+180h+pvData], rax; pvData
0x18012acca  xor     edx, edx; lpSubKey
0x18012accc  mov     [rsp+180h+phkResult], r15; pdwType
0x18012acd1  call    cs:__imp_RegGetValueW
0x18012acd7  mov     ebx, eax
0x18012acd9  test    eax, eax
0x18012acdb  jz      short loc_18012ACE4
0x18012acdd  cmp     eax, 0EAh
0x18012ace2  jnz     short loc_18012AD56
0x18012ace4  mov     ecx, [rsp+180h+var_140]; cb
0x18012ace8  call    cs:__imp_CoTaskMemAlloc
0x18012acee  mov     [rdi], rax
0x18012acf1  test    rax, rax
0x18012acf4  jz      short loc_18012AD51
0x18012acf6  test    ebx, ebx
0x18012acf8  jnz     short loc_18012AD0E
0x18012acfa  mov     r8d, [rsp+180h+var_140]; Size
0x18012acff  lea     rdx, [rsp+180h+Src]; Src
0x18012ad04  mov     rcx, rax; void *
0x18012ad07  call    memcpy_0
0x18012ad0c  jmp     short loc_18012AD56
0x18012ad0e  lea     rcx, [rsp+180h+var_140]
0x18012ad13  mov     r9d, 2; dwFlags
0x18012ad19  mov     [rsp+180h+pcbData], rcx; pcbData
0x18012ad1e  mov     r8, r14; lpValue
0x18012ad21  mov     rcx, [rsp+180h+hkey]; hkey
0x18012ad26  xor     edx, edx; lpSubKey
0x18012ad28  mov     [rsp+180h+pvData], rax; pvData
0x18012ad2d  mov     [rsp+180h+phkResult], r15; pdwType
0x18012ad32  call    cs:__imp_RegGetValueW
0x18012ad38  test    eax, eax
0x18012ad3a  jnz     short loc_18012AD41
0x18012ad3c  mov     ebx, r15d
0x18012ad3f  jmp     short loc_18012AD56
0x18012ad41  mov     rcx, [rdi]; pv
0x18012ad44  mov     ebx, 3EBh
0x18012ad49  call    cs:__imp_CoTaskMemFree
0x18012ad4f  jmp     short loc_18012AD56
0x18012ad51  mov     ebx, 0Eh
0x18012ad56  test    esi, esi
0x18012ad58  jz      short loc_18012AD65
0x18012ad5a  mov     rcx, [rsp+180h+hkey]; hKey
0x18012ad5f  call    cs:__imp_RegCloseKey
0x18012ad65  test    ebx, ebx
0x18012ad67  jz      short loc_18012AD79
0x18012ad69  mov     [rdi], r15
0x18012ad6c  test    ebx, ebx
0x18012ad6e  jle     short loc_18012AD79
0x18012ad70  movzx   ebx, bx
0x18012ad73  or      ebx, 80070000h
0x18012ad79  mov     eax, ebx
0x18012ad7b  mov     rcx, [rbp+80h+var_30]
0x18012ad7f  xor     rcx, rsp; StackCookie
0x18012ad82  call    __security_check_cookie
0x18012ad87  mov     rbx, [rsp+180h+arg_0]
0x18012ad8f  add     rsp, 160h
0x18012ad96  pop     r15
0x18012ad98  pop     r14
0x18012ad9a  pop     rdi
0x18012ad9b  pop     rsi
0x18012ad9c  pop     rbp
0x18012ad9d  retn
```
