# FwWriteAuthApps(_tag_FW_RULE_MANIPULATOR *,void *,ushort const *,_tag_FW_RULE *)

- ea: `0x180032a28`
- end: `0x180032bc3`
- name: `?FwWriteAuthApps@@YAJPEAU_tag_FW_RULE_MANIPULATOR@@PEAXPEBGPEAU_tag_FW_RULE@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(struct _tag_FW_RULE_MANIPULATOR *, _QWORD *, const unsigned __int16 *, struct _tag_FW_RULE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004e04`

## callees

- `0x1800042c4`
- `0x18001f650`
- `0x18001ffd4`
- `0x180032a28`

## import_xrefs

- `fwbase!FwFree` at `0x180032b98`
- `fwbase!FwFree` at `0x180032b98`
- `fwbase!FwRegCloseKey` at `0x180032b8e`
- `fwbase!FwRegCloseKey` at `0x180032b8e`
- `fwbase!FwRegCreateKey` at `0x180032b04`
- `fwbase!FwRegCreateKey` at `0x180032b04`
- `fwbase!FwRegSetString` at `0x180032b4d`
- `fwbase!FwRegSetString` at `0x180032b4d`
- `fwbase!FwAuthorizedAppEncode` at `0x180032abd`
- `fwbase!FwAuthorizedAppEncode` at `0x180032abd`

## pseudocode

```c
__int64 __fastcall FwWriteAuthApps(
        struct _tag_FW_RULE_MANIPULATOR *a1,
        _QWORD *a2,
        const unsigned __int16 *a3,
        struct _tag_FW_RULE *a4)
{
  __int64 v4; // r15
  __int128 v8; // xmm0
  bool v9; // zf
  int v10; // ebx
  LPCOLESTR v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v15; // [rsp+20h] [rbp-59h] BYREF
  __int64 v16; // [rsp+28h] [rbp-51h] BYREF
  __int64 v17; // [rsp+30h] [rbp-49h] BYREF
  __int64 v18; // [rsp+38h] [rbp-41h]
  int v19; // [rsp+48h] [rbp-31h]
  __int128 v20; // [rsp+50h] [rbp-29h]
  BOOL v21; // [rsp+98h] [rbp+1Fh]

  v4 = a2[5];
  v16 = 0;
  v15 = 0;
  memset_0(&v17, 0, 0x70u);
  v8 = *(_OWORD *)((char *)a4 + 184);
  v17 = *((_QWORD *)a4 + 3);
  v18 = *((_QWORD *)a4 + 34);
  v19 = *((_BYTE *)a4 + 176) & 1;
  v9 = *((_DWORD *)a4 + 72) == 3;
  v20 = v8;
  v21 = v9;
  v10 = FwAuthorizedAppEncode(&v17, &v16);
  if ( v10 >= 0 )
  {
    v10 = FwRegCreateKey(v4, a3, 3, &v15);
    if ( v10 >= 0 )
    {
      v13 = v18;
      if ( *((_DWORD *)a2 + 1) != 1 )
        v13 = *((_QWORD *)a4 + 2);
      v10 = FwRegSetString(v15, L"List", v13, v16);
      if ( v10 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v12 = 45;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v12 = 44;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v12 = 43;
LABEL_15:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_10622196d762368449fa8f46c322a63a_Traceguids, (unsigned int)v10);
    }
  }
  FwRegCloseKey(v15);
  FwFree(v16);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180032a28  mov     [rsp-8+arg_0], rbx
0x180032a2d  push    rbp
0x180032a2e  push    rsi
0x180032a2f  push    rdi
0x180032a30  push    r14
0x180032a32  push    r15
0x180032a34  lea     rbp, [rsp-37h]
0x180032a39  sub     rsp, 0B0h
0x180032a40  mov     rax, cs:__security_cookie
0x180032a47  xor     rax, rsp
0x180032a4a  mov     [rbp+57h+var_30], rax
0x180032a4e  mov     r15, [rdx+28h]
0x180032a52  lea     rcx, [rbp+57h+var_A0]; void *
0x180032a56  mov     rsi, rdx
0x180032a59  mov     [rbp+57h+var_A8], 0
0x180032a61  xor     edx, edx; Val
0x180032a63  mov     [rbp+57h+var_B0], 0
0x180032a6b  mov     r14, r8
0x180032a6e  mov     rdi, r9
0x180032a71  lea     r8d, [rdx+70h]; Size
0x180032a75  call    memset_0
0x180032a7a  mov     rax, [rdi+18h]
0x180032a7e  lea     rdx, [rbp+57h+var_A8]
0x180032a82  movups  xmm0, xmmword ptr [rdi+0B8h]
0x180032a89  mov     [rbp+57h+var_A0], rax
0x180032a8d  lea     rcx, [rbp+57h+var_A0]
0x180032a91  mov     rax, [rdi+110h]
0x180032a98  mov     [rbp+57h+var_98], rax
0x180032a9c  movzx   eax, byte ptr [rdi+0B0h]
0x180032aa3  and     eax, 1
0x180032aa6  mov     [rbp+57h+var_88], eax
0x180032aa9  xor     eax, eax
0x180032aab  cmp     dword ptr [rdi+120h], 3
0x180032ab2  movdqu  [rbp+57h+var_80], xmm0
0x180032ab7  setz    al
0x180032aba  mov     [rbp+57h+var_38], eax
0x180032abd  call    cs:__imp_FwAuthorizedAppEncode
0x180032ac3  mov     ebx, eax
0x180032ac5  test    eax, eax
0x180032ac7  jns     short loc_180032AF4
0x180032ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ad0  lea     rax, WPP_GLOBAL_Control
0x180032ad7  cmp     rcx, rax
0x180032ada  jz      loc_180032B8A
0x180032ae0  test    byte ptr [rcx+1Ch], 1
0x180032ae4  jz      loc_180032B8A
0x180032aea  mov     edx, 2Bh ; '+'
0x180032aef  jmp     loc_180032B77
0x180032af4  lea     r9, [rbp+57h+var_B0]
0x180032af8  mov     r8d, 3
0x180032afe  mov     rdx, r14
0x180032b01  mov     rcx, r15
0x180032b04  call    cs:__imp_FwRegCreateKey
0x180032b0a  mov     ebx, eax
0x180032b0c  test    eax, eax
0x180032b0e  jns     short loc_180032B30
0x180032b10  mov     rcx, cs:WPP_GLOBAL_Control
0x180032b17  lea     rax, WPP_GLOBAL_Control
0x180032b1e  cmp     rcx, rax
0x180032b21  jz      short loc_180032B8A
0x180032b23  test    byte ptr [rcx+1Ch], 1
0x180032b27  jz      short loc_180032B8A
0x180032b29  mov     edx, 2Ch ; ','
0x180032b2e  jmp     short loc_180032B77
0x180032b30  cmp     dword ptr [rsi+4], 1
0x180032b34  mov     r8, [rbp+57h+var_98]
0x180032b38  jz      short loc_180032B3E
0x180032b3a  mov     r8, [rdi+10h]
0x180032b3e  mov     r9, [rbp+57h+var_A8]
0x180032b42  lea     rdx, aList; "List"
0x180032b49  mov     rcx, [rbp+57h+var_B0]
0x180032b4d  call    cs:__imp_FwRegSetString
0x180032b53  mov     ebx, eax
0x180032b55  test    eax, eax
0x180032b57  jns     short loc_180032B8A
0x180032b59  mov     rcx, cs:WPP_GLOBAL_Control
0x180032b60  lea     rax, WPP_GLOBAL_Control
0x180032b67  cmp     rcx, rax
0x180032b6a  jz      short loc_180032B8A
0x180032b6c  test    byte ptr [rcx+1Ch], 1
0x180032b70  jz      short loc_180032B8A
0x180032b72  mov     edx, 2Dh ; '-'
0x180032b77  mov     rcx, [rcx+10h]
0x180032b7b  lea     r8, WPP_10622196d762368449fa8f46c322a63a_Traceguids
0x180032b82  mov     r9d, ebx
0x180032b85  call    WPP_SF_d
0x180032b8a  mov     rcx, [rbp+57h+var_B0]
0x180032b8e  call    cs:__imp_FwRegCloseKey
0x180032b94  mov     rcx, [rbp+57h+var_A8]
0x180032b98  call    cs:__imp_FwFree
0x180032b9e  mov     eax, ebx
0x180032ba0  mov     rcx, [rbp+57h+var_30]
0x180032ba4  xor     rcx, rsp; StackCookie
0x180032ba7  call    __security_check_cookie
0x180032bac  mov     rbx, [rsp+0D0h+arg_0]
0x180032bb4  add     rsp, 0B0h
0x180032bbb  pop     r15
0x180032bbd  pop     r14
0x180032bbf  pop     rdi
0x180032bc0  pop     rsi
0x180032bc1  pop     rbp
0x180032bc2  retn
```
