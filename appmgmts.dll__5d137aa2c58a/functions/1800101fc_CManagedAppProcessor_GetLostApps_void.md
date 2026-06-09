# CManagedAppProcessor::GetLostApps(void)

- ea: `0x1800101fc`
- end: `0x180010695`
- name: `?GetLostApps@CManagedAppProcessor@@AEAAKXZ`
- size: `1177`
- prototype: `__int64 __fastcall(CManagedAppProcessor *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180011ac0`

## callees

- `0x1800016d0`
- `0x1800016f4`
- `0x180002024`
- `0x180004e30`
- `0x180004fc0`
- `0x18000a554`
- `0x18000e834`
- `0x18000edc0`
- `0x18000f470`
- `0x1800101fc`
- `0x18001b1a0`
- `0x18001bbe0`
- `0x18001c0e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103fd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180010442`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180010442`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800103d3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800103d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010464`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010464`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800105af`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800105af`

## pseudocode

```c
__int64 __fastcall CManagedAppProcessor::GetLostApps(CManagedAppProcessor *this)
{
  int v2; // r13d
  unsigned int v3; // r14d
  __int64 v4; // r15
  char *v5; // rsi
  int AppInRSoP; // eax
  struct CAppInfo *v7; // rax
  CAppInfo *v8; // rbx
  DWORD LastError; // eax
  signed int v10; // eax
  unsigned int AppInfo; // esi
  int v12; // esi
  CAppInfo *v13; // rax
  __int64 v14; // rsi
  char *v15; // r15
  int v16; // eax
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+34h] [rbp-CCh] BYREF
  CAppInfo *v20; // [rsp+38h] [rbp-C8h]
  struct _GUID v21; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID v22; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v23[3]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[208]; // [rsp+90h] [rbp-70h] BYREF

  memset(v23, 0, 40);
  memset_0(v24, 0, sizeof(v24));
  v22 = 0;
  v19 = 0;
  if ( *((_DWORD *)this + 99) != 1 && *((_DWORD *)this + 74) )
  {
    v2 = 0;
    v3 = 0;
    *((_QWORD *)this + 26) = *((_QWORD *)this + 25);
    v4 = *((_QWORD *)this + 24);
    v5 = (char *)this + 184;
    while ( 1 )
    {
      *((_QWORD *)this + 25) = v4;
      if ( (char *)v4 == v5 )
        v4 = 0;
      if ( !v4 )
      {
LABEL_69:
        *((_QWORD *)this + 25) = *((_QWORD *)this + 26);
        return v3;
      }
      if ( *(_DWORD *)(v4 + 224) )
        goto LABEL_60;
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xC2Cu);
      AppInRSoP = CManagedAppProcessor::FindAppInRSoP(this, (struct CAppInfo *)v4, &v22, &v19);
      if ( AppInRSoP < 0 )
      {
        if ( AppInRSoP != -2147217406 )
        {
          v3 = AppInRSoP;
          if ( *(_DWORD *)&gDebugLevel )
            _DebugMsg(4, 0xC2Fu, (unsigned int)AppInRSoP);
          goto LABEL_69;
        }
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xC2Eu);
        CManagedAppProcessor::DeleteScriptFile(this, (struct _GUID *)(v4 + 24));
        goto LABEL_60;
      }
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xC2Du);
      v21 = *(struct _GUID *)(v4 + 24);
      v7 = CAppList::Find((CManagedAppProcessor *)((char *)this + 32), &v21);
      v8 = v7;
      if ( v7 )
      {
        v2 = 0;
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xC34u, *((_QWORD *)v7 + 5), *((_QWORD *)v7 + 9));
LABEL_47:
        *((_DWORD *)v8 + 56) |= 0x2002u;
        *((_DWORD *)v8 + 47) = 1;
        *((_DWORD *)v8 + 48) = v19;
        *(_QWORD *)((char *)v8 + 196) = *(_QWORD *)(v4 + 196);
        *((_DWORD *)this + 75) = 0;
        if ( v2 )
        {
          *((_QWORD *)this + 13) = *((_QWORD *)this + 12);
          v14 = *((_QWORD *)this + 11);
          v15 = (char *)this + 80;
          while ( 1 )
          {
            *((_QWORD *)this + 12) = v14;
            if ( (char *)v14 == v15 )
              v14 = 0;
            if ( !v14 )
            {
              *((_QWORD *)v8 + 1) = v15;
              *(_QWORD *)v8 = *(_QWORD *)v15;
              *(_QWORD *)(*(_QWORD *)v15 + 8LL) = v8;
              *(_QWORD *)v15 = v8;
              goto LABEL_59;
            }
            v16 = CGPOInfoList::Compare(
                    (LPCWSTR *)this,
                    *(const unsigned __int16 **)(v14 + 48),
                    *((const unsigned __int16 **)v8 + 6));
            if ( v16 != -1
              && (v16 == 1 || CompareFileTime((const FILETIME *)(v14 + 172), (const FILETIME *)((char *)v8 + 172)) >= 0) )
            {
              break;
            }
            v14 = *(_QWORD *)(*((_QWORD *)this + 12) + 8LL);
          }
          *(_QWORD *)v8 = *(_QWORD *)v14;
          *((_QWORD *)v8 + 1) = v14;
          *(_QWORD *)(*(_QWORD *)v14 + 8LL) = v8;
          *(_QWORD *)v14 = v8;
LABEL_59:
          v5 = (char *)this + 184;
        }
        goto LABEL_60;
      }
      memset_0(v24, 0, sizeof(v24));
      LODWORD(v23[0]) = 6;
      *(_OWORD *)((char *)v23 + 8) = *(_OWORD *)(v4 + 24);
      *(struct _GUID *)((char *)&v23[1] + 8) = v22;
      if ( *((_DWORD *)this + 99) == 1 || !*((_DWORD *)this + 74) || ImpersonateLoggedOnUser(*((HANDLE *)this + 33)) )
      {
        v3 = 0;
      }
      else
      {
        if ( *(_DWORD *)&gDebugLevel )
        {
          LastError = GetLastError();
          _DebugMsg(2, 0xBC4u, LastError);
        }
        v10 = GetLastError();
        v3 = v10;
        if ( v10 )
        {
          if ( v10 > 0 )
            AppInfo = (unsigned __int16)v10 | 0x80070000;
          else
            AppInfo = v10;
          goto LABEL_33;
        }
      }
      AppInfo = CsGetAppInfo(v23, 0, v24);
      if ( *((_DWORD *)this + 99) != 1 && *((_DWORD *)this + 74) )
        RevertToSelf();
LABEL_33:
      if ( AppInfo )
      {
        if ( AppInfo != -2147221148 )
        {
          v3 = AppInfo;
          goto LABEL_67;
        }
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xC31u);
        CManagedAppProcessor::DeleteScriptFile(this, (struct _GUID *)(v4 + 24));
      }
      else
      {
        v12 = 1;
        v18 = 1;
        v13 = (CAppInfo *)LocalAlloc(0, 0x1C8u);
        v20 = v13;
        if ( v13 )
        {
          v8 = CAppInfo::CAppInfo(v13, this, (struct tagPACKAGEDISPINFO *)v24, 0, &v18);
          v12 = v18;
        }
        else
        {
          v8 = 0;
        }
        ReleasePackageInfo(v24);
        if ( !v12 )
        {
          if ( v8 )
          {
            CAppInfo::~CAppInfo(v8);
            operator delete(v8);
          }
LABEL_65:
          v3 = 14;
LABEL_67:
          if ( *(_DWORD *)&gDebugLevel )
            _DebugMsg(4, 0xC32u, v3);
          goto LABEL_69;
        }
        if ( !v8 )
          goto LABEL_65;
        v2 = 1;
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xC30u, *((_QWORD *)v8 + 5), *((_QWORD *)v8 + 9));
      }
      if ( v3 )
        goto LABEL_67;
      v5 = (char *)this + 184;
      if ( v8 )
        goto LABEL_47;
LABEL_60:
      v4 = *(_QWORD *)(*((_QWORD *)this + 25) + 8LL);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800101fc  push    rbp
0x1800101fe  push    rbx
0x1800101ff  push    rsi
0x180010200  push    rdi
0x180010201  push    r12
0x180010203  push    r13
0x180010205  push    r14
0x180010207  push    r15
0x180010209  lea     rbp, [rsp-78h]
0x18001020e  sub     rsp, 178h
0x180010215  mov     rax, cs:__security_cookie
0x18001021c  xor     rax, rsp
0x18001021f  mov     [rbp+0B0h+var_50], rax
0x180010223  mov     rdi, rcx
0x180010226  xorps   xmm0, xmm0
0x180010229  xor     eax, eax
0x18001022b  movups  [rsp+1B0h+var_150], xmm0
0x180010230  movups  [rsp+1B0h+var_140], xmm0
0x180010235  mov     [rbp+0B0h+var_130], rax
0x180010239  xor     edx, edx; Val
0x18001023b  mov     r8d, 0D0h; Size
0x180010241  lea     rcx, [rbp+0B0h+var_120]; void *
0x180010245  call    memset_0
0x18001024a  xorps   xmm0, xmm0
0x18001024d  movups  xmmword ptr [rsp+1B0h+var_160.Data1], xmm0
0x180010252  xor     r12d, r12d
0x180010255  mov     [rsp+1B0h+var_17C], r12d
0x18001025a  cmp     dword ptr [rdi+18Ch], 1
0x180010261  jz      loc_180010673
0x180010267  cmp     [rdi+128h], r12d
0x18001026e  jz      loc_180010673
0x180010274  mov     r13d, r12d
0x180010277  mov     r14d, r12d
0x18001027a  mov     rax, [rdi+0C8h]
0x180010281  mov     [rdi+0D0h], rax
0x180010288  mov     r15, [rdi+0C0h]
0x18001028f  lea     rsi, [rdi+0B8h]
0x180010296  mov     [rdi+0C8h], r15
0x18001029d  cmp     r15, rsi
0x1800102a0  cmovz   r15, r12
0x1800102a4  test    r15, r15
0x1800102a7  jz      loc_180010660
0x1800102ad  cmp     [r15+0E0h], r12d
0x1800102b4  jnz     loc_1800105F9
0x1800102ba  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x1800102c1  jz      short loc_1800102D2
0x1800102c3  mov     edx, 0C2Ch; unsigned int
0x1800102c8  mov     ecx, 4; unsigned int
0x1800102cd  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800102d2  lea     r9, [rsp+1B0h+var_17C]; int *
0x1800102d7  lea     r8, [rsp+1B0h+var_160]; struct _GUID *
0x1800102dc  mov     rdx, r15; struct CAppInfo *
0x1800102df  mov     rcx, rdi; this
0x1800102e2  call    ?FindAppInRSoP@CManagedAppProcessor@@AEAAJPEAVCAppInfo@@PEAU_GUID@@PEAJ@Z; CManagedAppProcessor::FindAppInRSoP(CAppInfo *,_GUID *,long *)
0x1800102e7  test    eax, eax
0x1800102e9  jns     short loc_18001031F
0x1800102eb  cmp     eax, 80041002h
0x1800102f0  jnz     loc_180010609
0x1800102f6  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x1800102fd  jz      short loc_18001030E
0x1800102ff  mov     edx, 0C2Eh; unsigned int
0x180010304  mov     ecx, 4; unsigned int
0x180010309  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001030e  lea     rdx, [r15+18h]; struct _GUID *
0x180010312  mov     rcx, rdi; this
0x180010315  call    ?DeleteScriptFile@CManagedAppProcessor@@AEAAXAEAU_GUID@@@Z; CManagedAppProcessor::DeleteScriptFile(_GUID &)
0x18001031a  jmp     loc_1800105F9
0x18001031f  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x180010326  jz      short loc_180010337
0x180010328  mov     edx, 0C2Dh; unsigned int
0x18001032d  mov     ecx, 4; unsigned int
0x180010332  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180010337  lea     r12, [r15+18h]
0x18001033b  movups  xmm0, xmmword ptr [r12]
0x180010340  movdqu  xmmword ptr [rsp+1B0h+var_170.Data1], xmm0
0x180010346  lea     rcx, [rdi+20h]; this
0x18001034a  lea     rdx, [rsp+1B0h+var_170]; struct _GUID
0x18001034f  call    ?Find@CAppList@@QEAAPEAVCAppInfo@@U_GUID@@@Z; CAppList::Find(_GUID)
0x180010354  mov     rbx, rax
0x180010357  test    rax, rax
0x18001035a  jz      short loc_18001038B
0x18001035c  xor     r12d, r12d
0x18001035f  mov     r13d, r12d
0x180010362  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x180010369  jz      loc_18001052B
0x18001036f  mov     r9, [rax+48h]
0x180010373  mov     r8, [rax+28h]
0x180010377  mov     edx, 0C34h; unsigned int
0x18001037c  lea     ecx, [r12+4]; unsigned int
0x180010381  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180010386  jmp     loc_18001052B
0x18001038b  xor     edx, edx; Val
0x18001038d  mov     r8d, 0D0h; Size
0x180010393  lea     rcx, [rbp+0B0h+var_120]; void *
0x180010397  call    memset_0
0x18001039c  mov     dword ptr [rsp+1B0h+var_150], 6
0x1800103a4  movups  xmm0, xmmword ptr [r12]
0x1800103a9  movdqu  [rsp+1B0h+var_150+8], xmm0
0x1800103af  movups  xmm1, xmmword ptr [rsp+1B0h+var_160.Data1]
0x1800103b4  movdqu  [rsp+1B0h+var_140+8], xmm1
0x1800103ba  cmp     dword ptr [rdi+18Ch], 1
0x1800103c1  jz      short loc_18001041B
0x1800103c3  cmp     dword ptr [rdi+128h], 0
0x1800103ca  jz      short loc_18001041B
0x1800103cc  mov     rcx, [rdi+108h]; hToken
0x1800103d3  call    cs:__imp_ImpersonateLoggedOnUser
0x1800103d9  test    eax, eax
0x1800103db  jnz     short loc_18001041B
0x1800103dd  cmp     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x1800103e3  jz      short loc_1800103FD
0x1800103e5  call    cs:__imp_GetLastError
0x1800103eb  mov     r8d, eax
0x1800103ee  mov     edx, 0BC4h; unsigned int
0x1800103f3  mov     ecx, 2; unsigned int
0x1800103f8  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800103fd  call    cs:__imp_GetLastError
0x180010403  mov     r14d, eax
0x180010406  test    eax, eax
0x180010408  jz      short loc_18001041E
0x18001040a  jg      short loc_180010410
0x18001040c  mov     esi, eax
0x18001040e  jmp     short loc_180010448
0x180010410  movzx   esi, ax
0x180010413  or      esi, 80070000h
0x180010419  jmp     short loc_180010448
0x18001041b  xor     r14d, r14d
0x18001041e  lea     r8, [rbp+0B0h+var_120]
0x180010422  xor     edx, edx
0x180010424  lea     rcx, [rsp+1B0h+var_150]
0x180010429  call    CsGetAppInfo
0x18001042e  mov     esi, eax
0x180010430  cmp     dword ptr [rdi+18Ch], 1
0x180010437  jz      short loc_180010448
0x180010439  cmp     dword ptr [rdi+128h], 0
0x180010440  jz      short loc_180010448
0x180010442  call    cs:__imp_RevertToSelf
0x180010448  test    esi, esi
0x18001044a  jnz     loc_1800104E0
0x180010450  mov     esi, 1
0x180010455  mov     [rsp+1B0h+var_180], esi
0x180010459  mov     r13d, 1C8h
0x18001045f  mov     edx, r13d; uBytes
0x180010462  xor     ecx, ecx; uFlags
0x180010464  call    cs:__imp_LocalAlloc
0x18001046a  mov     [rsp+1B0h+var_178], rax
0x18001046f  xor     r12d, r12d
0x180010472  test    rax, rax
0x180010475  jz      short loc_18001049C
0x180010477  lea     rcx, [rsp+1B0h+var_180]
0x18001047c  mov     [rsp+1B0h+var_190], rcx; int *
0x180010481  xor     r9d, r9d; int
0x180010484  lea     r8, [rbp+0B0h+var_120]; struct tagPACKAGEDISPINFO *
0x180010488  mov     rdx, rdi; struct CManagedAppProcessor *
0x18001048b  mov     rcx, rax; this
0x18001048e  call    ??0CAppInfo@@QEAA@PEAVCManagedAppProcessor@@PEAUtagPACKAGEDISPINFO@@HAEAH@Z; CAppInfo::CAppInfo(CManagedAppProcessor *,tagPACKAGEDISPINFO *,int,int &)
0x180010493  mov     rbx, rax
0x180010496  mov     esi, [rsp+1B0h+var_180]
0x18001049a  jmp     short loc_18001049F
0x18001049c  mov     rbx, r12
0x18001049f  lea     rcx, [rbp+0B0h+var_120]; void *
0x1800104a3  call    ReleasePackageInfo
0x1800104a8  test    esi, esi
0x1800104aa  jz      loc_18001061F
0x1800104b0  test    rbx, rbx
0x1800104b3  jz      loc_180010637
0x1800104b9  mov     r13d, 1
0x1800104bf  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x1800104c6  jz      short loc_180010512
0x1800104c8  mov     r9, [rbx+48h]
0x1800104cc  mov     r8, [rbx+28h]
0x1800104d0  mov     edx, 0C30h; unsigned int
0x1800104d5  lea     ecx, [r13+3]; unsigned int
0x1800104d9  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800104de  jmp     short loc_180010512
0x1800104e0  cmp     esi, 80040164h
0x1800104e6  jnz     loc_18001063F
0x1800104ec  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x1800104f3  jz      short loc_180010504
0x1800104f5  mov     edx, 0C31h; unsigned int
0x1800104fa  mov     ecx, 4; unsigned int
0x1800104ff  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180010504  mov     rdx, r12; struct _GUID *
0x180010507  mov     rcx, rdi; this
0x18001050a  call    ?DeleteScriptFile@CManagedAppProcessor@@AEAAXAEAU_GUID@@@Z; CManagedAppProcessor::DeleteScriptFile(_GUID &)
0x18001050f  xor     r12d, r12d
0x180010512  test    r14d, r14d
0x180010515  jnz     loc_180010645
0x18001051b  lea     rsi, [rdi+0B8h]
0x180010522  test    rbx, rbx
0x180010525  jz      loc_1800105F9
0x18001052b  or      dword ptr [rbx+0E0h], 2002h
0x180010535  mov     dword ptr [rbx+0BCh], 1
0x18001053f  mov     eax, [rsp+1B0h+var_17C]
0x180010543  mov     [rbx+0C0h], eax
0x180010549  mov     rax, [r15+0C4h]
0x180010550  mov     [rbx+0C4h], rax
0x180010557  mov     [rdi+12Ch], r12d
0x18001055e  test    r13d, r13d
0x180010561  jz      loc_1800105F9
0x180010567  mov     rax, [rdi+60h]
0x18001056b  mov     [rdi+68h], rax
0x18001056f  mov     rsi, [rdi+58h]
0x180010573  lea     r15, [rdi+50h]
0x180010577  mov     [rdi+60h], rsi
0x18001057b  cmp     rsi, r15
0x18001057e  cmovz   rsi, r12
0x180010582  test    rsi, rsi
0x180010585  jz      short loc_1800105C8
0x180010587  mov     r8, [rbx+30h]; unsigned __int16 *
0x18001058b  mov     rdx, [rsi+30h]; unsigned __int16 *
0x18001058f  mov     rcx, rdi; this
0x180010592  call    ?Compare@CGPOInfoList@@QEAAHPEBG0@Z; CGPOInfoList::Compare(ushort const *,ushort const *)
0x180010597  cmp     eax, 0FFFFFFFFh
0x18001059a  jz      short loc_1800105B9
0x18001059c  cmp     eax, 1
0x18001059f  jz      short loc_1800105C3
0x1800105a1  lea     rdx, [rbx+0ACh]; lpFileTime2
0x1800105a8  lea     rcx, [rsi+0ACh]; lpFileTime1
0x1800105af  call    cs:__imp_CompareFileTime
0x1800105b5  test    eax, eax
0x1800105b7  jns     short loc_1800105C3
0x1800105b9  mov     rax, [rdi+60h]
0x1800105bd  mov     rsi, [rax+8]
0x1800105c1  jmp     short loc_180010577
0x1800105c3  test    rsi, rsi
0x1800105c6  jnz     short loc_1800105DE
0x1800105c8  mov     [rbx+8], r15
0x1800105cc  mov     rax, [r15]
0x1800105cf  mov     [rbx], rax
0x1800105d2  mov     rax, [r15]
0x1800105d5  mov     [rax+8], rbx
0x1800105d9  mov     [r15], rbx
0x1800105dc  jmp     short loc_1800105F2
0x1800105de  mov     rax, [rsi]
0x1800105e1  mov     [rbx], rax
0x1800105e4  mov     [rbx+8], rsi
0x1800105e8  mov     rax, [rsi]
0x1800105eb  mov     [rax+8], rbx
0x1800105ef  mov     [rsi], rbx
0x1800105f2  lea     rsi, [rdi+0B8h]
0x1800105f9  mov     rax, [rdi+0C8h]
0x180010600  mov     r15, [rax+8]
0x180010604  jmp     loc_180010296
0x180010609  mov     r14d, eax
0x18001060c  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x180010613  jz      short loc_180010660
0x180010615  mov     r8d, eax
0x180010618  mov     edx, 0C2Fh
0x18001061d  jmp     short loc_180010656
0x18001061f  test    rbx, rbx
0x180010622  jz      short loc_180010637
0x180010624  mov     rcx, rbx; this
0x180010627  call    ??1CAppInfo@@QEAA@XZ; CAppInfo::~CAppInfo(void)
0x18001062c  mov     rdx, r13; unsigned __int64
0x18001062f  mov     rcx, rbx; void *
0x180010632  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010637  mov     r14d, 0Eh
0x18001063d  jmp     short loc_180010645
0x18001063f  mov     r14d, esi
0x180010642  xor     r12d, r12d
0x180010645  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x18001064c  jz      short loc_180010660
0x18001064e  mov     r8d, r14d
0x180010651  mov     edx, 0C32h; unsigned int
0x180010656  mov     ecx, 4; unsigned int
0x18001065b  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180010660  mov     rcx, [rdi+0D0h]
0x180010667  mov     [rdi+0C8h], rcx
0x18001066e  mov     eax, r14d
0x180010671  jmp     short loc_180010675
0x180010673  xor     eax, eax
0x180010675  mov     rcx, [rbp+0B0h+var_50]
0x180010679  xor     rcx, rsp; StackCookie
0x18001067c  call    __security_check_cookie
0x180010681  add     rsp, 178h
0x180010688  pop     r15
0x18001068a  pop     r14
0x18001068c  pop     r13
0x18001068e  pop     r12
0x180010690  pop     rdi
0x180010691  pop     rsi
0x180010692  pop     rbx
0x180010693  pop     rbp
0x180010694  retn
```
