# IsBootstrapEnabled(void)

- ea: `0x1800acf14`
- end: `0x1800ad179`
- name: `?IsBootstrapEnabled@@YAEXZ`
- size: `613`
- prototype: `unsigned __int8(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800accf4`

## callees

- `0x1800acf14`
- `0x1801ba1b0`

## import_xrefs

- `msvcrt!fclose` at `0x1800ad13a`
- `msvcrt!fclose` at `0x1800ad13a`
- `msvcrt!fopen_s` at `0x1800ad124`
- `msvcrt!fopen_s` at `0x1800ad124`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800acfbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800acfbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800acfb2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800acfb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800acf7c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800acf7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x1800ad008`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x1800ad008`

## string_xrefs

- `0x1800acfcd`: `MetaConfig.mof`
- `0x1800ad04f`: `\Configuration\`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int8 IsBootstrapEnabled(void)
{
  LSTATUS v0; // ebx
  __int64 v1; // rdx
  CHAR *v2; // rax
  __int64 v3; // r8
  const char *v4; // r9
  __int64 v5; // rax
  CHAR *v6; // rdx
  __int64 v7; // rcx
  CHAR *v8; // rax
  __int64 v9; // rdi
  unsigned int i; // ebx
  unsigned __int64 v11; // rcx
  CHAR *v12; // rdx
  __int64 v13; // r8
  CHAR *v14; // r9
  CHAR *v15; // rax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  FILE *Stream; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v22[4]; // [rsp+50h] [rbp-B0h]
  CHAR Buffer[272]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
          0,
          0x101u,
          &hKey) )
  {
    v0 = RegQueryValueExW(hKey, L"DSCAutomationHostEnabled", 0, &Type, Data, &cbData);
    RegCloseKey(hKey);
    if ( v0 )
      goto LABEL_3;
    if ( *(_DWORD *)Data == 1 )
      return 1;
    if ( *(_DWORD *)Data )
    {
LABEL_3:
      Stream = 0;
      v22[0] = "MetaConfig.mof";
      v22[1] = "Pending.mof";
      v22[2] = "Current.mof";
      if ( GetSystemDirectoryA(Buffer, 0x104u) )
      {
        v1 = 260;
        v2 = Buffer;
        do
        {
          if ( !*v2 )
            break;
          ++v2;
          --v1;
        }
        while ( v1 );
        v3 = (260 - v1) & -(__int64)(v1 != 0);
        if ( v1 )
        {
          v4 = "\\Configuration\\";
          v5 = 2147483646;
          v6 = &Buffer[v3];
          v7 = 260 - v3;
          if ( v3 != 260 )
          {
            do
            {
              if ( !v5 )
                break;
              if ( !*v4 )
                break;
              *v6++ = *v4++;
              --v5;
              --v7;
            }
            while ( v7 );
          }
          v8 = v6 - 1;
          if ( v7 )
            v8 = v6;
          *v8 = 0;
          if ( v7 )
          {
            v9 = -1;
            do
              ++v9;
            while ( Buffer[v9] );
            for ( i = 0; i < 3; ++i )
            {
              v11 = 260LL - (int)v9;
              if ( (int)v9 == 260 )
                break;
              v12 = &Buffer[(int)v9];
              if ( v11 > 0x7FFFFFFF )
              {
                *v12 = 0;
                return 0;
              }
              v13 = 2147483646;
              v14 = (CHAR *)v22[i];
              do
              {
                if ( !v13 )
                  break;
                if ( !*v14 )
                  break;
                *v12++ = *v14++;
                --v13;
                --v11;
              }
              while ( v11 );
              v15 = v12 - 1;
              if ( v11 )
                v15 = v12;
              *v15 = 0;
              if ( !v11 )
                return 0;
              if ( !fopen_s(&Stream, Buffer, "r") )
              {
                fclose(Stream);
                return 1;
              }
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800acf14  push    rbp
0x1800acf16  push    rbx
0x1800acf17  push    rdi
0x1800acf18  push    r15
0x1800acf1a  lea     rbp, [rsp-98h]
0x1800acf22  sub     rsp, 198h
0x1800acf29  mov     rax, cs:__security_cookie
0x1800acf30  xor     rax, rsp
0x1800acf33  mov     [rbp+0B0h+var_30], rax
0x1800acf3a  lea     rax, [rsp+1B0h+hKey]
0x1800acf3f  mov     [rsp+1B0h+hKey], 0
0x1800acf48  mov     r9d, 101h; samDesired
0x1800acf4e  mov     [rsp+1B0h+phkResult], rax; phkResult
0x1800acf53  xor     r8d, r8d; ulOptions
0x1800acf56  mov     dword ptr [rsp+1B0h+Data], 0
0x1800acf5e  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800acf65  mov     [rsp+1B0h+cbData], 4
0x1800acf6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800acf74  mov     [rsp+1B0h+Type], 0
0x1800acf7c  call    cs:__imp_RegOpenKeyExW
0x1800acf82  test    eax, eax
0x1800acf84  jnz     loc_1800AD15E
0x1800acf8a  mov     rcx, [rsp+1B0h+hKey]; hKey
0x1800acf8f  lea     rax, [rsp+1B0h+cbData]
0x1800acf94  mov     [rsp+1B0h+lpcbData], rax; lpcbData
0x1800acf99  lea     r9, [rsp+1B0h+Type]; lpType
0x1800acf9e  lea     rax, [rsp+1B0h+Data]
0x1800acfa3  xor     r8d, r8d; lpReserved
0x1800acfa6  lea     rdx, aDscautomationh; "DSCAutomationHostEnabled"
0x1800acfad  mov     [rsp+1B0h+phkResult], rax; lpData
0x1800acfb2  call    cs:__imp_RegQueryValueExW
0x1800acfb8  mov     rcx, [rsp+1B0h+hKey]; hKey
0x1800acfbd  mov     ebx, eax
0x1800acfbf  call    cs:__imp_RegCloseKey
0x1800acfc5  test    ebx, ebx
0x1800acfc7  jz      loc_1800AD162
0x1800acfcd  lea     rax, aMetaconfigMof; "MetaConfig.mof"
0x1800acfd4  mov     [rsp+1B0h+Stream], 0
0x1800acfdd  mov     [rsp+1B0h+var_160], rax
0x1800acfe2  lea     rcx, [rsp+1B0h+Buffer]; lpBuffer
0x1800acfe7  lea     rax, aPendingMof; "Pending.mof"
0x1800acfee  mov     r15d, 104h
0x1800acff4  mov     [rsp+1B0h+var_158], rax
0x1800acff9  mov     edx, r15d; uSize
0x1800acffc  lea     rax, aCurrentMof; "Current.mof"
0x1800ad003  mov     [rsp+1B0h+var_150], rax
0x1800ad008  call    cs:__imp_GetSystemDirectoryA
0x1800ad00e  test    eax, eax
0x1800ad010  jz      loc_1800AD15E
0x1800ad016  mov     edx, r15d
0x1800ad019  lea     rax, [rsp+1B0h+Buffer]
0x1800ad01e  cmp     byte ptr [rax], 0
0x1800ad021  jz      short loc_1800AD02C
0x1800ad023  inc     rax
0x1800ad026  sub     rdx, 1
0x1800ad02a  jnz     short loc_1800AD01E
0x1800ad02c  mov     rcx, r15
0x1800ad02f  mov     rax, rdx
0x1800ad032  sub     rcx, rdx
0x1800ad035  neg     rax
0x1800ad038  sbb     r8, r8
0x1800ad03b  and     r8, rcx
0x1800ad03e  test    rdx, rdx
0x1800ad041  jz      loc_1800AD15E
0x1800ad047  mov     rcx, r15
0x1800ad04a  lea     rdx, [rsp+1B0h+Buffer]
0x1800ad04f  lea     r9, aConfiguration; "\\Configuration\\"
0x1800ad056  mov     eax, 7FFFFFFEh
0x1800ad05b  lea     rdx, [rdx+r8]
0x1800ad05f  sub     rcx, r8
0x1800ad062  jz      short loc_1800AD083
0x1800ad064  test    rax, rax
0x1800ad067  jz      short loc_1800AD083
0x1800ad069  mov     r8b, [r9]
0x1800ad06c  test    r8b, r8b
0x1800ad06f  jz      short loc_1800AD083
0x1800ad071  mov     [rdx], r8b
0x1800ad074  inc     r9
0x1800ad077  inc     rdx
0x1800ad07a  dec     rax
0x1800ad07d  sub     rcx, 1
0x1800ad081  jnz     short loc_1800AD064
0x1800ad083  test    rcx, rcx
0x1800ad086  lea     rax, [rdx-1]
0x1800ad08a  cmovnz  rax, rdx
0x1800ad08e  mov     byte ptr [rax], 0
0x1800ad091  jz      loc_1800AD15E
0x1800ad097  lea     rax, [rsp+1B0h+Buffer]
0x1800ad09c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800ad0a0  inc     rdi
0x1800ad0a3  cmp     byte ptr [rax+rdi], 0
0x1800ad0a7  jnz     short loc_1800AD0A0
0x1800ad0a9  xor     ebx, ebx
0x1800ad0ab  cmp     ebx, 3
0x1800ad0ae  jnb     loc_1800AD15E
0x1800ad0b4  movsxd  rax, edi
0x1800ad0b7  mov     rcx, r15
0x1800ad0ba  sub     rcx, rax
0x1800ad0bd  jz      loc_1800AD15E
0x1800ad0c3  lea     rdx, [rsp+1B0h+Buffer]
0x1800ad0c8  add     rdx, rax
0x1800ad0cb  cmp     rcx, 7FFFFFFFh
0x1800ad0d2  ja      loc_1800AD174
0x1800ad0d8  movsxd  rax, ebx
0x1800ad0db  mov     r8d, 7FFFFFFEh
0x1800ad0e1  mov     r9, [rsp+rax*8+1B0h+var_160]
0x1800ad0e6  test    r8, r8
0x1800ad0e9  jz      short loc_1800AD103
0x1800ad0eb  mov     al, [r9]
0x1800ad0ee  test    al, al
0x1800ad0f0  jz      short loc_1800AD103
0x1800ad0f2  mov     [rdx], al
0x1800ad0f4  inc     r9
0x1800ad0f7  inc     rdx
0x1800ad0fa  dec     r8
0x1800ad0fd  sub     rcx, 1
0x1800ad101  jnz     short loc_1800AD0E6
0x1800ad103  test    rcx, rcx
0x1800ad106  lea     rax, [rdx-1]
0x1800ad10a  cmovnz  rax, rdx
0x1800ad10e  mov     byte ptr [rax], 0
0x1800ad111  jz      short loc_1800AD15E
0x1800ad113  lea     r8, Mode; "r"
0x1800ad11a  lea     rdx, [rsp+1B0h+Buffer]; FileName
0x1800ad11f  lea     rcx, [rsp+1B0h+Stream]; Stream
0x1800ad124  call    cs:__imp_fopen_s
0x1800ad12a  test    eax, eax
0x1800ad12c  jz      short loc_1800AD135
0x1800ad12e  inc     ebx
0x1800ad130  jmp     loc_1800AD0AB
0x1800ad135  mov     rcx, [rsp+1B0h+Stream]; Stream
0x1800ad13a  call    cs:__imp_fclose
0x1800ad140  mov     al, 1
0x1800ad142  mov     rcx, [rbp+0B0h+var_30]
0x1800ad149  xor     rcx, rsp; StackCookie
0x1800ad14c  call    __security_check_cookie
0x1800ad151  add     rsp, 198h
0x1800ad158  pop     r15
0x1800ad15a  pop     rdi
0x1800ad15b  pop     rbx
0x1800ad15c  pop     rbp
0x1800ad15d  retn
0x1800ad15e  xor     al, al
0x1800ad160  jmp     short loc_1800AD142
0x1800ad162  mov     ecx, dword ptr [rsp+1B0h+Data]
0x1800ad166  cmp     ecx, 1
0x1800ad169  jz      short loc_1800AD140
0x1800ad16b  test    ecx, ecx
0x1800ad16d  jz      short loc_1800AD15E
0x1800ad16f  jmp     loc_1800ACFCD
0x1800ad174  mov     byte ptr [rdx], 0
0x1800ad177  jmp     short loc_1800AD15E
```
