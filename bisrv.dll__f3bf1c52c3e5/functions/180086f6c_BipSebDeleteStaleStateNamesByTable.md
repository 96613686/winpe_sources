# BipSebDeleteStaleStateNamesByTable

- ea: `0x180086f6c`
- end: `0x1800872fe`
- name: `BipSebDeleteStaleStateNamesByTable`
- size: `914`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180086d18`

## callees

- `0x18002b060`
- `0x180086bac`
- `0x180086f6c`
- `0x180087578`
- `0x18009467a`
- `0x1800946a0`
- `0x180094730`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800870ee`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800870ee`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x180087209`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x180087209`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800872d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800872d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087025`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087025`

## pseudocode

```c
__int64 __fastcall BipSebDeleteStaleStateNamesByTable(__int64 a1)
{
  __int64 v1; // rsi
  LSTATUS v2; // r12d
  int v3; // r14d
  int v4; // r15d
  LSTATUS v5; // ecx
  unsigned int v6; // ebx
  DWORD v7; // edi
  DWORD i; // edx
  DWORD v9; // r13d
  LSTATUS v10; // ebx
  LSTATUS v11; // eax
  LSTATUS v12; // esi
  __int64 v13; // rax
  bool v14; // zf
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  LSTATUS v19; // [rsp+4Ch] [rbp-B4h] BYREF
  LSTATUS v20; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v21; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v25[32]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v26; // [rsp+90h] [rbp-70h]
  __int64 v27; // [rsp+98h] [rbp-68h]
  CHAR *v28; // [rsp+A0h] [rbp-60h]
  __int64 v29; // [rsp+A8h] [rbp-58h]
  LSTATUS *v30; // [rsp+B0h] [rbp-50h]
  __int64 v31; // [rsp+B8h] [rbp-48h]
  unsigned int *v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+C8h] [rbp-38h]
  __int64 *v34; // [rsp+D0h] [rbp-30h]
  __int64 v35; // [rsp+D8h] [rbp-28h]
  char v36[32]; // [rsp+E0h] [rbp-20h] BYREF
  CHAR ValueName[512]; // [rsp+100h] [rbp+0h] BYREF
  BYTE Data[4096]; // [rsp+300h] [rbp+200h] BYREF

  v1 = a1;
  v24 = a1;
  cbData = 0;
  hKey = 0;
  cchValueName = 0;
  Type = 0;
  if ( (unsigned int)dword_1800C3098 > 4 )
    tlgWriteTransfer_EventWriteTransfer(&dword_1800C3098, word_1800B2922, 0, 0, 2, v36);
  hKey = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Notifications",
         0,
         0xF003Fu,
         &hKey);
  if ( v5 )
  {
    v6 = -1073739508;
  }
  else
  {
    cchValueName = 512;
    cbData = 4096;
    v7 = 0;
    memset_0(Data, 0, sizeof(Data));
    memset_0(ValueName, 0, sizeof(ValueName));
    for ( i = 0; ; i = v7 )
    {
      v5 = RegEnumValueA(hKey, i, ValueName, &cchValueName, 0, &Type, Data, &cbData);
      if ( v5 == 259 )
        break;
      v9 = v7;
      ++v4;
      ++v7;
      if ( !v5 && Type == 3 && cbData == 1076 )
      {
        v23 = 0;
        ++v2;
        if ( (int)BipGetStateNameFromString(ValueName, cchValueName) >= 0 )
        {
          v10 = v23;
          if ( (unsigned int)BipSebLookupStateNameFromTable(v1, v23, 0) == -1073741275 )
          {
            v11 = RegDeleteValueA(hKey, ValueName);
            v12 = v11;
            if ( (unsigned int)dword_1800C3098 > 4 )
            {
              v19 = v11;
              v27 = 4;
              v26 = &v19;
              v13 = -1;
              do
                ++v13;
              while ( ValueName[v13] );
              v29 = (unsigned int)(v13 + 1);
              v28 = ValueName;
              v30 = &v20;
              v21 = HIDWORD(v23);
              v31 = 4;
              v32 = &v21;
              v33 = 4;
              v20 = v10;
              tlgWriteTransfer_EventWriteTransfer(&dword_1800C3098, &word_1800B2A5E, 0, 0, 6, v25);
            }
            v14 = v12 == 0;
            v1 = v24;
            if ( v14 )
            {
              ++v3;
              v7 = v9;
            }
          }
        }
      }
      cbData = 4096;
      cchValueName = 512;
      memset_0(Data, 0, sizeof(Data));
      memset_0(ValueName, 0, sizeof(ValueName));
    }
    v6 = 0;
  }
  if ( (unsigned int)dword_1800C3098 > 4 )
  {
    v20 = v5;
    v26 = &v21;
    v21 = v6;
    v28 = (CHAR *)&v20;
    v27 = 4;
    v30 = &v19;
    v29 = 4;
    v32 = (unsigned int *)&v24;
    v19 = v2;
    v34 = &v23;
    v31 = 4;
    LODWORD(v24) = v3;
    v33 = 4;
    LODWORD(v23) = v4;
    v35 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800C3098, byte_1800B29D9, 0, 0, 7, v25);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180086f6c  push    rbp
0x180086f6e  push    rbx
0x180086f6f  push    rsi
0x180086f70  push    rdi
0x180086f71  push    r12
0x180086f73  push    r13
0x180086f75  push    r14
0x180086f77  push    r15
0x180086f79  lea     rbp, [rsp-1218h]
0x180086f81  mov     eax, 1318h
0x180086f86  call    _alloca_probe
0x180086f8b  sub     rsp, rax
0x180086f8e  mov     rax, cs:__security_cookie
0x180086f95  xor     rax, rsp
0x180086f98  mov     [rbp+1250h+var_50], rax
0x180086f9f  mov     eax, cs:dword_1800C3098
0x180086fa5  xor     r13d, r13d
0x180086fa8  mov     rsi, rcx
0x180086fab  mov     [rsp+1350h+var_12E8], rcx
0x180086fb0  mov     [rsp+1350h+cbData], r13d
0x180086fb5  mov     [rsp+1350h+hKey], r13
0x180086fba  lea     edi, [r13+4]
0x180086fbe  mov     [rsp+1350h+cchValueName], r13d
0x180086fc3  mov     [rsp+1350h+Type], r13d
0x180086fc8  cmp     eax, edi
0x180086fca  jbe     short loc_180086FF6
0x180086fcc  lea     rax, [rbp+1250h+var_1270]
0x180086fd0  xor     r9d, r9d
0x180086fd3  mov     [rsp+1350h+lpType], rax
0x180086fd8  lea     rdx, word_1800B2922
0x180086fdf  xor     r8d, r8d
0x180086fe2  mov     dword ptr [rsp+1350h+phkResult], 2
0x180086fea  lea     rcx, dword_1800C3098
0x180086ff1  call    _tlgWriteTransfer_EventWriteTransfer
0x180086ff6  lea     rax, [rsp+1350h+hKey]
0x180086ffb  mov     [rsp+1350h+hKey], r13
0x180087000  mov     r9d, 0F003Fh; samDesired
0x180087006  mov     [rsp+1350h+phkResult], rax; phkResult
0x18008700b  xor     r8d, r8d; ulOptions
0x18008700e  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180087015  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008701c  mov     r12d, r13d
0x18008701f  mov     r14d, r13d
0x180087022  mov     r15d, r13d
0x180087025  call    cs:__imp_RegOpenKeyExW
0x18008702b  mov     ecx, eax
0x18008702d  test    eax, eax
0x18008702f  jz      short loc_18008703B
0x180087031  mov     ebx, 0C000090Ch
0x180087036  jmp     loc_180087224
0x18008703b  mov     eax, 1000h
0x180087040  mov     [rsp+1350h+cchValueName], 200h
0x180087048  mov     r8d, eax; Size
0x18008704b  mov     [rsp+1350h+cbData], eax
0x18008704f  xor     edx, edx; Val
0x180087051  lea     rcx, [rbp+1250h+Data]; void *
0x180087058  mov     edi, r13d
0x18008705b  call    memset_0
0x180087060  xor     edx, edx; Val
0x180087062  lea     rcx, [rbp+1250h+ValueName]; void *
0x180087066  mov     r8d, 200h; Size
0x18008706c  call    memset_0
0x180087071  xor     edx, edx
0x180087073  jmp     loc_1800871D6
0x180087078  mov     r13d, edi
0x18008707b  inc     r15d
0x18008707e  inc     edi
0x180087080  test    ecx, ecx
0x180087082  jnz     loc_18008719E
0x180087088  cmp     [rsp+1350h+Type], 3
0x18008708d  jnz     loc_18008719E
0x180087093  cmp     [rsp+1350h+cbData], 434h
0x18008709b  jnz     loc_18008719E
0x1800870a1  mov     edx, [rsp+1350h+cchValueName]; Size
0x1800870a5  lea     r8, [rsp+1350h+var_12F0]
0x1800870aa  lea     rcx, [rbp+1250h+ValueName]; Src
0x1800870ae  mov     [rsp+1350h+var_12F0], 0
0x1800870b7  inc     r12d
0x1800870ba  call    BipGetStateNameFromString
0x1800870bf  test    eax, eax
0x1800870c1  js      loc_18008719E
0x1800870c7  mov     rbx, [rsp+1350h+var_12F0]
0x1800870cc  xor     r8d, r8d
0x1800870cf  mov     rdx, rbx
0x1800870d2  mov     rcx, rsi
0x1800870d5  call    BipSebLookupStateNameFromTable
0x1800870da  cmp     eax, 0C0000225h
0x1800870df  jnz     loc_18008719E
0x1800870e5  mov     rcx, [rsp+1350h+hKey]; hKey
0x1800870ea  lea     rdx, [rbp+1250h+ValueName]; lpValueName
0x1800870ee  call    cs:__imp_RegDeleteValueA
0x1800870f4  mov     ecx, cs:dword_1800C3098
0x1800870fa  mov     r8d, 4
0x180087100  mov     esi, eax
0x180087102  cmp     ecx, r8d
0x180087105  jbe     loc_18008718F
0x18008710b  mov     [rsp+1350h+var_1304], eax
0x18008710f  lea     rcx, [rbp+1250h+ValueName]
0x180087113  lea     rax, [rsp+1350h+var_1304]
0x180087118  mov     [rbp+1250h+var_12B8], r8
0x18008711c  xor     edx, edx
0x18008711e  mov     [rbp+1250h+var_12C0], rax
0x180087122  or      rax, 0FFFFFFFFFFFFFFFFh
0x180087126  inc     rax
0x180087129  cmp     [rcx+rax], dl
0x18008712c  jnz     short loc_180087126
0x18008712e  inc     eax
0x180087130  mov     dword ptr [rbp+1250h+var_12A8+4], edx
0x180087133  mov     dword ptr [rbp+1250h+var_12A8], eax
0x180087136  lea     rcx, [rbp+1250h+ValueName]
0x18008713a  lea     rax, [rsp+1350h+var_1300]
0x18008713f  mov     [rbp+1250h+var_12B0], rcx
0x180087143  mov     [rbp+1250h+var_12A0], rax
0x180087147  lea     rdx, word_1800B2A5E
0x18008714e  mov     eax, dword ptr [rsp+1350h+var_12F0+4]
0x180087152  lea     rcx, dword_1800C3098
0x180087159  mov     [rsp+1350h+var_12FC], eax
0x18008715d  xor     r9d, r9d
0x180087160  lea     rax, [rsp+1350h+var_12FC]
0x180087165  mov     [rbp+1250h+var_1298], r8
0x180087169  mov     [rbp+1250h+var_1290], rax
0x18008716d  lea     rax, [rsp+1350h+var_12E0]
0x180087172  mov     [rbp+1250h+var_1288], r8
0x180087176  xor     r8d, r8d
0x180087179  mov     [rsp+1350h+lpType], rax
0x18008717e  mov     dword ptr [rsp+1350h+phkResult], 6
0x180087186  mov     [rsp+1350h+var_1300], ebx
0x18008718a  call    _tlgWriteTransfer_EventWriteTransfer
0x18008718f  test    esi, esi
0x180087191  mov     rsi, [rsp+1350h+var_12E8]
0x180087196  jnz     short loc_18008719E
0x180087198  inc     r14d
0x18008719b  mov     edi, r13d
0x18008719e  mov     eax, 1000h
0x1800871a3  lea     rcx, [rbp+1250h+Data]; void *
0x1800871aa  mov     r13d, 200h
0x1800871b0  mov     [rsp+1350h+cbData], eax
0x1800871b4  mov     r8d, eax; Size
0x1800871b7  mov     [rsp+1350h+cchValueName], r13d
0x1800871bc  xor     edx, edx; Val
0x1800871be  call    memset_0
0x1800871c3  mov     r8d, r13d; Size
0x1800871c6  lea     rcx, [rbp+1250h+ValueName]; void *
0x1800871ca  xor     edx, edx; Val
0x1800871cc  call    memset_0
0x1800871d1  xor     r13d, r13d
0x1800871d4  mov     edx, edi; dwIndex
0x1800871d6  mov     rcx, [rsp+1350h+hKey]; hKey
0x1800871db  lea     rax, [rsp+1350h+cbData]
0x1800871e0  mov     [rsp+1350h+lpcbData], rax; lpcbData
0x1800871e5  lea     r9, [rsp+1350h+cchValueName]; lpcchValueName
0x1800871ea  lea     rax, [rbp+1250h+Data]
0x1800871f1  mov     [rsp+1350h+lpData], rax; lpData
0x1800871f6  lea     r8, [rbp+1250h+ValueName]; lpValueName
0x1800871fa  lea     rax, [rsp+1350h+Type]
0x1800871ff  mov     [rsp+1350h+lpType], rax; lpType
0x180087204  mov     [rsp+1350h+phkResult], r13; lpReserved
0x180087209  call    cs:__imp_RegEnumValueA
0x18008720f  mov     ecx, eax
0x180087211  cmp     eax, 103h
0x180087216  jnz     loc_180087078
0x18008721c  mov     ebx, r13d
0x18008721f  mov     edi, 4
0x180087224  mov     eax, cs:dword_1800C3098
0x18008722a  cmp     eax, edi
0x18008722c  jbe     loc_1800872C9
0x180087232  lea     rax, [rsp+1350h+var_12FC]
0x180087237  mov     [rsp+1350h+var_1300], ecx
0x18008723b  mov     [rbp+1250h+var_12C0], rax
0x18008723f  lea     rdx, byte_1800B29D9
0x180087246  lea     rax, [rsp+1350h+var_1300]
0x18008724b  mov     [rsp+1350h+var_12FC], ebx
0x18008724f  mov     [rbp+1250h+var_12B0], rax
0x180087253  lea     rcx, dword_1800C3098
0x18008725a  lea     rax, [rsp+1350h+var_1304]
0x18008725f  mov     [rbp+1250h+var_12B8], 4
0x180087267  mov     [rbp+1250h+var_12A0], rax
0x18008726b  xor     r9d, r9d
0x18008726e  lea     rax, [rsp+1350h+var_12E8]
0x180087273  mov     [rbp+1250h+var_12A8], 4
0x18008727b  mov     [rbp+1250h+var_1290], rax
0x18008727f  xor     r8d, r8d
0x180087282  lea     rax, [rsp+1350h+var_12F0]
0x180087287  mov     [rsp+1350h+var_1304], r12d
0x18008728c  mov     [rbp+1250h+var_1280], rax
0x180087290  lea     rax, [rsp+1350h+var_12E0]
0x180087295  mov     [rsp+1350h+lpType], rax
0x18008729a  mov     dword ptr [rsp+1350h+phkResult], 7
0x1800872a2  mov     [rbp+1250h+var_1298], 4
0x1800872aa  mov     dword ptr [rsp+1350h+var_12E8], r14d
0x1800872af  mov     [rbp+1250h+var_1288], 4
0x1800872b7  mov     dword ptr [rsp+1350h+var_12F0], r15d
0x1800872bc  mov     [rbp+1250h+var_1278], 4
0x1800872c4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800872c9  mov     rcx, [rsp+1350h+hKey]; hKey
0x1800872ce  test    rcx, rcx
0x1800872d1  jz      short loc_1800872D9
0x1800872d3  call    cs:__imp_RegCloseKey
0x1800872d9  mov     eax, ebx
0x1800872db  mov     rcx, [rbp+1250h+var_50]
0x1800872e2  xor     rcx, rsp; StackCookie
0x1800872e5  call    __security_check_cookie
0x1800872ea  add     rsp, 1318h
0x1800872f1  pop     r15
0x1800872f3  pop     r14
0x1800872f5  pop     r13
0x1800872f7  pop     r12
0x1800872f9  pop     rdi
0x1800872fa  pop     rsi
0x1800872fb  pop     rbx
0x1800872fc  pop     rbp
0x1800872fd  retn
```
