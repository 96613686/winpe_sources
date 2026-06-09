# FwInterfaceNameToLuid(_IP_ADAPTER_ADDRESSES_LH *,ushort * const,_GUID *)

- ea: `0x18002fa00`
- end: `0x18002fb87`
- name: `?FwInterfaceNameToLuid@@YAJPEAU_IP_ADAPTER_ADDRESSES_LH@@QEAGPEAU_GUID@@@Z`
- size: `391`
- prototype: `int(struct _IP_ADAPTER_ADDRESSES_LH *, unsigned __int16 *const, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180030324`

## callees

- `0x180005954`
- `0x180023228`
- `0x1800277b0`
- `0x1800284c4`
- `0x18002fa00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb0a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002fa5a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002fa5a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002fada`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002fb58`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002fada`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002fb58`

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
0x18002fa00  push    rbx
0x18002fa02  push    rsi
0x18002fa03  push    rdi
0x18002fa04  sub     rsp, 90h
0x18002fa0b  mov     rax, cs:__security_cookie
0x18002fa12  xor     rax, rsp
0x18002fa15  mov     [rsp+0A8h+var_28], rax
0x18002fa1d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002fa24  mov     rdi, r8
0x18002fa27  mov     rsi, rdx
0x18002fa2a  mov     rbx, rcx
0x18002fa2d  movdqu  xmmword ptr [r8], xmm0
0x18002fa32  test    rbx, rbx
0x18002fa35  jz      loc_18002FB52
0x18002fa3b  mov     rax, [rbx+48h]
0x18002fa3f  or      r9d, 0FFFFFFFFh; cchCount1
0x18002fa43  mov     [rsp+0A8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002fa4b  mov     r8, rsi; lpString1
0x18002fa4e  mov     [rsp+0A8h+lpString2], rax; lpString2
0x18002fa53  lea     edx, [r9+2]; dwCmpFlags
0x18002fa57  lea     ecx, [rdx+7Eh]; Locale
0x18002fa5a  call    cs:__imp_CompareStringW
0x18002fa60  test    eax, eax
0x18002fa62  jz      loc_18002FB0A
0x18002fa68  cmp     eax, 2
0x18002fa6b  jz      short loc_18002FA73
0x18002fa6d  mov     rbx, [rbx+8]
0x18002fa71  jmp     short loc_18002FA32
0x18002fa73  xor     eax, eax
0x18002fa75  lea     rcx, [rsp+0A8h+var_76]; void *
0x18002fa7a  xor     edx, edx; Val
0x18002fa7c  mov     [rsp+0A8h+pszDest], ax
0x18002fa81  lea     r8d, [rax+4Eh]; Size
0x18002fa85  call    memset_0
0x18002fa8a  mov     r9, [rbx+10h]
0x18002fa8e  lea     r8, aS_0; "%S"
0x18002fa95  mov     edx, 27h ; '''; cchDest
0x18002fa9a  lea     rcx, [rsp+0A8h+pszDest]; pszDest
0x18002fa9f  call    StringCchPrintfW
0x18002faa4  mov     ebx, eax
0x18002faa6  test    eax, eax
0x18002faa8  jns     short loc_18002FAD2
0x18002faaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fab1  lea     rax, WPP_GLOBAL_Control
0x18002fab8  cmp     rcx, rax
0x18002fabb  jz      loc_18002FB6A
0x18002fac1  test    byte ptr [rcx+1Ch], 1
0x18002fac5  jz      loc_18002FB6A
0x18002facb  mov     edx, 35h ; '5'
0x18002fad0  jmp     short loc_18002FB3D
0x18002fad2  mov     rdx, rdi; pclsid
0x18002fad5  lea     rcx, [rsp+0A8h+pszDest]; lpsz
0x18002fada  call    cs:__imp_CLSIDFromString
0x18002fae0  mov     ebx, eax
0x18002fae2  test    eax, eax
0x18002fae4  jns     loc_18002FB6A
0x18002faea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002faf1  lea     rax, WPP_GLOBAL_Control
0x18002faf8  cmp     rcx, rax
0x18002fafb  jz      short loc_18002FB6A
0x18002fafd  test    byte ptr [rcx+1Ch], 1
0x18002fb01  jz      short loc_18002FB6A
0x18002fb03  mov     edx, 36h ; '6'
0x18002fb08  jmp     short loc_18002FB3D
0x18002fb0a  call    cs:__imp_GetLastError
0x18002fb10  mov     ebx, eax
0x18002fb12  test    eax, eax
0x18002fb14  jle     short loc_18002FB1F
0x18002fb16  movzx   ebx, ax
0x18002fb19  or      ebx, 80070000h
0x18002fb1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb26  lea     rax, WPP_GLOBAL_Control
0x18002fb2d  cmp     rcx, rax
0x18002fb30  jz      short loc_18002FB6A
0x18002fb32  test    byte ptr [rcx+1Ch], 1
0x18002fb36  jz      short loc_18002FB6A
0x18002fb38  mov     edx, 34h ; '4'
0x18002fb3d  mov     rcx, [rcx+10h]
0x18002fb41  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18002fb48  mov     r9d, ebx
0x18002fb4b  call    WPP_SF_d
0x18002fb50  jmp     short loc_18002FB6A
0x18002fb52  mov     rdx, rdi; pclsid
0x18002fb55  mov     rcx, rsi; lpsz
0x18002fb58  call    cs:__imp_CLSIDFromString
0x18002fb5e  mov     ebx, eax
0x18002fb60  mov     eax, 80070490h
0x18002fb65  test    ebx, ebx
0x18002fb67  cmovs   ebx, eax
0x18002fb6a  mov     eax, ebx
0x18002fb6c  mov     rcx, [rsp+0A8h+var_28]
0x18002fb74  xor     rcx, rsp; StackCookie
0x18002fb77  call    __security_check_cookie
0x18002fb7c  add     rsp, 90h
0x18002fb83  pop     rdi
0x18002fb84  pop     rsi
0x18002fb85  pop     rbx
0x18002fb86  retn
```
