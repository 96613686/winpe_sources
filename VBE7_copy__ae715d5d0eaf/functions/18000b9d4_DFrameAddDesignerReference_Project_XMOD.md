# DFrameAddDesignerReference(Project *,XMOD *)

- ea: `0x18000b9d4`
- end: `0x18000bc13`
- name: `?DFrameAddDesignerReference@@YAJPEAVProject@@PEAUXMOD@@@Z`
- size: `575`
- prototype: `__int64 __fastcall(struct Project *, struct XMOD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b1c4`
- `0x180050140`

## callees

- `0x18000b9d4`
- `0x180047738`
- `0x18005ab18`
- `0x18005b0d4`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!strtoul` at `0x18000bb90`
- `MSVCR100!strtoul` at `0x18000bbae`
- `MSVCR100!strtoul` at `0x18000bb90`
- `MSVCR100!strtoul` at `0x18000bbae`
- `USER32!wsprintfA` at `0x18000bab3`
- `USER32!wsprintfA` at `0x18000bb5b`
- `USER32!wsprintfA` at `0x18000bab3`
- `USER32!wsprintfA` at `0x18000bb5b`
- `ADVAPI32!RegQueryValueA` at `0x18000bacf`
- `ADVAPI32!RegQueryValueA` at `0x18000bb77`
- `ADVAPI32!RegQueryValueA` at `0x18000bacf`
- `ADVAPI32!RegQueryValueA` at `0x18000bb77`
- `ole32!CLSIDFromString` at `0x18000bb3e`
- `ole32!CLSIDFromString` at `0x18000bb3e`

## string_xrefs

- `0x18000baa8`: `CLSID\%s\TypeLib`
- `0x18000bb50`: `CLSID\%s\Version`

## pseudocode

```c
__int64 __fastcall DFrameAddDesignerReference(struct Project *a1, struct XMOD *a2)
{
  __int64 v2; // rax
  struct _GUID *v4; // rax
  __int64 v5; // rbx
  bool v6; // cf
  int v7; // eax
  __int64 result; // rax
  unsigned __int16 v9; // si
  const OLECHAR *v10; // rax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  unsigned __int16 v15; // bx
  LONG cbData; // [rsp+30h] [rbp+0h] BYREF
  char *EndPtr; // [rsp+38h] [rbp+8h] BYREF
  struct _GUID v18; // [rsp+40h] [rbp+10h] BYREF
  CLSID pclsid; // [rsp+50h] [rbp+20h] BYREF
  char v20[40]; // [rsp+60h] [rbp+30h] BYREF
  CHAR SubKey[72]; // [rsp+88h] [rbp+58h] BYREF
  CHAR Data[2048]; // [rsp+D0h] [rbp+A0h] BYREF

  v2 = *((_QWORD *)a2 + 1);
  if ( v2 )
    v4 = (struct _GUID *)(v2 + 280);
  else
    v4 = (struct _GUID *)((char *)a2 + 280);
  v5 = -1;
  v18 = *v4;
  v6 = *(_QWORD *)&v18.Data1 < *(_QWORD *)&CLSID_Forms3Form.Data1;
  if ( *(_QWORD *)&v18.Data1 == *(_QWORD *)&CLSID_Forms3Form.Data1
    && (v6 = *(_QWORD *)v18.Data4 < *(_QWORD *)CLSID_Forms3Form.Data4,
        *(_QWORD *)v18.Data4 == *(_QWORD *)CLSID_Forms3Form.Data4) )
  {
    v7 = 0;
  }
  else
  {
    v7 = -v6 - (v6 - 1);
  }
  if ( !v7 )
    return Project::ProfferTypeLib(a1, &LIDID_Form3, 2u, 0, 1u, 0);
  cbData = 2048;
  v9 = 0;
  StringFromGUID2Ansi(&v18, v20, 39);
  wsprintfA(SubKey, "CLSID\\%s\\TypeLib", v20);
  if ( RegQueryValueA(HKEY_CLASSES_ROOT, SubKey, Data, &cbData) )
    return 2147500037LL;
  v10 = (const OLECHAR *)Data;
  if ( ((unsigned __int64)Data & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    do
      ++v5;
    while ( Data[v5] );
    v11 = 2 * v5 + 17;
    if ( v11 <= 2 * v5 + 2 )
      v11 = 0xFFFFFFFFFFFFFF0LL;
    v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
    v13 = alloca(v12);
    v14 = alloca(v12);
    v10 = strcpyWfromA((wchar_t *)&cbData, Data);
  }
  if ( CLSIDFromString(v10, &pclsid) < 0 )
    return (unsigned int)cbData;
  wsprintfA(SubKey, "CLSID\\%s\\Version", v20);
  if ( RegQueryValueA(HKEY_CLASSES_ROOT, SubKey, Data, &cbData) )
    return (unsigned int)cbData;
  v15 = strtoul(Data, &EndPtr, 16);
  if ( *EndPtr == 46 )
    v9 = strtoul(EndPtr + 1, &EndPtr, 16);
  result = Project::ProfferTypeLib(a1, &pclsid, v15, v9, 1u, 0);
  if ( (int)result >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18000b9d4  push    rbp
0x18000b9d6  push    rdi
0x18000b9d7  push    r14
0x18000b9d9  mov     eax, 8E0h
0x18000b9de  call    _alloca_probe
0x18000b9e3  sub     rsp, rax
0x18000b9e6  lea     rbp, [rsp+30h]
0x18000b9eb  mov     [rbp+8C0h+arg_10], rbx
0x18000b9f2  mov     [rbp+8C0h+arg_18], rsi
0x18000b9f9  mov     rax, cs:__security_cookie
0x18000ba00  xor     rax, rbp
0x18000ba03  mov     [rbp+8C0h+var_20], rax
0x18000ba0a  mov     rax, [rdx+8]
0x18000ba0e  xor     r14d, r14d
0x18000ba11  mov     rdi, rcx
0x18000ba14  test    rax, rax
0x18000ba17  jz      short loc_18000BA21
0x18000ba19  add     rax, 118h
0x18000ba1f  jmp     short loc_18000BA28
0x18000ba21  lea     rax, [rdx+118h]
0x18000ba28  movups  xmm0, xmmword ptr [rax]
0x18000ba2b  lea     rax, [rbp+8C0h+var_8B0]
0x18000ba2f  lea     rcx, CLSID_Forms3Form
0x18000ba36  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ba3a  movdqu  xmmword ptr [rbp+8C0h+var_8B0.Data1], xmm0
0x18000ba3f  mov     rdx, [rax]
0x18000ba42  cmp     rdx, [rcx]
0x18000ba45  jnz     short loc_18000BA56
0x18000ba47  mov     rdx, [rax+8]
0x18000ba4b  cmp     rdx, [rcx+8]
0x18000ba4f  jnz     short loc_18000BA56
0x18000ba51  mov     eax, r14d
0x18000ba54  jmp     short loc_18000BA5A
0x18000ba56  sbb     eax, eax
0x18000ba58  sbb     eax, ebx
0x18000ba5a  test    eax, eax
0x18000ba5c  jnz     short loc_18000BA86
0x18000ba5e  lea     r8d, [rax+2]; unsigned int
0x18000ba62  lea     rdx, LIDID_Form3; struct _GUID *
0x18000ba69  xor     r9d, r9d; unsigned int
0x18000ba6c  mov     rcx, rdi; this
0x18000ba6f  mov     [rsp+8F0h+var_8C8], r14d; int
0x18000ba74  mov     [rsp+8F0h+var_8D0], 1; unsigned int
0x18000ba7c  call    ?ProfferTypeLib@Project@@QEAAJAEBU_GUID@@IIKH@Z; Project::ProfferTypeLib(_GUID const &,uint,uint,ulong,int)
0x18000ba81  jmp     loc_18000BBEA
0x18000ba86  lea     rdx, [rbp+8C0h+var_890]; char *
0x18000ba8a  lea     rcx, [rbp+8C0h+var_8B0]; struct _GUID *
0x18000ba8e  mov     r8d, 27h ; '''; int
0x18000ba94  mov     [rbp+8C0h+cbData], 800h
0x18000ba9b  movzx   esi, r14w
0x18000ba9f  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x18000baa4  lea     r8, [rbp+8C0h+var_890]
0x18000baa8  lea     rdx, aClsidSTypelib; "CLSID\\%s\\TypeLib"
0x18000baaf  lea     rcx, [rbp+8C0h+SubKey]; LPSTR
0x18000bab3  call    cs:__imp_wsprintfA
0x18000bab9  lea     r9, [rbp+8C0h+cbData]; lpcbData
0x18000babd  lea     r8, [rbp+8C0h+Data]; lpData
0x18000bac4  lea     rdx, [rbp+8C0h+SubKey]; lpSubKey
0x18000bac8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000bacf  call    cs:__imp_RegQueryValueA
0x18000bad5  test    eax, eax
0x18000bad7  jnz     loc_18000BBE5
0x18000badd  lea     rax, [rbp+8C0h+Data]
0x18000bae4  test    rax, 0FFFFFFFFFFFF0000h
0x18000baea  lea     rax, [rbp+8C0h+Data]
0x18000baf1  jz      short loc_18000BB37
0x18000baf3  inc     rbx
0x18000baf6  cmp     [rax+rbx], r14b
0x18000bafa  jnz     short loc_18000BAF3
0x18000bafc  lea     rax, ds:2[rbx*2]
0x18000bb04  lea     rcx, [rax+0Fh]
0x18000bb08  cmp     rcx, rax
0x18000bb0b  ja      short loc_18000BB17
0x18000bb0d  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000bb17  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000bb1b  mov     rax, rcx
0x18000bb1e  call    _alloca_probe
0x18000bb23  sub     rsp, rcx
0x18000bb26  lea     rdx, [rbp+8C0h+Data]; char *
0x18000bb2d  lea     rcx, [rsp+8F0h+cbData]; wchar_t *
0x18000bb32  call    ?strcpyWfromA@@YAPEA_WPEA_WPEBD@Z; strcpyWfromA(wchar_t *,char const *)
0x18000bb37  lea     rdx, [rbp+8C0h+pclsid]; pclsid
0x18000bb3b  mov     rcx, rax; lpsz
0x18000bb3e  call    cs:__imp_CLSIDFromString
0x18000bb44  test    eax, eax
0x18000bb46  js      loc_18000BBE0
0x18000bb4c  lea     r8, [rbp+8C0h+var_890]
0x18000bb50  lea     rdx, aClsidSVersion; "CLSID\\%s\\Version"
0x18000bb57  lea     rcx, [rbp+8C0h+SubKey]; LPSTR
0x18000bb5b  call    cs:__imp_wsprintfA
0x18000bb61  lea     r9, [rbp+8C0h+cbData]; lpcbData
0x18000bb65  lea     r8, [rbp+8C0h+Data]; lpData
0x18000bb6c  lea     rdx, [rbp+8C0h+SubKey]; lpSubKey
0x18000bb70  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000bb77  call    cs:__imp_RegQueryValueA
0x18000bb7d  test    eax, eax
0x18000bb7f  jnz     short loc_18000BBE0
0x18000bb81  lea     r8d, [rax+10h]; Radix
0x18000bb85  lea     rdx, [rbp+8C0h+EndPtr]; EndPtr
0x18000bb89  lea     rcx, [rbp+8C0h+Data]; String
0x18000bb90  call    cs:__imp_strtoul
0x18000bb96  mov     rcx, [rbp+8C0h+EndPtr]
0x18000bb9a  cmp     byte ptr [rcx], 2Eh ; '.'
0x18000bb9d  mov     ebx, eax
0x18000bb9f  jnz     short loc_18000BBB6
0x18000bba1  lea     rdx, [rbp+8C0h+EndPtr]; EndPtr
0x18000bba5  inc     rcx; String
0x18000bba8  mov     r8d, 10h; Radix
0x18000bbae  call    cs:__imp_strtoul
0x18000bbb4  mov     esi, eax
0x18000bbb6  lea     rdx, [rbp+8C0h+pclsid]; struct _GUID *
0x18000bbba  movzx   r9d, si; unsigned int
0x18000bbbe  movzx   r8d, bx; unsigned int
0x18000bbc2  mov     rcx, rdi; this
0x18000bbc5  mov     [rsp+8F0h+var_8C8], r14d; int
0x18000bbca  mov     [rsp+8F0h+var_8D0], 1; unsigned int
0x18000bbd2  call    ?ProfferTypeLib@Project@@QEAAJAEBU_GUID@@IIKH@Z; Project::ProfferTypeLib(_GUID const &,uint,uint,ulong,int)
0x18000bbd7  test    eax, eax
0x18000bbd9  js      short loc_18000BBEA
0x18000bbdb  mov     eax, r14d
0x18000bbde  jmp     short loc_18000BBEA
0x18000bbe0  mov     eax, [rbp+8C0h+cbData]
0x18000bbe3  jmp     short loc_18000BBEA
0x18000bbe5  mov     eax, 80004005h
0x18000bbea  mov     rcx, [rbp+8C0h+var_20]
0x18000bbf1  xor     rcx, rbp; StackCookie
0x18000bbf4  call    __security_check_cookie
0x18000bbf9  mov     rbx, [rbp+8C0h+arg_10]
0x18000bc00  mov     rsi, [rbp+8C0h+arg_18]
0x18000bc07  lea     rsp, [rbp+8B0h]
0x18000bc0e  pop     r14
0x18000bc10  pop     rdi
0x18000bc11  pop     rbp
0x18000bc12  retn
```
