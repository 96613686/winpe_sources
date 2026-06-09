# SystemSettings::DataModel::CopyCurrentUserSettings::IntlCopyRegKeyValues(HKEY__ *,HKEY__ *)

- ea: `0x1400438c8`
- end: `0x140043a59`
- name: `?IntlCopyRegKeyValues@CopyCurrentUserSettings@DataModel@SystemSettings@@CAKPEAUHKEY__@@0@Z`
- size: `401`
- prototype: `unsigned int __fastcall(HKEY hKey, HKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140043a60`

## callees

- `0x140005f30`
- `0x1400438c8`

## import_xrefs

- `KERNEL32!RegSetValueExW` at `0x140043a04`
- `KERNEL32!RegSetValueExW` at `0x140043a04`
- `KERNEL32!HeapFree` at `0x140043a26`
- `KERNEL32!HeapFree` at `0x140043a26`
- `KERNEL32!GetProcessHeap` at `0x140043975`
- `KERNEL32!GetProcessHeap` at `0x140043a18`
- `KERNEL32!GetProcessHeap` at `0x140043975`
- `KERNEL32!GetProcessHeap` at `0x140043a18`
- `KERNEL32!HeapAlloc` at `0x140043984`
- `KERNEL32!HeapAlloc` at `0x140043984`
- `KERNEL32!RegQueryInfoKeyW` at `0x140043956`
- `KERNEL32!RegQueryInfoKeyW` at `0x140043956`
- `KERNEL32!RegEnumValueW` at `0x1400439dc`
- `KERNEL32!RegEnumValueW` at `0x1400439dc`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CopyCurrentUserSettings::IntlCopyRegKeyValues(HKEY hKey, HKEY a2)
{
  unsigned int v4; // edi
  DWORD v5; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v7; // rsi
  DWORD i; // ebx
  HANDLE v9; // rax
  DWORD cValues; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchValueName; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD Type[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[256]; // [rsp+80h] [rbp-80h] BYREF

  cchValueName = 0;
  Type[0] = 0;
  cbData = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, &cbMaxValueLen, 0, 0);
  if ( !v4 )
  {
    if ( cValues )
    {
      v5 = cbMaxValueLen;
      ProcessHeap = GetProcessHeap();
      v7 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v5);
      if ( v7 )
      {
        for ( i = 0; i < cValues; ++i )
        {
          cbData = cbMaxValueLen;
          cchValueName = 256;
          v4 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, Type, v7, &cbData);
          if ( v4 )
            break;
          v4 = RegSetValueExW(a2, ValueName, 0, Type[0], v7, cbData);
          if ( v4 )
            break;
        }
        v9 = GetProcessHeap();
        HeapFree(v9, 0, v7);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1400438c8  mov     [rsp-8+arg_10], rbx
0x1400438cd  mov     [rsp-8+arg_18], rsi
0x1400438d2  push    rbp
0x1400438d3  push    rdi
0x1400438d4  push    r12
0x1400438d6  push    r14
0x1400438d8  push    r15
0x1400438da  lea     rbp, [rsp-190h]
0x1400438e2  sub     rsp, 290h
0x1400438e9  mov     rax, cs:__security_cookie
0x1400438f0  xor     rax, rsp
0x1400438f3  mov     [rbp+1B0h+var_30], rax
0x1400438fa  xor     r12d, r12d
0x1400438fd  lea     rax, [rsp+2B0h+cbMaxValueLen]
0x140043902  mov     [rsp+2B0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x140043907  mov     r15, rdx
0x14004390a  mov     [rsp+2B0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x14004390f  xor     r9d, r9d; lpReserved
0x140043912  mov     [rsp+2B0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x140043917  xor     r8d, r8d; lpcchClass
0x14004391a  mov     [rsp+2B0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x14004391f  lea     rax, [rsp+2B0h+cValues]
0x140043924  mov     [rsp+2B0h+lpcValues], rax; lpcValues
0x140043929  xor     edx, edx; lpClass
0x14004392b  mov     [rsp+2B0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x140043930  mov     r14, rcx
0x140043933  mov     [rsp+2B0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x140043938  mov     [rsp+2B0h+lpcSubKeys], r12; lpcSubKeys
0x14004393d  mov     [rsp+2B0h+cchValueName], r12d
0x140043942  mov     [rsp+2B0h+Type], r12d
0x140043947  mov     [rsp+2B0h+cbData], r12d
0x14004394c  mov     [rsp+2B0h+cValues], r12d
0x140043951  mov     [rsp+2B0h+cbMaxValueLen], r12d
0x140043956  call    cs:__imp_RegQueryInfoKeyW
0x14004395c  mov     edi, eax
0x14004395e  test    eax, eax
0x140043960  jnz     loc_140043A2C
0x140043966  cmp     [rsp+2B0h+cValues], r12d
0x14004396b  jz      loc_140043A2C
0x140043971  mov     ebx, [rsp+2B0h+cbMaxValueLen]
0x140043975  call    cs:__imp_GetProcessHeap
0x14004397b  mov     r8d, ebx; dwBytes
0x14004397e  lea     edx, [rdi+8]; dwFlags
0x140043981  mov     rcx, rax; hHeap
0x140043984  call    cs:__imp_HeapAlloc
0x14004398a  mov     rsi, rax
0x14004398d  test    rax, rax
0x140043990  jz      loc_140043A2C
0x140043996  mov     ebx, r12d
0x140043999  cmp     [rsp+2B0h+cValues], r12d
0x14004399e  jbe     short loc_140043A18
0x1400439a0  mov     ecx, [rsp+2B0h+cbMaxValueLen]
0x1400439a4  lea     rax, [rsp+2B0h+cbData]
0x1400439a9  mov     [rsp+2B0h+lpcValues], rax; lpcbData
0x1400439ae  lea     r9, [rsp+2B0h+cchValueName]; lpcchValueName
0x1400439b3  lea     rax, [rsp+2B0h+Type]
0x1400439b8  mov     [rsp+2B0h+cbData], ecx
0x1400439bc  mov     [rsp+2B0h+lpcbMaxClassLen], rsi; lpData
0x1400439c1  lea     r8, [rbp+1B0h+ValueName]; lpValueName
0x1400439c5  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rax; lpType
0x1400439ca  mov     edx, ebx; dwIndex
0x1400439cc  mov     rcx, r14; hKey
0x1400439cf  mov     [rsp+2B0h+lpcSubKeys], r12; lpReserved
0x1400439d4  mov     [rsp+2B0h+cchValueName], 100h
0x1400439dc  call    cs:__imp_RegEnumValueW
0x1400439e2  mov     edi, eax
0x1400439e4  test    eax, eax
0x1400439e6  jnz     short loc_140043A18
0x1400439e8  mov     eax, [rsp+2B0h+cbData]
0x1400439ec  lea     rdx, [rbp+1B0h+ValueName]; lpValueName
0x1400439f0  mov     r9d, [rsp+2B0h+Type]; dwType
0x1400439f5  xor     r8d, r8d; Reserved
0x1400439f8  mov     dword ptr [rsp+2B0h+lpcbMaxSubKeyLen], eax; cbData
0x1400439fc  mov     rcx, r15; hKey
0x1400439ff  mov     [rsp+2B0h+lpcSubKeys], rsi; lpData
0x140043a04  call    cs:__imp_RegSetValueExW
0x140043a0a  mov     edi, eax
0x140043a0c  test    eax, eax
0x140043a0e  jnz     short loc_140043A18
0x140043a10  inc     ebx
0x140043a12  cmp     ebx, [rsp+2B0h+cValues]
0x140043a16  jb      short loc_1400439A0
0x140043a18  call    cs:__imp_GetProcessHeap
0x140043a1e  mov     r8, rsi; lpMem
0x140043a21  xor     edx, edx; dwFlags
0x140043a23  mov     rcx, rax; hHeap
0x140043a26  call    cs:__imp_HeapFree
0x140043a2c  mov     eax, edi
0x140043a2e  mov     rcx, [rbp+1B0h+var_30]
0x140043a35  xor     rcx, rsp; StackCookie
0x140043a38  call    __security_check_cookie
0x140043a3d  lea     r11, [rsp+2B0h+var_20]
0x140043a45  mov     rbx, [r11+40h]
0x140043a49  mov     rsi, [r11+48h]
0x140043a4d  mov     rsp, r11
0x140043a50  pop     r15
0x140043a52  pop     r14
0x140043a54  pop     r12
0x140043a56  pop     rdi
0x140043a57  pop     rbp
0x140043a58  retn
```
