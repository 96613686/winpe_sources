# CSystemMspEnumerator::_GetNextInstalledSystemMsi(ushort *,uint)

- ea: `0x180044ac4`
- end: `0x180044bd0`
- name: `?_GetNextInstalledSystemMsi@CSystemMspEnumerator@@AEAAJPEAGI@Z`
- size: `268`
- prototype: `int(CSystemMspEnumerator *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800449fc`

## callees

- `0x180011bd0`
- `0x180012598`
- `0x180044ac4`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044b17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044b17`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044b7e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044b7e`
- `ADVAPI32!RegEnumKeyW` at `0x180044b3e`
- `ADVAPI32!RegEnumKeyW` at `0x180044b3e`

## string_xrefs

- `0x180044b09`: `Software\Microsoft\Windows\CurrentVersion\Uninstall\SystemMSP`

## pseudocode

```c
__int64 __fastcall CSystemMspEnumerator::_GetNextInstalledSystemMsi(CSystemMspEnumerator *this, unsigned __int16 *a2)
{
  HKEY *v2; // rsi
  unsigned int v5; // ebx
  HKEY v6; // rcx
  DWORD pcbData[4]; // [rsp+40h] [rbp-248h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-238h] BYREF

  v2 = (HKEY *)((char *)this + 88);
  if ( *((_QWORD *)this + 11)
    || !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\SystemMSP",
          0,
          0x20019u,
          (PHKEY)this + 11) )
  {
    while ( 1 )
    {
      v5 = 1;
      if ( RegEnumKeyW(*v2, *((_DWORD *)this + 20), Name, 0x104u) )
        break;
      v6 = *v2;
      ++*((_DWORD *)this + 20);
      pcbData[0] = 78;
      if ( RegGetValueW(v6, Name, L"ParentID", 2u, 0, a2, pcbData) )
        break;
      v5 = 0;
      if ( (unsigned int)CHashTable<void,unsigned short>::ContainsKey((char *)this + 96, a2) )
      {
        CHashTable<void,unsigned short>::AddPtr((char *)this + 96, a2);
        return v5;
      }
    }
  }
  else
  {
    return 1;
  }
  return v5;
}

```

## disassembly

```asm
0x180044ac4  mov     [rsp+arg_10], rbx
0x180044ac9  mov     [rsp+arg_18], rbp
0x180044ace  push    rsi
0x180044acf  push    rdi
0x180044ad0  push    r14
0x180044ad2  sub     rsp, 270h
0x180044ad9  mov     rax, cs:__security_cookie
0x180044ae0  xor     rax, rsp
0x180044ae3  mov     [rsp+288h+var_28], rax
0x180044aeb  lea     rsi, [rcx+58h]
0x180044aef  mov     rbp, rdx
0x180044af2  cmp     qword ptr [rsi], 0
0x180044af6  mov     rdi, rcx
0x180044af9  jnz     short loc_180044B28
0x180044afb  mov     r9d, 20019h; samDesired
0x180044b01  mov     [rsp+288h+phkResult], rsi; phkResult
0x180044b06  xor     r8d, r8d; ulOptions
0x180044b09  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180044b10  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044b17  call    cs:__imp_RegOpenKeyExW
0x180044b1d  test    eax, eax
0x180044b1f  jz      short loc_180044B28
0x180044b21  mov     ebx, 1
0x180044b26  jmp     short loc_180044BA6
0x180044b28  mov     edx, [rdi+50h]; dwIndex
0x180044b2b  lea     r8, [rsp+288h+Name]; lpName
0x180044b30  mov     rcx, [rsi]; hKey
0x180044b33  mov     r9d, 104h; cchName
0x180044b39  mov     ebx, 1
0x180044b3e  call    cs:__imp_RegEnumKeyW
0x180044b44  test    eax, eax
0x180044b46  jnz     short loc_180044BA6
0x180044b48  mov     rcx, [rsi]; hkey
0x180044b4b  lea     rax, [rsp+288h+var_248]
0x180044b50  inc     dword ptr [rdi+50h]
0x180044b53  lea     r9d, [rbx+1]; dwFlags
0x180044b57  mov     [rsp+288h+pcbData], rax; pcbData
0x180044b5c  lea     r8, aParentid; "ParentID"
0x180044b63  mov     [rsp+288h+pvData], rbp; pvData
0x180044b68  lea     rdx, [rsp+288h+Name]; lpSubKey
0x180044b6d  mov     [rsp+288h+phkResult], 0; pdwType
0x180044b76  mov     [rsp+288h+var_248], 4Eh ; 'N'
0x180044b7e  call    cs:__imp_RegGetValueW
0x180044b84  test    eax, eax
0x180044b86  jnz     short loc_180044BA6
0x180044b88  mov     rdx, rbp
0x180044b8b  lea     rcx, [rdi+60h]
0x180044b8f  xor     ebx, ebx
0x180044b91  call    ?ContainsKey@?$CHashTable@XG@@QEBAJPEBG@Z; CHashTable<void,ushort>::ContainsKey(ushort const *)
0x180044b96  test    eax, eax
0x180044b98  jz      short loc_180044B28
0x180044b9a  mov     rdx, rbp
0x180044b9d  lea     rcx, [rdi+60h]
0x180044ba1  call    ?AddPtr@?$CHashTable@XG@@QEAAJPEBGPEAX@Z; CHashTable<void,ushort>::AddPtr(ushort const *,void *)
0x180044ba6  mov     eax, ebx
0x180044ba8  mov     rcx, [rsp+288h+var_28]
0x180044bb0  xor     rcx, rsp; StackCookie
0x180044bb3  call    __security_check_cookie
0x180044bb8  lea     r11, [rsp+288h+var_18]
0x180044bc0  mov     rbx, [r11+30h]
0x180044bc4  mov     rbp, [r11+38h]
0x180044bc8  mov     rsp, r11
0x180044bcb  pop     r14
0x180044bcd  pop     rdi
0x180044bce  pop     rsi
0x180044bcf  retn
```
