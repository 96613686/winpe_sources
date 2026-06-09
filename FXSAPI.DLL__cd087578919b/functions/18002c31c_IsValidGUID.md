# IsValidGUID

- ea: `0x18002c31c`
- end: `0x18002c423`
- name: `IsValidGUID`
- size: `263`
- prototype: `__int64 __fastcall(LPCOLESTR lpsz)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023070`
- `0x1800240f0`
- `0x180028ef0`
- `0x180029e10`

## callees

- `0x18000abe4`
- `0x180016124`
- `0x18002c31c`
- `0x18002c954`
- `0x18003d510`

## import_xrefs

- `ole32!CLSIDFromString` at `0x18002c37c`
- `ole32!CLSIDFromString` at `0x18002c37c`

## pseudocode

```c
__int64 __fastcall IsValidGUID(LPCOLESTR lpsz)
{
  HRESULT v2; // eax
  int v3; // r8d
  CLSID pclsid; // [rsp+30h] [rbp-28h] BYREF

  pclsid = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_04fb59550d79390d980a26525e0212b0_Traceguids);
  }
  v2 = CLSIDFromString(lpsz, &pclsid);
  if ( (int)(v2 + 0x80000000) < 0 || v2 == -2147221167 )
    return 0;
  if ( v2 == -2147221005 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_04fb59550d79390d980a26525e0212b0_Traceguids, lpsz);
    }
    return 4200;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x80000000, v3, (_DWORD)lpsz, v2);
    }
    return 31;
  }
}

```

## disassembly

```asm
0x18002c31c  mov     [rsp+arg_8], rbx
0x18002c321  push    rsi
0x18002c322  sub     rsp, 50h
0x18002c326  mov     rax, cs:__security_cookie
0x18002c32d  xor     rax, rsp
0x18002c330  mov     [rsp+58h+var_18], rax
0x18002c335  xorps   xmm0, xmm0
0x18002c338  mov     rbx, rcx
0x18002c33b  movups  xmmword ptr [rsp+58h+pclsid.Data1], xmm0
0x18002c340  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c347  lea     rsi, WPP_GLOBAL_Control
0x18002c34e  cmp     rcx, rsi
0x18002c351  jz      short loc_18002C374
0x18002c353  test    byte ptr [rcx+1Ch], 2
0x18002c357  jz      short loc_18002C374
0x18002c359  cmp     byte ptr [rcx+19h], 5
0x18002c35d  jb      short loc_18002C374
0x18002c35f  mov     rcx, [rcx+10h]
0x18002c363  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x18002c36a  mov     edx, 1Dh
0x18002c36f  call    WPP_SF_
0x18002c374  lea     rdx, [rsp+58h+pclsid]; pclsid
0x18002c379  mov     rcx, rbx; lpsz
0x18002c37c  call    cs:__imp_CLSIDFromString
0x18002c383  nop     dword ptr [rax+rax+00h]
0x18002c388  mov     edx, 80000000h
0x18002c38d  lea     ecx, [rax+rdx]
0x18002c390  test    edx, ecx
0x18002c392  jnz     short loc_18002C408
0x18002c394  cmp     eax, 80040151h
0x18002c399  jz      short loc_18002C408
0x18002c39b  cmp     eax, 800401F3h
0x18002c3a0  jnz     short loc_18002C3D9
0x18002c3a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3a9  cmp     rcx, rsi
0x18002c3ac  jz      short loc_18002C3D2
0x18002c3ae  test    byte ptr [rcx+1Ch], 2
0x18002c3b2  jz      short loc_18002C3D2
0x18002c3b4  cmp     byte ptr [rcx+19h], 2
0x18002c3b8  jb      short loc_18002C3D2
0x18002c3ba  mov     rcx, [rcx+10h]
0x18002c3be  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x18002c3c5  mov     edx, 1Eh
0x18002c3ca  mov     r9, rbx
0x18002c3cd  call    WPP_SF_S
0x18002c3d2  mov     eax, 1068h
0x18002c3d7  jmp     short loc_18002C40A
0x18002c3d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3e0  cmp     rcx, rsi
0x18002c3e3  jz      short loc_18002C401
0x18002c3e5  test    byte ptr [rcx+1Ch], 2
0x18002c3e9  jz      short loc_18002C401
0x18002c3eb  cmp     byte ptr [rcx+19h], 2
0x18002c3ef  jb      short loc_18002C401
0x18002c3f1  mov     rcx, [rcx+10h]
0x18002c3f5  mov     r9, rbx
0x18002c3f8  mov     [rsp+58h+var_38], eax
0x18002c3fc  call    WPP_SF_SD
0x18002c401  mov     eax, 1Fh
0x18002c406  jmp     short loc_18002C40A
0x18002c408  xor     eax, eax
0x18002c40a  mov     rcx, [rsp+58h+var_18]
0x18002c40f  xor     rcx, rsp; StackCookie
0x18002c412  call    __security_check_cookie
0x18002c417  mov     rbx, [rsp+58h+arg_8]
0x18002c41c  add     rsp, 50h
0x18002c420  pop     rsi
0x18002c421  retn
```
