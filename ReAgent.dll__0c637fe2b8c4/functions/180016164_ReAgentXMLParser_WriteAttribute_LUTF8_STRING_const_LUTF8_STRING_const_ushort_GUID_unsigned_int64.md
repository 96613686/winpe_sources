# ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)

- ea: `0x180016164`
- end: `0x1800163db`
- name: `?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z`
- size: `631`
- prototype: `__int64 __fastcall(ReAgentXMLParser *__hidden this, const struct _LUTF8_STRING *, const struct _LUTF8_STRING *, unsigned __int16 *, struct _GUID *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180014754`
- `0x180016a50`
- `0x180040390`

## callees

- `0x1800059fc`
- `0x180014638`
- `0x180014694`
- `0x180016164`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `ServicingCommon!RtlDuplicateLUnicodeStringToLUtf8String` at `0x18001623c`
- `ServicingCommon!RtlDuplicateLUnicodeStringToLUtf8String` at `0x18001623c`
- `ServicingCommon!RtlInitLUnicodeStringFromNullTerminatedString` at `0x1800161f3`
- `ServicingCommon!RtlInitLUnicodeStringFromNullTerminatedString` at `0x1800161f3`
- `ole32!CoTaskMemFree` at `0x1800163a2`
- `ole32!CoTaskMemFree` at `0x1800163a2`

## string_xrefs

- `0x18001620e`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x180016365`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x180016218`: `ReAgentXMLParser::WriteAttribute %s (0x%x) in file %S line %d`
- `0x180016388`: `ReAgentXMLParser::WriteAttribute %s (0x%x) in file %S line %d`

## pseudocode

```c
__int64 __fastcall ReAgentXMLParser::WriteAttribute(
        ReAgentXMLParser *this,
        const struct _LUTF8_STRING *a2,
        const struct _LUTF8_STRING *a3,
        unsigned __int16 *a4,
        struct _GUID *a5,
        unsigned __int64 *a6)
{
  int v8; // r15d
  int inited; // ebx
  const wchar_t *v10; // r8
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdx
  __int64 v14; // [rsp+28h] [rbp-D8h]
  int v15; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v16; // [rsp+70h] [rbp-90h] BYREF
  __int128 v17; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-78h]
  __int128 v19; // [rsp+90h] [rbp-70h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-60h]
  char v21[256]; // [rsp+B0h] [rbp-50h] BYREF

  v20 = 0;
  pv = 0;
  v16 = 0;
  v19 = 0;
  v17 = 0;
  if ( a4 || a5 )
  {
    v8 = 0;
    if ( a4 )
    {
      inited = RtlInitLUnicodeStringFromNullTerminatedString(a4, &v19, a3, a5);
      if ( inited >= 0 )
      {
        inited = RtlDuplicateLUnicodeStringToLUtf8String(&v19, &v17);
        if ( inited >= 0 )
        {
          v8 = 1;
LABEL_21:
          inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const struct _LUTF8_STRING *, __int128 *))(**((_QWORD **)this + 5) + 112LL))(
                     *((_QWORD *)this + 5),
                     0,
                     a2,
                     &v17);
          if ( inited < 0 )
          {
            LODWORD(v14) = 1371;
            UnattendLogW(
              2,
              L"ReAgentXMLParser::WriteAttribute %s (0x%x) in file %S line %d",
              L"failed to emit attribute",
              (unsigned int)inited,
              "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
              v14);
          }
          if ( v8 )
          {
            if ( pv )
              CoTaskMemFree(pv);
          }
          return (unsigned int)inited;
        }
        v15 = 1316;
        v10 = L"failed to duplicate unicode string";
      }
      else
      {
        v15 = 1313;
        v10 = L"failed to init unicode string";
      }
      UnattendLogW(
        2,
        L"ReAgentXMLParser::WriteAttribute %s (0x%x) in file %S line %d",
        v10,
        (unsigned int)inited,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
        v15);
      return (unsigned int)inited;
    }
    if ( a5 )
    {
      if ( (int)StringCbPrintfA(
                  v21,
                  0x100u,
                  "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
                  a5->Data1,
                  a5->Data2,
                  a5->Data3,
                  a5->Data4[0],
                  a5->Data4[1],
                  a5->Data4[2],
                  a5->Data4[3],
                  a5->Data4[4],
                  a5->Data4[5],
                  a5->Data4[6],
                  a5->Data4[7]) >= 0 )
      {
        v11 = 38;
LABEL_20:
        *((_QWORD *)&v17 + 1) = v11;
        *(_QWORD *)&v17 = v11;
        pv = v21;
        goto LABEL_21;
      }
      return (unsigned int)-1073741811;
    }
    if ( a6 )
    {
LABEL_17:
      if ( (int)StringCbPrintfA(v21, 0x100u, "%I64u", *a6) >= 0 && (int)StringCbLengthA(v21, v12, &v16) >= 0 )
      {
        v11 = v16;
        goto LABEL_20;
      }
      return (unsigned int)-1073741811;
    }
  }
  else if ( a6 )
  {
    v8 = 0;
    goto LABEL_17;
  }
  return 87;
}

```

## disassembly

```asm
0x180016164  mov     [rsp-8+arg_10], rbx
0x180016169  push    rbp
0x18001616a  push    rsi
0x18001616b  push    rdi
0x18001616c  push    r12
0x18001616e  push    r13
0x180016170  push    r14
0x180016172  push    r15
0x180016174  lea     rbp, [rsp-0C0h]
0x18001617c  sub     rsp, 1C0h
0x180016183  mov     rax, cs:__security_cookie
0x18001618a  xor     rax, rsp
0x18001618d  mov     [rbp+0F0h+var_40], rax
0x180016194  mov     rax, [rbp+0F0h+arg_28]
0x18001619b  mov     r10, r9
0x18001619e  mov     r9, [rbp+0F0h+arg_20]
0x1800161a5  mov     r13, rcx
0x1800161a8  xor     ecx, ecx
0x1800161aa  xorps   xmm0, xmm0
0x1800161ad  mov     [rbp+0F0h+var_150], rcx
0x1800161b1  xorps   xmm1, xmm1
0x1800161b4  mov     [rbp+0F0h+pv], rcx
0x1800161b8  mov     r12, rdx
0x1800161bb  mov     [rsp+1F0h+var_180], rcx
0x1800161c0  movups  [rbp+0F0h+var_160], xmm0
0x1800161c4  movups  [rsp+1F0h+var_178], xmm1
0x1800161c9  test    r10, r10
0x1800161cc  jnz     short loc_1800161E4
0x1800161ce  test    r9, r9
0x1800161d1  jnz     short loc_1800161E4
0x1800161d3  test    rax, rax
0x1800161d6  jz      loc_1800163AC
0x1800161dc  xor     r15d, r15d
0x1800161df  jmp     loc_180016301
0x1800161e4  xor     r15d, r15d
0x1800161e7  test    r10, r10
0x1800161ea  jz      short loc_180016264
0x1800161ec  lea     rdx, [rbp+0F0h+var_160]
0x1800161f0  mov     rcx, r10
0x1800161f3  call    cs:__imp_RtlInitLUnicodeStringFromNullTerminatedString
0x1800161f9  mov     ebx, eax
0x1800161fb  test    eax, eax
0x1800161fd  jns     short loc_180016233
0x1800161ff  mov     dword ptr [rsp+1F0h+var_1C8], 521h
0x180016207  lea     r8, aFailedToInitUn; "failed to init unicode string"
0x18001620e  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180016215  mov     r9d, ebx
0x180016218  lea     rdx, aReagentxmlpars_9; "ReAgentXMLParser::WriteAttribute %s (0x"...
0x18001621f  mov     [rsp+1F0h+var_1D0], rax
0x180016224  mov     ecx, 2
0x180016229  call    UnattendLogW
0x18001622e  jmp     loc_1800163A8
0x180016233  lea     rdx, [rsp+1F0h+var_178]
0x180016238  lea     rcx, [rbp+0F0h+var_160]
0x18001623c  call    cs:__imp_RtlDuplicateLUnicodeStringToLUtf8String
0x180016242  mov     ebx, eax
0x180016244  test    eax, eax
0x180016246  jns     short loc_180016259
0x180016248  mov     dword ptr [rsp+1F0h+var_1C8], 524h
0x180016250  lea     r8, aFailedToDuplic; "failed to duplicate unicode string"
0x180016257  jmp     short loc_18001620E
0x180016259  mov     r15d, 1
0x18001625f  jmp     loc_180016345
0x180016264  test    r9, r9
0x180016267  jz      loc_1800162F8
0x18001626d  movzx   ecx, byte ptr [r9+0Eh]
0x180016272  movzx   edx, byte ptr [r9+0Dh]
0x180016277  movzx   r8d, byte ptr [r9+0Ch]
0x18001627c  movzx   eax, byte ptr [r9+0Fh]
0x180016281  movzx   r10d, byte ptr [r9+0Bh]
0x180016286  movzx   r11d, byte ptr [r9+0Ah]
0x18001628b  movzx   ebx, byte ptr [r9+9]
0x180016290  movzx   edi, byte ptr [r9+8]
0x180016295  movzx   esi, word ptr [r9+6]
0x18001629a  movzx   r14d, word ptr [r9+4]
0x18001629f  mov     r9d, [r9]
0x1800162a2  mov     [rsp+1F0h+var_188], eax
0x1800162a6  mov     [rsp+1F0h+var_190], ecx
0x1800162aa  lea     rcx, [rbp+0F0h+var_140]; char *
0x1800162ae  mov     [rsp+1F0h+var_198], edx
0x1800162b2  mov     edx, 100h; unsigned __int64
0x1800162b7  mov     [rsp+1F0h+var_1A0], r8d
0x1800162bc  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x1800162c3  mov     [rsp+1F0h+var_1A8], r10d
0x1800162c8  mov     [rsp+1F0h+var_1B0], r11d
0x1800162cd  mov     [rsp+1F0h+var_1B8], ebx
0x1800162d1  mov     [rsp+1F0h+var_1C0], edi
0x1800162d5  mov     dword ptr [rsp+1F0h+var_1C8], esi
0x1800162d9  mov     dword ptr [rsp+1F0h+var_1D0], r14d
0x1800162de  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x1800162e3  test    eax, eax
0x1800162e5  jns     short loc_1800162F1
0x1800162e7  mov     ebx, 0C000000Dh
0x1800162ec  jmp     loc_1800163A8
0x1800162f1  mov     eax, 26h ; '&'
0x1800162f6  jmp     short loc_180016334
0x1800162f8  test    rax, rax
0x1800162fb  jz      loc_1800163AC
0x180016301  mov     r9, [rax]
0x180016304  lea     r8, aI64u; "%I64u"
0x18001630b  mov     edx, 100h; unsigned __int64
0x180016310  lea     rcx, [rbp+0F0h+var_140]; char *
0x180016314  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x180016319  test    eax, eax
0x18001631b  js      short loc_1800162E7
0x18001631d  lea     r8, [rsp+1F0h+var_180]; unsigned __int64 *
0x180016322  lea     rcx, [rbp+0F0h+var_140]; char *
0x180016326  call    ?StringCbLengthA@@YAJPEBD_KPEA_K@Z; StringCbLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18001632b  test    eax, eax
0x18001632d  js      short loc_1800162E7
0x18001632f  mov     rax, [rsp+1F0h+var_180]
0x180016334  mov     qword ptr [rbp+0F0h+var_178+8], rax
0x180016338  mov     qword ptr [rsp+1F0h+var_178], rax
0x18001633d  lea     rax, [rbp+0F0h+var_140]
0x180016341  mov     [rbp+0F0h+pv], rax
0x180016345  mov     rcx, [r13+28h]
0x180016349  lea     r9, [rsp+1F0h+var_178]
0x18001634e  mov     r8, r12
0x180016351  xor     edx, edx
0x180016353  mov     rax, [rcx]
0x180016356  mov     rax, [rax+70h]
0x18001635a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001635f  mov     ebx, eax
0x180016361  test    eax, eax
0x180016363  jns     short loc_180016394
0x180016365  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18001636c  mov     dword ptr [rsp+1F0h+var_1C8], 55Bh
0x180016374  mov     r9d, ebx
0x180016377  mov     [rsp+1F0h+var_1D0], rax
0x18001637c  lea     r8, aFailedToEmitAt; "failed to emit attribute"
0x180016383  mov     ecx, 2
0x180016388  lea     rdx, aReagentxmlpars_9; "ReAgentXMLParser::WriteAttribute %s (0x"...
0x18001638f  call    UnattendLogW
0x180016394  test    r15d, r15d
0x180016397  jz      short loc_1800163A8
0x180016399  mov     rcx, [rbp+0F0h+pv]; pv
0x18001639d  test    rcx, rcx
0x1800163a0  jz      short loc_1800163A8
0x1800163a2  call    cs:__imp_CoTaskMemFree
0x1800163a8  mov     eax, ebx
0x1800163aa  jmp     short loc_1800163B1
0x1800163ac  mov     eax, 57h ; 'W'
0x1800163b1  mov     rcx, [rbp+0F0h+var_40]
0x1800163b8  xor     rcx, rsp; StackCookie
0x1800163bb  call    __security_check_cookie
0x1800163c0  mov     rbx, [rsp+1F0h+arg_10]
0x1800163c8  add     rsp, 1C0h
0x1800163cf  pop     r15
0x1800163d1  pop     r14
0x1800163d3  pop     r13
0x1800163d5  pop     r12
0x1800163d7  pop     rdi
0x1800163d8  pop     rsi
0x1800163d9  pop     rbp
0x1800163da  retn
```
