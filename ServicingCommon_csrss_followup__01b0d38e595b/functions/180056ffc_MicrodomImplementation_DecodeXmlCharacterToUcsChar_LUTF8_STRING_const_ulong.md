# MicrodomImplementation::DecodeXmlCharacterToUcsChar(_LUTF8_STRING const &,ulong *)

- ea: `0x180056ffc`
- end: `0x1800571f2`
- name: `?DecodeXmlCharacterToUcsChar@MicrodomImplementation@@YAJAEBU_LUTF8_STRING@@PEAK@Z`
- size: `502`
- prototype: `__int64 __fastcall(MicrodomImplementation *__hidden this, const struct _LUTF8_STRING *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005c70`

## callees

- `0x180003de0`
- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x1800562d8`
- `0x180056ffc`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x1800571e5`
- `ntdll!RtlRaiseStatus` at `0x1800571e5`

## string_xrefs

- `0x180057044`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800570ac`: `onecore\base\xml\udom_microdom.cpp`
- `0x180057169`: `onecore\base\xml\udom_microdom.cpp`
- `0x180057198`: `onecore\base\xml\udom_microdom.cpp`
- `0x180057057`: `MicrodomImplementation::DecodeXmlCharacterToUcsChar`
- `0x1800570bf`: `MicrodomImplementation::DecodeXmlCharacterToUcsChar`
- `0x18005717c`: `MicrodomImplementation::DecodeXmlCharacterToUcsChar`
- `0x1800571af`: `MicrodomImplementation::DecodeXmlCharacterToUcsChar`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::DecodeXmlCharacterToUcsChar(
        MicrodomImplementation *this,
        const struct _LUTF8_STRING *a2,
        unsigned int *a3)
{
  _BYTE *v3; // rax
  unsigned int v4; // ebx
  unsigned __int64 v6; // rcx
  const char *v7; // rax
  __int64 result; // rax
  _BYTE *v9; // r10
  unsigned int v10; // edi
  _BYTE *v11; // rsi
  __int64 v12; // rax
  int v13; // ecx
  __int64 v14; // r10
  unsigned int v15; // r11d
  int v16; // r11d
  unsigned int v17; // [rsp+20h] [rbp-40h] BYREF
  const char *v18; // [rsp+28h] [rbp-38h] BYREF
  const char *v19; // [rsp+30h] [rbp-30h]
  __int64 v20; // [rsp+38h] [rbp-28h]
  const char *v21; // [rsp+40h] [rbp-20h]
  int v22; // [rsp+48h] [rbp-18h] BYREF

  v3 = (_BYTE *)*((_QWORD *)this + 2);
  v4 = 0;
  v22 = 0;
  v17 = 0;
  if ( *v3 != 35 )
    goto LABEL_28;
  v6 = *(_QWORD *)this;
  if ( v6 < 2 )
  {
    v20 = 192;
    v18 = "onecore\\base\\xml\\udom_microdom.cpp";
    v19 = "MicrodomImplementation::DecodeXmlCharacterToUcsChar";
    v7 = "Source.Length >= 2";
    goto LABEL_4;
  }
  v9 = v3 + 1;
  if ( v3[1] == 120 )
  {
    if ( v6 < 3 )
    {
      v20 = 198;
      v18 = "onecore\\base\\xml\\udom_microdom.cpp";
      v19 = "MicrodomImplementation::DecodeXmlCharacterToUcsChar";
      v7 = "Source.Length >= 3";
      goto LABEL_4;
    }
    v9 = v3 + 2;
    v10 = 16;
  }
  else
  {
    v10 = 10;
  }
  v11 = &v3[v6];
  while ( 1 )
  {
    if ( v9 == v11 )
    {
      *(_DWORD *)a2 = v4;
      return 0;
    }
    v12 = RtlDecodeUtf8(&v18, v9, v11);
    v13 = *(_DWORD *)v12;
    v14 = *(_QWORD *)(v12 + 8);
    if ( *(_DWORD *)v12 == -1 )
    {
      if ( (int)v14 < 0 )
      {
        v20 = 208;
        v18 = "onecore\\base\\xml\\udom_microdom.cpp";
        v19 = "MicrodomImplementation::DecodeXmlCharacterToUcsChar";
        v21 = "__rv.UcsCharacter != (0xffffffff)";
        return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                 &v22,
                 &v18,
                 (unsigned int)v14);
      }
LABEL_28:
      RtlRaiseStatus(-1073741595);
    }
    v15 = v13 - 48;
    if ( (unsigned int)(v13 - 48) > 9 )
    {
      if ( (unsigned int)(v13 - 97) > 5 )
      {
        v15 = 0;
        if ( (unsigned int)(v13 - 65) <= 5 )
          v15 = v13 - 55;
      }
      else
      {
        v15 = v13 - 87;
      }
    }
    if ( v15 >= v10 )
      break;
    result = BUCL::Rtl::Multiply<unsigned long>(v4, v10, &v17);
    if ( (int)result < 0 )
      return result;
    v4 = v17 + v16;
    if ( v17 + v16 < v17 )
      return 3221225621LL;
    v17 += v16;
  }
  v20 = 224;
  v18 = "onecore\\base\\xml\\udom_microdom.cpp";
  v19 = "MicrodomImplementation::DecodeXmlCharacterToUcsChar";
  v7 = "ulValue < MultFactor";
LABEL_4:
  v21 = v7;
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
           &v22,
           &v18);
}

```

## disassembly

```asm
0x180056ffc  mov     [rsp-18h+arg_10], rbx
0x180057001  mov     [rsp-18h+arg_18], rsi
0x180057006  push    rbp
0x180057007  push    rdi
0x180057008  push    r14
0x18005700a  mov     rbp, rsp
0x18005700d  sub     rsp, 60h
0x180057011  mov     rax, cs:__security_cookie
0x180057018  xor     rax, rsp
0x18005701b  mov     [rbp+var_10], rax
0x18005701f  mov     rax, [rcx+10h]
0x180057023  xor     ebx, ebx
0x180057025  mov     r14, rdx
0x180057028  mov     [rbp+var_18], 0
0x18005702f  mov     [rbp+var_40], ebx
0x180057032  cmp     byte ptr [rax], 23h ; '#'
0x180057035  jnz     loc_1800571E0
0x18005703b  mov     rcx, [rcx]
0x18005703e  cmp     rcx, 2
0x180057042  jnb     short loc_18005709C
0x180057044  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005704b  mov     [rbp+var_28], 0C0h
0x180057053  mov     [rbp+var_38], rax
0x180057057  lea     rax, aMicrodomimplem_11; "MicrodomImplementation::DecodeXmlCharac"...
0x18005705e  mov     [rbp+var_30], rax
0x180057062  lea     rax, aSourceLength2; "Source.Length >= 2"
0x180057069  lea     rdx, [rbp+var_38]
0x18005706d  mov     [rbp+var_20], rax
0x180057071  lea     rcx, [rbp+var_18]
0x180057075  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005707a  mov     rcx, [rbp+var_10]
0x18005707e  xor     rcx, rsp; StackCookie
0x180057081  call    __security_check_cookie
0x180057086  lea     r11, [rsp+60h+var_s0]
0x18005708b  mov     rbx, [r11+30h]
0x18005708f  mov     rsi, [r11+38h]
0x180057093  mov     rsp, r11
0x180057096  pop     r14
0x180057098  pop     rdi
0x180057099  pop     rbp
0x18005709a  retn
0x18005709c  lea     r10, [rax+1]
0x1800570a0  cmp     byte ptr [r10], 78h ; 'x'
0x1800570a4  jnz     short loc_1800570DE
0x1800570a6  cmp     rcx, 3
0x1800570aa  jnb     short loc_1800570D3
0x1800570ac  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800570b3  mov     [rbp+var_28], 0C6h
0x1800570bb  mov     [rbp+var_38], rax
0x1800570bf  lea     rax, aMicrodomimplem_11; "MicrodomImplementation::DecodeXmlCharac"...
0x1800570c6  mov     [rbp+var_30], rax
0x1800570ca  lea     rax, aSourceLength3; "Source.Length >= 3"
0x1800570d1  jmp     short loc_180057069
0x1800570d3  lea     r10, [rax+2]
0x1800570d7  mov     edi, 10h
0x1800570dc  jmp     short loc_1800570E3
0x1800570de  mov     edi, 0Ah
0x1800570e3  lea     rsi, [rcx+rax]
0x1800570e7  cmp     r10, rsi
0x1800570ea  jz      loc_1800571D6
0x1800570f0  mov     r8, rsi
0x1800570f3  lea     rcx, [rbp+var_38]
0x1800570f7  mov     rdx, r10
0x1800570fa  call    RtlDecodeUtf8
0x1800570ff  mov     ecx, [rax]
0x180057101  mov     r10, [rax+8]
0x180057105  cmp     ecx, 0FFFFFFFFh
0x180057108  jz      loc_180057193
0x18005710e  lea     r11d, [rcx-30h]
0x180057112  cmp     r11d, 9
0x180057116  jbe     short loc_180057135
0x180057118  lea     eax, [rcx-61h]
0x18005711b  cmp     eax, 5
0x18005711e  ja      short loc_180057126
0x180057120  lea     r11d, [rcx-57h]
0x180057124  jmp     short loc_180057135
0x180057126  xor     r11d, r11d
0x180057129  lea     eax, [rcx-41h]
0x18005712c  cmp     eax, 5
0x18005712f  ja      short loc_180057135
0x180057131  lea     r11d, [rcx-37h]
0x180057135  cmp     r11d, edi
0x180057138  jnb     short loc_180057169
0x18005713a  lea     r8, [rbp+var_40]
0x18005713e  mov     edx, edi
0x180057140  mov     ecx, ebx
0x180057142  call    ??$Multiply@K@Rtl@BUCL@@YAJKKAEAK@Z; BUCL::Rtl::Multiply<ulong>(ulong,ulong,ulong &)
0x180057147  test    eax, eax
0x180057149  js      loc_18005707A
0x18005714f  mov     eax, [rbp+var_40]
0x180057152  lea     ebx, [rax+r11]
0x180057156  cmp     ebx, eax
0x180057158  jb      short loc_18005715F
0x18005715a  mov     [rbp+var_40], ebx
0x18005715d  jmp     short loc_1800570E7
0x18005715f  mov     eax, 0C0000095h
0x180057164  jmp     loc_18005707A
0x180057169  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180057170  mov     [rbp+var_28], 0E0h
0x180057178  mov     [rbp+var_38], rax
0x18005717c  lea     rax, aMicrodomimplem_11; "MicrodomImplementation::DecodeXmlCharac"...
0x180057183  mov     [rbp+var_30], rax
0x180057187  lea     rax, aUlvalueMultfac; "ulValue < MultFactor"
0x18005718e  jmp     loc_180057069
0x180057193  test    r10d, r10d
0x180057196  jns     short loc_1800571E0
0x180057198  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005719f  mov     [rbp+var_28], 0D0h
0x1800571a7  mov     [rbp+var_38], rax
0x1800571ab  lea     rdx, [rbp+var_38]
0x1800571af  lea     rax, aMicrodomimplem_11; "MicrodomImplementation::DecodeXmlCharac"...
0x1800571b6  mov     r8d, r10d
0x1800571b9  mov     [rbp+var_30], rax
0x1800571bd  lea     rcx, [rbp+var_18]
0x1800571c1  lea     rax, aRvUcscharacter_0; "__rv.UcsCharacter != (0xffffffff)"
0x1800571c8  mov     [rbp+var_20], rax
0x1800571cc  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800571d1  jmp     loc_18005707A
0x1800571d6  mov     [r14], ebx
0x1800571d9  xor     eax, eax
0x1800571db  jmp     loc_18005707A
0x1800571e0  mov     ecx, 0C00000E5h; Status
0x1800571e5  call    cs:__imp_RtlRaiseStatus
0x1800571ec  nop     dword ptr [rax+rax+00h]
0x1800571f1  int     3; Trap to Debugger
```
