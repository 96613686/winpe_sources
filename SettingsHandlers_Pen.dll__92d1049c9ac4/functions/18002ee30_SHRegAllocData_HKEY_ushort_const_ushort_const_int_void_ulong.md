# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x18002ee30`
- end: `0x18002ef9b`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `363`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002668c`
- `0x18002674c`
- `0x1800272b8`
- `0x1800281d0`
- `0x180029580`
- `0x18002c1d0`
- `0x18002c3c8`

## callees

- `0x1800030e0`
- `0x1800045b5`
- `0x18002ee30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ef46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ef46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002eee5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002eee5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ee87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ee87`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002eece`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ef2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002eece`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ef2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ef5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ef5c`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  int v6; // esi
  LSTATUS v7; // eax
  int v8; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  hkey = a1;
  if ( a2 && *a2 )
  {
    v6 = 1;
    v7 = RegOpenKeyExW(a1, a2, 0, 1u, &hkey);
    a1 = hkey;
    v8 = v7;
  }
  else
  {
    v8 = 0;
    v6 = 0;
  }
  if ( v8 )
    goto LABEL_18;
  pcbData = 256;
  ValueW = RegGetValueW(a1, 0, a3, 2u, 0, Src, &pcbData);
  v8 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v8 )
      {
        if ( RegGetValueW(hkey, 0, a3, 2u, 0, pvData, &pcbData) )
        {
          v8 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          v8 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v8 = 14;
    }
  }
  if ( v6 )
    RegCloseKey(hkey);
  if ( v8 )
  {
LABEL_18:
    *a5 = 0;
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002ee30  mov     [rsp-8+arg_18], rbx
0x18002ee35  push    rbp
0x18002ee36  push    rsi
0x18002ee37  push    rdi
0x18002ee38  push    r14
0x18002ee3a  push    r15
0x18002ee3c  lea     rbp, [rsp-60h]
0x18002ee41  sub     rsp, 160h
0x18002ee48  mov     rax, cs:__security_cookie
0x18002ee4f  xor     rax, rsp
0x18002ee52  mov     [rbp+80h+var_30], rax
0x18002ee56  mov     rdi, [rbp+80h+arg_20]
0x18002ee5d  xor     r15d, r15d
0x18002ee60  mov     [rsp+180h+hkey], rcx
0x18002ee65  mov     r14, r8
0x18002ee68  test    rdx, rdx
0x18002ee6b  jz      short loc_18002EE96
0x18002ee6d  cmp     [rdx], r15w
0x18002ee71  jz      short loc_18002EE96
0x18002ee73  lea     rax, [rsp+180h+hkey]
0x18002ee78  xor     r8d, r8d; ulOptions
0x18002ee7b  lea     esi, [r15+1]
0x18002ee7f  mov     [rsp+180h+phkResult], rax; phkResult
0x18002ee84  mov     r9d, esi; samDesired
0x18002ee87  call    cs:__imp_RegOpenKeyExW
0x18002ee8d  mov     rcx, [rsp+180h+hkey]; hkey
0x18002ee92  mov     ebx, eax
0x18002ee94  jmp     short loc_18002EE9C
0x18002ee96  mov     ebx, r15d
0x18002ee99  mov     esi, r15d
0x18002ee9c  test    ebx, ebx
0x18002ee9e  jnz     loc_18002EF66
0x18002eea4  lea     rax, [rsp+180h+var_140]
0x18002eea9  mov     [rsp+180h+var_140], 100h
0x18002eeb1  mov     [rsp+180h+pcbData], rax; pcbData
0x18002eeb6  lea     r9d, [rbx+2]; dwFlags
0x18002eeba  lea     rax, [rsp+180h+Src]
0x18002eebf  mov     r8, r14; lpValue
0x18002eec2  mov     [rsp+180h+pvData], rax; pvData
0x18002eec7  xor     edx, edx; lpSubKey
0x18002eec9  mov     [rsp+180h+phkResult], r15; pdwType
0x18002eece  call    cs:__imp_RegGetValueW
0x18002eed4  mov     ebx, eax
0x18002eed6  test    eax, eax
0x18002eed8  jz      short loc_18002EEE1
0x18002eeda  cmp     eax, 0EAh
0x18002eedf  jnz     short loc_18002EF53
0x18002eee1  mov     ecx, [rsp+180h+var_140]; cb
0x18002eee5  call    cs:__imp_CoTaskMemAlloc
0x18002eeeb  mov     [rdi], rax
0x18002eeee  test    rax, rax
0x18002eef1  jz      short loc_18002EF4E
0x18002eef3  test    ebx, ebx
0x18002eef5  jnz     short loc_18002EF0B
0x18002eef7  mov     r8d, [rsp+180h+var_140]; Size
0x18002eefc  lea     rdx, [rsp+180h+Src]; Src
0x18002ef01  mov     rcx, rax; void *
0x18002ef04  call    memcpy_0
0x18002ef09  jmp     short loc_18002EF53
0x18002ef0b  lea     rcx, [rsp+180h+var_140]
0x18002ef10  mov     r9d, 2; dwFlags
0x18002ef16  mov     [rsp+180h+pcbData], rcx; pcbData
0x18002ef1b  mov     r8, r14; lpValue
0x18002ef1e  mov     rcx, [rsp+180h+hkey]; hkey
0x18002ef23  xor     edx, edx; lpSubKey
0x18002ef25  mov     [rsp+180h+pvData], rax; pvData
0x18002ef2a  mov     [rsp+180h+phkResult], r15; pdwType
0x18002ef2f  call    cs:__imp_RegGetValueW
0x18002ef35  test    eax, eax
0x18002ef37  jnz     short loc_18002EF3E
0x18002ef39  mov     ebx, r15d
0x18002ef3c  jmp     short loc_18002EF53
0x18002ef3e  mov     rcx, [rdi]; pv
0x18002ef41  mov     ebx, 3EBh
0x18002ef46  call    cs:__imp_CoTaskMemFree
0x18002ef4c  jmp     short loc_18002EF53
0x18002ef4e  mov     ebx, 0Eh
0x18002ef53  test    esi, esi
0x18002ef55  jz      short loc_18002EF62
0x18002ef57  mov     rcx, [rsp+180h+hkey]; hKey
0x18002ef5c  call    cs:__imp_RegCloseKey
0x18002ef62  test    ebx, ebx
0x18002ef64  jz      short loc_18002EF76
0x18002ef66  mov     [rdi], r15
0x18002ef69  test    ebx, ebx
0x18002ef6b  jle     short loc_18002EF76
0x18002ef6d  movzx   ebx, bx
0x18002ef70  or      ebx, 80070000h
0x18002ef76  mov     eax, ebx
0x18002ef78  mov     rcx, [rbp+80h+var_30]
0x18002ef7c  xor     rcx, rsp; StackCookie
0x18002ef7f  call    __security_check_cookie
0x18002ef84  mov     rbx, [rsp+180h+arg_18]
0x18002ef8c  add     rsp, 160h
0x18002ef93  pop     r15
0x18002ef95  pop     r14
0x18002ef97  pop     rdi
0x18002ef98  pop     rsi
0x18002ef99  pop     rbp
0x18002ef9a  retn
```
