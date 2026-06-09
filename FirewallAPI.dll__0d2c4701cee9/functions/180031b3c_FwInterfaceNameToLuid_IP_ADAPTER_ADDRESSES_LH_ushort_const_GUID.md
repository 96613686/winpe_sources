# FwInterfaceNameToLuid(_IP_ADAPTER_ADDRESSES_LH *,ushort * const,_GUID *)

- ea: `0x180031b3c`
- end: `0x180031cdc`
- name: `?FwInterfaceNameToLuid@@YAJPEAU_IP_ADAPTER_ADDRESSES_LH@@QEAGPEAU_GUID@@@Z`
- size: `416`
- prototype: `int(struct _IP_ADAPTER_ADDRESSES_LH *, unsigned __int16 *const, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800324fc`

## callees

- `0x180005e0c`
- `0x180024cb0`
- `0x1800294b0`
- `0x18002a1f4`
- `0x180031b3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c52`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031b96`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031b96`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180031c1c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180031ca6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180031c1c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180031ca6`

## pseudocode

```c
__int64 __fastcall FwInterfaceNameToLuid(
        struct _IP_ADAPTER_ADDRESSES_LH *a1,
        unsigned __int16 *const a2,
        struct _GUID *a3)
{
  int v6; // eax
  int v7; // ebx
  FwPolicy2 *v8; // rcx
  __int64 v9; // rdx
  signed int LastError; // eax
  wchar_t pszDest; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v13[78]; // [rsp+32h] [rbp-76h] BYREF

  *a3 = GUID_NULL;
  while ( 1 )
  {
    if ( !a1 )
    {
      v7 = CLSIDFromString(a2, a3);
      if ( v7 < 0 )
        return (unsigned int)-2147023728;
      return (unsigned int)v7;
    }
    v6 = CompareStringW(0x7Fu, 1u, a2, -1, a1->FriendlyName, -1);
    if ( !v6 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 52;
        goto LABEL_19;
      }
      return (unsigned int)v7;
    }
    if ( v6 == 2 )
      break;
    a1 = a1->Next;
  }
  pszDest = 0;
  memset_0(v13, 0, sizeof(v13));
  v7 = StringCchPrintfW(&pszDest, 0x27u, L"%S", a1->AdapterName);
  if ( v7 >= 0 )
  {
    v7 = CLSIDFromString(&pszDest, a3);
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 54;
        goto LABEL_19;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 53;
LABEL_19:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, (unsigned int)v7);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180031b3c  push    rbx
0x180031b3e  push    rsi
0x180031b3f  push    rdi
0x180031b40  sub     rsp, 90h
0x180031b47  mov     rax, cs:__security_cookie
0x180031b4e  xor     rax, rsp
0x180031b51  mov     [rsp+0A8h+var_28], rax
0x180031b59  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180031b60  mov     rdi, r8
0x180031b63  mov     rsi, rdx
0x180031b66  mov     rbx, rcx
0x180031b69  movdqu  xmmword ptr [r8], xmm0
0x180031b6e  test    rbx, rbx
0x180031b71  jz      loc_180031CA0
0x180031b77  mov     rax, [rbx+48h]
0x180031b7b  or      r9d, 0FFFFFFFFh; cchCount1
0x180031b7f  mov     [rsp+0A8h+cchCount2], 0FFFFFFFFh; cchCount2
0x180031b87  mov     r8, rsi; lpString1
0x180031b8a  mov     [rsp+0A8h+lpString2], rax; lpString2
0x180031b8f  lea     edx, [r9+2]; dwCmpFlags
0x180031b93  lea     ecx, [rdx+7Eh]; Locale
0x180031b96  call    cs:__imp_CompareStringW
0x180031b9d  nop     dword ptr [rax+rax+00h]
0x180031ba2  test    eax, eax
0x180031ba4  jz      loc_180031C52
0x180031baa  cmp     eax, 2
0x180031bad  jz      short loc_180031BB5
0x180031baf  mov     rbx, [rbx+8]
0x180031bb3  jmp     short loc_180031B6E
0x180031bb5  xor     eax, eax
0x180031bb7  lea     rcx, [rsp+0A8h+var_76]; void *
0x180031bbc  xor     edx, edx; Val
0x180031bbe  mov     [rsp+0A8h+pszDest], ax
0x180031bc3  lea     r8d, [rax+4Eh]; Size
0x180031bc7  call    memset_0
0x180031bcc  mov     r9, [rbx+10h]
0x180031bd0  lea     r8, aS_0; "%S"
0x180031bd7  mov     edx, 27h ; '''; cchDest
0x180031bdc  lea     rcx, [rsp+0A8h+pszDest]; pszDest
0x180031be1  call    StringCchPrintfW
0x180031be6  mov     ebx, eax
0x180031be8  test    eax, eax
0x180031bea  jns     short loc_180031C14
0x180031bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180031bf3  lea     rax, WPP_GLOBAL_Control
0x180031bfa  cmp     rcx, rax
0x180031bfd  jz      loc_180031CBE
0x180031c03  test    byte ptr [rcx+1Ch], 1
0x180031c07  jz      loc_180031CBE
0x180031c0d  mov     edx, 35h ; '5'
0x180031c12  jmp     short loc_180031C8B
0x180031c14  mov     rdx, rdi; pclsid
0x180031c17  lea     rcx, [rsp+0A8h+pszDest]; lpsz
0x180031c1c  call    cs:__imp_CLSIDFromString
0x180031c23  nop     dword ptr [rax+rax+00h]
0x180031c28  mov     ebx, eax
0x180031c2a  test    eax, eax
0x180031c2c  jns     loc_180031CBE
0x180031c32  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c39  lea     rax, WPP_GLOBAL_Control
0x180031c40  cmp     rcx, rax
0x180031c43  jz      short loc_180031CBE
0x180031c45  test    byte ptr [rcx+1Ch], 1
0x180031c49  jz      short loc_180031CBE
0x180031c4b  mov     edx, 36h ; '6'
0x180031c50  jmp     short loc_180031C8B
0x180031c52  call    cs:__imp_GetLastError
0x180031c59  nop     dword ptr [rax+rax+00h]
0x180031c5e  mov     ebx, eax
0x180031c60  test    eax, eax
0x180031c62  jle     short loc_180031C6D
0x180031c64  movzx   ebx, ax
0x180031c67  or      ebx, 80070000h
0x180031c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c74  lea     rax, WPP_GLOBAL_Control
0x180031c7b  cmp     rcx, rax
0x180031c7e  jz      short loc_180031CBE
0x180031c80  test    byte ptr [rcx+1Ch], 1
0x180031c84  jz      short loc_180031CBE
0x180031c86  mov     edx, 34h ; '4'
0x180031c8b  mov     rcx, [rcx+10h]
0x180031c8f  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x180031c96  mov     r9d, ebx
0x180031c99  call    WPP_SF_d
0x180031c9e  jmp     short loc_180031CBE
0x180031ca0  mov     rdx, rdi; pclsid
0x180031ca3  mov     rcx, rsi; lpsz
0x180031ca6  call    cs:__imp_CLSIDFromString
0x180031cad  nop     dword ptr [rax+rax+00h]
0x180031cb2  mov     ebx, eax
0x180031cb4  mov     eax, 80070490h
0x180031cb9  test    ebx, ebx
0x180031cbb  cmovs   ebx, eax
0x180031cbe  mov     eax, ebx
0x180031cc0  mov     rcx, [rsp+0A8h+var_28]
0x180031cc8  xor     rcx, rsp; StackCookie
0x180031ccb  call    __security_check_cookie
0x180031cd0  add     rsp, 90h
0x180031cd7  pop     rdi
0x180031cd8  pop     rsi
0x180031cd9  pop     rbx
0x180031cda  retn
```
