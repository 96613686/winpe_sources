# GetWorkspaceSSPInfo(ushort const *,int &)

- ea: `0x180079eb4`
- end: `0x18007a05b`
- name: `?GetWorkspaceSSPInfo@@YAJPEBGAEAH@Z`
- size: `423`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, PVOID pvData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18007a064`

## callees

- `0x18000b1d8`
- `0x18000ec94`
- `0x180079eb4`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180079fad`
- `ADVAPI32!RegGetValueW` at `0x180079fad`
- `ADVAPI32!RegCloseKey` at `0x18007a048`
- `ADVAPI32!RegCloseKey` at `0x18007a048`
- `ADVAPI32!RegOpenKeyExW` at `0x180079ef6`
- `ADVAPI32!RegOpenKeyExW` at `0x180079ef6`

## string_xrefs

- `0x180079f9c`: `CreatedThroughSSP`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall GetWorkspaceSSPInfo(LPCWSTR lpSubKey, _DWORD *pvData)
{
  int v3; // ebx
  unsigned int v4; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS ValueW; // eax
  unsigned int v7; // edi
  unsigned int v8; // eax
  DWORD pcbData; // [rsp+80h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+88h] [rbp+20h] BYREF

  hkey = 0;
  pcbData = 0;
  v3 = RegOpenKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 0x20019u, &hkey);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v3 > 0 )
        v4 = (unsigned __int16)v3 | 0x80070000;
      else
        v4 = v3;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_9a9b29d69df23d7c330004de722d1721_Traceguids,
        CurrentThreadActivityIdPrefix,
        v4);
    }
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    goto LABEL_26;
  }
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"CreatedThroughSSP", 0x10u, 0, pvData, &pcbData);
  v3 = ValueW;
  if ( !ValueW )
  {
LABEL_25:
    v3 = 0;
    goto LABEL_26;
  }
  if ( ValueW == 2 )
  {
    *pvData = 0;
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( ValueW > 0 )
      v7 = (unsigned __int16)ValueW | 0x80070000;
    else
      v7 = ValueW;
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids, v8, v7);
  }
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
LABEL_26:
  if ( hkey )
    RegCloseKey(hkey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180079eb4  mov     rax, rsp
0x180079eb7  push    rdi
0x180079eb8  sub     rsp, 60h
0x180079ebc  mov     qword ptr [rax-20h], 0FFFFFFFFFFFFFFFEh
0x180079ec4  mov     [rax+8], rbx
0x180079ec8  mov     rdi, rdx
0x180079ecb  mov     qword ptr [rax+20h], 0
0x180079ed3  mov     dword ptr [rax+18h], 0
0x180079eda  lea     rax, [rax+20h]
0x180079ede  mov     [rsp+68h+phkResult], rax; phkResult
0x180079ee3  mov     r9d, 20019h; samDesired
0x180079ee9  xor     r8d, r8d; ulOptions
0x180079eec  mov     rdx, rcx; lpSubKey
0x180079eef  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180079ef6  call    cs:__imp_RegOpenKeyExW
0x180079efc  mov     ebx, eax
0x180079efe  test    eax, eax
0x180079f00  jz      short loc_180079F70
0x180079f02  lea     rcx, WPP_GLOBAL_Control
0x180079f09  mov     rax, cs:WPP_GLOBAL_Control
0x180079f10  cmp     rax, rcx
0x180079f13  jz      short loc_180079F5A
0x180079f15  test    byte ptr [rax+1Ch], 8
0x180079f19  jz      short loc_180079F5A
0x180079f1b  cmp     byte ptr [rax+19h], 2
0x180079f1f  jb      short loc_180079F5A
0x180079f21  test    ebx, ebx
0x180079f23  jg      short loc_180079F29
0x180079f25  mov     edi, ebx
0x180079f27  jmp     short loc_180079F32
0x180079f29  movzx   edi, bx
0x180079f2c  or      edi, 80070000h
0x180079f32  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079f37  mov     edx, 17h
0x180079f3c  mov     dword ptr [rsp+68h+phkResult], edi
0x180079f40  mov     r9d, eax
0x180079f43  lea     r8, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids
0x180079f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180079f51  mov     rcx, [rcx+10h]
0x180079f55  call    WPP_SF_Dd
0x180079f5a  test    ebx, ebx
0x180079f5c  jle     short loc_180079F67
0x180079f5e  movzx   ebx, bx
0x180079f61  or      ebx, 80070000h
0x180079f67  mov     [rsp+68h+var_28], ebx
0x180079f6b  jmp     loc_18007A03B
0x180079f70  mov     [rsp+68h+arg_10], 4
0x180079f7b  lea     rax, [rsp+68h+arg_10]
0x180079f83  mov     [rsp+68h+pcbData], rax; pcbData
0x180079f88  mov     [rsp+68h+pvData], rdi; pvData
0x180079f8d  mov     [rsp+68h+phkResult], 0; pdwType
0x180079f96  mov     r9d, 10h; dwFlags
0x180079f9c  lea     r8, aCreatedthrough; "CreatedThroughSSP"
0x180079fa3  xor     edx, edx; lpSubKey
0x180079fa5  mov     rcx, [rsp+68h+hkey]; hkey
0x180079fad  call    cs:__imp_RegGetValueW
0x180079fb3  mov     ebx, eax
0x180079fb5  test    eax, eax
0x180079fb7  jz      short loc_18007A031
0x180079fb9  cmp     eax, 2
0x180079fbc  jnz     short loc_180079FC6
0x180079fbe  mov     dword ptr [rdi], 0
0x180079fc4  jmp     short loc_18007A031
0x180079fc6  lea     rcx, WPP_GLOBAL_Control
0x180079fcd  mov     rax, cs:WPP_GLOBAL_Control
0x180079fd4  cmp     rax, rcx
0x180079fd7  jz      short loc_18007A01E
0x180079fd9  test    byte ptr [rax+1Ch], 8
0x180079fdd  jz      short loc_18007A01E
0x180079fdf  cmp     byte ptr [rax+19h], 2
0x180079fe3  jb      short loc_18007A01E
0x180079fe5  test    ebx, ebx
0x180079fe7  jg      short loc_180079FED
0x180079fe9  mov     edi, ebx
0x180079feb  jmp     short loc_180079FF6
0x180079fed  movzx   edi, bx
0x180079ff0  or      edi, 80070000h
0x180079ff6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079ffb  mov     edx, 18h
0x18007a000  mov     dword ptr [rsp+68h+phkResult], edi
0x18007a004  mov     r9d, eax
0x18007a007  lea     r8, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids
0x18007a00e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a015  mov     rcx, [rcx+10h]
0x18007a019  call    WPP_SF_Dd
0x18007a01e  test    ebx, ebx
0x18007a020  jle     short loc_18007A02B
0x18007a022  movzx   ebx, bx
0x18007a025  or      ebx, 80070000h
0x18007a02b  mov     [rsp+68h+var_28], ebx
0x18007a02f  jmp     short loc_18007A03B
0x18007a031  xor     ebx, ebx
0x18007a033  jmp     short loc_18007A03B
0x18007a035  jmp     short $+2
0x18007a037  mov     ebx, [rsp+68h+var_28]
0x18007a03b  mov     rcx, [rsp+68h+hkey]; hKey
0x18007a043  test    rcx, rcx
0x18007a046  jz      short loc_18007A04E
0x18007a048  call    cs:__imp_RegCloseKey
0x18007a04e  mov     eax, ebx
0x18007a050  mov     rbx, [rsp+68h+arg_0]
0x18007a055  add     rsp, 60h
0x18007a059  pop     rdi
0x18007a05a  retn
```
