# FwAdvPolicyLoadSuite(_tag_FW_SET_MANIPULATOR *,HKEY__ *,ushort const *,_tag_FW_BLOB_RULE *,ulong *,_tag_FW_RULE_PARSER * * const)

- ea: `0x180017dfc`
- end: `0x18001820f`
- name: `?FwAdvPolicyLoadSuite@@YAJPEAU_tag_FW_SET_MANIPULATOR@@PEAUHKEY__@@PEBGPEAU_tag_FW_BLOB_RULE@@PEAKQEAPEAU_tag_FW_RULE_PARSER@@@Z`
- size: `1043`
- prototype: `__int64 __fastcall(__int64 (__fastcall **)(struct _tag_FW_BLOB_RULE *), HKEY, const unsigned __int16 *, struct _tag_FW_BLOB_RULE *, unsigned int *, struct _tag_FW_RULE_PARSER **const)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001777c`

## callees

- `0x1800041d0`
- `0x1800042c4`
- `0x18000f280`
- `0x180017dfc`
- `0x180018218`
- `0x18001f650`
- `0x18003b010`

## import_xrefs

- `fwbase!FwFree` at `0x180017fb3`
- `fwbase!FwFree` at `0x180018100`
- `fwbase!FwFree` at `0x180018112`
- `fwbase!FwFree` at `0x1800181d3`
- `fwbase!FwFree` at `0x1800181dd`
- `fwbase!FwFree` at `0x180017fb3`
- `fwbase!FwFree` at `0x180018100`
- `fwbase!FwFree` at `0x180018112`
- `fwbase!FwFree` at `0x1800181d3`
- `fwbase!FwFree` at `0x1800181dd`
- `fwbase!FwRegOpenKey` at `0x180017e66`
- `fwbase!FwRegOpenKey` at `0x180017e66`
- `fwbase!FwRegQueryString` at `0x180017f14`
- `fwbase!FwRegQueryString` at `0x180017f14`
- `fwbase!FwRegCloseKey` at `0x1800181e7`
- `fwbase!FwRegCloseKey` at `0x1800181e7`
- `fwbase!FwRegQueryNumValues` at `0x180017ec0`
- `fwbase!FwRegQueryNumValues` at `0x180017ec0`
- `fwbase!FwRegEnumValueNameAndValueData` at `0x180018055`
- `fwbase!FwRegEnumValueNameAndValueData` at `0x180018055`

## pseudocode

```c
__int64 __fastcall FwAdvPolicyLoadSuite(
        __int64 (__fastcall **a1)(struct _tag_FW_BLOB_RULE *),
        HKEY a2,
        const unsigned __int16 *a3,
        struct _tag_FW_BLOB_RULE *a4,
        unsigned int *a5,
        struct _tag_FW_RULE_PARSER **const a6)
{
  int v8; // eax
  unsigned int v9; // edi
  LPCOLESTR v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int v13; // eax
  int v14; // esi
  unsigned int v15; // r15d
  __int64 (__fastcall *v16)(struct _tag_FW_BLOB_RULE *); // rbx
  __int64 v17; // rax
  __int64 (__fastcall *v18)(struct _tag_FW_BLOB_RULE *); // rax
  unsigned __int16 v19; // bx
  struct _tag_FW_BLOB_RULE *v20; // rax
  bool v21; // cc
  __int64 (__fastcall *v22)(struct _tag_FW_BLOB_RULE *); // rax
  unsigned int v24; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v25; // [rsp+44h] [rbp-35h] BYREF
  struct _tag_FW_RULE_PARSER **v26; // [rsp+48h] [rbp-31h]
  wchar_t *String; // [rsp+50h] [rbp-29h] BYREF
  LPCWSTR lpString2; // [rsp+58h] [rbp-21h] BYREF
  __int64 v29; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int16 *v30; // [rsp+68h] [rbp-11h] BYREF
  int v31; // [rsp+70h] [rbp-9h] BYREF
  unsigned int v32; // [rsp+74h] [rbp-5h] BYREF

  v29 = 0;
  v26 = a6;
  v31 = 0;
  v32 = 0;
  lpString2 = 0;
  String = 0;
  v8 = FwRegOpenKey(a2, a3, 9, &v29, &v31);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_48;
    v11 = 11;
LABEL_5:
    v12 = (unsigned int)v8;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids, v12);
    goto LABEL_48;
  }
  if ( v31 )
  {
    v8 = FwRegQueryNumValues(v29, &v32);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_48;
      v11 = 12;
      goto LABEL_5;
    }
  }
  else
  {
    v32 = 0;
  }
  v8 = FwRegQueryString(v29, 0, L"SkipVersion", &String, &v31);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_48;
    v11 = 13;
    goto LABEL_5;
  }
  if ( !v31 )
    goto LABEL_24;
  v30 = String;
  v25 = 0;
  v24 = 0;
  v8 = FwAdvPolicyDecodeVersion(String, &v25, &v24, (const unsigned __int16 **)&v30);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_48;
    v11 = 14;
    goto LABEL_5;
  }
  FwFree(String);
  String = 0;
  v30 = 0;
  if ( (unsigned __int16)((unsigned __int8)v24 | ((unsigned __int8)v25 << 8)) >= 0x221u )
  {
    *(_DWORD *)a1[5](a4) = 0x20000;
    v13 = 0;
    v32 = 0;
  }
  else
  {
LABEL_24:
    v13 = v32;
  }
  v14 = 0;
  if ( v13 )
  {
    v15 = 0;
    v16 = a1[14];
    v17 = ((__int64 (__fastcall *)(struct _tag_FW_BLOB_RULE *, _QWORD))a1[2])(a4, *a5);
    v16((struct _tag_FW_BLOB_RULE *)v17);
    v14 = 1;
    while ( v15 < v32 )
    {
      v8 = FwRegEnumValueNameAndValueData(v29, v15, &lpString2, &String, &v31, 0, 0);
      v9 = v8;
      if ( v8 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v11 = 15;
          goto LABEL_5;
        }
        goto LABEL_48;
      }
      if ( !v31 )
        break;
      v18 = a1[7];
      v24 = 0;
      v19 = *(_WORD *)v18(a4);
      v20 = (struct _tag_FW_BLOB_RULE *)((__int64 (__fastcall *)(struct _tag_FW_BLOB_RULE *, _QWORD))a1[2])(a4, *a5);
      v8 = FwAdvPolicySetParseField(lpString2, String, v20, &v24, v26[1], v19);
      if ( v8 == -2147467263 )
      {
        v21 = *(_WORD *)a1[7](a4) <= 0x221u;
        v22 = a1[5];
        if ( v21 )
        {
          *(_DWORD *)v22(a4) = 3670016;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x10) != 0 )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids,
              lpString2);
            v10 = WPP_GLOBAL_Control;
          }
          v9 = -2147024809;
          if ( v10 != (LPCOLESTR)&WPP_GLOBAL_Control && (v10[14] & 1) != 0 )
          {
            v11 = 17;
            v12 = 2147942487LL;
            goto LABEL_6;
          }
          goto LABEL_48;
        }
        *(_DWORD *)v22(a4) = 0x20000;
      }
      else
      {
        v9 = v8;
        if ( v8 < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v11 = 18;
            goto LABEL_5;
          }
          goto LABEL_48;
        }
      }
      ++v15;
      FwFree(lpString2);
      lpString2 = 0;
      FwFree(String);
      String = 0;
    }
  }
  *a5 += v14;
LABEL_48:
  FwFree(lpString2);
  FwFree(String);
  FwRegCloseKey(v29);
  return v9;
}

```

## disassembly

```asm
0x180017dfc  push    rbp
0x180017dfe  push    rbx
0x180017dff  push    rsi
0x180017e00  push    rdi
0x180017e01  push    r12
0x180017e03  push    r13
0x180017e05  push    r14
0x180017e07  push    r15
0x180017e09  lea     rbp, [rsp-0Fh]
0x180017e0e  sub     rsp, 88h
0x180017e15  mov     rax, cs:__security_cookie
0x180017e1c  xor     rax, rsp
0x180017e1f  mov     [rbp+47h+var_48], rax
0x180017e23  mov     r12, [rbp+47h+arg_20]
0x180017e27  xor     ebx, ebx
0x180017e29  mov     r13, rcx
0x180017e2c  mov     [rbp+47h+var_60], rbx
0x180017e30  mov     rcx, [rbp+47h+arg_28]
0x180017e34  mov     r10, r8
0x180017e37  mov     [rbp+47h+var_78], rcx
0x180017e3b  mov     rax, rdx
0x180017e3e  lea     rcx, [rbp+47h+var_50]
0x180017e42  mov     [rbp+47h+var_50], ebx
0x180017e45  mov     [rsp+0C0h+var_A0], rcx
0x180017e4a  lea     r8d, [rbx+9]
0x180017e4e  mov     r14, r9
0x180017e51  mov     [rbp+47h+var_4C], ebx
0x180017e54  mov     rcx, rax
0x180017e57  mov     [rbp+47h+lpString2], rbx
0x180017e5b  lea     r9, [rbp+47h+var_60]
0x180017e5f  mov     [rbp+47h+String], rbx
0x180017e63  mov     rdx, r10
0x180017e66  call    cs:__imp_FwRegOpenKey
0x180017e6c  mov     edi, eax
0x180017e6e  test    eax, eax
0x180017e70  jns     short loc_180017EB3
0x180017e72  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e79  lea     rbx, WPP_GLOBAL_Control
0x180017e80  cmp     rcx, rbx
0x180017e83  jz      loc_1800181CF
0x180017e89  mov     esi, 1
0x180017e8e  test    [rcx+1Ch], sil
0x180017e92  jz      loc_1800181CF
0x180017e98  lea     edx, [rsi+0Ah]
0x180017e9b  mov     r9d, eax
0x180017e9e  mov     rcx, [rcx+10h]
0x180017ea2  lea     r8, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids
0x180017ea9  call    WPP_SF_d
0x180017eae  jmp     loc_1800181CF
0x180017eb3  cmp     [rbp+47h+var_50], ebx
0x180017eb6  jz      short loc_180017EF7
0x180017eb8  mov     rcx, [rbp+47h+var_60]
0x180017ebc  lea     rdx, [rbp+47h+var_4C]
0x180017ec0  call    cs:__imp_FwRegQueryNumValues
0x180017ec6  mov     edi, eax
0x180017ec8  test    eax, eax
0x180017eca  jns     short loc_180017EFA
0x180017ecc  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ed3  lea     rbx, WPP_GLOBAL_Control
0x180017eda  cmp     rcx, rbx
0x180017edd  jz      loc_1800181CF
0x180017ee3  mov     esi, 1
0x180017ee8  test    [rcx+1Ch], sil
0x180017eec  jz      loc_1800181CF
0x180017ef2  lea     edx, [rsi+0Bh]
0x180017ef5  jmp     short loc_180017E9B
0x180017ef7  mov     [rbp+47h+var_4C], ebx
0x180017efa  mov     rcx, [rbp+47h+var_60]
0x180017efe  lea     rax, [rbp+47h+var_50]
0x180017f02  lea     r9, [rbp+47h+String]
0x180017f06  mov     [rsp+0C0h+var_A0], rax
0x180017f0b  lea     r8, aSkipversion; "SkipVersion"
0x180017f12  xor     edx, edx
0x180017f14  call    cs:__imp_FwRegQueryString
0x180017f1a  mov     edi, eax
0x180017f1c  test    eax, eax
0x180017f1e  jns     short loc_180017F4E
0x180017f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f27  lea     rbx, WPP_GLOBAL_Control
0x180017f2e  cmp     rcx, rbx
0x180017f31  jz      loc_1800181CF
0x180017f37  mov     esi, 1
0x180017f3c  test    [rcx+1Ch], sil
0x180017f40  jz      loc_1800181CF
0x180017f46  lea     edx, [rsi+0Ch]
0x180017f49  jmp     loc_180017E9B
0x180017f4e  mov     esi, 221h
0x180017f53  cmp     [rbp+47h+var_50], ebx
0x180017f56  jz      loc_180017FEE
0x180017f5c  mov     rcx, [rbp+47h+String]; String
0x180017f60  lea     r9, [rbp+47h+var_58]; unsigned __int16 **
0x180017f64  lea     r8, [rbp+47h+var_80]; unsigned int *
0x180017f68  mov     [rbp+47h+var_58], rcx
0x180017f6c  lea     rdx, [rbp+47h+var_7C]; unsigned int *
0x180017f70  mov     [rbp+47h+var_7C], ebx
0x180017f73  mov     [rbp+47h+var_80], ebx
0x180017f76  call    ?FwAdvPolicyDecodeVersion@@YAJPEBGPEAK1PEAPEBG@Z; FwAdvPolicyDecodeVersion(ushort const *,ulong *,ulong *,ushort const * *)
0x180017f7b  mov     edi, eax
0x180017f7d  test    eax, eax
0x180017f7f  jns     short loc_180017FAF
0x180017f81  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f88  lea     rbx, WPP_GLOBAL_Control
0x180017f8f  cmp     rcx, rbx
0x180017f92  jz      loc_1800181CF
0x180017f98  mov     esi, 1
0x180017f9d  test    [rcx+1Ch], sil
0x180017fa1  jz      loc_1800181CF
0x180017fa7  lea     edx, [rsi+0Dh]
0x180017faa  jmp     loc_180017E9B
0x180017faf  mov     rcx, [rbp+47h+String]
0x180017fb3  call    cs:__imp_FwFree
0x180017fb9  movzx   ecx, byte ptr [rbp+47h+var_7C]
0x180017fbd  movzx   eax, byte ptr [rbp+47h+var_80]
0x180017fc1  shl     cx, 8
0x180017fc5  or      cx, ax
0x180017fc8  mov     [rbp+47h+String], rbx
0x180017fcc  mov     [rbp+47h+var_58], rbx
0x180017fd0  cmp     si, cx
0x180017fd3  ja      short loc_180017FEE
0x180017fd5  mov     rax, [r13+28h]
0x180017fd9  mov     rcx, r14
0x180017fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fe1  mov     dword ptr [rax], 20000h
0x180017fe7  mov     eax, ebx
0x180017fe9  mov     [rbp+47h+var_4C], ebx
0x180017fec  jmp     short loc_180017FF1
0x180017fee  mov     eax, [rbp+47h+var_4C]
0x180017ff1  mov     esi, ebx
0x180017ff3  test    eax, eax
0x180017ff5  jz      loc_1800181CB
0x180017ffb  mov     edx, [r12]
0x180017fff  mov     r15d, ebx
0x180018002  mov     rax, [r13+10h]
0x180018006  mov     rcx, r14
0x180018009  mov     rbx, [r13+70h]
0x18001800d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018012  mov     rcx, rax
0x180018015  mov     rax, rbx
0x180018018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001801d  mov     esi, 1
0x180018022  cmp     r15d, [rbp+47h+var_4C]
0x180018026  jnb     loc_1800181CB
0x18001802c  mov     rcx, [rbp+47h+var_60]
0x180018030  lea     rax, [rbp+47h+var_50]
0x180018034  mov     [rsp+0C0h+var_90], 0
0x18001803d  lea     r9, [rbp+47h+String]
0x180018041  mov     dword ptr [rsp+0C0h+var_98], 0
0x180018049  lea     r8, [rbp+47h+lpString2]
0x18001804d  mov     edx, r15d
0x180018050  mov     [rsp+0C0h+var_A0], rax
0x180018055  call    cs:__imp_FwRegEnumValueNameAndValueData
0x18001805b  mov     edi, eax
0x18001805d  test    eax, eax
0x18001805f  js      loc_1800181A8
0x180018065  cmp     [rbp+47h+var_50], 0
0x180018069  jz      loc_1800181CB
0x18001806f  mov     rax, [r13+38h]
0x180018073  mov     rcx, r14
0x180018076  mov     [rbp+47h+var_80], 0
0x18001807d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018082  mov     edx, [r12]
0x180018086  mov     rcx, r14
0x180018089  movzx   ebx, word ptr [rax]
0x18001808c  mov     rax, [r13+10h]
0x180018090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018095  mov     rcx, [rbp+47h+var_78]
0x180018099  lea     r9, [rbp+47h+var_80]; unsigned int *
0x18001809d  mov     rdx, [rbp+47h+String]; unsigned __int16 *
0x1800180a1  mov     [rsp+0C0h+var_98], bx; unsigned __int16
0x1800180a6  mov     r8, [rcx+8]
0x1800180aa  mov     rcx, [rbp+47h+lpString2]; lpString2
0x1800180ae  mov     [rsp+0C0h+var_A0], r8; struct _tag_FW_RULE_PARSER *
0x1800180b3  mov     r8, rax; struct _tag_FW_BLOB_RULE *
0x1800180b6  call    ?FwAdvPolicySetParseField@@YAJPEBG0PEAU_tag_FW_BLOB_RULE@@PEAKPEAU_tag_FW_RULE_PARSER@@G@Z; FwAdvPolicySetParseField(ushort const *,ushort const *,_tag_FW_BLOB_RULE *,ulong *,_tag_FW_RULE_PARSER *,ushort)
0x1800180bb  cmp     eax, 80004001h
0x1800180c0  jnz     short loc_1800180EF
0x1800180c2  mov     rax, [r13+38h]
0x1800180c6  mov     rcx, r14
0x1800180c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180ce  mov     rdx, [r13+28h]
0x1800180d2  mov     ecx, 221h
0x1800180d7  cmp     [rax], cx
0x1800180da  mov     rcx, r14
0x1800180dd  mov     rax, rdx
0x1800180e0  jbe     short loc_180018125
0x1800180e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180e7  mov     dword ptr [rax], 20000h
0x1800180ed  jmp     short loc_1800180F9
0x1800180ef  mov     edi, eax
0x1800180f1  test    eax, eax
0x1800180f3  js      loc_180018185
0x1800180f9  mov     rcx, [rbp+47h+lpString2]
0x1800180fd  add     r15d, esi
0x180018100  call    cs:__imp_FwFree
0x180018106  mov     rcx, [rbp+47h+String]
0x18001810a  mov     [rbp+47h+lpString2], 0
0x180018112  call    cs:__imp_FwFree
0x180018118  mov     [rbp+47h+String], 0
0x180018120  jmp     loc_180018022
0x180018125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001812a  mov     dword ptr [rax], 380000h
0x180018130  mov     rcx, cs:WPP_GLOBAL_Control
0x180018137  lea     rbx, WPP_GLOBAL_Control
0x18001813e  cmp     rcx, rbx
0x180018141  jz      short loc_180018168
0x180018143  mov     edx, 10h
0x180018148  test    [rcx+1Ch], dl
0x18001814b  jz      short loc_180018168
0x18001814d  mov     r9, [rbp+47h+lpString2]
0x180018151  lea     r8, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids
0x180018158  mov     rcx, [rcx+10h]
0x18001815c  call    WPP_SF_S
0x180018161  mov     rcx, cs:WPP_GLOBAL_Control
0x180018168  mov     edi, 80070057h
0x18001816d  cmp     rcx, rbx
0x180018170  jz      short loc_1800181CF
0x180018172  test    [rcx+1Ch], sil
0x180018176  jz      short loc_1800181CF
0x180018178  mov     edx, 11h
0x18001817d  mov     r9d, edi
0x180018180  jmp     loc_180017E9E
0x180018185  mov     rcx, cs:WPP_GLOBAL_Control
0x18001818c  lea     rbx, WPP_GLOBAL_Control
0x180018193  cmp     rcx, rbx
0x180018196  jz      short loc_1800181CF
0x180018198  test    [rcx+1Ch], sil
0x18001819c  jz      short loc_1800181CF
0x18001819e  mov     edx, 12h
0x1800181a3  jmp     loc_180017E9B
0x1800181a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181af  lea     rbx, WPP_GLOBAL_Control
0x1800181b6  cmp     rcx, rbx
0x1800181b9  jz      short loc_1800181CF
0x1800181bb  test    [rcx+1Ch], sil
0x1800181bf  jz      short loc_1800181CF
0x1800181c1  mov     edx, 0Fh
0x1800181c6  jmp     loc_180017E9B
0x1800181cb  add     [r12], esi
0x1800181cf  mov     rcx, [rbp+47h+lpString2]
0x1800181d3  call    cs:__imp_FwFree
0x1800181d9  mov     rcx, [rbp+47h+String]
0x1800181dd  call    cs:__imp_FwFree
0x1800181e3  mov     rcx, [rbp+47h+var_60]
0x1800181e7  call    cs:__imp_FwRegCloseKey
0x1800181ed  mov     eax, edi
0x1800181ef  mov     rcx, [rbp+47h+var_48]
0x1800181f3  xor     rcx, rsp; StackCookie
0x1800181f6  call    __security_check_cookie
0x1800181fb  add     rsp, 88h
0x180018202  pop     r15
0x180018204  pop     r14
0x180018206  pop     r13
0x180018208  pop     r12
0x18001820a  pop     rdi
0x18001820b  pop     rsi
0x18001820c  pop     rbx
0x18001820d  pop     rbp
0x18001820e  retn
```
