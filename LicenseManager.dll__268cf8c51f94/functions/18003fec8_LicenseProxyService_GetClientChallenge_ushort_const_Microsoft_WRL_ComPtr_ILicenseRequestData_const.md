# LicenseProxyService::GetClientChallenge(ushort const *,Microsoft::WRL::ComPtr<ILicenseRequestData> const &)

- ea: `0x18003fec8`
- end: `0x18003ffb5`
- name: `?GetClientChallenge@LicenseProxyService@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEBV?$ComPtr@UILicenseRequestData@@@WRL@Microsoft@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008e70`
- `0x18003fcd4`

## callees

- `0x18003fec8`
- `0x18003ffe0`
- `0x1800593bc`
- `0x180081360`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ff7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ff7d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003ff9b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003ff9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ff5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ff5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void *__fastcall LicenseProxyService::GetClientChallenge(void *Src, __int64 a2, __int64 **a3)
{
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // eax
  int v8[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  int v10; // [rsp+70h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+28h] BYREF

  v10 = 0;
  *(_QWORD *)v8 = 0;
  pv = 0;
  v4 = *a3;
  v5 = **a3;
  pv = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, LPVOID *, int *))(v5 + 32))(v4, a2, &pv, &v10);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x809,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      (const char *)(unsigned int)v6,
      (int)v8);
  _to_base64(Src);
  if ( pv )
    CoTaskMemFree(pv);
  return Src;
}

```

## disassembly

```asm
0x18003fec8  mov     [rsp-8+arg_0], rbx
0x18003fecd  mov     [rsp-8+arg_8], rsi
0x18003fed2  push    rbp
0x18003fed3  mov     rbp, rsp
0x18003fed6  sub     rsp, 50h
0x18003feda  mov     rbx, rcx
0x18003fedd  mov     [rbp+arg_10], 0
0x18003fee4  lea     rsi, ??_7?$HandleT@UCoTaskMemBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::`vftable'
0x18003feeb  mov     [rbp+var_18], rsi
0x18003feef  mov     qword ptr [rbp+var_10], 0
0x18003fef7  mov     [rbp+pv], 0
0x18003feff  mov     rcx, [r8]
0x18003ff02  mov     rax, [rcx]
0x18003ff05  mov     [rbp+pv], 0
0x18003ff0d  lea     r8, [rbp+var_10]
0x18003ff11  mov     qword ptr [rsp+50h+var_30], r8; int
0x18003ff16  lea     r9, [rbp+arg_10]
0x18003ff1a  lea     r8, [rbp+pv]
0x18003ff1e  mov     rax, [rax+20h]
0x18003ff22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff27  mov     rcx, [rbp+8]; this
0x18003ff2b  test    eax, eax
0x18003ff2d  jns     short loc_18003FF44
0x18003ff2f  mov     r9d, eax; char *
0x18003ff32  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18003ff39  mov     edx, 809h; void *
0x18003ff3e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003ff44  mov     r8d, [rbp+arg_10]
0x18003ff48  mov     rdx, qword ptr [rbp+var_10]
0x18003ff4c  mov     rcx, rbx; Src
0x18003ff4f  call    ?_to_base64@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBE_K@Z; _to_base64(uchar const *,unsigned __int64)
0x18003ff54  nop
0x18003ff55  mov     rcx, [rbp+pv]; pv
0x18003ff59  test    rcx, rcx
0x18003ff5c  jz      short loc_18003FF65
0x18003ff5e  call    cs:__imp_CoTaskMemFree
0x18003ff64  nop
0x18003ff65  mov     [rbp+var_18], rsi
0x18003ff69  cmp     qword ptr [rbp+var_10], 0
0x18003ff6e  jz      short loc_18003FFA2
0x18003ff70  lea     rcx, [rbp+var_18]
0x18003ff74  call    ?InternalClose@?$HandleT@UCoTaskMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::InternalClose(void)
0x18003ff79  test    al, al
0x18003ff7b  jnz     short loc_18003FFA2
0x18003ff7d  call    cs:__imp_GetLastError
0x18003ff83  test    eax, eax
0x18003ff85  jle     short loc_18003FF8F
0x18003ff87  movzx   eax, ax
0x18003ff8a  or      eax, 80070000h
0x18003ff8f  xor     r9d, r9d; lpArguments
0x18003ff92  xor     r8d, r8d; nNumberOfArguments
0x18003ff95  lea     edx, [r9+1]; dwExceptionFlags
0x18003ff99  mov     ecx, eax; dwExceptionCode
0x18003ff9b  call    cs:__imp_RaiseException
0x18003ffa1  int     3; Trap to Debugger
0x18003ffa2  mov     rax, rbx
0x18003ffa5  mov     rbx, [rsp+50h+arg_0]
0x18003ffaa  mov     rsi, [rsp+50h+arg_8]
0x18003ffaf  add     rsp, 50h
0x18003ffb3  pop     rbp
0x18003ffb4  retn
```
