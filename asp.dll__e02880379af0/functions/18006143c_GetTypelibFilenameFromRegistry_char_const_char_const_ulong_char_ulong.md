# GetTypelibFilenameFromRegistry(char const *,char const *,ulong,char *,ulong)

- ea: `0x18006143c`
- end: `0x180061788`
- name: `?GetTypelibFilenameFromRegistry@@YAJPEBD0KPEADK@Z`
- size: `844`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey, const char *, unsigned int, char *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18005ea94`

## callees

- `0x180023dd0`
- `0x18006143c`

## import_xrefs

- `msvcrt!strtoul` at `0x180061567`
- `msvcrt!strtoul` at `0x18006157c`
- `msvcrt!strtoul` at `0x180061567`
- `msvcrt!strtoul` at `0x18006157c`
- `msvcrt!strchr` at `0x18006154f`
- `msvcrt!strchr` at `0x18006154f`
- `msvcrt!strcpy_s` at `0x1800615a0`
- `msvcrt!strcpy_s` at `0x1800615dc`
- `msvcrt!strcpy_s` at `0x1800615a0`
- `msvcrt!strcpy_s` at `0x1800615dc`
- `msvcrt!_ultoa_s` at `0x18006167a`
- `msvcrt!_ultoa_s` at `0x18006167a`
- `ADVAPI32!RegQueryValueA` at `0x18006171e`
- `ADVAPI32!RegQueryValueA` at `0x18006171e`
- `ADVAPI32!RegEnumKeyA` at `0x180061511`
- `ADVAPI32!RegEnumKeyA` at `0x1800615bd`
- `ADVAPI32!RegEnumKeyA` at `0x180061511`
- `ADVAPI32!RegEnumKeyA` at `0x1800615bd`
- `ADVAPI32!RegCloseKey` at `0x1800614db`
- `ADVAPI32!RegCloseKey` at `0x1800616fa`
- `ADVAPI32!RegCloseKey` at `0x18006172f`
- `ADVAPI32!RegCloseKey` at `0x180061739`
- `ADVAPI32!RegCloseKey` at `0x180061743`
- `ADVAPI32!RegCloseKey` at `0x18006174d`
- `ADVAPI32!RegCloseKey` at `0x1800614db`
- `ADVAPI32!RegCloseKey` at `0x1800616fa`
- `ADVAPI32!RegCloseKey` at `0x18006172f`
- `ADVAPI32!RegCloseKey` at `0x180061739`
- `ADVAPI32!RegCloseKey` at `0x180061743`
- `ADVAPI32!RegCloseKey` at `0x18006174d`
- `ADVAPI32!RegOpenKeyExA` at `0x1800614a3`
- `ADVAPI32!RegOpenKeyExA` at `0x1800614cd`
- `ADVAPI32!RegOpenKeyExA` at `0x18006160d`
- `ADVAPI32!RegOpenKeyExA` at `0x18006169f`
- `ADVAPI32!RegOpenKeyExA` at `0x1800616c3`
- `ADVAPI32!RegOpenKeyExA` at `0x1800616e7`
- `ADVAPI32!RegOpenKeyExA` at `0x1800614a3`
- `ADVAPI32!RegOpenKeyExA` at `0x1800614cd`
- `ADVAPI32!RegOpenKeyExA` at `0x18006160d`
- `ADVAPI32!RegOpenKeyExA` at `0x18006169f`
- `ADVAPI32!RegOpenKeyExA` at `0x1800616c3`
- `ADVAPI32!RegOpenKeyExA` at `0x1800616e7`

## pseudocode

```c
__int64 __fastcall GetTypelibFilenameFromRegistry(LPCSTR lpSubKey, const char *a2, unsigned int a3, char *a4)
{
  int v4; // edi
  int v9; // r14d
  int v10; // r13d
  unsigned int v11; // r12d
  LSTATUS v12; // eax
  char *v13; // rdi
  unsigned int v14; // ebx
  unsigned int v15; // edi
  DWORD v16; // edx
  int v17; // ebx
  unsigned int v18; // ecx
  unsigned int Value; // [rsp+30h] [rbp-51h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-49h] BYREF
  HKEY v21; // [rsp+40h] [rbp-41h] BYREF
  HKEY v22; // [rsp+48h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-31h] BYREF
  HKEY v24; // [rsp+58h] [rbp-29h] BYREF
  CHAR Buffer[16]; // [rsp+60h] [rbp-21h] BYREF
  CHAR Name[16]; // [rsp+70h] [rbp-11h] BYREF
  char Destination[16]; // [rsp+80h] [rbp-1h] BYREF

  v4 = 0;
  Value = a3;
  *a4 = 0;
  hKey = 0;
  phkResult = 0;
  if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, "TypeLib", 0, 0x20019u, &hKey) )
    return 2147500037LL;
  if ( RegOpenKeyExA(hKey, lpSubKey, 0, 0x20019u, &phkResult) )
  {
    RegCloseKey(hKey);
    return 2147500037LL;
  }
  if ( !a2 || (v9 = 1, !*a2) )
    v9 = 0;
  v10 = 1;
  Destination[0] = 0;
  v11 = 0;
  v12 = RegEnumKeyA(phkResult, 0, Name, 0x10u);
  while ( !v12 )
  {
    if ( v9 && strcmp(Name, a2) )
    {
      strcpy_s(Destination, 0x10u, Name);
      break;
    }
    v13 = strchr(Name, 46);
    if ( v13 )
    {
      if ( (v14 = strtoul(Name, 0, 16) << 16, (v15 = v14 | strtoul(v13 + 1, 0, 16)) != 0) && !Destination[0]
        || v15 > v11 )
      {
        strcpy_s(Destination, 0x10u, Name);
        v11 = v15;
      }
    }
    v16 = v10++;
    v12 = RegEnumKeyA(phkResult, v16, Name, 0x10u);
    v4 = 0;
  }
  if ( Destination[0] )
  {
    v24 = 0;
    if ( !RegOpenKeyExA(phkResult, Destination, 0, 0x20019u, &v24) )
    {
      v22 = 0;
      v17 = 1;
      while ( 1 )
      {
        if ( v17 > 3 )
        {
LABEL_42:
          RegCloseKey(v24);
          goto LABEL_43;
        }
        if ( v17 == 1 )
          break;
        if ( v17 != 2 )
        {
          if ( v17 == 3 )
            strcpy(Buffer, "0");
LABEL_33:
          v21 = 0;
          if ( !RegOpenKeyExA(v24, Buffer, 0, 0x20019u, &v21) )
          {
            if ( !RegOpenKeyExA(v21, "win64", 0, 0x20019u, &v22) || !RegOpenKeyExA(v21, "win32", 0, 0x20019u, &v22) )
              v4 = 1;
            RegCloseKey(v21);
          }
          goto LABEL_38;
        }
        if ( Value )
        {
          v18 = Value & 0x3FF;
LABEL_32:
          if ( !_ultoa_s(v18, Buffer, 0xAu, 16) )
            goto LABEL_33;
        }
LABEL_38:
        ++v17;
        if ( v4 )
        {
          Value = 260;
          if ( RegQueryValueA(v22, 0, a4, (PLONG)&Value) )
            *a4 = 0;
          RegCloseKey(v22);
          goto LABEL_42;
        }
      }
      if ( !Value )
        goto LABEL_38;
      v18 = Value;
      goto LABEL_32;
    }
  }
LABEL_43:
  RegCloseKey(phkResult);
  RegCloseKey(hKey);
  return *a4 == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18006143c  mov     [rsp-8+arg_8], rbx
0x180061441  push    rbp
0x180061442  push    rsi
0x180061443  push    rdi
0x180061444  push    r12
0x180061446  push    r13
0x180061448  push    r14
0x18006144a  push    r15
0x18006144c  lea     rbp, [rsp-1Fh]
0x180061451  sub     rsp, 0A0h
0x180061458  mov     rax, cs:__security_cookie
0x18006145f  xor     rax, rsp
0x180061462  mov     [rbp+4Fh+var_40], rax
0x180061466  xor     edi, edi
0x180061468  mov     [rbp+4Fh+Value], r8d
0x18006146c  mov     [r9], dil
0x18006146f  lea     rax, [rbp+4Fh+hKey]
0x180061473  mov     r15, r9
0x180061476  mov     [rbp+4Fh+hKey], rdi
0x18006147a  mov     rsi, rdx
0x18006147d  mov     [rbp+4Fh+var_98], rdi
0x180061481  mov     rbx, rcx
0x180061484  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180061489  mov     r14d, 20019h
0x18006148f  lea     rdx, aTypelib_0; "TypeLib"
0x180061496  mov     r9d, r14d; samDesired
0x180061499  xor     r8d, r8d; ulOptions
0x18006149c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800614a3  call    cs:__imp_RegOpenKeyExA
0x1800614a9  test    eax, eax
0x1800614ab  jz      short loc_1800614B7
0x1800614ad  mov     eax, 80004005h
0x1800614b2  jmp     loc_180061761
0x1800614b7  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800614bb  lea     rax, [rbp+4Fh+var_98]
0x1800614bf  mov     r9d, r14d; samDesired
0x1800614c2  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800614c7  xor     r8d, r8d; ulOptions
0x1800614ca  mov     rdx, rbx; lpSubKey
0x1800614cd  call    cs:__imp_RegOpenKeyExA
0x1800614d3  test    eax, eax
0x1800614d5  jz      short loc_1800614E3
0x1800614d7  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800614db  call    cs:__imp_RegCloseKey
0x1800614e1  jmp     short loc_1800614AD
0x1800614e3  test    rsi, rsi
0x1800614e6  jz      short loc_1800614F3
0x1800614e8  mov     r14d, 1
0x1800614ee  cmp     [rsi], dil
0x1800614f1  jnz     short loc_1800614F6
0x1800614f3  mov     r14d, edi
0x1800614f6  mov     rcx, [rbp+4Fh+var_98]; hKey
0x1800614fa  lea     r8, [rbp+4Fh+Name]; lpName
0x1800614fe  mov     r13d, 1
0x180061504  mov     [rbp+4Fh+Destination], dil
0x180061508  xor     edx, edx; dwIndex
0x18006150a  mov     r12d, edi
0x18006150d  lea     r9d, [r13+0Fh]; cchName
0x180061511  call    cs:__imp_RegEnumKeyA
0x180061517  jmp     loc_1800615C5
0x18006151c  test    r14d, r14d
0x18006151f  jz      short loc_180061546
0x180061521  lea     rax, [rbp+4Fh+Name]
0x180061525  mov     r8, rsi
0x180061528  sub     r8, rax
0x18006152b  movzx   ecx, byte ptr [rax]
0x18006152e  movzx   edx, byte ptr [rax+r8]
0x180061533  sub     ecx, edx
0x180061535  jnz     short loc_18006153E
0x180061537  inc     rax
0x18006153a  test    edx, edx
0x18006153c  jnz     short loc_18006152B
0x18006153e  test    ecx, ecx
0x180061540  jnz     loc_1800615CF
0x180061546  mov     edx, 2Eh ; '.'; Val
0x18006154b  lea     rcx, [rbp+4Fh+Name]; Str
0x18006154f  call    cs:__imp_strchr
0x180061555  mov     rdi, rax
0x180061558  test    rax, rax
0x18006155b  jz      short loc_1800615A9
0x18006155d  xor     edx, edx; EndPtr
0x18006155f  lea     rcx, [rbp+4Fh+Name]; String
0x180061563  lea     r8d, [rdx+10h]; Radix
0x180061567  call    cs:__imp_strtoul
0x18006156d  xor     edx, edx; EndPtr
0x18006156f  lea     rcx, [rdi+1]; String
0x180061573  mov     ebx, eax
0x180061575  shl     ebx, 10h
0x180061578  lea     r8d, [rdx+10h]; Radix
0x18006157c  call    cs:__imp_strtoul
0x180061582  mov     edi, eax
0x180061584  or      edi, ebx
0x180061586  jz      short loc_18006158E
0x180061588  cmp     [rbp+4Fh+Destination], 0
0x18006158c  jz      short loc_180061593
0x18006158e  cmp     edi, r12d
0x180061591  jbe     short loc_1800615A9
0x180061593  lea     r8, [rbp+4Fh+Name]; Source
0x180061597  mov     edx, 10h; SizeInBytes
0x18006159c  lea     rcx, [rbp+4Fh+Destination]; Destination
0x1800615a0  call    cs:__imp_strcpy_s
0x1800615a6  mov     r12d, edi
0x1800615a9  mov     rcx, [rbp+4Fh+var_98]; hKey
0x1800615ad  lea     r8, [rbp+4Fh+Name]; lpName
0x1800615b1  mov     edx, r13d; dwIndex
0x1800615b4  mov     r9d, 10h; cchName
0x1800615ba  inc     r13d
0x1800615bd  call    cs:__imp_RegEnumKeyA
0x1800615c3  xor     edi, edi
0x1800615c5  test    eax, eax
0x1800615c7  jz      loc_18006151C
0x1800615cd  jmp     short loc_1800615E2
0x1800615cf  lea     r8, [rbp+4Fh+Name]; Source
0x1800615d3  mov     edx, 10h; SizeInBytes
0x1800615d8  lea     rcx, [rbp+4Fh+Destination]; Destination
0x1800615dc  call    cs:__imp_strcpy_s
0x1800615e2  cmp     [rbp+4Fh+Destination], dil
0x1800615e6  jz      loc_18006173F
0x1800615ec  mov     rcx, [rbp+4Fh+var_98]; hKey
0x1800615f0  lea     rax, [rbp+4Fh+var_78]
0x1800615f4  mov     r14d, 20019h
0x1800615fa  mov     [rbp+4Fh+var_78], rdi
0x1800615fe  mov     r9d, r14d; samDesired
0x180061601  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180061606  xor     r8d, r8d; ulOptions
0x180061609  lea     rdx, [rbp+4Fh+Destination]; lpSubKey
0x18006160d  call    cs:__imp_RegOpenKeyExA
0x180061613  test    eax, eax
0x180061615  jnz     loc_18006173F
0x18006161b  mov     [rbp+4Fh+var_88], rdi
0x18006161f  lea     ebx, [rax+1]
0x180061622  xor     esi, esi
0x180061624  lea     r12d, [rax+0Ah]
0x180061628  cmp     ebx, 3
0x18006162b  jg      loc_180061735
0x180061631  mov     ecx, ebx
0x180061633  sub     ecx, 1
0x180061636  jz      short loc_180061660
0x180061638  sub     ecx, 1
0x18006163b  jz      short loc_18006164A
0x18006163d  cmp     ecx, 1
0x180061640  jnz     short loc_180061684
0x180061642  mov     word ptr [rbp+4Fh+Buffer], 30h ; '0'
0x180061648  jmp     short loc_180061684
0x18006164a  mov     eax, [rbp+4Fh+Value]
0x18006164d  test    eax, eax
0x18006164f  jz      loc_180061700
0x180061655  movzx   ecx, ax
0x180061658  and     ecx, 3FFh
0x18006165e  jmp     short loc_18006166D
0x180061660  mov     eax, [rbp+4Fh+Value]
0x180061663  test    eax, eax
0x180061665  jz      loc_180061700
0x18006166b  mov     ecx, eax; Value
0x18006166d  mov     r9d, 10h; Radix
0x180061673  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x180061677  mov     r8, r12; BufferCount
0x18006167a  call    cs:__imp__ultoa_s
0x180061680  test    eax, eax
0x180061682  jnz     short loc_180061700
0x180061684  mov     rcx, [rbp+4Fh+var_78]; hKey
0x180061688  lea     rax, [rbp+4Fh+var_90]
0x18006168c  mov     r9d, r14d; samDesired
0x18006168f  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180061694  xor     r8d, r8d; ulOptions
0x180061697  mov     [rbp+4Fh+var_90], rsi
0x18006169b  lea     rdx, [rbp+4Fh+Buffer]; lpSubKey
0x18006169f  call    cs:__imp_RegOpenKeyExA
0x1800616a5  test    eax, eax
0x1800616a7  jnz     short loc_180061700
0x1800616a9  mov     rcx, [rbp+4Fh+var_90]; hKey
0x1800616ad  lea     rax, [rbp+4Fh+var_88]
0x1800616b1  mov     r9d, r14d; samDesired
0x1800616b4  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800616b9  xor     r8d, r8d; ulOptions
0x1800616bc  lea     rdx, aWin64; "win64"
0x1800616c3  call    cs:__imp_RegOpenKeyExA
0x1800616c9  test    eax, eax
0x1800616cb  jz      short loc_1800616F1
0x1800616cd  mov     rcx, [rbp+4Fh+var_90]; hKey
0x1800616d1  lea     rax, [rbp+4Fh+var_88]
0x1800616d5  mov     r9d, r14d; samDesired
0x1800616d8  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800616dd  xor     r8d, r8d; ulOptions
0x1800616e0  lea     rdx, aWin32; "win32"
0x1800616e7  call    cs:__imp_RegOpenKeyExA
0x1800616ed  test    eax, eax
0x1800616ef  jnz     short loc_1800616F6
0x1800616f1  mov     edi, 1
0x1800616f6  mov     rcx, [rbp+4Fh+var_90]; hKey
0x1800616fa  call    cs:__imp_RegCloseKey
0x180061700  inc     ebx
0x180061702  test    edi, edi
0x180061704  jz      loc_180061628
0x18006170a  mov     rcx, [rbp+4Fh+var_88]; hKey
0x18006170e  lea     r9, [rbp+4Fh+Value]; lpcbData
0x180061712  mov     r8, r15; lpData
0x180061715  mov     [rbp+4Fh+Value], 104h
0x18006171c  xor     edx, edx; lpSubKey
0x18006171e  call    cs:__imp_RegQueryValueA
0x180061724  test    eax, eax
0x180061726  jz      short loc_18006172B
0x180061728  mov     [r15], sil
0x18006172b  mov     rcx, [rbp+4Fh+var_88]; hKey
0x18006172f  call    cs:__imp_RegCloseKey
0x180061735  mov     rcx, [rbp+4Fh+var_78]; hKey
0x180061739  call    cs:__imp_RegCloseKey
0x18006173f  mov     rcx, [rbp+4Fh+var_98]; hKey
0x180061743  call    cs:__imp_RegCloseKey
0x180061749  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18006174d  call    cs:__imp_RegCloseKey
0x180061753  mov     al, [r15]
0x180061756  neg     al
0x180061758  sbb     eax, eax
0x18006175a  not     eax
0x18006175c  and     eax, 80004005h
0x180061761  mov     rcx, [rbp+4Fh+var_40]
0x180061765  xor     rcx, rsp; StackCookie
0x180061768  call    __security_check_cookie
0x18006176d  mov     rbx, [rsp+0D0h+arg_8]
0x180061775  add     rsp, 0A0h
0x18006177c  pop     r15
0x18006177e  pop     r14
0x180061780  pop     r13
0x180061782  pop     r12
0x180061784  pop     rdi
0x180061785  pop     rsi
0x180061786  pop     rbp
0x180061787  retn
```
