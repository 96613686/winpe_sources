# sub_1801BC8BC

- ea: `0x1801bc8bc`
- end: `0x1801bcc6d`
- name: `sub_1801BC8BC`
- size: `945`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801a1ae8`
- `0x1801a5490`
- `0x1801aa21c`
- `0x1801bc6bc`

## callees

- `0x1800994a0`
- `0x180099ee0`
- `0x1801bc8bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bc933`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bca6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bcb02`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bc933`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bca6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bcb02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bca09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bcbba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bca09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bcbba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801bcac6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801bcb5e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801bcac6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801bcb5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801bc9f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801bcb9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801bc9f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801bcb9a`

## pseudocode

```c
__int64 __fastcall sub_1801BC8BC(int a1, char a2)
{
  unsigned int v2; // ebx
  WCHAR *v4; // rdx
  LSTATUS v6; // eax
  const WCHAR *v7; // rdx
  LSTATUS v8; // eax
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[80]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v16; // [rsp+E0h] [rbp-20h]
  __int16 v17; // [rsp+E2h] [rbp-1Eh]
  _BYTE v18[220]; // [rsp+E4h] [rbp-1Ch] BYREF

  v2 = -1;
  phkResult = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  Type = 0;
  cbData = 80;
  if ( a2 == 114 && !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Scrunch", 0, 1u, &hKey) )
  {
    if ( a1 <= 8 )
    {
      switch ( a1 )
      {
        case 8:
LABEL_13:
          wmemcpy(ValueName, (const wchar_t *)&xmmword_18023BAC0, 16);
          v17 = 0;
          memset(v18, 0, sizeof(v18));
          v4 = ValueName;
          v16 = a1 + 42;
          goto LABEL_14;
        case 0:
          v4 = L"Force Post Process Mode";
          goto LABEL_14;
        case 1:
          v4 = (WCHAR *)L"Current Post Process Mode";
          goto LABEL_14;
        case 2:
          v4 = L"Post Process Mode";
          goto LABEL_14;
        case 3:
          v8 = RegOpenKeyExW(hKey, L"Video", 0, 0, &phkResult);
          if ( v8 == 2 )
          {
            dwDisposition = 0;
            v8 = RegCreateKeyExW(hKey, L"Video", 0, (LPWSTR)&Class, 0, 0, 0, &phkResult, &dwDisposition);
          }
          if ( v8 )
            goto LABEL_16;
          v7 = L"Resolution";
          break;
        case 4:
          v6 = RegOpenKeyExW(hKey, L"Video", 0, 0, &phkResult);
          if ( v6 == 2 )
          {
            dwDisposition = 0;
            v6 = RegCreateKeyExW(hKey, L"Video", 0, (LPWSTR)&Class, 0, 0, 0, &phkResult, &dwDisposition);
          }
          if ( v6 )
            goto LABEL_16;
          v7 = L"BitRate";
          break;
        default:
          switch ( a1 )
          {
            case 5:
              v4 = L"Adapt Post Process Mode";
              break;
            case 6:
              v4 = (WCHAR *)L"Adapt MHz";
              break;
            case 7:
              goto LABEL_13;
            default:
LABEL_16:
              RegCloseKey(hKey);
              return v2;
          }
LABEL_14:
          if ( !RegQueryValueExW(hKey, v4, 0, &Type, Data, &cbData) )
            v2 = *(_DWORD *)Data;
          goto LABEL_16;
      }
      if ( !RegQueryValueExW(phkResult, v7, 0, &Type, Data, &cbData) && Type == 4 )
        v2 = *(_DWORD *)Data;
      RegCloseKey(phkResult);
      goto LABEL_16;
    }
    switch ( a1 )
    {
      case 9:
      case 10:
        goto LABEL_13;
      case 11:
        v4 = L"Omit BF Mode";
        break;
      case 12:
        v4 = L"Fake Player Behind";
        break;
      case 13:
        v4 = (WCHAR *)L"Count CPU Cycles";
        break;
      case 14:
        v4 = L"DisallowKMode";
        break;
      case 15:
        v4 = L"SetRGB16_1p5x_QualityLevel";
        break;
      case 16:
        v4 = L"WMVCpuFlags";
        break;
      default:
        goto LABEL_16;
    }
    goto LABEL_14;
  }
  return v2;
}

```

## disassembly

```asm
0x1801bc8bc  mov     [rsp-8+arg_0], rbx
0x1801bc8c1  mov     [rsp-8+arg_8], rdi
0x1801bc8c6  push    rbp
0x1801bc8c7  lea     rbp, [rsp-0D0h]
0x1801bc8cf  sub     rsp, 1D0h
0x1801bc8d6  mov     rax, cs:__security_cookie
0x1801bc8dd  xor     rax, rsp
0x1801bc8e0  mov     [rbp+0D0h+var_10], rax
0x1801bc8e7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801bc8eb  mov     [rsp+1D0h+var_170], 0
0x1801bc8f4  mov     [rsp+1D0h+hKey], rbx
0x1801bc8f9  mov     edi, ecx
0x1801bc8fb  mov     [rsp+1D0h+Type], 0
0x1801bc903  mov     [rsp+1D0h+cbData], 50h ; 'P'
0x1801bc90b  cmp     dl, 72h ; 'r'
0x1801bc90e  jnz     loc_1801BCA15
0x1801bc914  lea     rax, [rsp+1D0h+hKey]
0x1801bc919  xor     r8d, r8d; ulOptions
0x1801bc91c  lea     r9d, [rbx+2]; samDesired
0x1801bc920  mov     [rsp+1D0h+phkResult], rax; phkResult
0x1801bc925  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Scrunch"
0x1801bc92c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1801bc933  call    cs:RegOpenKeyExW
0x1801bc93a  nop     dword ptr [rax+rax+00h]
0x1801bc93f  test    eax, eax
0x1801bc941  jnz     loc_1801BCA15
0x1801bc947  cmp     edi, 8
0x1801bc94a  jg      loc_1801BCBEF
0x1801bc950  jz      short loc_1801BC997
0x1801bc952  mov     ecx, edi
0x1801bc954  test    edi, edi
0x1801bc956  jz      loc_1801BCBE3
0x1801bc95c  sub     ecx, 1
0x1801bc95f  jz      loc_1801BCBD7
0x1801bc965  sub     ecx, 1
0x1801bc968  jz      loc_1801BCBCB
0x1801bc96e  sub     ecx, 1
0x1801bc971  jz      loc_1801BCAE6
0x1801bc977  sub     ecx, 1
0x1801bc97a  jz      loc_1801BCA4E
0x1801bc980  sub     ecx, 1
0x1801bc983  jz      loc_1801BCA45
0x1801bc989  sub     ecx, 1
0x1801bc98c  jz      loc_1801BCA3C
0x1801bc992  cmp     ecx, 1
0x1801bc995  jnz     short loc_1801BCA04
0x1801bc997  movups  xmm0, cs:xmmword_18023BAC0
0x1801bc99e  xor     eax, eax
0x1801bc9a0  xor     edx, edx; Val
0x1801bc9a2  movups  xmm1, cs:xmmword_18023BAD0
0x1801bc9a9  mov     r8d, 0DCh; Size
0x1801bc9af  lea     rcx, [rbp+0D0h+var_EC]; void *
0x1801bc9b3  movaps  xmmword ptr [rbp+0D0h+ValueName], xmm0
0x1801bc9b7  movaps  [rbp+0D0h+var_100], xmm1
0x1801bc9bb  mov     [rbp+0D0h+var_EE], ax
0x1801bc9bf  call    memset
0x1801bc9c4  add     di, 2Ah ; '*'
0x1801bc9c8  lea     rdx, [rbp+0D0h+ValueName]; lpValueName
0x1801bc9cc  mov     [rbp+0D0h+var_F0], di
0x1801bc9d0  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1801bc9d5  lea     rax, [rsp+1D0h+cbData]
0x1801bc9da  mov     [rsp+1D0h+lpcbData], rax; lpcbData
0x1801bc9df  lea     r9, [rsp+1D0h+Type]; lpType
0x1801bc9e4  lea     rax, [rsp+1D0h+Data]
0x1801bc9e9  xor     r8d, r8d; lpReserved
0x1801bc9ec  mov     [rsp+1D0h+phkResult], rax; lpData
0x1801bc9f1  call    cs:RegQueryValueExW
0x1801bc9f8  nop     dword ptr [rax+rax+00h]
0x1801bc9fd  test    eax, eax
0x1801bc9ff  cmovz   ebx, dword ptr [rsp+1D0h+Data]
0x1801bca04  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1801bca09  call    cs:RegCloseKey
0x1801bca10  nop     dword ptr [rax+rax+00h]
0x1801bca15  mov     eax, ebx
0x1801bca17  mov     rcx, [rbp+0D0h+var_10]
0x1801bca1e  xor     rcx, rsp; StackCookie
0x1801bca21  call    __security_check_cookie
0x1801bca26  lea     r11, [rsp+1D0h+var_s0]
0x1801bca2e  mov     rbx, [r11+10h]
0x1801bca32  mov     rdi, [r11+18h]
0x1801bca36  mov     rsp, r11
0x1801bca39  pop     rbp
0x1801bca3a  retn
0x1801bca3c  lea     rdx, aAdaptMhz; "Adapt MHz"
0x1801bca43  jmp     short loc_1801BC9D0
0x1801bca45  lea     rdx, aAdaptPostProce; "Adapt Post Process Mode"
0x1801bca4c  jmp     short loc_1801BC9D0
0x1801bca4e  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1801bca53  lea     rax, [rsp+1D0h+var_170]
0x1801bca58  xor     r9d, r9d; samDesired
0x1801bca5b  mov     [rsp+1D0h+phkResult], rax; phkResult
0x1801bca60  xor     r8d, r8d; ulOptions
0x1801bca63  lea     rdx, aVideo; "Video"
0x1801bca6a  call    cs:RegOpenKeyExW
0x1801bca71  nop     dword ptr [rax+rax+00h]
0x1801bca76  cmp     eax, 2
0x1801bca79  jnz     short loc_1801BCAD2
0x1801bca7b  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1801bca80  lea     rax, [rsp+1D0h+dwDisposition]
0x1801bca85  mov     [rsp+1D0h+lpdwDisposition], rax; lpdwDisposition
0x1801bca8a  lea     r9, Class; lpClass
0x1801bca91  lea     rax, [rsp+1D0h+var_170]
0x1801bca96  mov     [rsp+1D0h+dwDisposition], 0
0x1801bca9e  mov     [rsp+1D0h+var_198], rax; phkResult
0x1801bcaa3  lea     rdx, aVideo; "Video"
0x1801bcaaa  mov     [rsp+1D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801bcab3  xor     r8d, r8d; Reserved
0x1801bcab6  mov     dword ptr [rsp+1D0h+lpcbData], 0; samDesired
0x1801bcabe  mov     dword ptr [rsp+1D0h+phkResult], 0; dwOptions
0x1801bcac6  call    cs:RegCreateKeyExW
0x1801bcacd  nop     dword ptr [rax+rax+00h]
0x1801bcad2  test    eax, eax
0x1801bcad4  jnz     loc_1801BCA04
0x1801bcada  lea     rdx, aBitrate; "BitRate"
0x1801bcae1  jmp     loc_1801BCB79
0x1801bcae6  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1801bcaeb  lea     rax, [rsp+1D0h+var_170]
0x1801bcaf0  xor     r9d, r9d; samDesired
0x1801bcaf3  mov     [rsp+1D0h+phkResult], rax; phkResult
0x1801bcaf8  xor     r8d, r8d; ulOptions
0x1801bcafb  lea     rdx, aVideo; "Video"
0x1801bcb02  call    cs:RegOpenKeyExW
0x1801bcb09  nop     dword ptr [rax+rax+00h]
0x1801bcb0e  cmp     eax, 2
0x1801bcb11  jnz     short loc_1801BCB6A
0x1801bcb13  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1801bcb18  lea     rax, [rsp+1D0h+dwDisposition]
0x1801bcb1d  mov     [rsp+1D0h+lpdwDisposition], rax; lpdwDisposition
0x1801bcb22  lea     r9, Class; lpClass
0x1801bcb29  lea     rax, [rsp+1D0h+var_170]
0x1801bcb2e  mov     [rsp+1D0h+dwDisposition], 0
0x1801bcb36  mov     [rsp+1D0h+var_198], rax; phkResult
0x1801bcb3b  lea     rdx, aVideo; "Video"
0x1801bcb42  mov     [rsp+1D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801bcb4b  xor     r8d, r8d; Reserved
0x1801bcb4e  mov     dword ptr [rsp+1D0h+lpcbData], 0; samDesired
0x1801bcb56  mov     dword ptr [rsp+1D0h+phkResult], 0; dwOptions
0x1801bcb5e  call    cs:RegCreateKeyExW
0x1801bcb65  nop     dword ptr [rax+rax+00h]
0x1801bcb6a  test    eax, eax
0x1801bcb6c  jnz     loc_1801BCA04
0x1801bcb72  lea     rdx, aResolution; "Resolution"
0x1801bcb79  mov     rcx, [rsp+1D0h+var_170]; hKey
0x1801bcb7e  lea     rax, [rsp+1D0h+cbData]
0x1801bcb83  mov     [rsp+1D0h+lpcbData], rax; lpcbData
0x1801bcb88  lea     r9, [rsp+1D0h+Type]; lpType
0x1801bcb8d  lea     rax, [rsp+1D0h+Data]
0x1801bcb92  xor     r8d, r8d; lpReserved
0x1801bcb95  mov     [rsp+1D0h+phkResult], rax; lpData
0x1801bcb9a  call    cs:RegQueryValueExW
0x1801bcba1  nop     dword ptr [rax+rax+00h]
0x1801bcba6  test    eax, eax
0x1801bcba8  jnz     short loc_1801BCBB5
0x1801bcbaa  cmp     [rsp+1D0h+Type], 4
0x1801bcbaf  jnz     short loc_1801BCBB5
0x1801bcbb1  mov     ebx, dword ptr [rsp+1D0h+Data]
0x1801bcbb5  mov     rcx, [rsp+1D0h+var_170]; hKey
0x1801bcbba  call    cs:RegCloseKey
0x1801bcbc1  nop     dword ptr [rax+rax+00h]
0x1801bcbc6  jmp     loc_1801BCA04
0x1801bcbcb  lea     rdx, aPostProcessMod; "Post Process Mode"
0x1801bcbd2  jmp     loc_1801BC9D0
0x1801bcbd7  lea     rdx, aCurrentPostPro; "Current Post Process Mode"
0x1801bcbde  jmp     loc_1801BC9D0
0x1801bcbe3  lea     rdx, aForcePostProce; "Force Post Process Mode"
0x1801bcbea  jmp     loc_1801BC9D0
0x1801bcbef  mov     ecx, edi
0x1801bcbf1  sub     ecx, 9
0x1801bcbf4  jz      loc_1801BC997
0x1801bcbfa  sub     ecx, 1
0x1801bcbfd  jz      loc_1801BC997
0x1801bcc03  sub     ecx, 1
0x1801bcc06  jz      short loc_1801BCC61
0x1801bcc08  sub     ecx, 1
0x1801bcc0b  jz      short loc_1801BCC55
0x1801bcc0d  sub     ecx, 1
0x1801bcc10  jz      short loc_1801BCC49
0x1801bcc12  sub     ecx, 1
0x1801bcc15  jz      short loc_1801BCC3D
0x1801bcc17  sub     ecx, 1
0x1801bcc1a  jz      short loc_1801BCC31
0x1801bcc1c  cmp     ecx, 1
0x1801bcc1f  jnz     loc_1801BCA04
0x1801bcc25  lea     rdx, aWmvcpuflags; "WMVCpuFlags"
0x1801bcc2c  jmp     loc_1801BC9D0
0x1801bcc31  lea     rdx, aSetrgb161p5xQu; "SetRGB16_1p5x_QualityLevel"
0x1801bcc38  jmp     loc_1801BC9D0
0x1801bcc3d  lea     rdx, aDisallowkmode; "DisallowKMode"
0x1801bcc44  jmp     loc_1801BC9D0
0x1801bcc49  lea     rdx, aCountCpuCycles; "Count CPU Cycles"
0x1801bcc50  jmp     loc_1801BC9D0
0x1801bcc55  lea     rdx, aFakePlayerBehi; "Fake Player Behind"
0x1801bcc5c  jmp     loc_1801BC9D0
0x1801bcc61  lea     rdx, aOmitBfMode; "Omit BF Mode"
0x1801bcc68  jmp     loc_1801BC9D0
```
