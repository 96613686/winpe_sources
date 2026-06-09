# GetLicensingPolicyValue

- ea: `0x18002c9dc`
- end: `0x18002cb1b`
- name: `GetLicensingPolicyValue`
- size: `319`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ccfc`
- `0x18002cd9c`

## callees

- `0x18000abe4`
- `0x18002c9dc`
- `0x18002cb24`
- `0x1800321cc`
- `0x18003e010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18002ca40`
- `KERNEL32!LoadLibraryW` at `0x18002ca40`
- `KERNEL32!FreeLibrary` at `0x18002cac0`
- `KERNEL32!FreeLibrary` at `0x18002cac0`
- `KERNEL32!GetProcAddress` at `0x18002ca5e`
- `KERNEL32!GetProcAddress` at `0x18002ca5e`
- `KERNEL32!GetLastError` at `0x18002ca6f`
- `KERNEL32!GetLastError` at `0x18002ca6f`

## string_xrefs

- `0x18002caaf`: `Microsoft-Windows-Fax-Common-EnableServerPolicy`
- `0x18002ca39`: `slc.dll`

## pseudocode

```c
__int64 __fastcall GetLicensingPolicyValue(__int64 a1, _DWORD *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // rsi
  FARPROC ProcAddress; // rax
  DWORD LastError; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
  }
  if ( !a2 )
    return 2147942487LL;
  if ( (unsigned int)LonghornOrMore() )
  {
    LibraryW = LoadLibraryW(L"slc.dll");
    v5 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "SLGetWindowsInformationDWORD");
      if ( ProcAddress )
      {
        LastError = ((__int64 (__fastcall *)(const wchar_t *, _DWORD *))ProcAddress)(
                      L"Microsoft-Windows-Fax-Common-EnableServerPolicy",
                      a2);
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
        }
      }
      FreeLibrary(v5);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
      }
      return 1157;
    }
  }
  else
  {
    LastError = 0;
    *a2 = GetProductSKU() & 0x5C;
  }
  return LastError;
}

```

## disassembly

```asm
0x18002c9dc  push    rbx
0x18002c9de  push    rsi
0x18002c9df  push    rdi
0x18002c9e0  push    r14
0x18002c9e2  sub     rsp, 28h
0x18002c9e6  mov     rdi, rdx
0x18002c9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c9f0  lea     r14, WPP_GLOBAL_Control
0x18002c9f7  cmp     rcx, r14
0x18002c9fa  jz      short loc_18002CA1D
0x18002c9fc  test    byte ptr [rcx+1Ch], 2
0x18002ca00  jz      short loc_18002CA1D
0x18002ca02  cmp     byte ptr [rcx+19h], 5
0x18002ca06  jb      short loc_18002CA1D
0x18002ca08  mov     rcx, [rcx+10h]
0x18002ca0c  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x18002ca13  mov     edx, 1Ch
0x18002ca18  call    WPP_SF_
0x18002ca1d  test    rdi, rdi
0x18002ca20  jnz     short loc_18002CA2C
0x18002ca22  mov     eax, 80070057h
0x18002ca27  jmp     loc_18002CB10
0x18002ca2c  call    LonghornOrMore
0x18002ca31  test    eax, eax
0x18002ca33  jz      loc_18002CB02
0x18002ca39  lea     rcx, aSlcDll; "slc.dll"
0x18002ca40  call    cs:__imp_LoadLibraryW
0x18002ca47  nop     dword ptr [rax+rax+00h]
0x18002ca4c  mov     rsi, rax
0x18002ca4f  test    rax, rax
0x18002ca52  jz      short loc_18002CACE
0x18002ca54  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x18002ca5b  mov     rcx, rax; hModule
0x18002ca5e  call    cs:__imp_GetProcAddress
0x18002ca65  nop     dword ptr [rax+rax+00h]
0x18002ca6a  test    rax, rax
0x18002ca6d  jnz     short loc_18002CAAC
0x18002ca6f  call    cs:__imp_GetLastError
0x18002ca76  nop     dword ptr [rax+rax+00h]
0x18002ca7b  mov     ebx, eax
0x18002ca7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca84  cmp     rcx, r14
0x18002ca87  jz      short loc_18002CABD
0x18002ca89  test    byte ptr [rcx+1Ch], 2
0x18002ca8d  jz      short loc_18002CABD
0x18002ca8f  cmp     byte ptr [rcx+19h], 2
0x18002ca93  jb      short loc_18002CABD
0x18002ca95  mov     rcx, [rcx+10h]
0x18002ca99  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x18002caa0  mov     edx, 1Dh
0x18002caa5  call    WPP_SF_
0x18002caaa  jmp     short loc_18002CABD
0x18002caac  mov     rdx, rdi
0x18002caaf  lea     rcx, aMicrosoftWindo; "Microsoft-Windows-Fax-Common-EnableServ"...
0x18002cab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cabb  mov     ebx, eax
0x18002cabd  mov     rcx, rsi; hLibModule
0x18002cac0  call    cs:__imp_FreeLibrary
0x18002cac7  nop     dword ptr [rax+rax+00h]
0x18002cacc  jmp     short loc_18002CB0E
0x18002cace  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cad5  cmp     rcx, r14
0x18002cad8  jz      short loc_18002CAFB
0x18002cada  test    byte ptr [rcx+1Ch], 2
0x18002cade  jz      short loc_18002CAFB
0x18002cae0  cmp     byte ptr [rcx+19h], 2
0x18002cae4  jb      short loc_18002CAFB
0x18002cae6  mov     rcx, [rcx+10h]
0x18002caea  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x18002caf1  mov     edx, 1Eh
0x18002caf6  call    WPP_SF_
0x18002cafb  mov     ebx, 485h
0x18002cb00  jmp     short loc_18002CB0E
0x18002cb02  xor     ebx, ebx
0x18002cb04  call    GetProductSKU
0x18002cb09  and     eax, 5Ch
0x18002cb0c  mov     [rdi], eax
0x18002cb0e  mov     eax, ebx
0x18002cb10  add     rsp, 28h
0x18002cb14  pop     r14
0x18002cb16  pop     rdi
0x18002cb17  pop     rsi
0x18002cb18  pop     rbx
0x18002cb19  retn
```
