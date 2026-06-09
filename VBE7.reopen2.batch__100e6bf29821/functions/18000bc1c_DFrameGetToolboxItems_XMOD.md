# DFrameGetToolboxItems(XMOD *)

- ea: `0x18000bc1c`
- end: `0x18000be94`
- name: `?DFrameGetToolboxItems@@YAXPEAUXMOD@@@Z`
- size: `632`
- prototype: `void __fastcall(struct XMOD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b784`
- `0x18004d6a0`

## callees

- `0x18000bc1c`
- `0x18005b0d4`
- `0x1800b0d68`
- `0x1800cf550`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!free` at `0x18000be53`
- `MSVCR100!free` at `0x18000be53`
- `MSVCR100!malloc` at `0x18000be0d`
- `MSVCR100!malloc` at `0x18000be0d`
- `KERNEL32!lstrcpyA` at `0x18000bc60`
- `KERNEL32!lstrcpyA` at `0x18000bc60`
- `KERNEL32!lstrcatA` at `0x18000bc89`
- `KERNEL32!lstrcatA` at `0x18000bc89`
- `ADVAPI32!RegQueryValueExA` at `0x18000bce1`
- `ADVAPI32!RegQueryValueExA` at `0x18000bd1f`
- `ADVAPI32!RegQueryValueExA` at `0x18000bd64`
- `ADVAPI32!RegQueryValueExA` at `0x18000bda2`
- `ADVAPI32!RegQueryValueExA` at `0x18000be42`
- `ADVAPI32!RegQueryValueExA` at `0x18000bce1`
- `ADVAPI32!RegQueryValueExA` at `0x18000bd1f`
- `ADVAPI32!RegQueryValueExA` at `0x18000bd64`
- `ADVAPI32!RegQueryValueExA` at `0x18000bda2`
- `ADVAPI32!RegQueryValueExA` at `0x18000be42`
- `ADVAPI32!RegOpenKeyA` at `0x18000bca0`
- `ADVAPI32!RegOpenKeyA` at `0x18000bca0`
- `ADVAPI32!RegCloseKey` at `0x18000be66`
- `ADVAPI32!RegCloseKey` at `0x18000be66`

## string_xrefs

- `0x18000bc54`: `CLSID\`
- `0x18000bd49`: `ResourcePath`

## pseudocode

```c
void __fastcall DFrameGetToolboxItems(struct XMOD *a1)
{
  char v2; // al
  BYTE *v3; // rax
  DWORD Type[2]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  BYTE lpData[4]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[4]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v8; // [rsp+48h] [rbp-B8h] BYREF
  CHAR String1[6]; // [rsp+50h] [rbp-B0h] BYREF
  char v10[2042]; // [rsp+56h] [rbp-AAh] BYREF

  lstrcpyA(String1, "CLSID\\");
  StringFromGUID2Ansi((const struct _GUID *)((char *)a1 + 280), v10, 2042);
  lstrcatA(String1, "\\DesignerToolbox");
  if ( !RegOpenKeyA(HKEY_CLASSES_ROOT, String1, &phkResult) )
  {
    Type[1] = 4;
    Type[0] = 4;
    if ( !RegQueryValueExA(phkResult, "ItemStartId", 0, Type, Data, &Type[1]) )
    {
      Type[1] = 4;
      Type[0] = 4;
      if ( !RegQueryValueExA(phkResult, "ItemCount", 0, Type, lpData, &Type[1]) )
      {
        Type[1] = 2048;
        Type[0] = 1;
        if ( !RegQueryValueExA(phkResult, "ResourcePath", 0, Type, (LPBYTE)String1, &Type[1]) )
        {
          Type[1] = 4;
          Type[0] = 4;
          if ( !RegQueryValueExA(phkResult, "NameId", 0, Type, (LPBYTE)&v8, &Type[1]) )
          {
            v2 = OleCFLoadToolboxItemsOfHxmod(String1, v8, *(unsigned int *)Data, *(unsigned int *)lpData, a1);
            *((_WORD *)a1 + 58) &= ~0x4000u;
            *((_WORD *)a1 + 58) |= (v2 & 1) << 14;
            if ( (*((_WORD *)a1 + 58) & 0x4000) != 0 )
            {
              ToolCreateDesignerGroup(a1);
              Type[0] = 3;
              Type[1] = 4 * *(_DWORD *)lpData;
              v3 = (BYTE *)malloc((unsigned int)(4 * *(_DWORD *)lpData));
              *((_QWORD *)a1 + 56) = v3;
              if ( v3 )
              {
                if ( RegQueryValueExA(phkResult, "HelpContextIDs", 0, Type, v3, &Type[1]) )
                {
                  free(*((void **)a1 + 56));
                  *((_QWORD *)a1 + 56) = 0;
                }
              }
            }
          }
        }
      }
    }
    RegCloseKey(phkResult);
  }
}

```

## disassembly

```asm
0x18000bc1c  mov     rax, rsp
0x18000bc1f  mov     [rax+10h], rbx
0x18000bc23  mov     [rax+18h], rsi
0x18000bc27  mov     [rax+20h], rdi
0x18000bc2b  push    rbp
0x18000bc2c  lea     rbp, [rax-768h]
0x18000bc33  mov     eax, 860h
0x18000bc38  call    _alloca_probe
0x18000bc3d  sub     rsp, rax
0x18000bc40  mov     rax, cs:__security_cookie
0x18000bc47  xor     rax, rsp
0x18000bc4a  mov     [rbp+760h+var_10], rax
0x18000bc51  mov     rbx, rcx
0x18000bc54  lea     rdx, String2; "CLSID\\"
0x18000bc5b  lea     rcx, [rsp+860h+String1]; lpString1
0x18000bc60  call    cs:__imp_lstrcpyA
0x18000bc66  lea     rcx, [rbx+118h]; struct _GUID *
0x18000bc6d  lea     rdx, [rsp+860h+var_80A]; char *
0x18000bc72  mov     r8d, 7FAh; int
0x18000bc78  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x18000bc7d  lea     rdx, aDesignertoolbo_0; "\\DesignerToolbox"
0x18000bc84  lea     rcx, [rsp+860h+String1]; lpString1
0x18000bc89  call    cs:__imp_lstrcatA
0x18000bc8f  lea     r8, [rsp+860h+phkResult]; phkResult
0x18000bc94  lea     rdx, [rsp+860h+String1]; lpSubKey
0x18000bc99  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000bca0  call    cs:__imp_RegOpenKeyA
0x18000bca6  test    eax, eax
0x18000bca8  jnz     loc_18000BE6C
0x18000bcae  mov     rcx, [rsp+860h+phkResult]; hKey
0x18000bcb3  lea     edi, [rax+4]
0x18000bcb6  lea     rax, [rsp+860h+Type+4]
0x18000bcbb  mov     [rsp+860h+lpcbData], rax; lpcbData
0x18000bcc0  lea     rax, [rsp+860h+Data]
0x18000bcc5  lea     r9, [rsp+860h+Type]; lpType
0x18000bcca  lea     rdx, ValueName; "ItemStartId"
0x18000bcd1  xor     r8d, r8d; lpReserved
0x18000bcd4  mov     [rsp+860h+Type+4], edi
0x18000bcd8  mov     [rsp+860h+lpData], rax; lpData
0x18000bcdd  mov     [rsp+860h+Type], edi
0x18000bce1  call    cs:__imp_RegQueryValueExA
0x18000bce7  test    eax, eax
0x18000bce9  jnz     loc_18000BE61
0x18000bcef  mov     rcx, [rsp+860h+phkResult]; hKey
0x18000bcf4  lea     rax, [rsp+860h+Type+4]
0x18000bcf9  lea     r9, [rsp+860h+Type]; lpType
0x18000bcfe  mov     [rsp+860h+lpcbData], rax; lpcbData
0x18000bd03  lea     rax, [rsp+860h+var_820]
0x18000bd08  lea     rdx, aItemcount; "ItemCount"
0x18000bd0f  xor     r8d, r8d; lpReserved
0x18000bd12  mov     [rsp+860h+Type+4], edi
0x18000bd16  mov     [rsp+860h+Type], edi
0x18000bd1a  mov     [rsp+860h+lpData], rax; lpData
0x18000bd1f  call    cs:__imp_RegQueryValueExA
0x18000bd25  test    eax, eax
0x18000bd27  jnz     loc_18000BE61
0x18000bd2d  mov     rcx, [rsp+860h+phkResult]; hKey
0x18000bd32  lea     rax, [rsp+860h+Type+4]
0x18000bd37  lea     esi, [rdi-3]
0x18000bd3a  mov     [rsp+860h+lpcbData], rax; lpcbData
0x18000bd3f  lea     rax, [rsp+860h+String1]
0x18000bd44  lea     r9, [rsp+860h+Type]; lpType
0x18000bd49  lea     rdx, aResourcepath; "ResourcePath"
0x18000bd50  xor     r8d, r8d; lpReserved
0x18000bd53  mov     [rsp+860h+Type+4], 800h
0x18000bd5b  mov     [rsp+860h+lpData], rax; lpData
0x18000bd60  mov     [rsp+860h+Type], esi
0x18000bd64  call    cs:__imp_RegQueryValueExA
0x18000bd6a  test    eax, eax
0x18000bd6c  jnz     loc_18000BE61
0x18000bd72  mov     rcx, [rsp+860h+phkResult]; hKey
0x18000bd77  lea     rax, [rsp+860h+Type+4]
0x18000bd7c  lea     r9, [rsp+860h+Type]; lpType
0x18000bd81  mov     [rsp+860h+lpcbData], rax; lpcbData
0x18000bd86  lea     rax, [rsp+860h+var_818]
0x18000bd8b  lea     rdx, aNameid; "NameId"
0x18000bd92  xor     r8d, r8d; lpReserved
0x18000bd95  mov     [rsp+860h+Type+4], edi
0x18000bd99  mov     [rsp+860h+Type], edi
0x18000bd9d  mov     [rsp+860h+lpData], rax; lpData
0x18000bda2  call    cs:__imp_RegQueryValueExA
0x18000bda8  test    eax, eax
0x18000bdaa  jnz     loc_18000BE61
0x18000bdb0  mov     r9d, dword ptr [rsp+860h+var_820]; unsigned int
0x18000bdb5  mov     r8d, dword ptr [rsp+860h+Data]; unsigned int
0x18000bdba  mov     edx, [rsp+860h+var_818]; unsigned int
0x18000bdbe  lea     rcx, [rsp+860h+String1]; char *
0x18000bdc3  mov     [rsp+860h+lpData], rbx; struct XMOD *
0x18000bdc8  call    ?OleCFLoadToolboxItemsOfHxmod@@YAHPEBDIIIPEAUXMOD@@@Z; OleCFLoadToolboxItemsOfHxmod(char const *,uint,uint,uint,XMOD *)
0x18000bdcd  mov     ecx, 0BFFFh
0x18000bdd2  and     [rbx+74h], cx
0x18000bdd6  and     ax, si
0x18000bdd9  shl     ax, 0Eh
0x18000bddd  or      [rbx+74h], ax
0x18000bde1  mov     eax, 4000h
0x18000bde6  test    [rbx+74h], ax
0x18000bdea  jz      short loc_18000BE61
0x18000bdec  mov     rcx, rbx; struct XMOD *
0x18000bdef  call    ?ToolCreateDesignerGroup@@YAXPEAUXMOD@@@Z; ToolCreateDesignerGroup(XMOD *)
0x18000bdf4  mov     r11d, dword ptr [rsp+860h+var_820]
0x18000bdf9  mov     [rsp+860h+Type], 3
0x18000be01  shl     r11d, 2
0x18000be05  mov     ecx, r11d; Size
0x18000be08  mov     [rsp+860h+Type+4], r11d
0x18000be0d  call    cs:__imp_malloc
0x18000be13  mov     [rbx+1C0h], rax
0x18000be1a  test    rax, rax
0x18000be1d  jz      short loc_18000BE61
0x18000be1f  lea     rcx, [rsp+860h+Type+4]
0x18000be24  lea     r9, [rsp+860h+Type]; lpType
0x18000be29  lea     rdx, aHelpcontextids; "HelpContextIDs"
0x18000be30  mov     [rsp+860h+lpcbData], rcx; lpcbData
0x18000be35  mov     rcx, [rsp+860h+phkResult]; hKey
0x18000be3a  xor     r8d, r8d; lpReserved
0x18000be3d  mov     [rsp+860h+lpData], rax; lpData
0x18000be42  call    cs:__imp_RegQueryValueExA
0x18000be48  test    eax, eax
0x18000be4a  jz      short loc_18000BE61
0x18000be4c  mov     rcx, [rbx+1C0h]; Block
0x18000be53  call    cs:__imp_free
0x18000be59  and     qword ptr [rbx+1C0h], 0
0x18000be61  mov     rcx, [rsp+860h+phkResult]; hKey
0x18000be66  call    cs:__imp_RegCloseKey
0x18000be6c  mov     rcx, [rbp+760h+var_10]
0x18000be73  xor     rcx, rsp; StackCookie
0x18000be76  call    __security_check_cookie
0x18000be7b  lea     r11, [rsp+860h+var_s0]
0x18000be83  mov     rbx, [r11+18h]
0x18000be87  mov     rsi, [r11+20h]
0x18000be8b  mov     rdi, [r11+28h]
0x18000be8f  mov     rsp, r11
0x18000be92  pop     rbp
0x18000be93  retn
```
