# FwStringToSids

- ea: `0x180010a10`
- end: `0x180010c2c`
- name: `FwStringToSids`
- size: `540`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x1800042c4`
- `0x180010a10`
- `0x180010c60`
- `0x180012940`
- `0x18001f650`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180010ad8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180010b4a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180010ad8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180010b4a`
- `fwbase!FwFree` at `0x180010a99`
- `fwbase!FwFree` at `0x180010a99`
- `fwbase!FwStringCopy` at `0x180010a5f`
- `fwbase!FwStringCopy` at `0x180010a5f`
- `fwbase!FwArrayAppend` at `0x180010b1c`
- `fwbase!FwArrayAppend` at `0x180010b1c`

## pseudocode

```c
__int64 __fastcall FwStringToSids(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  int v5; // eax
  int v6; // edi
  LPCOLESTR v7; // rcx
  wchar_t *i; // rax
  int v10; // esi
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdx
  wchar_t *String; // [rsp+20h] [rbp-40h] BYREF
  wchar_t *Context; // [rsp+28h] [rbp-38h] BYREF
  __int128 v17; // [rsp+30h] [rbp-30h] BYREF
  struct _SID *v18[2]; // [rsp+40h] [rbp-20h] BYREF

  *a2 = 0;
  String = 0;
  Context = 0;
  v17 = 0;
  *a3 = 0;
  v5 = FwStringCopy(a1, &String);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v12 = 160;
      v13 = (unsigned int)v5;
      goto LABEL_18;
    }
  }
  else
  {
    if ( !String )
    {
      v6 = 0;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_5;
      v12 = 161;
      v13 = 0;
LABEL_18:
      WPP_SF_d(*((_QWORD *)v7 + 2), v12, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, v13);
      goto LABEL_5;
    }
    for ( i = wcstok_s(String, &WF_ADDR_TOKEN_DELIMITER_STR, &Context);
          ;
          i = wcstok_s(0, &WF_ADDR_TOKEN_DELIMITER_STR, &Context) )
    {
      if ( !i )
      {
        *a2 = v17;
        *a3 = *((_QWORD *)&v17 + 1);
        goto LABEL_5;
      }
      *(_OWORD *)v18 = 0;
      v10 = FwAppCParserSid(i, v18);
      if ( v10 < 0 )
        break;
      v11 = FwArrayAppend(16, FwShallowCopySidAndAttributes, &v17, v18);
      v7 = WPP_GLOBAL_Control;
      v10 = v11;
      if ( v11 < 0 && WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v14 = 55;
LABEL_26:
        WPP_SF_d(*((_QWORD *)v7 + 2), v14, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids, (unsigned int)v10);
        v7 = WPP_GLOBAL_Control;
        goto LABEL_27;
      }
      v6 = v11;
      if ( v11 < 0 )
        goto LABEL_28;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v14 = 54;
      goto LABEL_26;
    }
LABEL_27:
    v6 = v10;
LABEL_28:
    if ( v7 != (LPCOLESTR)&WPP_GLOBAL_Control && (v7[14] & 1) != 0 )
    {
      v12 = 162;
      v13 = (unsigned int)v10;
      goto LABEL_18;
    }
  }
LABEL_5:
  FwFree(String);
  if ( v6 < 0 )
    FwSidAndAttributesFree((unsigned int)v17, *((_QWORD *)&v17 + 1));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180010a10  mov     [rsp-28h+arg_18], rbx
0x180010a15  push    rbp
0x180010a16  push    rsi
0x180010a17  push    rdi
0x180010a18  push    r14
0x180010a1a  push    r15
0x180010a1c  mov     rbp, rsp
0x180010a1f  sub     rsp, 60h
0x180010a23  mov     rax, cs:__security_cookie
0x180010a2a  xor     rax, rsp
0x180010a2d  mov     [rbp+var_10], rax
0x180010a31  mov     dword ptr [rdx], 0
0x180010a37  mov     r14, rdx
0x180010a3a  xorps   xmm0, xmm0
0x180010a3d  mov     [rbp+String], 0
0x180010a45  lea     rdx, [rbp+String]
0x180010a49  mov     [rbp+Context], 0
0x180010a51  movups  [rbp+var_30], xmm0
0x180010a55  mov     r15, r8
0x180010a58  mov     qword ptr [r8], 0
0x180010a5f  call    cs:__imp_FwStringCopy
0x180010a65  mov     edi, eax
0x180010a67  test    eax, eax
0x180010a69  js      loc_180010B64
0x180010a6f  cmp     [rbp+String], 0
0x180010a74  jnz     short loc_180010AC9
0x180010a76  xor     edi, edi
0x180010a78  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a7f  lea     rbx, WPP_GLOBAL_Control
0x180010a86  cmp     rcx, rbx
0x180010a89  jz      short loc_180010A95
0x180010a8b  test    byte ptr [rcx+1Ch], 1
0x180010a8f  jnz     loc_180010BAC
0x180010a95  mov     rcx, [rbp+String]
0x180010a99  call    cs:__imp_FwFree
0x180010a9f  test    edi, edi
0x180010aa1  js      loc_180010C1B
0x180010aa7  mov     eax, edi
0x180010aa9  mov     rcx, [rbp+var_10]
0x180010aad  xor     rcx, rsp; StackCookie
0x180010ab0  call    __security_check_cookie
0x180010ab5  mov     rbx, [rsp+60h+arg_18]
0x180010abd  add     rsp, 60h
0x180010ac1  pop     r15
0x180010ac3  pop     r14
0x180010ac5  pop     rdi
0x180010ac6  pop     rsi
0x180010ac7  pop     rbp
0x180010ac8  retn
0x180010ac9  mov     rcx, [rbp+String]; String
0x180010acd  lea     r8, [rbp+Context]; Context
0x180010ad1  lea     rdx, ?WF_ADDR_TOKEN_DELIMITER_STR@@3QBGB; Delimiter
0x180010ad8  call    cs:__imp_wcstok_s
0x180010ade  lea     rbx, WPP_GLOBAL_Control
0x180010ae5  test    rax, rax
0x180010ae8  jz      short loc_180010B52
0x180010aea  xorps   xmm0, xmm0
0x180010aed  lea     rdx, [rbp+var_20]; struct _SID **
0x180010af1  mov     rcx, rax; unsigned __int16 *
0x180010af4  movdqu  xmmword ptr [rbp+var_20], xmm0
0x180010af9  call    ?FwAppCParserSid@@YAJPEBGPEAPEAU_SID@@@Z; FwAppCParserSid(ushort const *,_SID * *)
0x180010afe  mov     esi, eax
0x180010b00  test    eax, eax
0x180010b02  js      loc_180010BD0
0x180010b08  lea     r9, [rbp+var_20]
0x180010b0c  mov     ecx, 10h
0x180010b11  lea     r8, [rbp+var_30]
0x180010b15  lea     rdx, ?FwShallowCopySidAndAttributes@@YAJPEBXPEAX@Z; FwShallowCopySidAndAttributes(void const *,void *)
0x180010b1c  call    cs:__imp_FwArrayAppend
0x180010b22  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b29  mov     esi, eax
0x180010b2b  test    eax, eax
0x180010b2d  js      loc_180010BB6
0x180010b33  mov     edi, esi
0x180010b35  test    esi, esi
0x180010b37  js      loc_180010C03
0x180010b3d  lea     r8, [rbp+Context]; Context
0x180010b41  xor     ecx, ecx; String
0x180010b43  lea     rdx, ?WF_ADDR_TOKEN_DELIMITER_STR@@3QBGB; Delimiter
0x180010b4a  call    cs:__imp_wcstok_s
0x180010b50  jmp     short loc_180010AE5
0x180010b52  mov     eax, dword ptr [rbp+var_30]
0x180010b55  mov     [r14], eax
0x180010b58  mov     rax, qword ptr [rbp+var_30+8]
0x180010b5c  mov     [r15], rax
0x180010b5f  jmp     loc_180010A95
0x180010b64  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b6b  lea     rbx, WPP_GLOBAL_Control
0x180010b72  cmp     rcx, rbx
0x180010b75  jz      loc_180010A95
0x180010b7b  test    byte ptr [rcx+1Ch], 1
0x180010b7f  jz      loc_180010A95
0x180010b85  mov     edx, 0A0h
0x180010b8a  mov     r9d, eax
0x180010b8d  jmp     short loc_180010B97
0x180010b8f  mov     edx, 0A2h
0x180010b94  mov     r9d, esi
0x180010b97  mov     rcx, [rcx+10h]
0x180010b9b  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180010ba2  call    WPP_SF_d
0x180010ba7  jmp     loc_180010A95
0x180010bac  mov     edx, 0A1h
0x180010bb1  xor     r9d, r9d
0x180010bb4  jmp     short loc_180010B97
0x180010bb6  cmp     rcx, rbx
0x180010bb9  jz      loc_180010B33
0x180010bbf  test    byte ptr [rcx+1Ch], 1
0x180010bc3  jz      loc_180010B33
0x180010bc9  mov     edx, 37h ; '7'
0x180010bce  jmp     short loc_180010BE7
0x180010bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bd7  cmp     rcx, rbx
0x180010bda  jz      short loc_180010C01
0x180010bdc  test    byte ptr [rcx+1Ch], 1
0x180010be0  jz      short loc_180010C01
0x180010be2  mov     edx, 36h ; '6'
0x180010be7  mov     rcx, [rcx+10h]
0x180010beb  lea     r8, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids
0x180010bf2  mov     r9d, esi
0x180010bf5  call    WPP_SF_d
0x180010bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c01  mov     edi, esi
0x180010c03  cmp     rcx, rbx
0x180010c06  jz      loc_180010A95
0x180010c0c  test    byte ptr [rcx+1Ch], 1
0x180010c10  jz      loc_180010A95
0x180010c16  jmp     loc_180010B8F
0x180010c1b  mov     rdx, qword ptr [rbp+var_30+8]
0x180010c1f  mov     ecx, dword ptr [rbp+var_30]
0x180010c22  call    FwSidAndAttributesFree
0x180010c27  jmp     loc_180010AA7
```
