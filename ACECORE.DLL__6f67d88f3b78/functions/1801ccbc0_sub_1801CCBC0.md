# sub_1801CCBC0

- ea: `0x1801ccbc0`
- end: `0x1801cceed`
- name: `sub_1801CCBC0`
- size: `813`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180073ccc`
- `0x1801ccbc0`
- `0x1801ccef0`
- `0x1801ccfac`
- `0x1801d4f70`
- `0x1801d6c50`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1801ccca4`
- `KERNEL32!GetModuleHandleW` at `0x1801cccb6`
- `KERNEL32!GetModuleHandleW` at `0x1801ccdcb`
- `KERNEL32!GetModuleHandleW` at `0x1801ccddd`
- `KERNEL32!GetModuleHandleW` at `0x1801ccca4`
- `KERNEL32!GetModuleHandleW` at `0x1801cccb6`
- `KERNEL32!GetModuleHandleW` at `0x1801ccdcb`
- `KERNEL32!GetModuleHandleW` at `0x1801ccddd`
- `KERNEL32!LoadLibraryExA` at `0x1801ccc67`
- `KERNEL32!LoadLibraryExA` at `0x1801ccc67`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x1801ccd91`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x1801ccede`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x1801ccd91`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x1801ccede`
- `Mso20Win32Client!Mso20Win32Client_16175` at `0x1801ccd12`
- `Mso20Win32Client!Mso20Win32Client_16175` at `0x1801cce57`
- `Mso20Win32Client!Mso20Win32Client_16175` at `0x1801ccd12`
- `Mso20Win32Client!Mso20Win32Client_16175` at `0x1801cce57`
- `Mso20Win32Client!Mso20Win32Client_46386` at `0x1801ccd5f`
- `Mso20Win32Client!Mso20Win32Client_46386` at `0x1801cceac`
- `Mso20Win32Client!Mso20Win32Client_46386` at `0x1801ccd5f`
- `Mso20Win32Client!Mso20Win32Client_46386` at `0x1801cceac`

## string_xrefs

- `0x1801cccaf`: `mso20win32server.dll`
- `0x1801ccdd6`: `mso20win32server.dll`
- `0x1801ccc9d`: `mso20win32client.dll`
- `0x1801ccdc4`: `mso20win32client.dll`
- `0x1801ccce6`: `DllName`
- `0x1801cce0d`: `DllName`

## pseudocode

```c
HMODULE __fastcall sub_1801CCBC0(int a1, __int64 a2)
{
  unsigned int v3; // ebx
  HMODULE Library; // r14
  const char **v5; // rdi
  __int64 (__fastcall ***v6)(); // rax
  const char *v7; // r8
  _QWORD *v9; // rax
  const char *v10; // r8
  __int64 v11; // [rsp+30h] [rbp-59h] BYREF
  __int64 v12; // [rsp+38h] [rbp-51h] BYREF
  __int64 (__fastcall **v13)(); // [rsp+40h] [rbp-49h] BYREF
  __int64 *v14; // [rsp+48h] [rbp-41h]
  __int64 *v15; // [rsp+50h] [rbp-39h]
  __int64 (__fastcall **v16)(); // [rsp+58h] [rbp-31h] BYREF
  __int64 *v17; // [rsp+60h] [rbp-29h]
  __int64 (__fastcall ***v18)(); // [rsp+68h] [rbp-21h]
  __int16 v19; // [rsp+70h] [rbp-19h]
  _QWORD Src[3]; // [rsp+78h] [rbp-11h] BYREF
  __int16 v21; // [rsp+90h] [rbp+7h]
  _BYTE v22[32]; // [rsp+98h] [rbp+Fh] BYREF

  if ( a1 != 3 )
    return 0;
  ++dword_18025ECA0;
  v3 = 1;
  while ( 1 )
  {
    if ( qword_18025EC98 )
      qword_18025EC98(v3, 50);
    if ( off_1802255A0 )
    {
      Library = (HMODULE)off_1802255A0();
      v5 = (const char **)(a2 + 24);
      if ( Library )
        break;
    }
    v5 = (const char **)(a2 + 24);
    if ( !**(_BYTE **)(a2 + 24) )
      __fastfail(5u);
    Library = LoadLibraryExA(*(LPCSTR *)(a2 + 24), 0, 0x1000u);
    if ( Library )
      break;
    v11 = 10LL * v3;
    sub_1801CCEF0(&v11);
    if ( ++v3 > 0x32 )
    {
      if ( GetModuleHandleW(L"mso20win32client.dll") || GetModuleHandleW(L"mso20win32server.dll") )
      {
        v6 = (__int64 (__fastcall ***)())sub_1801CCFAC(Src);
        if ( (unsigned __int64)v6[3] > 7 )
          v6 = (__int64 (__fastcall ***)())*v6;
        v16 = off_1801E2038;
        v17 = (__int64 *)L"DllName";
        v18 = v6;
        v19 = 0;
        if ( (unsigned __int8)Mso20Win32Client_16175(50685657, 51, 10) )
        {
          v13 = off_1801E2060;
          v14 = &v11;
          v15 = &v12;
          Mso20Win32Client_46386(50685657, 51, 10, 0, L"DelayloadRetryError", &v13, &v16, v12);
        }
        sub_180073CCC(Src);
      }
      ++dword_18025ECA8;
      v7 = (const char *)&qword_1801E5A80;
      if ( *v5 )
        v7 = *v5;
      strncpy_s(byte_18025ED10, 0x64u, v7, 0xFFFFFFFFFFFFFFFFuLL);
      return 0;
    }
  }
  if ( GetModuleHandleW(L"mso20win32client.dll") || GetModuleHandleW(L"mso20win32server.dll") )
  {
    v9 = (_QWORD *)sub_1801CCFAC(v22);
    if ( v9[3] > 7u )
      v9 = (_QWORD *)*v9;
    Src[0] = off_1801E2038;
    Src[1] = L"DllName";
    Src[2] = v9;
    v21 = 0;
    v13 = off_1801E2080;
    v14 = (__int64 *)L"NumRetries";
    LODWORD(v15) = v3;
    WORD2(v15) = 0;
    if ( (unsigned __int8)Mso20Win32Client_16175(50685656, 51, 50) )
    {
      v16 = off_1801E2060;
      v17 = &v11;
      v18 = &v13;
      Mso20Win32Client_46386(50685656, 51, 50, 0, L"DelayloadRetry", &v16, &v13, Src);
    }
    sub_180073CCC(v22);
  }
  ++dword_18025ECA4;
  v10 = (const char *)&qword_1801E5A80;
  if ( *v5 )
    v10 = *v5;
  strncpy_s(byte_18025ECAC, 0x64u, v10, 0xFFFFFFFFFFFFFFFFuLL);
  return Library;
}

```

## disassembly

```asm
0x1801ccbc0  mov     [rsp-8+arg_0], rbx
0x1801ccbc5  mov     [rsp-8+arg_10], rsi
0x1801ccbca  push    rbp
0x1801ccbcb  push    rdi
0x1801ccbcc  push    r12
0x1801ccbce  push    r14
0x1801ccbd0  push    r15
0x1801ccbd2  lea     rbp, [rsp-37h]
0x1801ccbd7  sub     rsp, 0C0h
0x1801ccbde  mov     rax, cs:__security_cookie
0x1801ccbe5  xor     rax, rsp
0x1801ccbe8  mov     [rbp+57h+var_28], rax
0x1801ccbec  mov     rsi, rdx
0x1801ccbef  cmp     ecx, 3
0x1801ccbf2  jnz     loc_1801CCD97
0x1801ccbf8  inc     cs:dword_18025ECA0
0x1801ccbfe  lea     ebx, [rcx-2]
0x1801ccc01  xor     r12d, r12d
0x1801ccc04  mov     rax, cs:qword_18025EC98
0x1801ccc0b  test    rax, rax
0x1801ccc0e  jz      short loc_1801CCC1F
0x1801ccc10  xor     r8d, r8d
0x1801ccc13  lea     edx, [r8+32h]
0x1801ccc17  mov     ecx, ebx
0x1801ccc19  call    cs:__guard_dispatch_icall_fptr
0x1801ccc1f  mov     rax, cs:off_1802255A0
0x1801ccc26  test    rax, rax
0x1801ccc29  jz      short loc_1801CCC49
0x1801ccc2b  mov     rdx, rsi
0x1801ccc2e  mov     ecx, 1
0x1801ccc33  call    cs:__guard_dispatch_icall_fptr
0x1801ccc39  mov     r14, rax
0x1801ccc3c  lea     rdi, [rsi+18h]
0x1801ccc40  test    rax, rax
0x1801ccc43  jnz     loc_1801CCDC1
0x1801ccc49  lea     rdi, [rsi+18h]
0x1801ccc4d  mov     rax, [rdi]
0x1801ccc50  cmp     [rax], r12b
0x1801ccc53  jnz     short loc_1801CCC5C
0x1801ccc55  mov     ecx, 5
0x1801ccc5a  int     29h; Win8: RtlFailFast(ecx)
0x1801ccc5c  xor     edx, edx; hFile
0x1801ccc5e  mov     r8d, 1000h; dwFlags
0x1801ccc64  mov     rcx, rax; lpLibFileName
0x1801ccc67  call    cs:LoadLibraryExA
0x1801ccc6d  mov     r14, rax
0x1801ccc70  test    rax, rax
0x1801ccc73  jnz     loc_1801CCDC1
0x1801ccc79  mov     eax, ebx
0x1801ccc7b  lea     rcx, [rax+rax*4]
0x1801ccc7f  add     rcx, rcx
0x1801ccc82  mov     [rbp+57h+var_B0], rcx
0x1801ccc86  lea     rcx, [rbp+57h+var_B0]
0x1801ccc8a  call    sub_1801CCEF0
0x1801ccc8f  inc     ebx
0x1801ccc91  cmp     ebx, 32h ; '2'
0x1801ccc94  jbe     loc_1801CCC04
0x1801ccc9a  mov     rbx, [rdi]
0x1801ccc9d  lea     rcx, aMso20win32clie_1; "mso20win32client.dll"
0x1801ccca4  call    cs:GetModuleHandleW
0x1801cccaa  test    rax, rax
0x1801cccad  jnz     short loc_1801CCCC5
0x1801cccaf  lea     rcx, aMso20win32serv; "mso20win32server.dll"
0x1801cccb6  call    cs:GetModuleHandleW
0x1801cccbc  test    rax, rax
0x1801cccbf  jz      loc_1801CCD6E
0x1801cccc5  mov     rdx, rbx
0x1801cccc8  lea     rcx, [rbp+57h+Src]; Src
0x1801ccccc  call    sub_1801CCFAC
0x1801cccd1  cmp     qword ptr [rax+18h], 7
0x1801cccd6  jbe     short loc_1801CCCDB
0x1801cccd8  mov     rax, [rax]
0x1801cccdb  lea     rcx, off_1801E2038
0x1801ccce2  mov     [rbp+57h+var_88], rcx
0x1801ccce6  lea     rcx, aDllname; "DllName"
0x1801ccced  mov     [rbp+57h+var_80], rcx
0x1801cccf1  mov     [rbp+57h+var_78], rax
0x1801cccf5  mov     [rbp+57h+var_70], r12w
0x1801cccfa  xor     r9d, r9d
0x1801cccfd  lea     esi, [r9+0Ah]
0x1801ccd01  mov     r8d, esi
0x1801ccd04  lea     ebx, [rsi+29h]
0x1801ccd07  mov     edx, ebx
0x1801ccd09  mov     r14d, 30566D9h
0x1801ccd0f  mov     ecx, r14d
0x1801ccd12  call    cs:Mso20Win32Client_16175
0x1801ccd18  test    al, al
0x1801ccd1a  jz      short loc_1801CCD65
0x1801ccd1c  lea     rax, [rbp+57h+var_88]
0x1801ccd20  mov     [rbp+57h+var_B0], rax
0x1801ccd24  lea     rax, off_1801E2060
0x1801ccd2b  mov     [rbp+57h+var_A0], rax
0x1801ccd2f  lea     rax, [rbp+57h+var_B0]
0x1801ccd33  mov     [rbp+57h+var_98], rax
0x1801ccd37  lea     rax, [rbp+57h+var_A8]
0x1801ccd3b  mov     [rbp+57h+var_90], rax
0x1801ccd3f  xor     r9d, r9d
0x1801ccd42  lea     rax, [rbp+57h+var_A0]
0x1801ccd46  mov     [rsp+0E0h+var_B8], rax
0x1801ccd4b  lea     rax, aDelayloadretry; "DelayloadRetryError"
0x1801ccd52  mov     [rsp+0E0h+var_C0], rax
0x1801ccd57  mov     r8d, esi
0x1801ccd5a  mov     edx, ebx
0x1801ccd5c  mov     ecx, r14d
0x1801ccd5f  call    cs:Mso20Win32Client_46386
0x1801ccd65  lea     rcx, [rbp+57h+Src]
0x1801ccd69  call    sub_180073CCC
0x1801ccd6e  inc     cs:dword_18025ECA8
0x1801ccd74  lea     r8, qword_1801E5A80
0x1801ccd7b  cmp     [rdi], r12
0x1801ccd7e  cmovnz  r8, [rdi]; Source
0x1801ccd82  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1801ccd86  lea     edx, [r9+65h]; SizeInBytes
0x1801ccd8a  lea     rcx, byte_18025ED10; Destination
0x1801ccd91  call    cs:strncpy_s
0x1801ccd97  xor     eax, eax
0x1801ccd99  mov     rcx, [rbp+57h+var_28]
0x1801ccd9d  xor     rcx, rsp; StackCookie
0x1801ccda0  call    __security_check_cookie
0x1801ccda5  lea     r11, [rsp+0E0h+var_20]
0x1801ccdad  mov     rbx, [r11+30h]
0x1801ccdb1  mov     rsi, [r11+40h]
0x1801ccdb5  mov     rsp, r11
0x1801ccdb8  pop     r15
0x1801ccdba  pop     r14
0x1801ccdbc  pop     r12
0x1801ccdbe  pop     rdi
0x1801ccdbf  pop     rbp
0x1801ccdc0  retn
0x1801ccdc1  mov     rsi, [rdi]
0x1801ccdc4  lea     rcx, aMso20win32clie_1; "mso20win32client.dll"
0x1801ccdcb  call    cs:GetModuleHandleW
0x1801ccdd1  test    rax, rax
0x1801ccdd4  jnz     short loc_1801CCDEC
0x1801ccdd6  lea     rcx, aMso20win32serv; "mso20win32server.dll"
0x1801ccddd  call    cs:GetModuleHandleW
0x1801ccde3  test    rax, rax
0x1801ccde6  jz      loc_1801CCEBB
0x1801ccdec  mov     rdx, rsi
0x1801ccdef  lea     rcx, [rbp+57h+var_48]; Src
0x1801ccdf3  call    sub_1801CCFAC
0x1801ccdf8  cmp     qword ptr [rax+18h], 7
0x1801ccdfd  jbe     short loc_1801CCE02
0x1801ccdff  mov     rax, [rax]
0x1801cce02  lea     rcx, off_1801E2038
0x1801cce09  mov     [rbp+57h+Src], rcx
0x1801cce0d  lea     rcx, aDllname; "DllName"
0x1801cce14  mov     [rbp+57h+var_60], rcx
0x1801cce18  mov     [rbp+57h+var_58], rax
0x1801cce1c  mov     [rbp+57h+var_50], r12w
0x1801cce21  lea     rax, off_1801E2080
0x1801cce28  mov     [rbp+57h+var_A0], rax
0x1801cce2c  lea     rax, aNumretries; "NumRetries"
0x1801cce33  mov     [rbp+57h+var_98], rax
0x1801cce37  mov     dword ptr [rbp+57h+var_90], ebx
0x1801cce3a  mov     word ptr [rbp+57h+var_90+4], r12w
0x1801cce3f  xor     r9d, r9d
0x1801cce42  lea     esi, [r9+32h]
0x1801cce46  mov     r8d, esi
0x1801cce49  lea     ebx, [rsi+1]
0x1801cce4c  mov     edx, ebx
0x1801cce4e  mov     r15d, 30566D8h
0x1801cce54  mov     ecx, r15d
0x1801cce57  call    cs:Mso20Win32Client_16175
0x1801cce5d  test    al, al
0x1801cce5f  jz      short loc_1801CCEB2
0x1801cce61  lea     rax, [rbp+57h+var_A0]
0x1801cce65  mov     [rbp+57h+var_B0], rax
0x1801cce69  lea     rax, [rbp+57h+Src]
0x1801cce6d  mov     [rbp+57h+var_A8], rax
0x1801cce71  lea     rax, off_1801E2060
0x1801cce78  mov     [rbp+57h+var_88], rax
0x1801cce7c  lea     rax, [rbp+57h+var_B0]
0x1801cce80  mov     [rbp+57h+var_80], rax
0x1801cce84  lea     rax, [rbp+57h+var_A0]
0x1801cce88  mov     [rbp+57h+var_78], rax
0x1801cce8c  xor     r9d, r9d
0x1801cce8f  lea     rax, [rbp+57h+var_88]
0x1801cce93  mov     [rsp+0E0h+var_B8], rax
0x1801cce98  lea     rax, aDelayloadretry_0; "DelayloadRetry"
0x1801cce9f  mov     [rsp+0E0h+var_C0], rax
0x1801ccea4  mov     r8d, esi
0x1801ccea7  mov     edx, ebx
0x1801ccea9  mov     ecx, r15d
0x1801cceac  call    cs:Mso20Win32Client_46386
0x1801cceb2  lea     rcx, [rbp+57h+var_48]
0x1801cceb6  call    sub_180073CCC
0x1801ccebb  inc     cs:dword_18025ECA4
0x1801ccec1  lea     r8, qword_1801E5A80
0x1801ccec8  cmp     [rdi], r12
0x1801ccecb  cmovnz  r8, [rdi]; Source
0x1801ccecf  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1801cced3  lea     edx, [r9+65h]; SizeInBytes
0x1801cced7  lea     rcx, byte_18025ECAC; Destination
0x1801ccede  call    cs:strncpy_s
0x1801ccee4  mov     rax, r14
0x1801ccee7  jmp     loc_1801CCD99
```
