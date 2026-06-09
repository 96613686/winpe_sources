# AhcpIsTaskHostXapLaunch

- ea: `0x140054e54`
- end: `0x14005501a`
- name: `AhcpIsTaskHostXapLaunch`
- size: `454`
- prototype: `__int64 __fastcall(_BYTE *, GUID *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x14005974c`

## callees

- `0x140032244`
- `0x14003e364`
- `0x140045d44`
- `0x140046ec4`
- `0x140047668`
- `0x14005498c`
- `0x140054e54`

## import_xrefs

- `ntoskrnl!_wcsnicmp` at `0x140054f8a`
- `ntoskrnl!_wcsnicmp` at `0x140054fac`
- `ntoskrnl!_wcsnicmp` at `0x140054f8a`
- `ntoskrnl!_wcsnicmp` at `0x140054fac`

## string_xrefs

- `0x140054eec`: `AhcpIsTaskHostXapLaunch`
- `0x140054f62`: `AhcpIsTaskHostXapLaunch`
- `0x140054fdf`: `Failed to copy XAP Id [%x]`

## pseudocode

```c
__int64 __fastcall AhcpIsTaskHostXapLaunch(_BYTE *a1, GUID *a2, __int64 a3, __int64 a4)
{
  unsigned int v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rsi
  int v11; // eax
  const char *v12; // r9
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v16; // [rsp+20h] [rbp-28h]
  __int64 v17; // [rsp+50h] [rbp+8h] BYREF

  v17 = 0;
  *a2 = 0;
  *a1 = 0;
  if ( !(unsigned __int8)AhcpIsXapHostExe(a3) )
    return 0;
  v7 = AslEnvVarQuery(a4, L"LOCALAPPDATA", 12, 0, 0, &v17);
  v9 = v7;
  if ( v7 == -1073741568 || v17 != 75 )
    return 0;
  if ( v7 == -1073741789 )
  {
    v10 = AslAlloc(v8, 150, 1);
    if ( !v10 )
      return (unsigned int)-1073741801;
    v11 = AslEnvVarQuery(a4, L"LOCALAPPDATA", 12, v10, 75, &v17);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = "Failed to get the value of LOCALAPPDATA variable [%x]";
      v13 = 148;
LABEL_10:
      LODWORD(v16) = v11;
      AslLogCallPrintf(1, "AhcpIsTaskHostXapLaunch", v13, v12, v16);
LABEL_19:
      AslFree(v14, v10);
      return v9;
    }
    if ( !_wcsnicmp((const wchar_t *)(v10 + 4), L"\\Data\\Users\\DefApps\\AppData\\", 0x1Cu)
      && !_wcsnicmp((const wchar_t *)(v10 + 136), L"\\Local", 6u) )
    {
      if ( *(_WORD *)(v10 + 60) == 123 && *(_WORD *)(v10 + 134) == 125 )
      {
        *(_WORD *)(v10 + 136) = 0;
        v11 = AslGuidFromString(a2);
        v9 = v11;
        if ( v11 < 0 )
        {
          v12 = "Failed to copy XAP Id [%x]";
          v13 = 190;
          goto LABEL_10;
        }
      }
      *a1 = 1;
    }
    v9 = 0;
    goto LABEL_19;
  }
  AslLogCallPrintf(1, "AhcpIsTaskHostXapLaunch", 131, "Failed to get the size of LOCALAPPDATA variable [%x]", v7);
  return v9;
}

```

## disassembly

```asm
0x140054e54  mov     [rsp+arg_8], rbx
0x140054e59  mov     [rsp+arg_10], rbp
0x140054e5e  push    rsi
0x140054e5f  push    r14
0x140054e61  push    r15
0x140054e63  sub     rsp, 30h
0x140054e67  xorps   xmm0, xmm0
0x140054e6a  mov     [rsp+48h+arg_0], 0
0x140054e73  movups  xmmword ptr [rdx], xmm0
0x140054e76  mov     byte ptr [rcx], 0
0x140054e79  mov     r14, rcx
0x140054e7c  mov     rcx, r8
0x140054e7f  mov     rbp, r9
0x140054e82  mov     r15, rdx
0x140054e85  call    AhcpIsXapHostExe
0x140054e8a  test    al, al
0x140054e8c  jz      loc_140055001
0x140054e92  xor     r9d, r9d
0x140054e95  lea     rax, [rsp+48h+arg_0]
0x140054e9a  mov     [rsp+48h+var_20], rax
0x140054e9f  lea     rdx, aLocalappdata; "LOCALAPPDATA"
0x140054ea6  mov     rcx, rbp
0x140054ea9  mov     [rsp+48h+var_28], 0
0x140054eb2  lea     r8d, [r9+0Ch]
0x140054eb6  call    AslEnvVarQuery
0x140054ebb  mov     ebx, eax
0x140054ebd  cmp     eax, 0C0000100h
0x140054ec2  jz      loc_140055001
0x140054ec8  cmp     [rsp+48h+arg_0], 4Bh ; 'K'
0x140054ece  jnz     loc_140055001
0x140054ed4  cmp     eax, 0C0000023h
0x140054ed9  jz      short loc_140054F02
0x140054edb  lea     r9, aFailedToGetThe_2; "Failed to get the size of LOCALAPPDATA "...
0x140054ee2  mov     dword ptr [rsp+48h+var_28], eax
0x140054ee6  mov     r8d, 83h
0x140054eec  lea     rdx, aAhcpistaskhost; "AhcpIsTaskHostXapLaunch"
0x140054ef3  mov     ecx, 1
0x140054ef8  call    AslLogCallPrintf
0x140054efd  jmp     loc_140055003
0x140054f02  mov     edx, 96h
0x140054f07  mov     r8d, 1
0x140054f0d  call    AslAlloc
0x140054f12  mov     rsi, rax
0x140054f15  test    rax, rax
0x140054f18  jnz     short loc_140054F24
0x140054f1a  mov     ebx, 0C0000017h
0x140054f1f  jmp     loc_140055003
0x140054f24  lea     rax, [rsp+48h+arg_0]
0x140054f29  mov     r9, rsi
0x140054f2c  mov     [rsp+48h+var_20], rax
0x140054f31  lea     rdx, aLocalappdata; "LOCALAPPDATA"
0x140054f38  mov     r8d, 0Ch
0x140054f3e  mov     [rsp+48h+var_28], 4Bh ; 'K'
0x140054f47  mov     rcx, rbp
0x140054f4a  call    AslEnvVarQuery
0x140054f4f  mov     ebx, eax
0x140054f51  test    eax, eax
0x140054f53  jns     short loc_140054F79
0x140054f55  lea     r9, aFailedToGetThe_5; "Failed to get the value of LOCALAPPDATA"...
0x140054f5c  mov     r8d, 94h
0x140054f62  lea     rdx, aAhcpistaskhost; "AhcpIsTaskHostXapLaunch"
0x140054f69  mov     dword ptr [rsp+48h+var_28], eax
0x140054f6d  mov     ecx, 1
0x140054f72  call    AslLogCallPrintf
0x140054f77  jmp     short loc_140054FF7
0x140054f79  mov     r8d, 1Ch; MaxCount
0x140054f7f  lea     rdx, aDataUsersDefap; "\\Data\\Users\\DefApps\\AppData\\"
0x140054f86  lea     rcx, [rsi+4]; Str1
0x140054f8a  call    cs:__imp__wcsnicmp
0x140054f91  nop     dword ptr [rax+rax+00h]
0x140054f96  test    eax, eax
0x140054f98  jnz     short loc_140054FF5
0x140054f9a  lea     rcx, [rsi+88h]; Str1
0x140054fa1  lea     r8d, [rax+6]; MaxCount
0x140054fa5  lea     rdx, aLocal; "\\Local"
0x140054fac  call    cs:__imp__wcsnicmp
0x140054fb3  nop     dword ptr [rax+rax+00h]
0x140054fb8  test    eax, eax
0x140054fba  jnz     short loc_140054FF5
0x140054fbc  lea     rdx, [rsi+3Ch]
0x140054fc0  cmp     word ptr [rdx], 7Bh ; '{'
0x140054fc4  jnz     short loc_140054FF1
0x140054fc6  cmp     word ptr [rdx+4Ah], 7Dh ; '}'
0x140054fcb  jnz     short loc_140054FF1
0x140054fcd  mov     rcx, r15; Guid
0x140054fd0  mov     [rdx+4Ch], ax
0x140054fd4  call    AslGuidFromString
0x140054fd9  mov     ebx, eax
0x140054fdb  test    eax, eax
0x140054fdd  jns     short loc_140054FF1
0x140054fdf  lea     r9, aFailedToCopyXa; "Failed to copy XAP Id [%x]"
0x140054fe6  mov     r8d, 0BEh
0x140054fec  jmp     loc_140054F62
0x140054ff1  mov     byte ptr [r14], 1
0x140054ff5  xor     ebx, ebx
0x140054ff7  mov     rdx, rsi
0x140054ffa  call    AslFree
0x140054fff  jmp     short loc_140055003
0x140055001  xor     ebx, ebx
0x140055003  mov     rbp, [rsp+48h+arg_10]
0x140055008  mov     eax, ebx
0x14005500a  mov     rbx, [rsp+48h+arg_8]
0x14005500f  add     rsp, 30h
0x140055013  pop     r15
0x140055015  pop     r14
0x140055017  pop     rsi
0x140055018  retn
```
