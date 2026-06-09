# HearingAidProfileClientImpl::Initialize(void)

- ea: `0x18005653c`
- end: `0x18005670b`
- name: `?Initialize@HearingAidProfileClientImpl@@AEAAXXZ`
- size: `463`
- prototype: `void __fastcall(HearingAidProfileClientImpl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003b8f8`

## callees

- `0x180012554`
- `0x1800288ac`
- `0x18005653c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005663e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005663e`

## string_xrefs

- `0x180056631`: `Microsoft.Bluetooth.Audio.dll`

## pseudocode

```c
void __fastcall HearingAidProfileClientImpl::Initialize(HearingAidProfileClientImpl *this)
{
  PVOID *v2; // rcx
  char v3; // dl
  _UNKNOWN **v4; // rax
  char v5; // r8
  char v6; // dl
  bool v7; // r8
  HMODULE Library; // rax
  char v9; // dl
  char v10; // r8
  __int16 v11; // [rsp+30h] [rbp-58h]
  char v12; // [rsp+40h] [rbp-48h]

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (v3 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    v3 = 0;
  }
  v4 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (v5 = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    v5 = 0;
  }
  if ( v3 || v5 )
  {
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      v5,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      1,
      11,
      &WPP_6fa7f4f46ed53a8c08fe2b7537b301f3_Traceguids,
      (char)this);
    v2 = (PVOID *)WPP_GLOBAL_Control;
    v4 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  if ( *((_QWORD *)this + 1) )
  {
    if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 1) == 0 || (v6 = 1, *((_BYTE *)v2 + 25) < 2u) )
      v6 = 0;
    v7 = v4 != &WPP_RECORDER_INITIALIZED;
    if ( v6 || v4 != &WPP_RECORDER_INITIALIZED )
    {
      v12 = (char)this;
      v11 = 12;
LABEL_19:
      WPP_RECORDER_AND_TRACE_SF_q(
        (int)v2[2],
        v6,
        v7,
        (int)v2[5],
        2,
        1,
        v11,
        &WPP_6fa7f4f46ed53a8c08fe2b7537b301f3_Traceguids,
        v12);
    }
  }
  else
  {
    Library = LoadLibraryExW(L"Microsoft.Bluetooth.Audio.dll", 0, 0x800u);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      (char *)this + 8,
      Library);
    if ( *((_QWORD *)this + 1) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || (v9 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
      {
        v9 = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (v10 = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
      {
        v10 = 0;
      }
      if ( v9 || v10 )
        WPP_RECORDER_AND_TRACE_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v9,
          v10,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          5,
          1,
          14,
          &WPP_6fa7f4f46ed53a8c08fe2b7537b301f3_Traceguids,
          (char)this);
    }
    else
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || (v6 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
      {
        v6 = 0;
      }
      v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v12 = (char)this;
        v11 = 13;
        goto LABEL_19;
      }
    }
  }
}

```

## disassembly

```asm
0x18005653c  push    rbx
0x18005653e  push    rbp
0x18005653f  push    rsi
0x180056540  push    rdi
0x180056541  push    r12
0x180056543  push    r14
0x180056545  push    r15
0x180056547  sub     rsp, 50h
0x18005654b  mov     rdi, rcx
0x18005654e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056555  lea     r14, WPP_GLOBAL_Control
0x18005655c  xor     esi, esi
0x18005655e  lea     ebp, [rsi+1]
0x180056561  cmp     rcx, r14
0x180056564  jz      short loc_180056575
0x180056566  test    [rcx+1Ch], bpl
0x18005656a  jz      short loc_180056575
0x18005656c  cmp     byte ptr [rcx+19h], 5
0x180056570  mov     dl, bpl
0x180056573  jnb     short loc_180056578
0x180056575  mov     dl, sil; int
0x180056578  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18005657f  lea     r15, WPP_RECORDER_INITIALIZED
0x180056586  cmp     rax, r15
0x180056589  jz      short loc_180056594
0x18005658b  mov     r8b, bpl
0x18005658e  cmp     [rcx+30h], si
0x180056592  jnz     short loc_180056597
0x180056594  mov     r8b, sil; int
0x180056597  lea     r12, WPP_6fa7f4f46ed53a8c08fe2b7537b301f3_Traceguids
0x18005659e  test    dl, dl
0x1800565a0  jnz     short loc_1800565A7
0x1800565a2  test    r8b, r8b
0x1800565a5  jz      short loc_1800565DC
0x1800565a7  mov     r9, [rcx+28h]; int
0x1800565ab  mov     rcx, [rcx+10h]; int
0x1800565af  mov     qword ptr [rsp+88h+var_48], rdi; char
0x1800565b4  mov     [rsp+88h+MessageGuid], r12; MessageGuid
0x1800565b9  mov     [rsp+88h+var_58], 0Bh; __int16
0x1800565c0  mov     [rsp+88h+var_60], ebp; int
0x1800565c4  mov     [rsp+88h+var_68], 5; char
0x1800565c9  call    WPP_RECORDER_AND_TRACE_SF_q
0x1800565ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800565d5  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x1800565dc  lea     rbx, [rdi+8]
0x1800565e0  cmp     [rbx], rsi
0x1800565e3  jz      short loc_18005662F
0x1800565e5  cmp     rcx, r14
0x1800565e8  jz      short loc_1800565F9
0x1800565ea  test    [rcx+1Ch], bpl
0x1800565ee  jz      short loc_1800565F9
0x1800565f0  cmp     byte ptr [rcx+19h], 2
0x1800565f4  mov     dl, bpl
0x1800565f7  jnb     short loc_1800565FC
0x1800565f9  mov     dl, sil
0x1800565fc  cmp     rax, r15
0x1800565ff  setnz   r8b
0x180056603  test    dl, dl
0x180056605  jnz     short loc_180056610
0x180056607  test    r8b, r8b
0x18005660a  jz      loc_1800566FC
0x180056610  mov     qword ptr [rsp+88h+var_48], rdi
0x180056615  mov     [rsp+88h+MessageGuid], r12
0x18005661a  mov     [rsp+88h+var_58], 0Ch
0x180056621  mov     [rsp+88h+var_60], ebp
0x180056625  mov     [rsp+88h+var_68], 2
0x18005662a  jmp     loc_1800566EF
0x18005662f  xor     edx, edx; hFile
0x180056631  lea     rcx, LibFileName; "Microsoft.Bluetooth.Audio.dll"
0x180056638  mov     r8d, 800h; dwFlags
0x18005663e  call    cs:__imp_LoadLibraryExW
0x180056644  mov     rdx, rax
0x180056647  mov     rcx, rbx
0x18005664a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18005664f  cmp     [rbx], rsi
0x180056652  jnz     short loc_180056699
0x180056654  mov     rcx, cs:WPP_GLOBAL_Control
0x18005665b  cmp     rcx, r14
0x18005665e  jz      short loc_18005666F
0x180056660  test    [rcx+1Ch], bpl
0x180056664  jz      short loc_18005666F
0x180056666  cmp     byte ptr [rcx+19h], 2
0x18005666a  mov     dl, bpl
0x18005666d  jnb     short loc_180056672
0x18005666f  mov     dl, sil
0x180056672  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180056679  setnz   r8b
0x18005667d  test    dl, dl
0x18005667f  jnz     short loc_180056686
0x180056681  test    r8b, r8b
0x180056684  jz      short loc_1800566FC
0x180056686  mov     qword ptr [rsp+88h+var_48], rdi
0x18005668b  mov     [rsp+88h+MessageGuid], r12
0x180056690  mov     [rsp+88h+var_58], 0Dh
0x180056697  jmp     short loc_180056621
0x180056699  mov     rcx, cs:WPP_GLOBAL_Control
0x1800566a0  cmp     rcx, r14
0x1800566a3  jz      short loc_1800566B4
0x1800566a5  test    [rcx+1Ch], bpl
0x1800566a9  jz      short loc_1800566B4
0x1800566ab  cmp     byte ptr [rcx+19h], 5
0x1800566af  mov     dl, bpl
0x1800566b2  jnb     short loc_1800566B7
0x1800566b4  mov     dl, sil; int
0x1800566b7  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800566be  jz      short loc_1800566C9
0x1800566c0  mov     r8b, bpl
0x1800566c3  cmp     [rcx+30h], si
0x1800566c7  jnz     short loc_1800566CC
0x1800566c9  mov     r8b, sil; int
0x1800566cc  test    dl, dl
0x1800566ce  jnz     short loc_1800566D5
0x1800566d0  test    r8b, r8b
0x1800566d3  jz      short loc_1800566FC
0x1800566d5  mov     qword ptr [rsp+88h+var_48], rdi; char
0x1800566da  mov     [rsp+88h+MessageGuid], r12; MessageGuid
0x1800566df  mov     [rsp+88h+var_58], 0Eh; __int16
0x1800566e6  mov     [rsp+88h+var_60], ebp; int
0x1800566ea  mov     [rsp+88h+var_68], 5; char
0x1800566ef  mov     r9, [rcx+28h]; int
0x1800566f3  mov     rcx, [rcx+10h]; int
0x1800566f7  call    WPP_RECORDER_AND_TRACE_SF_q
0x1800566fc  add     rsp, 50h
0x180056700  pop     r15
0x180056702  pop     r14
0x180056704  pop     r12
0x180056706  pop     rdi
0x180056707  pop     rsi
0x180056708  pop     rbp
0x180056709  pop     rbx
0x18005670a  retn
```
