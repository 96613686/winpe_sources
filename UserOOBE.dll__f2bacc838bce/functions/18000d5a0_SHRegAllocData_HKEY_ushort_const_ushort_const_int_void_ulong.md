# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x18000d5a0`
- end: `0x18000d732`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `402`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ad04`
- `0x18001bf10`
- `0x180028684`
- `0x180028adc`
- `0x180029260`
- `0x18002a480`

## callees

- `0x1800032b0`
- `0x1800041e8`
- `0x18000d5a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d663`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d663`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d6d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d6d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d648`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d6b5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d648`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d6b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d602`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d602`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d6ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d6ee`

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
  int v8; // r14d
  LSTATUS v9; // eax
  int v10; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  hkey = a1;
  if ( a2 && *a2 )
  {
    v8 = 1;
    v9 = RegOpenKeyExW(a1, a2, 0, 1u, &hkey);
    a1 = hkey;
    v10 = v9;
  }
  else
  {
    v10 = 0;
    v8 = 0;
  }
  if ( v10 )
    goto LABEL_21;
  pcbData = 256;
  ValueW = RegGetValueW(a1, 0, a3, a4, 0, Src, &pcbData);
  v10 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v10 )
      {
        if ( RegGetValueW(hkey, 0, a3, a4, 0, pvData, &pcbData) )
        {
          v10 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          if ( a6 )
            *a6 = pcbData;
          v10 = 0;
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
      v10 = 14;
    }
  }
  if ( v8 )
    RegCloseKey(hkey);
  if ( v10 )
  {
LABEL_21:
    *a5 = 0;
    if ( a6 )
      *a6 = 0;
    if ( v10 > 0 )
      return (unsigned __int16)v10 | 0x80070000;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000d5a0  push    rbp
0x18000d5a2  push    rbx
0x18000d5a3  push    rsi
0x18000d5a4  push    rdi
0x18000d5a5  push    r12
0x18000d5a7  push    r13
0x18000d5a9  push    r14
0x18000d5ab  push    r15
0x18000d5ad  lea     rbp, [rsp-68h]
0x18000d5b2  sub     rsp, 168h
0x18000d5b9  mov     rax, cs:__security_cookie
0x18000d5c0  xor     rax, rsp
0x18000d5c3  mov     [rbp+0A0h+var_50], rax
0x18000d5c7  mov     rsi, [rbp+0A0h+arg_20]
0x18000d5ce  xor     r13d, r13d
0x18000d5d1  mov     rdi, [rbp+0A0h+arg_28]
0x18000d5d8  mov     r12d, r9d
0x18000d5db  mov     [rsp+1A0h+hkey], rcx
0x18000d5e0  mov     r15, r8
0x18000d5e3  test    rdx, rdx
0x18000d5e6  jz      short loc_18000D611
0x18000d5e8  cmp     [rdx], r13w
0x18000d5ec  jz      short loc_18000D611
0x18000d5ee  lea     rax, [rsp+1A0h+hkey]
0x18000d5f3  xor     r8d, r8d; ulOptions
0x18000d5f6  lea     r14d, [r13+1]
0x18000d5fa  mov     [rsp+1A0h+phkResult], rax; phkResult
0x18000d5ff  mov     r9d, r14d; samDesired
0x18000d602  call    cs:__imp_RegOpenKeyExW
0x18000d608  mov     rcx, [rsp+1A0h+hkey]; hkey
0x18000d60d  mov     ebx, eax
0x18000d60f  jmp     short loc_18000D617
0x18000d611  mov     ebx, r13d
0x18000d614  mov     r14d, r13d
0x18000d617  test    ebx, ebx
0x18000d619  jnz     loc_18000D6F8
0x18000d61f  lea     rax, [rsp+1A0h+var_160]
0x18000d624  mov     [rsp+1A0h+var_160], 100h
0x18000d62c  mov     [rsp+1A0h+pcbData], rax; pcbData
0x18000d631  mov     r9d, r12d; dwFlags
0x18000d634  lea     rax, [rsp+1A0h+Src]
0x18000d639  mov     r8, r15; lpValue
0x18000d63c  mov     [rsp+1A0h+pvData], rax; pvData
0x18000d641  xor     edx, edx; lpSubKey
0x18000d643  mov     [rsp+1A0h+phkResult], r13; pdwType
0x18000d648  call    cs:__imp_RegGetValueW
0x18000d64e  mov     ebx, eax
0x18000d650  test    eax, eax
0x18000d652  jz      short loc_18000D65F
0x18000d654  cmp     eax, 0EAh
0x18000d659  jnz     loc_18000D6E4
0x18000d65f  mov     ecx, [rsp+1A0h+var_160]; cb
0x18000d663  call    cs:__imp_CoTaskMemAlloc
0x18000d669  mov     [rsi], rax
0x18000d66c  test    rax, rax
0x18000d66f  jz      short loc_18000D6DF
0x18000d671  test    ebx, ebx
0x18000d673  jnz     short loc_18000D694
0x18000d675  mov     r8d, [rsp+1A0h+var_160]; Size
0x18000d67a  lea     rdx, [rsp+1A0h+Src]; Src
0x18000d67f  mov     rcx, rax; void *
0x18000d682  call    memcpy_0
0x18000d687  test    rdi, rdi
0x18000d68a  jz      short loc_18000D6E4
0x18000d68c  mov     eax, [rsp+1A0h+var_160]
0x18000d690  mov     [rdi], eax
0x18000d692  jmp     short loc_18000D6E4
0x18000d694  lea     rcx, [rsp+1A0h+var_160]
0x18000d699  mov     r9d, r12d; dwFlags
0x18000d69c  mov     [rsp+1A0h+pcbData], rcx; pcbData
0x18000d6a1  mov     r8, r15; lpValue
0x18000d6a4  mov     rcx, [rsp+1A0h+hkey]; hkey
0x18000d6a9  xor     edx, edx; lpSubKey
0x18000d6ab  mov     [rsp+1A0h+pvData], rax; pvData
0x18000d6b0  mov     [rsp+1A0h+phkResult], r13; pdwType
0x18000d6b5  call    cs:__imp_RegGetValueW
0x18000d6bb  test    eax, eax
0x18000d6bd  jnz     short loc_18000D6CF
0x18000d6bf  test    rdi, rdi
0x18000d6c2  jz      short loc_18000D6CA
0x18000d6c4  mov     eax, [rsp+1A0h+var_160]
0x18000d6c8  mov     [rdi], eax
0x18000d6ca  mov     ebx, r13d
0x18000d6cd  jmp     short loc_18000D6E4
0x18000d6cf  mov     rcx, [rsi]; pv
0x18000d6d2  mov     ebx, 3EBh
0x18000d6d7  call    cs:__imp_CoTaskMemFree
0x18000d6dd  jmp     short loc_18000D6E4
0x18000d6df  mov     ebx, 0Eh
0x18000d6e4  test    r14d, r14d
0x18000d6e7  jz      short loc_18000D6F4
0x18000d6e9  mov     rcx, [rsp+1A0h+hkey]; hKey
0x18000d6ee  call    cs:__imp_RegCloseKey
0x18000d6f4  test    ebx, ebx
0x18000d6f6  jz      short loc_18000D710
0x18000d6f8  mov     [rsi], r13
0x18000d6fb  test    rdi, rdi
0x18000d6fe  jz      short loc_18000D703
0x18000d700  mov     [rdi], r13d
0x18000d703  test    ebx, ebx
0x18000d705  jle     short loc_18000D710
0x18000d707  movzx   ebx, bx
0x18000d70a  or      ebx, 80070000h
0x18000d710  mov     eax, ebx
0x18000d712  mov     rcx, [rbp+0A0h+var_50]
0x18000d716  xor     rcx, rsp; StackCookie
0x18000d719  call    __security_check_cookie
0x18000d71e  add     rsp, 168h
0x18000d725  pop     r15
0x18000d727  pop     r14
0x18000d729  pop     r13
0x18000d72b  pop     r12
0x18000d72d  pop     rdi
0x18000d72e  pop     rsi
0x18000d72f  pop     rbx
0x18000d730  pop     rbp
0x18000d731  retn
```
