# Wallet::Utils::CreateReadDeleteDssTokenForService(ushort const *,tlx::unique_any<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>> &)

- ea: `0x18003772c`
- end: `0x1800377dc`
- name: `?CreateReadDeleteDssTokenForService@Utils@Wallet@@YAJPEBGAEAV?$unique_any@U?$handle_traits@PEAGP6AXPEAG@Z$1?DSFreeString@@YAX0@Z$0A@@tlx@@@tlx@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180035260`

## callees

- `0x18001aa00`
- `0x180043052`
- `0x180043090`

## import_xrefs

- `dsclient!DSCreateSharedFileToken` at `0x1800377ac`
- `dsclient!DSCreateSharedFileToken` at `0x1800377ac`

## pseudocode

```c
__int64 __fastcall Wallet::Utils::CreateReadDeleteDssTokenForService(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  int v5; // eax
  unsigned int v6; // ecx
  _DWORD v8[2]; // [rsp+30h] [rbp-168h] BYREF
  __int64 v9; // [rsp+38h] [rbp-160h]
  __int64 v10; // [rsp+40h] [rbp-158h]
  const wchar_t *v11; // [rsp+48h] [rbp-150h]
  _BYTE v12[304]; // [rsp+50h] [rbp-148h] BYREF

  v8[0] = 0;
  v8[1] = 5;
  v9 = 1;
  v11 = L"S-1-5-18";
  v10 = 0;
  memset_0(v12, 0, sizeof(v12));
  v4 = tlx::replace<tlx::handle_traits<unsigned short *,void (*)(unsigned short *),&void DSFreeString(unsigned short *),0>>(a2);
  v5 = DSCreateSharedFileToken(a1, v8, 0, 0, v4);
  v6 = 0;
  if ( v5 < 0 )
    return (unsigned int)v5;
  return v6;
}

```

## disassembly

```asm
0x18003772c  mov     [rsp+arg_10], rbx
0x180037731  push    rdi
0x180037732  sub     rsp, 190h
0x180037739  mov     rax, cs:__security_cookie
0x180037740  xor     rax, rsp
0x180037743  mov     [rsp+198h+var_18], rax
0x18003774b  mov     rbx, rdx
0x18003774e  mov     [rsp+198h+var_168], 0
0x180037756  mov     rdi, rcx
0x180037759  mov     [rsp+198h+var_164], 5
0x180037761  lea     rax, aS1518; "S-1-5-18"
0x180037768  mov     [rsp+198h+var_160], 1
0x180037771  xor     edx, edx; Val
0x180037773  mov     [rsp+198h+var_150], rax
0x180037778  lea     rcx, [rsp+198h+var_148]; void *
0x18003777d  mov     [rsp+198h+var_158], 0
0x180037786  mov     r8d, 130h; Size
0x18003778c  call    memset_0
0x180037791  mov     rcx, rbx
0x180037794  call    ??$replace@U?$handle_traits@PEAGP6AXPEAG@Z$1?DSFreeString@@YAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAGAEAV?$unique_any@U?$handle_traits@PEAGP6AXPEAG@Z$1?DSFreeString@@YAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>>(tlx::unique_any<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>> &)
0x180037799  xor     r9d, r9d
0x18003779c  mov     [rsp+198h+var_178], rax
0x1800377a1  xor     r8d, r8d
0x1800377a4  lea     rdx, [rsp+198h+var_168]
0x1800377a9  mov     rcx, rdi
0x1800377ac  call    cs:__imp_DSCreateSharedFileToken
0x1800377b2  xor     ecx, ecx
0x1800377b4  test    eax, eax
0x1800377b6  cmovs   ecx, eax
0x1800377b9  mov     eax, ecx
0x1800377bb  mov     rcx, [rsp+198h+var_18]
0x1800377c3  xor     rcx, rsp; StackCookie
0x1800377c6  call    __security_check_cookie
0x1800377cb  mov     rbx, [rsp+198h+arg_10]
0x1800377d3  add     rsp, 190h
0x1800377da  pop     rdi
0x1800377db  retn
```
