# UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)

- ea: `0x140012994`
- end: `0x140012a95`
- name: `?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z`
- size: `257`
- prototype: `unsigned int __usercall@<eax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, unsigned int@<r9d>, bool *, bool)`
- caller_count: `16`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140011158`
- `0x140013f04`
- `0x14001e4a0`
- `0x14001f2dc`
- `0x140020118`
- `0x1400235a8`
- `0x1400251c0`
- `0x1400311d8`
- `0x140032050`
- `0x140036e5c`
- `0x1400420a4`
- `0x140046d00`
- `0x140046ed8`
- `0x1400472e0`
- `0x1400481cc`
- `0x140057940`

## callees

- `0x14000551c`
- `0x140012994`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140012a33`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140012a33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012a73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012a73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400129f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400129f3`

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
0x140012994  mov     rax, rsp
0x140012997  mov     [rax+10h], rbx
0x14001299b  mov     [rax+18h], rbp
0x14001299f  push    rsi
0x1400129a0  push    rdi
0x1400129a1  push    r14
0x1400129a3  sub     rsp, 40h
0x1400129a7  mov     rdi, [rsp+58h+arg_20]
0x1400129af  mov     ebx, r9d
0x1400129b2  mov     [rax+30h], ebx
0x1400129b5  mov     rsi, r8
0x1400129b8  mov     dword ptr [rax+20h], 4
0x1400129bf  mov     rbp, rdx
0x1400129c2  mov     qword ptr [rax+8], 0
0x1400129ca  mov     r14, rcx
0x1400129cd  test    rdi, rdi
0x1400129d0  jz      short loc_1400129D5
0x1400129d2  mov     byte ptr [rdi], 0
0x1400129d5  lea     rcx, [rsp+58h+hkey]
0x1400129da  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400129df  mov     r9d, 101h; samDesired
0x1400129e5  mov     [rsp+58h+phkResult], rax; phkResult
0x1400129ea  xor     r8d, r8d; ulOptions
0x1400129ed  mov     rdx, rbp; lpSubKey
0x1400129f0  mov     rcx, r14; hKey
0x1400129f3  call    cs:__imp_RegOpenKeyExW
0x1400129fa  nop     dword ptr [rax+rax+00h]
0x1400129ff  test    eax, eax
0x140012a01  jnz     short loc_140012A43
0x140012a03  mov     rcx, [rsp+58h+hkey]; hkey
0x140012a08  lea     rax, [rsp+58h+arg_18]
0x140012a0d  mov     [rsp+58h+pcbData], rax; pcbData
0x140012a12  mov     r9d, 10h; dwFlags
0x140012a18  lea     rax, [rsp+58h+arg_28]
0x140012a20  mov     r8, rsi; lpValue
0x140012a23  mov     [rsp+58h+pvData], rax; pvData
0x140012a28  xor     edx, edx; lpSubKey
0x140012a2a  mov     [rsp+58h+phkResult], 0; pdwType
0x140012a33  call    cs:__imp_RegGetValueW
0x140012a3a  nop     dword ptr [rax+rax+00h]
0x140012a3f  test    eax, eax
0x140012a41  jz      short loc_140012A62
0x140012a43  jle     short loc_140012A4F
0x140012a45  movzx   eax, ax
0x140012a48  or      eax, 80070000h
0x140012a4d  test    eax, eax
0x140012a4f  jns     short loc_140012A62
0x140012a51  mov     [rsp+58h+arg_28], ebx
0x140012a58  test    rdi, rdi
0x140012a5b  jz      short loc_140012A69
0x140012a5d  mov     byte ptr [rdi], 1
0x140012a60  jmp     short loc_140012A69
0x140012a62  mov     ebx, [rsp+58h+arg_28]
0x140012a69  mov     rcx, [rsp+58h+hkey]; hKey
0x140012a6e  test    rcx, rcx
0x140012a71  jz      short loc_140012A7F
0x140012a73  call    cs:__imp_RegCloseKey
0x140012a7a  nop     dword ptr [rax+rax+00h]
0x140012a7f  mov     rbp, [rsp+58h+arg_10]
0x140012a84  mov     eax, ebx
0x140012a86  mov     rbx, [rsp+58h+arg_8]
0x140012a8b  add     rsp, 40h
0x140012a8f  pop     r14
0x140012a91  pop     rdi
0x140012a92  pop     rsi
0x140012a93  retn
```
