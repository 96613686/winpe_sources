# IoMgrGetInterfaceIds(HKEY__ *,ushort const *,void *,ulong *)

- ea: `0x18002d2b0`
- end: `0x18002d553`
- name: `?IoMgrGetInterfaceIds@@YAJPEAUHKEY__@@PEBGPEAXPEAK@Z`
- size: `675`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, _QWORD *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003b94`
- `0x1800041d0`
- `0x1800042c4`
- `0x18001e9ac`
- `0x18001f650`
- `0x18001ffd4`
- `0x18002d2b0`
- `0x180039bb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002d422`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002d46f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002d422`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002d46f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002d44d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002d44d`
- `fwbase!FwFree` at `0x18002d52a`
- `fwbase!FwFree` at `0x18002d52a`
- `fwbase!FwRegQueryString` at `0x18002d375`
- `fwbase!FwRegQueryString` at `0x18002d375`

## pseudocode

```c
__int64 __fastcall IoMgrGetInterfaceIds(HKEY a1, const unsigned __int16 *a2, _QWORD *a3, unsigned int *a4)
{
  int v8; // eax
  HRESULT v9; // ebx
  LPCOLESTR v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  wchar_t *v13; // rax
  unsigned int v14; // edi
  unsigned int v15; // esi
  unsigned int v16; // edi
  __int128 v18; // [rsp+30h] [rbp-D0h]
  wchar_t *String; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *Context; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v21[4]; // [rsp+50h] [rbp-B0h] BYREF
  int Src; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v23[1020]; // [rsp+64h] [rbp-9Ch] BYREF

  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 276, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  v21[0] = 0;
  String = 0;
  Context = 0;
  Src = 0;
  v18 = 0;
  memset_0(v23, 0, sizeof(v23));
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v8 = FwRegQueryString(a1, 0, a2, &String, v21);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = 277;
      v12 = (unsigned int)v8;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v12);
      goto LABEL_37;
    }
    goto LABEL_37;
  }
  if ( v21[0] )
    goto LABEL_19;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 278, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, a2);
    if ( !v21[0] )
    {
      v10 = WPP_GLOBAL_Control;
      goto LABEL_16;
    }
LABEL_19:
    v13 = wcstok_s(String, L",", &Context);
    v14 = 0;
    v15 = 0;
    while ( v13 )
    {
      if ( v14 >= 0x40 )
      {
        v12 = 2147942413LL;
        v9 = -2147024883;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v11 = 280;
          goto LABEL_10;
        }
        goto LABEL_37;
      }
      v9 = CLSIDFromString(v13, (LPCLSID)&v23[16 * v14 - 4]);
      if ( v9 < 0 )
      {
        v12 = 2147942413LL;
        v9 = -2147024883;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v11 = 281;
          goto LABEL_10;
        }
        goto LABEL_37;
      }
      LODWORD(v18) = ++v14;
      v15 = v14;
      v13 = wcstok_s(0, L",", &Context);
    }
    v16 = 16 * (v14 + 1);
    if ( *a4 >= v16 )
    {
      *(_OWORD *)a3 = v18;
      if ( v15 )
      {
        a3[1] = a3 + 2;
        memcpy_0(a3 + 2, &Src, 16LL * v15);
      }
      *a4 = v16;
    }
    else
    {
      *a4 = v16;
      v9 = -2147024662;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v11 = 282;
        v12 = 2147942634LL;
        goto LABEL_10;
      }
    }
    goto LABEL_37;
  }
LABEL_16:
  v9 = -2147024894;
  if ( v10 != (LPCOLESTR)&WPP_GLOBAL_Control && (v10[14] & 1) != 0 )
  {
    v11 = 279;
    v12 = 2147942402LL;
    goto LABEL_10;
  }
LABEL_37:
  FwFree(String);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002d2b0  push    rbp
0x18002d2b2  push    rbx
0x18002d2b3  push    rsi
0x18002d2b4  push    rdi
0x18002d2b5  push    r13
0x18002d2b7  push    r14
0x18002d2b9  push    r15
0x18002d2bb  lea     rbp, [rsp-370h]
0x18002d2c3  sub     rsp, 470h
0x18002d2ca  mov     rax, cs:__security_cookie
0x18002d2d1  xor     rax, rsp
0x18002d2d4  mov     [rbp+3A0h+var_40], rax
0x18002d2db  mov     r14, r9
0x18002d2de  mov     r15, r8
0x18002d2e1  mov     rdi, rdx
0x18002d2e4  mov     rbx, rcx
0x18002d2e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d2ee  lea     r13, WPP_GLOBAL_Control
0x18002d2f5  lea     rsi, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002d2fc  cmp     rcx, r13
0x18002d2ff  jz      short loc_18002D318
0x18002d301  test    byte ptr [rcx+1Ch], 8
0x18002d305  jz      short loc_18002D318
0x18002d307  mov     rcx, [rcx+10h]
0x18002d30b  mov     edx, 114h
0x18002d310  mov     r8, rsi
0x18002d313  call    WPP_SF_
0x18002d318  xorps   xmm0, xmm0
0x18002d31b  mov     [rsp+4A0h+var_450], 0
0x18002d323  xor     edx, edx; Val
0x18002d325  mov     [rsp+4A0h+String], 0
0x18002d32e  mov     r8d, 3FCh; Size
0x18002d334  mov     [rsp+4A0h+Context], 0
0x18002d33d  lea     rcx, [rsp+4A0h+var_43C]; void *
0x18002d342  mov     [rsp+4A0h+Src], 0
0x18002d34a  movups  [rsp+4A0h+var_470], xmm0
0x18002d34f  call    memset_0
0x18002d354  test    rbx, rbx
0x18002d357  jnz     short loc_18002D35E
0x18002d359  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002d35e  lea     rax, [rsp+4A0h+var_450]
0x18002d363  mov     r8, rdi
0x18002d366  lea     r9, [rsp+4A0h+String]
0x18002d36b  mov     [rsp+4A0h+var_480], rax
0x18002d370  xor     edx, edx
0x18002d372  mov     rcx, rbx
0x18002d375  call    cs:__imp_FwRegQueryString
0x18002d37b  mov     ebx, eax
0x18002d37d  test    eax, eax
0x18002d37f  jns     short loc_18002D3B4
0x18002d381  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d388  cmp     rcx, r13
0x18002d38b  jz      loc_18002D525
0x18002d391  test    byte ptr [rcx+1Ch], 1
0x18002d395  jz      loc_18002D525
0x18002d39b  mov     edx, 115h
0x18002d3a0  mov     r9d, eax
0x18002d3a3  mov     r8, rsi
0x18002d3a6  mov     rcx, [rcx+10h]
0x18002d3aa  call    WPP_SF_d
0x18002d3af  jmp     loc_18002D525
0x18002d3b4  cmp     [rsp+4A0h+var_450], 0
0x18002d3b9  jnz     short loc_18002D411
0x18002d3bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3c2  cmp     rcx, r13
0x18002d3c5  jz      short loc_18002D3EF
0x18002d3c7  test    byte ptr [rcx+1Ch], 2
0x18002d3cb  jz      short loc_18002D3EF
0x18002d3cd  mov     rcx, [rcx+10h]
0x18002d3d1  mov     edx, 116h
0x18002d3d6  mov     r9, rdi
0x18002d3d9  mov     r8, rsi
0x18002d3dc  call    WPP_SF_S
0x18002d3e1  cmp     [rsp+4A0h+var_450], 0
0x18002d3e6  jnz     short loc_18002D411
0x18002d3e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3ef  mov     ebx, 80070002h
0x18002d3f4  cmp     rcx, r13
0x18002d3f7  jz      loc_18002D525
0x18002d3fd  test    byte ptr [rcx+1Ch], 1
0x18002d401  jz      loc_18002D525
0x18002d407  mov     edx, 117h
0x18002d40c  mov     r9d, ebx
0x18002d40f  jmp     short loc_18002D3A3
0x18002d411  mov     rcx, [rsp+4A0h+String]; String
0x18002d416  lea     r8, [rsp+4A0h+Context]; Context
0x18002d41b  lea     rdx, ?WF_INTERFACE_TOKEN_DELIMITER_STR@@3QBGB; ","
0x18002d422  call    cs:__imp_wcstok_s
0x18002d428  mov     edi, dword ptr [rsp+4A0h+var_470]
0x18002d42c  xor     esi, esi
0x18002d42e  test    rax, rax
0x18002d431  jz      loc_18002D4CD
0x18002d437  cmp     edi, 40h ; '@'
0x18002d43a  jnb     short loc_18002D4A1
0x18002d43c  mov     ecx, edi
0x18002d43e  lea     rdx, [rsp+4A0h+Src]
0x18002d443  shl     rcx, 4
0x18002d447  add     rdx, rcx; pclsid
0x18002d44a  mov     rcx, rax; lpsz
0x18002d44d  call    cs:__imp_CLSIDFromString
0x18002d453  mov     ebx, eax
0x18002d455  test    eax, eax
0x18002d457  js      short loc_18002D477
0x18002d459  inc     edi
0x18002d45b  lea     r8, [rsp+4A0h+Context]; Context
0x18002d460  lea     rdx, ?WF_INTERFACE_TOKEN_DELIMITER_STR@@3QBGB; ","
0x18002d467  mov     dword ptr [rsp+4A0h+var_470], edi
0x18002d46b  xor     ecx, ecx; String
0x18002d46d  mov     esi, edi
0x18002d46f  call    cs:__imp_wcstok_s
0x18002d475  jmp     short loc_18002D42E
0x18002d477  mov     r9d, 8007000Dh
0x18002d47d  mov     ebx, r9d
0x18002d480  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d487  cmp     rcx, r13
0x18002d48a  jz      loc_18002D525
0x18002d490  test    byte ptr [rcx+1Ch], 1
0x18002d494  jz      loc_18002D525
0x18002d49a  mov     edx, 119h
0x18002d49f  jmp     short loc_18002D4C1
0x18002d4a1  mov     r9d, 8007000Dh
0x18002d4a7  mov     ebx, r9d
0x18002d4aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d4b1  cmp     rcx, r13
0x18002d4b4  jz      short loc_18002D525
0x18002d4b6  test    byte ptr [rcx+1Ch], 1
0x18002d4ba  jz      short loc_18002D525
0x18002d4bc  mov     edx, 118h
0x18002d4c1  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002d4c8  jmp     loc_18002D3A6
0x18002d4cd  inc     edi
0x18002d4cf  shl     edi, 4
0x18002d4d2  cmp     [r14], edi
0x18002d4d5  jnb     short loc_18002D4FB
0x18002d4d7  mov     [r14], edi
0x18002d4da  mov     ebx, 800700EAh
0x18002d4df  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d4e6  cmp     rcx, r13
0x18002d4e9  jz      short loc_18002D525
0x18002d4eb  test    byte ptr [rcx+1Ch], 1
0x18002d4ef  jz      short loc_18002D525
0x18002d4f1  mov     edx, 11Ah
0x18002d4f6  mov     r9d, ebx
0x18002d4f9  jmp     short loc_18002D4C1
0x18002d4fb  movups  xmm0, [rsp+4A0h+var_470]
0x18002d500  movdqu  xmmword ptr [r15], xmm0
0x18002d505  test    esi, esi
0x18002d507  jz      short loc_18002D522
0x18002d509  lea     rcx, [r15+10h]; void *
0x18002d50d  mov     r8d, esi
0x18002d510  shl     r8, 4; Size
0x18002d514  lea     rdx, [rsp+4A0h+Src]; Src
0x18002d519  mov     [r15+8], rcx
0x18002d51d  call    memcpy_0
0x18002d522  mov     [r14], edi
0x18002d525  mov     rcx, [rsp+4A0h+String]
0x18002d52a  call    cs:__imp_FwFree
0x18002d530  mov     eax, ebx
0x18002d532  mov     rcx, [rbp+3A0h+var_40]
0x18002d539  xor     rcx, rsp; StackCookie
0x18002d53c  call    __security_check_cookie
0x18002d541  add     rsp, 470h
0x18002d548  pop     r15
0x18002d54a  pop     r14
0x18002d54c  pop     r13
0x18002d54e  pop     rdi
0x18002d54f  pop     rsi
0x18002d550  pop     rbx
0x18002d551  pop     rbp
0x18002d552  retn
```
