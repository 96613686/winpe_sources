# WaasMedic::TasksHelper::CreateOrUpdateTask(ushort const *,ushort const *,ushort const *)

- ea: `0x1800301e0`
- end: `0x18003054d`
- name: `?CreateOrUpdateTask@TasksHelper@WaasMedic@@QEAAJPEBG00@Z`
- size: `877`
- prototype: `int(WaasMedic::TasksHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001fe68`
- `0x180039e40`

## callees

- `0x1800023dc`
- `0x18000bbd4`
- `0x18000d04c`
- `0x18002e81c`
- `0x1800301e0`
- `0x1800639bc`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180030228`
- `OLEAUT32!__imp_SysAllocString` at `0x180030247`
- `OLEAUT32!__imp_SysAllocString` at `0x1800302e2`
- `OLEAUT32!__imp_SysAllocString` at `0x180030228`
- `OLEAUT32!__imp_SysAllocString` at `0x180030247`
- `OLEAUT32!__imp_SysAllocString` at `0x1800302e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800304f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800304fb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800304f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800304fb`
- `OLEAUT32!__imp_VariantInit` at `0x180030265`
- `OLEAUT32!__imp_VariantInit` at `0x18003032a`
- `OLEAUT32!__imp_VariantInit` at `0x18003033e`
- `OLEAUT32!__imp_VariantInit` at `0x180030265`
- `OLEAUT32!__imp_VariantInit` at `0x18003032a`
- `OLEAUT32!__imp_VariantInit` at `0x18003033e`
- `OLEAUT32!__imp_VariantClear` at `0x180030299`
- `OLEAUT32!__imp_VariantClear` at `0x1800303b7`
- `OLEAUT32!__imp_VariantClear` at `0x1800303c9`
- `OLEAUT32!__imp_VariantClear` at `0x1800304c0`
- `OLEAUT32!__imp_VariantClear` at `0x180030299`
- `OLEAUT32!__imp_VariantClear` at `0x1800303b7`
- `OLEAUT32!__imp_VariantClear` at `0x1800303c9`
- `OLEAUT32!__imp_VariantClear` at `0x1800304c0`

## string_xrefs

- `0x180030282`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`
- `0x1800303e5`: `Failed to create or update task %s! hr = 0x%08x`
- `0x1800304a9`: `taskXml: %s`
- `0x180030497`: `TasksHelper: Error encountered when attempting to create or update %s. hr = 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall WaasMedic::TasksHelper::CreateOrUpdateTask(
        WaasMedic::TasksHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  OLECHAR *v8; // rdi
  OLECHAR *v9; // rbx
  HRESULT v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r14
  __int128 v13; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v15; // xmm6
  IRecordInfo *v16; // xmm7_8
  HRESULT v17; // eax
  HRESULT v18; // eax
  __int64 v19; // rcx
  int v20; // r9d
  HRESULT v21; // eax
  __int64 v22; // rcx
  int v24; // [rsp+20h] [rbp-E0h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR *v26; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v27; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v28; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v29; // [rsp+80h] [rbp-80h] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v31; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG v32; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v33; // [rsp+C0h] [rbp-40h] BYREF
  IRecordInfo *v34; // [rsp+D0h] [rbp-30h]
  __int128 v35; // [rsp+E0h] [rbp-20h] BYREF
  IRecordInfo *v36; // [rsp+F0h] [rbp-10h]
  VARIANTARG v37; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]
  int v39; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v40; // [rsp+1A8h] [rbp+A8h] BYREF
  OLECHAR *v41; // [rsp+1B0h] [rbp+B0h]

  v8 = 0;
  v41 = 0;
  if ( a2 )
  {
    v8 = SysAllocString(a2);
    v41 = v8;
  }
  v9 = 0;
  v26 = 0;
  if ( a3 )
  {
    v9 = SysAllocString(a3);
    v26 = v9;
  }
  v40 = 0;
  VariantInit(&pvarg);
  if ( *((_BYTE *)this + 17) )
  {
    if ( a4 )
    {
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString(a4);
      LODWORD(a4) = pvarg.llVal == 0 ? 0x80004003 : 0;
    }
    else
    {
      pvarg.vt = 0;
    }
    if ( (int)a4 < 0 )
      goto LABEL_17;
    v12 = *((_QWORD *)this + 1);
    a4 = *(const unsigned __int16 **)(*(_QWORD *)v12 + 128LL);
    v13 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v32);
    v15 = *(_OWORD *)&v32.vt;
    v16 = v32.pRecInfo;
    VariantInit(&v31);
    v33 = v13;
    v34 = pRecInfo;
    v35 = v15;
    v36 = v16;
    v37 = v31;
    LODWORD(a4) = ((__int64 (__fastcall *)(__int64, OLECHAR *, OLECHAR *, __int64, VARIANTARG *, __int128 *, int, __int128 *, __int64 *))a4)(
                    v12,
                    v8,
                    v9,
                    6,
                    &v37,
                    &v35,
                    5,
                    &v33,
                    &v40);
    v17 = VariantClear(&v31);
    if ( v17 < 0 )
      _com_issue_error(v17);
    v18 = VariantClear(&v32);
    if ( v18 < 0 )
      _com_issue_error(v18);
    if ( (int)a4 < 0 )
    {
LABEL_17:
      LogLevelW(2u, L"Failed to create or update task %s! hr = 0x%08x", a2, (unsigned int)a4);
      v19 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
      if ( *(_DWORD *)v19 > 5u
        && (*(_QWORD *)(v19 + 16) & 0x400000000000LL) != 0
        && (*(_QWORD *)(v19 + 24) & 0x400000000000LL) == *(_QWORD *)(v19 + 24) )
      {
        v39 = (int)a4;
        v27 = a3;
        v28 = a2;
        v29 = gc_pszVersionString;
        v30 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v19,
          (unsigned int)&unk_1800931A1,
          0,
          v20,
          (__int64)&v30,
          (__int64)&v29,
          (__int64)&v28,
          (__int64)&v27,
          (__int64)&v39);
      }
      LogLevelW(
        2u,
        L"TasksHelper: Error encountered when attempting to create or update %s. hr = 0x%08X",
        a2,
        (unsigned int)a4);
      LogLevelW(4u, L"taskXml: %s", a3);
    }
    v21 = VariantClear(&pvarg);
    if ( v21 < 0 )
      _com_issue_error(v21);
    v22 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
  }
  else
  {
    LODWORD(a4) = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x165,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\taskshelper.cpp",
      (const char *)0x8007139FLL,
      v24);
    v10 = VariantClear(&pvarg);
    if ( v10 < 0 )
      _com_issue_error(v10);
    v11 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  SysFreeString(v9);
  SysFreeString(v8);
  return (unsigned int)a4;
}

```

## disassembly

```asm
0x1800301e0  mov     rax, rsp
0x1800301e3  push    rbp
0x1800301e4  push    rbx
0x1800301e5  push    rsi
0x1800301e6  push    rdi
0x1800301e7  push    r12
0x1800301e9  push    r14
0x1800301eb  push    r15
0x1800301ed  lea     rbp, [rsp-60h]
0x1800301f2  sub     rsp, 160h
0x1800301f9  movaps  xmmword ptr [rax-48h], xmm6
0x1800301fd  movaps  xmmword ptr [rax-58h], xmm7
0x180030201  movaps  xmmword ptr [rax-68h], xmm8
0x180030206  movaps  xmmword ptr [rax-78h], xmm9
0x18003020b  mov     rsi, r9
0x18003020e  mov     r12, r8
0x180030211  mov     r15, rdx
0x180030214  mov     r14, rcx
0x180030217  xor     edi, edi
0x180030219  mov     [rbp+90h+arg_10], rdi
0x180030220  test    rdx, rdx
0x180030223  jz      short loc_180030238
0x180030225  mov     rcx, rdx; psz
0x180030228  call    cs:__imp_SysAllocString
0x18003022e  mov     rdi, rax
0x180030231  mov     [rbp+90h+arg_10], rax
0x180030238  xor     ebx, ebx
0x18003023a  mov     [rsp+190h+var_128], rbx
0x18003023f  test    r12, r12
0x180030242  jz      short loc_180030255
0x180030244  mov     rcx, r12; psz
0x180030247  call    cs:__imp_SysAllocString
0x18003024d  mov     rbx, rax
0x180030250  mov     [rsp+190h+var_128], rax
0x180030255  mov     [rbp+90h+arg_8], 0
0x180030260  lea     rcx, [rsp+190h+pvarg]; pvarg
0x180030265  call    cs:__imp_VariantInit
0x18003026b  nop
0x18003026c  cmp     byte ptr [r14+11h], 0
0x180030271  jnz     short loc_1800302D0
0x180030273  mov     rcx, [rbp+98h]; this
0x18003027a  mov     esi, 8007139Fh
0x18003027f  mov     r9d, esi; char *
0x180030282  lea     r8, aOnecoreEnduser_8; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180030289  mov     edx, 165h; void *
0x18003028e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030293  nop
0x180030294  lea     rcx, [rsp+190h+pvarg]; pvarg
0x180030299  call    cs:__imp_VariantClear
0x18003029f  test    eax, eax
0x1800302a1  js      loc_180030535
0x1800302a7  mov     rcx, [rbp+90h+arg_8]
0x1800302ae  test    rcx, rcx
0x1800302b1  jz      short loc_1800302CB
0x1800302b3  mov     [rbp+90h+arg_8], 0
0x1800302be  mov     rdx, [rcx]
0x1800302c1  mov     rax, [rdx+10h]
0x1800302c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302ca  nop
0x1800302cb  jmp     loc_1800304EE
0x1800302d0  test    rsi, rsi
0x1800302d3  jz      short loc_1800302FC
0x1800302d5  mov     eax, 8
0x1800302da  mov     word ptr [rsp+190h+pvarg], ax
0x1800302df  mov     rcx, rsi; psz
0x1800302e2  call    cs:__imp_SysAllocString
0x1800302e8  mov     qword ptr [rsp+190h+pvarg+8], rax
0x1800302ed  neg     rax
0x1800302f0  sbb     esi, esi
0x1800302f2  not     esi
0x1800302f4  and     esi, 80004003h
0x1800302fa  jmp     short loc_180030303
0x1800302fc  xor     eax, eax
0x1800302fe  mov     word ptr [rsp+190h+pvarg], ax
0x180030303  test    esi, esi
0x180030305  js      loc_1800303DF
0x18003030b  mov     r14, [r14+8]
0x18003030f  mov     rax, [r14]
0x180030312  mov     rsi, [rax+80h]
0x180030319  movups  xmm8, xmmword ptr [rsp+190h+pvarg]
0x18003031f  movsd   xmm9, qword ptr [rsp+190h+pvarg+10h]
0x180030326  lea     rcx, [rbp+90h+var_E8]; pvarg
0x18003032a  call    cs:__imp_VariantInit
0x180030330  nop
0x180030331  movups  xmm6, xmmword ptr [rbp+90h+var_E8]
0x180030335  movsd   xmm7, qword ptr [rbp+90h+var_E8+10h]
0x18003033a  lea     rcx, [rbp+90h+var_100]; pvarg
0x18003033e  call    cs:__imp_VariantInit
0x180030344  nop
0x180030345  movups  xmm0, xmmword ptr [rbp+90h+var_100]
0x180030349  movsd   xmm1, qword ptr [rbp+90h+var_100+10h]
0x18003034e  movaps  [rbp+90h+var_D0], xmm8
0x180030353  movsd   [rbp+90h+var_C0], xmm9
0x180030359  movaps  [rbp+90h+var_B0], xmm6
0x18003035d  movsd   [rbp+90h+var_A0], xmm7
0x180030362  movaps  [rbp+90h+var_90], xmm0
0x180030366  movsd   [rbp+90h+var_80], xmm1
0x18003036b  lea     rax, [rbp+90h+arg_8]
0x180030372  mov     [rsp+190h+var_150], rax
0x180030377  lea     rax, [rbp+90h+var_D0]
0x18003037b  mov     [rsp+190h+var_158], rax
0x180030380  mov     dword ptr [rsp+190h+var_160], 5
0x180030388  lea     rax, [rbp+90h+var_B0]
0x18003038c  mov     [rsp+190h+var_168], rax
0x180030391  lea     rax, [rbp+90h+var_90]
0x180030395  mov     [rsp+190h+var_170], rax
0x18003039a  mov     r9d, 6
0x1800303a0  mov     r8, rbx
0x1800303a3  mov     rdx, rdi
0x1800303a6  mov     rcx, r14
0x1800303a9  mov     rax, rsi
0x1800303ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303b1  mov     esi, eax
0x1800303b3  lea     rcx, [rbp+90h+var_100]; pvarg
0x1800303b7  call    cs:__imp_VariantClear
0x1800303bd  test    eax, eax
0x1800303bf  js      loc_18003053D
0x1800303c5  lea     rcx, [rbp+90h+var_E8]; pvarg
0x1800303c9  call    cs:__imp_VariantClear
0x1800303cf  test    eax, eax
0x1800303d1  js      loc_180030545
0x1800303d7  test    esi, esi
0x1800303d9  jns     loc_1800304BB
0x1800303df  mov     r9d, esi
0x1800303e2  mov     r8, r15
0x1800303e5  lea     rdx, aFailedToCreate_4; "Failed to create or update task %s! hr "...
0x1800303ec  mov     r14d, 2
0x1800303f2  mov     ecx, r14d; unsigned __int8
0x1800303f5  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800303fa  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x1800303ff  mov     rcx, [rax+8]
0x180030403  mov     eax, [rcx]
0x180030405  cmp     eax, 5
0x180030408  jbe     loc_180030491
0x18003040e  mov     rdx, [rcx+18h]
0x180030412  mov     rax, [rcx+10h]
0x180030416  mov     r8, 400000000000h
0x180030420  test    r8, rax
0x180030423  jz      short loc_180030491
0x180030425  mov     rax, rdx
0x180030428  and     rax, r8
0x18003042b  cmp     rax, rdx
0x18003042e  jnz     short loc_180030491
0x180030430  mov     [rbp+90h+arg_0], esi
0x180030436  mov     [rsp+190h+var_120], r12
0x18003043b  mov     [rsp+190h+var_118], r15
0x180030440  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x180030447  mov     [rbp+90h+var_110], rax
0x18003044b  mov     [rbp+90h+var_108], 1000000h
0x180030453  lea     rax, [rbp+90h+arg_0]
0x18003045a  mov     [rsp+190h+var_150], rax
0x18003045f  lea     rax, [rsp+190h+var_120]
0x180030464  mov     [rsp+190h+var_158], rax
0x180030469  lea     rax, [rsp+190h+var_118]
0x18003046e  mov     [rsp+190h+var_160], rax
0x180030473  lea     rax, [rbp+90h+var_110]
0x180030477  mov     [rsp+190h+var_168], rax
0x18003047c  lea     rax, [rbp+90h+var_108]
0x180030480  mov     [rsp+190h+var_170], rax
0x180030485  lea     rdx, unk_1800931A1
0x18003048c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180030491  mov     r9d, esi
0x180030494  mov     r8, r15
0x180030497  lea     rdx, aTaskshelperErr; "TasksHelper: Error encountered when att"...
0x18003049e  mov     ecx, r14d; unsigned __int8
0x1800304a1  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800304a6  mov     r8, r12
0x1800304a9  lea     rdx, aTaskxmlS; "taskXml: %s"
0x1800304b0  mov     ecx, 4; unsigned __int8
0x1800304b5  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800304ba  nop
0x1800304bb  lea     rcx, [rsp+190h+pvarg]; pvarg
0x1800304c0  call    cs:__imp_VariantClear
0x1800304c6  test    eax, eax
0x1800304c8  js      short loc_18003052D
0x1800304ca  mov     rcx, [rbp+90h+arg_8]
0x1800304d1  test    rcx, rcx
0x1800304d4  jz      short loc_1800304EE
0x1800304d6  mov     [rbp+90h+arg_8], 0
0x1800304e1  mov     rdx, [rcx]
0x1800304e4  mov     rax, [rdx+10h]
0x1800304e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304ed  nop
0x1800304ee  mov     rcx, rbx; bstrString
0x1800304f1  call    cs:__imp_SysFreeString
0x1800304f7  nop
0x1800304f8  mov     rcx, rdi; bstrString
0x1800304fb  call    cs:__imp_SysFreeString
0x180030501  mov     eax, esi
0x180030503  lea     r11, [rsp+190h+var_30]
0x18003050b  movaps  xmm6, xmmword ptr [r11-10h]
0x180030510  movaps  xmm7, xmmword ptr [r11-20h]
0x180030515  movaps  xmm8, xmmword ptr [r11-30h]
0x18003051a  movaps  xmm9, xmmword ptr [r11-40h]
0x18003051f  mov     rsp, r11
0x180030522  pop     r15
0x180030524  pop     r14
0x180030526  pop     r12
0x180030528  pop     rdi
0x180030529  pop     rsi
0x18003052a  pop     rbx
0x18003052b  pop     rbp
0x18003052c  retn
0x18003052d  mov     ecx, eax; int
0x18003052f  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180030535  mov     ecx, eax; int
0x180030537  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003053d  mov     ecx, eax; int
0x18003053f  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180030545  mov     ecx, eax; int
0x180030547  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
