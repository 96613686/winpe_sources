# BasicXmlParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)

- ea: `0x180015fac`
- end: `0x18001615c`
- name: `?WriteAttribute@BasicXmlParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z`
- size: `432`
- prototype: `__int64 __fastcall(BasicXmlParser *__hidden this, const struct _LUTF8_STRING *, const struct _LUTF8_STRING *, unsigned __int16 *, struct _GUID *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180015800`
- `0x180016984`

## callees

- `0x1800059fc`
- `0x180014638`
- `0x180014694`
- `0x180015fac`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `ServicingCommon!RtlDuplicateLUnicodeStringToLUtf8String` at `0x1800160bb`
- `ServicingCommon!RtlDuplicateLUnicodeStringToLUtf8String` at `0x1800160bb`
- `ServicingCommon!RtlInitLUnicodeStringFromNullTerminatedString` at `0x180016071`
- `ServicingCommon!RtlInitLUnicodeStringFromNullTerminatedString` at `0x180016071`
- `ole32!CoTaskMemFree` at `0x18001613a`
- `ole32!CoTaskMemFree` at `0x18001613a`

## string_xrefs

- `0x18001608c`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x1800160fd`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x180016096`: `BasicXmlParser::WriteAttribute %s (0x%x) in file %S line %d`
- `0x180016120`: `BasicXmlParser::WriteAttribute %s (0x%x) in file %S line %d`

## pseudocode

```c
__int64 __fastcall BasicXmlParser::WriteAttribute(
        BasicXmlParser *this,
        const struct _LUTF8_STRING *a2,
        const struct _LUTF8_STRING *a3,
        unsigned __int16 *a4,
        struct _GUID *a5,
        unsigned __int64 *a6)
{
  int v8; // edi
  unsigned __int64 v9; // rdx
  int inited; // ebx
  const wchar_t *v12; // r8
  int v13; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v15; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h]
  __int128 v17; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h]
  char v19[256]; // [rsp+70h] [rbp-90h] BYREF

  v18 = 0;
  pv = 0;
  v14 = 0;
  v17 = 0;
  v15 = 0;
  if ( a4 )
  {
    inited = RtlInitLUnicodeStringFromNullTerminatedString(a4, &v17, a3, a6);
    if ( inited >= 0 )
    {
      inited = RtlDuplicateLUnicodeStringToLUtf8String(&v17, &v15);
      if ( inited >= 0 )
      {
        v8 = 1;
        goto LABEL_14;
      }
      v13 = 2983;
      v12 = L"failed to duplicate unicode string";
    }
    else
    {
      v13 = 2980;
      v12 = L"failed to init unicode string";
    }
    UnattendLogW(
      2,
      L"BasicXmlParser::WriteAttribute %s (0x%x) in file %S line %d",
      v12,
      (unsigned int)inited,
      "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
      v13);
  }
  else
  {
    if ( !a6 )
      return 87;
    v8 = 0;
    if ( (int)StringCbPrintfA(v19, 0x100u, "%I64u", *a6) >= 0 && (int)StringCbLengthA(v19, v9, &v14) >= 0 )
    {
      *((_QWORD *)&v15 + 1) = v14;
      *(_QWORD *)&v15 = v14;
      pv = v19;
LABEL_14:
      inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const struct _LUTF8_STRING *, __int128 *))(**((_QWORD **)this + 5) + 112LL))(
                 *((_QWORD *)this + 5),
                 0,
                 a2,
                 &v15);
      if ( inited < 0 )
        UnattendLogW(
          2,
          L"BasicXmlParser::WriteAttribute %s (0x%x) in file %S line %d",
          L"failed to emit attribute",
          (unsigned int)inited,
          "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
          3038);
      if ( v8 )
      {
        if ( pv )
          CoTaskMemFree(pv);
      }
      return (unsigned int)inited;
    }
    return (unsigned int)-1073741811;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180015fac  push    rbp
0x180015fae  push    rbx
0x180015faf  push    rsi
0x180015fb0  push    rdi
0x180015fb1  push    r14
0x180015fb3  lea     rbp, [rsp-80h]
0x180015fb8  sub     rsp, 180h
0x180015fbf  mov     rax, cs:__security_cookie
0x180015fc6  xor     rax, rsp
0x180015fc9  mov     [rbp+0A0h+var_30], rax
0x180015fcd  mov     rax, r9
0x180015fd0  mov     rsi, rcx
0x180015fd3  mov     r9, [rbp+0A0h+arg_28]
0x180015fda  xor     ecx, ecx
0x180015fdc  mov     [rsp+1A0h+var_140], rcx
0x180015fe1  xorps   xmm0, xmm0
0x180015fe4  mov     [rsp+1A0h+pv], rcx
0x180015fe9  xorps   xmm1, xmm1
0x180015fec  mov     [rsp+1A0h+var_170], rcx
0x180015ff1  mov     r14, rdx
0x180015ff4  movups  [rsp+1A0h+var_150], xmm0
0x180015ff9  movups  [rsp+1A0h+var_168], xmm1
0x180015ffe  test    rax, rax
0x180016001  jnz     short loc_180016069
0x180016003  test    r9, r9
0x180016006  jz      short loc_18001605F
0x180016008  mov     r9, [r9]
0x18001600b  lea     r8, aI64u; "%I64u"
0x180016012  mov     edx, 100h; unsigned __int64
0x180016017  lea     rcx, [rsp+1A0h+var_130]; char *
0x18001601c  xor     edi, edi
0x18001601e  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x180016023  test    eax, eax
0x180016025  jns     short loc_180016031
0x180016027  mov     ebx, 0C000000Dh
0x18001602c  jmp     loc_180016140
0x180016031  lea     r8, [rsp+1A0h+var_170]; unsigned __int64 *
0x180016036  lea     rcx, [rsp+1A0h+var_130]; char *
0x18001603b  call    ?StringCbLengthA@@YAJPEBD_KPEA_K@Z; StringCbLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180016040  test    eax, eax
0x180016042  js      short loc_180016027
0x180016044  mov     rax, [rsp+1A0h+var_170]
0x180016049  mov     qword ptr [rsp+1A0h+var_168+8], rax
0x18001604e  mov     qword ptr [rsp+1A0h+var_168], rax
0x180016053  lea     rax, [rsp+1A0h+var_130]
0x180016058  mov     [rsp+1A0h+pv], rax
0x18001605d  jmp     short loc_1800160DD
0x18001605f  mov     eax, 57h ; 'W'
0x180016064  jmp     loc_180016142
0x180016069  lea     rdx, [rsp+1A0h+var_150]
0x18001606e  mov     rcx, rax
0x180016071  call    cs:__imp_RtlInitLUnicodeStringFromNullTerminatedString
0x180016077  mov     ebx, eax
0x180016079  test    eax, eax
0x18001607b  jns     short loc_1800160B1
0x18001607d  mov     [rsp+1A0h+var_178], 0BA4h
0x180016085  lea     r8, aFailedToInitUn; "failed to init unicode string"
0x18001608c  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180016093  mov     r9d, ebx
0x180016096  lea     rdx, aBasicxmlparser; "BasicXmlParser::WriteAttribute %s (0x%x"...
0x18001609d  mov     [rsp+1A0h+var_180], rax
0x1800160a2  mov     ecx, 2
0x1800160a7  call    UnattendLogW
0x1800160ac  jmp     loc_180016140
0x1800160b1  lea     rdx, [rsp+1A0h+var_168]
0x1800160b6  lea     rcx, [rsp+1A0h+var_150]
0x1800160bb  call    cs:__imp_RtlDuplicateLUnicodeStringToLUtf8String
0x1800160c1  mov     ebx, eax
0x1800160c3  test    eax, eax
0x1800160c5  jns     short loc_1800160D8
0x1800160c7  mov     [rsp+1A0h+var_178], 0BA7h
0x1800160cf  lea     r8, aFailedToDuplic; "failed to duplicate unicode string"
0x1800160d6  jmp     short loc_18001608C
0x1800160d8  mov     edi, 1
0x1800160dd  mov     rcx, [rsi+28h]
0x1800160e1  lea     r9, [rsp+1A0h+var_168]
0x1800160e6  mov     r8, r14
0x1800160e9  xor     edx, edx
0x1800160eb  mov     rax, [rcx]
0x1800160ee  mov     rax, [rax+70h]
0x1800160f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160f7  mov     ebx, eax
0x1800160f9  test    eax, eax
0x1800160fb  jns     short loc_18001612C
0x1800160fd  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180016104  mov     [rsp+1A0h+var_178], 0BDEh
0x18001610c  mov     r9d, ebx
0x18001610f  mov     [rsp+1A0h+var_180], rax
0x180016114  lea     r8, aFailedToEmitAt; "failed to emit attribute"
0x18001611b  mov     ecx, 2
0x180016120  lea     rdx, aBasicxmlparser; "BasicXmlParser::WriteAttribute %s (0x%x"...
0x180016127  call    UnattendLogW
0x18001612c  test    edi, edi
0x18001612e  jz      short loc_180016140
0x180016130  mov     rcx, [rsp+1A0h+pv]; pv
0x180016135  test    rcx, rcx
0x180016138  jz      short loc_180016140
0x18001613a  call    cs:__imp_CoTaskMemFree
0x180016140  mov     eax, ebx
0x180016142  mov     rcx, [rbp+0A0h+var_30]
0x180016146  xor     rcx, rsp; StackCookie
0x180016149  call    __security_check_cookie
0x18001614e  add     rsp, 180h
0x180016155  pop     r14
0x180016157  pop     rdi
0x180016158  pop     rsi
0x180016159  pop     rbx
0x18001615a  pop     rbp
0x18001615b  retn
```
