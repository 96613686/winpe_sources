# TokenBindingCache::GetAikName(_NGC_TB_AIK_KEY_TYPE,AADJoinInfo const &,ushort const *,CSecureString &)

- ea: `0x18003dc74`
- end: `0x18003df32`
- name: `?GetAikName@TokenBindingCache@@AEAAJW4_NGC_TB_AIK_KEY_TYPE@@AEBUAADJoinInfo@@PEBGAEAVCSecureString@@@Z`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003df38`

## callees

- `0x1800063f4`
- `0x1800065e8`
- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x1800090d0`
- `0x18003dc74`
- `0x180071e14`
- `0x180077b34`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003def8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003def8`
- `popkeycli!NgcGetTokenBindingAikName` at `0x18003de43`
- `popkeycli!NgcGetTokenBindingAikName` at `0x18003de43`

## string_xrefs

- `0x18003dcbc`: `TokenBindingCache::GetAikName`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TokenBindingCache::GetAikName(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v8; // r12
  const WCHAR *v9; // rax
  const wchar_t *v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rcx
  int TokenBindingAikName; // eax
  unsigned int v14; // edi
  int v16; // [rsp+38h] [rbp-31h]
  __int64 v17; // [rsp+38h] [rbp-31h]
  __int64 v18; // [rsp+58h] [rbp-11h] BYREF
  const char *v19[7]; // [rsp+60h] [rbp-9h] BYREF
  int v20; // [rsp+C8h] [rbp+5Fh] BYREF
  int v21; // [rsp+CCh] [rbp+63h]
  HLOCAL hMem; // [rsp+D8h] [rbp+6Fh] BYREF

  v21 = HIDWORD(a1);
  v20 = 0;
  hMem = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v18);
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v19,
    (int)"tokenbindinghelper.cpp",
    (int)"TokenBindingCache::GetAikName",
    (int)&v20);
  v8 = a5;
  ATL::CSimpleStringT<unsigned short,0>::Empty(a5);
  v9 = &base;
  if ( *(_QWORD *)(a3 + 8) )
    v9 = *(const WCHAR **)(a3 + 8);
  v16 = 644;
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "tokenbindinghelper.cpp", v16, "Join tenant Id", v9);
  v10 = L"WPJ";
  if ( *(_DWORD *)(a3 + 16) != 2 )
    v10 = L"CDJ";
  LODWORD(v17) = 645;
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "tokenbindinghelper.cpp", v17, "Join type", v10);
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%u", 4, 0, "tokenbindinghelper.cpp", 646, "Key type", a2);
  v20 = StringUtility::StringFormat(&v18, L"%s_%s", *(_QWORD *)(a3 + 8), *(_QWORD *)(a3 + 24));
  v11 = v18;
  if ( v20 < 0 )
  {
    v12 = 2;
LABEL_12:
    WPPTraceLogA(v12, 0, "%x 0x%08x %s:%u : %s:%ws");
    goto LABEL_13;
  }
  if ( *(_DWORD *)(a3 + 16) != 2 )
    a4 = 0;
  TokenBindingAikName = NgcGetTokenBindingAikName(a2, *(_QWORD *)a3, v18, a4, &hMem);
  v20 = TokenBindingAikName;
  if ( TokenBindingAikName >= 0 )
  {
    CSecureString::operator=(v8, (__int64)hMem);
    v12 = 4;
    goto LABEL_12;
  }
  WPPTraceLogA(
    3,
    0,
    "%x 0x%08x %s:%u : %s:%u",
    3,
    TokenBindingAikName,
    "tokenbindinghelper.cpp",
    660,
    "Failed to get AIK name for key type",
    a2);
  v20 = 0;
LABEL_13:
  LocalFree(hMem);
  v14 = v20;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v19);
  ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
  return v14;
}

```

## disassembly

```asm
0x18003dc74  mov     rax, rsp
0x18003dc77  mov     [rax+10h], rbx
0x18003dc7b  mov     [rax+20h], rsi
0x18003dc7f  mov     [rax+8], rcx
0x18003dc83  push    rbp
0x18003dc84  push    rdi
0x18003dc85  push    r12
0x18003dc87  push    r14
0x18003dc89  push    r15
0x18003dc8b  lea     rbp, [rax-57h]
0x18003dc8f  sub     rsp, 90h
0x18003dc96  mov     rsi, r9
0x18003dc99  mov     r14, r8
0x18003dc9c  mov     r15d, edx
0x18003dc9f  mov     [rbp+4Fh+arg_0], 0
0x18003dca6  mov     [rbp+4Fh+hMem], 0
0x18003dcae  lea     rcx, [rbp+4Fh+var_60]; void *
0x18003dcb2  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003dcb7  nop
0x18003dcb8  lea     r9, [rbp+4Fh+arg_0]
0x18003dcbc  lea     r8, aTokenbindingca_7; "TokenBindingCache::GetAikName"
0x18003dcc3  lea     rbx, aOnecoreuapDsEx_15+21h; "tokenbindinghelper.cpp"
0x18003dcca  mov     rdx, rbx
0x18003dccd  lea     rcx, [rbp+4Fh+var_58]
0x18003dcd1  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18003dcd6  nop
0x18003dcd7  mov     r12, [rbp+4Fh+arg_20]
0x18003dcdb  mov     rcx, r12
0x18003dcde  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18003dce3  lea     rdi, base
0x18003dcea  mov     rax, rdi
0x18003dced  cmp     qword ptr [r14+8], 0
0x18003dcf2  cmovnz  rax, [r14+8]
0x18003dcf7  mov     [rsp+0B0h+var_70], rax
0x18003dcfc  lea     rax, aJoinTenantId; "Join tenant Id"
0x18003dd03  mov     [rsp+0B0h+var_78], rax
0x18003dd08  mov     dword ptr [rsp+0B0h+var_80], 284h
0x18003dd10  mov     qword ptr [rsp+0B0h+var_88], rbx
0x18003dd15  mov     [rsp+0B0h+var_90], 0
0x18003dd1e  mov     eax, 4
0x18003dd23  mov     r9d, eax
0x18003dd26  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003dd2d  xor     edx, edx
0x18003dd2f  mov     ecx, eax
0x18003dd31  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003dd36  lea     rcx, aCdj; "CDJ"
0x18003dd3d  lea     rax, aWpj; "WPJ"
0x18003dd44  cmp     dword ptr [r14+10h], 2
0x18003dd49  cmovnz  rax, rcx
0x18003dd4d  mov     [rsp+0B0h+var_70], rax
0x18003dd52  lea     rax, aJoinType; "Join type"
0x18003dd59  mov     [rsp+0B0h+var_78], rax
0x18003dd5e  mov     dword ptr [rsp+0B0h+var_80], 285h
0x18003dd66  mov     qword ptr [rsp+0B0h+var_88], rbx
0x18003dd6b  mov     [rsp+0B0h+var_90], 0
0x18003dd74  mov     ecx, 4
0x18003dd79  mov     r9d, ecx
0x18003dd7c  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003dd83  xor     edx, edx
0x18003dd85  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003dd8a  mov     dword ptr [rsp+0B0h+var_70], r15d
0x18003dd8f  lea     rax, aKeyType; "Key type"
0x18003dd96  mov     [rsp+0B0h+var_78], rax
0x18003dd9b  mov     dword ptr [rsp+0B0h+var_80], 286h
0x18003dda3  mov     qword ptr [rsp+0B0h+var_88], rbx
0x18003dda8  mov     [rsp+0B0h+var_90], 0
0x18003ddb1  mov     eax, 4
0x18003ddb6  mov     r9d, eax
0x18003ddb9  lea     r8, aX0x08xSUSU; "%x 0x%08x %s:%u : %s:%u"
0x18003ddc0  xor     edx, edx
0x18003ddc2  mov     ecx, eax
0x18003ddc4  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003ddc9  mov     r9, [r14+18h]
0x18003ddcd  mov     r8, [r14+8]
0x18003ddd1  lea     rdx, aSS_2; "%s_%s"
0x18003ddd8  lea     rcx, [rbp+4Fh+var_60]
0x18003dddc  call    ?StringFormat@StringUtility@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGZZ; StringUtility::StringFormat(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,...)
0x18003dde1  mov     [rbp+4Fh+arg_0], eax
0x18003dde4  mov     rbx, [rbp+4Fh+var_60]
0x18003dde8  test    eax, eax
0x18003ddea  jns     short loc_18003DE23
0x18003ddec  mov     [rsp+0B0h+var_70], rdi
0x18003ddf1  lea     rcx, aHresult; "HRESULT"
0x18003ddf8  mov     [rsp+0B0h+var_78], rcx
0x18003ddfd  mov     dword ptr [rsp+0B0h+var_80], 28Ah
0x18003de05  lea     rcx, aOnecoreuapDsEx_15+21h; "tokenbindinghelper.cpp"
0x18003de0c  mov     qword ptr [rsp+0B0h+var_88], rcx
0x18003de11  mov     dword ptr [rsp+0B0h+var_90], eax
0x18003de15  mov     r9d, 2
0x18003de1b  mov     ecx, r9d
0x18003de1e  jmp     loc_18003DEE6
0x18003de23  xor     eax, eax
0x18003de25  cmp     dword ptr [r14+10h], 2
0x18003de2a  cmovnz  rsi, rax
0x18003de2e  lea     rax, [rbp+4Fh+hMem]
0x18003de32  mov     [rsp+0B0h+var_90], rax
0x18003de37  mov     r9, rsi
0x18003de3a  mov     r8, rbx
0x18003de3d  mov     rdx, [r14]
0x18003de40  mov     ecx, r15d
0x18003de43  call    cs:__imp_NgcGetTokenBindingAikName
0x18003de49  mov     [rbp+4Fh+arg_0], eax
0x18003de4c  test    eax, eax
0x18003de4e  jns     short loc_18003DE98
0x18003de50  mov     dword ptr [rsp+0B0h+var_70], r15d
0x18003de55  lea     rcx, aFailedToGetAik; "Failed to get AIK name for key type"
0x18003de5c  mov     [rsp+0B0h+var_78], rcx
0x18003de61  mov     dword ptr [rsp+0B0h+var_80], 294h
0x18003de69  lea     rcx, aOnecoreuapDsEx_15+21h; "tokenbindinghelper.cpp"
0x18003de70  mov     qword ptr [rsp+0B0h+var_88], rcx
0x18003de75  mov     dword ptr [rsp+0B0h+var_90], eax
0x18003de79  mov     ecx, 3
0x18003de7e  mov     r9d, ecx
0x18003de81  lea     r8, aX0x08xSUSU; "%x 0x%08x %s:%u : %s:%u"
0x18003de88  xor     edx, edx
0x18003de8a  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003de8f  mov     [rbp+4Fh+arg_0], 0
0x18003de96  jmp     short loc_18003DEF4
0x18003de98  mov     rdx, [rbp+4Fh+hMem]
0x18003de9c  mov     rcx, r12
0x18003de9f  call    ??4CSecureString@@QEAAAEAV0@PEBG@Z; CSecureString::operator=(ushort const *)
0x18003dea4  cmp     qword ptr [r12], 0
0x18003dea9  cmovnz  rdi, [r12]
0x18003deae  mov     [rsp+0B0h+var_70], rdi
0x18003deb3  lea     rax, aAik; "AIK"
0x18003deba  mov     [rsp+0B0h+var_78], rax
0x18003debf  mov     dword ptr [rsp+0B0h+var_80], 29Ah
0x18003dec7  lea     rcx, aOnecoreuapDsEx_15+21h; "tokenbindinghelper.cpp"
0x18003dece  mov     qword ptr [rsp+0B0h+var_88], rcx
0x18003ded3  mov     [rsp+0B0h+var_90], 0
0x18003dedc  mov     eax, 4
0x18003dee1  mov     r9d, eax
0x18003dee4  mov     ecx, eax
0x18003dee6  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003deed  xor     edx, edx
0x18003deef  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003def4  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18003def8  call    cs:__imp_LocalFree
0x18003defe  mov     edi, [rbp+4Fh+arg_0]
0x18003df01  lea     rcx, [rbp+4Fh+var_58]
0x18003df05  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18003df0a  nop
0x18003df0b  lea     rcx, [rbx-18h]; this
0x18003df0f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003df14  mov     eax, edi
0x18003df16  lea     r11, [rsp+0B0h+var_20]
0x18003df1e  mov     rbx, [r11+38h]
0x18003df22  mov     rsi, [r11+48h]
0x18003df26  mov     rsp, r11
0x18003df29  pop     r15
0x18003df2b  pop     r14
0x18003df2d  pop     r12
0x18003df2f  pop     rdi
0x18003df30  pop     rbp
0x18003df31  retn
```
