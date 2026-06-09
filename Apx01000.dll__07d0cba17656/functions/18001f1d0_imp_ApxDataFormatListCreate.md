# imp_ApxDataFormatListCreate

- ea: `0x18001f1d0`
- end: `0x18001f3ba`
- name: `imp_ApxDataFormatListCreate`
- size: `490`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this, Apx::ApfVerify *, Apx::ApfVerify *, Apx::ApfVerify *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000a12c`
- `0x18000a154`
- `0x18000a820`
- `0x18000a8e8`
- `0x18000a948`
- `0x18000ae48`
- `0x18000d210`
- `0x18001ef48`
- `0x18001f1d0`

## string_xrefs

- `0x18001f279`: `Config`

## pseudocode

```c
__int64 __fastcall imp_ApxDataFormatListCreate(
        Apx::ApfVerify *this,
        Apx::ApfVerify *a2,
        Apx::ApfVerify *a3,
        Apx::ApfVerify *a4)
{
  Apx::ApfVerify *v8; // rcx
  int IsNull; // ebx
  struct APX_CLIENT_GLOBALS__ *v10; // rdx
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r8
  struct _APX_DATAFORMAT_LIST_CONFIG *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // r9
  struct Apx::ApfDataFormatList *v18; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_62a05fd9d1433e3077cc2cc299829a3e_Traceguids);
  }
  v18 = 0;
  IsNull = Apx::ApfVerify::IsNull(this, L"Globals", (const unsigned __int16 *)a3);
  if ( IsNull < 0 )
    goto LABEL_25;
  IsNull = Apx::ApfVerify::IsApxInitialized(v8);
  if ( IsNull < 0 )
    goto LABEL_25;
  IsNull = Apx::ApfVerify::ValidateClientBindings(this, v10);
  if ( IsNull < 0 )
    goto LABEL_25;
  IsNull = Apx::ApfVerify::IsNull(a2, L"Attributes", v11);
  if ( IsNull < 0 )
    goto LABEL_25;
  IsNull = Apx::ApfVerify::IsNotNull(a3, L"Config", v12);
  if ( IsNull < 0 )
    goto LABEL_25;
  IsNull = Apx::ApfVerify::IsNotNull(a4, L"DataFormatList", v13);
  if ( IsNull < 0 )
    goto LABEL_25;
  *(_QWORD *)a4 = 0;
  if ( *(_DWORD *)a3 == 8 )
  {
    v16 = *((unsigned int *)a3 + 1);
    if ( (_DWORD)v16 )
    {
      IsNull = -2147024809;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)IsNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_26;
      WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_62a05fd9d1433e3077cc2cc299829a3e_Traceguids, v16, 0);
    }
    else
    {
      IsNull = Apx::ApfDataFormatList::_CreateAndInitialize(v14, &v18);
      if ( IsNull < 0 )
      {
        if ( v18 )
          imp_ApxObjectDelete(0, (Apx::ApfVerify *)~(unsigned __int64)v18);
      }
      else
      {
        IsNull = 0;
        *(_QWORD *)a4 = ~(unsigned __int64)v18;
      }
    }
    goto LABEL_25;
  }
  IsNull = -2147024809;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)IsNull;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DDd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_62a05fd9d1433e3077cc2cc299829a3e_Traceguids,
      8,
      *(_DWORD *)a3);
LABEL_25:
    v15 = WPP_GLOBAL_Control;
  }
LABEL_26:
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
    WPP_SF_(v15[2], 13, WPP_62a05fd9d1433e3077cc2cc299829a3e_Traceguids);
  return (unsigned int)IsNull;
}

```

## disassembly

```asm
0x18001f1d0  push    rbx
0x18001f1d2  push    rbp
0x18001f1d3  push    rsi
0x18001f1d4  push    rdi
0x18001f1d5  push    r12
0x18001f1d7  push    r14
0x18001f1d9  sub     rsp, 48h
0x18001f1dd  mov     rsi, r9
0x18001f1e0  mov     rdi, r8
0x18001f1e3  mov     r14, rdx
0x18001f1e6  mov     rbp, rcx
0x18001f1e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1f0  lea     r12, WPP_GLOBAL_Control
0x18001f1f7  cmp     rcx, r12
0x18001f1fa  jz      short loc_18001F21D
0x18001f1fc  test    byte ptr [rcx+1Ch], 1
0x18001f200  jz      short loc_18001F21D
0x18001f202  cmp     byte ptr [rcx+19h], 5
0x18001f206  jb      short loc_18001F21D
0x18001f208  mov     rcx, [rcx+10h]
0x18001f20c  lea     r8, WPP_62a05fd9d1433e3077cc2cc299829a3e_Traceguids
0x18001f213  mov     edx, 0Ah
0x18001f218  call    WPP_SF_
0x18001f21d  lea     rdx, aGlobals; "Globals"
0x18001f224  mov     [rsp+78h+var_48], 0
0x18001f22d  mov     rcx, rbp; this
0x18001f230  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18001f235  mov     ebx, eax
0x18001f237  test    eax, eax
0x18001f239  js      loc_18001F37E
0x18001f23f  call    ?IsApxInitialized@ApfVerify@Apx@@YAJXZ; Apx::ApfVerify::IsApxInitialized(void)
0x18001f244  mov     ebx, eax
0x18001f246  test    eax, eax
0x18001f248  js      loc_18001F37E
0x18001f24e  mov     rcx, rbp; this
0x18001f251  call    ?ValidateClientBindings@ApfVerify@Apx@@YAJPEAUAPX_CLIENT_GLOBALS__@@@Z; Apx::ApfVerify::ValidateClientBindings(APX_CLIENT_GLOBALS__ *)
0x18001f256  mov     ebx, eax
0x18001f258  test    eax, eax
0x18001f25a  js      loc_18001F37E
0x18001f260  lea     rdx, aAttributes; "Attributes"
0x18001f267  mov     rcx, r14; this
0x18001f26a  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18001f26f  mov     ebx, eax
0x18001f271  test    eax, eax
0x18001f273  js      loc_18001F37E
0x18001f279  lea     rdx, aConfig_0; "Config"
0x18001f280  mov     rcx, rdi; this
0x18001f283  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001f288  mov     ebx, eax
0x18001f28a  test    eax, eax
0x18001f28c  js      loc_18001F37E
0x18001f292  lea     rdx, aDataformatlist; "DataFormatList"
0x18001f299  mov     rcx, rsi; this
0x18001f29c  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001f2a1  mov     ebx, eax
0x18001f2a3  test    eax, eax
0x18001f2a5  js      loc_18001F37E
0x18001f2ab  mov     qword ptr [rsi], 0
0x18001f2b2  mov     r9d, 8
0x18001f2b8  mov     eax, [rdi]
0x18001f2ba  cmp     eax, r9d
0x18001f2bd  jz      short loc_18001F302
0x18001f2bf  mov     ebx, 80070057h
0x18001f2c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2cb  cmp     rcx, r12
0x18001f2ce  jz      loc_18001F3AB
0x18001f2d4  test    byte ptr [rcx+1Ch], 40h
0x18001f2d8  jz      loc_18001F385
0x18001f2de  cmp     byte ptr [rcx+19h], 2
0x18001f2e2  jb      loc_18001F385
0x18001f2e8  mov     rcx, [rcx+10h]
0x18001f2ec  lea     edx, [r9+3]
0x18001f2f0  lea     r8, WPP_62a05fd9d1433e3077cc2cc299829a3e_Traceguids
0x18001f2f7  mov     [rsp+78h+var_58], eax
0x18001f2fb  call    WPP_SF_DDd
0x18001f300  jmp     short loc_18001F37E
0x18001f302  mov     r9d, [rdi+4]
0x18001f306  test    r9d, r9d
0x18001f309  jz      short loc_18001F34B
0x18001f30b  mov     ebx, 80070057h
0x18001f310  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f317  cmp     rcx, r12
0x18001f31a  jz      loc_18001F3AB
0x18001f320  test    byte ptr [rcx+1Ch], 40h
0x18001f324  jz      short loc_18001F385
0x18001f326  cmp     byte ptr [rcx+19h], 2
0x18001f32a  jb      short loc_18001F385
0x18001f32c  mov     rcx, [rcx+10h]
0x18001f330  lea     r8, WPP_62a05fd9d1433e3077cc2cc299829a3e_Traceguids
0x18001f337  mov     edx, 0Ch
0x18001f33c  mov     [rsp+78h+var_58], 0
0x18001f344  call    WPP_SF_DDd
0x18001f349  jmp     short loc_18001F37E
0x18001f34b  lea     rdx, [rsp+78h+var_48]; struct Apx::ApfDataFormatList **
0x18001f350  call    ?_CreateAndInitialize@ApfDataFormatList@Apx@@SAJPEAU_APX_DATAFORMAT_LIST_CONFIG@@PEAPEAV12@@Z; Apx::ApfDataFormatList::_CreateAndInitialize(_APX_DATAFORMAT_LIST_CONFIG *,Apx::ApfDataFormatList * *)
0x18001f355  mov     ebx, eax
0x18001f357  test    eax, eax
0x18001f359  js      short loc_18001F36A
0x18001f35b  mov     rax, [rsp+78h+var_48]
0x18001f360  xor     ebx, ebx
0x18001f362  not     rax
0x18001f365  mov     [rsi], rax
0x18001f368  jmp     short loc_18001F37E
0x18001f36a  mov     rdx, [rsp+78h+var_48]
0x18001f36f  test    rdx, rdx
0x18001f372  jz      short loc_18001F37E
0x18001f374  not     rdx; Apx::ApfVerify *
0x18001f377  xor     ecx, ecx; this
0x18001f379  call    imp_ApxObjectDelete
0x18001f37e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f385  cmp     rcx, r12
0x18001f388  jz      short loc_18001F3AB
0x18001f38a  test    byte ptr [rcx+1Ch], 1
0x18001f38e  jz      short loc_18001F3AB
0x18001f390  cmp     byte ptr [rcx+19h], 5
0x18001f394  jb      short loc_18001F3AB
0x18001f396  mov     rcx, [rcx+10h]
0x18001f39a  lea     r8, WPP_62a05fd9d1433e3077cc2cc299829a3e_Traceguids
0x18001f3a1  mov     edx, 0Dh
0x18001f3a6  call    WPP_SF_
0x18001f3ab  mov     eax, ebx
0x18001f3ad  add     rsp, 48h
0x18001f3b1  pop     r14
0x18001f3b3  pop     r12
0x18001f3b5  pop     rdi
0x18001f3b6  pop     rsi
0x18001f3b7  pop     rbp
0x18001f3b8  pop     rbx
0x18001f3b9  retn
```
