# GetMsmqGuidFromAD

- ea: `0x180024b58`
- end: `0x180024ec0`
- name: `GetMsmqGuidFromAD`
- size: `872`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180023f54`
- `0x180024184`

## callees

- `0x18000bb04`
- `0x18000cb80`
- `0x18000f35c`
- `0x180011578`
- `0x1800236c4`
- `0x180024b58`
- `0x18002c61c`
- `0x18009bd1c`
- `0x1800ce4d4`
- `0x1800d08f8`
- `0x1800e4010`

## import_xrefs

- `msvcrt!free` at `0x180024bf5`
- `msvcrt!free` at `0x180024cc0`
- `msvcrt!free` at `0x180024ce0`
- `msvcrt!free` at `0x180024db7`
- `msvcrt!free` at `0x180024dd7`
- `msvcrt!free` at `0x180024e84`
- `msvcrt!free` at `0x180024ea4`
- `msvcrt!free` at `0x180024bf5`
- `msvcrt!free` at `0x180024cc0`
- `msvcrt!free` at `0x180024ce0`
- `msvcrt!free` at `0x180024db7`
- `msvcrt!free` at `0x180024dd7`
- `msvcrt!free` at `0x180024e84`
- `msvcrt!free` at `0x180024ea4`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x180024c71`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x180024c71`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180024e4a`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180024e4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetMsmqGuidFromAD(const wchar_t *a1, _OWORD *a2)
{
  unsigned __int64 v4; // rdi
  wchar_t *v5; // rbx
  int v6; // eax
  int v7; // esi
  const WCHAR *v8; // rax
  HRESULT v9; // eax
  int v10; // eax
  void *v11; // rcx
  __int64 v12; // rax
  LPVOID pMem; // [rsp+30h] [rbp-20h] BYREF
  void *Block; // [rsp+38h] [rbp-18h]
  _QWORD v16[2]; // [rsp+40h] [rbp-10h] BYREF
  int v17; // [rsp+80h] [rbp+30h] BYREF
  void *ppObject; // [rsp+88h] [rbp+38h] BYREF

  v4 = mqwcslen(a1) + 16;
  v5 = (wchar_t *)MmAllocate(saturated_mul(v4, 2u));
  v16[1] = v5;
  v6 = StringCchPrintfW(v5, (unsigned int)v4, L"%s%s", L"LDAP://cn=msmq,", a1);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_f073386f5643352810e6d9a62b947684_Traceguids,
        (unsigned int)v6);
LABEL_15:
    free(v5);
    return (unsigned int)v7;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
  ppObject = 0;
  Block = 0;
  v8 = (const WCHAR *)UtlEscapeAdsPathName(v5);
  v9 = ADsOpenObject(v8, 0, 0, 1u, &IID_IDirectoryObject, &ppObject);
  v7 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_f073386f5643352810e6d9a62b947684_Traceguids,
        (unsigned int)v9);
    LogMsgHR(v7, (wchar_t *)L"joinstat", 0x28u);
    free(Block);
    if ( ppObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  v16[0] = L"objectGUID";
  v17 = 0;
  pMem = 0;
  v10 = (*(__int64 (__fastcall **)(void *, _QWORD *, __int64, LPVOID *, int *))(*(_QWORD *)ppObject + 32LL))(
          ppObject,
          v16,
          1,
          &pMem,
          &v17);
  v7 = v10;
  if ( v10 >= 0 )
  {
    v11 = pMem;
    if ( v17 )
    {
      v7 = -1072824295;
      if ( *((_DWORD *)pMem + 3) == 8 )
      {
        v12 = *((_QWORD *)pMem + 2);
        if ( *(_DWORD *)(v12 + 8) == 16 )
        {
          *a2 = *(_OWORD *)*(_QWORD *)(v12 + 16);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_f073386f5643352810e6d9a62b947684_Traceguids, a2);
            v11 = pMem;
          }
          v7 = 0;
        }
      }
    }
    else
    {
      v7 = -1072823025;
    }
    if ( v11 )
      FreeADsMem(v11);
    LODWORD(qword_1801291DC) = qword_1801291DC + 1;
    HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
    SetStatus();
    if ( v7 < 0 )
      LogMsgHR(v7, (wchar_t *)L"joinstat", 0x3Cu);
    free(Block);
    if ( ppObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        &WPP_f073386f5643352810e6d9a62b947684_Traceguids,
        (unsigned int)v10);
    LogMsgHR(v7, (wchar_t *)L"joinstat", 0x32u);
    free(Block);
    if ( ppObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
  }
  free(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180024b58  mov     [rsp-18h+arg_0], rbx
0x180024b5d  mov     [rsp-18h+arg_8], rsi
0x180024b62  push    rbp
0x180024b63  push    rdi
0x180024b64  push    r15
0x180024b66  mov     rbp, rsp
0x180024b69  sub     rsp, 50h
0x180024b6d  mov     r15, rdx
0x180024b70  mov     rsi, rcx
0x180024b73  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180024b78  lea     edi, [rax+10h]
0x180024b7b  mov     eax, 2
0x180024b80  mul     rdi
0x180024b83  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180024b8a  cmovb   rax, rcx
0x180024b8e  mov     rcx, rax; unsigned __int64
0x180024b91  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180024b96  mov     rbx, rax
0x180024b99  mov     [rbp+var_8], rax
0x180024b9d  mov     [rsp+50h+riid], rsi
0x180024ba2  lea     r9, aLdapCnMsmq; "LDAP://cn=msmq,"
0x180024ba9  lea     r8, aSS_4; "%s%s"
0x180024bb0  mov     edx, edi; unsigned __int64
0x180024bb2  mov     rcx, rax; wchar_t *
0x180024bb5  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180024bba  mov     esi, eax
0x180024bbc  test    eax, eax
0x180024bbe  jns     short loc_180024C01
0x180024bc0  lea     rdi, WPP_GLOBAL_Control
0x180024bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180024bce  cmp     rcx, rdi
0x180024bd1  jz      short loc_180024BF2
0x180024bd3  test    byte ptr [rcx+1Ch], 1
0x180024bd7  jz      short loc_180024BF2
0x180024bd9  mov     edx, 10h
0x180024bde  mov     r9d, eax
0x180024be1  lea     r8, WPP_f073386f5643352810e6d9a62b947684_Traceguids
0x180024be8  mov     rcx, [rcx+10h]
0x180024bec  call    WPP_SF_d
0x180024bf1  nop
0x180024bf2  mov     rcx, rbx; Block
0x180024bf5  call    cs:__imp_free
0x180024bfb  nop
0x180024bfc  jmp     loc_180024EAB
0x180024c01  lea     rdi, WPP_GLOBAL_Control
0x180024c08  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c0f  cmp     rcx, rdi
0x180024c12  jz      short loc_180024C32
0x180024c14  test    byte ptr [rcx+1Ch], 4
0x180024c18  jz      short loc_180024C32
0x180024c1a  mov     edx, 11h
0x180024c1f  mov     r9, rbx
0x180024c22  lea     r8, WPP_f073386f5643352810e6d9a62b947684_Traceguids
0x180024c29  mov     rcx, [rcx+10h]; LoggerHandle
0x180024c2d  call    WPP_SF_S
0x180024c32  mov     [rbp+arg_18], 0
0x180024c3a  mov     [rbp+Block], 0
0x180024c42  lea     rdx, [rbp+Block]
0x180024c46  mov     rcx, rbx; wchar_t *
0x180024c49  call    ?UtlEscapeAdsPathName@@YAPEB_WPEB_WAEAV?$AP@_W@@@Z; UtlEscapeAdsPathName(wchar_t const *,AP<wchar_t> &)
0x180024c4e  mov     rcx, rax; lpszPathName
0x180024c51  lea     rax, [rbp+arg_18]
0x180024c55  mov     [rsp+50h+ppObject], rax; ppObject
0x180024c5a  lea     rax, IID_IDirectoryObject
0x180024c61  mov     [rsp+50h+riid], rax; riid
0x180024c66  mov     r9d, 1; dwReserved
0x180024c6c  xor     r8d, r8d; lpszPassword
0x180024c6f  xor     edx, edx; lpszUserName
0x180024c71  call    cs:__imp_ADsOpenObject
0x180024c77  mov     esi, eax
0x180024c79  test    eax, eax
0x180024c7b  jns     short loc_180024CEC
0x180024c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c84  cmp     rcx, rdi
0x180024c87  jz      short loc_180024CA7
0x180024c89  test    byte ptr [rcx+1Ch], 2
0x180024c8d  jz      short loc_180024CA7
0x180024c8f  mov     edx, 12h
0x180024c94  mov     r9d, eax
0x180024c97  lea     r8, WPP_f073386f5643352810e6d9a62b947684_Traceguids
0x180024c9e  mov     rcx, [rcx+10h]
0x180024ca2  call    WPP_SF_d
0x180024ca7  mov     r8d, 28h ; '('; unsigned __int16
0x180024cad  lea     rdx, aJoinstat; "joinstat"
0x180024cb4  mov     ecx, esi; int
0x180024cb6  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180024cbb  nop
0x180024cbc  mov     rcx, [rbp+Block]; Block
0x180024cc0  call    cs:__imp_free
0x180024cc6  nop
0x180024cc7  mov     rcx, [rbp+arg_18]
0x180024ccb  test    rcx, rcx
0x180024cce  jz      short loc_180024CDD
0x180024cd0  mov     rax, [rcx]
0x180024cd3  mov     rax, [rax+10h]
0x180024cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cdc  nop
0x180024cdd  mov     rcx, rbx; Block
0x180024ce0  call    cs:__imp_free
0x180024ce6  nop
0x180024ce7  jmp     loc_180024EAB
0x180024cec  mov     rcx, cs:WPP_GLOBAL_Control
0x180024cf3  cmp     rcx, rdi
0x180024cf6  jz      short loc_180024D16
0x180024cf8  test    byte ptr [rcx+1Ch], 4
0x180024cfc  jz      short loc_180024D16
0x180024cfe  mov     edx, 13h
0x180024d03  mov     r9, rbx
0x180024d06  lea     r8, WPP_f073386f5643352810e6d9a62b947684_Traceguids
0x180024d0d  mov     rcx, [rcx+10h]; LoggerHandle
0x180024d11  call    WPP_SF_S
0x180024d16  inc     dword ptr cs:qword_1801291DC
0x180024d1c  mov     eax, cs:?g_ServiceProgressTime@@3KA; ulong g_ServiceProgressTime
0x180024d22  mov     dword ptr cs:qword_1801291DC+4, eax
0x180024d28  call    ?SetStatus@@YAXXZ; SetStatus(void)
0x180024d2d  lea     rax, aObjectguid; "objectGUID"
0x180024d34  mov     [rbp+var_10], rax
0x180024d38  mov     [rbp+arg_10], 0
0x180024d3f  mov     [rbp+pMem], 0
0x180024d47  mov     rcx, [rbp+arg_18]
0x180024d4b  mov     rax, [rcx]
0x180024d4e  lea     rdx, [rbp+arg_10]
0x180024d52  mov     [rsp+50h+riid], rdx
0x180024d57  lea     r9, [rbp+pMem]
0x180024d5b  mov     r8d, 1
0x180024d61  lea     rdx, [rbp+var_10]
0x180024d65  mov     rax, [rax+20h]
0x180024d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d6e  mov     esi, eax
0x180024d70  test    eax, eax
0x180024d72  jns     short loc_180024DE3
0x180024d74  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d7b  cmp     rcx, rdi
0x180024d7e  jz      short loc_180024D9E
0x180024d80  test    byte ptr [rcx+1Ch], 1
0x180024d84  jz      short loc_180024D9E
0x180024d86  mov     edx, 14h
0x180024d8b  mov     r9d, eax
0x180024d8e  lea     r8, WPP_f073386f5643352810e6d9a62b947684_Traceguids
0x180024d95  mov     rcx, [rcx+10h]
0x180024d99  call    WPP_SF_d
0x180024d9e  mov     r8d, 32h ; '2'; unsigned __int16
0x180024da4  lea     rdx, aJoinstat; "joinstat"
0x180024dab  mov     ecx, esi; int
0x180024dad  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180024db2  nop
0x180024db3  mov     rcx, [rbp+Block]; Block
0x180024db7  call    cs:__imp_free
0x180024dbd  nop
0x180024dbe  mov     rcx, [rbp+arg_18]
0x180024dc2  test    rcx, rcx
0x180024dc5  jz      short loc_180024DD4
0x180024dc7  mov     rax, [rcx]
0x180024dca  mov     rax, [rax+10h]
0x180024dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dd3  nop
0x180024dd4  mov     rcx, rbx; Block
0x180024dd7  call    cs:__imp_free
0x180024ddd  nop
0x180024dde  jmp     loc_180024EAB
0x180024de3  mov     rcx, [rbp+pMem]
0x180024de7  cmp     [rbp+arg_10], 0
0x180024deb  jnz     short loc_180024DF4
0x180024ded  mov     esi, 0C00E050Fh
0x180024df2  jmp     short loc_180024E45
0x180024df4  mov     esi, 0C00E0019h
0x180024df9  cmp     dword ptr [rcx+0Ch], 8
0x180024dfd  jnz     short loc_180024E45
0x180024dff  mov     rax, [rcx+10h]
0x180024e03  cmp     dword ptr [rax+8], 10h
0x180024e07  jnz     short loc_180024E45
0x180024e09  mov     rax, [rax+10h]
0x180024e0d  movups  xmm0, xmmword ptr [rax]
0x180024e10  movdqu  xmmword ptr [r15], xmm0
0x180024e15  mov     rax, cs:WPP_GLOBAL_Control
0x180024e1c  cmp     rax, rdi
0x180024e1f  jz      short loc_180024E43
0x180024e21  test    byte ptr [rax+1Ch], 4
0x180024e25  jz      short loc_180024E43
0x180024e27  mov     edx, 15h
0x180024e2c  mov     r9, r15
0x180024e2f  lea     r8, WPP_f073386f5643352810e6d9a62b947684_Traceguids
0x180024e36  mov     rcx, [rax+10h]
0x180024e3a  call    WPP_SF__guid_
0x180024e3f  mov     rcx, [rbp+pMem]; pMem
0x180024e43  xor     esi, esi
0x180024e45  test    rcx, rcx
0x180024e48  jz      short loc_180024E50
0x180024e4a  call    cs:__imp_FreeADsMem
0x180024e50  inc     dword ptr cs:qword_1801291DC
0x180024e56  mov     eax, cs:?g_ServiceProgressTime@@3KA; ulong g_ServiceProgressTime
0x180024e5c  mov     dword ptr cs:qword_1801291DC+4, eax
0x180024e62  call    ?SetStatus@@YAXXZ; SetStatus(void)
0x180024e67  test    esi, esi
0x180024e69  jns     short loc_180024E80
0x180024e6b  mov     r8d, 3Ch ; '<'; unsigned __int16
0x180024e71  lea     rdx, aJoinstat; "joinstat"
0x180024e78  mov     ecx, esi; int
0x180024e7a  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180024e7f  nop
0x180024e80  mov     rcx, [rbp+Block]; Block
0x180024e84  call    cs:__imp_free
0x180024e8a  nop
0x180024e8b  mov     rcx, [rbp+arg_18]
0x180024e8f  test    rcx, rcx
0x180024e92  jz      short loc_180024EA1
0x180024e94  mov     rdx, [rcx]
0x180024e97  mov     rax, [rdx+10h]
0x180024e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ea0  nop
0x180024ea1  mov     rcx, rbx; Block
0x180024ea4  call    cs:__imp_free
0x180024eaa  nop
0x180024eab  mov     eax, esi
0x180024ead  mov     rbx, [rsp+50h+arg_0]
0x180024eb2  mov     rsi, [rsp+50h+arg_8]
0x180024eb7  add     rsp, 50h
0x180024ebb  pop     r15
0x180024ebd  pop     rdi
0x180024ebe  pop     rbp
0x180024ebf  retn
```
