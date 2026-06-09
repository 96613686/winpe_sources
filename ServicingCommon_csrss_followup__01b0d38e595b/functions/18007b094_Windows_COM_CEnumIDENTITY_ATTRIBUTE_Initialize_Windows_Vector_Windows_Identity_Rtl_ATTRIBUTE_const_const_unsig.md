# Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize(Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE const> const *,unsigned __int64)

- ea: `0x18007b094`
- end: `0x18007b2d3`
- name: `?Initialize@CEnumIDENTITY_ATTRIBUTE@COM@Windows@@IEAAJPEBU?$Vector@$$CBU_ATTRIBUTE@Rtl@Identity@Windows@@@3@_K@Z`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007acec`

## callees

- `0x1800211f0`
- `0x18002175c`
- `0x180026e0c`
- `0x18002d2b0`
- `0x180066860`
- `0x18006b3e0`
- `0x18007aa0c`
- `0x18007b094`
- `0x180097e20`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18007b298`
- `ntdll!RtlRaiseStatus` at `0x18007b298`

## string_xrefs

- `0x18007b0d6`: `onecore\base\wcp\identity\com\enum_idattribute.cpp`
- `0x18007b220`: `onecore\base\wcp\identity\com\enum_idattribute.cpp`
- `0x18007b263`: `onecore\base\wcp\identity\com\enum_idattribute.cpp`
- `0x18007b0e9`: `Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize`
- `0x18007b237`: `Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize`
- `0x18007b276`: `Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize`

## pseudocode

```c
__int64 __fastcall Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize(_QWORD *a1, _QWORD *a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // r15
  const char *v6; // rax
  unsigned __int64 v8; // r14
  __int64 v9; // r12
  bool v10; // cf
  unsigned __int64 v11; // r12
  unsigned __int64 *v12; // rax
  unsigned __int64 *v13; // r13
  __int64 v14; // rcx
  unsigned __int64 i; // r14
  __int64 v16; // rcx
  __int64 v17; // r12
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  const char *v21; // [rsp+20h] [rbp-30h] BYREF
  const char *v22; // [rsp+28h] [rbp-28h]
  __int64 v23; // [rsp+30h] [rbp-20h]
  const char *v24; // [rsp+38h] [rbp-18h]
  int v25; // [rsp+40h] [rbp-10h] BYREF

  v3 = a3;
  v25 = 0;
  if ( !a2 )
  {
    if ( a3 )
    {
      v23 = 44;
      v21 = "onecore\\base\\wcp\\identity\\com\\enum_idattribute.cpp";
      v22 = "Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize";
      v6 = "(IdentityAttributeList != 0) || (CurrentPosition == 0)";
      goto LABEL_4;
    }
    if ( a1[4] )
      RtlRaiseStatus(-1073741595);
    v3 = 0;
    goto LABEL_33;
  }
  if ( a2[1] < a3 )
  {
    v23 = 43;
    v21 = "onecore\\base\\wcp\\identity\\com\\enum_idattribute.cpp";
    v22 = "Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize";
    v6 = "(IdentityAttributeList == 0) || (IdentityAttributeList->Length >= CurrentPosition)";
LABEL_4:
    v24 = v6;
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(
             &v25,
             &v21,
             a3);
  }
  if ( a1[3] )
    goto LABEL_27;
  v8 = a2[1];
  if ( v8 )
  {
    v9 = 72 * v8;
    if ( !is_mul_ok(v8, 0x48u) )
      v9 = -1;
    v10 = __CFADD__(v9, 8);
    v11 = v9 + 8;
    if ( v10 )
      v11 = -1;
    v12 = (unsigned __int64 *)operator new[](v11);
    v13 = v12;
    if ( v12 )
    {
      memset(v12, 0, v11);
      *v13 = v8;
      __builtin_array_init_helper<Windows::COM::CEnumIDENTITY_ATTRIBUTE::AutoAttribute>(v13 + 1, v8);
      if ( v14 )
      {
        a1[3] = v14;
        a1[4] = v8;
        goto LABEL_16;
      }
LABEL_27:
      v23 = 48;
      v21 = "onecore\\base\\wcp\\identity\\com\\enum_idattribute.cpp";
      v22 = "Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize";
      v24 = "m_IdentityAttributeList.Allocate(IdentityAttributeList->Length)";
      return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
               &v25,
               &v21,
               2147942414LL);
    }
    v14 = 0;
  }
  else
  {
    v14 = 8;
  }
LABEL_16:
  if ( !v14 )
    goto LABEL_27;
  for ( i = 0; i < a2[1]; ++i )
  {
    v16 = *(_QWORD *)(*a2 + 24 * i);
    v17 = 72 * i;
    if ( !v16 || (v18 = RtlDuplicateLUnicodeString(v16, v17 + a1[3]), v18 >= 0) )
    {
      v19 = *(_QWORD *)(*a2 + 24 * i + 8);
      if ( !v19 || (v18 = RtlDuplicateLUnicodeString(v19, v17 + a1[3] + 24LL), v18 >= 0) )
      {
        v20 = *(_QWORD *)(*a2 + 24 * i + 16);
        if ( !v20 )
          continue;
        v18 = RtlDuplicateLUnicodeString(v20, v17 + a1[3] + 48LL);
        if ( v18 >= 0 )
          continue;
      }
    }
    return ConvertNtStatusToHResult((unsigned int)v18);
  }
LABEL_33:
  a1[5] = v3;
  return 0;
}

```

## disassembly

```asm
0x18007b094  mov     [rsp-38h+arg_10], rbx
0x18007b099  push    rbp
0x18007b09a  push    rsi
0x18007b09b  push    rdi
0x18007b09c  push    r12
0x18007b09e  push    r13
0x18007b0a0  push    r14
0x18007b0a2  push    r15
0x18007b0a4  mov     rbp, rsp
0x18007b0a7  sub     rsp, 50h
0x18007b0ab  mov     rax, cs:__security_cookie
0x18007b0b2  xor     rax, rsp
0x18007b0b5  mov     [rbp+var_8], rax
0x18007b0b9  xor     ebx, ebx
0x18007b0bb  mov     r15, r8
0x18007b0be  mov     [rbp+var_10], ebx
0x18007b0c1  mov     rsi, rdx
0x18007b0c4  mov     rdi, rcx
0x18007b0c7  test    rdx, rdx
0x18007b0ca  jz      loc_18007B25E
0x18007b0d0  cmp     [rdx+8], r8
0x18007b0d4  jnb     short loc_18007B111
0x18007b0d6  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\identity\\com\\enum"...
0x18007b0dd  mov     [rbp+var_20], 2Bh ; '+'
0x18007b0e5  mov     [rbp+var_30], rax
0x18007b0e9  lea     rax, aWindowsComCenu_2; "Windows::COM::CEnumIDENTITY_ATTRIBUTE::"...
0x18007b0f0  mov     [rbp+var_28], rax
0x18007b0f4  lea     rax, aIdentityattrib_1; "(IdentityAttributeList == 0) || (Identi"...
0x18007b0fb  lea     rdx, [rbp+var_30]
0x18007b0ff  mov     [rbp+var_18], rax
0x18007b103  lea     rcx, [rbp+var_10]
0x18007b107  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007b10c  jmp     loc_18007B2AE
0x18007b111  cmp     [rcx+18h], rbx
0x18007b115  jnz     loc_18007B220
0x18007b11b  mov     r14, [rdx+8]
0x18007b11f  test    r14, r14
0x18007b122  jz      short loc_18007B186
0x18007b124  mov     eax, 48h ; 'H'
0x18007b129  mul     r14
0x18007b12c  mov     r12, rax
0x18007b12f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18007b136  cmovb   r12, rax
0x18007b13a  add     r12, 8
0x18007b13e  cmovb   r12, rax
0x18007b142  mov     rcx, r12; unsigned __int64
0x18007b145  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007b14a  mov     r13, rax
0x18007b14d  test    rax, rax
0x18007b150  jz      short loc_18007B182
0x18007b152  mov     r8, r12; Size
0x18007b155  xor     edx, edx; Val
0x18007b157  mov     rcx, rax; void *
0x18007b15a  call    memset
0x18007b15f  lea     rcx, [r13+8]
0x18007b163  mov     [r13+0], r14
0x18007b167  mov     rdx, r14
0x18007b16a  call    ??$__builtin_array_init_helper@UAutoAttribute@CEnumIDENTITY_ATTRIBUTE@COM@Windows@@@@YAXPEAUAutoAttribute@CEnumIDENTITY_ATTRIBUTE@COM@Windows@@_K@Z; __builtin_array_init_helper<Windows::COM::CEnumIDENTITY_ATTRIBUTE::AutoAttribute>(Windows::COM::CEnumIDENTITY_ATTRIBUTE::AutoAttribute *,unsigned __int64)
0x18007b16f  test    rcx, rcx
0x18007b172  jz      loc_18007B220
0x18007b178  mov     [rdi+18h], rcx
0x18007b17c  mov     [rdi+20h], r14
0x18007b180  jmp     short loc_18007B18B
0x18007b182  xor     ecx, ecx
0x18007b184  jmp     short loc_18007B18B
0x18007b186  mov     ecx, 8
0x18007b18b  test    rcx, rcx
0x18007b18e  jz      loc_18007B220
0x18007b194  xor     r14d, r14d
0x18007b197  cmp     r14, [rsi+8]
0x18007b19b  jnb     loc_18007B2A8
0x18007b1a1  mov     rax, [rsi]
0x18007b1a4  lea     r13, [r14+r14*2]
0x18007b1a8  mov     rcx, [rax+r13*8]
0x18007b1ac  lea     rax, [r14+r14*8]
0x18007b1b0  lea     r12, ds:0[rax*8]
0x18007b1b8  test    rcx, rcx
0x18007b1bb  jz      short loc_18007B1CD
0x18007b1bd  mov     rdx, [rdi+18h]
0x18007b1c1  add     rdx, r12
0x18007b1c4  call    RtlDuplicateLUnicodeString
0x18007b1c9  test    eax, eax
0x18007b1cb  js      short loc_18007B214
0x18007b1cd  mov     rax, [rsi]
0x18007b1d0  mov     rcx, [rax+r13*8+8]
0x18007b1d5  test    rcx, rcx
0x18007b1d8  jz      short loc_18007B1EE
0x18007b1da  mov     rdx, [rdi+18h]
0x18007b1de  add     rdx, 18h
0x18007b1e2  add     rdx, r12
0x18007b1e5  call    RtlDuplicateLUnicodeString
0x18007b1ea  test    eax, eax
0x18007b1ec  js      short loc_18007B214
0x18007b1ee  mov     rax, [rsi]
0x18007b1f1  mov     rcx, [rax+r13*8+10h]
0x18007b1f6  test    rcx, rcx
0x18007b1f9  jz      short loc_18007B20F
0x18007b1fb  mov     rdx, [rdi+18h]
0x18007b1ff  add     rdx, 30h ; '0'
0x18007b203  add     rdx, r12
0x18007b206  call    RtlDuplicateLUnicodeString
0x18007b20b  test    eax, eax
0x18007b20d  js      short loc_18007B214
0x18007b20f  inc     r14
0x18007b212  jmp     short loc_18007B197
0x18007b214  mov     ecx, eax
0x18007b216  call    ConvertNtStatusToHResult
0x18007b21b  jmp     loc_18007B2AE
0x18007b220  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\identity\\com\\enum"...
0x18007b227  mov     [rbp+var_20], 30h ; '0'
0x18007b22f  mov     [rbp+var_30], rax
0x18007b233  lea     rdx, [rbp+var_30]
0x18007b237  lea     rax, aWindowsComCenu_2; "Windows::COM::CEnumIDENTITY_ATTRIBUTE::"...
0x18007b23e  mov     r8d, 8007000Eh
0x18007b244  mov     [rbp+var_28], rax
0x18007b248  lea     rcx, [rbp+var_10]
0x18007b24c  lea     rax, aMIdentityattri; "m_IdentityAttributeList.Allocate(Identi"...
0x18007b253  mov     [rbp+var_18], rax
0x18007b257  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007b25c  jmp     short loc_18007B2AE
0x18007b25e  test    r8, r8
0x18007b261  jz      short loc_18007B28D
0x18007b263  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\identity\\com\\enum"...
0x18007b26a  mov     [rbp+var_20], 2Ch ; ','
0x18007b272  mov     [rbp+var_30], rax
0x18007b276  lea     rax, aWindowsComCenu_2; "Windows::COM::CEnumIDENTITY_ATTRIBUTE::"...
0x18007b27d  mov     [rbp+var_28], rax
0x18007b281  lea     rax, aIdentityattrib_0; "(IdentityAttributeList != 0) || (Curren"...
0x18007b288  jmp     loc_18007B0FB
0x18007b28d  cmp     [rcx+20h], rbx
0x18007b291  jz      short loc_18007B2A5
0x18007b293  mov     ecx, 0C00000E5h; Status
0x18007b298  call    cs:__imp_RtlRaiseStatus
0x18007b29f  nop     dword ptr [rax+rax+00h]
0x18007b2a4  int     3; Trap to Debugger
0x18007b2a5  xor     r15d, r15d
0x18007b2a8  mov     [rdi+28h], r15
0x18007b2ac  mov     eax, ebx
0x18007b2ae  mov     rcx, [rbp+var_8]
0x18007b2b2  xor     rcx, rsp; StackCookie
0x18007b2b5  call    __security_check_cookie
0x18007b2ba  mov     rbx, [rsp+50h+arg_10]
0x18007b2c2  add     rsp, 50h
0x18007b2c6  pop     r15
0x18007b2c8  pop     r14
0x18007b2ca  pop     r13
0x18007b2cc  pop     r12
0x18007b2ce  pop     rdi
0x18007b2cf  pop     rsi
0x18007b2d0  pop     rbp
0x18007b2d1  retn
```
