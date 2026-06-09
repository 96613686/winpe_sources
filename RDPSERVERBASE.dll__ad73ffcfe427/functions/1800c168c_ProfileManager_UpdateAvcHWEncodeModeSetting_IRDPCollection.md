# ProfileManager::UpdateAvcHWEncodeModeSetting(IRDPCollection *)

- ea: `0x1800c168c`
- end: `0x1800c17f0`
- name: `?UpdateAvcHWEncodeModeSetting@ProfileManager@@AEAAXPEAUIRDPCollection@@@Z`
- size: `356`
- prototype: `void __fastcall(ProfileManager *__hidden this, struct IRDPCollection *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c06b8`

## callees

- `0x180001308`
- `0x1800c168c`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c175b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c175b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c1720`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c1720`

## string_xrefs

- `0x1800c1712`: `Software\Policies\Microsoft\Windows NT\Terminal Services\H264Encoding`
- `0x1800c1790`: `UpdateAvcHWEncodeModeSetting: AVC HW Encode Mode is preferred for this session`
- `0x1800c17b0`: `UpdateAvcHWEncodeModeSetting: AVC HW Encode Mode is required for this session`
- `0x1800c17c5`: `UpdateAvcHWEncodeModeSetting: AVC HW Encode Mode not requested for this session`

## pseudocode

```c
void __fastcall ProfileManager::UpdateAvcHWEncodeModeSetting(ProfileManager *this, struct IRDPCollection *a2)
{
  __int64 v2; // rax
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int v7; // eax
  const char *v8; // rax
  __int16 *v9; // rdx
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  int v12; // [rsp+58h] [rbp+18h] BYREF
  const char *Type; // [rsp+60h] [rbp+20h] BYREF
  int Data; // [rsp+68h] [rbp+28h] BYREF

  v2 = *(_QWORD *)a2;
  v12 = 0;
  if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, int *))(v2 + 40))(
         a2,
         L"GfxPipeline::AVCHwEncodePreferred",
         &v12) < 0 )
    return;
  if ( v12 != 1 )
  {
    if ( v12 == 2 )
    {
      if ( !*((_DWORD *)this + 59) )
        goto LABEL_9;
    }
    else if ( v12 != 3 || *((_DWORD *)this + 59) )
    {
      goto LABEL_9;
    }
  }
  *((_DWORD *)this + 68) = 1;
LABEL_9:
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\H264Encoding",
          0,
          0x20019u,
          &hKey) )
  {
    Data = 0;
    LODWORD(Type) = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnableAvcHWEncode", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData) && (_DWORD)Type == 4 )
    {
      if ( Data )
        *((_DWORD *)this + 68) = 2;
    }
  }
  v7 = *((_DWORD *)this + 68);
  if ( v7 == 1 )
  {
    if ( (unsigned int)CallbackContext <= 4 )
      return;
    v8 = "UpdateAvcHWEncodeModeSetting: AVC HW Encode Mode is preferred for this session";
    v9 = (__int16 *)&unk_18027E6A8;
  }
  else if ( v7 == 2 )
  {
    if ( (unsigned int)CallbackContext <= 4 )
      return;
    v8 = "UpdateAvcHWEncodeModeSetting: AVC HW Encode Mode is required for this session";
    v9 = (__int16 *)&byte_18027E67F;
  }
  else
  {
    if ( (unsigned int)CallbackContext <= 4 )
      return;
    v8 = "UpdateAvcHWEncodeModeSetting: AVC HW Encode Mode not requested for this session";
    v9 = &word_18027E656;
  }
  Type = v8;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
    v4,
    (_DWORD)v9,
    v5,
    v6,
    (__int64)&Type);
}

```

## disassembly

```asm
0x1800c168c  mov     [rsp-8+arg_0], rbx
0x1800c1691  push    rbp
0x1800c1692  mov     rbp, rsp
0x1800c1695  sub     rsp, 40h
0x1800c1699  mov     rax, [rdx]
0x1800c169c  lea     r8, [rbp+arg_8]
0x1800c16a0  mov     r9, rdx
0x1800c16a3  mov     [rbp+arg_8], 0
0x1800c16aa  mov     rbx, rcx
0x1800c16ad  lea     rdx, aGfxpipelineAvc; "GfxPipeline::AVCHwEncodePreferred"
0x1800c16b4  mov     rcx, r9
0x1800c16b7  mov     rax, [rax+28h]
0x1800c16bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c16c0  test    eax, eax
0x1800c16c2  js      loc_1800C17E5
0x1800c16c8  mov     eax, [rbp+arg_8]
0x1800c16cb  sub     eax, 1
0x1800c16ce  jz      short loc_1800C16EE
0x1800c16d0  sub     eax, 1
0x1800c16d3  jz      short loc_1800C16E5
0x1800c16d5  cmp     eax, 1
0x1800c16d8  jnz     short loc_1800C16F8
0x1800c16da  cmp     dword ptr [rbx+0ECh], 0
0x1800c16e1  jz      short loc_1800C16EE
0x1800c16e3  jmp     short loc_1800C16F8
0x1800c16e5  cmp     dword ptr [rbx+0ECh], 0
0x1800c16ec  jz      short loc_1800C16F8
0x1800c16ee  mov     dword ptr [rbx+110h], 1
0x1800c16f8  lea     rax, [rbp+hKey]
0x1800c16fc  mov     [rbp+hKey], 0
0x1800c1704  mov     r9d, 20019h; samDesired
0x1800c170a  mov     [rsp+40h+phkResult], rax; phkResult
0x1800c170f  xor     r8d, r8d; ulOptions
0x1800c1712  lea     rdx, aSoftwarePolici_7; "Software\\Policies\\Microsoft\\Windows "...
0x1800c1719  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c1720  call    cs:__imp_RegOpenKeyExW
0x1800c1726  test    eax, eax
0x1800c1728  jnz     short loc_1800C177A
0x1800c172a  mov     rcx, [rbp+hKey]; hKey
0x1800c172e  lea     r9, [rbp+Type]; lpType
0x1800c1732  mov     [rbp+Data], eax
0x1800c1735  lea     rdx, aEnableavchwenc; "EnableAvcHWEncode"
0x1800c173c  mov     dword ptr [rbp+Type], eax
0x1800c173f  xor     r8d, r8d; lpReserved
0x1800c1742  lea     rax, [rbp+cbData]
0x1800c1746  mov     [rbp+cbData], 4
0x1800c174d  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800c1752  lea     rax, [rbp+Data]
0x1800c1756  mov     [rsp+40h+phkResult], rax; lpData
0x1800c175b  call    cs:__imp_RegQueryValueExW
0x1800c1761  test    eax, eax
0x1800c1763  jnz     short loc_1800C177A
0x1800c1765  cmp     dword ptr [rbp+Type], 4
0x1800c1769  jnz     short loc_1800C177A
0x1800c176b  cmp     [rbp+Data], eax
0x1800c176e  jz      short loc_1800C177A
0x1800c1770  mov     dword ptr [rbx+110h], 2
0x1800c177a  mov     eax, [rbx+110h]
0x1800c1780  cmp     eax, 1
0x1800c1783  jnz     short loc_1800C17A0
0x1800c1785  mov     eax, cs:CallbackContext
0x1800c178b  cmp     eax, 4
0x1800c178e  jbe     short loc_1800C17E5
0x1800c1790  lea     rax, aUpdateavchwenc_0; "UpdateAvcHWEncodeModeSetting: AVC HW En"...
0x1800c1797  lea     rdx, unk_18027E6A8
0x1800c179e  jmp     short loc_1800C17D3
0x1800c17a0  cmp     eax, 2
0x1800c17a3  mov     eax, cs:CallbackContext
0x1800c17a9  jnz     short loc_1800C17C0
0x1800c17ab  cmp     eax, 4
0x1800c17ae  jbe     short loc_1800C17E5
0x1800c17b0  lea     rax, aUpdateavchwenc_1; "UpdateAvcHWEncodeModeSetting: AVC HW En"...
0x1800c17b7  lea     rdx, byte_18027E67F
0x1800c17be  jmp     short loc_1800C17D3
0x1800c17c0  cmp     eax, 4
0x1800c17c3  jbe     short loc_1800C17E5
0x1800c17c5  lea     rax, aUpdateavchwenc; "UpdateAvcHWEncodeModeSetting: AVC HW En"...
0x1800c17cc  lea     rdx, word_18027E656
0x1800c17d3  mov     [rbp+Type], rax
0x1800c17d7  lea     rax, [rbp+Type]
0x1800c17db  mov     [rsp+40h+phkResult], rax
0x1800c17e0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800c17e5  mov     rbx, [rsp+40h+arg_0]
0x1800c17ea  add     rsp, 40h
0x1800c17ee  pop     rbp
0x1800c17ef  retn
```
