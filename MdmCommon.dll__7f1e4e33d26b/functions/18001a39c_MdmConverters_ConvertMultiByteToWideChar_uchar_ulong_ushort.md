# MdmConverters::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *)

- ea: `0x18001a39c`
- end: `0x18001a581`
- name: `?ConvertMultiByteToWideChar@MdmConverters@@SAJPEAEKPEAPEAG@Z`
- size: `485`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int cbMultiByte, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009b24`
- `0x18000a314`
- `0x18001b394`
- `0x18001c298`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x180006548`
- `0x18001a39c`
- `0x18001a7c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4fb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001a472`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001a4f1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001a472`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001a4f1`

## string_xrefs

- `0x18001a3e0`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmconverters.cpp`
- `0x18001a528`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmconverters.cpp`

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
  int v15; // edx
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
            operator delete(v13);
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
0x18001a39c  push    rbx
0x18001a39e  push    rbp
0x18001a39f  push    rsi
0x18001a3a0  push    rdi
0x18001a3a1  push    r14
0x18001a3a3  push    r15
0x18001a3a5  sub     rsp, 38h
0x18001a3a9  mov     rdi, r8
0x18001a3ac  mov     ebx, edx
0x18001a3ae  mov     rbp, rcx
0x18001a3b1  test    rcx, rcx
0x18001a3b4  jnz     short loc_18001A3F1
0x18001a3b6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a3bd  mov     r8d, 80070057h
0x18001a3c3  mov     ebx, r8d
0x18001a3c6  jz      loc_18001A552
0x18001a3cc  lea     rax, aCprPbbytearray; "CPR(pbByteArray)"
0x18001a3d3  mov     qword ptr [rsp+68h+cchWideChar], rax
0x18001a3d8  mov     dword ptr [rsp+68h+lpWideCharStr], 22h ; '"'
0x18001a3e0  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001a3e7  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a3ec  jmp     loc_18001A552
0x18001a3f1  test    rdi, rdi
0x18001a3f4  jnz     short loc_18001A422
0x18001a3f6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a3fd  mov     r8d, 80070057h
0x18001a403  mov     ebx, r8d
0x18001a406  jz      loc_18001A552
0x18001a40c  lea     rax, aCprPpwidecharb; "CPR(ppWideCharBuffer)"
0x18001a413  mov     qword ptr [rsp+68h+cchWideChar], rax
0x18001a418  mov     dword ptr [rsp+68h+lpWideCharStr], 23h ; '#'
0x18001a420  jmp     short loc_18001A3E0
0x18001a422  cmp     qword ptr [r8], 0
0x18001a426  jz      short loc_18001A454
0x18001a428  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a42f  mov     r8d, 80070057h
0x18001a435  mov     ebx, r8d
0x18001a438  jz      loc_18001A552
0x18001a43e  lea     rax, aCbrPpwidecharb; "CBR(*ppWideCharBuffer == nullptr)"
0x18001a445  mov     qword ptr [rsp+68h+cchWideChar], rax
0x18001a44a  mov     dword ptr [rsp+68h+lpWideCharStr], 24h ; '$'
0x18001a452  jmp     short loc_18001A3E0
0x18001a454  mov     [rsp+68h+cchWideChar], 0; cchWideChar
0x18001a45c  mov     r9d, ebx; cbMultiByte
0x18001a45f  mov     r8, rbp; lpMultiByteStr
0x18001a462  mov     [rsp+68h+lpWideCharStr], 0; lpWideCharStr
0x18001a46b  xor     edx, edx; dwFlags
0x18001a46d  mov     ecx, 0FDE9h; CodePage
0x18001a472  call    cs:__imp_MultiByteToWideChar
0x18001a478  movsxd  r14, eax
0x18001a47b  mov     eax, 2
0x18001a480  lea     r15d, [r14+1]
0x18001a484  movsxd  rcx, r15d
0x18001a487  mul     rcx
0x18001a48a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001a491  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a498  cmovb   rax, rcx
0x18001a49c  mov     rcx, rax; unsigned __int64
0x18001a49f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001a4a4  mov     rsi, rax
0x18001a4a7  test    rax, rax
0x18001a4aa  jnz     short loc_18001A4DA
0x18001a4ac  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a4b3  mov     ebx, 8007000Eh
0x18001a4b8  jz      loc_18001A552
0x18001a4be  lea     rax, aCprPszbuffer; "CPR(pszBuffer)"
0x18001a4c5  mov     r8d, ebx
0x18001a4c8  mov     qword ptr [rsp+68h+cchWideChar], rax
0x18001a4cd  mov     dword ptr [rsp+68h+lpWideCharStr], 31h ; '1'
0x18001a4d5  jmp     loc_18001A3E0
0x18001a4da  mov     [rsp+68h+cchWideChar], r15d; cchWideChar
0x18001a4df  mov     r9d, ebx; cbMultiByte
0x18001a4e2  mov     r8, rbp; lpMultiByteStr
0x18001a4e5  mov     [rsp+68h+lpWideCharStr], rsi; lpWideCharStr
0x18001a4ea  xor     edx, edx; dwFlags
0x18001a4ec  mov     ecx, 0FDE9h; CodePage
0x18001a4f1  call    cs:__imp_MultiByteToWideChar
0x18001a4f7  test    eax, eax
0x18001a4f9  jnz     short loc_18001A546
0x18001a4fb  call    cs:__imp_GetLastError
0x18001a501  mov     ebx, eax
0x18001a503  test    eax, eax
0x18001a505  jle     short loc_18001A510
0x18001a507  movzx   ebx, ax
0x18001a50a  or      ebx, 80070000h
0x18001a510  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a517  jz      short loc_18001A53C
0x18001a519  lea     rax, aCbr0Multibytet; "CBR(0 != MultiByteToWideChar( 65001, 0,"...
0x18001a520  mov     r8d, ebx
0x18001a523  mov     qword ptr [rsp+68h+cchWideChar], rax
0x18001a528  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001a52f  mov     dword ptr [rsp+68h+lpWideCharStr], 3Bh ; ';'
0x18001a537  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a53c  mov     rcx, rsi; void *
0x18001a53f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a544  jmp     short loc_18001A552
0x18001a546  xor     ebx, ebx
0x18001a548  xor     eax, eax
0x18001a54a  mov     [rsi+r14*2], ax
0x18001a54f  mov     [rdi], rsi
0x18001a552  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x18001a559  jz      short loc_18001A572
0x18001a55b  mov     r9, [rdi]
0x18001a55e  lea     rdx, MDMCOMMON_MULTIBYTE_TO_WIDE_CONVERSION
0x18001a565  mov     r8d, ebx
0x18001a568  mov     [rsp+68h+lpWideCharStr], rbp
0x18001a56d  call    McTemplateU0dzs_EventWriteTransfer
0x18001a572  mov     eax, ebx
0x18001a574  add     rsp, 38h
0x18001a578  pop     r15
0x18001a57a  pop     r14
0x18001a57c  pop     rdi
0x18001a57d  pop     rsi
0x18001a57e  pop     rbp
0x18001a57f  pop     rbx
0x18001a580  retn
```
