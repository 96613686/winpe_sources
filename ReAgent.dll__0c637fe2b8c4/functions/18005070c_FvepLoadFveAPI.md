# FvepLoadFveAPI

- ea: `0x18005070c`
- end: `0x180050a22`
- name: `FvepLoadFveAPI`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180050500`

## callees

- `0x180006e84`
- `0x18005070c`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180050788`
- `KERNEL32!GetLastError` at `0x18005092d`
- `KERNEL32!GetLastError` at `0x180050788`
- `KERNEL32!GetLastError` at `0x18005092d`
- `KERNEL32!GetProcAddress` at `0x1800507e4`
- `KERNEL32!GetProcAddress` at `0x180050802`
- `KERNEL32!GetProcAddress` at `0x180050820`
- `KERNEL32!GetProcAddress` at `0x18005083e`
- `KERNEL32!GetProcAddress` at `0x180050857`
- `KERNEL32!GetProcAddress` at `0x180050875`
- `KERNEL32!GetProcAddress` at `0x180050899`
- `KERNEL32!GetProcAddress` at `0x1800508b7`
- `KERNEL32!GetProcAddress` at `0x1800508d1`
- `KERNEL32!GetProcAddress` at `0x1800508ea`
- `KERNEL32!GetProcAddress` at `0x180050904`
- `KERNEL32!GetProcAddress` at `0x18005091d`
- `KERNEL32!GetProcAddress` at `0x18005095a`
- `KERNEL32!GetProcAddress` at `0x18005096f`
- `KERNEL32!GetProcAddress` at `0x180050983`
- `KERNEL32!GetProcAddress` at `0x1800507e4`
- `KERNEL32!GetProcAddress` at `0x180050802`
- `KERNEL32!GetProcAddress` at `0x180050820`
- `KERNEL32!GetProcAddress` at `0x18005083e`
- `KERNEL32!GetProcAddress` at `0x180050857`
- `KERNEL32!GetProcAddress` at `0x180050875`
- `KERNEL32!GetProcAddress` at `0x180050899`
- `KERNEL32!GetProcAddress` at `0x1800508b7`
- `KERNEL32!GetProcAddress` at `0x1800508d1`
- `KERNEL32!GetProcAddress` at `0x1800508ea`
- `KERNEL32!GetProcAddress` at `0x180050904`
- `KERNEL32!GetProcAddress` at `0x18005091d`
- `KERNEL32!GetProcAddress` at `0x18005095a`
- `KERNEL32!GetProcAddress` at `0x18005096f`
- `KERNEL32!GetProcAddress` at `0x180050983`
- `KERNEL32!FreeLibrary` at `0x180050945`
- `KERNEL32!FreeLibrary` at `0x180050945`
- `KERNEL32!LoadLibraryExW` at `0x1800507cc`
- `KERNEL32!LoadLibraryExW` at `0x1800507cc`
- `KERNEL32!GetSystemDirectoryW` at `0x18005077e`
- `KERNEL32!GetSystemDirectoryW` at `0x18005077e`

## string_xrefs

- `0x1800507da`: `FveOpenVolumeW`
- `0x180050913`: `FveCommitChanges`
- `0x1800507a6`: `\FVEAPI.DLL`
- `0x1800508fa`: `FveDeleteAuthMethod`
- `0x180050950`: `FveCommitChangesEx`

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
0x18005070c  mov     [rsp-8+arg_10], rbx
0x180050711  mov     [rsp-8+arg_18], rsi
0x180050716  push    rbp
0x180050717  push    rdi
0x180050718  push    r14
0x18005071a  lea     rbp, [rsp-200h]
0x180050722  sub     rsp, 300h
0x180050729  mov     rax, cs:__security_cookie
0x180050730  xor     rax, rsp
0x180050733  mov     [rbp+210h+var_20], rax
0x18005073a  mov     rsi, rdx
0x18005073d  mov     r14, rcx
0x180050740  xor     edx, edx; Val
0x180050742  lea     rcx, [rbp+210h+Buffer]; void *
0x180050746  mov     r8d, 208h; Size
0x18005074c  call    memset_0
0x180050751  xor     edx, edx; Val
0x180050753  lea     rcx, [rsp+310h+var_2E0]; void *
0x180050758  mov     r8d, 0A8h; Size
0x18005075e  call    memset_0
0x180050763  mov     ebx, 104h
0x180050768  mov     qword ptr [r14], 0
0x18005076f  mov     edx, ebx; uSize
0x180050771  mov     qword ptr [rsp+310h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x18005077a  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x18005077e  call    cs:__imp_GetSystemDirectoryW
0x180050784  test    eax, eax
0x180050786  jnz     short loc_1800507A6
0x180050788  call    cs:__imp_GetLastError
0x18005078e  mov     ebx, eax
0x180050790  test    eax, eax
0x180050792  jle     loc_1800509F9
0x180050798  movzx   ebx, ax
0x18005079b  or      ebx, 80070000h
0x1800507a1  jmp     loc_1800509F9
0x1800507a6  lea     r8, aFveapiDll; "\\FVEAPI.DLL"
0x1800507ad  mov     rdx, rbx; cchDest
0x1800507b0  lea     rcx, [rbp+210h+Buffer]; pszDest
0x1800507b4  call    StringCchCatW
0x1800507b9  mov     ebx, eax
0x1800507bb  test    eax, eax
0x1800507bd  js      loc_1800509F9
0x1800507c3  xor     r8d, r8d; dwFlags
0x1800507c6  lea     rcx, [rbp+210h+Buffer]; lpLibFileName
0x1800507ca  xor     edx, edx; hFile
0x1800507cc  call    cs:__imp_LoadLibraryExW
0x1800507d2  mov     rdi, rax
0x1800507d5  test    rax, rax
0x1800507d8  jz      short loc_180050788
0x1800507da  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x1800507e1  mov     rcx, rax; hModule
0x1800507e4  call    cs:__imp_GetProcAddress
0x1800507ea  mov     qword ptr [rsp+310h+var_2F0+8], rax
0x1800507ef  mov     rcx, rdi; hModule
0x1800507f2  test    rax, rax
0x1800507f5  jnz     loc_180050892
0x1800507fb  lea     rdx, aFvegetstatusba; "FveGetStatusBasicW"
0x180050802  call    cs:__imp_GetProcAddress
0x180050808  mov     qword ptr [rsp+310h+var_2C0+8], rax
0x18005080d  test    rax, rax
0x180050810  jz      loc_18005092D
0x180050816  lea     rdx, aFvesetfipsallo; "FveSetFipsAllowDisabled"
0x18005081d  mov     rcx, rdi; hModule
0x180050820  call    cs:__imp_GetProcAddress
0x180050826  mov     qword ptr [rsp+310h+var_2B0], rax
0x18005082b  test    rax, rax
0x18005082e  jz      loc_18005092D
0x180050834  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x18005083b  mov     rcx, rdi; hModule
0x18005083e  call    cs:__imp_GetProcAddress
0x180050844  test    rax, rax
0x180050847  jz      loc_18005092D
0x18005084d  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x180050854  mov     rcx, rdi; hModule
0x180050857  call    cs:__imp_GetProcAddress
0x18005085d  mov     qword ptr [rsp+310h+var_2B0+8], rax
0x180050862  test    rax, rax
0x180050865  jz      loc_18005092D
0x18005086b  lea     rdx, aFveenableauthe; "FveEnableAuthenticationW"
0x180050872  mov     rcx, rdi; hModule
0x180050875  call    cs:__imp_GetProcAddress
0x18005087b  mov     qword ptr [rsp+310h+var_2A0], rax
0x180050880  test    rax, rax
0x180050883  jz      loc_18005092D
0x180050889  mov     rax, [rbp+210h+var_240]
0x18005088d  jmp     loc_180050989
0x180050892  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x180050899  call    cs:__imp_GetProcAddress
0x18005089f  mov     qword ptr [rsp+310h+var_2E0], rax
0x1800508a4  test    rax, rax
0x1800508a7  jz      loc_18005092D
0x1800508ad  lea     rdx, aFvegetstatus; "FveGetStatus"
0x1800508b4  mov     rcx, rdi; hModule
0x1800508b7  call    cs:__imp_GetProcAddress
0x1800508bd  mov     qword ptr [rsp+310h+var_2C0], rax
0x1800508c2  test    rax, rax
0x1800508c5  jz      short loc_18005092D
0x1800508c7  lea     rdx, aFveaddauthmeth; "FveAddAuthMethodInformation"
0x1800508ce  mov     rcx, rdi; hModule
0x1800508d1  call    cs:__imp_GetProcAddress
0x1800508d7  mov     qword ptr [rbp+210h+var_290], rax
0x1800508db  test    rax, rax
0x1800508de  jz      short loc_18005092D
0x1800508e0  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x1800508e7  mov     rcx, rdi; hModule
0x1800508ea  call    cs:__imp_GetProcAddress
0x1800508f0  mov     qword ptr [rsp+310h+var_2A0+8], rax
0x1800508f5  test    rax, rax
0x1800508f8  jz      short loc_18005092D
0x1800508fa  lea     rdx, aFvedeleteauthm; "FveDeleteAuthMethod"
0x180050901  mov     rcx, rdi; hModule
0x180050904  call    cs:__imp_GetProcAddress
0x18005090a  mov     qword ptr [rbp+210h+var_290+8], rax
0x18005090e  test    rax, rax
0x180050911  jz      short loc_18005092D
0x180050913  lea     rdx, aFvecommitchang_0; "FveCommitChanges"
0x18005091a  mov     rcx, rdi; hModule
0x18005091d  call    cs:__imp_GetProcAddress
0x180050923  mov     qword ptr [rsp+310h+var_2E0+8], rax
0x180050928  test    rax, rax
0x18005092b  jnz     short loc_180050950
0x18005092d  call    cs:__imp_GetLastError
0x180050933  mov     ebx, eax
0x180050935  test    eax, eax
0x180050937  jle     short loc_180050942
0x180050939  movzx   ebx, ax
0x18005093c  or      ebx, 80070000h
0x180050942  mov     rcx, rdi; hLibModule
0x180050945  call    cs:__imp_FreeLibrary
0x18005094b  jmp     loc_1800509F9
0x180050950  lea     rdx, aFvecommitchang; "FveCommitChangesEx"
0x180050957  mov     rcx, rdi; hModule
0x18005095a  call    cs:__imp_GetProcAddress
0x180050960  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x180050967  mov     rcx, rdi; hModule
0x18005096a  mov     qword ptr [rsp+310h+var_2D0], rax
0x18005096f  call    cs:__imp_GetProcAddress
0x180050975  lea     rdx, aFvecontrol; "FveControl"
0x18005097c  mov     rcx, rdi; hModule
0x18005097f  mov     qword ptr [rbp+210h+var_280], rax
0x180050983  call    cs:__imp_GetProcAddress
0x180050989  movaps  xmm0, [rsp+310h+var_2F0]
0x18005098e  movaps  xmm1, [rsp+310h+var_2E0]
0x180050993  mov     [r14], rdi
0x180050996  movups  xmmword ptr [rsi], xmm0
0x180050999  movaps  xmm0, [rsp+310h+var_2D0]
0x18005099e  movups  xmmword ptr [rsi+10h], xmm1
0x1800509a2  movaps  xmm1, [rsp+310h+var_2C0]
0x1800509a7  movups  xmmword ptr [rsi+20h], xmm0
0x1800509ab  movaps  xmm0, [rsp+310h+var_2B0]
0x1800509b0  movups  xmmword ptr [rsi+30h], xmm1
0x1800509b4  movaps  xmm1, [rsp+310h+var_2A0]
0x1800509b9  movups  xmmword ptr [rsi+40h], xmm0
0x1800509bd  movaps  xmm0, [rbp+210h+var_290]
0x1800509c1  movups  xmmword ptr [rsi+50h], xmm1
0x1800509c5  movaps  xmm1, [rbp+210h+var_280]
0x1800509c9  movups  xmmword ptr [rsi+60h], xmm0
0x1800509cd  movaps  xmm0, [rbp+210h+var_270]
0x1800509d1  movups  xmmword ptr [rsi+70h], xmm1
0x1800509d5  movaps  xmm1, [rbp+210h+var_260]
0x1800509d9  movups  xmmword ptr [rsi+80h], xmm0
0x1800509e0  movaps  xmm0, [rbp+210h+var_250]
0x1800509e4  movups  xmmword ptr [rsi+90h], xmm1
0x1800509eb  movups  xmmword ptr [rsi+0A0h], xmm0
0x1800509f2  mov     [rsi+0B0h], rax
0x1800509f9  mov     eax, ebx
0x1800509fb  mov     rcx, [rbp+210h+var_20]
0x180050a02  xor     rcx, rsp; StackCookie
0x180050a05  call    __security_check_cookie
0x180050a0a  lea     r11, [rsp+310h+var_10]
0x180050a12  mov     rbx, [r11+30h]
0x180050a16  mov     rsi, [r11+38h]
0x180050a1a  mov     rsp, r11
0x180050a1d  pop     r14
0x180050a1f  pop     rdi
0x180050a20  pop     rbp
0x180050a21  retn
```
