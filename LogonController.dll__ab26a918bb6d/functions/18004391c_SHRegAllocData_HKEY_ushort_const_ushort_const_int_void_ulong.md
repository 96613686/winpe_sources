# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x18004391c`
- end: `0x180043abc`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `416`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, DWORD, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005c3e0`
- `0x18006a2a8`

## callees

- `0x18004391c`
- `0x18006c000`
- `0x18009b79c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043a30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043a30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043aa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043aa7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800439fc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043a82`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800439fc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043a82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800439c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800439c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043a19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043a19`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        void **a5,
        unsigned int *a6)
{
  int v8; // ebx
  int v9; // r14d
  LSTATUS v11; // eax
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  hkey = a1;
  if ( a2 && *a2 )
  {
    v9 = 1;
    v11 = RegOpenKeyExW(a1, a2, 0, 1u, &hkey);
    a1 = hkey;
    v8 = v11;
  }
  else
  {
    v8 = 0;
    v9 = 0;
  }
  if ( v8 )
    goto LABEL_4;
  pcbData = 256;
  ValueW = RegGetValueW(a1, 0, a3, a4, 0, Src, &pcbData);
  v8 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v8 )
      {
        if ( RegGetValueW(hkey, 0, a3, a4, 0, pvData, &pcbData) )
        {
          v8 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          if ( a6 )
            *a6 = pcbData;
          v8 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
        if ( a6 )
          *a6 = pcbData;
      }
    }
    else
    {
      v8 = 14;
    }
  }
  if ( v9 )
    RegCloseKey(hkey);
  if ( v8 )
  {
LABEL_4:
    *a5 = 0;
    if ( a6 )
      *a6 = 0;
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004391c  push    rbp
0x18004391e  push    rbx
0x18004391f  push    rsi
0x180043920  push    rdi
0x180043921  push    r12
0x180043923  push    r13
0x180043925  push    r14
0x180043927  push    r15
0x180043929  lea     rbp, [rsp-68h]
0x18004392e  sub     rsp, 168h
0x180043935  mov     rax, cs:__security_cookie
0x18004393c  xor     rax, rsp
0x18004393f  mov     [rbp+0A0h+var_50], rax
0x180043943  mov     rsi, [rbp+0A0h+arg_20]
0x18004394a  xor     r13d, r13d
0x18004394d  mov     rdi, [rbp+0A0h+arg_28]
0x180043954  mov     r12d, r9d
0x180043957  mov     [rsp+1A0h+hkey], rcx
0x18004395c  mov     r15, r8
0x18004395f  test    rdx, rdx
0x180043962  jnz     short loc_1800439A8
0x180043964  mov     ebx, r13d
0x180043967  mov     r14d, r13d
0x18004396a  test    ebx, ebx
0x18004396c  jz      short loc_1800439D3
0x18004396e  mov     [rsi], r13
0x180043971  test    rdi, rdi
0x180043974  jz      short loc_180043979
0x180043976  mov     [rdi], r13d
0x180043979  test    ebx, ebx
0x18004397b  jle     short loc_180043986
0x18004397d  movzx   ebx, bx
0x180043980  or      ebx, 80070000h
0x180043986  mov     eax, ebx
0x180043988  mov     rcx, [rbp+0A0h+var_50]
0x18004398c  xor     rcx, rsp; StackCookie
0x18004398f  call    __security_check_cookie
0x180043994  add     rsp, 168h
0x18004399b  pop     r15
0x18004399d  pop     r14
0x18004399f  pop     r13
0x1800439a1  pop     r12
0x1800439a3  pop     rdi
0x1800439a4  pop     rsi
0x1800439a5  pop     rbx
0x1800439a6  pop     rbp
0x1800439a7  retn
0x1800439a8  cmp     [rdx], r13w
0x1800439ac  jz      short loc_180043964
0x1800439ae  lea     rax, [rsp+1A0h+hkey]
0x1800439b3  mov     r14d, 1
0x1800439b9  mov     r9d, r14d; samDesired
0x1800439bc  mov     [rsp+1A0h+phkResult], rax; phkResult
0x1800439c1  xor     r8d, r8d; ulOptions
0x1800439c4  call    cs:__imp_RegOpenKeyExW
0x1800439ca  mov     rcx, [rsp+1A0h+hkey]; hkey
0x1800439cf  mov     ebx, eax
0x1800439d1  jmp     short loc_18004396A
0x1800439d3  lea     rax, [rsp+1A0h+var_160]
0x1800439d8  mov     [rsp+1A0h+var_160], 100h
0x1800439e0  mov     [rsp+1A0h+pcbData], rax; pcbData
0x1800439e5  mov     r9d, r12d; dwFlags
0x1800439e8  lea     rax, [rsp+1A0h+Src]
0x1800439ed  mov     r8, r15; lpValue
0x1800439f0  mov     [rsp+1A0h+pvData], rax; pvData
0x1800439f5  xor     edx, edx; lpSubKey
0x1800439f7  mov     [rsp+1A0h+phkResult], r13; pdwType
0x1800439fc  call    cs:__imp_RegGetValueW
0x180043a02  mov     ebx, eax
0x180043a04  test    eax, eax
0x180043a06  jz      short loc_180043A2C
0x180043a08  cmp     eax, 0EAh
0x180043a0d  jz      short loc_180043A2C
0x180043a0f  test    r14d, r14d
0x180043a12  jz      short loc_180043A1F
0x180043a14  mov     rcx, [rsp+1A0h+hkey]; hKey
0x180043a19  call    cs:__imp_RegCloseKey
0x180043a1f  test    ebx, ebx
0x180043a21  jz      loc_180043986
0x180043a27  jmp     loc_18004396E
0x180043a2c  mov     ecx, [rsp+1A0h+var_160]; cb
0x180043a30  call    cs:__imp_CoTaskMemAlloc
0x180043a36  mov     [rsi], rax
0x180043a39  test    rax, rax
0x180043a3c  jz      short loc_180043AB2
0x180043a3e  test    ebx, ebx
0x180043a40  jnz     short loc_180043A61
0x180043a42  mov     r8d, [rsp+1A0h+var_160]; Size
0x180043a47  lea     rdx, [rsp+1A0h+Src]; Src
0x180043a4c  mov     rcx, rax; void *
0x180043a4f  call    memcpy_0
0x180043a54  test    rdi, rdi
0x180043a57  jz      short loc_180043A0F
0x180043a59  mov     eax, [rsp+1A0h+var_160]
0x180043a5d  mov     [rdi], eax
0x180043a5f  jmp     short loc_180043A0F
0x180043a61  lea     rcx, [rsp+1A0h+var_160]
0x180043a66  mov     r9d, r12d; dwFlags
0x180043a69  mov     [rsp+1A0h+pcbData], rcx; pcbData
0x180043a6e  mov     r8, r15; lpValue
0x180043a71  mov     rcx, [rsp+1A0h+hkey]; hkey
0x180043a76  xor     edx, edx; lpSubKey
0x180043a78  mov     [rsp+1A0h+pvData], rax; pvData
0x180043a7d  mov     [rsp+1A0h+phkResult], r13; pdwType
0x180043a82  call    cs:__imp_RegGetValueW
0x180043a88  test    eax, eax
0x180043a8a  jnz     short loc_180043A9F
0x180043a8c  test    rdi, rdi
0x180043a8f  jz      short loc_180043A97
0x180043a91  mov     eax, [rsp+1A0h+var_160]
0x180043a95  mov     [rdi], eax
0x180043a97  mov     ebx, r13d
0x180043a9a  jmp     loc_180043A0F
0x180043a9f  mov     rcx, [rsi]; pv
0x180043aa2  mov     ebx, 3EBh
0x180043aa7  call    cs:__imp_CoTaskMemFree
0x180043aad  jmp     loc_180043A0F
0x180043ab2  mov     ebx, 0Eh
0x180043ab7  jmp     loc_180043A0F
```
