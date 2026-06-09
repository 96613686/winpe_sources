# MdmConverters::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *)

- ea: `0x18001a8c0`
- end: `0x18001aab8`
- name: `?ConvertMultiByteToWideChar@MdmConverters@@SAJPEAEKPEAPEAG@Z`
- size: `504`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int cbMultiByte, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009d18`
- `0x18000a528`
- `0x18001b924`
- `0x18001c8d0`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x1800065c0`
- `0x18001a8c0`
- `0x18001ad0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa2b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001a996`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001aa1b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001a996`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001aa1b`

## string_xrefs

- `0x18001a904`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmconverters.cpp`
- `0x18001aa5e`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmconverters.cpp`

## pseudocode

```c
__int64 __fastcall MdmConverters::ConvertMultiByteToWideChar(
        LPCCH lpMultiByteStr,
        int cbMultiByte,
        unsigned __int16 **a3)
{
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // r14
  int cchWideChar; // r15d
  unsigned __int64 v10; // rax
  WCHAR *lpWideCharStr; // rax
  int v12; // edx
  unsigned __int16 *v13; // rsi
  signed int LastError; // eax
  unsigned __int64 v15; // rdx
  int v16; // ecx

  if ( lpMultiByteStr )
  {
    if ( a3 )
    {
      if ( *a3 )
      {
        v6 = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            (_DWORD)lpMultiByteStr,
            cbMultiByte,
            -2147024809,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmconverters.cpp",
            36,
            (__int64)"CBR(*ppWideCharBuffer == nullptr)");
      }
      else
      {
        v7 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, cbMultiByte, 0, 0);
        v8 = v7;
        cchWideChar = v7 + 1;
        v10 = 2LL * (v7 + 1);
        if ( !is_mul_ok(cchWideChar, 2u) )
          v10 = -1;
        lpWideCharStr = (WCHAR *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
        v13 = lpWideCharStr;
        if ( lpWideCharStr )
        {
          if ( MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, cbMultiByte, lpWideCharStr, cchWideChar) )
          {
            v6 = 0;
            v13[v8] = 0;
            *a3 = v13;
          }
          else
          {
            LastError = GetLastError();
            v6 = LastError;
            if ( LastError > 0 )
              v6 = (unsigned __int16)LastError | 0x80070000;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v16,
                v15,
                v6,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmconverters.cpp",
                59,
                (__int64)"CBR(0 != MultiByteToWideChar( 65001, 0, (CHAR*)pbByteArray, cbByteArray, pszBuffer, nNeededLen + 1))");
            operator delete(v13, v15);
          }
        }
        else
        {
          v6 = -2147024882;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              (_DWORD)lpMultiByteStr,
              v12,
              -2147024882,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmconverters.cpp",
              49,
              (__int64)"CPR(pszBuffer)");
        }
      }
    }
    else
    {
      v6 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)lpMultiByteStr,
          cbMultiByte,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmconverters.cpp",
          35,
          (__int64)"CPR(ppWideCharBuffer)");
    }
  }
  else
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        cbMultiByte,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmconverters.cpp",
        34,
        (__int64)"CPR(pbByteArray)");
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McTemplateU0dzs_EventWriteTransfer(
      (_DWORD)lpMultiByteStr,
      (unsigned int)MDMCOMMON_MULTIBYTE_TO_WIDE_CONVERSION,
      v6,
      (unsigned int)*a3,
      (__int64)lpMultiByteStr);
  return v6;
}

```

## disassembly

```asm
0x18001a8c0  push    rbx
0x18001a8c2  push    rbp
0x18001a8c3  push    rsi
0x18001a8c4  push    rdi
0x18001a8c5  push    r14
0x18001a8c7  push    r15
0x18001a8c9  sub     rsp, 38h
0x18001a8cd  mov     rdi, r8
0x18001a8d0  mov     ebx, edx
0x18001a8d2  mov     rbp, rcx
0x18001a8d5  test    rcx, rcx
0x18001a8d8  jnz     short loc_18001A915
0x18001a8da  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a8e1  mov     r8d, 80070057h
0x18001a8e7  mov     ebx, r8d
0x18001a8ea  jz      loc_18001AA88
0x18001a8f0  lea     rax, aCprPbbytearray; "CPR(pbByteArray)"
0x18001a8f7  mov     qword ptr [rsp+68h+cchWideChar], rax
0x18001a8fc  mov     dword ptr [rsp+68h+lpWideCharStr], 22h ; '"'
0x18001a904  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001a90b  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a910  jmp     loc_18001AA88
0x18001a915  test    rdi, rdi
0x18001a918  jnz     short loc_18001A946
0x18001a91a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a921  mov     r8d, 80070057h
0x18001a927  mov     ebx, r8d
0x18001a92a  jz      loc_18001AA88
0x18001a930  lea     rax, aCprPpwidecharb; "CPR(ppWideCharBuffer)"
0x18001a937  mov     qword ptr [rsp+68h+cchWideChar], rax
0x18001a93c  mov     dword ptr [rsp+68h+lpWideCharStr], 23h ; '#'
0x18001a944  jmp     short loc_18001A904
0x18001a946  cmp     qword ptr [r8], 0
0x18001a94a  jz      short loc_18001A978
0x18001a94c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a953  mov     r8d, 80070057h
0x18001a959  mov     ebx, r8d
0x18001a95c  jz      loc_18001AA88
0x18001a962  lea     rax, aCbrPpwidecharb; "CBR(*ppWideCharBuffer == nullptr)"
0x18001a969  mov     qword ptr [rsp+68h+cchWideChar], rax
0x18001a96e  mov     dword ptr [rsp+68h+lpWideCharStr], 24h ; '$'
0x18001a976  jmp     short loc_18001A904
0x18001a978  mov     [rsp+68h+cchWideChar], 0; cchWideChar
0x18001a980  mov     r9d, ebx; cbMultiByte
0x18001a983  mov     r8, rbp; lpMultiByteStr
0x18001a986  mov     [rsp+68h+lpWideCharStr], 0; lpWideCharStr
0x18001a98f  xor     edx, edx; dwFlags
0x18001a991  mov     ecx, 0FDE9h; CodePage
0x18001a996  call    cs:__imp_MultiByteToWideChar
0x18001a99d  nop     dword ptr [rax+rax+00h]
0x18001a9a2  movsxd  r14, eax
0x18001a9a5  mov     eax, 2
0x18001a9aa  lea     r15d, [r14+1]
0x18001a9ae  movsxd  rcx, r15d
0x18001a9b1  mul     rcx
0x18001a9b4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001a9bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a9c2  cmovb   rax, rcx
0x18001a9c6  mov     rcx, rax; unsigned __int64
0x18001a9c9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001a9ce  mov     rsi, rax
0x18001a9d1  test    rax, rax
0x18001a9d4  jnz     short loc_18001AA04
0x18001a9d6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a9dd  mov     ebx, 8007000Eh
0x18001a9e2  jz      loc_18001AA88
0x18001a9e8  lea     rax, aCprPszbuffer; "CPR(pszBuffer)"
0x18001a9ef  mov     r8d, ebx
0x18001a9f2  mov     qword ptr [rsp+68h+cchWideChar], rax
0x18001a9f7  mov     dword ptr [rsp+68h+lpWideCharStr], 31h ; '1'
0x18001a9ff  jmp     loc_18001A904
0x18001aa04  mov     [rsp+68h+cchWideChar], r15d; cchWideChar
0x18001aa09  mov     r9d, ebx; cbMultiByte
0x18001aa0c  mov     r8, rbp; lpMultiByteStr
0x18001aa0f  mov     [rsp+68h+lpWideCharStr], rsi; lpWideCharStr
0x18001aa14  xor     edx, edx; dwFlags
0x18001aa16  mov     ecx, 0FDE9h; CodePage
0x18001aa1b  call    cs:__imp_MultiByteToWideChar
0x18001aa22  nop     dword ptr [rax+rax+00h]
0x18001aa27  test    eax, eax
0x18001aa29  jnz     short loc_18001AA7C
0x18001aa2b  call    cs:__imp_GetLastError
0x18001aa32  nop     dword ptr [rax+rax+00h]
0x18001aa37  mov     ebx, eax
0x18001aa39  test    eax, eax
0x18001aa3b  jle     short loc_18001AA46
0x18001aa3d  movzx   ebx, ax
0x18001aa40  or      ebx, 80070000h
0x18001aa46  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001aa4d  jz      short loc_18001AA72
0x18001aa4f  lea     rax, aCbr0Multibytet; "CBR(0 != MultiByteToWideChar( 65001, 0,"...
0x18001aa56  mov     r8d, ebx
0x18001aa59  mov     qword ptr [rsp+68h+cchWideChar], rax
0x18001aa5e  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001aa65  mov     dword ptr [rsp+68h+lpWideCharStr], 3Bh ; ';'
0x18001aa6d  call    McTemplateU0dsqs_EventWriteTransfer
0x18001aa72  mov     rcx, rsi; void *
0x18001aa75  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001aa7a  jmp     short loc_18001AA88
0x18001aa7c  xor     ebx, ebx
0x18001aa7e  xor     eax, eax
0x18001aa80  mov     [rsi+r14*2], ax
0x18001aa85  mov     [rdi], rsi
0x18001aa88  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x18001aa8f  jz      short loc_18001AAA8
0x18001aa91  mov     r9, [rdi]
0x18001aa94  lea     rdx, MDMCOMMON_MULTIBYTE_TO_WIDE_CONVERSION
0x18001aa9b  mov     r8d, ebx
0x18001aa9e  mov     [rsp+68h+lpWideCharStr], rbp
0x18001aaa3  call    McTemplateU0dzs_EventWriteTransfer
0x18001aaa8  mov     eax, ebx
0x18001aaaa  add     rsp, 38h
0x18001aaae  pop     r15
0x18001aab0  pop     r14
0x18001aab2  pop     rdi
0x18001aab3  pop     rsi
0x18001aab4  pop     rbp
0x18001aab5  pop     rbx
0x18001aab6  retn
```
