# InitializeAboCompatibilityLayer(IAboSink *)

- ea: `0x180001010`
- end: `0x180001184`
- name: `?InitializeAboCompatibilityLayer@@YAJPEAVIAboSink@@@Z`
- size: `372`
- prototype: `__int64 __fastcall(struct IAboSink *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001010`
- `0x18000118c`
- `0x180001340`
- `0x18000147c`
- `0x180001500`
- `0x180001604`
- `0x180001f90`
- `0x180002990`
- `0x18000341a`
- `0x180003460`
- `0x180004140`

## import_xrefs

- `WS2_32!__imp_WSAGetLastError` at `0x180003850`
- `WS2_32!__imp_WSAGetLastError` at `0x180003850`
- `WS2_32!__imp_WSAStartup` at `0x18000112d`
- `WS2_32!__imp_WSAStartup` at `0x18000112d`
- `nativerd!InitializeNativeConfiguration` at `0x180001090`
- `nativerd!InitializeNativeConfiguration` at `0x180001090`

## pseudocode

```c
__int64 __fastcall InitializeAboCompatibilityLayer(struct IAboSink *a1)
{
  _QWORD *v2; // rax
  const unsigned __int16 *v3; // rdx
  signed int v4; // ebx
  ABO_WRAPPER *v5; // rax
  ABO_WRAPPER *v6; // rcx
  int Error; // eax
  WSAData WSAData; // [rsp+20h] [rbp-1B8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  v2 = operator new(0x18u);
  if ( !v2 )
  {
    g_pAboLog = 0;
    goto LABEL_18;
  }
  v2[1] = -1;
  *v2 = &ABO_MAPPER_LOG::`vftable';
  *((_DWORD *)v2 + 4) = 0;
  g_pAboLog = (ABO_MAPPER_LOG *)v2;
  g_InitStatus = 1;
  v4 = ABO_MAPPER_LOG::Create((ABO_MAPPER_LOG *)&ABO_MAPPER_LOG::`vftable', v3);
  if ( v4 < 0 )
    goto LABEL_19;
  v4 = InitializeNativeConfiguration();
  if ( v4 < 0 )
    goto LABEL_19;
  g_InitStatus = 2;
  v4 = ABO_NODE::Initialize();
  if ( v4 < 0 )
    goto LABEL_19;
  g_InitStatus = 3;
  v4 = InitializePropertyTables();
  if ( v4 < 0 )
    goto LABEL_19;
  g_InitStatus = 4;
  v5 = (ABO_WRAPPER *)operator new(0xF8u);
  if ( !v5 )
  {
    g_pAboWrapper = 0;
    goto LABEL_18;
  }
  g_pAboWrapper = ABO_WRAPPER::ABO_WRAPPER(v5);
  if ( !g_pAboWrapper )
  {
LABEL_18:
    v4 = -2147024888;
LABEL_19:
    if ( g_pAboLog )
      ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"AboMapper Abort Sequence Initiated");
    TerminateAboCompatibilityLayer();
    return (unsigned int)v4;
  }
  g_InitStatus = 5;
  v4 = ABO_WRAPPER::Create(v6, a1);
  if ( v4 < 0 )
    goto LABEL_19;
  if ( !WSAStartup(0x202u, &WSAData) )
  {
    g_InitStatus = 6;
    ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"AboMapper Started");
    return (unsigned int)v4;
  }
  Error = WSAGetLastError();
  v4 = Error;
  if ( Error > 0 )
    v4 = (unsigned __int16)Error | 0x80070000;
  if ( v4 < 0 )
    goto LABEL_19;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_0], rbx
0x180001015  push    rdi
0x180001016  sub     rsp, 1D0h
0x18000101d  mov     rax, cs:__security_cookie
0x180001024  xor     rax, rsp
0x180001027  mov     [rsp+1D8h+var_18], rax
0x18000102f  mov     rdi, rcx
0x180001032  xor     edx, edx; Val
0x180001034  lea     rcx, [rsp+1D8h+WSAData]; void *
0x180001039  mov     r8d, 198h; Size
0x18000103f  call    memset_0
0x180001044  mov     ecx, 18h; Size
0x180001049  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000104e  test    rax, rax
0x180001051  jz      loc_18000387B
0x180001057  lea     rcx, ??_7ABO_MAPPER_LOG@@6B@; this
0x18000105e  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x180001066  mov     [rax], rcx
0x180001069  mov     dword ptr [rax+10h], 0
0x180001070  mov     cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA, rax; ABO_MAPPER_LOG * g_pAboLog
0x180001077  mov     cs:?g_InitStatus@@3W4INIT_COMPAT_STATUS@@A, 1; INIT_COMPAT_STATUS g_InitStatus
0x180001081  call    ?Create@ABO_MAPPER_LOG@@QEAAJPEBG@Z; ABO_MAPPER_LOG::Create(ushort const *)
0x180001086  mov     ebx, eax
0x180001088  test    eax, eax
0x18000108a  js      loc_18000388B
0x180001090  call    cs:__imp_?InitializeNativeConfiguration@@YAJXZ; InitializeNativeConfiguration(void)
0x180001096  mov     ebx, eax
0x180001098  test    eax, eax
0x18000109a  js      loc_18000388B
0x1800010a0  mov     cs:?g_InitStatus@@3W4INIT_COMPAT_STATUS@@A, 2; INIT_COMPAT_STATUS g_InitStatus
0x1800010aa  call    ?Initialize@ABO_NODE@@SAJXZ; ABO_NODE::Initialize(void)
0x1800010af  mov     ebx, eax
0x1800010b1  test    eax, eax
0x1800010b3  js      loc_18000388B
0x1800010b9  mov     cs:?g_InitStatus@@3W4INIT_COMPAT_STATUS@@A, 3; INIT_COMPAT_STATUS g_InitStatus
0x1800010c3  call    ?InitializePropertyTables@@YAJXZ; InitializePropertyTables(void)
0x1800010c8  mov     ebx, eax
0x1800010ca  test    eax, eax
0x1800010cc  js      loc_18000388B
0x1800010d2  mov     ecx, 0F8h; Size
0x1800010d7  mov     cs:?g_InitStatus@@3W4INIT_COMPAT_STATUS@@A, 4; INIT_COMPAT_STATUS g_InitStatus
0x1800010e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800010e6  test    rax, rax
0x1800010e9  jz      loc_18000386E
0x1800010ef  mov     rcx, rax; this
0x1800010f2  call    ??0ABO_WRAPPER@@QEAA@XZ; ABO_WRAPPER::ABO_WRAPPER(void)
0x1800010f7  mov     cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA, rax; ABO_WRAPPER * g_pAboWrapper
0x1800010fe  test    rax, rax
0x180001101  jz      loc_180003886
0x180001107  mov     rdx, rdi; struct IAboSink *
0x18000110a  mov     cs:?g_InitStatus@@3W4INIT_COMPAT_STATUS@@A, 5; INIT_COMPAT_STATUS g_InitStatus
0x180001114  call    ?Create@ABO_WRAPPER@@QEAAJPEAVIAboSink@@@Z; ABO_WRAPPER::Create(IAboSink *)
0x180001119  mov     ebx, eax
0x18000111b  test    eax, eax
0x18000111d  js      loc_18000388B
0x180001123  mov     ecx, 202h; wVersionRequested
0x180001128  lea     rdx, [rsp+1D8h+WSAData]; lpWSAData
0x18000112d  call    cs:__imp_WSAStartup
0x180001133  test    eax, eax
0x180001135  jnz     loc_180003850
0x18000113b  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180001142  lea     rdx, aAbomapperStart; "AboMapper Started"
0x180001149  mov     cs:?g_InitStatus@@3W4INIT_COMPAT_STATUS@@A, 6; INIT_COMPAT_STATUS g_InitStatus
0x180001153  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180001158  mov     eax, ebx
0x18000115a  mov     rcx, [rsp+1D8h+var_18]
0x180001162  xor     rcx, rsp; StackCookie
0x180001165  call    __security_check_cookie
0x18000116a  mov     rbx, [rsp+1D8h+arg_0]
0x180001172  add     rsp, 1D0h
0x180001179  pop     rdi
0x18000117a  retn
0x18000117b  test    ebx, ebx
0x18000117d  jns     short loc_180001158
0x18000117f  jmp     loc_18000388B
0x180003850  call    cs:__imp_WSAGetLastError
0x180003856  mov     ebx, eax
0x180003858  test    eax, eax
0x18000385a  jle     loc_18000117B
0x180003860  movzx   ebx, ax
0x180003863  or      ebx, 80070000h
0x180003869  jmp     loc_18000117B
0x18000386e  mov     cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA, 0; ABO_WRAPPER * g_pAboWrapper
0x180003879  jmp     short loc_180003886
0x18000387b  mov     cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA, 0; ABO_MAPPER_LOG * g_pAboLog
0x180003886  mov     ebx, 80070008h
0x18000388b  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180003892  test    rcx, rcx
0x180003895  jz      short loc_1800038A3
0x180003897  lea     rdx, aAbomapperAbort; "AboMapper Abort Sequence Initiated"
0x18000389e  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x1800038a3  call    ?TerminateAboCompatibilityLayer@@YAXXZ; TerminateAboCompatibilityLayer(void)
0x1800038a8  nop
0x1800038a9  jmp     loc_180001158
```
