# FvepLoadFveAPI

- ea: `0x1800643c4`
- end: `0x1800646ce`
- name: `FvepLoadFveAPI`
- size: `778`
- prototype: `__int64 __fastcall(HMODULE *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800636d0`
- `0x180063a38`

## callees

- `0x1800643c4`
- `0x1800646d4`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180064478`
- `KERNEL32!LoadLibraryExW` at `0x180064478`
- `KERNEL32!FreeLibrary` at `0x1800645f1`
- `KERNEL32!FreeLibrary` at `0x1800645f1`
- `KERNEL32!GetProcAddress` at `0x180064490`
- `KERNEL32!GetProcAddress` at `0x1800644ae`
- `KERNEL32!GetProcAddress` at `0x1800644cc`
- `KERNEL32!GetProcAddress` at `0x1800644ea`
- `KERNEL32!GetProcAddress` at `0x180064503`
- `KERNEL32!GetProcAddress` at `0x180064521`
- `KERNEL32!GetProcAddress` at `0x180064545`
- `KERNEL32!GetProcAddress` at `0x180064563`
- `KERNEL32!GetProcAddress` at `0x18006457d`
- `KERNEL32!GetProcAddress` at `0x180064596`
- `KERNEL32!GetProcAddress` at `0x1800645b0`
- `KERNEL32!GetProcAddress` at `0x1800645c9`
- `KERNEL32!GetProcAddress` at `0x180064606`
- `KERNEL32!GetProcAddress` at `0x18006461b`
- `KERNEL32!GetProcAddress` at `0x18006462f`
- `KERNEL32!GetProcAddress` at `0x180064490`
- `KERNEL32!GetProcAddress` at `0x1800644ae`
- `KERNEL32!GetProcAddress` at `0x1800644cc`
- `KERNEL32!GetProcAddress` at `0x1800644ea`
- `KERNEL32!GetProcAddress` at `0x180064503`
- `KERNEL32!GetProcAddress` at `0x180064521`
- `KERNEL32!GetProcAddress` at `0x180064545`
- `KERNEL32!GetProcAddress` at `0x180064563`
- `KERNEL32!GetProcAddress` at `0x18006457d`
- `KERNEL32!GetProcAddress` at `0x180064596`
- `KERNEL32!GetProcAddress` at `0x1800645b0`
- `KERNEL32!GetProcAddress` at `0x1800645c9`
- `KERNEL32!GetProcAddress` at `0x180064606`
- `KERNEL32!GetProcAddress` at `0x18006461b`
- `KERNEL32!GetProcAddress` at `0x18006462f`
- `KERNEL32!GetLastError` at `0x18006443e`
- `KERNEL32!GetLastError` at `0x1800645d9`
- `KERNEL32!GetLastError` at `0x18006443e`
- `KERNEL32!GetLastError` at `0x1800645d9`
- `KERNEL32!GetSystemDirectoryW` at `0x180064434`
- `KERNEL32!GetSystemDirectoryW` at `0x180064434`

## string_xrefs

- `0x180064486`: `FveOpenVolumeW`
- `0x1800645a6`: `FveDeleteAuthMethod`
- `0x1800645fc`: `FveCommitChangesEx`
- `0x1800645bf`: `FveCommitChanges`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FvepLoadFveAPI(HMODULE *a1, __int64 a2)
{
  size_t v4; // rdx
  const wchar_t *v5; // r8
  signed int v6; // eax
  unsigned int v7; // ebx
  HMODULE Library; // rax
  HMODULE v9; // rdi
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v23; // [rsp+20h] [rbp-E0h]
  __int128 v24; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v25; // [rsp+40h] [rbp-C0h]
  __int128 v26; // [rsp+50h] [rbp-B0h]
  __int128 v27; // [rsp+60h] [rbp-A0h]
  __int128 v28; // [rsp+70h] [rbp-90h]
  __int128 v29; // [rsp+80h] [rbp-80h]
  __int128 v30; // [rsp+90h] [rbp-70h]
  __int128 v31; // [rsp+A0h] [rbp-60h]
  __int128 v32; // [rsp+B0h] [rbp-50h]
  __int128 v33; // [rsp+C0h] [rbp-40h]
  INT_PTR (__stdcall *v34)(); // [rsp+D0h] [rbp-30h]
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(&v24, 0, 0xA8u);
  *a1 = 0;
  *(_QWORD *)&v23 = -1;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    goto LABEL_2;
  v7 = StringCchCatW(Buffer, v4, v5);
  if ( (v7 & 0x80000000) != 0 )
    return v7;
  Library = LoadLibraryExW(Buffer, 0, 0);
  v9 = Library;
  if ( Library )
  {
    *((_QWORD *)&v23 + 1) = GetProcAddress(Library, "FveOpenVolumeW");
    if ( *((_QWORD *)&v23 + 1) )
    {
      *(_QWORD *)&v24 = GetProcAddress(v9, "FveCloseVolume");
      if ( (_QWORD)v24 )
      {
        *(_QWORD *)&v26 = GetProcAddress(v9, "FveGetStatus");
        if ( (_QWORD)v26 )
        {
          *(_QWORD *)&v29 = GetProcAddress(v9, "FveAddAuthMethodInformation");
          if ( (_QWORD)v29 )
          {
            *((_QWORD *)&v28 + 1) = GetProcAddress(v9, "FveGetAuthMethodInformation");
            if ( *((_QWORD *)&v28 + 1) )
            {
              *((_QWORD *)&v29 + 1) = GetProcAddress(v9, "FveDeleteAuthMethod");
              if ( *((_QWORD *)&v29 + 1) )
              {
                *((_QWORD *)&v24 + 1) = GetProcAddress(v9, "FveCommitChanges");
                if ( *((_QWORD *)&v24 + 1) )
                {
                  *(_QWORD *)&v25 = GetProcAddress(v9, "FveCommitChangesEx");
                  *(_QWORD *)&v30 = GetProcAddress(v9, "FveGetSecureBootBindingState");
                  ProcAddress = GetProcAddress(v9, "FveControl");
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
      *((_QWORD *)&v26 + 1) = GetProcAddress(v9, "FveGetStatusBasicW");
      if ( *((_QWORD *)&v26 + 1) )
      {
        *(_QWORD *)&v27 = GetProcAddress(v9, "FveSetFipsAllowDisabled");
        if ( (_QWORD)v27 )
        {
          if ( GetProcAddress(v9, "FveDisableAuthenticationW") )
          {
            *((_QWORD *)&v27 + 1) = GetProcAddress(v9, "FveDisableAuthenticationW");
            if ( *((_QWORD *)&v27 + 1) )
            {
              *(_QWORD *)&v28 = GetProcAddress(v9, "FveEnableAuthenticationW");
              if ( (_QWORD)v28 )
              {
                ProcAddress = v34;
LABEL_23:
                v12 = v24;
                *a1 = v9;
                *(_OWORD *)a2 = v23;
                v13 = v25;
                *(_OWORD *)(a2 + 16) = v12;
                v14 = v26;
                *(_OWORD *)(a2 + 32) = v13;
                v15 = v27;
                *(_OWORD *)(a2 + 48) = v14;
                v16 = v28;
                *(_OWORD *)(a2 + 64) = v15;
                v17 = v29;
                *(_OWORD *)(a2 + 80) = v16;
                v18 = v30;
                *(_OWORD *)(a2 + 96) = v17;
                v19 = v31;
                *(_OWORD *)(a2 + 112) = v18;
                v20 = v32;
                *(_OWORD *)(a2 + 128) = v19;
                v21 = v33;
                *(_OWORD *)(a2 + 144) = v20;
                *(_OWORD *)(a2 + 160) = v21;
                *(_QWORD *)(a2 + 176) = ProcAddress;
                return v7;
              }
            }
          }
        }
      }
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    FreeLibrary(v9);
  }
  else
  {
LABEL_2:
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
  }
  return v7;
}

```

## disassembly

```asm
0x1800643c4  mov     [rsp-8+arg_10], rbx
0x1800643c9  mov     [rsp-8+arg_18], rsi
0x1800643ce  push    rbp
0x1800643cf  push    rdi
0x1800643d0  push    r14
0x1800643d2  lea     rbp, [rsp-200h]
0x1800643da  sub     rsp, 300h
0x1800643e1  mov     rax, cs:__security_cookie
0x1800643e8  xor     rax, rsp
0x1800643eb  mov     [rbp+210h+var_20], rax
0x1800643f2  mov     rsi, rdx
0x1800643f5  mov     r14, rcx
0x1800643f8  xor     edx, edx; Val
0x1800643fa  lea     rcx, [rbp+210h+Buffer]; void *
0x1800643fe  mov     r8d, 208h; Size
0x180064404  call    memset_0
0x180064409  xor     edx, edx; Val
0x18006440b  lea     rcx, [rsp+310h+var_2E0]; void *
0x180064410  mov     r8d, 0A8h; Size
0x180064416  call    memset_0
0x18006441b  mov     edx, 104h; uSize
0x180064420  mov     qword ptr [r14], 0
0x180064427  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x18006442b  mov     qword ptr [rsp+310h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x180064434  call    cs:__imp_GetSystemDirectoryW
0x18006443a  test    eax, eax
0x18006443c  jnz     short loc_18006445C
0x18006443e  call    cs:__imp_GetLastError
0x180064444  mov     ebx, eax
0x180064446  test    eax, eax
0x180064448  jle     loc_1800646A5
0x18006444e  movzx   ebx, ax
0x180064451  or      ebx, 80070000h
0x180064457  jmp     loc_1800646A5
0x18006445c  lea     rcx, [rbp+210h+Buffer]; pszDest
0x180064460  call    StringCchCatW
0x180064465  mov     ebx, eax
0x180064467  test    eax, eax
0x180064469  js      loc_1800646A5
0x18006446f  xor     r8d, r8d; dwFlags
0x180064472  lea     rcx, [rbp+210h+Buffer]; lpLibFileName
0x180064476  xor     edx, edx; hFile
0x180064478  call    cs:__imp_LoadLibraryExW
0x18006447e  mov     rdi, rax
0x180064481  test    rax, rax
0x180064484  jz      short loc_18006443E
0x180064486  lea     rdx, aFveopenvolumew_0; "FveOpenVolumeW"
0x18006448d  mov     rcx, rax; hModule
0x180064490  call    cs:__imp_GetProcAddress
0x180064496  mov     qword ptr [rsp+310h+var_2F0+8], rax
0x18006449b  mov     rcx, rdi; hModule
0x18006449e  test    rax, rax
0x1800644a1  jnz     loc_18006453E
0x1800644a7  lea     rdx, aFvegetstatusba; "FveGetStatusBasicW"
0x1800644ae  call    cs:__imp_GetProcAddress
0x1800644b4  mov     qword ptr [rsp+310h+var_2C0+8], rax
0x1800644b9  test    rax, rax
0x1800644bc  jz      loc_1800645D9
0x1800644c2  lea     rdx, aFvesetfipsallo; "FveSetFipsAllowDisabled"
0x1800644c9  mov     rcx, rdi; hModule
0x1800644cc  call    cs:__imp_GetProcAddress
0x1800644d2  mov     qword ptr [rsp+310h+var_2B0], rax
0x1800644d7  test    rax, rax
0x1800644da  jz      loc_1800645D9
0x1800644e0  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x1800644e7  mov     rcx, rdi; hModule
0x1800644ea  call    cs:__imp_GetProcAddress
0x1800644f0  test    rax, rax
0x1800644f3  jz      loc_1800645D9
0x1800644f9  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x180064500  mov     rcx, rdi; hModule
0x180064503  call    cs:__imp_GetProcAddress
0x180064509  mov     qword ptr [rsp+310h+var_2B0+8], rax
0x18006450e  test    rax, rax
0x180064511  jz      loc_1800645D9
0x180064517  lea     rdx, aFveenableauthe; "FveEnableAuthenticationW"
0x18006451e  mov     rcx, rdi; hModule
0x180064521  call    cs:__imp_GetProcAddress
0x180064527  mov     qword ptr [rsp+310h+var_2A0], rax
0x18006452c  test    rax, rax
0x18006452f  jz      loc_1800645D9
0x180064535  mov     rax, [rbp+210h+var_240]
0x180064539  jmp     loc_180064635
0x18006453e  lea     rdx, aFveclosevolume_0; "FveCloseVolume"
0x180064545  call    cs:__imp_GetProcAddress
0x18006454b  mov     qword ptr [rsp+310h+var_2E0], rax
0x180064550  test    rax, rax
0x180064553  jz      loc_1800645D9
0x180064559  lea     rdx, aFvegetstatus_0; "FveGetStatus"
0x180064560  mov     rcx, rdi; hModule
0x180064563  call    cs:__imp_GetProcAddress
0x180064569  mov     qword ptr [rsp+310h+var_2C0], rax
0x18006456e  test    rax, rax
0x180064571  jz      short loc_1800645D9
0x180064573  lea     rdx, aFveaddauthmeth; "FveAddAuthMethodInformation"
0x18006457a  mov     rcx, rdi; hModule
0x18006457d  call    cs:__imp_GetProcAddress
0x180064583  mov     qword ptr [rbp+210h+var_290], rax
0x180064587  test    rax, rax
0x18006458a  jz      short loc_1800645D9
0x18006458c  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x180064593  mov     rcx, rdi; hModule
0x180064596  call    cs:__imp_GetProcAddress
0x18006459c  mov     qword ptr [rsp+310h+var_2A0+8], rax
0x1800645a1  test    rax, rax
0x1800645a4  jz      short loc_1800645D9
0x1800645a6  lea     rdx, aFvedeleteauthm; "FveDeleteAuthMethod"
0x1800645ad  mov     rcx, rdi; hModule
0x1800645b0  call    cs:__imp_GetProcAddress
0x1800645b6  mov     qword ptr [rbp+210h+var_290+8], rax
0x1800645ba  test    rax, rax
0x1800645bd  jz      short loc_1800645D9
0x1800645bf  lea     rdx, aFvecommitchang_0; "FveCommitChanges"
0x1800645c6  mov     rcx, rdi; hModule
0x1800645c9  call    cs:__imp_GetProcAddress
0x1800645cf  mov     qword ptr [rsp+310h+var_2E0+8], rax
0x1800645d4  test    rax, rax
0x1800645d7  jnz     short loc_1800645FC
0x1800645d9  call    cs:__imp_GetLastError
0x1800645df  mov     ebx, eax
0x1800645e1  test    eax, eax
0x1800645e3  jle     short loc_1800645EE
0x1800645e5  movzx   ebx, ax
0x1800645e8  or      ebx, 80070000h
0x1800645ee  mov     rcx, rdi; hLibModule
0x1800645f1  call    cs:__imp_FreeLibrary
0x1800645f7  jmp     loc_1800646A5
0x1800645fc  lea     rdx, aFvecommitchang; "FveCommitChangesEx"
0x180064603  mov     rcx, rdi; hModule
0x180064606  call    cs:__imp_GetProcAddress
0x18006460c  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x180064613  mov     rcx, rdi; hModule
0x180064616  mov     qword ptr [rsp+310h+var_2D0], rax
0x18006461b  call    cs:__imp_GetProcAddress
0x180064621  lea     rdx, aFvecontrol; "FveControl"
0x180064628  mov     rcx, rdi; hModule
0x18006462b  mov     qword ptr [rbp+210h+var_280], rax
0x18006462f  call    cs:__imp_GetProcAddress
0x180064635  movaps  xmm0, [rsp+310h+var_2F0]
0x18006463a  movaps  xmm1, [rsp+310h+var_2E0]
0x18006463f  mov     [r14], rdi
0x180064642  movups  xmmword ptr [rsi], xmm0
0x180064645  movaps  xmm0, [rsp+310h+var_2D0]
0x18006464a  movups  xmmword ptr [rsi+10h], xmm1
0x18006464e  movaps  xmm1, [rsp+310h+var_2C0]
0x180064653  movups  xmmword ptr [rsi+20h], xmm0
0x180064657  movaps  xmm0, [rsp+310h+var_2B0]
0x18006465c  movups  xmmword ptr [rsi+30h], xmm1
0x180064660  movaps  xmm1, [rsp+310h+var_2A0]
0x180064665  movups  xmmword ptr [rsi+40h], xmm0
0x180064669  movaps  xmm0, [rbp+210h+var_290]
0x18006466d  movups  xmmword ptr [rsi+50h], xmm1
0x180064671  movaps  xmm1, [rbp+210h+var_280]
0x180064675  movups  xmmword ptr [rsi+60h], xmm0
0x180064679  movaps  xmm0, [rbp+210h+var_270]
0x18006467d  movups  xmmword ptr [rsi+70h], xmm1
0x180064681  movaps  xmm1, [rbp+210h+var_260]
0x180064685  movups  xmmword ptr [rsi+80h], xmm0
0x18006468c  movaps  xmm0, [rbp+210h+var_250]
0x180064690  movups  xmmword ptr [rsi+90h], xmm1
0x180064697  movups  xmmword ptr [rsi+0A0h], xmm0
0x18006469e  mov     [rsi+0B0h], rax
0x1800646a5  mov     eax, ebx
0x1800646a7  mov     rcx, [rbp+210h+var_20]
0x1800646ae  xor     rcx, rsp; StackCookie
0x1800646b1  call    __security_check_cookie
0x1800646b6  lea     r11, [rsp+310h+var_10]
0x1800646be  mov     rbx, [r11+30h]
0x1800646c2  mov     rsi, [r11+38h]
0x1800646c6  mov     rsp, r11
0x1800646c9  pop     r14
0x1800646cb  pop     rdi
0x1800646cc  pop     rbp
0x1800646cd  retn
```
