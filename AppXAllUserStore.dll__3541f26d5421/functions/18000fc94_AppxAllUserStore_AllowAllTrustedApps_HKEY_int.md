# AppxAllUserStore::AllowAllTrustedApps(HKEY__ *,int *)

- ea: `0x18000fc94`
- end: `0x18000fd9a`
- name: `?AllowAllTrustedApps@AppxAllUserStore@@YAJPEAUHKEY__@@PEAH@Z`
- size: `262`
- prototype: `LSTATUS __fastcall(AppxAllUserStore *this, _DWORD *, int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fc30`
- `0x180019ff8`
- `0x18002eac0`

## callees

- `0x18000fc94`
- `0x180017f50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fd8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fd8a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fd2a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fd2a`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000fcc4`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000fcc4`

## string_xrefs

- `0x18000fd5f`: `onecore\admin\appmodel\appxalluserstore\src\commonutilities.cpp`

## pseudocode

```c
LSTATUS __fastcall AppxAllUserStore::AllowAllTrustedApps(AppxAllUserStore *this, _DWORD *a2, int *a3)
{
  char v3; // di
  LSTATUS result; // eax
  LSTATUS ValueW; // eax
  signed int v7; // ebx
  int v8; // edx
  bool v9; // sf
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY phkResult; // [rsp+60h] [rbp+8h] BYREF
  int pvData; // [rsp+68h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp+18h] BYREF

  phkResult = (HKEY)this;
  v3 = 0;
  *a2 = 0;
  if ( !this )
  {
    result = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE", &phkResult);
    if ( result )
    {
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    this = (AppxAllUserStore *)phkResult;
    v3 = 1;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             (HKEY)this,
             L"Policies\\Microsoft\\Windows\\Appx",
             L"AllowAllTrustedApps",
             0x18u,
             0,
             &pvData,
             &pcbData);
  v7 = ValueW;
  if ( !ValueW )
  {
    v8 = pvData;
LABEL_11:
    v9 = v7 < 0;
    goto LABEL_12;
  }
  v8 = 0xFFFF;
  if ( (unsigned int)(ValueW - 2) <= 1 )
  {
    v7 = 0;
    goto LABEL_15;
  }
  v9 = ValueW < 0;
  if ( ValueW > 0 )
  {
    v7 = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_11;
  }
LABEL_12:
  if ( !v9 )
  {
LABEL_15:
    *a2 = v8 != 0;
    goto LABEL_16;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xA9,
    (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\commonutilities.cpp",
    (const char *)(unsigned int)v7);
LABEL_16:
  if ( v3 )
    RegCloseKey(phkResult);
  return v7;
}

```

## disassembly

```asm
0x18000fc94  mov     [rsp+phkResult], rcx
0x18000fc99  push    rbx
0x18000fc9a  push    rsi
0x18000fc9b  push    rdi
0x18000fc9c  sub     rsp, 40h
0x18000fca0  xor     dil, dil
0x18000fca3  mov     dword ptr [rdx], 0
0x18000fca9  mov     rsi, rdx
0x18000fcac  test    rcx, rcx
0x18000fcaf  jnz     short loc_18000FCE9
0x18000fcb1  lea     r8, [rsp+58h+phkResult]; phkResult
0x18000fcb6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fcbd  lea     rdx, aSoftware; "SOFTWARE"
0x18000fcc4  call    cs:__imp_RegOpenKeyW
0x18000fcca  test    eax, eax
0x18000fccc  jz      short loc_18000FCE1
0x18000fcce  jle     loc_18000FD92
0x18000fcd4  movzx   eax, ax
0x18000fcd7  or      eax, 80070000h
0x18000fcdc  jmp     loc_18000FD92
0x18000fce1  mov     rcx, [rsp+58h+phkResult]; hkey
0x18000fce6  mov     dil, 1
0x18000fce9  lea     rax, [rsp+58h+arg_10]
0x18000fcee  mov     [rsp+58h+arg_8], 0
0x18000fcf6  mov     [rsp+58h+pcbData], rax; pcbData
0x18000fcfb  lea     r8, aAllowalltruste; "AllowAllTrustedApps"
0x18000fd02  lea     rax, [rsp+58h+arg_8]
0x18000fd07  mov     [rsp+58h+arg_10], 4
0x18000fd0f  mov     [rsp+58h+pvData], rax; pvData
0x18000fd14  lea     rdx, aPoliciesMicros; "Policies\\Microsoft\\Windows\\Appx"
0x18000fd1b  mov     r9d, 18h; dwFlags
0x18000fd21  mov     [rsp+58h+pdwType], 0; int
0x18000fd2a  call    cs:__imp_RegGetValueW
0x18000fd30  mov     ebx, eax
0x18000fd32  test    eax, eax
0x18000fd34  jnz     short loc_18000FD3C
0x18000fd36  mov     edx, [rsp+58h+arg_8]
0x18000fd3a  jmp     short loc_18000FD56
0x18000fd3c  add     eax, 0FFFFFFFEh
0x18000fd3f  mov     edx, 0FFFFh
0x18000fd44  cmp     eax, 1
0x18000fd47  jbe     short loc_18000FD75
0x18000fd49  test    ebx, ebx
0x18000fd4b  jle     short loc_18000FD58
0x18000fd4d  movzx   ebx, bx
0x18000fd50  or      ebx, 80070000h
0x18000fd56  test    ebx, ebx
0x18000fd58  jns     short loc_18000FD77
0x18000fd5a  mov     rcx, [rsp+58h]; this
0x18000fd5f  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000fd66  mov     r9d, ebx; char *
0x18000fd69  mov     edx, 0A9h; void *
0x18000fd6e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000fd73  jmp     short loc_18000FD80
0x18000fd75  xor     ebx, ebx
0x18000fd77  xor     ecx, ecx
0x18000fd79  test    edx, edx
0x18000fd7b  setnz   cl
0x18000fd7e  mov     [rsi], ecx
0x18000fd80  test    dil, dil
0x18000fd83  jz      short loc_18000FD90
0x18000fd85  mov     rcx, [rsp+58h+phkResult]; hKey
0x18000fd8a  call    cs:__imp_RegCloseKey
0x18000fd90  mov     eax, ebx
0x18000fd92  add     rsp, 40h
0x18000fd96  pop     rdi
0x18000fd97  pop     rsi
0x18000fd98  pop     rbx
0x18000fd99  retn
```
