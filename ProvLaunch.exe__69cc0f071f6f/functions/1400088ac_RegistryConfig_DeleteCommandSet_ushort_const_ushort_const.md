# RegistryConfig::DeleteCommandSet(ushort const *,ushort const *)

- ea: `0x1400088ac`
- end: `0x1400089d4`
- name: `?DeleteCommandSet@RegistryConfig@@QEAAXPEBG0@Z`
- size: `296`
- prototype: `void __fastcall(RegistryConfig *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140006e18`

## callees

- `0x140001008`
- `0x1400064d0`
- `0x140008484`
- `0x1400088ac`
- `0x14000a370`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000899a`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000899a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140008981`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140008981`

## string_xrefs

- `0x1400089c2`: `admin\prov\launch\lib\registryconfig.cpp`

## pseudocode

```c
void __fastcall RegistryConfig::DeleteCommandSet(
        RegistryConfig *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  char *v5; // rbx
  char *v6; // r9
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  int *v10; // rax
  const WCHAR *v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // [rsp+20h] [rbp-60h]
  int *v14; // [rsp+40h] [rbp-40h] BYREF
  int *v15; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v16[2]; // [rsp+50h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v18; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v5 = (char *)this + 8;
  if ( *((_QWORD *)this + 4) < 8u )
    v6 = (char *)this + 8;
  else
    v6 = *(char **)v5;
  RegistryConfig::AppendStrings((__int64)this, (char *)lpSubKey, 5, v6, L"\\", L"PrimaryContext", L"\\", a3);
  if ( (unsigned int)dword_140010000 > 4 )
  {
    v10 = (int *)lpSubKey;
    if ( v18 >= 8 )
      v10 = (int *)lpSubKey[0];
    v14 = v10;
    v15 = (int *)a3;
    if ( *((_QWORD *)v5 + 3) >= 8u )
      v5 = *(char **)v5;
    *(_QWORD *)v16 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v7,
      (__int64)byte_14000D733,
      v8,
      v9,
      (int **)v16,
      &v15,
      &v14);
  }
  v11 = (const WCHAR *)lpSubKey;
  if ( v18 >= 8 )
    v11 = lpSubKey[0];
  v12 = RegDeleteTreeW(*(HKEY *)this, v11);
  if ( v12 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xB7,
      (int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v12,
      v13);
  if ( v18 >= 8 )
    operator delete((void *)lpSubKey[0]);
}

```

## disassembly

```asm
0x1400088ac  mov     [rsp-18h+arg_8], rbx
0x1400088b1  push    rbp
0x1400088b2  push    rsi
0x1400088b3  push    rdi
0x1400088b4  mov     rbp, rsp
0x1400088b7  sub     rsp, 80h
0x1400088be  mov     rax, cs:__security_cookie
0x1400088c5  xor     rax, rsp
0x1400088c8  mov     [rbp+var_8], rax
0x1400088cc  mov     rsi, r8
0x1400088cf  mov     rdi, rcx
0x1400088d2  lea     rbx, [rcx+8]
0x1400088d6  cmp     qword ptr [rbx+18h], 8
0x1400088db  jb      short loc_1400088E2
0x1400088dd  mov     r9, [rbx]
0x1400088e0  jmp     short loc_1400088E5
0x1400088e2  mov     r9, rbx
0x1400088e5  mov     [rsp+80h+var_48], rsi
0x1400088ea  lea     rcx, asc_14000CE24; "\\"
0x1400088f1  mov     [rsp+80h+var_50], rcx
0x1400088f6  lea     rax, aPrimarycontext; "PrimaryContext"
0x1400088fd  mov     [rsp+80h+var_58], rax
0x140008902  mov     qword ptr [rsp+80h+var_60], rcx
0x140008907  mov     r8d, 5
0x14000890d  lea     rdx, [rbp+lpSubKey]
0x140008911  mov     rcx, rdi
0x140008914  call    ?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ; RegistryConfig::AppendStrings(int,...)
0x140008919  nop
0x14000891a  mov     eax, cs:dword_140010000
0x140008920  cmp     eax, 4
0x140008923  jbe     short loc_140008970
0x140008925  lea     rax, [rbp+lpSubKey]
0x140008929  cmp     [rbp+var_10], 8
0x14000892e  cmovnb  rax, [rbp+lpSubKey]
0x140008933  mov     [rbp+var_40], rax
0x140008937  mov     [rbp+var_38], rsi
0x14000893b  cmp     qword ptr [rbx+18h], 8
0x140008940  jb      short loc_140008945
0x140008942  mov     rbx, [rbx]
0x140008945  mov     qword ptr [rbp+var_30], rbx
0x140008949  lea     rax, [rbp+var_40]
0x14000894d  mov     [rsp+80h+var_50], rax
0x140008952  lea     rax, [rbp+var_38]
0x140008956  mov     [rsp+80h+var_58], rax
0x14000895b  lea     rax, [rbp+var_30]
0x14000895f  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x140008964  lea     rdx, byte_14000D733
0x14000896b  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140008970  lea     rdx, [rbp+lpSubKey]
0x140008974  cmp     [rbp+var_10], 8
0x140008979  cmovnb  rdx, [rbp+lpSubKey]; lpSubKey
0x14000897e  mov     rcx, [rdi]; hKey
0x140008981  call    cs:__imp_RegDeleteTreeW
0x140008987  mov     rcx, [rbp+18h]; this
0x14000898b  test    eax, eax
0x14000898d  jnz     short loc_1400089BF
0x14000898f  cmp     [rbp+var_10], 8
0x140008994  jb      short loc_1400089A0
0x140008996  mov     rcx, [rbp+lpSubKey]
0x14000899a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400089a0  mov     rcx, [rbp+var_8]
0x1400089a4  xor     rcx, rsp; StackCookie
0x1400089a7  call    __security_check_cookie
0x1400089ac  mov     rbx, [rsp+80h+arg_8]
0x1400089b4  add     rsp, 80h
0x1400089bb  pop     rdi
0x1400089bc  pop     rsi
0x1400089bd  pop     rbp
0x1400089be  retn
0x1400089bf  mov     r9d, eax; char *
0x1400089c2  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x1400089c9  mov     edx, 0B7h; void *
0x1400089ce  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
