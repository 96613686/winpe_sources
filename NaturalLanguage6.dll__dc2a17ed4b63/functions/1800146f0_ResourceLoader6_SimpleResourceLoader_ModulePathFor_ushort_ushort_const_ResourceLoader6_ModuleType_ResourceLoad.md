# ResourceLoader6::SimpleResourceLoader::ModulePathFor(ushort,ushort const *,ResourceLoader6::ModuleType,ResourceLoader6::__MIDL___MIDL_itf_ILoadResources_0006_0001_0001 *)

- ea: `0x1800146f0`
- end: `0x180014be6`
- name: `?ModulePathFor@SimpleResourceLoader@ResourceLoader6@@MEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GPEBGW4ModuleType@2@PEAU__MIDL___MIDL_itf_ILoadResources_0006_0001_0001@2@@Z`
- size: `1270`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned __int16, const unsigned __int16 *, unsigned int, IID *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004aa70`

## callees

- `0x18001409c`
- `0x1800145b4`
- `0x1800146f0`
- `0x180014bec`
- `0x180014cf0`
- `0x180014d28`
- `0x180014ebc`
- `0x180014f2c`
- `0x1800162e4`
- `0x180017858`
- `0x1800325e8`
- `0x180035640`
- `0x18003ed6c`
- `0x18009e300`
- `0x18009e3c0`
- `0x1800b0010`

## import_xrefs

- `msvcrt!fclose` at `0x180014b03`
- `msvcrt!fclose` at `0x180014b2f`
- `msvcrt!fclose` at `0x180014b03`
- `msvcrt!fclose` at `0x180014b2f`
- `msvcrt!fgetws` at `0x180014af5`
- `msvcrt!fgetws` at `0x180014af5`
- `msvcrt!_wfopen` at `0x180014ab2`
- `msvcrt!_wfopen` at `0x180014ab2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800148ed`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001492b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014ba1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800148ed`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001492b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014ba1`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180014b3f`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180014b3f`

## pseudocode

```c
__int64 __fastcall ResourceLoader6::SimpleResourceLoader::ModulePathFor(
        _QWORD *a1,
        __int64 a2,
        unsigned __int16 a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        IID *a6)
{
  IID *v10; // rcx
  unsigned __int64 v11; // r11
  unsigned __int64 i; // rsi
  char v13; // r12
  int v14; // eax
  __int64 v15; // r11
  __int64 v16; // r8
  __int64 v17; // rcx
  char v18; // al
  unsigned __int16 v19; // ax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  const wchar_t *v25; // rcx
  FILE *v26; // rax
  FILE *v27; // rdi
  HRESULT v28; // eax
  __int64 v29; // [rsp+20h] [rbp-E0h]
  void *v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v31; // [rsp+70h] [rbp-90h]
  unsigned __int64 v32; // [rsp+78h] [rbp-88h]
  void *pExceptionObject[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v34; // [rsp+90h] [rbp-70h]
  unsigned __int64 v35; // [rsp+98h] [rbp-68h]
  wchar_t *FileName[4]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v37[128]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v38[512]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v39[512]; // [rsp+5E0h] [rbp+4E0h] BYREF
  wchar_t Buffer[1024]; // [rsp+9E0h] [rbp+8E0h] BYREF
  const void *retaddr; // [rsp+1238h] [rbp+1138h]

  v10 = a6;
  v11 = 0;
  v37[0] = 0;
  if ( a4 )
  {
    StringCchCopyW(v37, 0x80u, a4);
    v37[127] = v11;
    v10 = a6;
  }
  while ( 2 )
  {
    for ( i = v11; i < (__int64)(a1[3] - a1[2]) >> 5; ++i )
    {
      v13 = 1;
      if ( !a4 )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, unsigned __int16 *, __int64, IID *))(*a1 + 120LL))(
                a1,
                a3,
                a5,
                v37,
                128,
                v10);
        v11 = 0;
      }
      v32 = 7;
      v31 = v11;
      LOWORD(v30[0]) = v11;
      std::wstring::assign(v30, 32 * i + a1[2], 0, -1);
      if ( v13 )
      {
        LODWORD(v29) = a5;
        v14 = StringCchPrintfW(v38, 0x200u, L"%04x\\%04x\\%s", a3, v29, v37);
        v15 = 0;
        if ( v14 < 0 )
        {
          CNLException::CNLException((CNLException *)pExceptionObject, -2147467259, retaddr);
          throw (CNLException *)pExceptionObject;
        }
      }
      else if ( StringCchCopyW(v38, 0x200u, v37) < 0 )
      {
        CNLException::CNLException((CNLException *)pExceptionObject, -2147467259, retaddr);
        throw (CNLException *)pExceptionObject;
      }
      v35 = 7;
      v34 = v15;
      LOWORD(pExceptionObject[0]) = v15;
      if ( v38[0] == (_WORD)v15 )
      {
        v16 = v15;
      }
      else
      {
        v16 = -1;
        do
          ++v16;
        while ( v38[v16] != (_WORD)v15 );
      }
      std::wstring::assign(pExceptionObject, v38, v16);
      std::wstring::append(v30, pExceptionObject, 0, -1);
      if ( v35 >= 8 )
        operator delete(pExceptionObject[0]);
      v35 = 7;
      v34 = 0;
      LOWORD(pExceptionObject[0]) = 0;
      v18 = ResourceLoader6::SimpleResourceLoader::Exists(v17, v30);
      v11 = 0;
      if ( v18 )
      {
        if ( a6 )
        {
          std::wstring::wstring(FileName, 32 * i + a1[2]);
          if ( v13 )
          {
            LODWORD(v29) = a5;
            if ( StringCchPrintfW(v39, 0x200u, L"%04x\\%04x\\%s", a3, v29, L"GUID.txt") < 0 )
            {
              CNLException::CNLException((CNLException *)pExceptionObject, -2147467259, retaddr);
              throw (CNLException *)pExceptionObject;
            }
          }
          else if ( StringCchCopyW(v39, 0x200u, L"GUID.txt") < 0 )
          {
            CNLException::CNLException((CNLException *)pExceptionObject, -2147467259, retaddr);
            throw (CNLException *)pExceptionObject;
          }
          v21 = std::wstring::wstring(pExceptionObject, v39);
          std::wstring::append(FileName, v21, 0, -1);
          LOBYTE(v22) = 1;
          std::wstring::_Tidy(pExceptionObject, v22, 0);
          if ( (unsigned __int8)ResourceLoader6::SimpleResourceLoader::Exists(v23, FileName) )
          {
            v25 = (const wchar_t *)FileName;
            if ( FileName[3] >= (wchar_t *)8 )
              v25 = FileName[0];
            v26 = _wfopen(v25, L"r");
            v27 = v26;
            if ( !v26 )
            {
              CNLException::CNLException((CNLException *)pExceptionObject, -2147467259, retaddr);
              throw (CNLException *)pExceptionObject;
            }
            if ( !fgetws(Buffer, 1024, v26) )
            {
              fclose(v27);
              CNLException::CNLException((CNLException *)pExceptionObject, -2147467259, retaddr);
              throw (CNLException *)pExceptionObject;
            }
            fclose(v27);
            v28 = IIDFromString(Buffer, a6);
            if ( v28 < 0 )
            {
              CNLException::CNLException((CNLException *)pExceptionObject, v28, retaddr);
              throw (CNLException *)pExceptionObject;
            }
          }
          LOBYTE(v24) = 1;
          std::wstring::_Tidy(FileName, v24, 0);
        }
        std::wstring::wstring(a2, v30);
        if ( v32 >= 8 )
          operator delete(v30[0]);
        v32 = 7;
        v31 = 0;
        LOWORD(v30[0]) = 0;
        return a2;
      }
      if ( v32 >= 8 )
      {
        operator delete(v30[0]);
        v11 = 0;
      }
      v32 = 7;
      v31 = 0;
      LOWORD(v30[0]) = 0;
      v10 = a6;
    }
    v19 = a3;
    a3 &= 0x3FFu;
    if ( a3 != v19 )
      continue;
    break;
  }
  *(_QWORD *)(a2 + 24) = 7;
  *(_QWORD *)(a2 + 16) = v11;
  *(_WORD *)a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x1800146f0  push    rbp
0x1800146f2  push    rbx
0x1800146f3  push    rsi
0x1800146f4  push    rdi
0x1800146f5  push    r12
0x1800146f7  push    r13
0x1800146f9  push    r14
0x1800146fb  push    r15
0x1800146fd  lea     rbp, [rsp-10F8h]
0x180014705  mov     eax, 11F8h
0x18001470a  call    _alloca_probe
0x18001470f  sub     rsp, rax
0x180014712  mov     [rsp+1230h+var_11E0], 0FFFFFFFFFFFFFFFEh
0x18001471b  mov     rax, cs:__security_cookie
0x180014722  xor     rax, rsp
0x180014725  mov     [rbp+1130h+var_50], rax
0x18001472c  mov     r15, r9
0x18001472f  movzx   edi, r8w
0x180014733  mov     rbx, rdx
0x180014736  mov     r14, rcx
0x180014739  mov     [rsp+1230h+var_11D8], rdx
0x18001473e  mov     rcx, [rbp+1130h+arg_28]
0x180014745  mov     [rsp+1230h+lpiid], rcx
0x18001474a  xor     r11d, r11d
0x18001474d  mov     [rsp+1230h+var_11F0], r11d
0x180014752  mov     [rbp+1130h+var_1150], r11w
0x180014757  test    r9, r9
0x18001475a  jz      short loc_18001477A
0x18001475c  mov     r8, r9; unsigned __int16 *
0x18001475f  mov     edx, 80h; unsigned __int64
0x180014764  lea     rcx, [rbp+1130h+var_1150]; unsigned __int16 *
0x180014768  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001476d  mov     [rbp+1130h+var_1052], r11w
0x180014775  mov     rcx, [rsp+1230h+lpiid]
0x18001477a  mov     rsi, r11
0x18001477d  mov     rax, [r14+18h]
0x180014781  sub     rax, [r14+10h]
0x180014785  sar     rax, 5
0x180014789  cmp     rsi, rax
0x18001478c  jnb     loc_180014955
0x180014792  mov     r12b, 1
0x180014795  test    r15, r15
0x180014798  jnz     short loc_1800147CB
0x18001479a  mov     rax, [r14]
0x18001479d  mov     [rsp+1230h+var_1208], rcx
0x1800147a2  mov     [rsp+1230h+var_1210], 80h
0x1800147ab  lea     r9, [rbp+1130h+var_1150]
0x1800147af  mov     r8d, [rbp+1130h+arg_20]
0x1800147b6  movzx   edx, di
0x1800147b9  mov     rcx, r14
0x1800147bc  mov     rax, [rax+78h]
0x1800147c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147c5  mov     r12b, al
0x1800147c8  xor     r11d, r11d
0x1800147cb  mov     r13, rsi
0x1800147ce  shl     r13, 5
0x1800147d2  mov     [rsp+1230h+var_11C0], r11
0x1800147d7  mov     [rsp+1230h+var_11B8], r11
0x1800147dc  mov     [rsp+1230h+var_11B8], 7
0x1800147e5  mov     [rsp+1230h+var_11C0], r11
0x1800147ea  mov     word ptr [rsp+1230h+var_11D0], r11w
0x1800147f0  mov     rdx, [r14+10h]
0x1800147f4  add     rdx, r13
0x1800147f7  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800147fb  xor     r8d, r8d
0x1800147fe  lea     rcx, [rsp+1230h+var_11D0]
0x180014803  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180014808  nop
0x180014809  xor     r11d, r11d
0x18001480c  mov     edx, 200h; unsigned __int64
0x180014811  lea     rcx, [rbp+1130h+var_1050]; unsigned __int16 *
0x180014818  test    r12b, r12b
0x18001481b  jz      short loc_18001486D
0x18001481d  movzx   r9d, di
0x180014821  lea     rax, [rbp+1130h+var_1150]
0x180014825  mov     [rsp+1230h+var_1208], rax
0x18001482a  mov     eax, [rbp+1130h+arg_20]
0x180014830  mov     dword ptr [rsp+1230h+var_1210], eax
0x180014834  lea     r8, a04x04xS; "%04x\\%04x\\%s"
0x18001483b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014840  xor     r11d, r11d
0x180014843  test    eax, eax
0x180014845  jns     short loc_18001487E
0x180014847  mov     r8, [rbp+1138h]; void *
0x18001484e  mov     edx, 80004005h; int
0x180014853  lea     rcx, [rbp+1130h+pExceptionObject]; this
0x180014857  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18001485c  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180014863  lea     rcx, [rbp+1130h+pExceptionObject]; pExceptionObject
0x180014867  call    _CxxThrowException_0
0x18001486d  lea     r8, [rbp+1130h+var_1150]; unsigned __int16 *
0x180014871  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014876  test    eax, eax
0x180014878  js      loc_180014BC0
0x18001487e  mov     [rbp+1130h+var_11A0], r11
0x180014882  mov     [rbp+1130h+var_1198], r11
0x180014886  mov     [rbp+1130h+var_1198], 7
0x18001488e  mov     [rbp+1130h+var_11A0], r11
0x180014892  mov     word ptr [rbp+1130h+pExceptionObject], r11w
0x180014897  cmp     [rbp+1130h+var_1050], r11w
0x18001489f  jnz     short loc_1800148A6
0x1800148a1  mov     r8, r11
0x1800148a4  jmp     short loc_1800148BB
0x1800148a6  lea     rax, [rbp+1130h+var_1050]
0x1800148ad  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800148b1  inc     r8
0x1800148b4  cmp     [rax+r8*2], r11w
0x1800148b9  jnz     short loc_1800148B1
0x1800148bb  lea     rdx, [rbp+1130h+var_1050]
0x1800148c2  lea     rcx, [rbp+1130h+pExceptionObject]
0x1800148c6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800148cb  nop
0x1800148cc  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800148d0  xor     r8d, r8d
0x1800148d3  lea     rdx, [rbp+1130h+pExceptionObject]
0x1800148d7  lea     rcx, [rsp+1230h+var_11D0]
0x1800148dc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800148e1  nop
0x1800148e2  cmp     [rbp+1130h+var_1198], 8
0x1800148e7  jb      short loc_1800148F3
0x1800148e9  mov     rcx, [rbp+1130h+pExceptionObject]
0x1800148ed  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800148f3  mov     [rbp+1130h+var_1198], 7
0x1800148fb  mov     [rbp+1130h+var_11A0], 0
0x180014903  xor     eax, eax
0x180014905  mov     word ptr [rbp+1130h+pExceptionObject], ax
0x180014909  lea     rdx, [rsp+1230h+var_11D0]
0x18001490e  call    ?Exists@SimpleResourceLoader@ResourceLoader6@@IEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ResourceLoader6::SimpleResourceLoader::Exists(std::wstring const &)
0x180014913  xor     r11d, r11d
0x180014916  test    al, al
0x180014918  jnz     loc_1800149A7
0x18001491e  cmp     [rsp+1230h+var_11B8], 8
0x180014924  jb      short loc_180014934
0x180014926  mov     rcx, [rsp+1230h+var_11D0]
0x18001492b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014931  xor     r11d, r11d
0x180014934  mov     [rsp+1230h+var_11B8], 7
0x18001493d  mov     [rsp+1230h+var_11C0], r11
0x180014942  mov     word ptr [rsp+1230h+var_11D0], r11w
0x180014948  inc     rsi
0x18001494b  mov     rcx, [rsp+1230h+lpiid]
0x180014950  jmp     loc_18001477D
0x180014955  movzx   eax, di
0x180014958  mov     edx, 3FFh
0x18001495d  and     di, dx
0x180014960  cmp     di, ax
0x180014963  jnz     loc_18001477A
0x180014969  mov     qword ptr [rbx+18h], 7
0x180014971  mov     [rbx+10h], r11
0x180014975  mov     [rbx], r11w
0x180014979  mov     [rsp+1230h+var_11F0], 1
0x180014981  mov     rax, rbx
0x180014984  mov     rcx, [rbp+1130h+var_50]
0x18001498b  xor     rcx, rsp; StackCookie
0x18001498e  call    __security_check_cookie
0x180014993  add     rsp, 11F8h
0x18001499a  pop     r15
0x18001499c  pop     r14
0x18001499e  pop     r13
0x1800149a0  pop     r12
0x1800149a2  pop     rdi
0x1800149a3  pop     rsi
0x1800149a4  pop     rbx
0x1800149a5  pop     rbp
0x1800149a6  retn
0x1800149a7  mov     rsi, [rsp+1230h+lpiid]
0x1800149ac  test    rsi, rsi
0x1800149af  jz      loc_180014B7C
0x1800149b5  mov     rdx, [r14+10h]
0x1800149b9  add     rdx, r13
0x1800149bc  lea     rcx, [rbp+1130h+FileName]
0x1800149c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800149c5  nop
0x1800149c6  xor     r14d, r14d
0x1800149c9  lea     r8, aGuidTxt; "GUID.txt"
0x1800149d0  mov     edx, 200h; unsigned __int64
0x1800149d5  lea     rcx, [rbp+1130h+var_C50]; unsigned __int16 *
0x1800149dc  test    r12b, r12b
0x1800149df  jz      short loc_180014A2A
0x1800149e1  movzx   r9d, di
0x1800149e5  mov     [rsp+1230h+var_1208], r8
0x1800149ea  mov     eax, [rbp+1130h+arg_20]
0x1800149f0  mov     dword ptr [rsp+1230h+var_1210], eax
0x1800149f4  lea     r8, a04x04xS; "%04x\\%04x\\%s"
0x1800149fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014a00  test    eax, eax
0x180014a02  jns     short loc_180014A59
0x180014a04  mov     r8, [rbp+1138h]; void *
0x180014a0b  mov     edx, 80004005h; int
0x180014a10  lea     rcx, [rbp+1130h+pExceptionObject]; this
0x180014a14  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180014a19  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180014a20  lea     rcx, [rbp+1130h+pExceptionObject]; pExceptionObject
0x180014a24  call    _CxxThrowException_0
0x180014a2a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014a2f  test    eax, eax
0x180014a31  jns     short loc_180014A59
0x180014a33  mov     r8, [rbp+1138h]; void *
0x180014a3a  mov     edx, 80004005h; int
0x180014a3f  lea     rcx, [rbp+1130h+pExceptionObject]; this
0x180014a43  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180014a48  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180014a4f  lea     rcx, [rbp+1130h+pExceptionObject]; pExceptionObject
0x180014a53  call    _CxxThrowException_0
0x180014a59  lea     rdx, [rbp+1130h+var_C50]
0x180014a60  lea     rcx, [rbp+1130h+pExceptionObject]
0x180014a64  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180014a69  nop
0x180014a6a  or      r9, 0FFFFFFFFFFFFFFFFh
0x180014a6e  xor     r8d, r8d
0x180014a71  mov     rdx, rax
0x180014a74  lea     rcx, [rbp+1130h+FileName]
0x180014a78  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180014a7d  nop
0x180014a7e  xor     r8d, r8d
0x180014a81  mov     dl, 1
0x180014a83  lea     rcx, [rbp+1130h+pExceptionObject]
0x180014a87  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014a8c  lea     rdx, [rbp+1130h+FileName]
0x180014a90  call    ?Exists@SimpleResourceLoader@ResourceLoader6@@IEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ResourceLoader6::SimpleResourceLoader::Exists(std::wstring const &)
0x180014a95  test    al, al
0x180014a97  jz      loc_180014B6C
0x180014a9d  lea     rcx, [rbp+1130h+FileName]
0x180014aa1  cmp     [rbp+1130h+var_1158], 8
0x180014aa6  cmovnb  rcx, [rbp+1130h+FileName]; FileName
0x180014aab  lea     rdx, aR; "r"
0x180014ab2  call    cs:__imp__wfopen
0x180014ab8  mov     rdi, rax
0x180014abb  test    rax, rax
0x180014abe  jnz     short loc_180014AE6
0x180014ac0  mov     r8, [rbp+1138h]; void *
0x180014ac7  mov     edx, 80004005h; int
0x180014acc  lea     rcx, [rbp+1130h+pExceptionObject]; this
0x180014ad0  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180014ad5  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180014adc  lea     rcx, [rbp+1130h+pExceptionObject]; pExceptionObject
0x180014ae0  call    _CxxThrowException_0
0x180014ae6  mov     r8, rdi; Stream
0x180014ae9  mov     edx, 400h; BufferCount
0x180014aee  lea     rcx, [rbp+1130h+Buffer]; Buffer
0x180014af5  call    cs:__imp_fgetws
0x180014afb  mov     rcx, rdi; Stream
0x180014afe  test    rax, rax
0x180014b01  jnz     short loc_180014B2F
0x180014b03  call    cs:__imp_fclose
0x180014b09  mov     r8, [rbp+1138h]; void *
0x180014b10  mov     edx, 80004005h; int
0x180014b15  lea     rcx, [rbp+1130h+pExceptionObject]; this
0x180014b19  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180014b1e  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180014b25  lea     rcx, [rbp+1130h+pExceptionObject]; pExceptionObject
0x180014b29  call    _CxxThrowException_0
0x180014b2f  call    cs:__imp_fclose
0x180014b35  mov     rdx, rsi; lpiid
0x180014b38  lea     rcx, [rbp+1130h+Buffer]; lpsz
0x180014b3f  call    cs:__imp_IIDFromString
0x180014b45  test    eax, eax
0x180014b47  jns     short loc_180014B6C
0x180014b49  mov     r8, [rbp+1138h]; void *
0x180014b50  mov     edx, eax; int
0x180014b52  lea     rcx, [rbp+1130h+pExceptionObject]; this
0x180014b56  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180014b5b  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180014b62  lea     rcx, [rbp+1130h+pExceptionObject]; pExceptionObject
0x180014b66  call    _CxxThrowException_0
0x180014b6c  xor     r8d, r8d
0x180014b6f  mov     dl, 1
0x180014b71  lea     rcx, [rbp+1130h+FileName]
0x180014b75  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014b7a  jmp     short loc_180014B7F
0x180014b7c  xor     r14d, r14d
0x180014b7f  lea     rdx, [rsp+1230h+var_11D0]
0x180014b84  mov     rcx, rbx
0x180014b87  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180014b8c  mov     [rsp+1230h+var_11F0], 1
0x180014b94  cmp     [rsp+1230h+var_11B8], 8
0x180014b9a  jb      short loc_180014BA7
0x180014b9c  mov     rcx, [rsp+1230h+var_11D0]
0x180014ba1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014ba7  mov     [rsp+1230h+var_11B8], 7
0x180014bb0  mov     [rsp+1230h+var_11C0], r14
0x180014bb5  mov     word ptr [rsp+1230h+var_11D0], r14w
0x180014bbb  jmp     loc_180014981
0x180014bc0  mov     r8, [rbp+1138h]; void *
0x180014bc7  mov     edx, 80004005h; int
0x180014bcc  lea     rcx, [rbp+1130h+pExceptionObject]; this
0x180014bd0  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180014bd5  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180014bdc  lea     rcx, [rbp+1130h+pExceptionObject]; pExceptionObject
0x180014be0  call    _CxxThrowException_0
```
