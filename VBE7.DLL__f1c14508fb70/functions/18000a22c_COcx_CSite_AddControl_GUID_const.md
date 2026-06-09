# COcx::CSite::AddControl(_GUID const &)

- ea: `0x18000a22c`
- end: `0x18000a428`
- name: `?AddControl@CSite@COcx@@UEAAJAEBU_GUID@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(COcx::CSite *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a22c`
- `0x180047738`
- `0x18005ab18`
- `0x18005b0d4`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!strtoul` at `0x18000a3a6`
- `MSVCR100!strtoul` at `0x18000a3c4`
- `MSVCR100!strtoul` at `0x18000a3a6`
- `MSVCR100!strtoul` at `0x18000a3c4`
- `USER32!wsprintfA` at `0x18000a2bc`
- `USER32!wsprintfA` at `0x18000a371`
- `USER32!wsprintfA` at `0x18000a2bc`
- `USER32!wsprintfA` at `0x18000a371`
- `ADVAPI32!RegQueryValueA` at `0x18000a2d8`
- `ADVAPI32!RegQueryValueA` at `0x18000a38d`
- `ADVAPI32!RegQueryValueA` at `0x18000a2d8`
- `ADVAPI32!RegQueryValueA` at `0x18000a38d`
- `ole32!CLSIDFromString` at `0x18000a354`
- `ole32!CLSIDFromString` at `0x18000a354`

## string_xrefs

- `0x18000a2b1`: `CLSID\%s\TypeLib`
- `0x18000a366`: `CLSID\%s\Version`

## pseudocode

```c
__int64 __fastcall COcx::CSite::AddControl(COcx::CSite *this, const struct _GUID *a2)
{
  __int64 v2; // rax
  int v3; // ebx
  unsigned __int16 v4; // di
  Project *v5; // rsi
  __int64 v7; // rax
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  const OLECHAR *v13; // rax
  unsigned __int16 v14; // bx
  LONG cbData; // [rsp+30h] [rbp+0h] BYREF
  char *EndPtr; // [rsp+38h] [rbp+8h] BYREF
  CLSID pclsid; // [rsp+40h] [rbp+10h] BYREF
  char v18[40]; // [rsp+50h] [rbp+20h] BYREF
  CHAR SubKey[72]; // [rsp+78h] [rbp+48h] BYREF
  CHAR Data[2048]; // [rsp+C0h] [rbp+90h] BYREF

  v2 = *((_QWORD *)this - 42);
  cbData = 2048;
  v3 = 0;
  v4 = 0;
  v5 = *(Project **)(*(_QWORD *)(*(_QWORD *)(v2 + 136) + 120LL) + 40LL);
  if ( !v5 )
    return 2147500037LL;
  StringFromGUID2Ansi(a2, v18, 39);
  wsprintfA(SubKey, "CLSID\\%s\\TypeLib", v18);
  if ( RegQueryValueA(HKEY_CLASSES_ROOT, SubKey, Data, &cbData) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    if ( ((unsigned __int64)Data & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( Data[v7] );
      v8 = 2 * v7 + 2;
      v9 = v8 + 15;
      if ( v8 + 15 < v8 )
        v9 = 0xFFFFFFFFFFFFFF0LL;
      v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
      v11 = alloca(v10);
      v12 = alloca(v10);
      v13 = strcpyWfromA((wchar_t *)&cbData, Data);
    }
    else
    {
      v13 = (const OLECHAR *)Data;
    }
    if ( CLSIDFromString(v13, &pclsid) >= 0 )
    {
      wsprintfA(SubKey, "CLSID\\%s\\Version", v18);
      if ( !RegQueryValueA(HKEY_CLASSES_ROOT, SubKey, Data, &cbData) )
      {
        v14 = strtoul(Data, &EndPtr, 16);
        if ( *EndPtr == 46 )
          v4 = strtoul(EndPtr + 1, &EndPtr, 16);
        v3 = Project::ProfferTypeLib(v5, &pclsid, v14, v4, 1u, 0);
        if ( v3 >= 0 )
          return 0;
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000a22c  push    rbp
0x18000a22e  push    rdi
0x18000a22f  push    r14
0x18000a231  mov     eax, 8D0h
0x18000a236  call    _alloca_probe
0x18000a23b  sub     rsp, rax
0x18000a23e  lea     rbp, [rsp+30h]
0x18000a243  mov     [rbp+8B0h+arg_10], rbx
0x18000a24a  mov     [rbp+8B0h+arg_18], rsi
0x18000a251  mov     rax, cs:__security_cookie
0x18000a258  xor     rax, rbp
0x18000a25b  mov     [rbp+8B0h+var_20], rax
0x18000a262  mov     rax, [rcx-150h]
0x18000a269  mov     [rbp+8B0h+cbData], 800h
0x18000a270  xor     r14d, r14d
0x18000a273  mov     rcx, [rax+88h]
0x18000a27a  mov     r9, rdx
0x18000a27d  mov     ebx, r14d
0x18000a280  mov     rax, [rcx+78h]
0x18000a284  movzx   edi, r14w
0x18000a288  mov     rsi, [rax+28h]
0x18000a28c  test    rsi, rsi
0x18000a28f  jnz     short loc_18000A29B
0x18000a291  mov     eax, 80004005h
0x18000a296  jmp     loc_18000A3FF
0x18000a29b  lea     rdx, [rbp+8B0h+var_890]; char *
0x18000a29f  mov     r8d, 27h ; '''; int
0x18000a2a5  mov     rcx, r9; struct _GUID *
0x18000a2a8  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x18000a2ad  lea     r8, [rbp+8B0h+var_890]
0x18000a2b1  lea     rdx, aClsidSTypelib; "CLSID\\%s\\TypeLib"
0x18000a2b8  lea     rcx, [rbp+8B0h+SubKey]; LPSTR
0x18000a2bc  call    cs:__imp_wsprintfA
0x18000a2c2  lea     r9, [rbp+8B0h+cbData]; lpcbData
0x18000a2c6  lea     r8, [rbp+8B0h+Data]; lpData
0x18000a2cd  lea     rdx, [rbp+8B0h+SubKey]; lpSubKey
0x18000a2d1  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000a2d8  call    cs:__imp_RegQueryValueA
0x18000a2de  test    eax, eax
0x18000a2e0  jnz     loc_18000A3F8
0x18000a2e6  lea     rax, [rbp+8B0h+Data]
0x18000a2ed  test    rax, 0FFFFFFFFFFFF0000h
0x18000a2f3  jz      short loc_18000A346
0x18000a2f5  lea     rcx, [rbp+8B0h+Data]
0x18000a2fc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a300  inc     rax
0x18000a303  cmp     [rcx+rax], r14b
0x18000a307  jnz     short loc_18000A300
0x18000a309  lea     rax, ds:2[rax*2]
0x18000a311  lea     rcx, [rax+0Fh]
0x18000a315  cmp     rcx, rax
0x18000a318  ja      short loc_18000A324
0x18000a31a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000a324  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000a328  mov     rax, rcx
0x18000a32b  call    _alloca_probe
0x18000a330  sub     rsp, rcx
0x18000a333  lea     rdx, [rbp+8B0h+Data]; char *
0x18000a33a  lea     rcx, [rsp+8E0h+cbData]; wchar_t *
0x18000a33f  call    ?strcpyWfromA@@YAPEA_WPEA_WPEBD@Z; strcpyWfromA(wchar_t *,char const *)
0x18000a344  jmp     short loc_18000A34D
0x18000a346  lea     rax, [rbp+8B0h+Data]
0x18000a34d  lea     rdx, [rbp+8B0h+pclsid]; pclsid
0x18000a351  mov     rcx, rax; lpsz
0x18000a354  call    cs:__imp_CLSIDFromString
0x18000a35a  test    eax, eax
0x18000a35c  js      loc_18000A3FD
0x18000a362  lea     r8, [rbp+8B0h+var_890]
0x18000a366  lea     rdx, aClsidSVersion; "CLSID\\%s\\Version"
0x18000a36d  lea     rcx, [rbp+8B0h+SubKey]; LPSTR
0x18000a371  call    cs:__imp_wsprintfA
0x18000a377  lea     r9, [rbp+8B0h+cbData]; lpcbData
0x18000a37b  lea     r8, [rbp+8B0h+Data]; lpData
0x18000a382  lea     rdx, [rbp+8B0h+SubKey]; lpSubKey
0x18000a386  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000a38d  call    cs:__imp_RegQueryValueA
0x18000a393  test    eax, eax
0x18000a395  jnz     short loc_18000A3FD
0x18000a397  lea     r8d, [rax+10h]; Radix
0x18000a39b  lea     rdx, [rbp+8B0h+EndPtr]; EndPtr
0x18000a39f  lea     rcx, [rbp+8B0h+Data]; String
0x18000a3a6  call    cs:__imp_strtoul
0x18000a3ac  mov     rcx, [rbp+8B0h+EndPtr]
0x18000a3b0  cmp     byte ptr [rcx], 2Eh ; '.'
0x18000a3b3  mov     ebx, eax
0x18000a3b5  jnz     short loc_18000A3CC
0x18000a3b7  lea     rdx, [rbp+8B0h+EndPtr]; EndPtr
0x18000a3bb  inc     rcx; String
0x18000a3be  mov     r8d, 10h; Radix
0x18000a3c4  call    cs:__imp_strtoul
0x18000a3ca  mov     edi, eax
0x18000a3cc  lea     rdx, [rbp+8B0h+pclsid]; struct _GUID *
0x18000a3d0  movzx   r9d, di; unsigned int
0x18000a3d4  movzx   r8d, bx; unsigned int
0x18000a3d8  mov     rcx, rsi; this
0x18000a3db  mov     [rsp+8E0h+var_8B8], r14d; int
0x18000a3e0  mov     [rsp+8E0h+var_8C0], 1; unsigned int
0x18000a3e8  call    ?ProfferTypeLib@Project@@QEAAJAEBU_GUID@@IIKH@Z; Project::ProfferTypeLib(_GUID const &,uint,uint,ulong,int)
0x18000a3ed  mov     ebx, eax
0x18000a3ef  test    eax, eax
0x18000a3f1  js      short loc_18000A3FD
0x18000a3f3  mov     ebx, r14d
0x18000a3f6  jmp     short loc_18000A3FD
0x18000a3f8  mov     ebx, 80004005h
0x18000a3fd  mov     eax, ebx
0x18000a3ff  mov     rcx, [rbp+8B0h+var_20]
0x18000a406  xor     rcx, rbp; StackCookie
0x18000a409  call    __security_check_cookie
0x18000a40e  mov     rbx, [rbp+8B0h+arg_10]
0x18000a415  mov     rsi, [rbp+8B0h+arg_18]
0x18000a41c  lea     rsp, [rbp+8A0h]
0x18000a423  pop     r14
0x18000a425  pop     rdi
0x18000a426  pop     rbp
0x18000a427  retn
```
