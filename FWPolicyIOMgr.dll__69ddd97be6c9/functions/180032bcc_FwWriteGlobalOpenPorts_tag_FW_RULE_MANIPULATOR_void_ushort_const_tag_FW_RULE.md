# FwWriteGlobalOpenPorts(_tag_FW_RULE_MANIPULATOR *,void *,ushort const *,_tag_FW_RULE *)

- ea: `0x180032bcc`
- end: `0x180032dbc`
- name: `?FwWriteGlobalOpenPorts@@YAJPEAU_tag_FW_RULE_MANIPULATOR@@PEAXPEBGPEAU_tag_FW_RULE@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(struct _tag_FW_RULE_MANIPULATOR *, _QWORD *, const unsigned __int16 *, struct _tag_FW_RULE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004e04`

## callees

- `0x1800042c4`
- `0x18001e9ac`
- `0x18001f650`
- `0x18001ffd4`
- `0x180032bcc`

## import_xrefs

- `fwbase!FwFree` at `0x180032d91`
- `fwbase!FwFree` at `0x180032d91`
- `fwbase!FwRegCloseKey` at `0x180032d87`
- `fwbase!FwRegCloseKey` at `0x180032d87`
- `fwbase!FwRegCreateKey` at `0x180032cf6`
- `fwbase!FwRegCreateKey` at `0x180032cf6`
- `fwbase!FwRegSetString` at `0x180032d7b`
- `fwbase!FwRegSetString` at `0x180032d7b`
- `fwbase!FwStaticFwPortEncode` at `0x180032c9c`
- `fwbase!FwStaticFwPortEncode` at `0x180032c9c`
- `fwbase!FwStaticFwPortEncodeValueName` at `0x180032d33`
- `fwbase!FwStaticFwPortEncodeValueName` at `0x180032d33`

## pseudocode

```c
__int64 __fastcall FwWriteGlobalOpenPorts(
        struct _tag_FW_RULE_MANIPULATOR *a1,
        _QWORD *a2,
        const unsigned __int16 *a3,
        struct _tag_FW_RULE *a4)
{
  __int64 v4; // r15
  unsigned __int16 v8; // cx
  int v9; // eax
  __int128 v10; // xmm0
  bool v11; // zf
  int v12; // ebx
  LPCOLESTR v13; // rcx
  __int64 v14; // rdx
  __int128 *v15; // r8
  __int64 v17; // [rsp+20h] [rbp-69h] BYREF
  __int64 v18; // [rsp+28h] [rbp-61h] BYREF
  __int64 v19; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int16 v20; // [rsp+38h] [rbp-51h]
  unsigned int v21; // [rsp+3Ch] [rbp-4Dh]
  int v22; // [rsp+40h] [rbp-49h]
  __int128 v23; // [rsp+48h] [rbp-41h]
  BOOL v24; // [rsp+90h] [rbp+7h]
  __int128 v25; // [rsp+A0h] [rbp+17h] BYREF
  int v26; // [rsp+B0h] [rbp+27h]

  v4 = a2[5];
  v18 = 0;
  v17 = 0;
  v26 = 0;
  v25 = 0;
  memset_0(&v19, 0, 0x70u);
  if ( **((_WORD **)a4 + 9) != *(_WORD *)(*((_QWORD *)a4 + 9) + 2LL) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v8 = **((_WORD **)a4 + 9);
  v19 = *((_QWORD *)a4 + 3);
  v9 = 6;
  v20 = v8;
  if ( *((_WORD *)a4 + 24) != 6 )
  {
    v9 = v21;
    if ( *((_WORD *)a4 + 24) == 17 )
      v9 = 17;
  }
  v10 = *(_OWORD *)((char *)a4 + 184);
  v21 = v9;
  v22 = *((_BYTE *)a4 + 176) & 1;
  v11 = *((_DWORD *)a4 + 72) == 3;
  v23 = v10;
  v24 = v11;
  v12 = FwStaticFwPortEncode(&v19, &v18);
  if ( v12 >= 0 )
  {
    v12 = FwRegCreateKey(v4, a3, 2, &v17);
    if ( v12 >= 0 )
    {
      if ( *((_DWORD *)a2 + 1) )
      {
        v12 = FwStaticFwPortEncodeValueName(v20, v21, &v25);
        if ( v12 < 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v14 = 42;
            goto LABEL_10;
          }
          goto LABEL_23;
        }
        v15 = &v25;
      }
      else
      {
        v15 = (__int128 *)*((_QWORD *)a4 + 2);
      }
      v12 = FwRegSetString(v17, L"List", v15, v18);
      goto LABEL_23;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v14 = 41;
      goto LABEL_10;
    }
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v14 = 40;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_10622196d762368449fa8f46c322a63a_Traceguids, (unsigned int)v12);
    }
  }
LABEL_23:
  FwRegCloseKey(v17);
  FwFree(v18);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180032bcc  mov     [rsp-8+arg_0], rbx
0x180032bd1  push    rbp
0x180032bd2  push    rsi
0x180032bd3  push    rdi
0x180032bd4  push    r14
0x180032bd6  push    r15
0x180032bd8  lea     rbp, [rsp-37h]
0x180032bdd  sub     rsp, 0C0h
0x180032be4  mov     rax, cs:__security_cookie
0x180032beb  xor     rax, rsp
0x180032bee  mov     [rbp+57h+var_28], rax
0x180032bf2  mov     r15, [rdx+28h]
0x180032bf6  lea     rcx, [rbp+57h+var_B0]; void *
0x180032bfa  xor     eax, eax
0x180032bfc  mov     [rbp+57h+var_B8], 0
0x180032c04  mov     r14, r8
0x180032c07  mov     [rbp+57h+var_C0], 0
0x180032c0f  mov     rsi, rdx
0x180032c12  mov     [rbp+57h+var_30], eax
0x180032c15  xorps   xmm0, xmm0
0x180032c18  xor     edx, edx; Val
0x180032c1a  lea     r8d, [rax+70h]; Size
0x180032c1e  mov     rdi, r9
0x180032c21  movups  [rbp+57h+var_40], xmm0
0x180032c25  call    memset_0
0x180032c2a  mov     rcx, [rdi+48h]
0x180032c2e  movzx   eax, word ptr [rcx+2]
0x180032c32  cmp     [rcx], ax
0x180032c35  jz      short loc_180032C3C
0x180032c37  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180032c3c  mov     rax, [rdi+48h]
0x180032c40  movzx   ecx, word ptr [rax]
0x180032c43  mov     rax, [rdi+18h]
0x180032c47  mov     [rbp+57h+var_B0], rax
0x180032c4b  mov     eax, 6
0x180032c50  mov     [rbp+57h+var_A8], cx
0x180032c54  cmp     [rdi+30h], ax
0x180032c58  jz      short loc_180032C69
0x180032c5a  mov     eax, [rbp+57h+var_A4]
0x180032c5d  mov     ecx, 11h
0x180032c62  cmp     [rdi+30h], cx
0x180032c66  cmovz   eax, ecx
0x180032c69  movups  xmm0, xmmword ptr [rdi+0B8h]
0x180032c70  mov     [rbp+57h+var_A4], eax
0x180032c73  lea     rdx, [rbp+57h+var_B8]
0x180032c77  movzx   eax, byte ptr [rdi+0B0h]
0x180032c7e  lea     rcx, [rbp+57h+var_B0]
0x180032c82  and     eax, 1
0x180032c85  mov     [rbp+57h+var_A0], eax
0x180032c88  xor     eax, eax
0x180032c8a  cmp     dword ptr [rdi+120h], 3
0x180032c91  movdqu  [rbp+57h+var_98], xmm0
0x180032c96  setz    al
0x180032c99  mov     [rbp+57h+var_50], eax
0x180032c9c  call    cs:__imp_FwStaticFwPortEncode
0x180032ca2  mov     ebx, eax
0x180032ca4  test    eax, eax
0x180032ca6  jns     short loc_180032CE6
0x180032ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x180032caf  lea     rax, WPP_GLOBAL_Control
0x180032cb6  cmp     rcx, rax
0x180032cb9  jz      loc_180032D83
0x180032cbf  test    byte ptr [rcx+1Ch], 1
0x180032cc3  jz      loc_180032D83
0x180032cc9  mov     edx, 28h ; '('
0x180032cce  mov     rcx, [rcx+10h]
0x180032cd2  lea     r8, WPP_10622196d762368449fa8f46c322a63a_Traceguids
0x180032cd9  mov     r9d, ebx
0x180032cdc  call    WPP_SF_d
0x180032ce1  jmp     loc_180032D83
0x180032ce6  lea     r9, [rbp+57h+var_C0]
0x180032cea  mov     r8d, 2
0x180032cf0  mov     rdx, r14
0x180032cf3  mov     rcx, r15
0x180032cf6  call    cs:__imp_FwRegCreateKey
0x180032cfc  mov     ebx, eax
0x180032cfe  test    eax, eax
0x180032d00  jns     short loc_180032D22
0x180032d02  mov     rcx, cs:WPP_GLOBAL_Control
0x180032d09  lea     rax, WPP_GLOBAL_Control
0x180032d10  cmp     rcx, rax
0x180032d13  jz      short loc_180032D83
0x180032d15  test    byte ptr [rcx+1Ch], 1
0x180032d19  jz      short loc_180032D83
0x180032d1b  mov     edx, 29h ; ')'
0x180032d20  jmp     short loc_180032CCE
0x180032d22  cmp     dword ptr [rsi+4], 0
0x180032d26  jz      short loc_180032D68
0x180032d28  mov     edx, [rbp+57h+var_A4]
0x180032d2b  lea     r8, [rbp+57h+var_40]
0x180032d2f  movzx   ecx, [rbp+57h+var_A8]
0x180032d33  call    cs:__imp_FwStaticFwPortEncodeValueName
0x180032d39  mov     ebx, eax
0x180032d3b  test    eax, eax
0x180032d3d  jns     short loc_180032D62
0x180032d3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032d46  lea     rax, WPP_GLOBAL_Control
0x180032d4d  cmp     rcx, rax
0x180032d50  jz      short loc_180032D83
0x180032d52  test    byte ptr [rcx+1Ch], 1
0x180032d56  jz      short loc_180032D83
0x180032d58  mov     edx, 2Ah ; '*'
0x180032d5d  jmp     loc_180032CCE
0x180032d62  lea     r8, [rbp+57h+var_40]
0x180032d66  jmp     short loc_180032D6C
0x180032d68  mov     r8, [rdi+10h]
0x180032d6c  mov     r9, [rbp+57h+var_B8]
0x180032d70  lea     rdx, aList; "List"
0x180032d77  mov     rcx, [rbp+57h+var_C0]
0x180032d7b  call    cs:__imp_FwRegSetString
0x180032d81  mov     ebx, eax
0x180032d83  mov     rcx, [rbp+57h+var_C0]
0x180032d87  call    cs:__imp_FwRegCloseKey
0x180032d8d  mov     rcx, [rbp+57h+var_B8]
0x180032d91  call    cs:__imp_FwFree
0x180032d97  mov     eax, ebx
0x180032d99  mov     rcx, [rbp+57h+var_28]
0x180032d9d  xor     rcx, rsp; StackCookie
0x180032da0  call    __security_check_cookie
0x180032da5  mov     rbx, [rsp+0E0h+arg_0]
0x180032dad  add     rsp, 0C0h
0x180032db4  pop     r15
0x180032db6  pop     r14
0x180032db8  pop     rdi
0x180032db9  pop     rsi
0x180032dba  pop     rbp
0x180032dbb  retn
```
