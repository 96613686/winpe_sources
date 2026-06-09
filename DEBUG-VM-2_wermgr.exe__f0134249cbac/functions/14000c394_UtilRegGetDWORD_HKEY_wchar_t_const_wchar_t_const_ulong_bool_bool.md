# UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)

- ea: `0x14000c394`
- end: `0x14000c482`
- name: `?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z`
- size: `238`
- prototype: `unsigned int __usercall@<eax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, unsigned int@<r9d>, bool *, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400084f4`
- `0x14001b850`

## callees

- `0x14000470c`
- `0x14000c394`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c467`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c467`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000c3f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000c3f3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000c42d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000c42d`

## pseudocode

```c
__int64 __fastcall UtilRegGetDWORD(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValue,
        unsigned int a4,
        bool *a5,
        unsigned int pvData)
{
  bool *v6; // rdi
  unsigned int v7; // ebx
  HKEY *phkResult; // rax
  LSTATUS v12; // eax
  bool v13; // sf
  bool v14; // cc
  LSTATUS ValueW; // eax
  HKEY hkey; // [rsp+60h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+20h] BYREF

  v6 = a5;
  v7 = a4;
  pvData = a4;
  pcbData = 4;
  hkey = 0;
  if ( a5 )
    *a5 = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  v12 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x101u, phkResult);
  v13 = v12 < 0;
  v14 = v12 <= 0;
  if ( !v12 )
  {
    ValueW = RegGetValueW(hkey, 0, lpValue, 0x10u, 0, &pvData, &pcbData);
    v13 = ValueW < 0;
    v14 = ValueW <= 0;
    if ( !ValueW )
      goto LABEL_10;
  }
  if ( !v14 )
    v13 = 1;
  if ( v13 )
  {
    pvData = v7;
    if ( v6 )
      *v6 = 1;
  }
  else
  {
LABEL_10:
    v7 = pvData;
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v7;
}

```

## disassembly

```asm
0x14000c394  mov     rax, rsp
0x14000c397  mov     [rax+10h], rbx
0x14000c39b  mov     [rax+18h], rbp
0x14000c39f  push    rsi
0x14000c3a0  push    rdi
0x14000c3a1  push    r14
0x14000c3a3  sub     rsp, 40h
0x14000c3a7  mov     rdi, [rsp+58h+arg_20]
0x14000c3af  mov     ebx, r9d
0x14000c3b2  mov     [rax+30h], ebx
0x14000c3b5  mov     rsi, r8
0x14000c3b8  mov     dword ptr [rax+20h], 4
0x14000c3bf  mov     rbp, rdx
0x14000c3c2  mov     qword ptr [rax+8], 0
0x14000c3ca  mov     r14, rcx
0x14000c3cd  test    rdi, rdi
0x14000c3d0  jz      short loc_14000C3D5
0x14000c3d2  mov     byte ptr [rdi], 0
0x14000c3d5  lea     rcx, [rsp+58h+hkey]
0x14000c3da  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14000c3df  mov     r9d, 101h; samDesired
0x14000c3e5  mov     [rsp+58h+phkResult], rax; phkResult
0x14000c3ea  xor     r8d, r8d; ulOptions
0x14000c3ed  mov     rdx, rbp; lpSubKey
0x14000c3f0  mov     rcx, r14; hKey
0x14000c3f3  call    cs:__imp_RegOpenKeyExW
0x14000c3f9  test    eax, eax
0x14000c3fb  jnz     short loc_14000C437
0x14000c3fd  mov     rcx, [rsp+58h+hkey]; hkey
0x14000c402  lea     rax, [rsp+58h+arg_18]
0x14000c407  mov     [rsp+58h+pcbData], rax; pcbData
0x14000c40c  mov     r9d, 10h; dwFlags
0x14000c412  lea     rax, [rsp+58h+arg_28]
0x14000c41a  mov     r8, rsi; lpValue
0x14000c41d  mov     [rsp+58h+pvData], rax; pvData
0x14000c422  xor     edx, edx; lpSubKey
0x14000c424  mov     [rsp+58h+phkResult], 0; pdwType
0x14000c42d  call    cs:__imp_RegGetValueW
0x14000c433  test    eax, eax
0x14000c435  jz      short loc_14000C456
0x14000c437  jle     short loc_14000C443
0x14000c439  movzx   eax, ax
0x14000c43c  or      eax, 80070000h
0x14000c441  test    eax, eax
0x14000c443  jns     short loc_14000C456
0x14000c445  mov     [rsp+58h+arg_28], ebx
0x14000c44c  test    rdi, rdi
0x14000c44f  jz      short loc_14000C45D
0x14000c451  mov     byte ptr [rdi], 1
0x14000c454  jmp     short loc_14000C45D
0x14000c456  mov     ebx, [rsp+58h+arg_28]
0x14000c45d  mov     rcx, [rsp+58h+hkey]; hKey
0x14000c462  test    rcx, rcx
0x14000c465  jz      short loc_14000C46D
0x14000c467  call    cs:__imp_RegCloseKey
0x14000c46d  mov     rbp, [rsp+58h+arg_10]
0x14000c472  mov     eax, ebx
0x14000c474  mov     rbx, [rsp+58h+arg_8]
0x14000c479  add     rsp, 40h
0x14000c47d  pop     r14
0x14000c47f  pop     rdi
0x14000c480  pop     rsi
0x14000c481  retn
```
