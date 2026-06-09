# AddKeywordProperty(IPropertyStore *,ushort const *)

- ea: `0x18000cef0`
- end: `0x18000d225`
- name: `?AddKeywordProperty@@YAJPEAUIPropertyStore@@PEBG@Z`
- size: `821`
- prototype: `__int64 __fastcall(struct IPropertyStore *, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005000`

## callees

- `0x18000cef0`
- `0x1800144b4`
- `0x1800191ac`
- `0x180019210`
- `0x18001b010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d07c`
- `msvcrt!_wcsicmp` at `0x18000d07c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000cfc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000cfc6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d026`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d0c9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d026`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000d0c9`

## pseudocode

```c
__int64 __fastcall AddKeywordProperty(struct IPropertyStore *a1, const unsigned __int16 *a2, __int64 a3)
{
  unsigned int v4; // edx
  unsigned int v5; // ebx
  const wchar_t **v6; // rcx
  unsigned int v7; // ebx
  char *v8; // rax
  __int64 v9; // rbx
  int v10; // eax
  int v11; // edx
  __int64 v12; // r8
  unsigned int v13; // ebx
  CIdentityProfileHandler *v14; // rcx
  CIdentityProfileHandler *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  int v19; // eax
  wchar_t *String2[3]; // [rsp+30h] [rbp-30h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-8h]
  int v23; // [rsp+98h] [rbp+38h] BYREF
  int v24; // [rsp+9Ch] [rbp+3Ch]

  v24 = HIDWORD(a2);
  String2[0] = (wchar_t *)L"connected";
  v23 = 0;
  *(_OWORD *)pvar = 0;
  pv = 0;
  String2[2] = (wchar_t *)"AddKeywordProperty";
  String2[1] = (wchar_t *)&v23;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "AddKeywordProperty");
  }
  v23 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->GetValue)(
          a1,
          &PKEY_Keywords,
          pvar);
  if ( v23 >= 0 && LOWORD(pvar[0]) == 4127 )
  {
    v4 = (unsigned int)pvar[1];
    if ( LODWORD(pvar[1]) )
    {
      v5 = 0;
      v6 = (const wchar_t **)pv;
      while ( v5 < v4 )
      {
        if ( v6[v5] )
        {
          if ( !_wcsicmp(v6[v5], String2[0]) )
            goto LABEL_13;
          v6 = (const wchar_t **)pv;
          v4 = (unsigned int)pvar[1];
        }
        ++v5;
      }
      v7 = v4 + 1;
      if ( v4 == -1 )
      {
        v23 = -2147024809;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_13;
        }
        v17 = 130;
        v18 = 2147942487LL;
      }
      else
      {
        v8 = (char *)CoTaskMemRealloc(v6, 8LL * v7);
        if ( v8 )
        {
          pv = v8;
          LODWORD(pvar[1]) = v7;
          v9 = 8LL * (v7 - 1);
          *(wchar_t **)&v8[v9] = String2[0];
          v10 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->SetValue)(
                  a1,
                  &PKEY_Keywords,
                  pvar);
          v23 = v10;
          if ( v10 < 0
            && WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              132,
              WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
              (unsigned int)v10);
          }
          *(_QWORD *)((char *)pv + v9) = 0;
          --LODWORD(pvar[1]);
          goto LABEL_13;
        }
        v23 = -2147024882;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_13;
        }
        v17 = 131;
        v18 = 2147942414LL;
      }
      WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v18);
      goto LABEL_13;
    }
  }
  PropVariantClear(pvar);
  LOWORD(pvar[0]) = 4127;
  LODWORD(pvar[1]) = 1;
  pv = String2;
  v19 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->SetValue)(
          a1,
          &PKEY_Keywords,
          pvar);
  v23 = v19;
  if ( v19 < 0
    && WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      129,
      WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
      (unsigned int)v19);
  }
  *(_OWORD *)pvar = 0;
  pv = 0;
LABEL_13:
  PropVariantClear(pvar);
  v13 = v23;
  if ( v23 >= 0 )
  {
LABEL_14:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_15;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
    return v13;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_sL(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, (unsigned int)"AddKeywordProperty", v23);
    goto LABEL_14;
  }
LABEL_15:
  if ( v14 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)v14 + 2), 12, v12, "AddKeywordProperty");
  return v13;
}

```

## disassembly

```asm
0x18000cef0  mov     [rsp-28h+arg_0], rbx
0x18000cef5  mov     [rsp-28h+arg_10], rsi
0x18000cefa  mov     [rsp-28h+arg_8], rdx
0x18000ceff  push    rbp
0x18000cf00  push    rdi
0x18000cf01  push    r12
0x18000cf03  push    r14
0x18000cf05  push    r15
0x18000cf07  mov     rbp, rsp
0x18000cf0a  sub     rsp, 60h
0x18000cf0e  mov     rdi, rcx
0x18000cf11  lea     rax, aConnected_0; "connected"
0x18000cf18  mov     [rbp+String2], rax
0x18000cf1c  xor     r14d, r14d
0x18000cf1f  mov     dword ptr [rbp+arg_8], r14d
0x18000cf23  xorps   xmm0, xmm0
0x18000cf26  xor     eax, eax
0x18000cf28  movups  xmmword ptr [rbp+pvar], xmm0
0x18000cf2c  mov     [rbp+pv], rax
0x18000cf30  lea     r12, aAddkeywordprop; "AddKeywordProperty"
0x18000cf37  mov     [rbp+var_20], r12
0x18000cf3b  lea     rax, [rbp+arg_8]
0x18000cf3f  mov     [rbp+var_28], rax
0x18000cf43  lea     r15, WPP_GLOBAL_Control
0x18000cf4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf51  cmp     rcx, r15
0x18000cf54  jz      short loc_18000CF63
0x18000cf56  test    dword ptr [rcx+1Ch], 400h
0x18000cf5d  jnz     loc_18000D148
0x18000cf63  mov     rax, [rdi]
0x18000cf66  lea     r8, [rbp+pvar]
0x18000cf6a  lea     rdx, PKEY_Keywords
0x18000cf71  mov     rcx, rdi
0x18000cf74  mov     rax, [rax+28h]
0x18000cf78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf7d  mov     dword ptr [rbp+arg_8], eax
0x18000cf80  mov     ebx, 101Fh
0x18000cf85  test    eax, eax
0x18000cf87  js      loc_18000D0C5
0x18000cf8d  cmp     word ptr [rbp+pvar], bx
0x18000cf91  jnz     loc_18000D0C5
0x18000cf97  mov     edx, dword ptr [rbp+pvar+8]
0x18000cf9a  test    edx, edx
0x18000cf9c  jz      loc_18000D0C5
0x18000cfa2  mov     rsi, [rbp+String2]
0x18000cfa6  mov     ebx, r14d
0x18000cfa9  mov     rcx, [rbp+pv]; pv
0x18000cfad  cmp     ebx, edx
0x18000cfaf  jb      loc_18000D06B
0x18000cfb5  lea     ebx, [rdx+1]
0x18000cfb8  test    ebx, ebx
0x18000cfba  jz      loc_18000D094
0x18000cfc0  mov     edx, ebx
0x18000cfc2  shl     rdx, 3; cb
0x18000cfc6  call    cs:__imp_CoTaskMemRealloc
0x18000cfcc  mov     rdx, rax
0x18000cfcf  test    rax, rax
0x18000cfd2  jz      loc_18000D17E
0x18000cfd8  mov     [rbp+pv], rax
0x18000cfdc  mov     dword ptr [rbp+pvar+8], ebx
0x18000cfdf  lea     eax, [rbx-1]
0x18000cfe2  lea     rbx, ds:0[rax*8]
0x18000cfea  mov     rax, [rbp+String2]
0x18000cfee  mov     [rbx+rdx], rax
0x18000cff2  mov     rax, [rdi]
0x18000cff5  lea     r8, [rbp+pvar]
0x18000cff9  lea     rdx, PKEY_Keywords
0x18000d000  mov     rcx, rdi
0x18000d003  mov     rax, [rax+30h]
0x18000d007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d00c  mov     dword ptr [rbp+arg_8], eax
0x18000d00f  test    eax, eax
0x18000d011  js      loc_18000D1A1
0x18000d017  mov     rax, [rbp+pv]
0x18000d01b  mov     [rbx+rax], r14
0x18000d01f  dec     dword ptr [rbp+pvar+8]
0x18000d022  lea     rcx, [rbp+pvar]; pvar
0x18000d026  call    cs:__imp_PropVariantClear
0x18000d02c  mov     ebx, dword ptr [rbp+arg_8]
0x18000d02f  test    ebx, ebx
0x18000d031  js      loc_18000D119
0x18000d037  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d03e  cmp     rcx, r15
0x18000d041  jz      short loc_18000D050
0x18000d043  test    dword ptr [rcx+1Ch], 400h
0x18000d04a  jnz     loc_18000D20F
0x18000d050  mov     eax, ebx
0x18000d052  lea     r11, [rsp+60h+var_s0]
0x18000d057  mov     rbx, [r11+30h]
0x18000d05b  mov     rsi, [r11+40h]
0x18000d05f  mov     rsp, r11
0x18000d062  pop     r15
0x18000d064  pop     r14
0x18000d066  pop     r12
0x18000d068  pop     rdi
0x18000d069  pop     rbp
0x18000d06a  retn
0x18000d06b  mov     eax, ebx
0x18000d06d  mov     r8, [rcx+rax*8]
0x18000d071  test    r8, r8
0x18000d074  jz      short loc_18000D08D
0x18000d076  mov     rdx, rsi; String2
0x18000d079  mov     rcx, r8; String1
0x18000d07c  call    cs:__imp__wcsicmp
0x18000d082  test    eax, eax
0x18000d084  jz      short loc_18000D022
0x18000d086  mov     rcx, [rbp+pv]
0x18000d08a  mov     edx, dword ptr [rbp+pvar+8]
0x18000d08d  inc     ebx
0x18000d08f  jmp     loc_18000CFAD
0x18000d094  mov     dword ptr [rbp+arg_8], 80070057h
0x18000d09b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0a2  cmp     rcx, r15
0x18000d0a5  jz      loc_18000D022
0x18000d0ab  test    byte ptr [rcx+1Ch], 4
0x18000d0af  jz      loc_18000D022
0x18000d0b5  mov     edx, 82h
0x18000d0ba  mov     r9d, 80070057h
0x18000d0c0  jmp     loc_18000D169
0x18000d0c5  lea     rcx, [rbp+pvar]; pvar
0x18000d0c9  call    cs:__imp_PropVariantClear
0x18000d0cf  mov     word ptr [rbp+pvar], bx
0x18000d0d3  mov     dword ptr [rbp+pvar+8], 1
0x18000d0da  lea     rax, [rbp+String2]
0x18000d0de  mov     [rbp+pv], rax
0x18000d0e2  mov     rax, [rdi]
0x18000d0e5  lea     r8, [rbp+pvar]
0x18000d0e9  lea     rdx, PKEY_Keywords
0x18000d0f0  mov     rcx, rdi
0x18000d0f3  mov     rax, [rax+30h]
0x18000d0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0fc  mov     dword ptr [rbp+arg_8], eax
0x18000d0ff  test    eax, eax
0x18000d101  js      loc_18000D1D8
0x18000d107  xorps   xmm0, xmm0
0x18000d10a  xor     eax, eax
0x18000d10c  movups  xmmword ptr [rbp+pvar], xmm0
0x18000d110  mov     [rbp+pv], rax
0x18000d114  jmp     loc_18000D022
0x18000d119  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d120  cmp     rcx, r15
0x18000d123  jz      loc_18000D050
0x18000d129  test    byte ptr [rcx+1Ch], 4
0x18000d12d  jz      loc_18000D03E
0x18000d133  mov     [rsp+60h+var_40], ebx
0x18000d137  mov     r9, r12
0x18000d13a  mov     rcx, [rcx+10h]
0x18000d13e  call    WPP_SF_sL
0x18000d143  jmp     loc_18000D037
0x18000d148  mov     edx, 0Ah
0x18000d14d  mov     r9, r12
0x18000d150  mov     rcx, [rcx+10h]
0x18000d154  call    WPP_SF_s
0x18000d159  jmp     loc_18000CF63
0x18000d15e  mov     edx, 83h
0x18000d163  mov     r9d, 8007000Eh
0x18000d169  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x18000d170  mov     rcx, [rcx+10h]
0x18000d174  call    WPP_SF_d
0x18000d179  jmp     loc_18000D022
0x18000d17e  mov     dword ptr [rbp+arg_8], 8007000Eh
0x18000d185  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d18c  cmp     rcx, r15
0x18000d18f  jz      loc_18000D022
0x18000d195  test    byte ptr [rcx+1Ch], 4
0x18000d199  jz      loc_18000D022
0x18000d19f  jmp     short loc_18000D15E
0x18000d1a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1a8  cmp     rcx, r15
0x18000d1ab  jz      loc_18000D017
0x18000d1b1  test    byte ptr [rcx+1Ch], 4
0x18000d1b5  jz      loc_18000D017
0x18000d1bb  mov     edx, 84h
0x18000d1c0  mov     r9d, eax
0x18000d1c3  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x18000d1ca  mov     rcx, [rcx+10h]
0x18000d1ce  call    WPP_SF_d
0x18000d1d3  jmp     loc_18000D017
0x18000d1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1df  cmp     rcx, r15
0x18000d1e2  jz      loc_18000D107
0x18000d1e8  test    byte ptr [rcx+1Ch], 4
0x18000d1ec  jz      loc_18000D107
0x18000d1f2  mov     edx, 81h
0x18000d1f7  mov     r9d, eax
0x18000d1fa  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x18000d201  mov     rcx, [rcx+10h]
0x18000d205  call    WPP_SF_d
0x18000d20a  jmp     loc_18000D107
0x18000d20f  mov     edx, 0Ch
0x18000d214  mov     r9, r12
0x18000d217  mov     rcx, [rcx+10h]
0x18000d21b  call    WPP_SF_s
0x18000d220  jmp     loc_18000D050
```
