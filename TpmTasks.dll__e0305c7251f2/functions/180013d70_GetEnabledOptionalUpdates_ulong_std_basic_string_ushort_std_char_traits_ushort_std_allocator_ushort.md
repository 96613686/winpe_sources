# GetEnabledOptionalUpdates(ulong *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180013d70`
- end: `0x180013e11`
- name: `?GetEnabledOptionalUpdates@@YAXPEAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18001e5d0`

## callees

- `0x18000bc54`
- `0x180013d70`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180013da0`
- `ntdll!RtlInitUnicodeString` at `0x180013da0`
- `ntdll!NtQueryLicenseValue` at `0x180013dc0`
- `ntdll!NtQueryLicenseValue` at `0x180013dc0`

## string_xrefs

- `0x180013d8f`: `SecureBootServicingOptionalUpdates-Enabled`
- `0x180013ddc`: `DBXSVNUpdateWnc`
- `0x180013dd5`: ` | DBXSVNUpdateWnc`

## pseudocode

```c
__int64 __fastcall GetEnabledOptionalUpdates(int *a1, __int64 a2)
{
  int v4; // ebx
  __int64 result; // rax
  const wchar_t *v6; // rdx
  __int64 v7; // r8
  struct _UNICODE_STRING v8[2]; // [rsp+30h] [rbp-28h] BYREF
  int v9; // [rsp+60h] [rbp+8h] BYREF
  int v10; // [rsp+70h] [rbp+18h] BYREF

  v9 = 0;
  v10 = 0;
  v4 = 0;
  v8[0] = 0;
  RtlInitUnicodeString(v8, L"SecureBootServicingOptionalUpdates-Enabled");
  result = NtQueryLicenseValue(v8, 0, &v9, 4, &v10);
  if ( (int)result >= 0 && v9 == 1 )
  {
    v6 = L"DBXSVNUpdateWnc";
    v4 = 512;
    if ( *(_QWORD *)(a2 + 16) )
      v6 = L" | DBXSVNUpdateWnc";
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    result = std::wstring::_Append<unsigned short>(a2, v6, v7);
  }
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180013d70  mov     rax, rsp
0x180013d73  mov     [rax+10h], rbx
0x180013d77  push    rbp
0x180013d78  push    rsi
0x180013d79  push    rdi
0x180013d7a  sub     rsp, 40h
0x180013d7e  xor     ebp, ebp
0x180013d80  mov     rdi, rdx
0x180013d83  mov     rsi, rcx
0x180013d86  mov     [rax+8], ebp
0x180013d89  xorps   xmm0, xmm0
0x180013d8c  mov     [rax+18h], ebp
0x180013d8f  lea     rdx, SourceString; "SecureBootServicingOptionalUpdates-Enab"...
0x180013d96  mov     ebx, ebp
0x180013d98  lea     rcx, [rax-28h]; DestinationString
0x180013d9c  movups  xmmword ptr [rax-28h], xmm0
0x180013da0  call    cs:__imp_RtlInitUnicodeString
0x180013da6  lea     rax, [rsp+58h+arg_10]
0x180013dab  xor     edx, edx
0x180013dad  lea     r9d, [rbp+4]
0x180013db1  mov     [rsp+58h+var_38], rax
0x180013db6  lea     r8, [rsp+58h+arg_0]
0x180013dbb  lea     rcx, [rsp+58h+var_28]
0x180013dc0  call    cs:__imp_NtQueryLicenseValue
0x180013dc6  test    eax, eax
0x180013dc8  js      short loc_180013E02
0x180013dca  cmp     [rsp+58h+arg_0], 1
0x180013dcf  jnz     short loc_180013E02
0x180013dd1  cmp     [rdi+10h], rbp
0x180013dd5  lea     rax, aDbxsvnupdatewn_0; " | DBXSVNUpdateWnc"
0x180013ddc  lea     rdx, aDbxsvnupdatewn; "DBXSVNUpdateWnc"
0x180013de3  mov     ebx, 200h
0x180013de8  cmovnz  rdx, rax
0x180013dec  or      r8, 0FFFFFFFFFFFFFFFFh
0x180013df0  inc     r8
0x180013df3  cmp     [rdx+r8*2], bp
0x180013df8  jnz     short loc_180013DF0
0x180013dfa  mov     rcx, rdi
0x180013dfd  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180013e02  mov     [rsi], ebx
0x180013e04  mov     rbx, [rsp+58h+arg_8]
0x180013e09  add     rsp, 40h
0x180013e0d  pop     rdi
0x180013e0e  pop     rsi
0x180013e0f  pop     rbp
0x180013e10  retn
```
