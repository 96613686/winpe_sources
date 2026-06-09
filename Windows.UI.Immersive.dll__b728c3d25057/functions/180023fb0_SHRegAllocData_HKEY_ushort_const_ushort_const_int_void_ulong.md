# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x180023fb0`
- end: `0x180024135`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `389`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009320`
- `0x18000ada8`
- `0x18002d43c`
- `0x180032a8c`
- `0x1800358d0`
- `0x18003d0d4`
- `0x18003feb0`
- `0x1800b0ba4`

## callees

- `0x180023fb0`
- `0x180050ba0`
- `0x180056c06`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800240e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800240e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024009`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024009`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024052`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800240b7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024052`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800240b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024069`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024069`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800240cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800240cd`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  int v6; // edi
  LSTATUS v7; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-138h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-130h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-128h] BYREF

  hkey = a1;
  if ( a2 && *a2 )
  {
    v6 = 1;
    v7 = RegOpenKeyExW(a1, a2, 0, 1u, &hkey);
    if ( v7 )
    {
LABEL_18:
      *a5 = 0;
      goto LABEL_19;
    }
    a1 = hkey;
  }
  else
  {
    v6 = 0;
  }
  pcbData = 256;
  ValueW = RegGetValueW(a1, 0, a3, 2u, 0, Src, &pcbData);
  v7 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v7 )
      {
        if ( RegGetValueW(hkey, 0, a3, 2u, 0, pvData, &pcbData) )
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
  if ( v6 )
    RegCloseKey(hkey);
  if ( v7 )
    goto LABEL_18;
LABEL_19:
  if ( v7 > 0 )
    return (unsigned __int16)v7 | 0x80070000;
  else
    return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023fb0  mov     r11, rsp
0x180023fb3  push    rbx
0x180023fb4  sub     rsp, 170h
0x180023fbb  mov     rax, cs:__security_cookie
0x180023fc2  xor     rax, rsp
0x180023fc5  mov     [rsp+178h+var_28], rax
0x180023fcd  mov     [r11+20h], rsi
0x180023fd1  mov     rsi, r8
0x180023fd4  mov     [r11-10h], rdi
0x180023fd8  mov     [r11-18h], r14
0x180023fdc  mov     r14, [rsp+178h+arg_20]
0x180023fe4  mov     [rsp+178h+hkey], rcx
0x180023fe9  test    rdx, rdx
0x180023fec  jz      short loc_180024020
0x180023fee  cmp     word ptr [rdx], 0
0x180023ff2  jz      short loc_180024020
0x180023ff4  lea     rax, [rsp+178h+hkey]
0x180023ff9  mov     edi, 1
0x180023ffe  mov     r9d, edi; samDesired
0x180024001  mov     [rsp+178h+phkResult], rax; phkResult
0x180024006  xor     r8d, r8d; ulOptions
0x180024009  call    cs:__imp_RegOpenKeyExW
0x18002400f  mov     ebx, eax
0x180024011  test    eax, eax
0x180024013  jnz     loc_1800240ED
0x180024019  mov     rcx, [rsp+178h+hkey]; hkey
0x18002401e  jmp     short loc_180024022
0x180024020  xor     edi, edi
0x180024022  lea     rax, [rsp+178h+var_138]
0x180024027  mov     [rsp+178h+var_138], 100h
0x18002402f  mov     [rsp+178h+pcbData], rax; pcbData
0x180024034  mov     r9d, 2; dwFlags
0x18002403a  lea     rax, [rsp+178h+Src]
0x18002403f  mov     r8, rsi; lpValue
0x180024042  mov     [rsp+178h+pvData], rax; pvData
0x180024047  xor     edx, edx; lpSubKey
0x180024049  mov     [rsp+178h+phkResult], 0; pdwType
0x180024052  call    cs:__imp_RegGetValueW
0x180024058  mov     ebx, eax
0x18002405a  test    eax, eax
0x18002405c  jz      short loc_180024065
0x18002405e  cmp     eax, 0EAh
0x180024063  jnz     short loc_1800240DA
0x180024065  mov     ecx, [rsp+178h+var_138]; cb
0x180024069  call    cs:__imp_CoTaskMemAlloc
0x18002406f  mov     [r14], rax
0x180024072  test    rax, rax
0x180024075  jz      short loc_1800240D5
0x180024077  test    ebx, ebx
0x180024079  jnz     short loc_18002408F
0x18002407b  mov     r8d, [rsp+178h+var_138]; Size
0x180024080  lea     rdx, [rsp+178h+Src]; Src
0x180024085  mov     rcx, rax; void *
0x180024088  call    memcpy_0
0x18002408d  jmp     short loc_1800240DA
0x18002408f  lea     rcx, [rsp+178h+var_138]
0x180024094  mov     r9d, 2; dwFlags
0x18002409a  mov     [rsp+178h+pcbData], rcx; pcbData
0x18002409f  mov     r8, rsi; lpValue
0x1800240a2  mov     rcx, [rsp+178h+hkey]; hkey
0x1800240a7  xor     edx, edx; lpSubKey
0x1800240a9  mov     [rsp+178h+pvData], rax; pvData
0x1800240ae  mov     [rsp+178h+phkResult], 0; pdwType
0x1800240b7  call    cs:__imp_RegGetValueW
0x1800240bd  test    eax, eax
0x1800240bf  jnz     short loc_1800240C5
0x1800240c1  xor     ebx, ebx
0x1800240c3  jmp     short loc_1800240DA
0x1800240c5  mov     rcx, [r14]; pv
0x1800240c8  mov     ebx, 3EBh
0x1800240cd  call    cs:__imp_CoTaskMemFree
0x1800240d3  jmp     short loc_1800240DA
0x1800240d5  mov     ebx, 0Eh
0x1800240da  test    edi, edi
0x1800240dc  jz      short loc_1800240E9
0x1800240de  mov     rcx, [rsp+178h+hkey]; hKey
0x1800240e3  call    cs:__imp_RegCloseKey
0x1800240e9  test    ebx, ebx
0x1800240eb  jz      short loc_1800240F4
0x1800240ed  mov     qword ptr [r14], 0
0x1800240f4  mov     r14, [rsp+178h+var_18]
0x1800240fc  mov     rdi, [rsp+178h+var_10]
0x180024104  mov     rsi, [rsp+178h+arg_18]
0x18002410c  test    ebx, ebx
0x18002410e  jg      short loc_180024114
0x180024110  mov     eax, ebx
0x180024112  jmp     short loc_18002411C
0x180024114  movzx   eax, bx
0x180024117  or      eax, 80070000h
0x18002411c  mov     rcx, [rsp+178h+var_28]
0x180024124  xor     rcx, rsp; StackCookie
0x180024127  call    __security_check_cookie
0x18002412c  add     rsp, 170h
0x180024133  pop     rbx
0x180024134  retn
```
