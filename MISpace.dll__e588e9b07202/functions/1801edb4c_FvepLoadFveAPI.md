# FvepLoadFveAPI

- ea: `0x1801edb4c`
- end: `0x1801ede62`
- name: `FvepLoadFveAPI`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801ed940`

## callees

- `0x180006290`
- `0x180006cf4`
- `0x1801edb4c`
- `0x1801ede68`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801edbbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801edbbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801edbc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801edd6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801edbc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801edd6d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801edc0c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801edc0c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801edd85`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801edd85`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edc24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edc42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edc60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edc7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edc97`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edcb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edcd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edcf7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edd11`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edd2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edd44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edd5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edd9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801eddaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801eddc3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edc24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edc42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edc60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edc7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edc97`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edcb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edcd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edcf7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edd11`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edd2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edd44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edd5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801edd9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801eddaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801eddc3`

## string_xrefs

- `0x1801edd3a`: `FveDeleteAuthMethod`
- `0x1801edd53`: `FveCommitChanges`
- `0x1801edd90`: `FveCommitChangesEx`
- `0x1801edbe6`: `\FVEAPI.DLL`
- `0x1801edc1a`: `FveOpenVolumeW`

## pseudocode

```c
__int64 __fastcall FvepLoadFveAPI(HMODULE *a1, __int64 a2)
{
  signed int v4; // eax
  unsigned int v5; // ebx
  HMODULE Library; // rax
  HMODULE v7; // rdi
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v21; // [rsp+20h] [rbp-E0h]
  __int128 v22; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+40h] [rbp-C0h]
  __int128 v24; // [rsp+50h] [rbp-B0h]
  __int128 v25; // [rsp+60h] [rbp-A0h]
  __int128 v26; // [rsp+70h] [rbp-90h]
  __int128 v27; // [rsp+80h] [rbp-80h]
  __int128 v28; // [rsp+90h] [rbp-70h]
  __int128 v29; // [rsp+A0h] [rbp-60h]
  __int128 v30; // [rsp+B0h] [rbp-50h]
  __int128 v31; // [rsp+C0h] [rbp-40h]
  INT_PTR (__stdcall *v32)(); // [rsp+D0h] [rbp-30h]
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(&v22, 0, 0xA8u);
  *a1 = 0;
  *(_QWORD *)&v21 = -1;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    goto LABEL_2;
  v5 = StringCchCatW(Buffer, 0x104u, L"\\FVEAPI.DLL");
  if ( (v5 & 0x80000000) != 0 )
    return v5;
  Library = LoadLibraryExW(Buffer, 0, 0);
  v7 = Library;
  if ( Library )
  {
    *((_QWORD *)&v21 + 1) = GetProcAddress(Library, "FveOpenVolumeW");
    if ( *((_QWORD *)&v21 + 1) )
    {
      *(_QWORD *)&v22 = GetProcAddress(v7, "FveCloseVolume");
      if ( (_QWORD)v22 )
      {
        *(_QWORD *)&v24 = GetProcAddress(v7, "FveGetStatus");
        if ( (_QWORD)v24 )
        {
          *(_QWORD *)&v27 = GetProcAddress(v7, "FveAddAuthMethodInformation");
          if ( (_QWORD)v27 )
          {
            *((_QWORD *)&v26 + 1) = GetProcAddress(v7, "FveGetAuthMethodInformation");
            if ( *((_QWORD *)&v26 + 1) )
            {
              *((_QWORD *)&v27 + 1) = GetProcAddress(v7, "FveDeleteAuthMethod");
              if ( *((_QWORD *)&v27 + 1) )
              {
                *((_QWORD *)&v22 + 1) = GetProcAddress(v7, "FveCommitChanges");
                if ( *((_QWORD *)&v22 + 1) )
                {
                  *(_QWORD *)&v23 = GetProcAddress(v7, "FveCommitChangesEx");
                  *(_QWORD *)&v28 = GetProcAddress(v7, "FveGetSecureBootBindingState");
                  ProcAddress = GetProcAddress(v7, "FveControl");
                  goto LABEL_23;
                }
              }
            }
          }
        }
      }
    }
    else
    {
      *((_QWORD *)&v24 + 1) = GetProcAddress(v7, "FveGetStatusBasicW");
      if ( *((_QWORD *)&v24 + 1) )
      {
        *(_QWORD *)&v25 = GetProcAddress(v7, "FveSetFipsAllowDisabled");
        if ( (_QWORD)v25 )
        {
          if ( GetProcAddress(v7, "FveDisableAuthenticationW") )
          {
            *((_QWORD *)&v25 + 1) = GetProcAddress(v7, "FveDisableAuthenticationW");
            if ( *((_QWORD *)&v25 + 1) )
            {
              *(_QWORD *)&v26 = GetProcAddress(v7, "FveEnableAuthenticationW");
              if ( (_QWORD)v26 )
              {
                ProcAddress = v32;
LABEL_23:
                v10 = v22;
                *a1 = v7;
                *(_OWORD *)a2 = v21;
                v11 = v23;
                *(_OWORD *)(a2 + 16) = v10;
                v12 = v24;
                *(_OWORD *)(a2 + 32) = v11;
                v13 = v25;
                *(_OWORD *)(a2 + 48) = v12;
                v14 = v26;
                *(_OWORD *)(a2 + 64) = v13;
                v15 = v27;
                *(_OWORD *)(a2 + 80) = v14;
                v16 = v28;
                *(_OWORD *)(a2 + 96) = v15;
                v17 = v29;
                *(_OWORD *)(a2 + 112) = v16;
                v18 = v30;
                *(_OWORD *)(a2 + 128) = v17;
                v19 = v31;
                *(_OWORD *)(a2 + 144) = v18;
                *(_OWORD *)(a2 + 160) = v19;
                *(_QWORD *)(a2 + 176) = ProcAddress;
                return v5;
              }
            }
          }
        }
      }
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    FreeLibrary(v7);
  }
  else
  {
LABEL_2:
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  return v5;
}

```

## disassembly

```asm
0x1801edb4c  mov     [rsp-8+arg_10], rbx
0x1801edb51  mov     [rsp-8+arg_18], rsi
0x1801edb56  push    rbp
0x1801edb57  push    rdi
0x1801edb58  push    r14
0x1801edb5a  lea     rbp, [rsp-200h]
0x1801edb62  sub     rsp, 300h
0x1801edb69  mov     rax, cs:__security_cookie
0x1801edb70  xor     rax, rsp
0x1801edb73  mov     [rbp+210h+var_20], rax
0x1801edb7a  mov     rsi, rdx
0x1801edb7d  mov     r14, rcx
0x1801edb80  xor     edx, edx; Val
0x1801edb82  lea     rcx, [rbp+210h+Buffer]; void *
0x1801edb86  mov     r8d, 208h; Size
0x1801edb8c  call    memset_0
0x1801edb91  xor     edx, edx; Val
0x1801edb93  lea     rcx, [rsp+310h+var_2E0]; void *
0x1801edb98  mov     r8d, 0A8h; Size
0x1801edb9e  call    memset_0
0x1801edba3  mov     ebx, 104h
0x1801edba8  mov     qword ptr [r14], 0
0x1801edbaf  mov     edx, ebx; uSize
0x1801edbb1  mov     qword ptr [rsp+310h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x1801edbba  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x1801edbbe  call    cs:__imp_GetSystemDirectoryW
0x1801edbc4  test    eax, eax
0x1801edbc6  jnz     short loc_1801EDBE6
0x1801edbc8  call    cs:__imp_GetLastError
0x1801edbce  mov     ebx, eax
0x1801edbd0  test    eax, eax
0x1801edbd2  jle     loc_1801EDE39
0x1801edbd8  movzx   ebx, ax
0x1801edbdb  or      ebx, 80070000h
0x1801edbe1  jmp     loc_1801EDE39
0x1801edbe6  lea     r8, aFveapiDll_0; "\\FVEAPI.DLL"
0x1801edbed  mov     rdx, rbx; cchDest
0x1801edbf0  lea     rcx, [rbp+210h+Buffer]; pszDest
0x1801edbf4  call    StringCchCatW
0x1801edbf9  mov     ebx, eax
0x1801edbfb  test    eax, eax
0x1801edbfd  js      loc_1801EDE39
0x1801edc03  xor     r8d, r8d; dwFlags
0x1801edc06  lea     rcx, [rbp+210h+Buffer]; lpLibFileName
0x1801edc0a  xor     edx, edx; hFile
0x1801edc0c  call    cs:__imp_LoadLibraryExW
0x1801edc12  mov     rdi, rax
0x1801edc15  test    rax, rax
0x1801edc18  jz      short loc_1801EDBC8
0x1801edc1a  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x1801edc21  mov     rcx, rax; hModule
0x1801edc24  call    cs:__imp_GetProcAddress
0x1801edc2a  mov     qword ptr [rsp+310h+var_2F0+8], rax
0x1801edc2f  mov     rcx, rdi; hModule
0x1801edc32  test    rax, rax
0x1801edc35  jnz     loc_1801EDCD2
0x1801edc3b  lea     rdx, aFvegetstatusba; "FveGetStatusBasicW"
0x1801edc42  call    cs:__imp_GetProcAddress
0x1801edc48  mov     qword ptr [rsp+310h+var_2C0+8], rax
0x1801edc4d  test    rax, rax
0x1801edc50  jz      loc_1801EDD6D
0x1801edc56  lea     rdx, aFvesetfipsallo; "FveSetFipsAllowDisabled"
0x1801edc5d  mov     rcx, rdi; hModule
0x1801edc60  call    cs:__imp_GetProcAddress
0x1801edc66  mov     qword ptr [rsp+310h+var_2B0], rax
0x1801edc6b  test    rax, rax
0x1801edc6e  jz      loc_1801EDD6D
0x1801edc74  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x1801edc7b  mov     rcx, rdi; hModule
0x1801edc7e  call    cs:__imp_GetProcAddress
0x1801edc84  test    rax, rax
0x1801edc87  jz      loc_1801EDD6D
0x1801edc8d  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x1801edc94  mov     rcx, rdi; hModule
0x1801edc97  call    cs:__imp_GetProcAddress
0x1801edc9d  mov     qword ptr [rsp+310h+var_2B0+8], rax
0x1801edca2  test    rax, rax
0x1801edca5  jz      loc_1801EDD6D
0x1801edcab  lea     rdx, aFveenableauthe; "FveEnableAuthenticationW"
0x1801edcb2  mov     rcx, rdi; hModule
0x1801edcb5  call    cs:__imp_GetProcAddress
0x1801edcbb  mov     qword ptr [rsp+310h+var_2A0], rax
0x1801edcc0  test    rax, rax
0x1801edcc3  jz      loc_1801EDD6D
0x1801edcc9  mov     rax, [rbp+210h+var_240]
0x1801edccd  jmp     loc_1801EDDC9
0x1801edcd2  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x1801edcd9  call    cs:__imp_GetProcAddress
0x1801edcdf  mov     qword ptr [rsp+310h+var_2E0], rax
0x1801edce4  test    rax, rax
0x1801edce7  jz      loc_1801EDD6D
0x1801edced  lea     rdx, aFvegetstatus; "FveGetStatus"
0x1801edcf4  mov     rcx, rdi; hModule
0x1801edcf7  call    cs:__imp_GetProcAddress
0x1801edcfd  mov     qword ptr [rsp+310h+var_2C0], rax
0x1801edd02  test    rax, rax
0x1801edd05  jz      short loc_1801EDD6D
0x1801edd07  lea     rdx, aFveaddauthmeth; "FveAddAuthMethodInformation"
0x1801edd0e  mov     rcx, rdi; hModule
0x1801edd11  call    cs:__imp_GetProcAddress
0x1801edd17  mov     qword ptr [rbp+210h+var_290], rax
0x1801edd1b  test    rax, rax
0x1801edd1e  jz      short loc_1801EDD6D
0x1801edd20  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x1801edd27  mov     rcx, rdi; hModule
0x1801edd2a  call    cs:__imp_GetProcAddress
0x1801edd30  mov     qword ptr [rsp+310h+var_2A0+8], rax
0x1801edd35  test    rax, rax
0x1801edd38  jz      short loc_1801EDD6D
0x1801edd3a  lea     rdx, aFvedeleteauthm; "FveDeleteAuthMethod"
0x1801edd41  mov     rcx, rdi; hModule
0x1801edd44  call    cs:__imp_GetProcAddress
0x1801edd4a  mov     qword ptr [rbp+210h+var_290+8], rax
0x1801edd4e  test    rax, rax
0x1801edd51  jz      short loc_1801EDD6D
0x1801edd53  lea     rdx, aFvecommitchang_0; "FveCommitChanges"
0x1801edd5a  mov     rcx, rdi; hModule
0x1801edd5d  call    cs:__imp_GetProcAddress
0x1801edd63  mov     qword ptr [rsp+310h+var_2E0+8], rax
0x1801edd68  test    rax, rax
0x1801edd6b  jnz     short loc_1801EDD90
0x1801edd6d  call    cs:__imp_GetLastError
0x1801edd73  mov     ebx, eax
0x1801edd75  test    eax, eax
0x1801edd77  jle     short loc_1801EDD82
0x1801edd79  movzx   ebx, ax
0x1801edd7c  or      ebx, 80070000h
0x1801edd82  mov     rcx, rdi; hLibModule
0x1801edd85  call    cs:__imp_FreeLibrary
0x1801edd8b  jmp     loc_1801EDE39
0x1801edd90  lea     rdx, aFvecommitchang; "FveCommitChangesEx"
0x1801edd97  mov     rcx, rdi; hModule
0x1801edd9a  call    cs:__imp_GetProcAddress
0x1801edda0  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x1801edda7  mov     rcx, rdi; hModule
0x1801eddaa  mov     qword ptr [rsp+310h+var_2D0], rax
0x1801eddaf  call    cs:__imp_GetProcAddress
0x1801eddb5  lea     rdx, aFvecontrol; "FveControl"
0x1801eddbc  mov     rcx, rdi; hModule
0x1801eddbf  mov     qword ptr [rbp+210h+var_280], rax
0x1801eddc3  call    cs:__imp_GetProcAddress
0x1801eddc9  movaps  xmm0, [rsp+310h+var_2F0]
0x1801eddce  movaps  xmm1, [rsp+310h+var_2E0]
0x1801eddd3  mov     [r14], rdi
0x1801eddd6  movups  xmmword ptr [rsi], xmm0
0x1801eddd9  movaps  xmm0, [rsp+310h+var_2D0]
0x1801eddde  movups  xmmword ptr [rsi+10h], xmm1
0x1801edde2  movaps  xmm1, [rsp+310h+var_2C0]
0x1801edde7  movups  xmmword ptr [rsi+20h], xmm0
0x1801eddeb  movaps  xmm0, [rsp+310h+var_2B0]
0x1801eddf0  movups  xmmword ptr [rsi+30h], xmm1
0x1801eddf4  movaps  xmm1, [rsp+310h+var_2A0]
0x1801eddf9  movups  xmmword ptr [rsi+40h], xmm0
0x1801eddfd  movaps  xmm0, [rbp+210h+var_290]
0x1801ede01  movups  xmmword ptr [rsi+50h], xmm1
0x1801ede05  movaps  xmm1, [rbp+210h+var_280]
0x1801ede09  movups  xmmword ptr [rsi+60h], xmm0
0x1801ede0d  movaps  xmm0, [rbp+210h+var_270]
0x1801ede11  movups  xmmword ptr [rsi+70h], xmm1
0x1801ede15  movaps  xmm1, [rbp+210h+var_260]
0x1801ede19  movups  xmmword ptr [rsi+80h], xmm0
0x1801ede20  movaps  xmm0, [rbp+210h+var_250]
0x1801ede24  movups  xmmword ptr [rsi+90h], xmm1
0x1801ede2b  movups  xmmword ptr [rsi+0A0h], xmm0
0x1801ede32  mov     [rsi+0B0h], rax
0x1801ede39  mov     eax, ebx
0x1801ede3b  mov     rcx, [rbp+210h+var_20]
0x1801ede42  xor     rcx, rsp; StackCookie
0x1801ede45  call    __security_check_cookie
0x1801ede4a  lea     r11, [rsp+310h+var_10]
0x1801ede52  mov     rbx, [r11+30h]
0x1801ede56  mov     rsi, [r11+38h]
0x1801ede5a  mov     rsp, r11
0x1801ede5d  pop     r14
0x1801ede5f  pop     rdi
0x1801ede60  pop     rbp
0x1801ede61  retn
```
