# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x18004e624`
- end: `0x18004e7b8`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `404`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800501e0`
- `0x180050298`
- `0x180129700`
- `0x180129c00`
- `0x18012a498`
- `0x180163ed0`
- `0x180196600`
- `0x1801981c8`
- `0x180199cb0`
- `0x18019bdf8`
- `0x18019f5c0`

## callees

- `0x18000c840`
- `0x180010e41`
- `0x18004e624`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e756`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e756`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e6e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e6e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004e6c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004e739`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004e6c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004e739`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e772`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e772`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004e67b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004e67b`

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
0x18004e624  mov     [rsp-8+arg_18], rbx
0x18004e629  push    rbp
0x18004e62a  push    rsi
0x18004e62b  push    rdi
0x18004e62c  push    r14
0x18004e62e  push    r15
0x18004e630  lea     rbp, [rsp-60h]
0x18004e635  sub     rsp, 160h
0x18004e63c  mov     rax, cs:__security_cookie
0x18004e643  xor     rax, rsp
0x18004e646  mov     [rbp+80h+var_30], rax
0x18004e64a  mov     rdi, [rbp+80h+arg_20]
0x18004e651  xor     r15d, r15d
0x18004e654  mov     [rsp+180h+hkey], rcx
0x18004e659  mov     r14, r8
0x18004e65c  test    rdx, rdx
0x18004e65f  jz      short loc_18004E690
0x18004e661  cmp     [rdx], r15w
0x18004e665  jz      short loc_18004E690
0x18004e667  lea     rax, [rsp+180h+hkey]
0x18004e66c  xor     r8d, r8d; ulOptions
0x18004e66f  lea     esi, [r15+1]
0x18004e673  mov     [rsp+180h+phkResult], rax; phkResult
0x18004e678  mov     r9d, esi; samDesired
0x18004e67b  call    cs:__imp_RegOpenKeyExW
0x18004e682  nop     dword ptr [rax+rax+00h]
0x18004e687  mov     rcx, [rsp+180h+hkey]; hkey
0x18004e68c  mov     ebx, eax
0x18004e68e  jmp     short loc_18004E696
0x18004e690  mov     ebx, r15d
0x18004e693  mov     esi, r15d
0x18004e696  test    ebx, ebx
0x18004e698  jnz     loc_18004E782
0x18004e69e  lea     rax, [rsp+180h+var_140]
0x18004e6a3  mov     [rsp+180h+var_140], 100h
0x18004e6ab  mov     [rsp+180h+pcbData], rax; pcbData
0x18004e6b0  lea     r9d, [rbx+2]; dwFlags
0x18004e6b4  lea     rax, [rsp+180h+Src]
0x18004e6b9  mov     r8, r14; lpValue
0x18004e6bc  mov     [rsp+180h+pvData], rax; pvData
0x18004e6c1  xor     edx, edx; lpSubKey
0x18004e6c3  mov     [rsp+180h+phkResult], r15; pdwType
0x18004e6c8  call    cs:__imp_RegGetValueW
0x18004e6cf  nop     dword ptr [rax+rax+00h]
0x18004e6d4  mov     ebx, eax
0x18004e6d6  test    eax, eax
0x18004e6d8  jz      short loc_18004E6E5
0x18004e6da  cmp     eax, 0EAh
0x18004e6df  jnz     loc_18004E769
0x18004e6e5  mov     ecx, [rsp+180h+var_140]; cb
0x18004e6e9  call    cs:__imp_CoTaskMemAlloc
0x18004e6f0  nop     dword ptr [rax+rax+00h]
0x18004e6f5  mov     [rdi], rax
0x18004e6f8  test    rax, rax
0x18004e6fb  jz      short loc_18004E764
0x18004e6fd  test    ebx, ebx
0x18004e6ff  jnz     short loc_18004E715
0x18004e701  mov     r8d, [rsp+180h+var_140]; Size
0x18004e706  lea     rdx, [rsp+180h+Src]; Src
0x18004e70b  mov     rcx, rax; void *
0x18004e70e  call    memcpy_0
0x18004e713  jmp     short loc_18004E769
0x18004e715  lea     rcx, [rsp+180h+var_140]
0x18004e71a  mov     r9d, 2; dwFlags
0x18004e720  mov     [rsp+180h+pcbData], rcx; pcbData
0x18004e725  mov     r8, r14; lpValue
0x18004e728  mov     rcx, [rsp+180h+hkey]; hkey
0x18004e72d  xor     edx, edx; lpSubKey
0x18004e72f  mov     [rsp+180h+pvData], rax; pvData
0x18004e734  mov     [rsp+180h+phkResult], r15; pdwType
0x18004e739  call    cs:__imp_RegGetValueW
0x18004e740  nop     dword ptr [rax+rax+00h]
0x18004e745  test    eax, eax
0x18004e747  jnz     short loc_18004E74E
0x18004e749  mov     ebx, r15d
0x18004e74c  jmp     short loc_18004E769
0x18004e74e  mov     rcx, [rdi]; pv
0x18004e751  mov     ebx, 3EBh
0x18004e756  call    cs:__imp_CoTaskMemFree
0x18004e75d  nop     dword ptr [rax+rax+00h]
0x18004e762  jmp     short loc_18004E769
0x18004e764  mov     ebx, 0Eh
0x18004e769  test    esi, esi
0x18004e76b  jz      short loc_18004E77E
0x18004e76d  mov     rcx, [rsp+180h+hkey]; hKey
0x18004e772  call    cs:__imp_RegCloseKey
0x18004e779  nop     dword ptr [rax+rax+00h]
0x18004e77e  test    ebx, ebx
0x18004e780  jz      short loc_18004E792
0x18004e782  mov     [rdi], r15
0x18004e785  test    ebx, ebx
0x18004e787  jle     short loc_18004E792
0x18004e789  movzx   ebx, bx
0x18004e78c  or      ebx, 80070000h
0x18004e792  mov     eax, ebx
0x18004e794  mov     rcx, [rbp+80h+var_30]
0x18004e798  xor     rcx, rsp; StackCookie
0x18004e79b  call    __security_check_cookie
0x18004e7a0  mov     rbx, [rsp+180h+arg_18]
0x18004e7a8  add     rsp, 160h
0x18004e7af  pop     r15
0x18004e7b1  pop     r14
0x18004e7b3  pop     rdi
0x18004e7b4  pop     rsi
0x18004e7b5  pop     rbp
0x18004e7b6  retn
```
