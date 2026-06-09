# VcommsCheck::checkHostName(HWND__ *,char,ulong *)

- ea: `0x180017800`
- end: `0x180017acf`
- name: `?checkHostName@VcommsCheck@@QEAAPEBDPEAUHWND__@@DPEAK@Z`
- size: `719`
- prototype: `const char *__fastcall(VcommsCheck *__hidden this, HWND, char, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180017800`
- `0x180017ad0`
- `0x180017ba4`
- `0x18004d894`
- `0x1800838f0`
- `0x180133d30`
- `0x180133fd0`
- `0x1801342d0`
- `0x1801503e0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x180017862`
- `ADVAPI32!RegOpenKeyExA` at `0x180017862`
- `ADVAPI32!RegQueryValueExA` at `0x1800178d0`
- `ADVAPI32!RegQueryValueExA` at `0x1800178d0`
- `ADVAPI32!RegCloseKey` at `0x1800178db`
- `ADVAPI32!RegCloseKey` at `0x1800178db`
- `ADVAPI32!RegEnumKeyA` at `0x180017887`
- `ADVAPI32!RegEnumKeyA` at `0x180017887`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180017969`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800179ab`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180017a26`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180017a6e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180017969`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800179ab`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180017a26`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180017a6e`

## string_xrefs

- `0x180017903`: `\Microsoft\Shared Tools\Web Server Extensions`
- `0x1800179cb`: `\Microsoft\Shared Tools\Web Server Extensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
const char *__fastcall VcommsCheck::checkHostName(VcommsCheck *this, HWND a2, char a3, unsigned int *a4)
{
  __int64 v6; // rdx
  DWORD v7; // ebx
  char v8; // di
  char *v10; // rbx
  __int64 v11; // r8
  char *v12; // rcx
  signed __int32 v13; // eax
  int *v14; // rcx
  char v15; // al
  char *v16; // rbx
  __int64 v17; // r8
  char *v18; // rcx
  int *v19; // rcx
  __int64 v20; // rbx
  __int64 v22; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C8h] BYREF
  BYTE Data[4]; // [rsp+48h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-BCh] BYREF
  DWORD Type[2]; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  char *v28; // [rsp+60h] [rbp-A8h] BYREF
  char *v29[2]; // [rsp+68h] [rbp-A0h] BYREF
  CHAR Name[1024]; // [rsp+78h] [rbp-90h] BYREF

  v29[1] = (char *)-2LL;
  if ( RegOpenKeyExA(
         HKEY_CURRENT_USER,
         "Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
         0,
         0x20019u,
         &hKey) )
  {
    goto LABEL_31;
  }
  v7 = 0;
  v8 = 1;
  while ( !RegEnumKeyA(hKey, v7++, Name, 0x400u) )
    ;
  *(_DWORD *)Data = 0;
  cbData = 4;
  Type[0] = 3;
  RegQueryValueExA(hKey, "EnableAutodial", 0, Type, Data, &cbData);
  RegCloseKey(hKey);
  if ( !*(_DWORD *)Data )
    goto LABEL_31;
  RWCString::RWCString((RWCString *)&v23, "SOFTWARE\\Policies");
  RWCString::RWCString((RWCString *)&v28, "\\Microsoft\\Shared Tools\\Web Server Extensions");
  v10 = v28;
  RWCString::replace((RWCString *)&v23, *(_DWORD *)(v23 - 4), 0, v28, *((_DWORD *)v28 - 1));
  v12 = v10 - 12;
  v13 = _InterlockedDecrement((volatile signed __int32 *)v10 - 3);
  if ( !v13 && v12 != (char *)&dword_1802AFD50 )
  {
    if ( dword_1802B0018 == v13 )
      free(v12);
    else
      COWSAllocator::Free(v12);
  }
  if ( (unsigned __int8)sub_18004D894(v12, v23, v11, &v22) )
    goto LABEL_11;
  RWCString::operator=((RWCString *)&v23, "SOFTWARE");
  RWCString::RWCString((RWCString *)v29, "\\Microsoft\\Shared Tools\\Web Server Extensions");
  v16 = v29[0];
  RWCString::replace((RWCString *)&v23, *(_DWORD *)(v23 - 4), 0, v29[0], *((_DWORD *)v29[0] - 1));
  v18 = v16 - 12;
  if ( !_InterlockedDecrement((volatile signed __int32 *)v16 - 3) && v18 != (char *)&dword_1802AFD50 )
  {
    if ( dword_1802B0018 )
      COWSAllocator::Free(v18);
    else
      free(v18);
  }
  if ( (unsigned __int8)sub_18004D894(v18, v23, v17, &v22) )
  {
LABEL_11:
    v14 = (int *)(v23 - 12);
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v23 - 12)) && v14 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v14);
      else
        free(v14);
    }
    v15 = v22;
  }
  else
  {
    v19 = (int *)(v23 - 12);
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v23 - 12)) && v19 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v19);
      else
        free(v19);
    }
    v15 = 0;
  }
  if ( v15 )
LABEL_31:
    v8 = 0;
  else
    sub_180017AD0(0);
  LOBYTE(v6) = a3;
  v20 = sub_180017BA4(this, v6);
  if ( v8 )
    sub_180017AD0(v8);
  return (const char *)v20;
}

```

## disassembly

```asm
0x180017800  mov     rax, rsp
0x180017803  push    rbp
0x180017804  push    rdi
0x180017805  push    r12
0x180017807  push    r13
0x180017809  push    r14
0x18001780b  lea     rbp, [rax-3A8h]
0x180017812  sub     rsp, 480h
0x180017819  mov     qword ptr [rsp+4A0h+var_438], 0FFFFFFFFFFFFFFFEh
0x180017822  mov     [rax+10h], rbx
0x180017826  mov     [rax+18h], rsi
0x18001782a  mov     rax, cs:__security_cookie
0x180017831  xor     rax, rsp
0x180017834  mov     [rbp+3A0h+var_30], rax
0x18001783b  mov     sil, r8b
0x18001783e  mov     r14, rcx
0x180017841  lea     rax, [rsp+4A0h+hKey]
0x180017846  mov     [rsp+4A0h+phkResult], rax; phkResult
0x18001784b  mov     r9d, 20019h; samDesired
0x180017851  xor     r8d, r8d; ulOptions
0x180017854  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001785b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180017862  call    cs:RegOpenKeyExA
0x180017868  test    eax, eax
0x18001786a  jnz     loc_180017A83
0x180017870  xor     ebx, ebx
0x180017872  lea     edi, [rax+1]
0x180017875  mov     r9d, 400h; cchName
0x18001787b  lea     r8, [rsp+4A0h+Name]; lpName
0x180017880  mov     edx, ebx; dwIndex
0x180017882  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180017887  call    cs:RegEnumKeyA
0x18001788d  add     ebx, edi
0x18001788f  test    eax, eax
0x180017891  jz      short loc_180017875
0x180017893  and     dword ptr [rsp+4A0h+Data], 0
0x180017898  mov     [rsp+4A0h+cbData], 4
0x1800178a0  mov     [rsp+4A0h+Type], 3
0x1800178a8  lea     rax, [rsp+4A0h+cbData]
0x1800178ad  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x1800178b2  lea     rax, [rsp+4A0h+Data]
0x1800178b7  mov     [rsp+4A0h+phkResult], rax; lpData
0x1800178bc  lea     r9, [rsp+4A0h+Type]; lpType
0x1800178c1  xor     r8d, r8d; lpReserved
0x1800178c4  lea     rdx, aEnableautodial; "EnableAutodial"
0x1800178cb  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800178d0  call    cs:RegQueryValueExA
0x1800178d6  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800178db  call    cs:RegCloseKey
0x1800178e1  cmp     dword ptr [rsp+4A0h+Data], 0
0x1800178e6  setnz   al
0x1800178e9  test    al, al
0x1800178eb  jz      loc_180017A83
0x1800178f1  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies"
0x1800178f8  lea     rcx, [rsp+4A0h+var_468]; this
0x1800178fd  call    ??0RWCString@@QEAA@PEBD@Z; RWCString::RWCString(char const *)
0x180017902  nop
0x180017903  lea     rdx, aMicrosoftShare; "\\Microsoft\\Shared Tools\\Web Server E"...
0x18001790a  lea     rcx, [rsp+4A0h+var_448]; this
0x18001790f  call    ??0RWCString@@QEAA@PEBD@Z; RWCString::RWCString(char const *)
0x180017914  nop
0x180017915  mov     rbx, [rsp+4A0h+var_448]
0x18001791a  mov     ecx, [rbx-4]
0x18001791d  mov     rax, [rsp+4A0h+var_468]
0x180017922  mov     dword ptr [rsp+4A0h+phkResult], ecx; unsigned int
0x180017926  mov     r9, rbx; char *
0x180017929  xor     r8d, r8d; unsigned int
0x18001792c  mov     edx, [rax-4]; unsigned int
0x18001792f  lea     rcx, [rsp+4A0h+var_468]; this
0x180017934  call    ?replace@RWCString@@QEAAAEAV1@IIPEBDI@Z; RWCString::replace(uint,uint,char const *,uint)
0x180017939  nop
0x18001793a  lea     rcx, [rbx-0Ch]; void *
0x18001793e  or      r12d, 0FFFFFFFFh
0x180017942  mov     eax, r12d
0x180017945  lock xadd [rcx], eax
0x180017949  lea     r13, dword_1802AFD50
0x180017950  add     eax, r12d
0x180017953  jnz     short loc_18001796F
0x180017955  cmp     rcx, r13
0x180017958  jz      short loc_18001796F
0x18001795a  cmp     cs:dword_1802B0018, eax
0x180017960  jz      short loc_180017969
0x180017962  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x180017967  jmp     short loc_18001796F
0x180017969  call    cs:free
0x18001796f  lea     r9, [rsp+4A0h+var_470]
0x180017974  mov     rdx, [rsp+4A0h+var_468]
0x180017979  call    sub_18004D894
0x18001797e  test    al, al
0x180017980  jz      short loc_1800179BA
0x180017982  mov     rcx, [rsp+4A0h+var_468]
0x180017987  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18001798b  mov     eax, r12d
0x18001798e  lock xadd [rcx], eax
0x180017992  add     eax, r12d
0x180017995  jnz     short loc_1800179B1
0x180017997  cmp     rcx, r13
0x18001799a  jz      short loc_1800179B1
0x18001799c  cmp     cs:dword_1802B0018, eax
0x1800179a2  jz      short loc_1800179AB
0x1800179a4  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800179a9  jmp     short loc_1800179B1
0x1800179ab  call    cs:free
0x1800179b1  mov     al, byte ptr [rsp+4A0h+var_470]
0x1800179b5  jmp     loc_180017A76
0x1800179ba  lea     rdx, aSoftware; "SOFTWARE"
0x1800179c1  lea     rcx, [rsp+4A0h+var_468]; this
0x1800179c6  call    ??4RWCString@@QEAAAEAV0@PEBD@Z; RWCString::operator=(char const *)
0x1800179cb  lea     rdx, aMicrosoftShare; "\\Microsoft\\Shared Tools\\Web Server E"...
0x1800179d2  lea     rcx, [rsp+4A0h+var_440]; this
0x1800179d7  call    ??0RWCString@@QEAA@PEBD@Z; RWCString::RWCString(char const *)
0x1800179dc  nop
0x1800179dd  mov     rbx, [rsp+4A0h+var_440]
0x1800179e2  mov     ecx, [rbx-4]
0x1800179e5  mov     rax, [rsp+4A0h+var_468]
0x1800179ea  mov     dword ptr [rsp+4A0h+phkResult], ecx; unsigned int
0x1800179ee  mov     r9, rbx; char *
0x1800179f1  xor     r8d, r8d; unsigned int
0x1800179f4  mov     edx, [rax-4]; unsigned int
0x1800179f7  lea     rcx, [rsp+4A0h+var_468]; this
0x1800179fc  call    ?replace@RWCString@@QEAAAEAV1@IIPEBDI@Z; RWCString::replace(uint,uint,char const *,uint)
0x180017a01  nop
0x180017a02  lea     rcx, [rbx-0Ch]; void *
0x180017a06  mov     eax, r12d
0x180017a09  lock xadd [rcx], eax
0x180017a0d  add     eax, r12d
0x180017a10  jnz     short loc_180017A2C
0x180017a12  cmp     rcx, r13
0x180017a15  jz      short loc_180017A2C
0x180017a17  cmp     cs:dword_1802B0018, eax
0x180017a1d  jz      short loc_180017A26
0x180017a1f  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x180017a24  jmp     short loc_180017A2C
0x180017a26  call    cs:free
0x180017a2c  lea     r9, [rsp+4A0h+var_470]
0x180017a31  mov     rdx, [rsp+4A0h+var_468]
0x180017a36  call    sub_18004D894
0x180017a3b  nop
0x180017a3c  test    al, al
0x180017a3e  jz      short loc_180017A45
0x180017a40  jmp     loc_180017982
0x180017a45  mov     rcx, [rsp+4A0h+var_468]
0x180017a4a  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x180017a4e  mov     eax, r12d
0x180017a51  lock xadd [rcx], eax
0x180017a55  add     eax, r12d
0x180017a58  jnz     short loc_180017A74
0x180017a5a  cmp     rcx, r13
0x180017a5d  jz      short loc_180017A74
0x180017a5f  cmp     cs:dword_1802B0018, eax
0x180017a65  jz      short loc_180017A6E
0x180017a67  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x180017a6c  jmp     short loc_180017A74
0x180017a6e  call    cs:free
0x180017a74  xor     al, al
0x180017a76  test    al, al
0x180017a78  jnz     short loc_180017A83
0x180017a7a  xor     ecx, ecx
0x180017a7c  call    sub_180017AD0
0x180017a81  jmp     short loc_180017A86
0x180017a83  xor     dil, dil
0x180017a86  mov     dl, sil
0x180017a89  mov     rcx, r14
0x180017a8c  call    sub_180017BA4
0x180017a91  mov     rbx, rax
0x180017a94  test    dil, dil
0x180017a97  jz      short loc_180017AA1
0x180017a99  mov     cl, dil
0x180017a9c  call    sub_180017AD0
0x180017aa1  mov     rax, rbx
0x180017aa4  mov     rcx, [rbp+3A0h+var_30]
0x180017aab  xor     rcx, rsp
0x180017aae  call    sub_1801503E0
0x180017ab3  lea     r11, [rsp+4A0h+var_20]
0x180017abb  mov     rbx, [r11+38h]
0x180017abf  mov     rsi, [r11+40h]
0x180017ac3  mov     rsp, r11
0x180017ac6  pop     r14
0x180017ac8  pop     r13
0x180017aca  pop     r12
0x180017acc  pop     rdi
0x180017acd  pop     rbp
0x180017ace  retn
```
