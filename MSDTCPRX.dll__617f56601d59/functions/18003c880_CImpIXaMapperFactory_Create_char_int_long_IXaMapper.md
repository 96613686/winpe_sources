# CImpIXaMapperFactory::Create(char *,int,long,IXaMapper * *)

- ea: `0x18003c880`
- end: `0x18003cebe`
- name: `?Create@CImpIXaMapperFactory@@UEAAJPEADHJPEAPEAUIXaMapper@@@Z`
- size: `1598`
- prototype: `__int64 __fastcall(CTmProxyCore **this, char *, int, int, struct IXaMapper **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000c080`
- `0x18001d138`
- `0x1800246c0`
- `0x18003c380`
- `0x18003c880`
- `0x18003cec4`
- `0x18003d164`
- `0x18003e13c`
- `0x180070f24`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `msvcrt!strnlen` at `0x18003cb13`
- `msvcrt!strnlen` at `0x18003cb13`
- `msvcrt!atoi` at `0x18003cafe`
- `msvcrt!atoi` at `0x18003cafe`
- `msvcrt!strtok` at `0x18003c9b5`
- `msvcrt!strtok` at `0x18003c9ed`
- `msvcrt!strtok` at `0x18003ca2b`
- `msvcrt!strtok` at `0x18003ca5b`
- `msvcrt!strtok` at `0x18003ca8b`
- `msvcrt!strtok` at `0x18003caa2`
- `msvcrt!strtok` at `0x18003c9b5`
- `msvcrt!strtok` at `0x18003c9ed`
- `msvcrt!strtok` at `0x18003ca2b`
- `msvcrt!strtok` at `0x18003ca5b`
- `msvcrt!strtok` at `0x18003ca8b`
- `msvcrt!strtok` at `0x18003caa2`
- `msvcrt!_stricmp` at `0x18003c9d1`
- `msvcrt!_stricmp` at `0x18003ca13`
- `msvcrt!_stricmp` at `0x18003ca43`
- `msvcrt!_stricmp` at `0x18003ca73`
- `msvcrt!_stricmp` at `0x18003cae8`
- `msvcrt!_stricmp` at `0x18003c9d1`
- `msvcrt!_stricmp` at `0x18003ca13`
- `msvcrt!_stricmp` at `0x18003ca43`
- `msvcrt!_stricmp` at `0x18003ca73`
- `msvcrt!_stricmp` at `0x18003cae8`

## string_xrefs

- `0x18003c93d`: `CImpIXaMapperFactory::Create`
- `0x18003cb63`: `CImpIXaMapperFactory::Create`
- `0x18003c94f`: `com\complus\dtc\dtc\msdtcprx\src\xamapper.cpp`
- `0x18003cb75`: `com\complus\dtc\dtc\msdtcprx\src\xamapper.cpp`
- `0x18003cc9a`: `Successfully created a new IXaMapper=%p`
- `0x18003ccd7`: `Failed to create a new IXaMapper`

## pseudocode

```c
__int64 __fastcall CImpIXaMapperFactory::Create(CTmProxyCore **this, char *a2, int a3, int a4, struct IXaMapper **a5)
{
  int v6; // r13d
  void *v7; // r9
  __int64 v9; // r14
  unsigned __int64 v10; // rax
  char *v11; // r15
  char *v12; // r12
  char *v13; // rdi
  char *v14; // rsi
  char *v15; // rbx
  struct CImpIXaMapper *AnXaMapper; // rax
  CImpIXaMapper *v17; // rax
  struct CImpIXaMapper *v18; // rcx
  struct CImpIXaMapper *v19; // rcx
  unsigned int v20; // esi
  size_t Size; // [rsp+28h] [rbp-D8h]
  size_t Sizec; // [rsp+28h] [rbp-D8h]
  size_t Sizea; // [rsp+28h] [rbp-D8h]
  size_t Sizeb; // [rsp+28h] [rbp-D8h]
  void *Src; // [rsp+38h] [rbp-C8h]
  struct CImpIXaMapper *v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+58h] [rbp-A8h]
  CImpIXaMapperFactory *v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+68h] [rbp-98h]
  char *v30; // [rsp+70h] [rbp-90h]
  char *v31; // [rsp+78h] [rbp-88h]
  struct IXaMapper **v32; // [rsp+80h] [rbp-80h]
  CImpIXaMapper *v33; // [rsp+88h] [rbp-78h]
  char String[3072]; // [rsp+90h] [rbp-70h] BYREF

  v27 = a3;
  v28 = (CImpIXaMapperFactory *)this;
  v32 = a5;
  v6 = 0;
  v26 = 0;
  if ( !a5 )
    return 2147942487LL;
  if ( !a2 || a4 )
  {
    *a5 = 0;
    return 2147942487LL;
  }
  *a5 = 0;
  if ( !(unsigned int)CTmProxyCore::GetXaTransactionsEnabled(this[1]) )
  {
    LODWORD(Size) = 0;
    DtcWriteToEventLoggerExW(2u, 5u, 0x80001309, v7, 0, Size, 0, 0, 1);
    LODWORD(Sizec) = 0;
    TraceStringInline(
      11,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\xamapper.cpp",
      213,
      L"CImpIXaMapperFactory::Create",
      Sizec,
      L"XA transactions not enabled");
    return 2147799078LL;
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  if ( v10 > 0xBFF )
    return 2147942487LL;
  v11 = 0;
  v30 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  TracedStringCchCopyA(String, 0xC00u, a2);
  v15 = strtok(String, "=, ");
  if ( !v15 )
    return 2147942487LL;
  do
  {
    if ( !_stricmp(v15, "TM") )
    {
      if ( !v11 )
      {
        v11 = strtok(0, "=, ");
        v30 = v11;
        if ( !v11 )
          return 2147942487LL;
      }
      goto LABEL_23;
    }
    if ( !_stricmp(v15, "RmRecoveryGuid") && !v12 )
    {
      v12 = strtok(0, "=, ");
      if ( !v12 )
        break;
    }
    if ( !_stricmp(v15, "Timeout") && !v13 )
    {
      v13 = strtok(0, "=, ");
      if ( !v13 )
        break;
    }
    if ( !_stricmp(v15, "BrIso") && !v14 )
    {
      v14 = strtok(0, "=, ");
      if ( !v14 )
        break;
    }
LABEL_23:
    v15 = strtok(0, "=, ");
  }
  while ( v15 );
  if ( !v11 || !v12 )
    return 2147942487LL;
  do
    ++v9;
  while ( v12[v9] );
  if ( v9 != 36 || v14 && _stricmp(v14, "Tight") )
    return 2147942487LL;
  if ( !v13 || (v6 = atoi(v13), v6 > 0) )
  {
LABEL_36:
    v29 = v14 != 0;
    TraceStringInline(
      11,
      4,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\xamapper.cpp",
      356,
      L"CImpIXaMapperFactory::Create",
      0,
      L"Finished parsing xa_info: dwTimeout=%d fTightlyCoupled=%d ",
      v6,
      v29);
    v31 = (char *)v28 + 48;
    (**((void (__fastcall ***)(char *))v28 + 6))((char *)v28 + 48);
    AnXaMapper = CImpIXaMapperFactory::FindAnXaMapper(v28, v27);
    v26 = AnXaMapper;
    if ( !AnXaMapper )
    {
      (*(void (__fastcall **)(CImpIXaMapperFactory *))(*(_QWORD *)v28 + 8LL))(v28);
      LODWORD(Src) = v27;
      TraceStringInline(
        11,
        4,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\xamapper.cpp",
        372,
        L"CImpIXaMapperFactory::Create",
        0,
        L"No existing IXaMapper for rmid=0x%x found",
        Src);
      v17 = (CImpIXaMapper *)operator new(0x128u);
      v33 = v17;
      if ( v17 )
        v18 = CImpIXaMapper::CImpIXaMapper(v17, v28, v30, v12, v27, v29);
      else
        v18 = 0;
      v26 = v18;
      if ( v18 )
      {
        (*(void (__fastcall **)(struct CImpIXaMapper *))(*(_QWORD *)v18 + 8LL))(v18);
        (*(void (__fastcall **)(struct CImpIXaMapper *))(*(_QWORD *)v26 + 8LL))(v26);
        (*(void (__fastcall **)(char *, struct CImpIXaMapper **))(*((_QWORD *)v28 + 2) + 16LL))((char *)v28 + 16, &v26);
        TraceStringInline(
          11,
          4,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\xamapper.cpp",
          386,
          L"CImpIXaMapperFactory::Create",
          0,
          L"Successfully created a new IXaMapper=%p",
          v26);
      }
      else
      {
        (*(void (__fastcall **)(CImpIXaMapperFactory *))(*(_QWORD *)v28 + 16LL))(v28);
        TraceStringInline(
          11,
          4,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\xamapper.cpp",
          392,
          L"CImpIXaMapperFactory::Create",
          0,
          L"Failed to create a new IXaMapper");
      }
      v19 = v26;
LABEL_44:
      if ( v19 )
      {
        TraceStringInline(
          11,
          4,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\xamapper.cpp",
          430,
          L"CImpIXaMapperFactory::Create",
          0,
          L"Initializing pCIXaMapper=%p",
          v19);
        v20 = CImpIXaMapper::Init(v26);
        if ( v20 )
        {
          LODWORD(Sizea) = v20;
          TraceStringInline(
            11,
            1,
            L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\xamapper.cpp",
            444,
            L"CImpIXaMapperFactory::Create",
            Sizea,
            L"Failed to initialize IXaMapper object");
          CImpIXaMapperFactory::RemoveFromList(v28, v26);
          (*(void (__fastcall **)(struct CImpIXaMapper *))(*(_QWORD *)v26 + 16LL))(v26);
          v26 = 0;
        }
        else
        {
          if ( v13 )
            *((_DWORD *)v26 + 31) = v6;
          *v32 = v26;
        }
      }
      else
      {
        v20 = -2147024882;
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v31 + 8LL))(v31);
      return v20;
    }
    TraceStringInline(
      11,
      4,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\xamapper.cpp",
      397,
      L"CImpIXaMapperFactory::Create",
      0,
      L"Found an existing IXaMapper=%p",
      AnXaMapper);
    v19 = v26;
    if ( *((_DWORD *)v26 + 9) )
    {
      if ( v14 )
        goto LABEL_44;
    }
    else if ( !v14 )
    {
      goto LABEL_44;
    }
    (*(void (**)(void))(*(_QWORD *)v26 + 16LL))();
    v26 = 0;
    LODWORD(Sizeb) = -2147024809;
    TraceStringInline(
      11,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\xamapper.cpp",
      414,
      L"CImpIXaMapperFactory::Create",
      Sizeb,
      L"Invalid arguments, releasing m_semexcForXaMapSet lock");
    (*(void (__fastcall **)(char *))(*(_QWORD *)v31 + 8LL))(v31);
    return 2147942487LL;
  }
  if ( strnlen(v13, 2u) && *v13 == 48 && !v13[1] )
  {
    v6 = 0;
    goto LABEL_36;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18003c880  mov     [rsp-8+arg_18], rbx
0x18003c885  push    rbp
0x18003c886  push    rsi
0x18003c887  push    rdi
0x18003c888  push    r12
0x18003c88a  push    r13
0x18003c88c  push    r14
0x18003c88e  push    r15
0x18003c890  lea     rbp, [rsp-0BA0h]
0x18003c898  sub     rsp, 0CA0h
0x18003c89f  mov     rax, cs:__security_cookie
0x18003c8a6  xor     rax, rsp
0x18003c8a9  mov     [rbp+0BD0h+var_40], rax
0x18003c8b0  mov     [rsp+0CD0h+var_C78], r8d
0x18003c8b5  mov     rbx, rdx
0x18003c8b8  mov     rax, rcx
0x18003c8bb  mov     [rsp+0CD0h+var_C70], rcx
0x18003c8c0  mov     rcx, [rbp+0BD0h+arg_20]
0x18003c8c7  mov     [rbp+0BD0h+var_C50], rcx
0x18003c8cb  xor     r13d, r13d
0x18003c8ce  mov     [rsp+0CD0h+var_C80], r13
0x18003c8d3  test    rcx, rcx
0x18003c8d6  jz      loc_18003CE8F
0x18003c8dc  test    rdx, rdx
0x18003c8df  jz      loc_18003CE8C
0x18003c8e5  test    r9d, r9d
0x18003c8e8  jnz     loc_18003CE8C
0x18003c8ee  mov     [rcx], r13
0x18003c8f1  mov     rcx, [rax+8]; this
0x18003c8f5  call    ?GetXaTransactionsEnabled@CTmProxyCore@@QEAAHXZ; CTmProxyCore::GetXaTransactionsEnabled(void)
0x18003c8fa  test    eax, eax
0x18003c8fc  jnz     short loc_18003C96C
0x18003c8fe  lea     edx, [rax+5]; unsigned __int16
0x18003c901  lea     ecx, [rax+2]; unsigned __int16
0x18003c904  mov     [rsp+0CD0h+var_C90], 1; int
0x18003c90c  mov     [rsp+0CD0h+Src], r13; Src
0x18003c911  mov     [rsp+0CD0h+var_CA0], r13; unsigned __int16 **
0x18003c916  mov     dword ptr [rsp+0CD0h+Size], r13d; Size
0x18003c91b  mov     [rsp+0CD0h+var_CB0], r13w; unsigned __int16
0x18003c921  mov     r8d, 80001309h; unsigned int
0x18003c927  call    ?DtcWriteToEventLoggerExW@@YAJGGKPEAXGKPEAPEBG0H@Z; DtcWriteToEventLoggerExW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)
0x18003c92c  lea     rax, aXaTransactions; "XA transactions not enabled"
0x18003c933  mov     [rsp+0CD0h+var_CA0], rax
0x18003c938  mov     dword ptr [rsp+0CD0h+Size], r13d
0x18003c93d  lea     r15, aCimpixamapperf; "CImpIXaMapperFactory::Create"
0x18003c944  mov     qword ptr [rsp+0CD0h+var_CB0], r15
0x18003c949  mov     r9d, 0D5h
0x18003c94f  lea     r8, aComComplusDtcD_16; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18003c956  lea     edx, [r13+1]
0x18003c95a  lea     ecx, [rdx+0Ah]
0x18003c95d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18003c962  mov     eax, 8004D026h
0x18003c967  jmp     loc_18003CE94
0x18003c96c  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003c970  mov     rax, r14
0x18003c973  inc     rax
0x18003c976  cmp     [rbx+rax], r13b
0x18003c97a  jnz     short loc_18003C973
0x18003c97c  cmp     rax, 0BFFh
0x18003c982  ja      loc_18003CE8F
0x18003c988  mov     r15, r13
0x18003c98b  mov     [rsp+0CD0h+var_C60], r13
0x18003c990  mov     r12, r13
0x18003c993  mov     rdi, r13
0x18003c996  mov     rsi, r13
0x18003c999  mov     r8, rbx; char *
0x18003c99c  mov     edx, 0C00h; unsigned __int64
0x18003c9a1  lea     rcx, [rbp+0BD0h+String]; char *
0x18003c9a5  call    ?TracedStringCchCopyA@@YAXPEAD_KPEBD@Z; TracedStringCchCopyA(char *,unsigned __int64,char const *)
0x18003c9aa  lea     rdx, Delimiter; "=, "
0x18003c9b1  lea     rcx, [rbp+0BD0h+String]; String
0x18003c9b5  call    cs:__imp_strtok
0x18003c9bb  mov     rbx, rax
0x18003c9be  test    rax, rax
0x18003c9c1  jz      loc_18003CE8F
0x18003c9c7  lea     rdx, String2; "TM"
0x18003c9ce  mov     rcx, rbx; String1
0x18003c9d1  call    cs:__imp__stricmp
0x18003c9d7  test    eax, eax
0x18003c9d9  jnz     short loc_18003CA09
0x18003c9db  test    r15, r15
0x18003c9de  jnz     loc_18003CA99
0x18003c9e4  lea     rdx, Delimiter; "=, "
0x18003c9eb  xor     ecx, ecx; String
0x18003c9ed  call    cs:__imp_strtok
0x18003c9f3  mov     r15, rax
0x18003c9f6  mov     [rsp+0CD0h+var_C60], rax
0x18003c9fb  test    rax, rax
0x18003c9fe  jz      loc_18003CE8F
0x18003ca04  jmp     loc_18003CA99
0x18003ca09  lea     rdx, aRmrecoveryguid; "RmRecoveryGuid"
0x18003ca10  mov     rcx, rbx; String1
0x18003ca13  call    cs:__imp__stricmp
0x18003ca19  test    eax, eax
0x18003ca1b  jnz     short loc_18003CA39
0x18003ca1d  test    r12, r12
0x18003ca20  jnz     short loc_18003CA39
0x18003ca22  lea     rdx, Delimiter; "=, "
0x18003ca29  xor     ecx, ecx; String
0x18003ca2b  call    cs:__imp_strtok
0x18003ca31  mov     r12, rax
0x18003ca34  test    rax, rax
0x18003ca37  jz      short loc_18003CAB4
0x18003ca39  lea     rdx, aTimeout; "Timeout"
0x18003ca40  mov     rcx, rbx; String1
0x18003ca43  call    cs:__imp__stricmp
0x18003ca49  test    eax, eax
0x18003ca4b  jnz     short loc_18003CA69
0x18003ca4d  test    rdi, rdi
0x18003ca50  jnz     short loc_18003CA69
0x18003ca52  lea     rdx, Delimiter; "=, "
0x18003ca59  xor     ecx, ecx; String
0x18003ca5b  call    cs:__imp_strtok
0x18003ca61  mov     rdi, rax
0x18003ca64  test    rax, rax
0x18003ca67  jz      short loc_18003CAB4
0x18003ca69  lea     rdx, aBriso; "BrIso"
0x18003ca70  mov     rcx, rbx; String1
0x18003ca73  call    cs:__imp__stricmp
0x18003ca79  test    eax, eax
0x18003ca7b  jnz     short loc_18003CA99
0x18003ca7d  test    rsi, rsi
0x18003ca80  jnz     short loc_18003CA99
0x18003ca82  lea     rdx, Delimiter; "=, "
0x18003ca89  xor     ecx, ecx; String
0x18003ca8b  call    cs:__imp_strtok
0x18003ca91  mov     rsi, rax
0x18003ca94  test    rax, rax
0x18003ca97  jz      short loc_18003CAB4
0x18003ca99  lea     rdx, Delimiter; "=, "
0x18003caa0  xor     ecx, ecx; String
0x18003caa2  call    cs:__imp_strtok
0x18003caa8  mov     rbx, rax
0x18003caab  test    rax, rax
0x18003caae  jnz     loc_18003C9C7
0x18003cab4  test    r15, r15
0x18003cab7  jz      loc_18003CE8F
0x18003cabd  test    r12, r12
0x18003cac0  jz      loc_18003CE8F
0x18003cac6  inc     r14
0x18003cac9  cmp     [r12+r14], r13b
0x18003cacd  jnz     short loc_18003CAC6
0x18003cacf  cmp     r14, 24h ; '$'
0x18003cad3  jnz     loc_18003CE8F
0x18003cad9  test    rsi, rsi
0x18003cadc  jz      short loc_18003CAF6
0x18003cade  lea     rdx, aTight; "Tight"
0x18003cae5  mov     rcx, rsi; String1
0x18003cae8  call    cs:__imp__stricmp
0x18003caee  test    eax, eax
0x18003caf0  jnz     loc_18003CE8F
0x18003caf6  test    rdi, rdi
0x18003caf9  jz      short loc_18003CB39
0x18003cafb  mov     rcx, rdi; String
0x18003cafe  call    cs:__imp_atoi
0x18003cb04  mov     r13d, eax
0x18003cb07  test    eax, eax
0x18003cb09  jg      short loc_18003CB39
0x18003cb0b  mov     edx, 2; MaxCount
0x18003cb10  mov     rcx, rdi; String
0x18003cb13  call    cs:__imp_strnlen
0x18003cb19  cmp     rax, 1
0x18003cb1d  jb      loc_18003CE8F
0x18003cb23  cmp     byte ptr [rdi], 30h ; '0'
0x18003cb26  jnz     loc_18003CE8F
0x18003cb2c  cmp     byte ptr [rdi+1], 0
0x18003cb30  jnz     loc_18003CE8F
0x18003cb36  xor     r13d, r13d
0x18003cb39  xor     eax, eax
0x18003cb3b  test    rsi, rsi
0x18003cb3e  setnz   al
0x18003cb41  mov     [rsp+0CD0h+var_C68], eax
0x18003cb45  mov     [rsp+0CD0h+var_C90], eax
0x18003cb49  mov     dword ptr [rsp+0CD0h+Src], r13d
0x18003cb4e  lea     rax, aFinishedParsin; "Finished parsing xa_info: dwTimeout=%d "...
0x18003cb55  mov     [rsp+0CD0h+var_CA0], rax
0x18003cb5a  mov     [rsp+0CD0h+Size], 0
0x18003cb63  lea     r15, aCimpixamapperf; "CImpIXaMapperFactory::Create"
0x18003cb6a  mov     qword ptr [rsp+0CD0h+var_CB0], r15
0x18003cb6f  mov     r9d, 164h
0x18003cb75  lea     rbx, aComComplusDtcD_16; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18003cb7c  mov     r8, rbx
0x18003cb7f  mov     edx, 4
0x18003cb84  lea     r14d, [rdx+7]
0x18003cb88  mov     ecx, r14d
0x18003cb8b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18003cb90  mov     rcx, [rsp+0CD0h+var_C70]
0x18003cb95  add     rcx, 30h ; '0'
0x18003cb99  mov     [rsp+0CD0h+var_C58], rcx
0x18003cb9e  mov     rax, [rcx]
0x18003cba1  mov     rax, [rax]
0x18003cba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cba9  mov     edx, [rsp+0CD0h+var_C78]; int
0x18003cbad  mov     rcx, [rsp+0CD0h+var_C70]; this
0x18003cbb2  call    ?FindAnXaMapper@CImpIXaMapperFactory@@QEAAPEAVCImpIXaMapper@@H@Z; CImpIXaMapperFactory::FindAnXaMapper(int)
0x18003cbb7  mov     [rsp+0CD0h+var_C80], rax
0x18003cbbc  test    rax, rax
0x18003cbbf  jnz     loc_18003CD75
0x18003cbc5  mov     rsi, [rsp+0CD0h+var_C70]
0x18003cbca  mov     rax, [rsi]
0x18003cbcd  mov     rcx, rsi
0x18003cbd0  mov     rax, [rax+8]
0x18003cbd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbd9  mov     eax, [rsp+0CD0h+var_C78]
0x18003cbdd  mov     dword ptr [rsp+0CD0h+Src], eax
0x18003cbe1  lea     rax, aNoExistingIxam; "No existing IXaMapper for rmid=0x%x fou"...
0x18003cbe8  mov     [rsp+0CD0h+var_CA0], rax
0x18003cbed  mov     [rsp+0CD0h+Size], 0
0x18003cbf6  mov     qword ptr [rsp+0CD0h+var_CB0], r15
0x18003cbfb  mov     r9d, 174h
0x18003cc01  mov     r8, rbx
0x18003cc04  lea     edx, [r14-7]
0x18003cc08  mov     ecx, r14d
0x18003cc0b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18003cc10  mov     ecx, 128h; Size
0x18003cc15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003cc1a  mov     [rbp+0BD0h+var_C48], rax
0x18003cc1e  test    rax, rax
0x18003cc21  jz      short loc_18003CC4E
0x18003cc23  mov     ecx, [rsp+0CD0h+var_C68]
0x18003cc27  mov     dword ptr [rsp+0CD0h+Size], ecx; int
0x18003cc2b  mov     ecx, [rsp+0CD0h+var_C78]
0x18003cc2f  mov     dword ptr [rsp+0CD0h+var_CB0], ecx; int
0x18003cc33  mov     r9, r12; char *
0x18003cc36  mov     r8, [rsp+0CD0h+var_C60]; char *
0x18003cc3b  mov     rdx, rsi; struct CImpIXaMapperFactory *
0x18003cc3e  mov     rcx, rax; this
0x18003cc41  call    ??0CImpIXaMapper@@QEAA@PEAVCImpIXaMapperFactory@@PEAD1HH@Z; CImpIXaMapper::CImpIXaMapper(CImpIXaMapperFactory *,char *,char *,int,int)
0x18003cc46  mov     rcx, rax
0x18003cc49  xor     r12d, r12d
0x18003cc4c  jmp     short loc_18003CC54
0x18003cc4e  xor     r12d, r12d
0x18003cc51  mov     ecx, r12d
0x18003cc54  mov     [rsp+0CD0h+var_C80], rcx
0x18003cc59  test    rcx, rcx
0x18003cc5c  jz      short loc_18003CCC8
0x18003cc5e  mov     rax, [rcx]
0x18003cc61  mov     rax, [rax+8]
0x18003cc65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc6a  mov     rcx, [rsp+0CD0h+var_C80]
0x18003cc6f  mov     rax, [rcx]
0x18003cc72  mov     rax, [rax+8]
0x18003cc76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc7b  lea     rcx, [rsi+10h]
0x18003cc7f  mov     rax, [rcx]
0x18003cc82  lea     rdx, [rsp+0CD0h+var_C80]
0x18003cc87  mov     rax, [rax+10h]
0x18003cc8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc90  mov     rax, [rsp+0CD0h+var_C80]
0x18003cc95  mov     [rsp+0CD0h+Src], rax
0x18003cc9a  lea     rax, aSuccessfullyCr; "Successfully created a new IXaMapper=%p"
0x18003cca1  mov     [rsp+0CD0h+var_CA0], rax
0x18003cca6  mov     [rsp+0CD0h+Size], r12
0x18003ccab  mov     qword ptr [rsp+0CD0h+var_CB0], r15
0x18003ccb0  mov     r9d, 182h
0x18003ccb6  mov     r8, rbx
0x18003ccb9  mov     edx, 4
0x18003ccbe  mov     ecx, r14d
0x18003ccc1  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18003ccc6  jmp     short loc_18003CD03
0x18003ccc8  mov     rax, [rsi]
0x18003cccb  mov     rcx, rsi
0x18003ccce  mov     rax, [rax+10h]
0x18003ccd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccd7  lea     rax, aFailedToCreate_1; "Failed to create a new IXaMapper"
0x18003ccde  mov     [rsp+0CD0h+var_CA0], rax
0x18003cce3  mov     [rsp+0CD0h+Size], r12
0x18003cce8  mov     qword ptr [rsp+0CD0h+var_CB0], r15
0x18003cced  mov     r9d, 188h
0x18003ccf3  mov     r8, rbx
0x18003ccf6  mov     edx, 4
0x18003ccfb  mov     ecx, r14d
0x18003ccfe  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18003cd03  mov     rcx, [rsp+0CD0h+var_C80]
0x18003cd08  test    rcx, rcx
0x18003cd0b  jz      loc_18003CE6F
0x18003cd11  mov     [rsp+0CD0h+Src], rcx
0x18003cd16  lea     rax, aInitializingPc; "Initializing pCIXaMapper=%p"
0x18003cd1d  mov     [rsp+0CD0h+var_CA0], rax
0x18003cd22  mov     [rsp+0CD0h+Size], r12
0x18003cd27  mov     qword ptr [rsp+0CD0h+var_CB0], r15
0x18003cd2c  mov     r9d, 1AEh
0x18003cd32  mov     r8, rbx
0x18003cd35  mov     edx, 4
0x18003cd3a  mov     ecx, r14d
0x18003cd3d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18003cd42  mov     rcx, [rsp+0CD0h+var_C80]; this
0x18003cd47  call    ?Init@CImpIXaMapper@@QEAAJXZ; CImpIXaMapper::Init(void)
0x18003cd4c  mov     esi, eax
0x18003cd4e  test    eax, eax
0x18003cd50  jnz     loc_18003CE1D
0x18003cd56  test    rdi, rdi
0x18003cd59  jz      short loc_18003CD64
0x18003cd5b  mov     rcx, [rsp+0CD0h+var_C80]
0x18003cd60  mov     [rcx+7Ch], r13d
0x18003cd64  mov     rcx, [rsp+0CD0h+var_C80]
0x18003cd69  mov     rax, [rbp+0BD0h+var_C50]
0x18003cd6d  mov     [rax], rcx
0x18003cd70  jmp     loc_18003CE74
0x18003cd75  mov     [rsp+0CD0h+Src], rax
  ... truncated ...
```
