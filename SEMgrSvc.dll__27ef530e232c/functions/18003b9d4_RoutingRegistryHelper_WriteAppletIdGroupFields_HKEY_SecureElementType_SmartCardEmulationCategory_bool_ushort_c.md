# RoutingRegistryHelper::WriteAppletIdGroupFields(HKEY__ *,SecureElementType,SmartCardEmulationCategory,bool,ushort const *,uint,uchar const *,bool,ushort const *)

- ea: `0x18003b9d4`
- end: `0x18003bc13`
- name: `?WriteAppletIdGroupFields@RoutingRegistryHelper@@CAJPEAUHKEY__@@W4SecureElementType@@W4SmartCardEmulationCategory@@_NPEBGIPEBE34@Z`
- size: `575`
- prototype: `int __fastcall(HKEY, int, int, BYTE, wchar_t *Source, DWORD cbData, BYTE *, BYTE, wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003bc1c`

## callees

- `0x18003b9d4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18003bb2e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18003bbc5`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18003bb2e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18003bbc5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ba15`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ba4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ba88`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bac5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bb07`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bb66`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bba2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bbee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ba15`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ba4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ba88`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bac5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bb07`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bb66`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bba2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bbee`

## pseudocode

```c
int __fastcall RoutingRegistryHelper::WriteAppletIdGroupFields(
        HKEY a1,
        int a2,
        int a3,
        BYTE a4,
        wchar_t *Source,
        DWORD cbData,
        BYTE *a7,
        BYTE a8,
        wchar_t *a9)
{
  int result; // eax
  bool v11; // sf
  bool v12; // sf
  bool v13; // sf
  bool v14; // sf
  bool v15; // sf
  wchar_t *v16; // rbx
  int v17; // eax
  bool v18; // sf
  bool v19; // sf
  wchar_t *v20; // rbx
  int v21; // eax
  LSTATUS v22; // eax
  signed int v23; // ecx
  BYTE v24[40]; // [rsp+30h] [rbp-28h] BYREF
  int Data; // [rsp+68h] [rbp+10h] BYREF
  int lpData; // [rsp+70h] [rbp+18h] BYREF
  BYTE v27; // [rsp+78h] [rbp+20h] BYREF

  v27 = a4;
  lpData = a3;
  Data = a2;
  *(_DWORD *)v24 = 0;
  result = RegSetValueExW(a1, L"Category", 0, 4u, (const BYTE *)&lpData, 4u);
  v11 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v11 = result < 0;
  }
  if ( !v11 )
  {
    result = RegSetValueExW(a1, L"Type", 0, 4u, (const BYTE *)&Data, 4u);
    v12 = result < 0;
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v12 = result < 0;
    }
    if ( !v12 )
    {
      result = RegSetValueExW(a1, L"AllowAutomaticEnable", 0, 4u, &v27, 1u);
      v13 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v13 = result < 0;
      }
      if ( !v13 )
      {
        *(_DWORD *)v24 = 0;
        result = RegSetValueExW(a1, L"Policy", 0, 4u, v24, 4u);
        v14 = result < 0;
        if ( result > 0 )
        {
          result = (unsigned __int16)result | 0x80070000;
          v14 = result < 0;
        }
        if ( !v14 )
        {
          result = RegSetValueExW(a1, L"Properties", 0, 3u, a7, cbData);
          v15 = result < 0;
          if ( result > 0 )
          {
            result = (unsigned __int16)result | 0x80070000;
            v15 = result < 0;
          }
          if ( !v15 )
          {
            v16 = Source;
            v17 = wcsnlen(Source, 0x41u);
            if ( v17 == 65 )
            {
              return -2147024809;
            }
            else
            {
              result = RegSetValueExW(a1, L"DisplayName", 0, 1u, (const BYTE *)v16, 2 * v17 + 2);
              v18 = result < 0;
              if ( result > 0 )
              {
                result = (unsigned __int16)result | 0x80070000;
                v18 = result < 0;
              }
              if ( !v18 )
              {
                result = RegSetValueExW(a1, L"RequiresSecureUserAuthentication", 0, 4u, &a8, 1u);
                v19 = result < 0;
                if ( result > 0 )
                {
                  result = (unsigned __int16)result | 0x80070000;
                  v19 = result < 0;
                }
                if ( !v19 )
                {
                  v20 = a9;
                  v21 = wcsnlen(a9, 0x101u);
                  v22 = RegSetValueExW(a1, L"Description", 0, 1u, (const BYTE *)v20, 2 * v21 + 2);
                  v23 = v22;
                  if ( v22 > 0 )
                    v23 = (unsigned __int16)v22 | 0x80070000;
                  result = 0;
                  if ( v23 < 0 )
                    return v23;
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003b9d4  mov     rax, rsp
0x18003b9d7  mov     [rax+8], rbx
0x18003b9db  mov     [rax+20h], r9b
0x18003b9df  mov     [rax+18h], r8d
0x18003b9e3  mov     [rax+10h], edx
0x18003b9e6  push    rbp
0x18003b9e7  push    rsi
0x18003b9e8  push    rdi
0x18003b9e9  sub     rsp, 40h
0x18003b9ed  mov     ebp, 4
0x18003b9f2  mov     dword ptr [rax-28h], 0
0x18003b9f9  mov     [rax-30h], ebp
0x18003b9fc  lea     rax, [rax+18h]
0x18003ba00  mov     r9d, ebp; dwType
0x18003ba03  mov     [rsp+58h+lpData], rax; lpData
0x18003ba08  xor     r8d, r8d; Reserved
0x18003ba0b  lea     rdx, aCategory; "Category"
0x18003ba12  mov     rdi, rcx
0x18003ba15  call    cs:__imp_RegSetValueExW
0x18003ba1b  mov     esi, 80070000h
0x18003ba20  test    eax, eax
0x18003ba22  jle     short loc_18003BA2B
0x18003ba24  movzx   eax, ax
0x18003ba27  or      eax, esi
0x18003ba29  test    eax, eax
0x18003ba2b  js      loc_18003BC06
0x18003ba31  lea     rax, [rsp+58h+Data]
0x18003ba36  mov     [rsp+58h+cbData], ebp; cbData
0x18003ba3a  mov     r9d, ebp; dwType
0x18003ba3d  mov     [rsp+58h+lpData], rax; lpData
0x18003ba42  xor     r8d, r8d; Reserved
0x18003ba45  lea     rdx, aType; "Type"
0x18003ba4c  mov     rcx, rdi; hKey
0x18003ba4f  call    cs:__imp_RegSetValueExW
0x18003ba55  test    eax, eax
0x18003ba57  jle     short loc_18003BA60
0x18003ba59  movzx   eax, ax
0x18003ba5c  or      eax, esi
0x18003ba5e  test    eax, eax
0x18003ba60  js      loc_18003BC06
0x18003ba66  lea     rax, [rsp+58h+arg_18]
0x18003ba6b  mov     [rsp+58h+cbData], 1; cbData
0x18003ba73  mov     r9d, ebp; dwType
0x18003ba76  mov     [rsp+58h+lpData], rax; lpData
0x18003ba7b  xor     r8d, r8d; Reserved
0x18003ba7e  lea     rdx, aAllowautomatic; "AllowAutomaticEnable"
0x18003ba85  mov     rcx, rdi; hKey
0x18003ba88  call    cs:__imp_RegSetValueExW
0x18003ba8e  test    eax, eax
0x18003ba90  jle     short loc_18003BA99
0x18003ba92  movzx   eax, ax
0x18003ba95  or      eax, esi
0x18003ba97  test    eax, eax
0x18003ba99  js      loc_18003BC06
0x18003ba9f  lea     rax, [rsp+58h+var_28]
0x18003baa4  mov     [rsp+58h+cbData], ebp; cbData
0x18003baa8  mov     r9d, ebp; dwType
0x18003baab  mov     [rsp+58h+lpData], rax; lpData
0x18003bab0  xor     r8d, r8d; Reserved
0x18003bab3  mov     dword ptr [rsp+58h+var_28], 0
0x18003babb  lea     rdx, aPolicy; "Policy"
0x18003bac2  mov     rcx, rdi; hKey
0x18003bac5  call    cs:__imp_RegSetValueExW
0x18003bacb  test    eax, eax
0x18003bacd  jle     short loc_18003BAD6
0x18003bacf  movzx   eax, ax
0x18003bad2  or      eax, esi
0x18003bad4  test    eax, eax
0x18003bad6  js      loc_18003BC06
0x18003badc  mov     eax, [rsp+58h+arg_28]
0x18003bae3  lea     rdx, ValueName; "Properties"
0x18003baea  mov     [rsp+58h+cbData], eax; cbData
0x18003baee  mov     r9d, 3; dwType
0x18003baf4  mov     rax, [rsp+58h+arg_30]
0x18003bafc  xor     r8d, r8d; Reserved
0x18003baff  mov     rcx, rdi; hKey
0x18003bb02  mov     [rsp+58h+lpData], rax; lpData
0x18003bb07  call    cs:__imp_RegSetValueExW
0x18003bb0d  test    eax, eax
0x18003bb0f  jle     short loc_18003BB18
0x18003bb11  movzx   eax, ax
0x18003bb14  or      eax, esi
0x18003bb16  test    eax, eax
0x18003bb18  js      loc_18003BC06
0x18003bb1e  mov     rbx, [rsp+58h+Source]
0x18003bb26  mov     edx, 41h ; 'A'; MaxCount
0x18003bb2b  mov     rcx, rbx; Source
0x18003bb2e  call    cs:__imp_wcsnlen
0x18003bb34  cmp     eax, 41h ; 'A'
0x18003bb37  jnz     short loc_18003BB43
0x18003bb39  mov     eax, 80070057h
0x18003bb3e  jmp     loc_18003BC06
0x18003bb43  lea     eax, ds:2[rax*2]
0x18003bb4a  mov     r9d, 1; dwType
0x18003bb50  mov     [rsp+58h+cbData], eax; cbData
0x18003bb54  lea     rdx, aDisplayname; "DisplayName"
0x18003bb5b  xor     r8d, r8d; Reserved
0x18003bb5e  mov     [rsp+58h+lpData], rbx; lpData
0x18003bb63  mov     rcx, rdi; hKey
0x18003bb66  call    cs:__imp_RegSetValueExW
0x18003bb6c  test    eax, eax
0x18003bb6e  jle     short loc_18003BB77
0x18003bb70  movzx   eax, ax
0x18003bb73  or      eax, esi
0x18003bb75  test    eax, eax
0x18003bb77  js      loc_18003BC06
0x18003bb7d  lea     rax, [rsp+58h+arg_38]
0x18003bb85  mov     [rsp+58h+cbData], 1; cbData
0x18003bb8d  mov     r9d, ebp; dwType
0x18003bb90  mov     [rsp+58h+lpData], rax; lpData
0x18003bb95  xor     r8d, r8d; Reserved
0x18003bb98  lea     rdx, aRequiressecure; "RequiresSecureUserAuthentication"
0x18003bb9f  mov     rcx, rdi; hKey
0x18003bba2  call    cs:__imp_RegSetValueExW
0x18003bba8  test    eax, eax
0x18003bbaa  jle     short loc_18003BBB3
0x18003bbac  movzx   eax, ax
0x18003bbaf  or      eax, esi
0x18003bbb1  test    eax, eax
0x18003bbb3  js      short loc_18003BC06
0x18003bbb5  mov     rbx, [rsp+58h+arg_40]
0x18003bbbd  mov     edx, 101h; MaxCount
0x18003bbc2  mov     rcx, rbx; Source
0x18003bbc5  call    cs:__imp_wcsnlen
0x18003bbcb  mov     r9d, 1; dwType
0x18003bbd1  lea     rdx, aDescription; "Description"
0x18003bbd8  xor     r8d, r8d; Reserved
0x18003bbdb  mov     rcx, rdi; hKey
0x18003bbde  lea     eax, ds:2[rax*2]
0x18003bbe5  mov     [rsp+58h+cbData], eax; cbData
0x18003bbe9  mov     [rsp+58h+lpData], rbx; lpData
0x18003bbee  call    cs:__imp_RegSetValueExW
0x18003bbf4  mov     ecx, eax
0x18003bbf6  test    eax, eax
0x18003bbf8  jle     short loc_18003BBFF
0x18003bbfa  movzx   ecx, ax
0x18003bbfd  or      ecx, esi
0x18003bbff  xor     eax, eax
0x18003bc01  test    ecx, ecx
0x18003bc03  cmovs   eax, ecx
0x18003bc06  mov     rbx, [rsp+58h+arg_0]
0x18003bc0b  add     rsp, 40h
0x18003bc0f  pop     rdi
0x18003bc10  pop     rsi
0x18003bc11  pop     rbp
0x18003bc12  retn
```
