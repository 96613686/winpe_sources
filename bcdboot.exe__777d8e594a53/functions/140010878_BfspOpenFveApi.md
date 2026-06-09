# BfspOpenFveApi

- ea: `0x140010878`
- end: `0x140010ba3`
- name: `BfspOpenFveApi`
- size: `811`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010728`
- `0x140010bac`

## callees

- `0x14000e628`
- `0x140010878`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400108a7`
- `KERNEL32!GetLastError` at `0x140010a4d`
- `KERNEL32!GetLastError` at `0x140010a87`
- `KERNEL32!GetLastError` at `0x140010ac1`
- `KERNEL32!GetLastError` at `0x140010afb`
- `KERNEL32!GetLastError` at `0x140010b32`
- `KERNEL32!GetLastError` at `0x140010b6b`
- `KERNEL32!GetLastError` at `0x1400108a7`
- `KERNEL32!GetLastError` at `0x140010a4d`
- `KERNEL32!GetLastError` at `0x140010a87`
- `KERNEL32!GetLastError` at `0x140010ac1`
- `KERNEL32!GetLastError` at `0x140010afb`
- `KERNEL32!GetLastError` at `0x140010b32`
- `KERNEL32!GetLastError` at `0x140010b6b`
- `KERNEL32!GetProcAddress` at `0x1400108e3`
- `KERNEL32!GetProcAddress` at `0x140010916`
- `KERNEL32!GetProcAddress` at `0x140010938`
- `KERNEL32!GetProcAddress` at `0x14001095a`
- `KERNEL32!GetProcAddress` at `0x14001097c`
- `KERNEL32!GetProcAddress` at `0x1400109a8`
- `KERNEL32!GetProcAddress` at `0x1400109d8`
- `KERNEL32!GetProcAddress` at `0x1400109fa`
- `KERNEL32!GetProcAddress` at `0x140010a1c`
- `KERNEL32!GetProcAddress` at `0x140010a3e`
- `KERNEL32!GetProcAddress` at `0x140010a78`
- `KERNEL32!GetProcAddress` at `0x140010ab2`
- `KERNEL32!GetProcAddress` at `0x140010aec`
- `KERNEL32!GetProcAddress` at `0x140010b23`
- `KERNEL32!GetProcAddress` at `0x140010b5c`
- `KERNEL32!GetProcAddress` at `0x1400108e3`
- `KERNEL32!GetProcAddress` at `0x140010916`
- `KERNEL32!GetProcAddress` at `0x140010938`
- `KERNEL32!GetProcAddress` at `0x14001095a`
- `KERNEL32!GetProcAddress` at `0x14001097c`
- `KERNEL32!GetProcAddress` at `0x1400109a8`
- `KERNEL32!GetProcAddress` at `0x1400109d8`
- `KERNEL32!GetProcAddress` at `0x1400109fa`
- `KERNEL32!GetProcAddress` at `0x140010a1c`
- `KERNEL32!GetProcAddress` at `0x140010a3e`
- `KERNEL32!GetProcAddress` at `0x140010a78`
- `KERNEL32!GetProcAddress` at `0x140010ab2`
- `KERNEL32!GetProcAddress` at `0x140010aec`
- `KERNEL32!GetProcAddress` at `0x140010b23`
- `KERNEL32!GetProcAddress` at `0x140010b5c`
- `KERNEL32!LoadLibraryExW` at `0x140010899`
- `KERNEL32!LoadLibraryExW` at `0x140010899`

## string_xrefs

- `0x1400108c2`: `Failed to load Fveapi.dll. HRESULT = [%x]`
- `0x14001088f`: `FVEAPI.DLL`
- `0x140010925`: `Failed GetProcAddress for FveOpenVolumeW . HRESULT = [%x]`
- `0x14001090f`: `FveOpenVolumeW`
- `0x140010975`: `FveCommitChangesEx`
- `0x140010969`: `Failed GetProcAddress for FveCommitChanges . HRESULT = [%x]`
- `0x140010953`: `FveCommitChanges`
- `0x140010990`: `Failed GetProcAddress for FveCommitChangesEx .`
- `0x140010ad6`: `Failed GetProcAddress for FveOpenVolumeByHandle . HRESULT = [%x]`
- `0x140010aab`: `FveOpenVolumeByHandle`

## pseudocode

```c
__int64 __fastcall BfspOpenFveApi(__int64 a1, _DWORD *a2)
{
  HMODULE Library; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  FARPROC ProcAddress; // rax
  const wchar_t *v8; // rdx
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax
  FARPROC v17; // rax
  signed int v18; // eax
  FARPROC v19; // rax
  signed int v20; // eax
  FARPROC v21; // rax
  signed int v22; // eax
  FARPROC v23; // rax
  signed int v24; // eax
  FARPROC v25; // rax
  signed int v26; // eax
  FARPROC v27; // rax
  signed int v28; // eax

  Library = LoadLibraryExW(L"FVEAPI.DLL", 0, 0);
  *(_QWORD *)a1 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    *a2 = 0;
    BfspLogMessage(4, L"Failed to load Fveapi.dll. HRESULT = [%x]");
    return v6;
  }
  *a2 = 1;
  ProcAddress = GetProcAddress(Library, "FveGetStatusW");
  *(_QWORD *)(a1 + 8) = ProcAddress;
  if ( !ProcAddress )
  {
    v8 = L"Failed GetProcAddress for FveGetStatusW . HRESULT = [%x]";
LABEL_7:
    v6 = -2147024769;
    goto LABEL_49;
  }
  v9 = GetProcAddress(*(HMODULE *)a1, "FveOpenVolumeW");
  *(_QWORD *)(a1 + 16) = v9;
  if ( !v9 )
  {
    v8 = L"Failed GetProcAddress for FveOpenVolumeW . HRESULT = [%x]";
    goto LABEL_7;
  }
  v10 = GetProcAddress(*(HMODULE *)a1, "FveAddAuthMethodInformation");
  *(_QWORD *)(a1 + 40) = v10;
  if ( !v10 )
  {
    v8 = L"Failed GetProcAddress for FveAddAuthMethodInformation . HRESULT = [%x]";
    goto LABEL_7;
  }
  v11 = GetProcAddress(*(HMODULE *)a1, "FveCommitChanges");
  *(_QWORD *)(a1 + 24) = v11;
  if ( !v11 )
  {
    v8 = L"Failed GetProcAddress for FveCommitChanges . HRESULT = [%x]";
    goto LABEL_7;
  }
  v12 = GetProcAddress(*(HMODULE *)a1, "FveCommitChangesEx");
  *(_QWORD *)(a1 + 32) = v12;
  if ( !v12 )
    BfspLogMessage(4, L"Failed GetProcAddress for FveCommitChangesEx .");
  v13 = GetProcAddress(*(HMODULE *)a1, "FveCloseVolume");
  *(_QWORD *)(a1 + 48) = v13;
  if ( !v13 )
  {
    v8 = L"Failed GetProcAddress for FveCloseVolume . HRESULT = [%x]";
LABEL_18:
    v6 = -2147024769;
    goto LABEL_49;
  }
  v14 = GetProcAddress(*(HMODULE *)a1, "FveGetAuthMethodGuids");
  *(_QWORD *)(a1 + 56) = v14;
  if ( !v14 )
  {
    v8 = L"Failed GetProcAddress for FveGetAuthMethodGuids . HRESULT = [%x]";
    goto LABEL_18;
  }
  v15 = GetProcAddress(*(HMODULE *)a1, "FveGetAuthMethodInformation");
  *(_QWORD *)(a1 + 64) = v15;
  if ( !v15 )
  {
    v8 = L"Failed GetProcAddress for FveGetAuthMethodInformation . HRESULT = [%x]";
    goto LABEL_18;
  }
  v16 = GetProcAddress(*(HMODULE *)a1, "FveKeyManagement");
  *(_QWORD *)(a1 + 72) = v16;
  if ( !v16 )
  {
    v8 = L"Failed GetProcAddress for FveKeyManagement . HRESULT = [%x]";
    goto LABEL_18;
  }
  v17 = GetProcAddress(*(HMODULE *)a1, "FveFindFirstVolume");
  *(_QWORD *)(a1 + 80) = v17;
  if ( v17 )
  {
    v19 = GetProcAddress(*(HMODULE *)a1, "FveFindNextVolume");
    *(_QWORD *)(a1 + 88) = v19;
    if ( v19 )
    {
      v21 = GetProcAddress(*(HMODULE *)a1, "FveOpenVolumeByHandle");
      *(_QWORD *)(a1 + 96) = v21;
      if ( v21 )
      {
        v23 = GetProcAddress(*(HMODULE *)a1, "FveGetStatus");
        *(_QWORD *)(a1 + 104) = v23;
        if ( v23 )
        {
          v25 = GetProcAddress(*(HMODULE *)a1, "FveGetVolumeNameW");
          *(_QWORD *)(a1 + 112) = v25;
          if ( v25 )
          {
            v6 = 0;
            v27 = GetProcAddress(*(HMODULE *)a1, "FveGetSecureBootBindingState");
            *(_QWORD *)(a1 + 120) = v27;
            if ( v27 )
              return v6;
            v28 = GetLastError();
            v6 = v28;
            if ( v28 > 0 )
              v6 = (unsigned __int16)v28 | 0x80070000;
            v8 = L"Failed GetProcAddress for FveGetSecureBootBindingState. HRESULT = [%x]";
LABEL_49:
            BfspLogMessage(4, v8);
            return v6;
          }
          v26 = GetLastError();
          v6 = v26;
          if ( v26 > 0 )
            v6 = (unsigned __int16)v26 | 0x80070000;
          BfspLogMessage(4, L"Failed GetProcAddress for FveGetVolumeNameW . HRESULT = [%x]");
        }
        else
        {
          v24 = GetLastError();
          v6 = v24;
          if ( v24 > 0 )
            v6 = (unsigned __int16)v24 | 0x80070000;
          BfspLogMessage(4, L"Failed GetProcAddress for FveGetStatus . HRESULT = [%x]");
        }
      }
      else
      {
        v22 = GetLastError();
        v6 = v22;
        if ( v22 > 0 )
          v6 = (unsigned __int16)v22 | 0x80070000;
        BfspLogMessage(4, L"Failed GetProcAddress for FveOpenVolumeByHandle . HRESULT = [%x]");
      }
    }
    else
    {
      v20 = GetLastError();
      v6 = v20;
      if ( v20 > 0 )
        v6 = (unsigned __int16)v20 | 0x80070000;
      BfspLogMessage(4, L"Failed GetProcAddress for FveFindNextVolume . HRESULT = [%x]");
    }
  }
  else
  {
    v18 = GetLastError();
    v6 = v18;
    if ( v18 > 0 )
      v6 = (unsigned __int16)v18 | 0x80070000;
    BfspLogMessage(4, L"Failed GetProcAddress for FveFindFirstVolume . HRESULT = [%x]");
  }
  return v6;
}

```

## disassembly

```asm
0x140010878  mov     [rsp+arg_0], rbx
0x14001087d  mov     [rsp+arg_8], rsi
0x140010882  push    rdi
0x140010883  sub     rsp, 20h
0x140010887  mov     rsi, rdx
0x14001088a  mov     rdi, rcx
0x14001088d  xor     edx, edx; hFile
0x14001088f  lea     rcx, aFveapiDll; "FVEAPI.DLL"
0x140010896  xor     r8d, r8d; dwFlags
0x140010899  call    cs:__imp_LoadLibraryExW
0x14001089f  mov     [rdi], rax
0x1400108a2  test    rax, rax
0x1400108a5  jnz     short loc_1400108D3
0x1400108a7  call    cs:__imp_GetLastError
0x1400108ad  mov     ebx, eax
0x1400108af  test    eax, eax
0x1400108b1  jle     short loc_1400108BC
0x1400108b3  movzx   ebx, ax
0x1400108b6  or      ebx, 80070000h
0x1400108bc  mov     dword ptr [rsi], 0
0x1400108c2  lea     rdx, aFailedToLoadFv; "Failed to load Fveapi.dll. HRESULT = [%"...
0x1400108c9  mov     ecx, 4
0x1400108ce  jmp     loc_140010B89
0x1400108d3  lea     rdx, aFvegetstatusw; "FveGetStatusW"
0x1400108da  mov     dword ptr [rsi], 1
0x1400108e0  mov     rcx, rax; hModule
0x1400108e3  call    cs:__imp_GetProcAddress
0x1400108e9  mov     [rdi+8], rax
0x1400108ed  test    rax, rax
0x1400108f0  jnz     short loc_14001090C
0x1400108f2  lea     rdx, aFailedGetproca; "Failed GetProcAddress for FveGetStatusW"...
0x1400108f9  mov     r8d, 8007007Fh
0x1400108ff  mov     ecx, 4
0x140010904  mov     ebx, r8d
0x140010907  jmp     loc_140010B8C
0x14001090c  mov     rcx, [rdi]; hModule
0x14001090f  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x140010916  call    cs:__imp_GetProcAddress
0x14001091c  mov     [rdi+10h], rax
0x140010920  test    rax, rax
0x140010923  jnz     short loc_14001092E
0x140010925  lea     rdx, aFailedGetproca_8; "Failed GetProcAddress for FveOpenVolume"...
0x14001092c  jmp     short loc_1400108F9
0x14001092e  mov     rcx, [rdi]; hModule
0x140010931  lea     rdx, aFveaddauthmeth_0; "FveAddAuthMethodInformation"
0x140010938  call    cs:__imp_GetProcAddress
0x14001093e  mov     [rdi+28h], rax
0x140010942  test    rax, rax
0x140010945  jnz     short loc_140010950
0x140010947  lea     rdx, aFailedGetproca_7; "Failed GetProcAddress for FveAddAuthMet"...
0x14001094e  jmp     short loc_1400108F9
0x140010950  mov     rcx, [rdi]; hModule
0x140010953  lea     rdx, aFvecommitchang_3; "FveCommitChanges"
0x14001095a  call    cs:__imp_GetProcAddress
0x140010960  mov     [rdi+18h], rax
0x140010964  test    rax, rax
0x140010967  jnz     short loc_140010972
0x140010969  lea     rdx, aFailedGetproca_6; "Failed GetProcAddress for FveCommitChan"...
0x140010970  jmp     short loc_1400108F9
0x140010972  mov     rcx, [rdi]; hModule
0x140010975  lea     rdx, aFvecommitchang_2; "FveCommitChangesEx"
0x14001097c  call    cs:__imp_GetProcAddress
0x140010982  mov     [rdi+20h], rax
0x140010986  mov     esi, 4
0x14001098b  test    rax, rax
0x14001098e  jnz     short loc_14001099E
0x140010990  lea     rdx, aFailedGetproca_2; "Failed GetProcAddress for FveCommitChan"...
0x140010997  mov     ecx, esi
0x140010999  call    BfspLogMessage
0x14001099e  mov     rcx, [rdi]; hModule
0x1400109a1  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x1400109a8  call    cs:__imp_GetProcAddress
0x1400109ae  mov     [rdi+30h], rax
0x1400109b2  test    rax, rax
0x1400109b5  jnz     short loc_1400109CE
0x1400109b7  lea     rdx, aFailedGetproca_13; "Failed GetProcAddress for FveCloseVolum"...
0x1400109be  mov     r8d, 8007007Fh
0x1400109c4  mov     ecx, esi
0x1400109c6  mov     ebx, r8d
0x1400109c9  jmp     loc_140010B8C
0x1400109ce  mov     rcx, [rdi]; hModule
0x1400109d1  lea     rdx, aFvegetauthmeth_0; "FveGetAuthMethodGuids"
0x1400109d8  call    cs:__imp_GetProcAddress
0x1400109de  mov     [rdi+38h], rax
0x1400109e2  test    rax, rax
0x1400109e5  jnz     short loc_1400109F0
0x1400109e7  lea     rdx, aFailedGetproca_9; "Failed GetProcAddress for FveGetAuthMet"...
0x1400109ee  jmp     short loc_1400109BE
0x1400109f0  mov     rcx, [rdi]; hModule
0x1400109f3  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x1400109fa  call    cs:__imp_GetProcAddress
0x140010a00  mov     [rdi+40h], rax
0x140010a04  test    rax, rax
0x140010a07  jnz     short loc_140010A12
0x140010a09  lea     rdx, aFailedGetproca_12; "Failed GetProcAddress for FveGetAuthMet"...
0x140010a10  jmp     short loc_1400109BE
0x140010a12  mov     rcx, [rdi]; hModule
0x140010a15  lea     rdx, aFvekeymanageme; "FveKeyManagement"
0x140010a1c  call    cs:__imp_GetProcAddress
0x140010a22  mov     [rdi+48h], rax
0x140010a26  test    rax, rax
0x140010a29  jnz     short loc_140010A34
0x140010a2b  lea     rdx, aFailedGetproca_5; "Failed GetProcAddress for FveKeyManagem"...
0x140010a32  jmp     short loc_1400109BE
0x140010a34  mov     rcx, [rdi]; hModule
0x140010a37  lea     rdx, aFvefindfirstvo; "FveFindFirstVolume"
0x140010a3e  call    cs:__imp_GetProcAddress
0x140010a44  mov     [rdi+50h], rax
0x140010a48  test    rax, rax
0x140010a4b  jnz     short loc_140010A6E
0x140010a4d  call    cs:__imp_GetLastError
0x140010a53  mov     ebx, eax
0x140010a55  test    eax, eax
0x140010a57  jle     short loc_140010A62
0x140010a59  movzx   ebx, ax
0x140010a5c  or      ebx, 80070000h
0x140010a62  lea     rdx, aFailedGetproca_1; "Failed GetProcAddress for FveFindFirstV"...
0x140010a69  jmp     loc_140010B87
0x140010a6e  mov     rcx, [rdi]; hModule
0x140010a71  lea     rdx, aFvefindnextvol; "FveFindNextVolume"
0x140010a78  call    cs:__imp_GetProcAddress
0x140010a7e  mov     [rdi+58h], rax
0x140010a82  test    rax, rax
0x140010a85  jnz     short loc_140010AA8
0x140010a87  call    cs:__imp_GetLastError
0x140010a8d  mov     ebx, eax
0x140010a8f  test    eax, eax
0x140010a91  jle     short loc_140010A9C
0x140010a93  movzx   ebx, ax
0x140010a96  or      ebx, 80070000h
0x140010a9c  lea     rdx, aFailedGetproca_3; "Failed GetProcAddress for FveFindNextVo"...
0x140010aa3  jmp     loc_140010B87
0x140010aa8  mov     rcx, [rdi]; hModule
0x140010aab  lea     rdx, aFveopenvolumeb; "FveOpenVolumeByHandle"
0x140010ab2  call    cs:__imp_GetProcAddress
0x140010ab8  mov     [rdi+60h], rax
0x140010abc  test    rax, rax
0x140010abf  jnz     short loc_140010AE2
0x140010ac1  call    cs:__imp_GetLastError
0x140010ac7  mov     ebx, eax
0x140010ac9  test    eax, eax
0x140010acb  jle     short loc_140010AD6
0x140010acd  movzx   ebx, ax
0x140010ad0  or      ebx, 80070000h
0x140010ad6  lea     rdx, aFailedGetproca_11; "Failed GetProcAddress for FveOpenVolume"...
0x140010add  jmp     loc_140010B87
0x140010ae2  mov     rcx, [rdi]; hModule
0x140010ae5  lea     rdx, aFvegetstatus; "FveGetStatus"
0x140010aec  call    cs:__imp_GetProcAddress
0x140010af2  mov     [rdi+68h], rax
0x140010af6  test    rax, rax
0x140010af9  jnz     short loc_140010B19
0x140010afb  call    cs:__imp_GetLastError
0x140010b01  mov     ebx, eax
0x140010b03  test    eax, eax
0x140010b05  jle     short loc_140010B10
0x140010b07  movzx   ebx, ax
0x140010b0a  or      ebx, 80070000h
0x140010b10  lea     rdx, aFailedGetproca_4; "Failed GetProcAddress for FveGetStatus "...
0x140010b17  jmp     short loc_140010B87
0x140010b19  mov     rcx, [rdi]; hModule
0x140010b1c  lea     rdx, aFvegetvolumena; "FveGetVolumeNameW"
0x140010b23  call    cs:__imp_GetProcAddress
0x140010b29  mov     [rdi+70h], rax
0x140010b2d  test    rax, rax
0x140010b30  jnz     short loc_140010B50
0x140010b32  call    cs:__imp_GetLastError
0x140010b38  mov     ebx, eax
0x140010b3a  test    eax, eax
0x140010b3c  jle     short loc_140010B47
0x140010b3e  movzx   ebx, ax
0x140010b41  or      ebx, 80070000h
0x140010b47  lea     rdx, aFailedGetproca_10; "Failed GetProcAddress for FveGetVolumeN"...
0x140010b4e  jmp     short loc_140010B87
0x140010b50  mov     rcx, [rdi]; hModule
0x140010b53  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x140010b5a  xor     ebx, ebx
0x140010b5c  call    cs:__imp_GetProcAddress
0x140010b62  mov     [rdi+78h], rax
0x140010b66  test    rax, rax
0x140010b69  jnz     short loc_140010B91
0x140010b6b  call    cs:__imp_GetLastError
0x140010b71  mov     ebx, eax
0x140010b73  test    eax, eax
0x140010b75  jle     short loc_140010B80
0x140010b77  movzx   ebx, ax
0x140010b7a  or      ebx, 80070000h
0x140010b80  lea     rdx, aFailedGetproca_0; "Failed GetProcAddress for FveGetSecureB"...
0x140010b87  mov     ecx, esi
0x140010b89  mov     r8d, ebx
0x140010b8c  call    BfspLogMessage
0x140010b91  mov     rsi, [rsp+28h+arg_8]
0x140010b96  mov     eax, ebx
0x140010b98  mov     rbx, [rsp+28h+arg_0]
0x140010b9d  add     rsp, 20h
0x140010ba1  pop     rdi
0x140010ba2  retn
```
