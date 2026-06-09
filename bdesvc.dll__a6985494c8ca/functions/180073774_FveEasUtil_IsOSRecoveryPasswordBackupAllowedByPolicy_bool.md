# FveEasUtil::IsOSRecoveryPasswordBackupAllowedByPolicy(bool *)

- ea: `0x180073774`
- end: `0x1800739ce`
- name: `?IsOSRecoveryPasswordBackupAllowedByPolicy@FveEasUtil@@SAJPEA_N@Z`
- size: `602`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180071ea8`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x180073774`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800738a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800738a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007381b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007381b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073985`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073985`

## pseudocode

```c
__int64 __fastcall FveEasUtil::IsOSRecoveryPasswordBackupAllowedByPolicy(bool *a1)
{
  PVOID *v2; // rcx
  int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // r9
  __int64 v6; // rdx
  unsigned int Data; // [rsp+60h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  Data = 0;
  cbData = 4;
  Type = 4;
  hKey = 0;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v3 = -2147467261;
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 )
    {
      v4 = 92;
LABEL_16:
      WPP_SF_d(v2[2], v4, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, (unsigned int)v3);
LABEL_29:
      v2 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  *a1 = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\FVE", 0, 0x20019u, &hKey);
  if ( (unsigned int)(v3 - 2) <= 1 || v3 == 1168 )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_37;
    v6 = 93;
    goto LABEL_36;
  }
  if ( !v3 )
  {
    v3 = RegQueryValueExW(hKey, L"OSRecoveryPassword", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( (unsigned int)(v3 - 2) > 1 && v3 != 1168 )
    {
      if ( v3 )
      {
        if ( v3 > 0 )
          v3 = (unsigned __int16)v3 | 0x80070000;
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v4 = 96;
          goto LABEL_16;
        }
      }
      else
      {
        v5 = Data;
        v3 = 0;
        if ( Data - 1 > 1 )
          goto LABEL_29;
        *a1 = 1;
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v5);
          goto LABEL_29;
        }
      }
      goto LABEL_38;
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
LABEL_37:
      v3 = 0;
      goto LABEL_38;
    }
    v6 = 95;
LABEL_36:
    WPP_SF_(v2[2], v6, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_37;
  }
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v4 = 94;
    goto LABEL_16;
  }
LABEL_38:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v2 = (PVOID *)WPP_GLOBAL_Control;
    hKey = 0;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_d(v2[2], 98, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180073774  push    rbp
0x180073776  push    rbx
0x180073777  push    rdi
0x180073778  push    r14
0x18007377a  push    r15
0x18007377c  mov     rbp, rsp
0x18007377f  sub     rsp, 30h
0x180073783  mov     eax, 4
0x180073788  mov     [rbp+Data], 0
0x18007378f  mov     [rbp+cbData], eax
0x180073792  mov     rdi, rcx
0x180073795  mov     [rbp+Type], eax
0x180073798  mov     [rbp+hKey], 0
0x1800737a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800737a7  lea     r14, WPP_GLOBAL_Control
0x1800737ae  lea     r15, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800737b5  cmp     rcx, r14
0x1800737b8  jz      short loc_1800737D6
0x1800737ba  test    byte ptr [rcx+1Ch], 20h
0x1800737be  jz      short loc_1800737D6
0x1800737c0  mov     rcx, [rcx+10h]
0x1800737c4  lea     edx, [rax+57h]
0x1800737c7  mov     r8, r15
0x1800737ca  call    WPP_SF_
0x1800737cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800737d6  test    rdi, rdi
0x1800737d9  jnz     short loc_1800737F8
0x1800737db  mov     ebx, 80004003h
0x1800737e0  cmp     rcx, r14
0x1800737e3  jz      loc_180073979
0x1800737e9  test    byte ptr [rcx+1Ch], 40h
0x1800737ed  jz      loc_180073979
0x1800737f3  lea     edx, [rdi+5Ch]
0x1800737f6  jmp     short loc_18007386F
0x1800737f8  lea     rax, [rbp+hKey]
0x1800737fc  mov     byte ptr [rdi], 0
0x1800737ff  mov     r9d, 20019h; samDesired
0x180073805  mov     [rsp+30h+phkResult], rax; phkResult
0x18007380a  xor     r8d, r8d; ulOptions
0x18007380d  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\FVE"
0x180073814  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007381b  call    cs:__imp_RegOpenKeyExW
0x180073822  nop     dword ptr [rax+rax+00h]
0x180073827  mov     ebx, eax
0x180073829  add     eax, 0FFFFFFFEh
0x18007382c  cmp     eax, 1
0x18007382f  jbe     loc_18007394D
0x180073835  cmp     ebx, 490h
0x18007383b  jz      loc_18007394D
0x180073841  test    ebx, ebx
0x180073843  jz      short loc_180073883
0x180073845  jle     short loc_180073850
0x180073847  movzx   ebx, bx
0x18007384a  or      ebx, 80070000h
0x180073850  mov     rcx, cs:WPP_GLOBAL_Control
0x180073857  cmp     rcx, r14
0x18007385a  jz      loc_180073979
0x180073860  test    byte ptr [rcx+1Ch], 2
0x180073864  jz      loc_180073979
0x18007386a  mov     edx, 5Eh ; '^'
0x18007386f  mov     rcx, [rcx+10h]
0x180073873  mov     r9d, ebx
0x180073876  mov     r8, r15
0x180073879  call    WPP_SF_d
0x18007387e  jmp     loc_18007392B
0x180073883  mov     rcx, [rbp+hKey]; hKey
0x180073887  lea     rax, [rbp+cbData]
0x18007388b  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180073890  lea     r9, [rbp+Type]; lpType
0x180073894  lea     rax, [rbp+Data]
0x180073898  xor     r8d, r8d; lpReserved
0x18007389b  lea     rdx, aOsrecoverypass; "OSRecoveryPassword"
0x1800738a2  mov     [rsp+30h+phkResult], rax; lpData
0x1800738a7  call    cs:__imp_RegQueryValueExW
0x1800738ae  nop     dword ptr [rax+rax+00h]
0x1800738b3  mov     ebx, eax
0x1800738b5  add     eax, 0FFFFFFFEh
0x1800738b8  cmp     eax, 1
0x1800738bb  jbe     short loc_180073934
0x1800738bd  cmp     ebx, 490h
0x1800738c3  jz      short loc_180073934
0x1800738c5  test    ebx, ebx
0x1800738c7  jz      short loc_1800738F8
0x1800738c9  jle     short loc_1800738D4
0x1800738cb  movzx   ebx, bx
0x1800738ce  or      ebx, 80070000h
0x1800738d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800738db  cmp     rcx, r14
0x1800738de  jz      loc_180073979
0x1800738e4  test    byte ptr [rcx+1Ch], 8
0x1800738e8  jz      loc_180073979
0x1800738ee  mov     edx, 60h ; '`'
0x1800738f3  jmp     loc_18007386F
0x1800738f8  mov     r9d, [rbp+Data]
0x1800738fc  xor     ebx, ebx
0x1800738fe  lea     eax, [r9-1]
0x180073902  cmp     eax, 1
0x180073905  ja      short loc_18007392B
0x180073907  mov     byte ptr [rdi], 1
0x18007390a  mov     rcx, cs:WPP_GLOBAL_Control
0x180073911  cmp     rcx, r14
0x180073914  jz      short loc_180073979
0x180073916  test    byte ptr [rcx+1Ch], 8
0x18007391a  jz      short loc_180073979
0x18007391c  mov     rcx, [rcx+10h]
0x180073920  lea     edx, [rbx+61h]
0x180073923  mov     r8, r15
0x180073926  call    WPP_SF_d
0x18007392b  mov     rcx, cs:WPP_GLOBAL_Control
0x180073932  jmp     short loc_180073979
0x180073934  mov     rcx, cs:WPP_GLOBAL_Control
0x18007393b  cmp     rcx, r14
0x18007393e  jz      short loc_180073977
0x180073940  test    byte ptr [rcx+1Ch], 8
0x180073944  jz      short loc_180073977
0x180073946  mov     edx, 5Fh ; '_'
0x18007394b  jmp     short loc_180073964
0x18007394d  mov     rcx, cs:WPP_GLOBAL_Control
0x180073954  cmp     rcx, r14
0x180073957  jz      short loc_180073977
0x180073959  test    byte ptr [rcx+1Ch], 8
0x18007395d  jz      short loc_180073977
0x18007395f  mov     edx, 5Dh ; ']'
0x180073964  mov     rcx, [rcx+10h]
0x180073968  mov     r8, r15
0x18007396b  call    WPP_SF_
0x180073970  mov     rcx, cs:WPP_GLOBAL_Control
0x180073977  xor     ebx, ebx
0x180073979  mov     rax, [rbp+hKey]
0x18007397d  test    rax, rax
0x180073980  jz      short loc_1800739A0
0x180073982  mov     rcx, rax; hKey
0x180073985  call    cs:__imp_RegCloseKey
0x18007398c  nop     dword ptr [rax+rax+00h]
0x180073991  mov     rcx, cs:WPP_GLOBAL_Control
0x180073998  mov     [rbp+hKey], 0
0x1800739a0  cmp     rcx, r14
0x1800739a3  jz      short loc_1800739BF
0x1800739a5  test    byte ptr [rcx+1Ch], 20h
0x1800739a9  jz      short loc_1800739BF
0x1800739ab  mov     rcx, [rcx+10h]
0x1800739af  mov     edx, 62h ; 'b'
0x1800739b4  mov     r9d, ebx
0x1800739b7  mov     r8, r15
0x1800739ba  call    WPP_SF_d
0x1800739bf  mov     eax, ebx
0x1800739c1  add     rsp, 30h
0x1800739c5  pop     r15
0x1800739c7  pop     r14
0x1800739c9  pop     rdi
0x1800739ca  pop     rbx
0x1800739cb  pop     rbp
0x1800739cc  retn
```
