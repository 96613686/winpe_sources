# WaaSProtectedSettingsProvider::ProtectFolderSecurityDescriptor(HSTRING__ *,HSTRING__ *)

- ea: `0x18003a540`
- end: `0x18003a64d`
- name: `?ProtectFolderSecurityDescriptor@WaaSProtectedSettingsProvider@@UEAAJPEAUHSTRING__@@0@Z`
- size: `269`
- prototype: `__int64 __fastcall(WaaSProtectedSettingsProvider *this, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x1800050a0`
- `0x180009cd0`
- `0x18002e81c`
- `0x180035018`
- `0x18003a540`
- `0x1800687a4`
- `0x180069254`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a574`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a574`

## string_xrefs

- `0x18003a605`: `Failed to persist the security descriptor to store. It won't be possible to restore. Error code: 0x%08x`
- `0x18003a5b7`: `Could not verify access to folder path: %s. Error code: 0x%08x.`
- `0x18003a5d4`: `Caller was not allowed to write to the requested folder path: %s`

## pseudocode

```c
__int64 __fastcall WaaSProtectedSettingsProvider::ProtectFolderSecurityDescriptor(
        WaaSProtectedSettingsProvider *this,
        HSTRING a2,
        HSTRING a3)
{
  WaasMedic::ProtectedSettingsNamespaceMapper *StringRawBuffer; // rdi
  const unsigned __int16 *v5; // rsi
  bool *v6; // r8
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned __int16 v11; // [rsp+20h] [rbp-38h] BYREF
  _OWORD v12[2]; // [rsp+28h] [rbp-30h] BYREF

  StringRawBuffer = (WaasMedic::ProtectedSettingsNamespaceMapper *)WindowsGetStringRawBuffer(a2, 0);
  v5 = WindowsGetStringRawBuffer(a3, 0);
  v12[0] = 0;
  v12[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v12[0]) = 0;
  LOBYTE(v11) = 0;
  v7 = WaasMedic::ProtectedSettingsNamespaceMapper::IsCallerAllowedToWriteToFolderPath(StringRawBuffer, &v11, v6);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( (_BYTE)v11 )
    {
      v9 = WaasMedic::SecurityDescriptorProtector::ProtectSecurityDescriptor(
             (WaasMedic::SecurityDescriptorProtector *)v12,
             (const unsigned __int16 *)StringRawBuffer,
             v5);
      v8 = v9;
      if ( v9 < 0 )
        LogLevelW(
          2u,
          L"Failed to persist the security descriptor to store. It won't be possible to restore. Error code: 0x%08x",
          (unsigned int)v9);
    }
    else
    {
      LogLevelW(4u, L"Caller was not allowed to write to the requested folder path: %s", StringRawBuffer);
      v8 = -2147024891;
    }
  }
  else
  {
    LogLevelW(2u, L"Could not verify access to folder path: %s. Error code: 0x%08x.", StringRawBuffer, (unsigned int)v7);
  }
  WaasMedic::TelemetryProvider::ReportSecurityDescriptorProtectionResult(
    v8,
    (const unsigned __int16 *)StringRawBuffer,
    1);
  std::wstring::~wstring(v12);
  return v8;
}

```

## disassembly

```asm
0x18003a540  mov     [rsp+arg_0], rbx
0x18003a545  mov     [rsp+arg_18], rsi
0x18003a54a  push    rdi
0x18003a54b  sub     rsp, 50h
0x18003a54f  mov     rax, cs:__security_cookie
0x18003a556  xor     rax, rsp
0x18003a559  mov     [rsp+58h+var_10], rax
0x18003a55e  mov     rbx, r8
0x18003a561  mov     rcx, rdx; string
0x18003a564  xor     edx, edx; length
0x18003a566  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a56c  mov     rdi, rax
0x18003a56f  xor     edx, edx; length
0x18003a571  mov     rcx, rbx; string
0x18003a574  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a57a  mov     rsi, rax
0x18003a57d  xorps   xmm0, xmm0
0x18003a580  movups  [rsp+58h+var_30], xmm0
0x18003a585  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003a58d  movdqu  [rsp+58h+var_20], xmm1
0x18003a593  xor     ecx, ecx
0x18003a595  mov     word ptr [rsp+58h+var_30], cx
0x18003a59a  mov     byte ptr [rsp+58h+var_38], cl
0x18003a59e  lea     rdx, [rsp+58h+var_38]; unsigned __int16 *
0x18003a5a3  mov     rcx, rdi; this
0x18003a5a6  call    ?IsCallerAllowedToWriteToFolderPath@ProtectedSettingsNamespaceMapper@WaasMedic@@YAJPEBGAEA_N@Z; WaasMedic::ProtectedSettingsNamespaceMapper::IsCallerAllowedToWriteToFolderPath(ushort const *,bool &)
0x18003a5ab  mov     ebx, eax
0x18003a5ad  test    eax, eax
0x18003a5af  jns     short loc_18003A5CA
0x18003a5b1  mov     r9d, eax
0x18003a5b4  mov     r8, rdi
0x18003a5b7  lea     rdx, aCouldNotVerify_2; "Could not verify access to folder path:"...
0x18003a5be  mov     ecx, 2; unsigned __int8
0x18003a5c3  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003a5c8  jmp     short loc_18003A616
0x18003a5ca  cmp     byte ptr [rsp+58h+var_38], 0
0x18003a5cf  jnz     short loc_18003A5EC
0x18003a5d1  mov     r8, rdi
0x18003a5d4  lea     rdx, aCallerWasNotAl; "Caller was not allowed to write to the "...
0x18003a5db  mov     ecx, 4; unsigned __int8
0x18003a5e0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003a5e5  mov     ebx, 80070005h
0x18003a5ea  jmp     short loc_18003A616
0x18003a5ec  mov     r8, rsi; unsigned __int16 *
0x18003a5ef  mov     rdx, rdi; unsigned __int16 *
0x18003a5f2  lea     rcx, [rsp+58h+var_30]; this
0x18003a5f7  call    ?ProtectSecurityDescriptor@SecurityDescriptorProtector@WaasMedic@@QEAAJPEBG0@Z; WaasMedic::SecurityDescriptorProtector::ProtectSecurityDescriptor(ushort const *,ushort const *)
0x18003a5fc  mov     ebx, eax
0x18003a5fe  test    eax, eax
0x18003a600  jns     short loc_18003A616
0x18003a602  mov     r8d, eax
0x18003a605  lea     rdx, aFailedToPersis; "Failed to persist the security descript"...
0x18003a60c  mov     ecx, 2; unsigned __int8
0x18003a611  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003a616  mov     r8b, 1; bool
0x18003a619  mov     rdx, rdi; unsigned __int16 *
0x18003a61c  mov     ecx, ebx; int
0x18003a61e  call    ?ReportSecurityDescriptorProtectionResult@TelemetryProvider@WaasMedic@@SAXJPEBG_N@Z; WaasMedic::TelemetryProvider::ReportSecurityDescriptorProtectionResult(long,ushort const *,bool)
0x18003a623  nop
0x18003a624  lea     rcx, [rsp+58h+var_30]; void *
0x18003a629  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a62e  mov     eax, ebx
0x18003a630  mov     rcx, [rsp+58h+var_10]
0x18003a635  xor     rcx, rsp; StackCookie
0x18003a638  call    __security_check_cookie
0x18003a63d  mov     rbx, [rsp+58h+arg_0]
0x18003a642  mov     rsi, [rsp+58h+arg_18]
0x18003a647  add     rsp, 50h
0x18003a64b  pop     rdi
0x18003a64c  retn
```
