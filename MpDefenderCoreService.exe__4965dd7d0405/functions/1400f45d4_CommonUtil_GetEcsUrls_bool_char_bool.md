# CommonUtil::GetEcsUrls(bool,char * *,bool &)

- ea: `0x1400f45d4`
- end: `0x1400f48a5`
- name: `?GetEcsUrls@CommonUtil@@YAJ_NPEAPEADAEA_N@Z`
- size: `721`
- prototype: `int(CommonUtil *__hidden this, bool, char **, bool *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14009f6a8`

## callees

- `0x140010fb4`
- `0x140011038`
- `0x140012100`
- `0x14001263c`
- `0x140014ac8`
- `0x1400154f4`
- `0x14003a130`
- `0x14003a5c0`
- `0x14003c594`
- `0x14005d2d0`
- `0x14007d210`
- `0x140085d94`
- `0x1400935a0`
- `0x1400f45d4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400f476a`
- `ADVAPI32!RegCloseKey` at `0x1400f4800`
- `ADVAPI32!RegCloseKey` at `0x1400f476a`
- `ADVAPI32!RegCloseKey` at `0x1400f4800`

## string_xrefs

- `0x1400f4870`: `https://ecs.office.com/config/v1/`
- `0x1400f479b`: `ECSURI:`
- `0x1400f47cf`: `endpoint.security.microsoft.com`
- `0x1400f47b6`: `%ls/config/v1/`

## pseudocode

```c
int __fastcall CommonUtil::GetEcsUrls(CommonUtil *this, CommonUtil *a2, char **a3, bool *a4)
{
  int v7; // eax
  __int64 v8; // r10
  int v9; // edi
  int ValueMultiString; // eax
  const struct std::nothrow_t *v11; // rdx
  const wchar_t *v12; // rsi
  unsigned __int64 v13; // rax
  const struct std::nothrow_t *v14; // rdx
  wchar_t **v15; // [rsp+20h] [rbp-88h]
  wchar_t *v16; // [rsp+48h] [rbp-60h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-58h] BYREF
  wchar_t v18[4]; // [rsp+58h] [rbp-50h] BYREF
  __int128 v19; // [rsp+60h] [rbp-48h] BYREF

  if ( !a2 )
    return -2147024809;
  *(_BYTE *)a3 = 0;
  if ( !(_BYTE)this )
  {
    *(_BYTE *)a3 = 1;
    return CommonUtil::HrDuplicateStringA(a2, (char **)"https://ecs.office.com/config/v1/", (const char *)a3);
  }
  hKey = 0;
  v7 = CommonUtil::UtilRegOpenKey(
         (CommonUtil *)&hKey,
         (HKEY *)0xFFFFFFFF80000002LL,
         (const WCHAR *)&stru_14019E4A0,
         (const wchar_t *)1);
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        98,
        (unsigned int)WPP_31c6392f1d31353d2174d94cd470b5f6_Traceguids,
        (unsigned int)&stru_14019E4A0,
        v7);
      v8 = WPP_GLOBAL_Control;
    }
    v9 = 0;
LABEL_20:
    if ( hKey )
    {
      RegCloseKey(hKey);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v9 < 0 && (_UNKNOWN *)v8 != &WPP_GLOBAL_Control && (*(_BYTE *)(v8 + 28) & 2) != 0 )
      WPP_SF_d(*(_QWORD *)(v8 + 16), 100, WPP_31c6392f1d31353d2174d94cd470b5f6_Traceguids, (unsigned int)v9);
    *(_BYTE *)a3 = 1;
    return CommonUtil::HrDuplicateStringA(a2, (char **)"https://ecs.office.com/config/v1/", (const char *)a3);
  }
  v16 = 0;
  *(_QWORD *)v18 = 0;
  ValueMultiString = CommonUtil::UtilRegGetValueMultiString(
                       (CommonUtil *)hKey,
                       (HKEY)&stru_14019E530,
                       v18,
                       (unsigned __int64 *)&v16,
                       v15);
  v9 = ValueMultiString;
  if ( ValueMultiString < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      WPP_SF_SSd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), (__int64)&stru_14019E4A0, ValueMultiString);
      v8 = WPP_GLOBAL_Control;
    }
    v9 = 0;
LABEL_18:
    if ( v16 )
    {
      operator delete(v16, v11);
      v8 = WPP_GLOBAL_Control;
    }
    goto LABEL_20;
  }
  v19 = 0;
  CommonUtil::CMultiStringIterator::CMultiStringIterator(
    (CommonUtil::CMultiStringIterator *)&v19,
    *(_QWORD *)v18 - 1LL,
    v16);
  while ( 1 )
  {
    v12 = CommonUtil::CMultiStringIterator::EnumString((CommonUtil::CMultiStringIterator *)&v19);
    if ( !v12 )
    {
      v8 = WPP_GLOBAL_Control;
      goto LABEL_18;
    }
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    if ( v13 > 7 )
    {
      _mm_lfence();
      if ( !wcsncmp(L"ECSURI:", v12, 7u) )
      {
        _mm_lfence();
        v9 = CommonUtil::NewSprintfA(a2, (char **)"%ls/config/v1/", (const char *)v12 + 14);
        if ( v9 >= 0 )
          break;
      }
    }
  }
  if ( !strstr(*(const char **)a2, "endpoint.security.microsoft.com") )
    *(_BYTE *)a3 = 1;
  if ( v16 )
    operator delete(v16, v14);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1400f45d4  mov     [rsp+arg_0], rbx
0x1400f45d9  push    rsi
0x1400f45da  push    rdi
0x1400f45db  push    r12
0x1400f45dd  push    r14
0x1400f45df  push    r15
0x1400f45e1  sub     rsp, 80h
0x1400f45e8  mov     rax, cs:__security_cookie
0x1400f45ef  xor     rax, rsp
0x1400f45f2  mov     [rsp+0A8h+var_38], rax
0x1400f45f7  mov     r15, r8
0x1400f45fa  mov     r14, rdx
0x1400f45fd  mov     [rsp+0A8h+var_78], rdx
0x1400f4602  mov     [rsp+0A8h+var_70], r8
0x1400f4607  xor     ebx, ebx
0x1400f4609  test    rdx, rdx
0x1400f460c  jnz     short loc_1400F4618
0x1400f460e  mov     eax, 80070057h
0x1400f4613  jmp     loc_1400F4880
0x1400f4618  mov     [r8], bl
0x1400f461b  test    cl, cl
0x1400f461d  jnz     short loc_1400F4628
0x1400f461f  mov     byte ptr [r8], 1
0x1400f4623  jmp     loc_1400F4870
0x1400f4628  mov     [rsp+0A8h+hKey], rbx
0x1400f462d  mov     r9d, 1; wchar_t *
0x1400f4633  lea     r12, stru_14019E4A0
0x1400f463a  mov     r8, r12; HKEY
0x1400f463d  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x1400f4644  lea     rcx, [rsp+0A8h+hKey]; this
0x1400f4649  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x1400f464e  test    eax, eax
0x1400f4650  jns     short loc_1400F4696
0x1400f4652  lea     rsi, WPP_GLOBAL_Control
0x1400f4659  mov     r10, cs:WPP_GLOBAL_Control
0x1400f4660  cmp     r10, rsi
0x1400f4663  jz      short loc_1400F468F
0x1400f4665  test    byte ptr [r10+1Ch], 2
0x1400f466a  jz      short loc_1400F468F
0x1400f466c  mov     edx, 62h ; 'b'
0x1400f4671  mov     dword ptr [rsp+0A8h+var_88], eax
0x1400f4675  mov     r9, r12
0x1400f4678  lea     r8, WPP_31c6392f1d31353d2174d94cd470b5f6_Traceguids
0x1400f467f  mov     rcx, [r10+10h]
0x1400f4683  call    WPP_SF_Sd
0x1400f4688  mov     r10, cs:WPP_GLOBAL_Control
0x1400f468f  mov     edi, ebx
0x1400f4691  jmp     loc_1400F4760
0x1400f4696  mov     [rsp+0A8h+var_60], rbx
0x1400f469b  mov     qword ptr [rsp+0A8h+var_50], rbx
0x1400f46a0  lea     r9, [rsp+0A8h+var_60]; unsigned __int64 *
0x1400f46a5  lea     r8, [rsp+0A8h+var_50]; wchar_t *
0x1400f46aa  lea     rdx, stru_14019E530; HKEY
0x1400f46b1  mov     rcx, [rsp+0A8h+hKey]; this
0x1400f46b6  call    ?UtilRegGetValueMultiString@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEA_KPEAPEA_W@Z; CommonUtil::UtilRegGetValueMultiString(HKEY__ *,wchar_t const *,unsigned __int64 *,wchar_t * *)
0x1400f46bb  mov     edi, eax
0x1400f46bd  test    eax, eax
0x1400f46bf  jns     short loc_1400F470B
0x1400f46c1  lea     rsi, WPP_GLOBAL_Control
0x1400f46c8  mov     r10, cs:WPP_GLOBAL_Control
0x1400f46cf  cmp     r10, rsi
0x1400f46d2  jz      short loc_1400F4707
0x1400f46d4  test    byte ptr [r10+1Ch], 2
0x1400f46d9  jz      short loc_1400F4707
0x1400f46db  mov     edx, 63h ; 'c'
0x1400f46e0  mov     dword ptr [rsp+0A8h+var_80], eax; char
0x1400f46e4  mov     [rsp+0A8h+var_88], r12; __int64
0x1400f46e9  lea     r9, stru_14019E530
0x1400f46f0  lea     r8, WPP_31c6392f1d31353d2174d94cd470b5f6_Traceguids
0x1400f46f7  mov     rcx, [r10+10h]; LoggerHandle
0x1400f46fb  call    WPP_SF_SSd
0x1400f4700  mov     r10, cs:WPP_GLOBAL_Control
0x1400f4707  mov     edi, ebx
0x1400f4709  jmp     short loc_1400F474A
0x1400f470b  xorps   xmm0, xmm0
0x1400f470e  movups  [rsp+0A8h+var_48], xmm0
0x1400f4713  mov     rdx, qword ptr [rsp+0A8h+var_50]
0x1400f4718  dec     rdx; unsigned __int64
0x1400f471b  mov     r8, [rsp+0A8h+var_60]; wchar_t *
0x1400f4720  lea     rcx, [rsp+0A8h+var_48]; this
0x1400f4725  call    ??0CMultiStringIterator@CommonUtil@@QEAA@_KPEB_W@Z; CommonUtil::CMultiStringIterator::CMultiStringIterator(unsigned __int64,wchar_t const *)
0x1400f472a  lea     rcx, [rsp+0A8h+var_48]; this
0x1400f472f  call    ?EnumString@CMultiStringIterator@CommonUtil@@QEAAPEB_WXZ; CommonUtil::CMultiStringIterator::EnumString(void)
0x1400f4734  mov     rsi, rax
0x1400f4737  test    rax, rax
0x1400f473a  jnz     short loc_1400F477C
0x1400f473c  lea     rsi, WPP_GLOBAL_Control
0x1400f4743  mov     r10, cs:WPP_GLOBAL_Control
0x1400f474a  mov     rcx, [rsp+0A8h+var_60]; void *
0x1400f474f  test    rcx, rcx
0x1400f4752  jz      short loc_1400F4760
0x1400f4754  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400f4759  mov     r10, cs:WPP_GLOBAL_Control
0x1400f4760  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1400f4765  test    rcx, rcx
0x1400f4768  jz      short loc_1400F4777
0x1400f476a  call    cs:__imp_RegCloseKey
0x1400f4770  mov     r10, cs:WPP_GLOBAL_Control
0x1400f4777  jmp     loc_1400F4844
0x1400f477c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400f4780  inc     rax
0x1400f4783  cmp     [rsi+rax*2], bx
0x1400f4787  jnz     short loc_1400F4780
0x1400f4789  cmp     rax, 7
0x1400f478d  jbe     short loc_1400F472A
0x1400f478f  lfence
0x1400f4792  mov     r8d, 7; MaxCount
0x1400f4798  mov     rdx, rsi; String2
0x1400f479b  lea     rcx, aEcsuri; "ECSURI:"
0x1400f47a2  call    wcsncmp
0x1400f47a7  test    eax, eax
0x1400f47a9  jnz     loc_1400F472A
0x1400f47af  lfence
0x1400f47b2  lea     r8, [rsi+0Eh]; char *
0x1400f47b6  lea     rdx, aLsConfigV1; "%ls/config/v1/"
0x1400f47bd  mov     rcx, r14; this
0x1400f47c0  call    ?NewSprintfA@CommonUtil@@YAJPEAPEADPEBDZZ; CommonUtil::NewSprintfA(char * *,char const *,...)
0x1400f47c5  mov     edi, eax
0x1400f47c7  test    eax, eax
0x1400f47c9  js      loc_1400F472A
0x1400f47cf  lea     rdx, aEndpointSecuri; "endpoint.security.microsoft.com"
0x1400f47d6  mov     rcx, [r14]; Str
0x1400f47d9  call    strstr
0x1400f47de  test    rax, rax
0x1400f47e1  jnz     short loc_1400F47E7
0x1400f47e3  mov     byte ptr [r15], 1
0x1400f47e7  mov     rcx, [rsp+0A8h+var_60]; void *
0x1400f47ec  test    rcx, rcx
0x1400f47ef  jz      short loc_1400F47F6
0x1400f47f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400f47f6  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1400f47fb  test    rcx, rcx
0x1400f47fe  jz      short loc_1400F4806
0x1400f4800  call    cs:__imp_RegCloseKey
0x1400f4806  xor     eax, eax
0x1400f4808  jmp     short loc_1400F4880
0x1400f480a  lea     rsi, WPP_GLOBAL_Control
0x1400f4811  mov     edi, dword ptr [rsp+0A8h+var_60]
0x1400f4815  mov     r10, cs:WPP_GLOBAL_Control
0x1400f481c  mov     r14, [rsp+0A8h+var_78]
0x1400f4821  mov     r15, [rsp+0A8h+var_70]
0x1400f4826  jmp     short loc_1400F4848
0x1400f4828  lea     rsi, WPP_GLOBAL_Control
0x1400f482f  mov     edi, dword ptr [rsp+0A8h+var_60]
0x1400f4833  mov     r10, cs:WPP_GLOBAL_Control
0x1400f483a  mov     r14, [rsp+0A8h+var_78]
0x1400f483f  mov     r15, [rsp+0A8h+var_70]
0x1400f4844  test    edi, edi
0x1400f4846  jns     short loc_1400F486C
0x1400f4848  cmp     r10, rsi
0x1400f484b  jz      short loc_1400F486C
0x1400f484d  test    byte ptr [r10+1Ch], 2
0x1400f4852  jz      short loc_1400F486C
0x1400f4854  mov     edx, 64h ; 'd'
0x1400f4859  mov     r9d, edi
0x1400f485c  lea     r8, WPP_31c6392f1d31353d2174d94cd470b5f6_Traceguids
0x1400f4863  mov     rcx, [r10+10h]
0x1400f4867  call    WPP_SF_d
0x1400f486c  mov     byte ptr [r15], 1
0x1400f4870  lea     rdx, aHttpsEcsOffice; "https://ecs.office.com/config/v1/"
0x1400f4877  mov     rcx, r14; this
0x1400f487a  call    ?HrDuplicateStringA@CommonUtil@@YAJPEAPEADPEBD@Z; CommonUtil::HrDuplicateStringA(char * *,char const *)
0x1400f487f  nop
0x1400f4880  mov     rcx, [rsp+0A8h+var_38]
0x1400f4885  xor     rcx, rsp; StackCookie
0x1400f4888  call    __security_check_cookie
0x1400f488d  mov     rbx, [rsp+0A8h+arg_0]
0x1400f4895  add     rsp, 80h
0x1400f489c  pop     r15
0x1400f489e  pop     r14
0x1400f48a0  pop     r12
0x1400f48a2  pop     rdi
0x1400f48a3  pop     rsi
0x1400f48a4  retn
```
