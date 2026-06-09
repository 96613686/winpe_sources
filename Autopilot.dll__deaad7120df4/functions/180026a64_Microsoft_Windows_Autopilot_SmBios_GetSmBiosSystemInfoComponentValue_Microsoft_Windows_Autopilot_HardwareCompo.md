# Microsoft::Windows::Autopilot::SmBios::GetSmBiosSystemInfoComponentValue(Microsoft::Windows::Autopilot::HardwareComponentName,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180026a64`
- end: `0x180026ddb`
- name: `?GetSmBiosSystemInfoComponentValue@SmBios@Autopilot@Windows@Microsoft@@SAJW4HardwareComponentName@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `887`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001b760`
- `0x18001b7b0`
- `0x18001b800`
- `0x18001b850`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180017a20`
- `0x18001982c`
- `0x180026888`
- `0x180026a64`
- `0x180026de4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180026d2d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180026d5b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180026db0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180026d2d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180026d5b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180026db0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180026b43`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180026b43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026af6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026af6`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemFirmwareTable` at `0x180026ac2`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemFirmwareTable` at `0x180026b64`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemFirmwareTable` at `0x180026ac2`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemFirmwareTable` at `0x180026b64`

## string_xrefs

- `0x180026b20`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\smbios.cpp`
- `0x180026d0e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\smbios.cpp`
- `0x180026d75`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\smbios.cpp`
- `0x180026d90`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\smbios.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::SmBios::GetSmBiosSystemInfoComponentValue(int a1, __int64 a2)
{
  UINT SystemFirmwareTable; // eax
  size_t v5; // r14
  unsigned __int8 *v6; // rsi
  signed int LastError; // eax
  signed int v8; // ebx
  signed int v9; // eax
  __int64 v10; // r8
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  unsigned int *v13; // rax
  UINT v14; // eax
  unsigned int v15; // edx
  unsigned __int64 v16; // r10
  unsigned __int8 *v17; // r9
  unsigned __int8 v18; // r11
  unsigned int i; // eax
  __int64 v20; // rcx
  int v21; // edi
  int v22; // edi
  int v23; // edi
  int v24; // edi
  int SmBiosUuid; // eax
  unsigned __int8 v26; // al
  bool v27; // cc
  void *Block[2]; // [rsp+20h] [rbp-48h] BYREF
  char v30; // [rsp+30h] [rbp-38h]
  _OWORD v31[2]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  Block[0] = 0;
  Block[1] = Block;
  v30 = 1;
  v31[0] = 0;
  v31[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v31[0]) = 0;
  SystemFirmwareTable = GetSystemFirmwareTable(0x52534D42u, 0, 0, 0);
  v5 = SystemFirmwareTable;
  if ( SystemFirmwareTable )
  {
    v8 = 0;
  }
  else
  {
    v6 = 0;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_5;
  }
  v13 = (unsigned int *)malloc(v5);
  v6 = (unsigned __int8 *)v13;
  if ( !v13 || (v14 = GetSystemFirmwareTable(0x52534D42u, 0, v13, v5)) == 0 )
  {
LABEL_5:
    v9 = GetLastError();
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_7;
  }
  if ( v14 > (unsigned int)v5 || v14 < 0xC || (unsigned __int64)*((unsigned int *)v6 + 1) + 8 > v14 )
    v8 = -2147418113;
LABEL_7:
  Block[0] = v6;
  if ( v8 >= 0 )
  {
    v15 = 0;
    v16 = *((unsigned int *)v6 + 1);
LABEL_17:
    v17 = 0;
    while ( (unsigned __int64)v15 + 4 < v16 )
    {
      LOBYTE(v10) = 0;
      v18 = v6[v15 + 8];
      if ( v18 == 1 )
        v17 = &v6[v15 + 8];
      v15 += v6[v15 + 9];
      for ( i = v15 + 1; i < (unsigned int)v16; i = v20 + 1 )
      {
        v20 = v15 + 1;
        if ( !v6[v15 + 8] && !v6[v20 + 8] )
        {
          LOBYTE(v10) = 1;
          v15 += 2;
          break;
        }
        ++v15;
      }
      if ( v18 == 2 )
      {
        if ( !(_BYTE)v10 )
          break;
        if ( v17 )
        {
          if ( v17 + 15 <= &v17[v17[1]] && v17[14] == 10 )
          {
LABEL_36:
            v21 = a1 - 1;
            if ( v21 )
            {
              v22 = v21 - 1;
              if ( v22 )
              {
                v23 = v22 - 2;
                if ( v23 )
                {
                  v24 = v23 - 60;
                  if ( v24 )
                  {
                    if ( v24 == 192 )
                    {
                      SmBiosUuid = Microsoft::Windows::Autopilot::SmBios::GetSmBiosUuid(v17, v31);
                      v8 = SmBiosUuid;
                      if ( SmBiosUuid < 0 )
                      {
                        v12 = 79;
LABEL_55:
                        v11 = (unsigned int)SmBiosUuid;
                        goto LABEL_56;
                      }
                    }
                    goto LABEL_57;
                  }
                  v26 = v6[1];
                  v27 = v26 <= 2u;
                  if ( v26 == 2 )
                  {
                    if ( v6[2] < 4u )
                    {
                      v27 = 1;
                      goto LABEL_46;
                    }
LABEL_47:
                    SmBiosUuid = Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(
                                   (__int64)v17,
                                   v17[25],
                                   (__int64)v31);
                    v8 = SmBiosUuid;
                    if ( SmBiosUuid < 0 )
                    {
                      v12 = 74;
                      goto LABEL_55;
                    }
                    goto LABEL_57;
                  }
LABEL_46:
                  if ( !v27 )
                    goto LABEL_47;
                }
                else
                {
                  SmBiosUuid = Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(
                                 (__int64)v17,
                                 v17[5],
                                 (__int64)v31);
                  v8 = SmBiosUuid;
                  if ( SmBiosUuid < 0 )
                  {
                    v12 = 65;
                    goto LABEL_55;
                  }
                }
              }
              else
              {
                SmBiosUuid = Microsoft::Windows::Autopilot::SmBios::GetSmBiosString((__int64)v17, v17[4], (__int64)v31);
                v8 = SmBiosUuid;
                if ( SmBiosUuid < 0 )
                {
                  v12 = 61;
                  goto LABEL_55;
                }
              }
            }
            else
            {
              SmBiosUuid = Microsoft::Windows::Autopilot::SmBios::GetSmBiosString((__int64)v17, v17[7], (__int64)v31);
              v8 = SmBiosUuid;
              if ( SmBiosUuid < 0 )
              {
                v12 = 57;
                goto LABEL_55;
              }
            }
LABEL_57:
            std::wstring::operator=(a2, v31, v10);
            std::wstring::_Tidy_deallocate((char **)v31);
            free(Block[0]);
            return 0;
          }
          goto LABEL_17;
        }
      }
      else
      {
        if ( !(_BYTE)v10 )
          break;
        if ( v17 )
          goto LABEL_36;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\smbios.cpp",
      (const char *)0x8000FFFFLL,
      (int)Block[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\smbios.cpp",
      (const char *)0x8000FFFFLL,
      (int)Block[0]);
    std::wstring::_Tidy_deallocate((char **)v31);
    free(Block[0]);
    return 2147549183LL;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\smbios.cpp",
      (const char *)(unsigned int)v8,
      (int)Block[0]);
    v11 = (unsigned int)v8;
    v12 = 48;
LABEL_56:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\smbios.cpp",
      (const char *)v11,
      (int)Block[0]);
    std::wstring::_Tidy_deallocate((char **)v31);
    free(Block[0]);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x180026a64  push    rbp
0x180026a66  push    rbx
0x180026a67  push    rsi
0x180026a68  push    rdi
0x180026a69  push    r14
0x180026a6b  push    r15
0x180026a6d  mov     rbp, rsp
0x180026a70  sub     rsp, 68h
0x180026a74  mov     rax, cs:__security_cookie
0x180026a7b  xor     rax, rsp
0x180026a7e  mov     [rbp+var_10], rax
0x180026a82  mov     r15, rdx
0x180026a85  mov     edi, ecx
0x180026a87  mov     [rbp+Block], 0
0x180026a8f  lea     rax, [rbp+Block]
0x180026a93  mov     [rbp+var_40], rax
0x180026a97  mov     [rbp+var_38], 1
0x180026a9b  xorps   xmm0, xmm0
0x180026a9e  movups  [rbp+var_30], xmm0
0x180026aa2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180026aaa  movdqu  [rbp+var_20], xmm1
0x180026aaf  xor     eax, eax
0x180026ab1  mov     word ptr [rbp+var_30], ax
0x180026ab5  xor     r9d, r9d; BufferSize
0x180026ab8  xor     r8d, r8d; pFirmwareTableBuffer
0x180026abb  xor     edx, edx; FirmwareTableID
0x180026abd  mov     ecx, 52534D42h; FirmwareTableProviderSignature
0x180026ac2  call    cs:__imp_GetSystemFirmwareTable
0x180026ac9  nop     dword ptr [rax+rax+00h]
0x180026ace  mov     r14d, eax
0x180026ad1  test    eax, eax
0x180026ad3  jnz     short loc_180026B3E
0x180026ad5  xor     esi, esi
0x180026ad7  call    cs:__imp_GetLastError
0x180026ade  nop     dword ptr [rax+rax+00h]
0x180026ae3  mov     ebx, eax
0x180026ae5  test    eax, eax
0x180026ae7  jle     short loc_180026AF2
0x180026ae9  movzx   ebx, ax
0x180026aec  or      ebx, 80070000h
0x180026af2  test    ebx, ebx
0x180026af4  jns     short loc_180026B40
0x180026af6  call    cs:__imp_GetLastError
0x180026afd  nop     dword ptr [rax+rax+00h]
0x180026b02  mov     ebx, eax
0x180026b04  test    eax, eax
0x180026b06  jle     short loc_180026B11
0x180026b08  movzx   ebx, ax
0x180026b0b  or      ebx, 80070000h
0x180026b11  mov     [rbp+Block], rsi
0x180026b15  test    ebx, ebx
0x180026b17  jns     short loc_180026B96
0x180026b19  mov     rcx, [rbp+30h]; this
0x180026b1d  mov     r9d, ebx; char *
0x180026b20  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026b27  mov     edx, 8Ch; void *
0x180026b2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026b31  mov     r9d, ebx
0x180026b34  mov     edx, 30h ; '0'
0x180026b39  jmp     loc_180026D0E
0x180026b3e  xor     ebx, ebx
0x180026b40  mov     rcx, r14; Size
0x180026b43  call    cs:__imp_malloc
0x180026b4a  nop     dword ptr [rax+rax+00h]
0x180026b4f  mov     rsi, rax
0x180026b52  test    rax, rax
0x180026b55  jz      short loc_180026AF6
0x180026b57  mov     r9d, r14d; BufferSize
0x180026b5a  mov     r8, rax; pFirmwareTableBuffer
0x180026b5d  xor     edx, edx; FirmwareTableID
0x180026b5f  mov     ecx, 52534D42h; FirmwareTableProviderSignature
0x180026b64  call    cs:__imp_GetSystemFirmwareTable
0x180026b6b  nop     dword ptr [rax+rax+00h]
0x180026b70  test    eax, eax
0x180026b72  jz      short loc_180026AF6
0x180026b74  cmp     eax, r14d
0x180026b77  ja      short loc_180026B8C
0x180026b79  cmp     eax, 0Ch
0x180026b7c  jb      short loc_180026B8C
0x180026b7e  mov     ecx, [rsi+4]
0x180026b81  add     rcx, 8
0x180026b85  mov     eax, eax
0x180026b87  cmp     rcx, rax
0x180026b8a  jbe     short loc_180026B11
0x180026b8c  mov     ebx, 8000FFFFh
0x180026b91  jmp     loc_180026B11
0x180026b96  xor     edx, edx
0x180026b98  mov     r10d, [rsi+4]
0x180026b9c  xor     r9d, r9d
0x180026b9f  mov     ecx, edx
0x180026ba1  lea     rax, [rcx+4]
0x180026ba5  cmp     rax, r10
0x180026ba8  jnb     loc_180026D6B
0x180026bae  xor     r8b, r8b
0x180026bb1  lea     rax, [rsi+8]
0x180026bb5  add     rax, rcx
0x180026bb8  mov     r11b, [rax]
0x180026bbb  cmp     r11b, 1
0x180026bbf  cmovz   r9, rax
0x180026bc3  lea     eax, [rdx+1]
0x180026bc6  movzx   eax, byte ptr [rax+rsi+8]
0x180026bcb  add     edx, eax
0x180026bcd  lea     eax, [rdx+1]
0x180026bd0  jmp     short loc_180026BEA
0x180026bd2  lea     ecx, [rdx+1]
0x180026bd5  mov     eax, edx
0x180026bd7  cmp     [rax+rsi+8], r8b
0x180026bdc  jnz     short loc_180026BE5
0x180026bde  cmp     [rcx+rsi+8], r8b
0x180026be3  jz      short loc_180026BF1
0x180026be5  mov     edx, ecx
0x180026be7  lea     eax, [rcx+1]
0x180026bea  cmp     eax, r10d
0x180026bed  jb      short loc_180026BD2
0x180026bef  jmp     short loc_180026BF7
0x180026bf1  mov     r8b, 1
0x180026bf4  add     edx, 2
0x180026bf7  cmp     r11b, 2
0x180026bfb  jnz     short loc_180026C28
0x180026bfd  test    r8b, r8b
0x180026c00  jz      loc_180026D6B
0x180026c06  test    r9, r9
0x180026c09  jz      short loc_180026B9F
0x180026c0b  movzx   ecx, byte ptr [r9+1]
0x180026c10  add     rcx, r9
0x180026c13  lea     rax, [r9+0Fh]
0x180026c17  cmp     rax, rcx
0x180026c1a  ja      short loc_180026B9C
0x180026c1c  cmp     byte ptr [r9+0Eh], 0Ah
0x180026c21  jz      short loc_180026C3A
0x180026c23  jmp     loc_180026B9C
0x180026c28  test    r8b, r8b
0x180026c2b  jz      loc_180026D6B
0x180026c31  test    r9, r9
0x180026c34  jz      loc_180026B9F
0x180026c3a  sub     edi, 1
0x180026c3d  jz      loc_180026CF0
0x180026c43  sub     edi, 1
0x180026c46  jz      loc_180026CD3
0x180026c4c  sub     edi, 2
0x180026c4f  jz      short loc_180026CB6
0x180026c51  sub     edi, 3Ch ; '<'
0x180026c54  jz      short loc_180026C80
0x180026c56  cmp     edi, 0C0h
0x180026c5c  jnz     loc_180026D40
0x180026c62  lea     rdx, [rbp+var_30]
0x180026c66  mov     rcx, r9
0x180026c69  call    ?GetSmBiosUuid@SmBios@Autopilot@Windows@Microsoft@@SAJPEBUSystemInfo@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosUuid(Microsoft::Windows::Autopilot::SystemInfo const *,std::wstring &)
0x180026c6e  mov     ebx, eax
0x180026c70  test    eax, eax
0x180026c72  jns     loc_180026D40
0x180026c78  lea     edx, [rdi-71h]
0x180026c7b  jmp     loc_180026D0B
0x180026c80  mov     al, [rsi+1]
0x180026c83  cmp     al, 2
0x180026c85  jnz     short loc_180026C8F
0x180026c87  cmp     byte ptr [rsi+2], 4
0x180026c8b  jnb     short loc_180026C95
0x180026c8d  cmp     al, al
0x180026c8f  jbe     loc_180026D40
0x180026c95  lea     r8, [rbp+var_30]
0x180026c99  mov     dl, [r9+19h]
0x180026c9d  mov     rcx, r9
0x180026ca0  call    ?GetSmBiosString@SmBios@Autopilot@Windows@Microsoft@@SAJPEBUSmBiosStructure@234@EAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(Microsoft::Windows::Autopilot::SmBiosStructure const *,uchar,std::wstring &)
0x180026ca5  mov     ebx, eax
0x180026ca7  test    eax, eax
0x180026ca9  jns     loc_180026D40
0x180026caf  mov     edx, 4Ah ; 'J'
0x180026cb4  jmp     short loc_180026D0B
0x180026cb6  lea     r8, [rbp+var_30]
0x180026cba  mov     dl, [r9+5]
0x180026cbe  mov     rcx, r9
0x180026cc1  call    ?GetSmBiosString@SmBios@Autopilot@Windows@Microsoft@@SAJPEBUSmBiosStructure@234@EAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(Microsoft::Windows::Autopilot::SmBiosStructure const *,uchar,std::wstring &)
0x180026cc6  mov     ebx, eax
0x180026cc8  test    eax, eax
0x180026cca  jns     short loc_180026D40
0x180026ccc  mov     edx, 41h ; 'A'
0x180026cd1  jmp     short loc_180026D0B
0x180026cd3  lea     r8, [rbp+var_30]
0x180026cd7  mov     dl, [r9+4]
0x180026cdb  mov     rcx, r9
0x180026cde  call    ?GetSmBiosString@SmBios@Autopilot@Windows@Microsoft@@SAJPEBUSmBiosStructure@234@EAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(Microsoft::Windows::Autopilot::SmBiosStructure const *,uchar,std::wstring &)
0x180026ce3  mov     ebx, eax
0x180026ce5  test    eax, eax
0x180026ce7  jns     short loc_180026D40
0x180026ce9  mov     edx, 3Dh ; '='
0x180026cee  jmp     short loc_180026D0B
0x180026cf0  lea     r8, [rbp+var_30]
0x180026cf4  mov     dl, [r9+7]
0x180026cf8  mov     rcx, r9
0x180026cfb  call    ?GetSmBiosString@SmBios@Autopilot@Windows@Microsoft@@SAJPEBUSmBiosStructure@234@EAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(Microsoft::Windows::Autopilot::SmBiosStructure const *,uchar,std::wstring &)
0x180026d00  mov     ebx, eax
0x180026d02  test    eax, eax
0x180026d04  jns     short loc_180026D40
0x180026d06  mov     edx, 39h ; '9'; void *
0x180026d0b  mov     r9d, eax; char *
0x180026d0e  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026d15  mov     rcx, [rbp+30h]; this
0x180026d19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026d1e  nop
0x180026d1f  lea     rcx, [rbp+var_30]
0x180026d23  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026d28  nop
0x180026d29  mov     rcx, [rbp+Block]; Block
0x180026d2d  call    cs:__imp_free
0x180026d34  nop     dword ptr [rax+rax+00h]
0x180026d39  mov     eax, ebx
0x180026d3b  jmp     loc_180026DC1
0x180026d40  lea     rdx, [rbp+var_30]
0x180026d44  mov     rcx, r15
0x180026d47  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180026d4c  nop
0x180026d4d  lea     rcx, [rbp+var_30]
0x180026d51  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026d56  nop
0x180026d57  mov     rcx, [rbp+Block]; Block
0x180026d5b  call    cs:__imp_free
0x180026d62  nop     dword ptr [rax+rax+00h]
0x180026d67  xor     eax, eax
0x180026d69  jmp     short loc_180026DC1
0x180026d6b  mov     rcx, [rbp+30h]; this
0x180026d6f  mov     r9d, 8000FFFFh; char *
0x180026d75  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026d7c  mov     edx, 0DAh; void *
0x180026d81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026d86  mov     rcx, [rbp+30h]; this
0x180026d8a  mov     r9d, 8000FFFFh; char *
0x180026d90  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026d97  mov     edx, 34h ; '4'; void *
0x180026d9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026da1  nop
0x180026da2  lea     rcx, [rbp+var_30]
0x180026da6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026dab  nop
0x180026dac  mov     rcx, [rbp+Block]; Block
0x180026db0  call    cs:__imp_free
0x180026db7  nop     dword ptr [rax+rax+00h]
0x180026dbc  mov     eax, 8000FFFFh
0x180026dc1  mov     rcx, [rbp+var_10]
0x180026dc5  xor     rcx, rsp; StackCookie
0x180026dc8  call    __security_check_cookie
0x180026dcd  add     rsp, 68h
0x180026dd1  pop     r15
0x180026dd3  pop     r14
0x180026dd5  pop     rdi
0x180026dd6  pop     rsi
0x180026dd7  pop     rbx
0x180026dd8  pop     rbp
0x180026dd9  retn
```
