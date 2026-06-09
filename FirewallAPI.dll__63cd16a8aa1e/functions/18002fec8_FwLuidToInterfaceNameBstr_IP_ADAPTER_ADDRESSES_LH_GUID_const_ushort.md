# FwLuidToInterfaceNameBstr(_IP_ADAPTER_ADDRESSES_LH *,_GUID const *,ushort * *)

- ea: `0x18002fec8`
- end: `0x1800300bc`
- name: `?FwLuidToInterfaceNameBstr@@YAJPEAU_IP_ADAPTER_ADDRESSES_LH@@PEBU_GUID@@PEAPEAG@Z`
- size: `500`
- prototype: `int(struct _IP_ADAPTER_ADDRESSES_LH *, const struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800300c4`

## callees

- `0x180005954`
- `0x180023228`
- `0x1800277b0`
- `0x1800284c4`
- `0x18002fec8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002ff82`
- `OLEAUT32!__imp_SysAllocString` at `0x18003005f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ff82`
- `OLEAUT32!__imp_SysAllocString` at `0x18003005f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003009a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003009a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003002f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003002f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002ff56`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002ff56`

## pseudocode

```c
__int64 __fastcall FwLuidToInterfaceNameBstr(
        struct _IP_ADAPTER_ADDRESSES_LH *a1,
        const struct _GUID *a2,
        unsigned __int16 **a3)
{
  HRESULT v6; // ebx
  __int64 v7; // rax
  unsigned __int16 *v8; // rax
  __int64 v9; // r9
  FwPolicy2 *v10; // rcx
  __int64 v11; // rdx
  unsigned __int16 *v12; // rax
  LPOLESTR lpsz; // [rsp+20h] [rbp-49h] BYREF
  GUID pclsid; // [rsp+28h] [rbp-41h] BYREF
  wchar_t pszDest; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v17[78]; // [rsp+42h] [rbp-27h] BYREF

  lpsz = 0;
  *a3 = 0;
  pclsid = GUID_NULL;
  while ( 1 )
  {
    if ( !a1 )
    {
      v6 = StringFromCLSID(a2, &lpsz);
      if ( v6 >= 0 )
      {
        v12 = SysAllocString(lpsz);
        *a3 = v12;
        if ( v12 )
        {
          CoTaskMemFree(lpsz);
        }
        else
        {
          v9 = 2147942414LL;
          v6 = -2147024882;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 59;
            goto LABEL_20;
          }
        }
        return (unsigned int)v6;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v6;
      v11 = 58;
LABEL_19:
      v9 = (unsigned int)v6;
      goto LABEL_20;
    }
    pszDest = 0;
    memset_0(v17, 0, sizeof(v17));
    v6 = StringCchPrintfW(&pszDest, 0x27u, L"%S", a1->AdapterName, lpsz);
    if ( v6 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v6;
      v11 = 55;
      goto LABEL_19;
    }
    v6 = CLSIDFromString(&pszDest, &pclsid);
    if ( v6 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v6;
      v11 = 56;
      goto LABEL_19;
    }
    v7 = *(_QWORD *)&pclsid.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&pclsid.Data1 == *(_QWORD *)&a2->Data1 )
      v7 = *(_QWORD *)pclsid.Data4 - *(_QWORD *)a2->Data4;
    if ( !v7 )
      break;
    a1 = a1->Next;
  }
  v8 = SysAllocString(a1->FriendlyName);
  *a3 = v8;
  if ( !v8 )
  {
    v9 = 2147942414LL;
    v6 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 57;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, v9);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002fec8  push    rbp
0x18002feca  push    rbx
0x18002fecb  push    rsi
0x18002fecc  push    rdi
0x18002fecd  push    r14
0x18002fecf  lea     rbp, [rsp-37h]
0x18002fed4  sub     rsp, 0A0h
0x18002fedb  mov     rax, cs:__security_cookie
0x18002fee2  xor     rax, rsp
0x18002fee5  mov     [rbp+57h+var_30], rax
0x18002fee9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002fef0  mov     r14, r8
0x18002fef3  mov     [rbp+57h+lpsz], 0
0x18002fefb  mov     rsi, rdx
0x18002fefe  mov     qword ptr [r8], 0
0x18002ff05  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18002ff0a  mov     rdi, rcx
0x18002ff0d  test    rdi, rdi
0x18002ff10  jz      loc_180030028
0x18002ff16  xor     eax, eax
0x18002ff18  lea     rcx, [rbp+57h+var_7E]; void *
0x18002ff1c  xor     edx, edx; Val
0x18002ff1e  mov     [rbp+57h+pszDest], ax
0x18002ff22  lea     r8d, [rax+4Eh]; Size
0x18002ff26  call    memset_0
0x18002ff2b  mov     r9, [rdi+10h]
0x18002ff2f  lea     r8, aS_0; "%S"
0x18002ff36  mov     edx, 27h ; '''; cchDest
0x18002ff3b  lea     rcx, [rbp+57h+pszDest]; pszDest
0x18002ff3f  call    StringCchPrintfW
0x18002ff44  mov     ebx, eax
0x18002ff46  test    eax, eax
0x18002ff48  js      loc_18002FFED
0x18002ff4e  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18002ff52  lea     rcx, [rbp+57h+pszDest]; lpsz
0x18002ff56  call    cs:__imp_CLSIDFromString
0x18002ff5c  mov     ebx, eax
0x18002ff5e  test    eax, eax
0x18002ff60  js      short loc_18002FFC5
0x18002ff62  mov     rax, qword ptr [rbp+57h+pclsid.Data1]
0x18002ff66  sub     rax, [rsi]
0x18002ff69  jnz     short loc_18002FF73
0x18002ff6b  mov     rax, qword ptr [rbp+57h+pclsid.Data4]
0x18002ff6f  sub     rax, [rsi+8]
0x18002ff73  test    rax, rax
0x18002ff76  jz      short loc_18002FF7E
0x18002ff78  mov     rdi, [rdi+8]
0x18002ff7c  jmp     short loc_18002FF0D
0x18002ff7e  mov     rcx, [rdi+48h]; psz
0x18002ff82  call    cs:__imp_SysAllocString
0x18002ff88  mov     [r14], rax
0x18002ff8b  test    rax, rax
0x18002ff8e  jnz     loc_1800300A0
0x18002ff94  mov     r9d, 8007000Eh
0x18002ff9a  mov     ebx, r9d
0x18002ff9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffa4  lea     rax, WPP_GLOBAL_Control
0x18002ffab  cmp     rcx, rax
0x18002ffae  jz      loc_1800300A0
0x18002ffb4  test    byte ptr [rcx+1Ch], 1
0x18002ffb8  jz      loc_1800300A0
0x18002ffbe  mov     edx, 39h ; '9'
0x18002ffc3  jmp     short loc_180030016
0x18002ffc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffcc  lea     rax, WPP_GLOBAL_Control
0x18002ffd3  cmp     rcx, rax
0x18002ffd6  jz      loc_1800300A0
0x18002ffdc  test    byte ptr [rcx+1Ch], 1
0x18002ffe0  jz      loc_1800300A0
0x18002ffe6  mov     edx, 38h ; '8'
0x18002ffeb  jmp     short loc_180030013
0x18002ffed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fff4  lea     rax, WPP_GLOBAL_Control
0x18002fffb  cmp     rcx, rax
0x18002fffe  jz      loc_1800300A0
0x180030004  test    byte ptr [rcx+1Ch], 1
0x180030008  jz      loc_1800300A0
0x18003000e  mov     edx, 37h ; '7'
0x180030013  mov     r9d, ebx
0x180030016  mov     rcx, [rcx+10h]
0x18003001a  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x180030021  call    WPP_SF_d
0x180030026  jmp     short loc_1800300A0
0x180030028  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x18003002c  mov     rcx, rsi; rclsid
0x18003002f  call    cs:__imp_StringFromCLSID
0x180030035  mov     ebx, eax
0x180030037  test    eax, eax
0x180030039  jns     short loc_18003005B
0x18003003b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030042  lea     rax, WPP_GLOBAL_Control
0x180030049  cmp     rcx, rax
0x18003004c  jz      short loc_1800300A0
0x18003004e  test    byte ptr [rcx+1Ch], 1
0x180030052  jz      short loc_1800300A0
0x180030054  mov     edx, 3Ah ; ':'
0x180030059  jmp     short loc_180030013
0x18003005b  mov     rcx, [rbp+57h+lpsz]; psz
0x18003005f  call    cs:__imp_SysAllocString
0x180030065  mov     [r14], rax
0x180030068  test    rax, rax
0x18003006b  jnz     short loc_180030096
0x18003006d  mov     r9d, 8007000Eh
0x180030073  mov     ebx, r9d
0x180030076  mov     rcx, cs:WPP_GLOBAL_Control
0x18003007d  lea     rax, WPP_GLOBAL_Control
0x180030084  cmp     rcx, rax
0x180030087  jz      short loc_1800300A0
0x180030089  test    byte ptr [rcx+1Ch], 1
0x18003008d  jz      short loc_1800300A0
0x18003008f  mov     edx, 3Bh ; ';'
0x180030094  jmp     short loc_180030016
0x180030096  mov     rcx, [rbp+57h+lpsz]; pv
0x18003009a  call    cs:__imp_CoTaskMemFree
0x1800300a0  mov     eax, ebx
0x1800300a2  mov     rcx, [rbp+57h+var_30]
0x1800300a6  xor     rcx, rsp; StackCookie
0x1800300a9  call    __security_check_cookie
0x1800300ae  add     rsp, 0A0h
0x1800300b5  pop     r14
0x1800300b7  pop     rdi
0x1800300b8  pop     rsi
0x1800300b9  pop     rbx
0x1800300ba  pop     rbp
0x1800300bb  retn
```
