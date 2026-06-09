# Microsoft::Windows::Autopilot::SmBios::GetSmBiosSystemInfoComponentValue(Microsoft::Windows::Autopilot::HardwareComponentName,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180025b90`
- end: `0x180025ed0`
- name: `?GetSmBiosSystemInfoComponentValue@SmBios@Autopilot@Windows@Microsoft@@SAJW4HardwareComponentName@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `832`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001b0c0`
- `0x18001b110`
- `0x18001b160`
- `0x18001b1b0`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x1800174f0`
- `0x180019230`
- `0x1800259c4`
- `0x180025b90`
- `0x180025ed8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025e38`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025e5d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025eac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025e38`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025e5d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025eac`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180025c5d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180025c5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c16`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemFirmwareTable` at `0x180025bee`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemFirmwareTable` at `0x180025c78`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemFirmwareTable` at `0x180025bee`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemFirmwareTable` at `0x180025c78`

## string_xrefs

- `0x180025c3a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\smbios.cpp`
- `0x180025e19`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\smbios.cpp`
- `0x180025e71`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\smbios.cpp`
- `0x180025e8c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\smbios.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Autopilot::SmBios::GetSmBiosSystemInfoComponentValue(int a1, __int64 a2)
{
  UINT SystemFirmwareTable; // eax
  size_t v5; // r14
  unsigned __int8 *v6; // rsi
  signed int LastError; // eax
  signed int v8; // ebx
  signed int v9; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  unsigned int *v12; // rax
  UINT v13; // eax
  __int64 v14; // rdx
  unsigned __int64 v15; // r10
  unsigned __int8 *v16; // r9
  char v17; // r8
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
  v12 = (unsigned int *)malloc(v5);
  v6 = (unsigned __int8 *)v12;
  if ( !v12 || (v13 = GetSystemFirmwareTable(0x52534D42u, 0, v12, v5)) == 0 )
  {
LABEL_5:
    v9 = GetLastError();
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_7;
  }
  if ( v13 > (unsigned int)v5 || v13 < 0xC || (unsigned __int64)*((unsigned int *)v6 + 1) + 8 > v13 )
    v8 = -2147418113;
LABEL_7:
  Block[0] = v6;
  if ( v8 >= 0 )
  {
    LODWORD(v14) = 0;
    v15 = *((unsigned int *)v6 + 1);
LABEL_17:
    v16 = 0;
    while ( (unsigned __int64)(unsigned int)v14 + 4 < v15 )
    {
      v17 = 0;
      v18 = v6[(unsigned int)v14 + 8];
      if ( v18 == 1 )
        v16 = &v6[(unsigned int)v14 + 8];
      v14 = v6[(unsigned int)(v14 + 1) + 8] + (unsigned int)v14;
      for ( i = v14 + 1; i < (unsigned int)v15; i = v20 + 1 )
      {
        v20 = (unsigned int)(v14 + 1);
        if ( !v6[(unsigned int)v14 + 8] && !v6[v20 + 8] )
        {
          v17 = 1;
          v14 = (unsigned int)(v14 + 2);
          break;
        }
        v14 = (unsigned int)v20;
      }
      if ( v18 == 2 )
      {
        if ( !v17 )
          break;
        if ( v16 )
        {
          if ( v16 + 15 <= &v16[v16[1]] && v16[14] == 10 )
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
                      SmBiosUuid = Microsoft::Windows::Autopilot::SmBios::GetSmBiosUuid(v16, v31);
                      v8 = SmBiosUuid;
                      if ( SmBiosUuid < 0 )
                      {
                        v11 = 79;
LABEL_55:
                        v10 = (unsigned int)SmBiosUuid;
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
                    LOBYTE(v14) = v16[25];
                    SmBiosUuid = Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(v16, v14, v31);
                    v8 = SmBiosUuid;
                    if ( SmBiosUuid < 0 )
                    {
                      v11 = 74;
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
                  LOBYTE(v14) = v16[5];
                  SmBiosUuid = Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(v16, v14, v31);
                  v8 = SmBiosUuid;
                  if ( SmBiosUuid < 0 )
                  {
                    v11 = 65;
                    goto LABEL_55;
                  }
                }
              }
              else
              {
                LOBYTE(v14) = v16[4];
                SmBiosUuid = Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(v16, v14, v31);
                v8 = SmBiosUuid;
                if ( SmBiosUuid < 0 )
                {
                  v11 = 61;
                  goto LABEL_55;
                }
              }
            }
            else
            {
              LOBYTE(v14) = v16[7];
              SmBiosUuid = Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(v16, v14, v31);
              v8 = SmBiosUuid;
              if ( SmBiosUuid < 0 )
              {
                v11 = 57;
                goto LABEL_55;
              }
            }
LABEL_57:
            std::wstring::operator=(a2, v31);
            std::wstring::_Tidy_deallocate(v31);
            free(Block[0]);
            return 0;
          }
          goto LABEL_17;
        }
      }
      else
      {
        if ( !v17 )
          break;
        if ( v16 )
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
    std::wstring::_Tidy_deallocate(v31);
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
    v10 = (unsigned int)v8;
    v11 = 48;
LABEL_56:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\smbios.cpp",
      (const char *)v10,
      (int)Block[0]);
    std::wstring::_Tidy_deallocate(v31);
    free(Block[0]);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x180025b90  push    rbp
0x180025b92  push    rbx
0x180025b93  push    rsi
0x180025b94  push    rdi
0x180025b95  push    r14
0x180025b97  push    r15
0x180025b99  mov     rbp, rsp
0x180025b9c  sub     rsp, 68h
0x180025ba0  mov     rax, cs:__security_cookie
0x180025ba7  xor     rax, rsp
0x180025baa  mov     [rbp+var_10], rax
0x180025bae  mov     r15, rdx
0x180025bb1  mov     edi, ecx
0x180025bb3  mov     [rbp+Block], 0
0x180025bbb  lea     rax, [rbp+Block]
0x180025bbf  mov     [rbp+var_40], rax
0x180025bc3  mov     [rbp+var_38], 1
0x180025bc7  xorps   xmm0, xmm0
0x180025bca  movups  [rbp+var_30], xmm0
0x180025bce  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180025bd6  movdqu  [rbp+var_20], xmm1
0x180025bdb  xor     eax, eax
0x180025bdd  mov     word ptr [rbp+var_30], ax
0x180025be1  xor     r9d, r9d; BufferSize
0x180025be4  xor     r8d, r8d; pFirmwareTableBuffer
0x180025be7  xor     edx, edx; FirmwareTableID
0x180025be9  mov     ecx, 52534D42h; FirmwareTableProviderSignature
0x180025bee  call    cs:__imp_GetSystemFirmwareTable
0x180025bf4  mov     r14d, eax
0x180025bf7  test    eax, eax
0x180025bf9  jnz     short loc_180025C58
0x180025bfb  xor     esi, esi
0x180025bfd  call    cs:__imp_GetLastError
0x180025c03  mov     ebx, eax
0x180025c05  test    eax, eax
0x180025c07  jle     short loc_180025C12
0x180025c09  movzx   ebx, ax
0x180025c0c  or      ebx, 80070000h
0x180025c12  test    ebx, ebx
0x180025c14  jns     short loc_180025C5A
0x180025c16  call    cs:__imp_GetLastError
0x180025c1c  mov     ebx, eax
0x180025c1e  test    eax, eax
0x180025c20  jle     short loc_180025C2B
0x180025c22  movzx   ebx, ax
0x180025c25  or      ebx, 80070000h
0x180025c2b  mov     [rbp+Block], rsi
0x180025c2f  test    ebx, ebx
0x180025c31  jns     short loc_180025CA1
0x180025c33  mov     rcx, [rbp+30h]; this
0x180025c37  mov     r9d, ebx; char *
0x180025c3a  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025c41  mov     edx, 8Ch; void *
0x180025c46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025c4b  mov     r9d, ebx
0x180025c4e  mov     edx, 30h ; '0'
0x180025c53  jmp     loc_180025E19
0x180025c58  xor     ebx, ebx
0x180025c5a  mov     rcx, r14; Size
0x180025c5d  call    cs:__imp_malloc
0x180025c63  mov     rsi, rax
0x180025c66  test    rax, rax
0x180025c69  jz      short loc_180025C16
0x180025c6b  mov     r9d, r14d; BufferSize
0x180025c6e  mov     r8, rax; pFirmwareTableBuffer
0x180025c71  xor     edx, edx; FirmwareTableID
0x180025c73  mov     ecx, 52534D42h; FirmwareTableProviderSignature
0x180025c78  call    cs:__imp_GetSystemFirmwareTable
0x180025c7e  test    eax, eax
0x180025c80  jz      short loc_180025C16
0x180025c82  cmp     eax, r14d
0x180025c85  ja      short loc_180025C9A
0x180025c87  cmp     eax, 0Ch
0x180025c8a  jb      short loc_180025C9A
0x180025c8c  mov     ecx, [rsi+4]
0x180025c8f  add     rcx, 8
0x180025c93  mov     eax, eax
0x180025c95  cmp     rcx, rax
0x180025c98  jbe     short loc_180025C2B
0x180025c9a  mov     ebx, 8000FFFFh
0x180025c9f  jmp     short loc_180025C2B
0x180025ca1  xor     edx, edx
0x180025ca3  mov     r10d, [rsi+4]
0x180025ca7  xor     r9d, r9d
0x180025caa  mov     ecx, edx
0x180025cac  lea     rax, [rcx+4]
0x180025cb0  cmp     rax, r10
0x180025cb3  jnb     loc_180025E67
0x180025cb9  xor     r8b, r8b
0x180025cbc  lea     rax, [rsi+8]
0x180025cc0  add     rax, rcx
0x180025cc3  mov     r11b, [rax]
0x180025cc6  cmp     r11b, 1
0x180025cca  cmovz   r9, rax
0x180025cce  lea     eax, [rdx+1]
0x180025cd1  movzx   eax, byte ptr [rax+rsi+8]
0x180025cd6  add     edx, eax
0x180025cd8  lea     eax, [rdx+1]
0x180025cdb  jmp     short loc_180025CF5
0x180025cdd  lea     ecx, [rdx+1]
0x180025ce0  mov     eax, edx
0x180025ce2  cmp     [rax+rsi+8], r8b
0x180025ce7  jnz     short loc_180025CF0
0x180025ce9  cmp     [rcx+rsi+8], r8b
0x180025cee  jz      short loc_180025CFC
0x180025cf0  mov     edx, ecx
0x180025cf2  lea     eax, [rcx+1]
0x180025cf5  cmp     eax, r10d
0x180025cf8  jb      short loc_180025CDD
0x180025cfa  jmp     short loc_180025D02
0x180025cfc  mov     r8b, 1
0x180025cff  add     edx, 2
0x180025d02  cmp     r11b, 2
0x180025d06  jnz     short loc_180025D33
0x180025d08  test    r8b, r8b
0x180025d0b  jz      loc_180025E67
0x180025d11  test    r9, r9
0x180025d14  jz      short loc_180025CAA
0x180025d16  movzx   ecx, byte ptr [r9+1]
0x180025d1b  add     rcx, r9
0x180025d1e  lea     rax, [r9+0Fh]
0x180025d22  cmp     rax, rcx
0x180025d25  ja      short loc_180025CA7
0x180025d27  cmp     byte ptr [r9+0Eh], 0Ah
0x180025d2c  jz      short loc_180025D45
0x180025d2e  jmp     loc_180025CA7
0x180025d33  test    r8b, r8b
0x180025d36  jz      loc_180025E67
0x180025d3c  test    r9, r9
0x180025d3f  jz      loc_180025CAA
0x180025d45  sub     edi, 1
0x180025d48  jz      loc_180025DFB
0x180025d4e  sub     edi, 1
0x180025d51  jz      loc_180025DDE
0x180025d57  sub     edi, 2
0x180025d5a  jz      short loc_180025DC1
0x180025d5c  sub     edi, 3Ch ; '<'
0x180025d5f  jz      short loc_180025D8B
0x180025d61  cmp     edi, 0C0h
0x180025d67  jnz     loc_180025E42
0x180025d6d  lea     rdx, [rbp+var_30]
0x180025d71  mov     rcx, r9
0x180025d74  call    ?GetSmBiosUuid@SmBios@Autopilot@Windows@Microsoft@@SAJPEBUSystemInfo@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosUuid(Microsoft::Windows::Autopilot::SystemInfo const *,std::wstring &)
0x180025d79  mov     ebx, eax
0x180025d7b  test    eax, eax
0x180025d7d  jns     loc_180025E42
0x180025d83  lea     edx, [rdi-71h]
0x180025d86  jmp     loc_180025E16
0x180025d8b  mov     al, [rsi+1]
0x180025d8e  cmp     al, 2
0x180025d90  jnz     short loc_180025D9A
0x180025d92  cmp     byte ptr [rsi+2], 4
0x180025d96  jnb     short loc_180025DA0
0x180025d98  cmp     al, al
0x180025d9a  jbe     loc_180025E42
0x180025da0  lea     r8, [rbp+var_30]
0x180025da4  mov     dl, [r9+19h]
0x180025da8  mov     rcx, r9
0x180025dab  call    ?GetSmBiosString@SmBios@Autopilot@Windows@Microsoft@@SAJPEBUSmBiosStructure@234@EAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(Microsoft::Windows::Autopilot::SmBiosStructure const *,uchar,std::wstring &)
0x180025db0  mov     ebx, eax
0x180025db2  test    eax, eax
0x180025db4  jns     loc_180025E42
0x180025dba  mov     edx, 4Ah ; 'J'
0x180025dbf  jmp     short loc_180025E16
0x180025dc1  lea     r8, [rbp+var_30]
0x180025dc5  mov     dl, [r9+5]
0x180025dc9  mov     rcx, r9
0x180025dcc  call    ?GetSmBiosString@SmBios@Autopilot@Windows@Microsoft@@SAJPEBUSmBiosStructure@234@EAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(Microsoft::Windows::Autopilot::SmBiosStructure const *,uchar,std::wstring &)
0x180025dd1  mov     ebx, eax
0x180025dd3  test    eax, eax
0x180025dd5  jns     short loc_180025E42
0x180025dd7  mov     edx, 41h ; 'A'
0x180025ddc  jmp     short loc_180025E16
0x180025dde  lea     r8, [rbp+var_30]
0x180025de2  mov     dl, [r9+4]
0x180025de6  mov     rcx, r9
0x180025de9  call    ?GetSmBiosString@SmBios@Autopilot@Windows@Microsoft@@SAJPEBUSmBiosStructure@234@EAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(Microsoft::Windows::Autopilot::SmBiosStructure const *,uchar,std::wstring &)
0x180025dee  mov     ebx, eax
0x180025df0  test    eax, eax
0x180025df2  jns     short loc_180025E42
0x180025df4  mov     edx, 3Dh ; '='
0x180025df9  jmp     short loc_180025E16
0x180025dfb  lea     r8, [rbp+var_30]
0x180025dff  mov     dl, [r9+7]
0x180025e03  mov     rcx, r9
0x180025e06  call    ?GetSmBiosString@SmBios@Autopilot@Windows@Microsoft@@SAJPEBUSmBiosStructure@234@EAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(Microsoft::Windows::Autopilot::SmBiosStructure const *,uchar,std::wstring &)
0x180025e0b  mov     ebx, eax
0x180025e0d  test    eax, eax
0x180025e0f  jns     short loc_180025E42
0x180025e11  mov     edx, 39h ; '9'; void *
0x180025e16  mov     r9d, eax; char *
0x180025e19  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025e20  mov     rcx, [rbp+30h]; this
0x180025e24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025e29  nop
0x180025e2a  lea     rcx, [rbp+var_30]
0x180025e2e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025e33  nop
0x180025e34  mov     rcx, [rbp+Block]; Block
0x180025e38  call    cs:__imp_free
0x180025e3e  mov     eax, ebx
0x180025e40  jmp     short loc_180025EB7
0x180025e42  lea     rdx, [rbp+var_30]
0x180025e46  mov     rcx, r15
0x180025e49  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180025e4e  nop
0x180025e4f  lea     rcx, [rbp+var_30]
0x180025e53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025e58  nop
0x180025e59  mov     rcx, [rbp+Block]; Block
0x180025e5d  call    cs:__imp_free
0x180025e63  xor     eax, eax
0x180025e65  jmp     short loc_180025EB7
0x180025e67  mov     rcx, [rbp+30h]; this
0x180025e6b  mov     r9d, 8000FFFFh; char *
0x180025e71  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025e78  mov     edx, 0DAh; void *
0x180025e7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025e82  mov     rcx, [rbp+30h]; this
0x180025e86  mov     r9d, 8000FFFFh; char *
0x180025e8c  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025e93  mov     edx, 34h ; '4'; void *
0x180025e98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025e9d  nop
0x180025e9e  lea     rcx, [rbp+var_30]
0x180025ea2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025ea7  nop
0x180025ea8  mov     rcx, [rbp+Block]; Block
0x180025eac  call    cs:__imp_free
0x180025eb2  mov     eax, 8000FFFFh
0x180025eb7  mov     rcx, [rbp+var_10]
0x180025ebb  xor     rcx, rsp; StackCookie
0x180025ebe  call    __security_check_cookie
0x180025ec3  add     rsp, 68h
0x180025ec7  pop     r15
0x180025ec9  pop     r14
0x180025ecb  pop     rdi
0x180025ecc  pop     rsi
0x180025ecd  pop     rbx
0x180025ece  pop     rbp
0x180025ecf  retn
```
