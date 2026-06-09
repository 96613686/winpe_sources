# _SetBindingDeviceInterfacePath

- ea: `0x18000eac4`
- end: `0x18000ecda`
- name: `_SetBindingDeviceInterfacePath`
- size: `534`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ece0`
- `0x18000ed40`

## callees

- `0x180005910`
- `0x180008cb0`
- `0x180008ff0`
- `0x180009020`
- `0x180009850`
- `0x18000b6f4`
- `0x18000d978`
- `0x18000eac4`
- `0x18000f06c`

## pseudocode

```c
__int64 __fastcall SetBindingDeviceInterfacePath(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  PVOID *v6; // rcx
  HKEY v7; // rdx
  unsigned int AccountRegistryPath; // ebx
  unsigned __int16 *v9; // r9
  int v10; // eax
  unsigned int v11; // r9d
  PVOID *v12; // rcx
  int v13; // eax
  unsigned int v15; // [rsp+20h] [rbp-288h]
  struct _SECURITY_ATTRIBUTES *v16; // [rsp+30h] [rbp-278h]
  unsigned int *v17; // [rsp+38h] [rbp-270h]
  _QWORD v18[4]; // [rsp+40h] [rbp-268h] BYREF
  unsigned __int16 v19[264]; // [rsp+60h] [rbp-248h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  memset(v18, 0, 24);
  if ( a1 && *a1 && a3 && *a3 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
      WPP_SF_SSS((TRACEHANDLE)v6[2], (__int64)a2, (__int64)a3);
    AccountRegistryPath = GetAccountRegistryPath(a1, (__int64)a2, v19);
    if ( (AccountRegistryPath & 0x80000000) == 0 )
    {
      v10 = ATL::CRegKey::Create((ATL::CRegKey *)v18, v7, v19, v9, v15, 0x2001Fu, v16, v17);
      if ( v10 )
      {
        if ( v10 > 0 )
          AccountRegistryPath = (unsigned __int16)v10 | 0x80070000;
        else
          AccountRegistryPath = v10;
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            &WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids,
            AccountRegistryPath);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_28;
      }
      v13 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)v18, a2, a3, v11);
      if ( !v13 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_30:
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x10) != 0 )
          WPP_SF_d(v12[2], 15, &WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids, AccountRegistryPath);
        ATL::CRegKey::Close((ATL::CRegKey *)v18);
        return AccountRegistryPath;
      }
      if ( v13 > 0 )
        AccountRegistryPath = (unsigned __int16)v13 | 0x80070000;
      else
        AccountRegistryPath = v13;
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_28:
        if ( AccountRegistryPath == -2147024894 )
          AccountRegistryPath = -2147023728;
        goto LABEL_30;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids,
        AccountRegistryPath);
    }
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_28;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
    WPP_SF_(v6[2], 11, &WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids);
  ATL::CRegKey::Close((ATL::CRegKey *)v18);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000eac4  mov     [rsp+arg_18], rbx
0x18000eac9  push    rbp
0x18000eaca  push    rsi
0x18000eacb  push    rdi
0x18000eacc  push    r14
0x18000eace  push    r15
0x18000ead0  sub     rsp, 280h
0x18000ead7  mov     rax, cs:__security_cookie
0x18000eade  xor     rax, rsp
0x18000eae1  mov     [rsp+2A8h+var_38], rax
0x18000eae9  mov     rdi, r8
0x18000eaec  mov     rsi, rdx
0x18000eaef  mov     rbx, rcx
0x18000eaf2  lea     r14, WPP_GLOBAL_Control
0x18000eaf9  lea     r15, WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids
0x18000eb00  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb07  cmp     rcx, r14
0x18000eb0a  jz      short loc_18000EB2A
0x18000eb0c  test    byte ptr [rcx+1Ch], 10h
0x18000eb10  jz      short loc_18000EB2A
0x18000eb12  mov     edx, 0Ah
0x18000eb17  mov     r8, r15
0x18000eb1a  mov     rcx, [rcx+10h]
0x18000eb1e  call    WPP_SF_
0x18000eb23  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb2a  xor     ebp, ebp
0x18000eb2c  mov     [rsp+2A8h+var_268], rbp
0x18000eb31  mov     [rsp+2A8h+var_260], rbp
0x18000eb36  mov     [rsp+2A8h+var_258], rbp
0x18000eb3b  test    rbx, rbx
0x18000eb3e  jz      loc_18000EC87
0x18000eb44  cmp     [rbx], bp
0x18000eb47  jz      loc_18000EC87
0x18000eb4d  test    rdi, rdi
0x18000eb50  jz      loc_18000EC87
0x18000eb56  cmp     [rdi], bp
0x18000eb59  jz      loc_18000EC87
0x18000eb5f  cmp     rcx, r14
0x18000eb62  jz      short loc_18000EB80
0x18000eb64  test    byte ptr [rcx+1Ch], 10h
0x18000eb68  jz      short loc_18000EB80
0x18000eb6a  mov     qword ptr [rsp+2A8h+var_280], rdi; __int64
0x18000eb6f  mov     qword ptr [rsp+2A8h+var_288], rsi; unsigned int
0x18000eb74  mov     r9, rbx
0x18000eb77  mov     rcx, [rcx+10h]; LoggerHandle
0x18000eb7b  call    WPP_SF_SSS
0x18000eb80  lea     r8, [rsp+2A8h+var_248]; unsigned __int16 *
0x18000eb85  mov     rcx, rbx; unsigned __int16 *
0x18000eb88  call    ?GetAccountRegistryPath@@YAJPEBG_KPEAG@Z; GetAccountRegistryPath(ushort const *,unsigned __int64,ushort *)
0x18000eb8d  mov     ebx, eax
0x18000eb8f  test    eax, eax
0x18000eb91  js      loc_18000EC3B
0x18000eb97  mov     [rsp+2A8h+var_280], 2001Fh; unsigned int
0x18000eb9f  lea     r8, [rsp+2A8h+var_248]; unsigned __int16 *
0x18000eba4  lea     rcx, [rsp+2A8h+var_268]; this
0x18000eba9  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18000ebae  test    eax, eax
0x18000ebb0  jz      short loc_18000EBF2
0x18000ebb2  jg      short loc_18000EBB8
0x18000ebb4  mov     ebx, eax
0x18000ebb6  jmp     short loc_18000EBC1
0x18000ebb8  movzx   ebx, ax
0x18000ebbb  or      ebx, 80070000h
0x18000ebc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebc8  cmp     rcx, r14
0x18000ebcb  jz      short loc_18000EBEE
0x18000ebcd  test    byte ptr [rcx+1Ch], 2
0x18000ebd1  jz      short loc_18000EBEE
0x18000ebd3  mov     edx, 0Dh
0x18000ebd8  mov     r9d, ebx
0x18000ebdb  mov     r8, r15
0x18000ebde  mov     rcx, [rcx+10h]
0x18000ebe2  call    WPP_SF_d
0x18000ebe7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebee  test    ebx, ebx
0x18000ebf0  js      short loc_18000EC42
0x18000ebf2  mov     r8, rdi; unsigned __int16 *
0x18000ebf5  mov     rdx, rsi; unsigned __int16 *
0x18000ebf8  lea     rcx, [rsp+2A8h+var_268]; this
0x18000ebfd  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x18000ec02  test    eax, eax
0x18000ec04  jz      short loc_18000EC7E
0x18000ec06  jg      short loc_18000EC0C
0x18000ec08  mov     ebx, eax
0x18000ec0a  jmp     short loc_18000EC15
0x18000ec0c  movzx   ebx, ax
0x18000ec0f  or      ebx, 80070000h
0x18000ec15  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec1c  cmp     rcx, r14
0x18000ec1f  jz      short loc_18000EC42
0x18000ec21  test    byte ptr [rcx+1Ch], 2
0x18000ec25  jz      short loc_18000EC42
0x18000ec27  mov     edx, 0Eh
0x18000ec2c  mov     r9d, ebx
0x18000ec2f  mov     r8, r15
0x18000ec32  mov     rcx, [rcx+10h]
0x18000ec36  call    WPP_SF_d
0x18000ec3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec42  mov     eax, 80070490h
0x18000ec47  cmp     ebx, 80070002h
0x18000ec4d  cmovz   ebx, eax
0x18000ec50  cmp     rcx, r14
0x18000ec53  jz      short loc_18000EC70
0x18000ec55  test    byte ptr [rcx+1Ch], 10h
0x18000ec59  jz      short loc_18000EC70
0x18000ec5b  mov     edx, 0Fh
0x18000ec60  mov     r9d, ebx
0x18000ec63  mov     r8, r15
0x18000ec66  mov     rcx, [rcx+10h]
0x18000ec6a  call    WPP_SF_d
0x18000ec6f  nop
0x18000ec70  lea     rcx, [rsp+2A8h+var_268]; this
0x18000ec75  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ec7a  mov     eax, ebx
0x18000ec7c  jmp     short loc_18000ECB3
0x18000ec7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec85  jmp     short loc_18000EC50
0x18000ec87  cmp     rcx, r14
0x18000ec8a  jz      short loc_18000ECA4
0x18000ec8c  test    byte ptr [rcx+1Ch], 2
0x18000ec90  jz      short loc_18000ECA4
0x18000ec92  mov     edx, 0Bh
0x18000ec97  mov     r8, r15
0x18000ec9a  mov     rcx, [rcx+10h]
0x18000ec9e  call    WPP_SF_
0x18000eca3  nop
0x18000eca4  lea     rcx, [rsp+2A8h+var_268]; this
0x18000eca9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ecae  mov     eax, 80070057h
0x18000ecb3  mov     rcx, [rsp+2A8h+var_38]
0x18000ecbb  xor     rcx, rsp; StackCookie
0x18000ecbe  call    __security_check_cookie
0x18000ecc3  mov     rbx, [rsp+2A8h+arg_18]
0x18000eccb  add     rsp, 280h
0x18000ecd2  pop     r15
0x18000ecd4  pop     r14
0x18000ecd6  pop     rdi
0x18000ecd7  pop     rsi
0x18000ecd8  pop     rbp
0x18000ecd9  retn
```
