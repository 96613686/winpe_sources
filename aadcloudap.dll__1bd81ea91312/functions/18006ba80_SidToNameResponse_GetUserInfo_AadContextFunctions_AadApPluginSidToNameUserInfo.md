# SidToNameResponse::GetUserInfo(AadContextFunctions *,_AadApPluginSidToNameUserInfo *)

- ea: `0x18006ba80`
- end: `0x18006bce8`
- name: `?GetUserInfo@SidToNameResponse@@QEAAJPEAVAadContextFunctions@@PEAU_AadApPluginSidToNameUserInfo@@@Z`
- size: `616`
- prototype: `int(SidToNameResponse *__hidden this, struct AadContextFunctions *, struct _AadApPluginSidToNameUserInfo *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002597c`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x18001a8c0`
- `0x18006ba80`
- `0x180071e14`
- `0x180078780`
- `0x1800787ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bb95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bb95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bcb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bcb8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006bb8b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006bb8b`

## string_xrefs

- `0x18006baab`: `SidToNameResponse::GetUserInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SidToNameResponse::GetUserInfo(
        SidToNameResponse *this,
        struct AadContextFunctions *a2,
        unsigned __int16 **a3)
{
  int v6; // r8d
  const unsigned __int16 **v7; // r14
  const unsigned __int16 *v8; // rdx
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // rdx
  const WCHAR *v12; // rcx
  signed int LastError; // eax
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // rdx
  const unsigned __int16 *v16; // rdx
  int v17; // r8d
  const unsigned __int16 *v18; // rdx
  unsigned int v19; // ebx
  signed int v21; // [rsp+20h] [rbp-88h]
  int v22; // [rsp+30h] [rbp-78h]
  const char *v23[11]; // [rsp+50h] [rbp-58h] BYREF
  int v24; // [rsp+B8h] [rbp+10h] BYREF
  PSID Sid; // [rsp+C8h] [rbp+20h] BYREF

  v24 = 0;
  Sid = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v23,
    (int)"sidtonameresponse.cpp",
    (int)"SidToNameResponse::GetUserInfo",
    (int)&v24);
  if ( !a2 || !a3 )
  {
    LastError = -2147024809;
    v24 = -2147024809;
    v22 = 61;
    goto LABEL_34;
  }
  v7 = (const unsigned __int16 **)((char *)this + 248);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
  {
    if ( !*((_DWORD *)*v7 - 4) )
    {
      v8 = (const unsigned __int16 *)*((_QWORD *)this + 37);
      if ( *((_DWORD *)v8 - 4) || (v8 = (const unsigned __int16 *)*((_QWORD *)this + 33), *((_DWORD *)v8 - 4)) )
        DuplicateString(a2, v8, v6, a3 + 1);
    }
  }
  if ( *((_DWORD *)*v7 - 4) )
    DuplicateString(a2, *v7, v6, a3 + 1);
  v9 = (const unsigned __int16 *)*((_QWORD *)this + 33);
  if ( *((_DWORD *)v9 - 4) )
    DuplicateString(a2, v9, v6, a3 + 2);
  v10 = (const unsigned __int16 *)*((_QWORD *)this + 34);
  if ( *((_DWORD *)v10 - 4) )
    DuplicateString(a2, v10, v6, a3 + 4);
  v11 = (const unsigned __int16 *)*((_QWORD *)this + 35);
  if ( *((_DWORD *)v11 - 4) )
    DuplicateString(a2, v11, v6, a3 + 3);
  v12 = (const WCHAR *)*((_QWORD *)this + 36);
  if ( *((_DWORD *)v12 - 4) )
  {
    if ( !ConvertStringSidToSidW(v12, &Sid) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v24 = LastError;
      if ( LastError < 0 )
      {
        v22 = 102;
LABEL_34:
        v21 = LastError;
        WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v21, "sidtonameresponse.cpp", v22, "HRESULT", &base);
        goto LABEL_35;
      }
    }
    DuplicateSID(a2, Sid, (void **)a3);
  }
  v14 = (const unsigned __int16 *)*((_QWORD *)this + 37);
  if ( *((_DWORD *)v14 - 4) )
    DuplicateString(a2, v14, v6, a3 + 5);
  v15 = (const unsigned __int16 *)*((_QWORD *)this + 38);
  if ( *((_DWORD *)v15 - 4) )
    DuplicateString(a2, v15, v6, a3 + 6);
  v16 = (const unsigned __int16 *)*((_QWORD *)this + 39);
  if ( *((_DWORD *)v16 - 4) )
    DuplicateString(a2, v16, v6, a3 + 7);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
  {
    v18 = (const unsigned __int16 *)*((_QWORD *)this + 40);
    if ( !*((_DWORD *)v18 - 4) )
      v18 = L"user";
    DuplicateString(a2, v18, v17, a3 + 8);
  }
LABEL_35:
  LocalFree(Sid);
  v19 = v24;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v23);
  return v19;
}

```

## disassembly

```asm
0x18006ba80  mov     rax, rsp
0x18006ba83  mov     [rax+8], rbx
0x18006ba87  push    rbp
0x18006ba88  push    rsi
0x18006ba89  push    rdi
0x18006ba8a  push    r14
0x18006ba8c  push    r15
0x18006ba8e  sub     rsp, 80h
0x18006ba95  mov     rsi, r8
0x18006ba98  mov     rdi, rdx
0x18006ba9b  mov     rbx, rcx
0x18006ba9e  xor     ebp, ebp
0x18006baa0  mov     [rax+10h], ebp
0x18006baa3  mov     [rax+20h], rbp
0x18006baa7  lea     r9, [rax+10h]
0x18006baab  lea     r8, aSidtonamerespo_0; "SidToNameResponse::GetUserInfo"
0x18006bab2  lea     r15, aOnecoreuapDsEx_31+21h; "sidtonameresponse.cpp"
0x18006bab9  mov     rdx, r15
0x18006babc  lea     rcx, [rax-58h]
0x18006bac0  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18006bac5  nop
0x18006bac6  test    rdi, rdi
0x18006bac9  jz      loc_18006BC65
0x18006bacf  test    rsi, rsi
0x18006bad2  jz      loc_18006BC65
0x18006bad8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support> `wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl(void)'::`2'::impl
0x18006badf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled(void)
0x18006bae4  lea     r14, [rbx+0F8h]
0x18006baeb  test    al, al
0x18006baed  jz      short loc_18006BB1B
0x18006baef  mov     rax, [r14]
0x18006baf2  cmp     [rax-10h], ebp
0x18006baf5  jnz     short loc_18006BB1B
0x18006baf7  mov     rdx, [rbx+128h]
0x18006bafe  cmp     [rdx-10h], ebp
0x18006bb01  jnz     short loc_18006BB0F
0x18006bb03  mov     rdx, [rbx+108h]; unsigned __int16 *
0x18006bb0a  cmp     [rdx-10h], ebp
0x18006bb0d  jz      short loc_18006BB1B
0x18006bb0f  lea     r9, [rsi+8]; unsigned __int16 **
0x18006bb13  mov     rcx, rdi; struct AadContextFunctions *
0x18006bb16  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18006bb1b  mov     rdx, [r14]; unsigned __int16 *
0x18006bb1e  cmp     [rdx-10h], ebp
0x18006bb21  jz      short loc_18006BB2F
0x18006bb23  lea     r9, [rsi+8]; unsigned __int16 **
0x18006bb27  mov     rcx, rdi; struct AadContextFunctions *
0x18006bb2a  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18006bb2f  mov     rdx, [rbx+108h]; unsigned __int16 *
0x18006bb36  cmp     [rdx-10h], ebp
0x18006bb39  jz      short loc_18006BB47
0x18006bb3b  lea     r9, [rsi+10h]; unsigned __int16 **
0x18006bb3f  mov     rcx, rdi; struct AadContextFunctions *
0x18006bb42  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18006bb47  mov     rdx, [rbx+110h]; unsigned __int16 *
0x18006bb4e  cmp     [rdx-10h], ebp
0x18006bb51  jz      short loc_18006BB5F
0x18006bb53  lea     r9, [rsi+20h]; unsigned __int16 **
0x18006bb57  mov     rcx, rdi; struct AadContextFunctions *
0x18006bb5a  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18006bb5f  mov     rdx, [rbx+118h]; unsigned __int16 *
0x18006bb66  cmp     [rdx-10h], ebp
0x18006bb69  jz      short loc_18006BB77
0x18006bb6b  lea     r9, [rsi+18h]; unsigned __int16 **
0x18006bb6f  mov     rcx, rdi; struct AadContextFunctions *
0x18006bb72  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18006bb77  mov     rcx, [rbx+120h]; StringSid
0x18006bb7e  cmp     [rcx-10h], ebp
0x18006bb81  jz      short loc_18006BBEA
0x18006bb83  lea     rdx, [rsp+0A8h+Sid]; Sid
0x18006bb8b  call    cs:__imp_ConvertStringSidToSidW
0x18006bb91  test    eax, eax
0x18006bb93  jnz     short loc_18006BBD7
0x18006bb95  call    cs:__imp_GetLastError
0x18006bb9b  test    eax, eax
0x18006bb9d  jle     short loc_18006BBA7
0x18006bb9f  movzx   eax, ax
0x18006bba2  or      eax, 80070000h
0x18006bba7  mov     [rsp+0A8h+arg_8], eax
0x18006bbae  test    eax, eax
0x18006bbb0  jns     short loc_18006BBD7
0x18006bbb2  lea     rcx, base
0x18006bbb9  mov     [rsp+0A8h+var_68], rcx
0x18006bbbe  lea     rcx, aHresult; "HRESULT"
0x18006bbc5  mov     [rsp+0A8h+var_70], rcx
0x18006bbca  mov     [rsp+0A8h+var_78], 66h ; 'f'
0x18006bbd2  jmp     loc_18006BC91
0x18006bbd7  mov     r8, rsi; void **
0x18006bbda  mov     rdx, [rsp+0A8h+Sid]; void *
0x18006bbe2  mov     rcx, rdi; struct AadContextFunctions *
0x18006bbe5  call    ?DuplicateSID@@YAJPEAVAadContextFunctions@@PEAXPEAPEAX@Z; DuplicateSID(AadContextFunctions *,void *,void * *)
0x18006bbea  mov     rdx, [rbx+128h]; unsigned __int16 *
0x18006bbf1  cmp     [rdx-10h], ebp
0x18006bbf4  jz      short loc_18006BC02
0x18006bbf6  lea     r9, [rsi+28h]; unsigned __int16 **
0x18006bbfa  mov     rcx, rdi; struct AadContextFunctions *
0x18006bbfd  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18006bc02  mov     rdx, [rbx+130h]; unsigned __int16 *
0x18006bc09  cmp     [rdx-10h], ebp
0x18006bc0c  jz      short loc_18006BC1A
0x18006bc0e  lea     r9, [rsi+30h]; unsigned __int16 **
0x18006bc12  mov     rcx, rdi; struct AadContextFunctions *
0x18006bc15  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18006bc1a  mov     rdx, [rbx+138h]; unsigned __int16 *
0x18006bc21  cmp     [rdx-10h], ebp
0x18006bc24  jz      short loc_18006BC32
0x18006bc26  lea     r9, [rsi+38h]; unsigned __int16 **
0x18006bc2a  mov     rcx, rdi; struct AadContextFunctions *
0x18006bc2d  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18006bc32  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support> `wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl(void)'::`2'::impl
0x18006bc39  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled(void)
0x18006bc3e  test    al, al
0x18006bc40  jz      short loc_18006BCB0
0x18006bc42  mov     rdx, [rbx+140h]; unsigned __int16 *
0x18006bc49  lea     r9, [rsi+40h]; unsigned __int16 **
0x18006bc4d  mov     rcx, rdi; struct AadContextFunctions *
0x18006bc50  cmp     [rdx-10h], ebp
0x18006bc53  jz      short loc_18006BC5C
0x18006bc55  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18006bc5a  jmp     short loc_18006BCB0
0x18006bc5c  lea     rdx, aUser; "user"
0x18006bc63  jmp     short loc_18006BC55
0x18006bc65  mov     eax, 80070057h
0x18006bc6a  mov     [rsp+0A8h+arg_8], eax
0x18006bc71  lea     rcx, base
0x18006bc78  mov     [rsp+0A8h+var_68], rcx
0x18006bc7d  lea     rcx, aHresult; "HRESULT"
0x18006bc84  mov     [rsp+0A8h+var_70], rcx
0x18006bc89  mov     [rsp+0A8h+var_78], 3Dh ; '='
0x18006bc91  mov     [rsp+0A8h+var_80], r15
0x18006bc96  mov     ecx, 2
0x18006bc9b  mov     [rsp+0A8h+var_88], eax
0x18006bc9f  mov     r9d, ecx
0x18006bca2  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18006bca9  xor     edx, edx
0x18006bcab  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18006bcb0  mov     rcx, [rsp+0A8h+Sid]; hMem
0x18006bcb8  call    cs:__imp_LocalFree
0x18006bcbe  mov     ebx, [rsp+0A8h+arg_8]
0x18006bcc5  lea     rcx, [rsp+0A8h+var_58]
0x18006bcca  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18006bccf  mov     eax, ebx
0x18006bcd1  mov     rbx, [rsp+0A8h+arg_0]
0x18006bcd9  add     rsp, 80h
0x18006bce0  pop     r15
0x18006bce2  pop     r14
0x18006bce4  pop     rdi
0x18006bce5  pop     rsi
0x18006bce6  pop     rbp
0x18006bce7  retn
```
