# SystemSettings::StorageSenseHandlers::CAppBackgroundPermissionsSettingBase::IsApplicable(void)

- ea: `0x1800cb75c`
- end: `0x1800cb7d6`
- name: `?IsApplicable@CAppBackgroundPermissionsSettingBase@StorageSenseHandlers@SystemSettings@@IEAA_NXZ`
- size: `122`
- prototype: `bool __fastcall(SystemSettings::StorageSenseHandlers::CAppBackgroundPermissionsSettingBase *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800cc5c0`

## callees

- `0x1800cb75c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800cb78d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800cb7c0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800cb78d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800cb7c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cb76e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cb7a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cb76e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cb7a1`

## pseudocode

```c
bool __fastcall SystemSettings::StorageSenseHandlers::CAppBackgroundPermissionsSettingBase::IsApplicable(HSTRING *this)
{
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v3; // rax

  StringRawBuffer = WindowsGetStringRawBuffer(this[31], 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"MicrosoftWindows.Client.AIX_cw5n1h2txyewy", -1, 1) == 2 )
    return 0;
  v3 = WindowsGetStringRawBuffer(this[31], 0);
  return CompareStringOrdinal(v3, -1, L"MicrosoftWindows.Client.CoreAI_cw5n1h2txyewy", -1, 1) != 2;
}

```

## disassembly

```asm
0x1800cb75c  push    rbx
0x1800cb75e  sub     rsp, 30h
0x1800cb762  mov     rbx, rcx
0x1800cb765  xor     edx, edx; length
0x1800cb767  mov     rcx, [rcx+0F8h]; string
0x1800cb76e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cb774  or      r9d, 0FFFFFFFFh; cchCount2
0x1800cb778  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800cb780  or      edx, r9d; cchCount1
0x1800cb783  lea     r8, aMicrosoftwindo_1; "MicrosoftWindows.Client.AIX_cw5n1h2txye"...
0x1800cb78a  mov     rcx, rax; lpString1
0x1800cb78d  call    cs:__imp_CompareStringOrdinal
0x1800cb793  cmp     eax, 2
0x1800cb796  jz      short loc_1800CB7CE
0x1800cb798  mov     rcx, [rbx+0F8h]; string
0x1800cb79f  xor     edx, edx; length
0x1800cb7a1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cb7a7  or      r9d, 0FFFFFFFFh; cchCount2
0x1800cb7ab  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800cb7b3  or      edx, r9d; cchCount1
0x1800cb7b6  lea     r8, aMicrosoftwindo_11; "MicrosoftWindows.Client.CoreAI_cw5n1h2t"...
0x1800cb7bd  mov     rcx, rax; lpString1
0x1800cb7c0  call    cs:__imp_CompareStringOrdinal
0x1800cb7c6  cmp     eax, 2
0x1800cb7c9  setnz   al
0x1800cb7cc  jmp     short loc_1800CB7D0
0x1800cb7ce  xor     al, al
0x1800cb7d0  add     rsp, 30h
0x1800cb7d4  pop     rbx
0x1800cb7d5  retn
```
