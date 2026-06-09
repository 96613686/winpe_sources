# RunSetupCommandW

- ea: `0x18000bdb0`
- end: `0x18000bf6f`
- name: `RunSetupCommandW`
- size: `447`
- prototype: `HRESULT __stdcall(HWND hWnd, LPCWSTR szCmdName, LPCWSTR szInfSection, LPCWSTR szDir, LPCWSTR lpszTitle, HANDLE *phEXE, DWORD dwFlags, LPVOID pvReserved)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002ad4`
- `0x18000bcb0`

## callees

- `0x180003ce0`
- `0x180003e20`
- `0x1800045e8`
- `0x180004880`
- `0x1800080c8`
- `0x1800080f0`
- `0x180008644`
- `0x18000bdb0`
- `0x18000c574`

## import_xrefs

- `USER32!IsWindow` at `0x18000be25`
- `USER32!IsWindow` at `0x18000be25`
- `KERNEL32!GetLastError` at `0x18000bf2f`
- `KERNEL32!GetLastError` at `0x18000bf2f`

## string_xrefs

- `0x18000bdc1`: `RunSetupCommand:`
- `0x18000bf4c`: `RunSetupCommand: Cmd=%1 End hr=0x%2!x!\n`

## pseudocode

```c
HRESULT __stdcall RunSetupCommandW(
        HWND hWnd,
        LPCWSTR szCmdName,
        LPCWSTR szInfSection,
        LPCWSTR szDir,
        LPCWSTR lpszTitle,
        HANDLE *phEXE,
        DWORD dwFlags,
        LPVOID pvReserved)
{
  unsigned int v12; // ebx
  DWORD v13; // r8d
  int v14; // edx
  ULONG v15; // eax
  int v16; // r14d
  signed int LastError; // eax

  AdvWriteToLog(L"RunSetupCommand:");
  if ( !(unsigned int)SaveGlobalContext() )
  {
    v12 = -2147024882;
LABEL_25:
    AdvWriteToLog(L"RunSetupCommand: Cmd=%1 End hr=0x%2!x!\r\n", szCmdName, v12);
    return v12;
  }
  if ( szCmdName && szDir )
  {
    AdvWriteToLog(L" Cmd=%1\r\n", szCmdName);
    pszTitleString = lpszTitle;
    ::hWnd = hWnd;
    if ( !hWnd || IsWindow(hWnd) )
      v13 = dwFlags;
    else
      v13 = dwFlags | 4;
    word_1800257D2 = (v13 & 4) != 0;
    dword_1800257D4 = ((unsigned __int8)v13 >> 4) & 1;
    if ( (v13 & 1) != 0 )
    {
      v14 = ~(unsigned __int8)(v13 >> 2) & 2 | 0x80;
      if ( (v13 & 0x200) == 0 )
        v14 = ~(unsigned __int8)(v13 >> 2) & 2;
      v15 = v14 | 0x100;
      if ( (v13 & 0x400) == 0 )
        v15 = v14;
      v12 = CoreInstall(szCmdName, szInfSection, (unsigned __int16 *)szDir, 0, v15, 0);
    }
    else if ( (unsigned int)CheckOSVersion() )
    {
      v16 = InternalNeedRebootInit((const unsigned __int16 *)ctx);
      v12 = LaunchAndWait(szCmdName, szDir, phEXE, 0xFFFFFFFF, 0);
      if ( v12 )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
      }
      else if ( phEXE )
      {
        v12 = 262632;
      }
      else if ( InternalNeedReboot(v16, ctx) )
      {
        v12 = 3010;
      }
    }
    else
    {
      v12 = -2147023746;
    }
    RestoreGlobalContext();
    goto LABEL_25;
  }
  return -2147024809;
}

```

## disassembly

```asm
0x18000bdb0  push    rbx
0x18000bdb2  push    rbp
0x18000bdb3  push    rsi
0x18000bdb4  push    rdi
0x18000bdb5  push    r14
0x18000bdb7  sub     rsp, 30h
0x18000bdbb  mov     rbx, rcx
0x18000bdbe  mov     rbp, r9
0x18000bdc1  lea     rcx, aRunsetupcomman_3; "RunSetupCommand:"
0x18000bdc8  mov     rsi, r8
0x18000bdcb  mov     rdi, rdx
0x18000bdce  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000bdd3  call    ?SaveGlobalContext@@YAHXZ; SaveGlobalContext(void)
0x18000bdd8  test    eax, eax
0x18000bdda  jnz     short loc_18000BDE6
0x18000bddc  mov     ebx, 8007000Eh
0x18000bde1  jmp     loc_18000BF49
0x18000bde6  test    rdi, rdi
0x18000bde9  jz      loc_18000BF5F
0x18000bdef  test    rbp, rbp
0x18000bdf2  jz      loc_18000BF5F
0x18000bdf8  mov     rdx, rdi
0x18000bdfb  lea     rcx, aCmd1; " Cmd=%1\r\n"
0x18000be02  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000be07  mov     rax, [rsp+58h+lpszTitle]
0x18000be0f  mov     cs:pszTitleString, rax
0x18000be16  mov     cs:hWnd, rbx
0x18000be1d  test    rbx, rbx
0x18000be20  jz      short loc_18000BE3D
0x18000be22  mov     rcx, rbx; hWnd
0x18000be25  call    cs:__imp_IsWindow
0x18000be2b  test    eax, eax
0x18000be2d  jnz     short loc_18000BE3D
0x18000be2f  mov     r8d, [rsp+58h+dwFlags]
0x18000be37  or      r8d, 4
0x18000be3b  jmp     short loc_18000BE45
0x18000be3d  mov     r8d, [rsp+58h+dwFlags]
0x18000be45  mov     ecx, 1
0x18000be4a  test    r8b, 4
0x18000be4e  jz      short loc_18000BE59
0x18000be50  mov     cs:word_1800257D2, cx
0x18000be57  jmp     short loc_18000BE62
0x18000be59  xor     eax, eax
0x18000be5b  mov     cs:word_1800257D2, ax
0x18000be62  movzx   eax, r8b
0x18000be66  shr     eax, 4
0x18000be69  and     eax, ecx
0x18000be6b  mov     cs:dword_1800257D4, eax
0x18000be71  test    cl, r8b
0x18000be74  jz      short loc_18000BEC2
0x18000be76  mov     ecx, r8d
0x18000be79  mov     [rsp+58h+var_30], 0; unsigned __int16 *
0x18000be82  shr     ecx, 2
0x18000be85  not     ecx
0x18000be87  and     ecx, 2
0x18000be8a  mov     edx, ecx
0x18000be8c  bts     edx, 7
0x18000be90  bt      r8d, 9
0x18000be95  cmovnb  edx, ecx
0x18000be98  mov     rcx, rdi; unsigned __int16 *
0x18000be9b  mov     eax, edx
0x18000be9d  bts     eax, 8
0x18000bea1  bt      r8d, 0Ah
0x18000bea6  mov     r8, rbp; unsigned __int16 *
0x18000bea9  cmovnb  eax, edx
0x18000beac  xor     r9d, r9d; unsigned int
0x18000beaf  mov     rdx, rsi; unsigned __int16 *
0x18000beb2  mov     [rsp+58h+var_38], eax; ULONG
0x18000beb6  call    ?CoreInstall@@YAJPEBG00KK0@Z; CoreInstall(ushort const *,ushort const *,ushort const *,ulong,ulong,ushort const *)
0x18000bebb  mov     ebx, eax
0x18000bebd  jmp     loc_18000BF44
0x18000bec2  call    ?CheckOSVersion@@YAHXZ; CheckOSVersion(void)
0x18000bec7  test    eax, eax
0x18000bec9  jnz     short loc_18000BED2
0x18000becb  mov     ebx, 8007047Eh
0x18000bed0  jmp     short loc_18000BF44
0x18000bed2  movzx   ecx, cs:?ctx@@3UADVCONTEXTW@@A; unsigned __int16
0x18000bed9  call    ?InternalNeedRebootInit@@YAKG@Z; InternalNeedRebootInit(ushort)
0x18000bede  mov     rsi, [rsp+58h+phEXE]
0x18000bee6  or      r9d, 0FFFFFFFFh; unsigned int
0x18000beea  mov     r8, rsi; void **
0x18000beed  mov     [rsp+58h+var_38], 0; unsigned int
0x18000bef5  mov     rdx, rbp; lpCurrentDirectory
0x18000bef8  mov     rcx, rdi; unsigned __int16 *
0x18000befb  mov     r14d, eax
0x18000befe  call    ?LaunchAndWait@@YAJPEBG0PEAPEAXKK@Z; LaunchAndWait(ushort const *,ushort const *,void * *,ulong,ulong)
0x18000bf03  mov     ebx, eax
0x18000bf05  test    eax, eax
0x18000bf07  jnz     short loc_18000BF2F
0x18000bf09  test    rsi, rsi
0x18000bf0c  jz      short loc_18000BF15
0x18000bf0e  mov     ebx, 401E8h
0x18000bf13  jmp     short loc_18000BF44
0x18000bf15  movzx   edx, cs:?ctx@@3UADVCONTEXTW@@A; unsigned __int16
0x18000bf1c  mov     ecx, r14d; unsigned int
0x18000bf1f  call    ?InternalNeedReboot@@YAHKG@Z; InternalNeedReboot(ulong,ushort)
0x18000bf24  test    eax, eax
0x18000bf26  jz      short loc_18000BF44
0x18000bf28  mov     ebx, 0BC2h
0x18000bf2d  jmp     short loc_18000BF44
0x18000bf2f  call    cs:__imp_GetLastError
0x18000bf35  mov     ebx, eax
0x18000bf37  test    eax, eax
0x18000bf39  jle     short loc_18000BF44
0x18000bf3b  movzx   ebx, ax
0x18000bf3e  or      ebx, 80070000h
0x18000bf44  call    ?RestoreGlobalContext@@YAHXZ; RestoreGlobalContext(void)
0x18000bf49  mov     r8d, ebx
0x18000bf4c  lea     rcx, aRunsetupcomman_2; "RunSetupCommand: Cmd=%1 End hr=0x%2!x!"...
0x18000bf53  mov     rdx, rdi
0x18000bf56  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000bf5b  mov     eax, ebx
0x18000bf5d  jmp     short loc_18000BF64
0x18000bf5f  mov     eax, 80070057h
0x18000bf64  add     rsp, 30h
0x18000bf68  pop     r14
0x18000bf6a  pop     rdi
0x18000bf6b  pop     rsi
0x18000bf6c  pop     rbp
0x18000bf6d  pop     rbx
0x18000bf6e  retn
```
