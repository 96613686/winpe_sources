# DeleteRebootCSPTaskInRegistry(ushort const *,RecurrenceFrequency)

- ea: `0x18005f760`
- end: `0x18005f826`
- name: `?DeleteRebootCSPTaskInRegistry@@YAXPEBGW4RecurrenceFrequency@@@Z`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x180007270`
- `0x180058420`
- `0x18005bb38`
- `0x18005f760`
- `0x18005fb68`
- `0x18005fb90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005f7e4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005f7e4`

## pseudocode

```c
void __fastcall DeleteRebootCSPTaskInRegistry(__int64 a1, int a2)
{
  const unsigned __int16 *v4; // r8
  int v5; // eax
  unsigned int v6; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  unsigned int SubKey[64]; // [rsp+20h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  if ( isSupportedSkuOnWCOS() )
  {
    v4 = qword_18010E290;
    if ( !a2 )
      v4 = qword_18010E298;
    v5 = StringCchPrintfW((unsigned __int16 *)SubKey, 0x80u, v4, a1);
    if ( v5 >= 0 )
    {
      v6 = RegDeleteKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)SubKey, 0, 0);
      if ( v6 )
        wil::details::in1diag3::_Log_Win32(retaddr, v7, v8, (const char *)v6, SubKey[0]);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\miscutils\\rebootcsputils.cpp",
        (const char *)(unsigned int)v5,
        SubKey[0]);
    }
  }
}

```

## disassembly

```asm
0x18005f760  mov     [rsp+arg_8], rbx
0x18005f765  push    rdi
0x18005f766  sub     rsp, 130h
0x18005f76d  mov     rax, cs:__security_cookie
0x18005f774  xor     rax, rsp
0x18005f777  mov     [rsp+138h+var_18], rax
0x18005f77f  mov     ebx, edx
0x18005f781  mov     rdi, rcx
0x18005f784  call    ?isSupportedSkuOnWCOS@@YA_NXZ; isSupportedSkuOnWCOS(void)
0x18005f789  test    al, al
0x18005f78b  jz      short loc_18005F804
0x18005f78d  mov     r8, cs:qword_18010E290
0x18005f794  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x18005f799  test    ebx, ebx
0x18005f79b  mov     r9, rdi
0x18005f79e  mov     edx, 80h; unsigned __int64
0x18005f7a3  cmovz   r8, cs:qword_18010E298; unsigned __int16 *
0x18005f7ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005f7b0  test    eax, eax
0x18005f7b2  jns     short loc_18005F7D2
0x18005f7b4  mov     rcx, [rsp+138h]; this
0x18005f7bc  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\dm\\dmcmnutils\\misc"...
0x18005f7c3  mov     r9d, eax; char *
0x18005f7c6  mov     edx, 97h; void *
0x18005f7cb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005f7d0  jmp     short loc_18005F804
0x18005f7d2  xor     r9d, r9d; Reserved
0x18005f7d5  lea     rdx, [rsp+138h+SubKey]; lpSubKey
0x18005f7da  xor     r8d, r8d; samDesired
0x18005f7dd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005f7e4  call    cs:__imp_RegDeleteKeyExW
0x18005f7eb  nop     dword ptr [rax+rax+00h]
0x18005f7f0  test    eax, eax
0x18005f7f2  jz      short loc_18005F804
0x18005f7f4  mov     rcx, [rsp+138h]; this
0x18005f7fc  mov     r9d, eax; char *
0x18005f7ff  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18005f804  mov     rcx, [rsp+138h+var_18]
0x18005f80c  xor     rcx, rsp; StackCookie
0x18005f80f  call    __security_check_cookie
0x18005f814  mov     rbx, [rsp+138h+arg_8]
0x18005f81c  add     rsp, 130h
0x18005f823  pop     rdi
0x18005f824  retn
```
