# UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)

- ea: `0x14001211c`
- end: `0x14001220a`
- name: `?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z`
- size: `238`
- prototype: `unsigned int __usercall@<eax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, unsigned int@<r9d>, bool *, bool)`
- caller_count: `16`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140010a7c`
- `0x1400135c0`
- `0x14001d1f8`
- `0x14001dd84`
- `0x14001eb14`
- `0x140021f40`
- `0x140023a6c`
- `0x14002f31c`
- `0x14002fee0`
- `0x14003494c`
- `0x14003f55c`
- `0x140043d54`
- `0x140043f20`
- `0x1400442d4`
- `0x1400450ac`
- `0x140053f7c`

## callees

- `0x140005468`
- `0x14001211c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400121b5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400121b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400121ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400121ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001217b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001217b`

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
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
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
0x14001211c  mov     rax, rsp
0x14001211f  mov     [rax+10h], rbx
0x140012123  mov     [rax+18h], rbp
0x140012127  push    rsi
0x140012128  push    rdi
0x140012129  push    r14
0x14001212b  sub     rsp, 40h
0x14001212f  mov     rdi, [rsp+58h+arg_20]
0x140012137  mov     ebx, r9d
0x14001213a  mov     [rax+30h], ebx
0x14001213d  mov     rsi, r8
0x140012140  mov     dword ptr [rax+20h], 4
0x140012147  mov     rbp, rdx
0x14001214a  mov     qword ptr [rax+8], 0
0x140012152  mov     r14, rcx
0x140012155  test    rdi, rdi
0x140012158  jz      short loc_14001215D
0x14001215a  mov     byte ptr [rdi], 0
0x14001215d  lea     rcx, [rsp+58h+hkey]
0x140012162  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140012167  mov     r9d, 101h; samDesired
0x14001216d  mov     [rsp+58h+phkResult], rax; phkResult
0x140012172  xor     r8d, r8d; ulOptions
0x140012175  mov     rdx, rbp; lpSubKey
0x140012178  mov     rcx, r14; hKey
0x14001217b  call    cs:__imp_RegOpenKeyExW
0x140012181  test    eax, eax
0x140012183  jnz     short loc_1400121BF
0x140012185  mov     rcx, [rsp+58h+hkey]; hkey
0x14001218a  lea     rax, [rsp+58h+arg_18]
0x14001218f  mov     [rsp+58h+pcbData], rax; pcbData
0x140012194  mov     r9d, 10h; dwFlags
0x14001219a  lea     rax, [rsp+58h+arg_28]
0x1400121a2  mov     r8, rsi; lpValue
0x1400121a5  mov     [rsp+58h+pvData], rax; pvData
0x1400121aa  xor     edx, edx; lpSubKey
0x1400121ac  mov     [rsp+58h+phkResult], 0; pdwType
0x1400121b5  call    cs:__imp_RegGetValueW
0x1400121bb  test    eax, eax
0x1400121bd  jz      short loc_1400121DE
0x1400121bf  jle     short loc_1400121CB
0x1400121c1  movzx   eax, ax
0x1400121c4  or      eax, 80070000h
0x1400121c9  test    eax, eax
0x1400121cb  jns     short loc_1400121DE
0x1400121cd  mov     [rsp+58h+arg_28], ebx
0x1400121d4  test    rdi, rdi
0x1400121d7  jz      short loc_1400121E5
0x1400121d9  mov     byte ptr [rdi], 1
0x1400121dc  jmp     short loc_1400121E5
0x1400121de  mov     ebx, [rsp+58h+arg_28]
0x1400121e5  mov     rcx, [rsp+58h+hkey]; hKey
0x1400121ea  test    rcx, rcx
0x1400121ed  jz      short loc_1400121F5
0x1400121ef  call    cs:__imp_RegCloseKey
0x1400121f5  mov     rbp, [rsp+58h+arg_10]
0x1400121fa  mov     eax, ebx
0x1400121fc  mov     rbx, [rsp+58h+arg_8]
0x140012201  add     rsp, 40h
0x140012205  pop     r14
0x140012207  pop     rdi
0x140012208  pop     rsi
0x140012209  retn
```
