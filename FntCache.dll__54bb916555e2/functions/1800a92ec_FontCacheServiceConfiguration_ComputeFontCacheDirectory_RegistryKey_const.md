# FontCacheServiceConfiguration::ComputeFontCacheDirectory(RegistryKey const &)

- ea: `0x1800a92ec`
- end: `0x1800a9531`
- name: `?ComputeFontCacheDirectory@FontCacheServiceConfiguration@@AEAA?AVRefString@DWrite@@AEBVRegistryKey@@@Z`
- size: `581`
- prototype: `struct DWrite::RefString::Data *__fastcall(__int64, struct DWrite::RefString::Data *, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b0b54`

## callees

- `0x18000e920`
- `0x18000f7bc`
- `0x180028c50`
- `0x18004d664`
- `0x18008e180`
- `0x1800a92ec`
- `0x1800a9538`
- `0x1800a98e0`
- `0x1800aa650`
- `0x1800ab180`
- `0x1800b0a5c`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a934f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a934f`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x1800a9390`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x1800a9390`

## string_xrefs

- `0x1800a943a`: `FontCachePath`

## pseudocode

```c
struct DWrite::RefString::Data *__fastcall FontCacheServiceConfiguration::ComputeFontCacheDirectory(
        __int64 a1,
        struct DWrite::RefString::Data *a2,
        _QWORD *a3)
{
  const char *v6; // rdx
  signed int ServiceDirectory; // r9d
  struct DWrite::RefString::Data *v8; // rbx
  int v9; // edx
  _WORD *v10; // rax
  __int64 v11; // rcx
  bool v12; // zf
  volatile signed __int32 **v13; // rax
  char v14; // di
  volatile signed __int32 *v15; // rax
  char v16; // di
  struct DWrite::RefString::Data *v18; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD *v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h]
  _BYTE *v21; // [rsp+48h] [rbp-B8h]
  __int64 v22; // [rsp+50h] [rbp-B0h]
  __int16 v23; // [rsp+58h] [rbp-A8h]
  struct DWrite::RefString::Data *v24; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+68h] [rbp-98h]
  struct DWrite::RefString::Data *v26; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v27[2]; // [rsp+78h] [rbp-88h] BYREF
  __int16 v28; // [rsp+80h] [rbp-80h]
  _BYTE v29[528]; // [rsp+90h] [rbp-70h] BYREF

  v24 = a2;
  v25 = 0;
  v27[0] = 6029404;
  v27[1] = 6029375;
  v28 = 0;
  if ( *(_QWORD *)(a1 + 32) && (unsigned __int8)RtlIsStateSeparationEnabled() )
  {
    memset_0(v29, 0, 0x208u);
    LODWORD(v18) = 0;
    ServiceDirectory = GetServiceDirectory(*(_QWORD *)(a1 + 32), 0, v29, 260, &v18);
    if ( !ServiceDirectory )
    {
      if ( !(_DWORD)v18 )
      {
        FailAssert(0x15Bu, v6);
        __debugbreak();
      }
      v19 = v27;
      v20 = 4;
      v21 = v29;
      v22 = (unsigned int)((_DWORD)v18 - 1);
      v23 = 92;
      DWrite::RefString::RefString(a2, &v19);
      return a2;
    }
    if ( ServiceDirectory > 0 )
      ServiceDirectory = (unsigned __int16)ServiceDirectory | 0x80070000;
    EventLogger::LogEvent<long,EventTag,unsigned int>(
      a1 + 16,
      1718513475,
      1869771365,
      ServiceDirectory,
      0x68746150637653LL,
      354);
  }
  if ( !*a3 )
  {
LABEL_21:
    ComputeFontCacheDirectoryFromProfile((__int64)a2);
    return a2;
  }
  RegistryKey::TryGetString(a3, &v18, L"FontCachePath");
  v8 = v18;
  v9 = *((_DWORD *)v18 + 1);
  if ( !v9 )
  {
    DWrite::RefString::DecrementRef(v18);
    goto LABEL_21;
  }
  v10 = (_WORD *)DWrite::RefString::operator[](&v18, (unsigned int)(v9 - 1));
  v11 = *((unsigned int *)v8 + 1);
  v20 = 4;
  v22 = v11;
  v12 = *v10 == 92;
  v19 = v27;
  v21 = (char *)v8 + 8;
  if ( v12 )
  {
    v13 = (volatile signed __int32 **)DWrite::RefString::RefString(&v24, &v19);
    v14 = 2;
  }
  else
  {
    v23 = 92;
    v13 = (volatile signed __int32 **)DWrite::RefString::RefString(&v26, &v19);
    v14 = 4;
  }
  v15 = *v13;
  *(_QWORD *)a2 = v15;
  _InterlockedIncrement(v15);
  v16 = v14 | 1;
  if ( (v16 & 4) != 0 )
  {
    v16 &= ~4u;
    DWrite::RefString::DecrementRef(v26);
  }
  if ( (v16 & 2) != 0 )
    DWrite::RefString::DecrementRef(v24);
  DWrite::RefString::DecrementRef(v8);
  return a2;
}

```

## disassembly

```asm
0x1800a92ec  push    rbp
0x1800a92ee  push    rbx
0x1800a92ef  push    rsi
0x1800a92f0  push    rdi
0x1800a92f1  push    r15
0x1800a92f3  lea     rbp, [rsp-1B0h]
0x1800a92fb  sub     rsp, 2B0h
0x1800a9302  mov     rax, cs:__security_cookie
0x1800a9309  xor     rax, rsp
0x1800a930c  mov     [rbp+1D0h+var_30], rax
0x1800a9313  mov     rbx, r8
0x1800a9316  mov     rsi, rdx
0x1800a9319  mov     rdi, rcx
0x1800a931c  mov     [rsp+2D0h+var_270], rdx
0x1800a9321  mov     [rsp+2D0h+var_268], 0
0x1800a9329  mov     r15d, 5Ch ; '\'
0x1800a932f  mov     [rsp+2D0h+var_258], 5C005Ch
0x1800a9337  mov     [rsp+2D0h+var_254], 5C003Fh
0x1800a933f  xor     eax, eax
0x1800a9341  mov     [rbp+1D0h+var_250], ax
0x1800a9345  cmp     [rcx+20h], rax
0x1800a9349  jz      loc_1800A9430
0x1800a934f  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800a9355  test    al, al
0x1800a9357  jz      loc_1800A9430
0x1800a935d  xor     edx, edx; Val
0x1800a935f  mov     r8d, 208h; Size
0x1800a9365  lea     rcx, [rbp+1D0h+var_240]; void *
0x1800a9369  call    memset_0
0x1800a936e  mov     dword ptr [rsp+2D0h+var_2A0], 0
0x1800a9376  lea     rax, [rsp+2D0h+var_2A0]
0x1800a937b  mov     [rsp+2D0h+var_2B0], rax
0x1800a9380  mov     r9d, 104h
0x1800a9386  lea     r8, [rbp+1D0h+var_240]
0x1800a938a  xor     edx, edx
0x1800a938c  mov     rcx, [rdi+20h]
0x1800a9390  call    cs:__imp_GetServiceDirectory
0x1800a9396  mov     r9d, eax
0x1800a9399  test    eax, eax
0x1800a939b  jnz     short loc_1800A93EC
0x1800a939d  mov     ecx, dword ptr [rsp+2D0h+var_2A0]
0x1800a93a1  test    ecx, ecx
0x1800a93a3  jnz     short loc_1800A93B0
0x1800a93a5  mov     ecx, 15Bh; unsigned int
0x1800a93aa  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x1800a93af  int     3; Trap to Debugger
0x1800a93b0  lea     rax, [rsp+2D0h+var_258]
0x1800a93b5  mov     [rsp+2D0h+var_298], rax
0x1800a93ba  mov     [rsp+2D0h+var_290], 4
0x1800a93c3  lea     rax, [rbp+1D0h+var_240]
0x1800a93c7  mov     [rsp+2D0h+var_288], rax
0x1800a93cc  lea     edx, [rcx-1]
0x1800a93cf  mov     [rsp+2D0h+var_280], rdx
0x1800a93d4  mov     [rsp+2D0h+var_278], r15w
0x1800a93da  lea     rdx, [rsp+2D0h+var_298]
0x1800a93df  mov     rcx, rsi
0x1800a93e2  call    ??$?0V?$StringSum@V?$StringSum@PEB_WPEB_W@@_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@V?$StringSum@PEB_WPEB_W@@_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<StringSum<wchar_t const *,wchar_t const *>,wchar_t>> const &)
0x1800a93e7  jmp     loc_1800A9511
0x1800a93ec  mov     rax, 68746150637653h
0x1800a93f6  test    r9d, r9d
0x1800a93f9  jle     short loc_1800A9406
0x1800a93fb  movzx   r9d, r9w
0x1800a93ff  or      r9d, 80070000h
0x1800a9406  mov     rdx, 6769666E6F43h
0x1800a9410  mov     r8, 726F727265h
0x1800a941a  lea     rcx, [rdi+10h]
0x1800a941e  mov     [rsp+2D0h+var_2A8], 162h
0x1800a9426  mov     [rsp+2D0h+var_2B0], rax
0x1800a942b  call    ??$LogEvent@JVEventTag@@I@EventLogger@@QEBAXVEventTag@@0J0I@Z; EventLogger::LogEvent<long,EventTag,uint>(EventTag,EventTag,long,EventTag,uint)
0x1800a9430  cmp     qword ptr [rbx], 0
0x1800a9434  jz      loc_1800A9509
0x1800a943a  lea     r8, aFontcachepath; "FontCachePath"
0x1800a9441  lea     rdx, [rsp+2D0h+var_2A0]
0x1800a9446  mov     rcx, rbx
0x1800a9449  call    ?TryGetString@RegistryKey@@QEBA?AVRefString@DWrite@@PEB_W@Z; RegistryKey::TryGetString(wchar_t const *)
0x1800a944e  nop
0x1800a944f  mov     rbx, [rsp+2D0h+var_2A0]
0x1800a9454  mov     edx, [rbx+4]
0x1800a9457  test    edx, edx
0x1800a9459  jz      loc_1800A9501
0x1800a945f  dec     edx
0x1800a9461  lea     rcx, [rsp+2D0h+var_2A0]
0x1800a9466  call    ??ARefString@DWrite@@QEBAAEB_WI@Z; DWrite::RefString::operator[](uint)
0x1800a946b  mov     ecx, [rbx+4]
0x1800a946e  mov     [rsp+2D0h+var_290], 4
0x1800a9477  mov     [rsp+2D0h+var_280], rcx
0x1800a947c  cmp     [rax], r15w
0x1800a9480  lea     rax, [rsp+2D0h+var_258]
0x1800a9485  mov     [rsp+2D0h+var_298], rax
0x1800a948a  lea     rax, [rbx+8]
0x1800a948e  mov     [rsp+2D0h+var_288], rax
0x1800a9493  jnz     short loc_1800A94AC
0x1800a9495  lea     rdx, [rsp+2D0h+var_298]
0x1800a949a  lea     rcx, [rsp+2D0h+var_270]
0x1800a949f  call    ??$?0V?$StringSum@PEB_WPEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@PEB_WPEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<wchar_t const *,wchar_t const *>> const &)
0x1800a94a4  nop
0x1800a94a5  mov     edi, 2
0x1800a94aa  jmp     short loc_1800A94C6
0x1800a94ac  mov     [rsp+2D0h+var_278], r15w
0x1800a94b2  lea     rdx, [rsp+2D0h+var_298]
0x1800a94b7  lea     rcx, [rsp+2D0h+var_260]
0x1800a94bc  call    ??$?0V?$StringSum@V?$StringSum@PEB_WPEB_W@@_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@V?$StringSum@PEB_WPEB_W@@_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<StringSum<wchar_t const *,wchar_t const *>,wchar_t>> const &)
0x1800a94c1  mov     edi, 4
0x1800a94c6  mov     rax, [rax]
0x1800a94c9  mov     [rsi], rax
0x1800a94cc  lock inc dword ptr [rax]
0x1800a94cf  or      edi, 1
0x1800a94d2  test    dil, 4
0x1800a94d6  jz      short loc_1800A94E6
0x1800a94d8  and     edi, 0FFFFFFFBh
0x1800a94db  mov     rcx, [rsp+2D0h+var_260]; struct DWrite::RefString::Data *
0x1800a94e0  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a94e5  nop
0x1800a94e6  test    dil, 2
0x1800a94ea  jz      short loc_1800A94F7
0x1800a94ec  mov     rcx, [rsp+2D0h+var_270]; struct DWrite::RefString::Data *
0x1800a94f1  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a94f6  nop
0x1800a94f7  mov     rcx, rbx; struct DWrite::RefString::Data *
0x1800a94fa  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a94ff  jmp     short loc_1800A9511
0x1800a9501  mov     rcx, rbx; struct DWrite::RefString::Data *
0x1800a9504  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a9509  mov     rcx, rsi
0x1800a950c  call    ?ComputeFontCacheDirectoryFromProfile@@YA?AVRefString@DWrite@@XZ; ComputeFontCacheDirectoryFromProfile(void)
0x1800a9511  mov     rax, rsi
0x1800a9514  mov     rcx, [rbp+1D0h+var_30]
0x1800a951b  xor     rcx, rsp; StackCookie
0x1800a951e  call    __security_check_cookie
0x1800a9523  add     rsp, 2B0h
0x1800a952a  pop     r15
0x1800a952c  pop     rdi
0x1800a952d  pop     rsi
0x1800a952e  pop     rbx
0x1800a952f  pop     rbp
0x1800a9530  retn
```
