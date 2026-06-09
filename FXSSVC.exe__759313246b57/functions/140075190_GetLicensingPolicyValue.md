# GetLicensingPolicyValue

- ea: `0x140075190`
- end: `0x14007533d`
- name: `GetLicensingPolicyValue`
- size: `429`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140025b04`
- `0x1400750e8`
- `0x14007551c`
- `0x1400755c4`
- `0x14007566c`

## callees

- `0x140004c78`
- `0x14006a188`
- `0x140075190`
- `0x140075344`
- `0x140086e82`
- `0x14008b010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140075274`
- `KERNEL32!FreeLibrary` at `0x140075274`
- `KERNEL32!GetLastError` at `0x140075227`
- `KERNEL32!GetLastError` at `0x140075227`
- `KERNEL32!LoadLibraryW` at `0x1400751f8`
- `KERNEL32!LoadLibraryW` at `0x1400751f8`
- `KERNEL32!GetProcAddress` at `0x140075216`
- `KERNEL32!GetProcAddress` at `0x140075216`

## string_xrefs

- `0x1400752b9`: `Microsoft-Windows-Fax-Common-EnableServerPolicy`
- `0x1400752da`: `Microsoft-Windows-Fax-Common-DeviceLimit`
- `0x1400751f1`: `slc.dll`

## pseudocode

```c
__int64 __fastcall GetLicensingPolicyValue(wchar_t *String1, int *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v6; // rbx
  FARPROC ProcAddress; // rax
  DWORD LastError; // edi
  int v9; // ebx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
  }
  if ( !a2 )
    return 2147942487LL;
  if ( LonghornOrMore() )
  {
    LibraryW = LoadLibraryW(L"slc.dll");
    v6 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "SLGetWindowsInformationDWORD");
      if ( ProcAddress )
      {
        LastError = ((__int64 (__fastcall *)(wchar_t *, int *))ProcAddress)(String1, a2);
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
        }
      }
      FreeLibrary(v6);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
      }
      return 1157;
    }
    return LastError;
  }
  LastError = 0;
  if ( wcscmp_0(String1, L"Microsoft-Windows-Fax-Common-EnableServerPolicy") )
  {
    if ( wcscmp_0(String1, L"Microsoft-Windows-Fax-Common-DeviceLimit") )
      return LastError;
    v9 = 0;
    v10 = GetProductSKU() - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 2;
        if ( !v12 )
          goto LABEL_36;
        v13 = v12 - 4;
        if ( !v13 || (v14 = v13 - 8) == 0 )
        {
          v9 = -1;
          goto LABEL_33;
        }
        v15 = v14 - 16;
        if ( !v15 )
          goto LABEL_32;
        v16 = v15 - 32;
        if ( !v16 )
        {
LABEL_36:
          v9 = 4;
          goto LABEL_33;
        }
        if ( v16 != 64 )
        {
LABEL_33:
          *a2 = v9;
          return LastError;
        }
      }
    }
LABEL_32:
    v9 = 1;
    goto LABEL_33;
  }
  *a2 = GetProductSKU() & 0x5C;
  return LastError;
}

```

## disassembly

```asm
0x140075190  push    rbx
0x140075192  push    rbp
0x140075193  push    rsi
0x140075194  push    rdi
0x140075195  push    r15
0x140075197  sub     rsp, 20h
0x14007519b  mov     rsi, rdx
0x14007519e  mov     rbp, rcx
0x1400751a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400751a8  lea     r15, WPP_GLOBAL_Control
0x1400751af  cmp     rcx, r15
0x1400751b2  jz      short loc_1400751D5
0x1400751b4  test    byte ptr [rcx+1Ch], 2
0x1400751b8  jz      short loc_1400751D5
0x1400751ba  cmp     byte ptr [rcx+19h], 5
0x1400751be  jb      short loc_1400751D5
0x1400751c0  mov     rcx, [rcx+10h]
0x1400751c4  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x1400751cb  mov     edx, 1Ch
0x1400751d0  call    WPP_SF_
0x1400751d5  test    rsi, rsi
0x1400751d8  jnz     short loc_1400751E4
0x1400751da  mov     eax, 80070057h
0x1400751df  jmp     loc_140075325
0x1400751e4  call    LonghornOrMore
0x1400751e9  test    eax, eax
0x1400751eb  jz      loc_1400752B9
0x1400751f1  lea     rcx, LibFileName; "slc.dll"
0x1400751f8  call    cs:__imp_LoadLibraryW
0x1400751ff  nop     dword ptr [rax+rax+00h]
0x140075204  mov     rbx, rax
0x140075207  test    rax, rax
0x14007520a  jz      short loc_140075285
0x14007520c  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x140075213  mov     rcx, rax; hModule
0x140075216  call    cs:__imp_GetProcAddress
0x14007521d  nop     dword ptr [rax+rax+00h]
0x140075222  test    rax, rax
0x140075225  jnz     short loc_140075264
0x140075227  call    cs:__imp_GetLastError
0x14007522e  nop     dword ptr [rax+rax+00h]
0x140075233  mov     edi, eax
0x140075235  mov     rcx, cs:WPP_GLOBAL_Control
0x14007523c  cmp     rcx, r15
0x14007523f  jz      short loc_140075271
0x140075241  test    byte ptr [rcx+1Ch], 2
0x140075245  jz      short loc_140075271
0x140075247  cmp     byte ptr [rcx+19h], 2
0x14007524b  jb      short loc_140075271
0x14007524d  mov     rcx, [rcx+10h]
0x140075251  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x140075258  mov     edx, 1Dh
0x14007525d  call    WPP_SF_
0x140075262  jmp     short loc_140075271
0x140075264  mov     rdx, rsi
0x140075267  mov     rcx, rbp
0x14007526a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007526f  mov     edi, eax
0x140075271  mov     rcx, rbx; hLibModule
0x140075274  call    cs:__imp_FreeLibrary
0x14007527b  nop     dword ptr [rax+rax+00h]
0x140075280  jmp     loc_140075323
0x140075285  mov     rcx, cs:WPP_GLOBAL_Control
0x14007528c  cmp     rcx, r15
0x14007528f  jz      short loc_1400752B2
0x140075291  test    byte ptr [rcx+1Ch], 2
0x140075295  jz      short loc_1400752B2
0x140075297  cmp     byte ptr [rcx+19h], 2
0x14007529b  jb      short loc_1400752B2
0x14007529d  mov     rcx, [rcx+10h]
0x1400752a1  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x1400752a8  mov     edx, 1Eh
0x1400752ad  call    WPP_SF_
0x1400752b2  mov     edi, 485h
0x1400752b7  jmp     short loc_140075323
0x1400752b9  lea     rdx, aMicrosoftWindo; "Microsoft-Windows-Fax-Common-EnableServ"...
0x1400752c0  mov     rcx, rbp; String1
0x1400752c3  xor     edi, edi
0x1400752c5  call    wcscmp_0
0x1400752ca  test    eax, eax
0x1400752cc  jnz     short loc_1400752DA
0x1400752ce  call    GetProductSKU
0x1400752d3  and     eax, 5Ch
0x1400752d6  mov     [rsi], eax
0x1400752d8  jmp     short loc_140075323
0x1400752da  lea     rdx, aMicrosoftWindo_1; "Microsoft-Windows-Fax-Common-DeviceLimi"...
0x1400752e1  mov     rcx, rbp; String1
0x1400752e4  call    wcscmp_0
0x1400752e9  test    eax, eax
0x1400752eb  jnz     short loc_140075323
0x1400752ed  xor     ebx, ebx
0x1400752ef  call    GetProductSKU
0x1400752f4  sub     eax, 1
0x1400752f7  jz      short loc_14007531C
0x1400752f9  sub     eax, 1
0x1400752fc  jz      short loc_14007531C
0x1400752fe  sub     eax, 2
0x140075301  jz      short loc_140075336
0x140075303  sub     eax, 4
0x140075306  jz      short loc_140075331
0x140075308  sub     eax, 8
0x14007530b  jz      short loc_140075331
0x14007530d  sub     eax, 10h
0x140075310  jz      short loc_14007531C
0x140075312  sub     eax, 20h ; ' '
0x140075315  jz      short loc_140075336
0x140075317  cmp     eax, 40h ; '@'
0x14007531a  jnz     short loc_140075321
0x14007531c  mov     ebx, 1
0x140075321  mov     [rsi], ebx
0x140075323  mov     eax, edi
0x140075325  add     rsp, 20h
0x140075329  pop     r15
0x14007532b  pop     rdi
0x14007532c  pop     rsi
0x14007532d  pop     rbp
0x14007532e  pop     rbx
0x14007532f  retn
0x140075331  or      ebx, 0FFFFFFFFh
0x140075334  jmp     short loc_140075321
0x140075336  mov     ebx, 4
0x14007533b  jmp     short loc_140075321
```
