# I_ServerCacheReadDataFromDisk(uchar * *,ulong *)

- ea: `0x18002b044`
- end: `0x18002b20d`
- name: `?I_ServerCacheReadDataFromDisk@@YAKPEAPEAEPEAK@Z`
- size: `457`
- prototype: `__int64 __fastcall(unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001943c`

## callees

- `0x1800028b0`
- `0x1800075d0`
- `0x180014dc0`
- `0x180028b78`
- `0x18002ab90`
- `0x18002b044`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b0d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b0d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b105`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b186`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b105`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b186`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b1af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b1af`

## string_xrefs

- `0x18002b0c2`: `Software\Microsoft\Cryptography\Calais\Cache`
- `0x18002b0ef`: `Cache`
- `0x18002b174`: `Cache`

## pseudocode

```c
__int64 __fastcall I_ServerCacheReadDataFromDisk(unsigned __int8 **a1, unsigned int *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  BYTE *v6; // rdi
  HKEY v7; // rcx
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  cbData = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_647da024c2503459d7fafff2f0112b72_Traceguids, WPP_pszIndent);
  }
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Cryptography\\Calais\\Cache", 0, 1u, &hKey);
  if ( !v4 )
  {
    v4 = RegQueryValueExW(hKey, L"Cache", 0, 0, 0, &cbData);
    if ( !v4 )
    {
      v6 = (BYTE *)AllocH(cbData);
      if ( v6 )
      {
        v4 = RegQueryValueExW(hKey, L"Cache", 0, 0, v6, &cbData);
        if ( v4 )
        {
          ConstStringHeapFree((const unsigned __int16 *)v6);
        }
        else
        {
          *a2 = cbData;
          *a1 = v6;
        }
      }
      else
      {
        WppTraceIndent(v5, 2);
        v4 = 8;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            &WPP_647da024c2503459d7fafff2f0112b72_Traceguids,
            WPP_pszIndent);
        }
      }
    }
  }
  v7 = hKey;
  if ( hKey )
    RegCloseKey(hKey);
  WppTraceIndent(v7, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)&WPP_647da024c2503459d7fafff2f0112b72_Traceguids,
      (_DWORD)WPP_pszIndent,
      v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18002b044  mov     rax, rsp
0x18002b047  mov     [rax+8], rbx
0x18002b04b  mov     [rax+10h], rsi
0x18002b04f  push    rdi
0x18002b050  push    r13
0x18002b052  push    r14
0x18002b054  sub     rsp, 30h
0x18002b058  mov     rsi, rdx
0x18002b05b  mov     qword ptr [rax+20h], 0
0x18002b063  xor     edx, edx
0x18002b065  mov     dword ptr [rax+18h], 0
0x18002b06c  mov     r14, rcx
0x18002b06f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b074  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b07b  lea     r13, WPP_GLOBAL_Control
0x18002b082  cmp     rcx, r13
0x18002b085  jz      short loc_18002B0AF
0x18002b087  test    byte ptr [rcx+1Ch], 2
0x18002b08b  jz      short loc_18002B0AF
0x18002b08d  cmp     byte ptr [rcx+19h], 5
0x18002b091  jb      short loc_18002B0AF
0x18002b093  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002b09a  lea     r8, WPP_647da024c2503459d7fafff2f0112b72_Traceguids
0x18002b0a1  mov     rcx, [rcx+10h]
0x18002b0a5  mov     edx, 0Ch
0x18002b0aa  call    WPP_SF_s
0x18002b0af  lea     rax, [rsp+48h+hKey]
0x18002b0b4  mov     r9d, 1; samDesired
0x18002b0ba  xor     r8d, r8d; ulOptions
0x18002b0bd  mov     [rsp+48h+phkResult], rax; phkResult
0x18002b0c2  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Cryptography\\Cala"...
0x18002b0c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b0d0  call    cs:__imp_RegOpenKeyExW
0x18002b0d6  mov     ebx, eax
0x18002b0d8  test    eax, eax
0x18002b0da  jnz     loc_18002B1A5
0x18002b0e0  mov     rcx, [rsp+48h+hKey]; hKey
0x18002b0e5  lea     rax, [rsp+48h+cbData]
0x18002b0ea  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002b0ef  lea     rdx, aCache; "Cache"
0x18002b0f6  xor     r9d, r9d; lpType
0x18002b0f9  mov     [rsp+48h+phkResult], 0; lpData
0x18002b102  xor     r8d, r8d; lpReserved
0x18002b105  call    cs:__imp_RegQueryValueExW
0x18002b10b  mov     ebx, eax
0x18002b10d  test    eax, eax
0x18002b10f  jnz     loc_18002B1A5
0x18002b115  mov     ecx, [rsp+48h+cbData]; unsigned __int64
0x18002b119  call    ?AllocH@@YAPEAX_K@Z; AllocH(unsigned __int64)
0x18002b11e  mov     rdi, rax
0x18002b121  test    rax, rax
0x18002b124  jnz     short loc_18002B165
0x18002b126  lea     edx, [rbx+2]
0x18002b129  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b12e  lea     ebx, [rdi+8]
0x18002b131  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b138  cmp     rcx, r13
0x18002b13b  jz      short loc_18002B1A5
0x18002b13d  test    byte ptr [rcx+1Ch], 1
0x18002b141  jz      short loc_18002B1A5
0x18002b143  cmp     byte ptr [rcx+19h], 2
0x18002b147  jb      short loc_18002B1A5
0x18002b149  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002b150  lea     edx, [rdi+0Dh]
0x18002b153  mov     rcx, [rcx+10h]
0x18002b157  lea     r8, WPP_647da024c2503459d7fafff2f0112b72_Traceguids
0x18002b15e  call    WPP_SF_s
0x18002b163  jmp     short loc_18002B1A5
0x18002b165  mov     rcx, [rsp+48h+hKey]; hKey
0x18002b16a  lea     rax, [rsp+48h+cbData]
0x18002b16f  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002b174  lea     rdx, aCache; "Cache"
0x18002b17b  xor     r9d, r9d; lpType
0x18002b17e  mov     [rsp+48h+phkResult], rdi; lpData
0x18002b183  xor     r8d, r8d; lpReserved
0x18002b186  call    cs:__imp_RegQueryValueExW
0x18002b18c  mov     ebx, eax
0x18002b18e  test    eax, eax
0x18002b190  jnz     short loc_18002B19D
0x18002b192  mov     eax, [rsp+48h+cbData]
0x18002b196  mov     [rsi], eax
0x18002b198  mov     [r14], rdi
0x18002b19b  jmp     short loc_18002B1A5
0x18002b19d  mov     rcx, rdi; unsigned __int16 *
0x18002b1a0  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x18002b1a5  mov     rcx, [rsp+48h+hKey]; hKey
0x18002b1aa  test    rcx, rcx
0x18002b1ad  jz      short loc_18002B1B5
0x18002b1af  call    cs:__imp_RegCloseKey
0x18002b1b5  mov     edx, 1
0x18002b1ba  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b1bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1c6  cmp     rcx, r13
0x18002b1c9  jz      short loc_18002B1F7
0x18002b1cb  test    byte ptr [rcx+1Ch], 2
0x18002b1cf  jz      short loc_18002B1F7
0x18002b1d1  cmp     byte ptr [rcx+19h], 5
0x18002b1d5  jb      short loc_18002B1F7
0x18002b1d7  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002b1de  lea     r8, WPP_647da024c2503459d7fafff2f0112b72_Traceguids
0x18002b1e5  mov     rcx, [rcx+10h]
0x18002b1e9  mov     edx, 0Eh
0x18002b1ee  mov     dword ptr [rsp+48h+phkResult], ebx
0x18002b1f2  call    WPP_SF_sD
0x18002b1f7  mov     rsi, [rsp+48h+arg_8]
0x18002b1fc  mov     eax, ebx
0x18002b1fe  mov     rbx, [rsp+48h+arg_0]
0x18002b203  add     rsp, 30h
0x18002b207  pop     r14
0x18002b209  pop     r13
0x18002b20b  pop     rdi
0x18002b20c  retn
```
