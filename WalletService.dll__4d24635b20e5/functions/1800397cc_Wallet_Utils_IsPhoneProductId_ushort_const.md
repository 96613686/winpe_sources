# Wallet::Utils::IsPhoneProductId(ushort const *)

- ea: `0x1800397cc`
- end: `0x180039833`
- name: `?IsPhoneProductId@Utils@Wallet@@YA_NPEBG@Z`
- size: `103`
- prototype: `bool __fastcall(LPCOLESTR lpsz, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026770`
- `0x18002d944`
- `0x180037064`
- `0x180037494`
- `0x1800396c8`

## callees

- `0x180039750`
- `0x1800397cc`
- `0x180043090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003980b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003980b`

## pseudocode

```c
bool __fastcall Wallet::Utils::IsPhoneProductId(OLECHAR *lpsz, const unsigned __int16 *a2)
{
  int v3; // ecx
  HRESULT v4; // eax
  GUID pclsid; // [rsp+20h] [rbp-28h] BYREF

  pclsid = 0;
  if ( *lpsz && Wallet::Utils::IsPhoneOS((Wallet::Utils *)lpsz) )
  {
    v4 = CLSIDFromString(lpsz, &pclsid);
    v3 = 0;
    if ( v4 < 0 )
      v3 = v4;
  }
  else
  {
    v3 = -2147024809;
  }
  return v3 >= 0;
}

```

## disassembly

```asm
0x1800397cc  push    rbx
0x1800397ce  sub     rsp, 40h
0x1800397d2  mov     rax, cs:__security_cookie
0x1800397d9  xor     rax, rsp
0x1800397dc  mov     [rsp+48h+var_18], rax
0x1800397e1  xor     eax, eax
0x1800397e3  xorps   xmm0, xmm0
0x1800397e6  mov     rbx, rcx
0x1800397e9  movups  xmmword ptr [rsp+48h+pclsid.Data1], xmm0
0x1800397ee  cmp     [rcx], ax
0x1800397f1  jnz     short loc_1800397FA
0x1800397f3  mov     ecx, 80070057h; this
0x1800397f8  jmp     short loc_180039818
0x1800397fa  call    ?IsPhoneOS@Utils@Wallet@@YA_NXZ; Wallet::Utils::IsPhoneOS(void)
0x1800397ff  test    al, al
0x180039801  jz      short loc_1800397F3
0x180039803  lea     rdx, [rsp+48h+pclsid]; pclsid
0x180039808  mov     rcx, rbx; lpsz
0x18003980b  call    cs:__imp_CLSIDFromString
0x180039811  xor     ecx, ecx
0x180039813  test    eax, eax
0x180039815  cmovs   ecx, eax
0x180039818  shr     ecx, 1Fh
0x18003981b  xor     cl, 1
0x18003981e  mov     al, cl
0x180039820  mov     rcx, [rsp+48h+var_18]
0x180039825  xor     rcx, rsp; StackCookie
0x180039828  call    __security_check_cookie
0x18003982d  add     rsp, 40h
0x180039831  pop     rbx
0x180039832  retn
```
