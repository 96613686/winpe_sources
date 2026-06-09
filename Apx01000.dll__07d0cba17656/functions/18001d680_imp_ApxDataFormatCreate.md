# imp_ApxDataFormatCreate

- ea: `0x18001d680`
- end: `0x18001d8b5`
- name: `imp_ApxDataFormatCreate`
- size: `565`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this, Apx::ApfVerify *, struct _APX_DATAFORMAT_CONFIG *, Apx::ApfVerify *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180017ba4`

## callees

- `0x18000a12c`
- `0x18000a154`
- `0x18000a820`
- `0x18000a8e8`
- `0x18000a948`
- `0x18000ae48`
- `0x18000be74`
- `0x18000d210`
- `0x18001d4fc`
- `0x18001d680`

## string_xrefs

- `0x18001d72e`: `Config`

## pseudocode

```c
__int64 __fastcall imp_ApxDataFormatCreate(
        Apx::ApfVerify *this,
        Apx::ApfVerify *a2,
        struct _APX_DATAFORMAT_CONFIG *a3,
        Apx::ApfVerify *a4)
{
  Apx::ApfVerify *v8; // rcx
  int IsNull; // ebx
  struct APX_CLIENT_GLOBALS__ *v10; // rdx
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r8
  _QWORD *v14; // rcx
  __int64 v15; // r9
  struct Apx::ApfDataFormat *v17; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_085bb02c36d139f159054a9413a74e1a_Traceguids);
  }
  v17 = 0;
  IsNull = Apx::ApfVerify::IsNull(this, L"Globals", (const unsigned __int16 *)a3);
  if ( IsNull < 0 )
    goto LABEL_30;
  IsNull = Apx::ApfVerify::IsApxInitialized(v8);
  if ( IsNull < 0 )
    goto LABEL_30;
  IsNull = Apx::ApfVerify::ValidateClientBindings(this, v10);
  if ( IsNull < 0 )
    goto LABEL_30;
  IsNull = Apx::ApfVerify::IsNull(a2, L"Attributes", v11);
  if ( IsNull < 0 )
    goto LABEL_30;
  IsNull = Apx::ApfVerify::IsNotNull(a3, L"Config", v12);
  if ( IsNull < 0 )
    goto LABEL_30;
  IsNull = Apx::ApfVerify::IsNotNull(a4, L"DataFormat", v13);
  if ( IsNull < 0 )
    goto LABEL_30;
  *(_QWORD *)a4 = 0;
  if ( *(_DWORD *)a3 == 24 )
  {
    v15 = *((unsigned int *)a3 + 1);
    if ( (_DWORD)v15 )
    {
      IsNull = -2147024809;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_31;
      WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_085bb02c36d139f159054a9413a74e1a_Traceguids, v15, 0);
    }
    else if ( *((int *)a3 + 2) < 1 )
    {
      IsNull = Apx::ApfDataFormat::_CreateAndInitialize(a3, &v17);
      if ( IsNull < 0 )
      {
        if ( v17 )
          imp_ApxObjectDelete(0, (Apx::ApfVerify *)~(unsigned __int64)v17);
      }
      else
      {
        IsNull = 0;
        *(_QWORD *)a4 = ~(unsigned __int64)v17;
      }
    }
    else
    {
      IsNull = -2147024809;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_31;
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_085bb02c36d139f159054a9413a74e1a_Traceguids);
    }
    goto LABEL_30;
  }
  IsNull = -2147024809;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)IsNull;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DDd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_085bb02c36d139f159054a9413a74e1a_Traceguids,
      24,
      *(_DWORD *)a3);
LABEL_30:
    v14 = WPP_GLOBAL_Control;
  }
LABEL_31:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 5u )
    WPP_SF_(v14[2], 14, WPP_085bb02c36d139f159054a9413a74e1a_Traceguids);
  return (unsigned int)IsNull;
}

```

## disassembly

```asm
0x18001d680  push    rbx
0x18001d682  push    rbp
0x18001d683  push    rsi
0x18001d684  push    rdi
0x18001d685  push    r12
0x18001d687  push    r13
0x18001d689  push    r14
0x18001d68b  sub     rsp, 40h
0x18001d68f  mov     rsi, r9
0x18001d692  mov     rdi, r8
0x18001d695  mov     r14, rdx
0x18001d698  mov     rbp, rcx
0x18001d69b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6a2  lea     r12, WPP_GLOBAL_Control
0x18001d6a9  lea     r13, WPP_085bb02c36d139f159054a9413a74e1a_Traceguids
0x18001d6b0  cmp     rcx, r12
0x18001d6b3  jz      short loc_18001D6D2
0x18001d6b5  test    byte ptr [rcx+1Ch], 1
0x18001d6b9  jz      short loc_18001D6D2
0x18001d6bb  cmp     byte ptr [rcx+19h], 5
0x18001d6bf  jb      short loc_18001D6D2
0x18001d6c1  mov     rcx, [rcx+10h]
0x18001d6c5  mov     edx, 0Ah
0x18001d6ca  mov     r8, r13
0x18001d6cd  call    WPP_SF_
0x18001d6d2  lea     rdx, aGlobals; "Globals"
0x18001d6d9  mov     [rsp+78h+var_48], 0
0x18001d6e2  mov     rcx, rbp; this
0x18001d6e5  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18001d6ea  mov     ebx, eax
0x18001d6ec  test    eax, eax
0x18001d6ee  js      loc_18001D87B
0x18001d6f4  call    ?IsApxInitialized@ApfVerify@Apx@@YAJXZ; Apx::ApfVerify::IsApxInitialized(void)
0x18001d6f9  mov     ebx, eax
0x18001d6fb  test    eax, eax
0x18001d6fd  js      loc_18001D87B
0x18001d703  mov     rcx, rbp; this
0x18001d706  call    ?ValidateClientBindings@ApfVerify@Apx@@YAJPEAUAPX_CLIENT_GLOBALS__@@@Z; Apx::ApfVerify::ValidateClientBindings(APX_CLIENT_GLOBALS__ *)
0x18001d70b  mov     ebx, eax
0x18001d70d  test    eax, eax
0x18001d70f  js      loc_18001D87B
0x18001d715  lea     rdx, aAttributes; "Attributes"
0x18001d71c  mov     rcx, r14; this
0x18001d71f  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18001d724  mov     ebx, eax
0x18001d726  test    eax, eax
0x18001d728  js      loc_18001D87B
0x18001d72e  lea     rdx, aConfig_0; "Config"
0x18001d735  mov     rcx, rdi; this
0x18001d738  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001d73d  mov     ebx, eax
0x18001d73f  test    eax, eax
0x18001d741  js      loc_18001D87B
0x18001d747  lea     rdx, aDataformat; "DataFormat"
0x18001d74e  mov     rcx, rsi; this
0x18001d751  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001d756  mov     ebx, eax
0x18001d758  test    eax, eax
0x18001d75a  js      loc_18001D87B
0x18001d760  mov     qword ptr [rsi], 0
0x18001d767  mov     r9d, 18h
0x18001d76d  mov     eax, [rdi]
0x18001d76f  cmp     eax, r9d
0x18001d772  jz      short loc_18001D7B6
0x18001d774  mov     ebx, 80070057h
0x18001d779  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d780  cmp     rcx, r12
0x18001d783  jz      loc_18001D8A4
0x18001d789  test    byte ptr [rcx+1Ch], 40h
0x18001d78d  jz      loc_18001D882
0x18001d793  cmp     byte ptr [rcx+19h], 2
0x18001d797  jb      loc_18001D882
0x18001d79d  mov     rcx, [rcx+10h]
0x18001d7a1  lea     edx, [r9-0Dh]
0x18001d7a5  mov     r8, r13
0x18001d7a8  mov     [rsp+78h+var_58], eax
0x18001d7ac  call    WPP_SF_DDd
0x18001d7b1  jmp     loc_18001D87B
0x18001d7b6  mov     r9d, [rdi+4]
0x18001d7ba  test    r9d, r9d
0x18001d7bd  jz      short loc_18001D803
0x18001d7bf  mov     ebx, 80070057h
0x18001d7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7cb  cmp     rcx, r12
0x18001d7ce  jz      loc_18001D8A4
0x18001d7d4  test    byte ptr [rcx+1Ch], 40h
0x18001d7d8  jz      loc_18001D882
0x18001d7de  cmp     byte ptr [rcx+19h], 2
0x18001d7e2  jb      loc_18001D882
0x18001d7e8  mov     rcx, [rcx+10h]
0x18001d7ec  mov     edx, 0Ch
0x18001d7f1  mov     r8, r13
0x18001d7f4  mov     [rsp+78h+var_58], 0
0x18001d7fc  call    WPP_SF_DDd
0x18001d801  jmp     short loc_18001D87B
0x18001d803  mov     r9d, [rdi+8]
0x18001d807  cmp     r9d, 1
0x18001d80b  jl      short loc_18001D845
0x18001d80d  mov     ebx, 80070057h
0x18001d812  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d819  cmp     rcx, r12
0x18001d81c  jz      loc_18001D8A4
0x18001d822  test    byte ptr [rcx+1Ch], 40h
0x18001d826  jz      short loc_18001D882
0x18001d828  cmp     byte ptr [rcx+19h], 2
0x18001d82c  jb      short loc_18001D882
0x18001d82e  mov     rcx, [rcx+10h]
0x18001d832  mov     edx, 0Dh
0x18001d837  mov     r8, r13
0x18001d83a  mov     [rsp+78h+var_58], ebx
0x18001d83e  call    WPP_SF_dd
0x18001d843  jmp     short loc_18001D87B
0x18001d845  lea     rdx, [rsp+78h+var_48]; struct Apx::ApfDataFormat **
0x18001d84a  mov     rcx, rdi; struct _APX_DATAFORMAT_CONFIG *
0x18001d84d  call    ?_CreateAndInitialize@ApfDataFormat@Apx@@SAJPEAU_APX_DATAFORMAT_CONFIG@@PEAPEAV12@@Z; Apx::ApfDataFormat::_CreateAndInitialize(_APX_DATAFORMAT_CONFIG *,Apx::ApfDataFormat * *)
0x18001d852  mov     ebx, eax
0x18001d854  test    eax, eax
0x18001d856  js      short loc_18001D867
0x18001d858  mov     rax, [rsp+78h+var_48]
0x18001d85d  xor     ebx, ebx
0x18001d85f  not     rax
0x18001d862  mov     [rsi], rax
0x18001d865  jmp     short loc_18001D87B
0x18001d867  mov     rdx, [rsp+78h+var_48]
0x18001d86c  test    rdx, rdx
0x18001d86f  jz      short loc_18001D87B
0x18001d871  not     rdx; Apx::ApfVerify *
0x18001d874  xor     ecx, ecx; this
0x18001d876  call    imp_ApxObjectDelete
0x18001d87b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d882  cmp     rcx, r12
0x18001d885  jz      short loc_18001D8A4
0x18001d887  test    byte ptr [rcx+1Ch], 1
0x18001d88b  jz      short loc_18001D8A4
0x18001d88d  cmp     byte ptr [rcx+19h], 5
0x18001d891  jb      short loc_18001D8A4
0x18001d893  mov     rcx, [rcx+10h]
0x18001d897  mov     edx, 0Eh
0x18001d89c  mov     r8, r13
0x18001d89f  call    WPP_SF_
0x18001d8a4  mov     eax, ebx
0x18001d8a6  add     rsp, 40h
0x18001d8aa  pop     r14
0x18001d8ac  pop     r13
0x18001d8ae  pop     r12
0x18001d8b0  pop     rdi
0x18001d8b1  pop     rsi
0x18001d8b2  pop     rbp
0x18001d8b3  pop     rbx
0x18001d8b4  retn
```
