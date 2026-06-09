# UtilRegGetQWORD(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64,bool *,bool)

- ea: `0x140016288`
- end: `0x140016375`
- name: `?UtilRegGetQWORD@@YA_KPEAUHKEY__@@PEB_W1_KPEA_N_N@Z`
- size: `237`
- prototype: `unsigned __int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, unsigned __int64@<r9>, bool *, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140012cc4`
- `0x140029ffc`

## callees

- `0x14000551c`
- `0x140016288`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140016328`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140016328`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016358`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016358`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400162e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400162e8`

## pseudocode

```c
__int64 __fastcall UtilRegGetQWORD(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValue, __int64 a4, bool *a5, DWORD pcbData)
{
  bool *v6; // rdi
  HKEY *phkResult; // rax
  __int64 v11; // rbx
  HKEY hkey; // [rsp+60h] [rbp+8h] BYREF
  __int64 pvData; // [rsp+78h] [rbp+20h] BYREF

  v6 = a5;
  pvData = 0;
  pcbData = 8;
  hkey = 0;
  if ( a5 )
    *a5 = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  if ( RegOpenKeyExW(hKey, lpSubKey, 0, 0x101u, phkResult)
    || RegGetValueW(hkey, 0, lpValue, 0x40u, 0, &pvData, &pcbData) )
  {
    v11 = 0;
    pvData = 0;
    if ( v6 )
      *v6 = 1;
  }
  else
  {
    v11 = pvData;
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v11;
}

```

## disassembly

```asm
0x140016288  mov     rax, rsp
0x14001628b  mov     [rax+10h], rbx
0x14001628f  mov     [rax+20h], r9
0x140016293  push    rbp
0x140016294  push    rsi
0x140016295  push    rdi
0x140016296  sub     rsp, 40h
0x14001629a  mov     rdi, [rsp+58h+arg_20]
0x1400162a2  mov     rbx, r8
0x1400162a5  mov     qword ptr [rax+20h], 0
0x1400162ad  mov     rsi, rdx
0x1400162b0  mov     dword ptr [rax+30h], 8
0x1400162b7  mov     rbp, rcx
0x1400162ba  mov     qword ptr [rax+8], 0
0x1400162c2  test    rdi, rdi
0x1400162c5  jz      short loc_1400162CA
0x1400162c7  mov     byte ptr [rdi], 0
0x1400162ca  lea     rcx, [rsp+58h+hkey]
0x1400162cf  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400162d4  mov     r9d, 101h; samDesired
0x1400162da  mov     [rsp+58h+phkResult], rax; phkResult
0x1400162df  xor     r8d, r8d; ulOptions
0x1400162e2  mov     rdx, rsi; lpSubKey
0x1400162e5  mov     rcx, rbp; hKey
0x1400162e8  call    cs:__imp_RegOpenKeyExW
0x1400162ef  nop     dword ptr [rax+rax+00h]
0x1400162f4  test    eax, eax
0x1400162f6  jnz     short loc_14001633F
0x1400162f8  mov     rcx, [rsp+58h+hkey]; hkey
0x1400162fd  lea     rax, [rsp+58h+arg_28]
0x140016305  mov     [rsp+58h+pcbData], rax; pcbData
0x14001630a  mov     r9d, 40h ; '@'; dwFlags
0x140016310  lea     rax, [rsp+58h+arg_18]
0x140016315  mov     r8, rbx; lpValue
0x140016318  mov     [rsp+58h+pvData], rax; pvData
0x14001631d  xor     edx, edx; lpSubKey
0x14001631f  mov     [rsp+58h+phkResult], 0; pdwType
0x140016328  call    cs:__imp_RegGetValueW
0x14001632f  nop     dword ptr [rax+rax+00h]
0x140016334  test    eax, eax
0x140016336  jnz     short loc_14001633F
0x140016338  mov     rbx, [rsp+58h+arg_18]
0x14001633d  jmp     short loc_14001634E
0x14001633f  xor     ebx, ebx
0x140016341  mov     [rsp+58h+arg_18], rbx
0x140016346  test    rdi, rdi
0x140016349  jz      short loc_14001634E
0x14001634b  mov     byte ptr [rdi], 1
0x14001634e  mov     rcx, [rsp+58h+hkey]; hKey
0x140016353  test    rcx, rcx
0x140016356  jz      short loc_140016364
0x140016358  call    cs:__imp_RegCloseKey
0x14001635f  nop     dword ptr [rax+rax+00h]
0x140016364  mov     rax, rbx
0x140016367  mov     rbx, [rsp+58h+arg_8]
0x14001636c  add     rsp, 40h
0x140016370  pop     rdi
0x140016371  pop     rsi
0x140016372  pop     rbp
0x140016373  retn
```
