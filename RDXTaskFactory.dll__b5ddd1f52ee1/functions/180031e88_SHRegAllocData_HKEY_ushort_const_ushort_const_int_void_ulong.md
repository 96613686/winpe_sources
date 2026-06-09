# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x180031e88`
- end: `0x180032010`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `392`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800464a0`

## callees

- `0x180003390`
- `0x1800056e1`
- `0x180031e88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031f22`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031f9a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031f22`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031f9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031edb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031edb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031fcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031fcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031fbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031fbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031f3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031f3d`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5,
        unsigned int *a6)
{
  LSTATUS v6; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  hkey = HKEY_LOCAL_MACHINE;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", 0, 1u, &hkey);
  if ( v6 )
    goto LABEL_15;
  pcbData = 256;
  ValueW = RegGetValueW(hkey, 0, L"ConnectedCredentials", 8u, 0, Src, &pcbData);
  v6 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v6 )
      {
        if ( RegGetValueW(hkey, 0, L"ConnectedCredentials", 8u, 0, pvData, &pcbData) )
        {
          v6 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          if ( a6 )
            *a6 = pcbData;
          v6 = 0;
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
      v6 = 14;
    }
  }
  RegCloseKey(hkey);
  if ( v6 )
  {
LABEL_15:
    *a5 = 0;
    if ( a6 )
      *a6 = 0;
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180031e88  push    rbp
0x180031e8a  push    rbx
0x180031e8b  push    rsi
0x180031e8c  push    rdi
0x180031e8d  lea     rbp, [rsp-68h]
0x180031e92  sub     rsp, 168h
0x180031e99  mov     rax, cs:__security_cookie
0x180031ea0  xor     rax, rsp
0x180031ea3  mov     [rbp+80h+var_30], rax
0x180031ea7  mov     rsi, [rbp+80h+arg_20]
0x180031eae  lea     rax, [rsp+180h+hkey]
0x180031eb3  mov     rdi, [rbp+80h+arg_28]
0x180031eba  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows NT\\Curren"...
0x180031ec1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031ec8  mov     [rsp+180h+phkResult], rax; phkResult
0x180031ecd  mov     r9d, 1; samDesired
0x180031ed3  mov     [rsp+180h+hkey], rcx
0x180031ed8  xor     r8d, r8d; ulOptions
0x180031edb  call    cs:__imp_RegOpenKeyExW
0x180031ee1  mov     ebx, eax
0x180031ee3  test    eax, eax
0x180031ee5  jnz     loc_180031FD7
0x180031eeb  mov     rcx, [rsp+180h+hkey]; hkey
0x180031ef0  lea     rax, [rsp+180h+var_140]
0x180031ef5  mov     [rsp+180h+pcbData], rax; pcbData
0x180031efa  lea     r9d, [rbx+8]; dwFlags
0x180031efe  lea     rax, [rsp+180h+Src]
0x180031f03  mov     [rsp+180h+var_140], 100h
0x180031f0b  mov     [rsp+180h+pvData], rax; pvData
0x180031f10  lea     r8, aConnectedcrede; "ConnectedCredentials"
0x180031f17  xor     edx, edx; lpSubKey
0x180031f19  mov     [rsp+180h+phkResult], 0; pdwType
0x180031f22  call    cs:__imp_RegGetValueW
0x180031f28  mov     ebx, eax
0x180031f2a  test    eax, eax
0x180031f2c  jz      short loc_180031F39
0x180031f2e  cmp     eax, 0EAh
0x180031f33  jnz     loc_180031FC8
0x180031f39  mov     ecx, [rsp+180h+var_140]; cb
0x180031f3d  call    cs:__imp_CoTaskMemAlloc
0x180031f43  mov     [rsi], rax
0x180031f46  test    rax, rax
0x180031f49  jz      short loc_180031FC3
0x180031f4b  test    ebx, ebx
0x180031f4d  jnz     short loc_180031F6E
0x180031f4f  mov     r8d, [rsp+180h+var_140]; Size
0x180031f54  lea     rdx, [rsp+180h+Src]; Src
0x180031f59  mov     rcx, rax; void *
0x180031f5c  call    memcpy_0
0x180031f61  test    rdi, rdi
0x180031f64  jz      short loc_180031FC8
0x180031f66  mov     eax, [rsp+180h+var_140]
0x180031f6a  mov     [rdi], eax
0x180031f6c  jmp     short loc_180031FC8
0x180031f6e  lea     rcx, [rsp+180h+var_140]
0x180031f73  mov     r9d, 8; dwFlags
0x180031f79  mov     [rsp+180h+pcbData], rcx; pcbData
0x180031f7e  lea     r8, aConnectedcrede; "ConnectedCredentials"
0x180031f85  mov     rcx, [rsp+180h+hkey]; hkey
0x180031f8a  xor     edx, edx; lpSubKey
0x180031f8c  mov     [rsp+180h+pvData], rax; pvData
0x180031f91  mov     [rsp+180h+phkResult], 0; pdwType
0x180031f9a  call    cs:__imp_RegGetValueW
0x180031fa0  test    eax, eax
0x180031fa2  jnz     short loc_180031FB3
0x180031fa4  test    rdi, rdi
0x180031fa7  jz      short loc_180031FAF
0x180031fa9  mov     eax, [rsp+180h+var_140]
0x180031fad  mov     [rdi], eax
0x180031faf  xor     ebx, ebx
0x180031fb1  jmp     short loc_180031FC8
0x180031fb3  mov     rcx, [rsi]; pv
0x180031fb6  mov     ebx, 3EBh
0x180031fbb  call    cs:__imp_CoTaskMemFree
0x180031fc1  jmp     short loc_180031FC8
0x180031fc3  mov     ebx, 0Eh
0x180031fc8  mov     rcx, [rsp+180h+hkey]; hKey
0x180031fcd  call    cs:__imp_RegCloseKey
0x180031fd3  test    ebx, ebx
0x180031fd5  jz      short loc_180031FF6
0x180031fd7  mov     qword ptr [rsi], 0
0x180031fde  test    rdi, rdi
0x180031fe1  jz      short loc_180031FE9
0x180031fe3  mov     dword ptr [rdi], 0
0x180031fe9  test    ebx, ebx
0x180031feb  jle     short loc_180031FF6
0x180031fed  movzx   ebx, bx
0x180031ff0  or      ebx, 80070000h
0x180031ff6  mov     eax, ebx
0x180031ff8  mov     rcx, [rbp+80h+var_30]
0x180031ffc  xor     rcx, rsp; StackCookie
0x180031fff  call    __security_check_cookie
0x180032004  add     rsp, 168h
0x18003200b  pop     rdi
0x18003200c  pop     rsi
0x18003200d  pop     rbx
0x18003200e  pop     rbp
0x18003200f  retn
```
