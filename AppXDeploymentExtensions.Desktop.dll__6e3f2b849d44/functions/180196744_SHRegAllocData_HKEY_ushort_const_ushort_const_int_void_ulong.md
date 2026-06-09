# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x180196744`
- end: `0x1801968e0`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `412`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801971f8`

## callees

- `0x1800aed10`
- `0x1800ba45d`
- `0x180196744`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801967eb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180196860`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801967eb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180196860`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180196899`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180196899`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019679a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019679a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019687d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019687d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019680c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019680c`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  int v5; // esi
  LSTATUS v6; // eax
  int v7; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  hkey = a1;
  if ( a2 && *a2 )
  {
    v5 = 1;
    v6 = RegOpenKeyExW(a1, a2, 0, 1u, &hkey);
    a1 = hkey;
    v7 = v6;
  }
  else
  {
    v7 = 0;
    v5 = 0;
  }
  if ( v7 )
    goto LABEL_18;
  pcbData = 256;
  ValueW = RegGetValueW(a1, 0, L"ProgId", 2u, 0, Src, &pcbData);
  v7 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v7 )
      {
        if ( RegGetValueW(hkey, 0, L"ProgId", 2u, 0, pvData, &pcbData) )
        {
          v7 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          v7 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v7 = 14;
    }
  }
  if ( v5 )
    RegCloseKey(hkey);
  if ( v7 )
  {
LABEL_18:
    *a5 = 0;
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180196744  mov     [rsp-8+arg_10], rbx
0x180196749  mov     [rsp-8+arg_18], rsi
0x18019674e  push    rbp
0x18019674f  push    rdi
0x180196750  push    r14
0x180196752  lea     rbp, [rsp-60h]
0x180196757  sub     rsp, 160h
0x18019675e  mov     rax, cs:__security_cookie
0x180196765  xor     rax, rsp
0x180196768  mov     [rbp+70h+var_20], rax
0x18019676c  mov     rdi, [rbp+70h+arg_20]
0x180196773  xor     r14d, r14d
0x180196776  mov     [rsp+170h+hkey], rcx
0x18019677b  test    rdx, rdx
0x18019677e  jz      short loc_1801967AF
0x180196780  cmp     [rdx], r14w
0x180196784  jz      short loc_1801967AF
0x180196786  lea     rax, [rsp+170h+hkey]
0x18019678b  xor     r8d, r8d; ulOptions
0x18019678e  lea     esi, [r14+1]
0x180196792  mov     [rsp+170h+phkResult], rax; phkResult
0x180196797  mov     r9d, esi; samDesired
0x18019679a  call    cs:__imp_RegOpenKeyExW
0x1801967a1  nop     dword ptr [rax+rax+00h]
0x1801967a6  mov     rcx, [rsp+170h+hkey]; hkey
0x1801967ab  mov     ebx, eax
0x1801967ad  jmp     short loc_1801967B5
0x1801967af  mov     ebx, r14d
0x1801967b2  mov     esi, r14d
0x1801967b5  test    ebx, ebx
0x1801967b7  jnz     loc_1801968A9
0x1801967bd  lea     rax, [rsp+170h+var_130]
0x1801967c2  mov     [rsp+170h+var_130], 100h
0x1801967ca  mov     [rsp+170h+pcbData], rax; pcbData
0x1801967cf  lea     r9d, [rbx+2]; dwFlags
0x1801967d3  lea     rax, [rsp+170h+Src]
0x1801967d8  xor     edx, edx; lpSubKey
0x1801967da  mov     [rsp+170h+pvData], rax; pvData
0x1801967df  lea     r8, aProgid; "ProgId"
0x1801967e6  mov     [rsp+170h+phkResult], r14; pdwType
0x1801967eb  call    cs:__imp_RegGetValueW
0x1801967f2  nop     dword ptr [rax+rax+00h]
0x1801967f7  mov     ebx, eax
0x1801967f9  test    eax, eax
0x1801967fb  jz      short loc_180196808
0x1801967fd  cmp     eax, 0EAh
0x180196802  jnz     loc_180196890
0x180196808  mov     ecx, [rsp+170h+var_130]; cb
0x18019680c  call    cs:__imp_CoTaskMemAlloc
0x180196813  nop     dword ptr [rax+rax+00h]
0x180196818  mov     [rdi], rax
0x18019681b  test    rax, rax
0x18019681e  jz      short loc_18019688B
0x180196820  test    ebx, ebx
0x180196822  jnz     short loc_180196838
0x180196824  mov     r8d, [rsp+170h+var_130]; Size
0x180196829  lea     rdx, [rsp+170h+Src]; Src
0x18019682e  mov     rcx, rax; void *
0x180196831  call    memcpy_0
0x180196836  jmp     short loc_180196890
0x180196838  lea     rcx, [rsp+170h+var_130]
0x18019683d  mov     r9d, 2; dwFlags
0x180196843  mov     [rsp+170h+pcbData], rcx; pcbData
0x180196848  lea     r8, aProgid; "ProgId"
0x18019684f  mov     rcx, [rsp+170h+hkey]; hkey
0x180196854  xor     edx, edx; lpSubKey
0x180196856  mov     [rsp+170h+pvData], rax; pvData
0x18019685b  mov     [rsp+170h+phkResult], r14; pdwType
0x180196860  call    cs:__imp_RegGetValueW
0x180196867  nop     dword ptr [rax+rax+00h]
0x18019686c  test    eax, eax
0x18019686e  jnz     short loc_180196875
0x180196870  mov     ebx, r14d
0x180196873  jmp     short loc_180196890
0x180196875  mov     rcx, [rdi]; pv
0x180196878  mov     ebx, 3EBh
0x18019687d  call    cs:__imp_CoTaskMemFree
0x180196884  nop     dword ptr [rax+rax+00h]
0x180196889  jmp     short loc_180196890
0x18019688b  mov     ebx, 0Eh
0x180196890  test    esi, esi
0x180196892  jz      short loc_1801968A5
0x180196894  mov     rcx, [rsp+170h+hkey]; hKey
0x180196899  call    cs:__imp_RegCloseKey
0x1801968a0  nop     dword ptr [rax+rax+00h]
0x1801968a5  test    ebx, ebx
0x1801968a7  jz      short loc_1801968B9
0x1801968a9  mov     [rdi], r14
0x1801968ac  test    ebx, ebx
0x1801968ae  jle     short loc_1801968B9
0x1801968b0  movzx   ebx, bx
0x1801968b3  or      ebx, 80070000h
0x1801968b9  mov     eax, ebx
0x1801968bb  mov     rcx, [rbp+70h+var_20]
0x1801968bf  xor     rcx, rsp; StackCookie
0x1801968c2  call    __security_check_cookie
0x1801968c7  lea     r11, [rsp+170h+var_10]
0x1801968cf  mov     rbx, [r11+30h]
0x1801968d3  mov     rsi, [r11+38h]
0x1801968d7  mov     rsp, r11
0x1801968da  pop     r14
0x1801968dc  pop     rdi
0x1801968dd  pop     rbp
0x1801968de  retn
```
