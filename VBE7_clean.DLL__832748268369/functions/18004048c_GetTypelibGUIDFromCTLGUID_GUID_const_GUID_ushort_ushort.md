# GetTypelibGUIDFromCTLGUID(_GUID const &,_GUID *,ushort *,ushort *)

- ea: `0x18004048c`
- end: `0x180040616`
- name: `?GetTypelibGUIDFromCTLGUID@@YAJAEBU_GUID@@PEAU1@PEAG2@Z`
- size: `394`
- prototype: `__int64 __fastcall(const struct _GUID *, struct _GUID *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800dd990`

## callees

- `0x18004048c`
- `0x18005ab18`
- `0x18005b0d4`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!strtoul` at `0x1800405ca`
- `MSVCR100!strtoul` at `0x1800405e6`
- `MSVCR100!strtoul` at `0x1800405ca`
- `MSVCR100!strtoul` at `0x1800405e6`
- `USER32!wsprintfA` at `0x1800404e4`
- `USER32!wsprintfA` at `0x180040593`
- `USER32!wsprintfA` at `0x1800404e4`
- `USER32!wsprintfA` at `0x180040593`
- `ADVAPI32!RegQueryValueA` at `0x180040500`
- `ADVAPI32!RegQueryValueA` at `0x1800405af`
- `ADVAPI32!RegQueryValueA` at `0x180040500`
- `ADVAPI32!RegQueryValueA` at `0x1800405af`
- `ole32!CLSIDFromString` at `0x18004057a`
- `ole32!CLSIDFromString` at `0x18004057a`

## string_xrefs

- `0x1800404d9`: `CLSID\%s\TypeLib`
- `0x180040588`: `CLSID\%s\Version`

## pseudocode

```c
__int64 __fastcall GetTypelibGUIDFromCTLGUID(
        const struct _GUID *a1,
        struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned int v6; // ebx
  __int64 v8; // rax
  unsigned __int64 v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  const OLECHAR *v14; // rax
  unsigned __int16 v15; // ax
  char *v16; // rcx
  LONG cbData; // [rsp+20h] [rbp+0h] BYREF
  char *EndPtr; // [rsp+28h] [rbp+8h] BYREF
  char v20[40]; // [rsp+30h] [rbp+10h] BYREF
  CHAR SubKey[72]; // [rsp+58h] [rbp+38h] BYREF
  CHAR Data[2048]; // [rsp+A0h] [rbp+80h] BYREF

  v6 = 0;
  cbData = 2048;
  StringFromGUID2Ansi(a1, v20, 39);
  wsprintfA(SubKey, "CLSID\\%s\\TypeLib", v20);
  if ( RegQueryValueA(HKEY_CLASSES_ROOT, SubKey, Data, &cbData) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    if ( ((unsigned __int64)Data & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      v8 = -1;
      do
        ++v8;
      while ( Data[v8] );
      v9 = 2 * v8 + 2;
      v10 = v9 + 15;
      if ( v9 + 15 < v9 )
        v10 = 0xFFFFFFFFFFFFFF0LL;
      v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
      v12 = alloca(v11);
      v13 = alloca(v11);
      v14 = strcpyWfromA((wchar_t *)&cbData, Data);
    }
    else
    {
      v14 = (const OLECHAR *)Data;
    }
    if ( CLSIDFromString(v14, a2) >= 0 )
    {
      wsprintfA(SubKey, "CLSID\\%s\\Version", v20);
      if ( !RegQueryValueA(HKEY_CLASSES_ROOT, SubKey, Data, &cbData) )
      {
        v15 = strtoul(Data, &EndPtr, 16);
        v16 = EndPtr;
        *a3 = v15;
        if ( *v16 == 46 )
          *a4 = strtoul(v16 + 1, &EndPtr, 16);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18004048c  push    rbp
0x18004048e  push    rbx
0x18004048f  push    rsi
0x180040490  push    rdi
0x180040491  push    r14
0x180040493  mov     eax, 8B0h
0x180040498  call    _alloca_probe
0x18004049d  sub     rsp, rax
0x1800404a0  lea     rbp, [rsp+20h]
0x1800404a5  mov     rax, cs:__security_cookie
0x1800404ac  xor     rax, rbp
0x1800404af  mov     [rbp+8B0h+var_30], rax
0x1800404b6  mov     rsi, r8
0x1800404b9  mov     rdi, rdx
0x1800404bc  xor     ebx, ebx
0x1800404be  lea     rdx, [rbp+8B0h+var_8A0]; char *
0x1800404c2  lea     r8d, [rbx+27h]; int
0x1800404c6  mov     r14, r9
0x1800404c9  mov     [rbp+8B0h+cbData], 800h
0x1800404d0  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x1800404d5  lea     r8, [rbp+8B0h+var_8A0]
0x1800404d9  lea     rdx, aClsidSTypelib; "CLSID\\%s\\TypeLib"
0x1800404e0  lea     rcx, [rbp+8B0h+SubKey]; LPSTR
0x1800404e4  call    cs:__imp_wsprintfA
0x1800404ea  lea     r9, [rbp+8B0h+cbData]; lpcbData
0x1800404ee  lea     r8, [rbp+8B0h+Data]; lpData
0x1800404f5  lea     rdx, [rbp+8B0h+SubKey]; lpSubKey
0x1800404f9  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180040500  call    cs:__imp_RegQueryValueA
0x180040506  test    eax, eax
0x180040508  jnz     loc_1800405F2
0x18004050e  lea     rax, [rbp+8B0h+Data]
0x180040515  test    rax, 0FFFFFFFFFFFF0000h
0x18004051b  jz      short loc_18004056D
0x18004051d  lea     rcx, [rbp+8B0h+Data]
0x180040524  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040528  inc     rax
0x18004052b  cmp     [rcx+rax], bl
0x18004052e  jnz     short loc_180040528
0x180040530  lea     rax, ds:2[rax*2]
0x180040538  lea     rcx, [rax+0Fh]
0x18004053c  cmp     rcx, rax
0x18004053f  ja      short loc_18004054B
0x180040541  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18004054b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18004054f  mov     rax, rcx
0x180040552  call    _alloca_probe
0x180040557  sub     rsp, rcx
0x18004055a  lea     rdx, [rbp+8B0h+Data]; char *
0x180040561  lea     rcx, [rsp+8D0h+cbData]; wchar_t *
0x180040566  call    ?strcpyWfromA@@YAPEA_WPEA_WPEBD@Z; strcpyWfromA(wchar_t *,char const *)
0x18004056b  jmp     short loc_180040574
0x18004056d  lea     rax, [rbp+8B0h+Data]
0x180040574  mov     rdx, rdi; pclsid
0x180040577  mov     rcx, rax; lpsz
0x18004057a  call    cs:__imp_CLSIDFromString
0x180040580  test    eax, eax
0x180040582  js      short loc_1800405F7
0x180040584  lea     r8, [rbp+8B0h+var_8A0]
0x180040588  lea     rdx, aClsidSVersion; "CLSID\\%s\\Version"
0x18004058f  lea     rcx, [rbp+8B0h+SubKey]; LPSTR
0x180040593  call    cs:__imp_wsprintfA
0x180040599  lea     r9, [rbp+8B0h+cbData]; lpcbData
0x18004059d  lea     r8, [rbp+8B0h+Data]; lpData
0x1800405a4  lea     rdx, [rbp+8B0h+SubKey]; lpSubKey
0x1800405a8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800405af  call    cs:__imp_RegQueryValueA
0x1800405b5  test    eax, eax
0x1800405b7  jnz     short loc_1800405F7
0x1800405b9  lea     edi, [rax+10h]
0x1800405bc  lea     rdx, [rbp+8B0h+EndPtr]; EndPtr
0x1800405c0  lea     rcx, [rbp+8B0h+Data]; String
0x1800405c7  mov     r8d, edi; Radix
0x1800405ca  call    cs:__imp_strtoul
0x1800405d0  mov     rcx, [rbp+8B0h+EndPtr]
0x1800405d4  mov     [rsi], ax
0x1800405d7  cmp     byte ptr [rcx], 2Eh ; '.'
0x1800405da  jnz     short loc_1800405F7
0x1800405dc  lea     rdx, [rbp+8B0h+EndPtr]; EndPtr
0x1800405e0  inc     rcx; String
0x1800405e3  mov     r8d, edi; Radix
0x1800405e6  call    cs:__imp_strtoul
0x1800405ec  mov     [r14], ax
0x1800405f0  jmp     short loc_1800405F7
0x1800405f2  mov     ebx, 80004005h
0x1800405f7  mov     eax, ebx
0x1800405f9  mov     rcx, [rbp+8B0h+var_30]
0x180040600  xor     rcx, rbp; StackCookie
0x180040603  call    __security_check_cookie
0x180040608  lea     rsp, [rbp+890h]
0x18004060f  pop     r14
0x180040611  pop     rdi
0x180040612  pop     rsi
0x180040613  pop     rbx
0x180040614  pop     rbp
0x180040615  retn
```
