# CMsmqVssWriter::HandleRestoreThread(void *)

- ea: `0x180090d40`
- end: `0x180091079`
- name: `?HandleRestoreThread@CMsmqVssWriter@@CAKPEAX@Z`
- size: `825`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000bb04`
- `0x18000f35c`
- `0x18002c61c`
- `0x18008f5bc`
- `0x18008fc94`
- `0x180090d40`
- `0x18009331c`
- `0x18009422c`
- `0x18009a488`
- `0x18009a590`
- `0x18009aa2c`
- `0x18009bd1c`
- `0x1800cff88`
- `0x1800cffcc`
- `0x1800d6e56`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x180090e40`
- `msvcrt!free` at `0x180090e4c`
- `msvcrt!free` at `0x180090f04`
- `msvcrt!free` at `0x180090f10`
- `msvcrt!free` at `0x180090f7a`
- `msvcrt!free` at `0x180090f86`
- `msvcrt!free` at `0x18009103c`
- `msvcrt!free` at `0x180091048`
- `msvcrt!free` at `0x180090e40`
- `msvcrt!free` at `0x180090e4c`
- `msvcrt!free` at `0x180090f04`
- `msvcrt!free` at `0x180090f10`
- `msvcrt!free` at `0x180090f7a`
- `msvcrt!free` at `0x180090f86`
- `msvcrt!free` at `0x18009103c`
- `msvcrt!free` at `0x180091048`
- `mqsec!DeleteFalconKeyValue` at `0x180090fa3`
- `mqsec!DeleteFalconKeyValue` at `0x180090fa3`

## string_xrefs

- `0x180090ddb`: `MsmqRootPath`
- `0x180090f9c`: `LogDataCreated`
- `0x180090ea9`: `writer/mqwriter`
- `0x180091014`: `writer/mqwriter`
- `0x180090d83`: `RestoreComponents`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMsmqVssWriter::HandleRestoreThread(CMsmqVssWriter *Parameter)
{
  __int64 v2; // rbx
  wchar_t *v3; // rbx
  int v4; // eax
  CMsmqVssWriter *v5; // rcx
  unsigned int v6; // edi
  unsigned int v8; // r9d
  int v9; // eax
  signed int v10; // eax
  void *v11; // r8
  int v12; // eax
  unsigned int v13; // r9d
  int v14; // eax
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h]
  const WCHAR *v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+60h] [rbp-A0h]
  __int64 v21; // [rsp+68h] [rbp-98h]
  int v22; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+78h] [rbp-88h]
  const wchar_t *v24; // [rsp+80h] [rbp-80h]
  int v25; // [rsp+88h] [rbp-78h]
  __int64 v26; // [rsp+90h] [rbp-70h]
  wchar_t *v27; // [rsp+98h] [rbp-68h]
  wchar_t v28[256]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = *((_QWORD *)Parameter + 4);
  v17 = 0;
  v18 = v2;
  v19 = L"RestoreComponents";
  v20 = 0;
  v21 = -2147483646;
  QueryValueInternal((struct RegEntry *)&v17);
  Block = 0;
  v22 = 1;
  v23 = v2;
  v24 = L"MsmqRootPath";
  v25 = 0;
  v26 = -2147483646;
  CmQueryValue((const struct RegEntry *)&v22, (wchar_t **)&Block);
  v3 = (wchar_t *)MmAllocate(0x20Au);
  v27 = v3;
  v4 = StringCchPrintfW(v3, 0x105u, L"%s\\%s", Block, L"Restore");
  if ( v4 < 0 )
  {
    v6 = (unsigned __int16)v4;
    free(v3);
    free(Block);
    return v6;
  }
  v16 = 0;
  v6 = CMsmqVssWriter::VerifyRestoreLocation(v5, v3, 0, &v16);
  if ( (v6 & 0x80000000) != 0 )
  {
    memset_0(v28, 0, sizeof(v28));
    v9 = CMsmqVssWriter::ConvertComponentsToNames(Parameter, v16, v28, v8);
    if ( v9 < 0 )
      LogMsgHR(v9, (wchar_t *)L"writer/mqwriter", 0x2ACu);
    EvReport(0xC00008BA, 2u, v3, v28);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_6af5f41940d83573eba81ec716aa4ffa_Traceguids, v6);
LABEL_10:
    v6 = (unsigned __int16)v6;
    free(v3);
    free(Block);
    return v6;
  }
  v10 = CMsmqVssWriter::RestoreServiceComponents(Parameter, 0, v3);
  v6 = v10;
  if ( v10 < 0 )
  {
    EvReportWithError(0xC00008B5, v10, 1u, v3);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_6af5f41940d83573eba81ec716aa4ffa_Traceguids, v6);
    goto LABEL_10;
  }
  CmDeleteValue((const struct RegEntry *)&v17);
  DeleteFalconKeyValue(L"LogDataCreated");
  v12 = CMsmqVssWriter::DeleteRestoreFiles(Parameter, v3, v11);
  if ( v12 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_6af5f41940d83573eba81ec716aa4ffa_Traceguids,
      (unsigned int)v12);
  memset_0(v28, 0, sizeof(v28));
  v14 = CMsmqVssWriter::ConvertComponentsToNames(Parameter, 0, v28, v13);
  if ( v14 < 0 )
    LogMsgHR(v14, (wchar_t *)L"writer/mqwriter", 0x2AEu);
  EvReport(0x400008B8u, 2u, v3, v28);
  free(v3);
  free(Block);
  return 0;
}

```

## disassembly

```asm
0x180090d40  mov     [rsp-8+arg_8], rbx
0x180090d45  mov     [rsp-8+arg_10], rdi
0x180090d4a  push    rbp
0x180090d4b  push    r12
0x180090d4d  push    r14
0x180090d4f  lea     rbp, [rsp-1B0h]
0x180090d57  sub     rsp, 2B0h
0x180090d5e  mov     rax, cs:__security_cookie
0x180090d65  xor     rax, rsp
0x180090d68  mov     [rbp+1C0h+var_20], rax
0x180090d6f  mov     r14, rcx
0x180090d72  mov     rbx, [rcx+20h]
0x180090d76  mov     [rsp+2C0h+var_278], 0
0x180090d7e  mov     [rsp+2C0h+var_270], rbx
0x180090d83  lea     rax, aRestorecompone; "RestoreComponents"
0x180090d8a  mov     [rsp+2C0h+var_268], rax
0x180090d8f  mov     [rsp+2C0h+var_260], 0
0x180090d97  mov     rdi, 0FFFFFFFF80000002h
0x180090d9e  mov     [rsp+2C0h+var_258], rdi
0x180090da3  mov     [rsp+2C0h+var_290], 0
0x180090dab  mov     edx, 4
0x180090db0  mov     r9d, edx
0x180090db3  lea     r8, [rsp+2C0h+var_290]
0x180090db8  lea     rcx, [rsp+2C0h+var_278]; struct RegEntry *
0x180090dbd  call    QueryValueInternal
0x180090dc2  mov     [rsp+2C0h+Block], 0
0x180090dcb  mov     r12d, 1
0x180090dd1  mov     [rsp+2C0h+var_250], r12d
0x180090dd6  mov     [rsp+2C0h+var_248], rbx
0x180090ddb  lea     rax, aMsmqrootpath; "MsmqRootPath"
0x180090de2  mov     [rbp+1C0h+var_240], rax
0x180090de6  mov     [rbp+1C0h+var_238], 0
0x180090ded  mov     [rbp+1C0h+var_230], rdi
0x180090df1  lea     rdx, [rsp+2C0h+Block]; wchar_t **
0x180090df6  lea     rcx, [rsp+2C0h+var_250]; struct RegEntry *
0x180090dfb  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAPEA_W@Z; CmQueryValue(RegEntry const &,wchar_t * *)
0x180090e00  mov     ecx, 20Ah; unsigned __int64
0x180090e05  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180090e0a  mov     rbx, rax
0x180090e0d  mov     [rbp+1C0h+var_228], rax
0x180090e11  lea     rax, aRestore; "Restore"
0x180090e18  mov     [rsp+2C0h+var_2A0], rax
0x180090e1d  mov     r9, [rsp+2C0h+Block]
0x180090e22  lea     r8, aSS_3; "%s\\%s"
0x180090e29  mov     edx, 105h; unsigned __int64
0x180090e2e  mov     rcx, rbx; wchar_t *
0x180090e31  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180090e36  test    eax, eax
0x180090e38  jns     short loc_180090E5A
0x180090e3a  movzx   edi, ax
0x180090e3d  mov     rcx, rbx; Block
0x180090e40  call    cs:__imp_free
0x180090e46  nop
0x180090e47  mov     rcx, [rsp+2C0h+Block]; Block
0x180090e4c  call    cs:__imp_free
0x180090e52  nop
0x180090e53  mov     eax, edi
0x180090e55  jmp     loc_180091051
0x180090e5a  mov     [rsp+2C0h+var_280], 0
0x180090e62  lea     r9, [rsp+2C0h+var_280]; unsigned int *
0x180090e67  mov     r8d, [rsp+2C0h+var_290]; unsigned int
0x180090e6c  mov     rdx, rbx; wchar_t *
0x180090e6f  call    ?VerifyRestoreLocation@CMsmqVssWriter@@AEAAJPEB_WKPEAK@Z; CMsmqVssWriter::VerifyRestoreLocation(wchar_t const *,ulong,ulong *)
0x180090e74  mov     edi, eax
0x180090e76  test    eax, eax
0x180090e78  jns     loc_180090F1C
0x180090e7e  xor     edx, edx; Val
0x180090e80  mov     r8d, 200h; Size
0x180090e86  lea     rcx, [rbp+1C0h+var_220]; void *
0x180090e8a  call    memset_0
0x180090e8f  lea     r8, [rbp+1C0h+var_220]; wchar_t *
0x180090e93  mov     edx, [rsp+2C0h+var_280]; unsigned int
0x180090e97  mov     rcx, r14; this
0x180090e9a  call    ?ConvertComponentsToNames@CMsmqVssWriter@@AEAAJKPEA_WK@Z; CMsmqVssWriter::ConvertComponentsToNames(ulong,wchar_t *,ulong)
0x180090e9f  test    eax, eax
0x180090ea1  jns     short loc_180090EB7
0x180090ea3  mov     r8d, 2ACh; unsigned __int16
0x180090ea9  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180090eb0  mov     ecx, eax; int
0x180090eb2  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180090eb7  mov     edx, 2; unsigned __int16
0x180090ebc  lea     r9, [rbp+1C0h+var_220]
0x180090ec0  mov     r8, rbx
0x180090ec3  mov     ecx, 0C00008BAh; unsigned int
0x180090ec8  call    ?EvReport@@YAXKGZZ; EvReport(ulong,ushort,...)
0x180090ecd  lea     rax, WPP_GLOBAL_Control
0x180090ed4  mov     rcx, cs:WPP_GLOBAL_Control
0x180090edb  cmp     rcx, rax
0x180090ede  jz      short loc_180090EFE
0x180090ee0  test    [rcx+1Ch], r12b
0x180090ee4  jz      short loc_180090EFE
0x180090ee6  mov     edx, 0Fh
0x180090eeb  mov     r9d, edi
0x180090eee  lea     r8, WPP_6af5f41940d83573eba81ec716aa4ffa_Traceguids
0x180090ef5  mov     rcx, [rcx+10h]
0x180090ef9  call    WPP_SF_d
0x180090efe  movzx   edi, di
0x180090f01  mov     rcx, rbx; Block
0x180090f04  call    cs:__imp_free
0x180090f0a  nop
0x180090f0b  mov     rcx, [rsp+2C0h+Block]; Block
0x180090f10  call    cs:__imp_free
0x180090f16  nop
0x180090f17  jmp     loc_180090E53
0x180090f1c  mov     r8, rbx; wchar_t *
0x180090f1f  mov     edx, [rsp+2C0h+var_290]; unsigned int
0x180090f23  mov     rcx, r14; this
0x180090f26  call    ?RestoreServiceComponents@CMsmqVssWriter@@AEAAJKPEB_W@Z; CMsmqVssWriter::RestoreServiceComponents(ulong,wchar_t const *)
0x180090f2b  mov     edi, eax
0x180090f2d  test    eax, eax
0x180090f2f  jns     short loc_180090F92
0x180090f31  mov     r9, rbx
0x180090f34  mov     r8d, r12d; unsigned __int16
0x180090f37  mov     edx, eax; dwMessageId
0x180090f39  mov     ecx, 0C00008B5h; unsigned int
0x180090f3e  call    ?EvReportWithError@@YAXKJGZZ; EvReportWithError(ulong,long,ushort,...)
0x180090f43  lea     rax, WPP_GLOBAL_Control
0x180090f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180090f51  cmp     rcx, rax
0x180090f54  jz      short loc_180090F74
0x180090f56  test    [rcx+1Ch], r12b
0x180090f5a  jz      short loc_180090F74
0x180090f5c  mov     edx, 10h
0x180090f61  mov     r9d, edi
0x180090f64  lea     r8, WPP_6af5f41940d83573eba81ec716aa4ffa_Traceguids
0x180090f6b  mov     rcx, [rcx+10h]
0x180090f6f  call    WPP_SF_d
0x180090f74  movzx   edi, di
0x180090f77  mov     rcx, rbx; Block
0x180090f7a  call    cs:__imp_free
0x180090f80  nop
0x180090f81  mov     rcx, [rsp+2C0h+Block]; Block
0x180090f86  call    cs:__imp_free
0x180090f8c  nop
0x180090f8d  jmp     loc_180090E53
0x180090f92  lea     rcx, [rsp+2C0h+var_278]; struct RegEntry *
0x180090f97  call    ?CmDeleteValue@@YAXAEBVRegEntry@@@Z; CmDeleteValue(RegEntry const &)
0x180090f9c  lea     rcx, aLogdatacreated; "LogDataCreated"
0x180090fa3  call    cs:__imp_?DeleteFalconKeyValue@@YAJPEB_W@Z; DeleteFalconKeyValue(wchar_t const *)
0x180090fa9  mov     rdx, rbx; wchar_t *
0x180090fac  mov     rcx, r14; this
0x180090faf  call    ?DeleteRestoreFiles@CMsmqVssWriter@@AEAAJPEB_WPEAX@Z; CMsmqVssWriter::DeleteRestoreFiles(wchar_t const *,void *)
0x180090fb4  mov     r9d, eax
0x180090fb7  test    eax, eax
0x180090fb9  jns     short loc_180090FE9
0x180090fbb  lea     rax, WPP_GLOBAL_Control
0x180090fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180090fc9  cmp     rcx, rax
0x180090fcc  jz      short loc_180090FE9
0x180090fce  test    [rcx+1Ch], r12b
0x180090fd2  jz      short loc_180090FE9
0x180090fd4  mov     edx, 11h
0x180090fd9  lea     r8, WPP_6af5f41940d83573eba81ec716aa4ffa_Traceguids
0x180090fe0  mov     rcx, [rcx+10h]
0x180090fe4  call    WPP_SF_d
0x180090fe9  xor     edx, edx; Val
0x180090feb  mov     r8d, 200h; Size
0x180090ff1  lea     rcx, [rbp+1C0h+var_220]; void *
0x180090ff5  call    memset_0
0x180090ffa  lea     r8, [rbp+1C0h+var_220]; wchar_t *
0x180090ffe  mov     edx, [rsp+2C0h+var_290]; unsigned int
0x180091002  mov     rcx, r14; this
0x180091005  call    ?ConvertComponentsToNames@CMsmqVssWriter@@AEAAJKPEA_WK@Z; CMsmqVssWriter::ConvertComponentsToNames(ulong,wchar_t *,ulong)
0x18009100a  test    eax, eax
0x18009100c  jns     short loc_180091022
0x18009100e  mov     r8d, 2AEh; unsigned __int16
0x180091014  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18009101b  mov     ecx, eax; int
0x18009101d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180091022  mov     edx, 2; unsigned __int16
0x180091027  lea     r9, [rbp+1C0h+var_220]
0x18009102b  mov     r8, rbx
0x18009102e  mov     ecx, 400008B8h; unsigned int
0x180091033  call    ?EvReport@@YAXKGZZ; EvReport(ulong,ushort,...)
0x180091038  nop
0x180091039  mov     rcx, rbx; Block
0x18009103c  call    cs:__imp_free
0x180091042  nop
0x180091043  mov     rcx, [rsp+2C0h+Block]; Block
0x180091048  call    cs:__imp_free
0x18009104e  nop
0x18009104f  xor     eax, eax
0x180091051  mov     rcx, [rbp+1C0h+var_20]
0x180091058  xor     rcx, rsp; StackCookie
0x18009105b  call    __security_check_cookie
0x180091060  lea     r11, [rsp+2C0h+var_10]
0x180091068  mov     rbx, [r11+28h]
0x18009106c  mov     rdi, [r11+30h]
0x180091070  mov     rsp, r11
0x180091073  pop     r14
0x180091075  pop     r12
0x180091077  pop     rbp
0x180091078  retn
```
