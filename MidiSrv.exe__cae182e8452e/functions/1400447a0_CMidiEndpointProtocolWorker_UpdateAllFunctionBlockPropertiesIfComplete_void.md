# CMidiEndpointProtocolWorker::UpdateAllFunctionBlockPropertiesIfComplete(void)

- ea: `0x1400447a0`
- end: `0x140044b6c`
- name: `?UpdateAllFunctionBlockPropertiesIfComplete@CMidiEndpointProtocolWorker@@AEAAJXZ`
- size: `972`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140043720`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x140013a38`
- `0x14001440c`
- `0x14001ddc4`
- `0x1400216cc`
- `0x1400274d8`
- `0x140028c74`
- `0x1400417cc`
- `0x1400418d4`
- `0x1400447a0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140044a65`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140044a65`

## string_xrefs

- `0x140044b20`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x1400447fc`: `CMidiEndpointProtocolWorker::UpdateAllFunctionBlockPropertiesIfComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMidiEndpointProtocolWorker::UpdateAllFunctionBlockPropertiesIfComplete(
        CMidiEndpointProtocolWorker *this)
{
  _DWORD *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  _QWORD *v5; // rax
  __int64 *v6; // rbx
  __int64 v7; // rdx
  __int64 **v8; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 *v11; // rbx
  _QWORD *v12; // rsi
  void *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned __int8 v16; // r8
  __int64 v17; // rdx
  __int64 **v18; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned __int64 v23; // r8
  _QWORD *v24; // rdx
  int v25; // eax
  unsigned int v26; // ebx
  int v28; // [rsp+20h] [rbp-99h]
  __int128 v29; // [rsp+40h] [rbp-79h] BYREF
  __int64 v30; // [rsp+50h] [rbp-69h]
  __int64 v31; // [rsp+58h] [rbp-61h] BYREF
  int v32[2]; // [rsp+60h] [rbp-59h] BYREF
  _QWORD *v33; // [rsp+68h] [rbp-51h] BYREF
  const wchar_t *v34; // [rsp+70h] [rbp-49h] BYREF
  CMidiEndpointProtocolWorker *v35; // [rsp+78h] [rbp-41h] BYREF
  struct _DEVPROPKEY v36; // [rsp+80h] [rbp-39h] BYREF
  DEVPROPGUID Src; // [rsp+A0h] [rbp-19h] BYREF
  __int128 pid; // [rsp+B0h] [rbp-9h]
  __int128 v39; // [rsp+C0h] [rbp+7h]
  char *v40[4]; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v5 = (_QWORD *)((char *)this + 56);
    if ( *((_QWORD *)this + 10) > 7u )
      v5 = (_QWORD *)*v5;
    v33 = v5;
    v34 = L"Enter";
    v35 = this;
    *(_QWORD *)v32 = "CMidiEndpointProtocolWorker::UpdateAllFunctionBlockPropertiesIfComplete";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)byte_14008BFDD,
      v3,
      v4,
      v32,
      (__int64)&v35,
      &v34,
      &v33);
  }
  v29 = 0;
  v30 = 0;
  v6 = (__int64 *)**((_QWORD **)this + 37);
  while ( !*((_BYTE *)v6 + 25) )
  {
    CMidiEndpointProtocolWorker::FunctionBlockPropertyKeyFromNumber(this, &v36, *((_BYTE *)v6 + 28));
    Src = v36.fmtid;
    pid = v36.pid;
    *(_QWORD *)&v39 = 0x1400001003LL;
    *((_QWORD *)&v39 + 1) = v6 + 4;
    v7 = *((_QWORD *)&v29 + 1);
    if ( *((_QWORD *)&v29 + 1) == v30 )
    {
      std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v29, *((_QWORD *)&v29 + 1), &Src);
    }
    else
    {
      **((_OWORD **)&v29 + 1) = v36.fmtid;
      *(_OWORD *)(v7 + 16) = pid;
      *(_OWORD *)(v7 + 32) = v39;
      *((_QWORD *)&v29 + 1) += 48LL;
    }
    v8 = (__int64 **)v6[2];
    if ( *((_BYTE *)v8 + 25) )
    {
      for ( i = (__int64 *)v6[1]; !*((_BYTE *)i + 25) && v6 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v6 = i;
      v6 = i;
    }
    else
    {
      v6 = (__int64 *)v6[2];
      for ( j = *v8; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v6 = j;
    }
  }
  v11 = (__int64 *)**((_QWORD **)this + 35);
  while ( !*((_BYTE *)v11 + 25) )
  {
    v12 = v11 + 5;
    if ( *((_BYTE *)v11 + 72) )
    {
      v13 = (void *)std::wstring::wstring((__int64)&v36, (__int64)(v11 + 5));
      v14 = WindowsMidiServicesInternal::TrimmedWStringCopy(&Src, v13);
      v15 = std::operator+<unsigned short>(v40, v14, &qword_140081AD0);
      std::wstring::operator=((char **)v11 + 5, v15);
      std::wstring::~wstring(v40);
      std::wstring::~wstring((char **)&Src);
      v16 = *((_BYTE *)v11 + 32);
      if ( v11[7] )
      {
        CMidiEndpointProtocolWorker::FunctionBlockNamePropertyKeyFromNumber(this, (struct _DEVPROPKEY *)&Src, v16);
        DWORD1(pid) = 0;
        *((_QWORD *)&pid + 1) = 0;
        LODWORD(v39) = 18;
        DWORD1(v39) = 2 * *((_DWORD *)v11 + 14) + 2;
        if ( (unsigned __int64)v11[8] > 7 )
          v12 = (_QWORD *)*v12;
        *((_QWORD *)&v39 + 1) = v12;
      }
      else
      {
        CMidiEndpointProtocolWorker::FunctionBlockNamePropertyKeyFromNumber(this, (struct _DEVPROPKEY *)&Src, v16);
        DWORD1(pid) = 0;
        *((_QWORD *)&pid + 1) = 0;
        v39 = 0u;
      }
      v17 = *((_QWORD *)&v29 + 1);
      if ( *((_QWORD *)&v29 + 1) == v30 )
      {
        std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v29, *((_QWORD *)&v29 + 1), &Src);
      }
      else
      {
        **((_OWORD **)&v29 + 1) = Src;
        *(_OWORD *)(v17 + 16) = pid;
        *(_OWORD *)(v17 + 32) = v39;
        *((_QWORD *)&v29 + 1) += 48LL;
      }
    }
    v18 = (__int64 **)v11[2];
    if ( *((_BYTE *)v18 + 25) )
    {
      for ( k = (__int64 *)v11[1]; !*((_BYTE *)k + 25) && v11 == (__int64 *)k[2]; k = (__int64 *)k[1] )
        v11 = k;
      v11 = k;
    }
    else
    {
      v11 = (__int64 *)v11[2];
      for ( m = *v18; !*((_BYTE *)m + 25); m = (__int64 *)*m )
        v11 = m;
    }
  }
  v31 = 0;
  GetSystemTimePreciseAsFileTime(&v31);
  Src = (DEVPROPGUID)PKEY_MIDI_FunctionBlocksLastUpdateTime;
  pid = 0xB7u;
  *(_QWORD *)&v39 = 0x800000010LL;
  *((_QWORD *)&v39 + 1) = &v31;
  v21 = *((_QWORD *)&v29 + 1);
  if ( *((_QWORD *)&v29 + 1) == v30 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v29, *((_QWORD *)&v29 + 1), &Src);
    v22 = *((_QWORD *)&v29 + 1);
  }
  else
  {
    **((_OWORD **)&v29 + 1) = PKEY_MIDI_FunctionBlocksLastUpdateTime;
    *(_OWORD *)(v21 + 16) = pid;
    *(_OWORD *)(v21 + 32) = v39;
    v22 = *((_QWORD *)&v29 + 1) + 48LL;
    *((_QWORD *)&v29 + 1) += 48LL;
  }
  v23 = 0xAAAAAAAAAAAAAAABuLL * ((v22 - (__int64)v29) >> 4);
  v24 = (_QWORD *)((char *)this + 56);
  if ( *((_QWORD *)this + 10) > 7u )
    v24 = (_QWORD *)*v24;
  v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, unsigned __int64))(**((_QWORD **)this + 22) + 48LL))(
          *((_QWORD *)this + 22),
          v24,
          v23);
  v26 = v25;
  if ( v25 >= 0 )
  {
    *((_BYTE *)this + 136) = 0;
    v26 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64C,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
      (const char *)(unsigned int)v25,
      v28);
  }
  std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v29);
  return v26;
}

```

## disassembly

```asm
0x1400447a0  mov     [rsp-8+arg_8], rbx
0x1400447a5  mov     [rsp-8+arg_10], rsi
0x1400447aa  push    rbp
0x1400447ab  push    rdi
0x1400447ac  push    r14
0x1400447ae  lea     rbp, [rsp-47h]
0x1400447b3  sub     rsp, 100h
0x1400447ba  mov     rax, cs:__security_cookie
0x1400447c1  xor     rax, rsp
0x1400447c4  mov     [rbp+57h+var_20], rax
0x1400447c8  mov     rdi, rcx
0x1400447cb  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400447d0  mov     rcx, [rax+8]
0x1400447d4  mov     eax, [rcx]
0x1400447d6  cmp     eax, 4
0x1400447d9  jbe     short loc_140044837
0x1400447db  lea     rax, [rdi+38h]
0x1400447df  cmp     qword ptr [rax+18h], 7
0x1400447e4  jbe     short loc_1400447E9
0x1400447e6  mov     rax, [rax]
0x1400447e9  mov     [rbp+57h+var_A8], rax
0x1400447ed  lea     rax, aEnter; "Enter"
0x1400447f4  mov     [rbp+57h+var_A0], rax
0x1400447f8  mov     [rbp+57h+var_98], rdi
0x1400447fc  lea     rax, aCmidiendpointp_21; "CMidiEndpointProtocolWorker::UpdateAllF"...
0x140044803  mov     qword ptr [rbp+57h+var_B0], rax
0x140044807  lea     rax, [rbp+57h+var_A8]
0x14004480b  mov     [rsp+110h+var_D8], rax
0x140044810  lea     rax, [rbp+57h+var_A0]
0x140044814  mov     [rsp+110h+var_E0], rax
0x140044819  lea     rax, [rbp+57h+var_98]
0x14004481d  mov     [rsp+110h+var_E8], rax
0x140044822  lea     rax, [rbp+57h+var_B0]
0x140044826  mov     qword ptr [rsp+110h+var_F0], rax; int
0x14004482b  lea     rdx, byte_14008BFDD
0x140044832  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140044837  xorps   xmm0, xmm0
0x14004483a  movdqu  [rbp+57h+var_D0], xmm0
0x14004483f  xor     r14d, r14d
0x140044842  mov     [rbp+57h+var_C0], r14
0x140044846  mov     rbx, [rdi+128h]
0x14004484d  mov     rbx, [rbx]
0x140044850  cmp     [rbx+19h], r14b
0x140044854  jnz     loc_140044916
0x14004485a  mov     r8b, [rbx+1Ch]; unsigned __int8
0x14004485e  lea     rdx, [rbp+57h+var_90]; retstr
0x140044862  mov     rcx, rdi; this
0x140044865  call    ?FunctionBlockPropertyKeyFromNumber@CMidiEndpointProtocolWorker@@AEAA?AU_DEVPROPKEY@@E@Z; CMidiEndpointProtocolWorker::FunctionBlockPropertyKeyFromNumber(uchar)
0x14004486a  movups  xmm0, xmmword ptr [rbp+57h+var_90.fmtid.Data1]
0x14004486e  movups  [rbp+57h+Src], xmm0
0x140044872  mov     eax, [rbp+57h+var_90.pid]
0x140044875  mov     dword ptr [rbp+57h+var_60], eax
0x140044878  mov     dword ptr [rbp+57h+var_60+4], r14d
0x14004487c  mov     qword ptr [rbp+57h+var_60+8], r14
0x140044880  mov     dword ptr [rbp+57h+var_50], 1003h
0x140044887  mov     dword ptr [rbp+57h+var_50+4], 14h
0x14004488e  lea     rax, [rbx+20h]
0x140044892  mov     qword ptr [rbp+57h+var_50+8], rax
0x140044896  mov     rdx, qword ptr [rbp+57h+var_D0+8]
0x14004489a  cmp     rdx, [rbp+57h+var_C0]
0x14004489e  jz      short loc_1400448BA
0x1400448a0  movups  xmmword ptr [rdx], xmm0
0x1400448a3  movups  xmm0, [rbp+57h+var_60]
0x1400448a7  movups  xmmword ptr [rdx+10h], xmm0
0x1400448ab  movups  xmm1, [rbp+57h+var_50]
0x1400448af  movups  xmmword ptr [rdx+20h], xmm1
0x1400448b3  add     qword ptr [rbp+57h+var_D0+8], 30h ; '0'
0x1400448b8  jmp     short loc_1400448C7
0x1400448ba  lea     r8, [rbp+57h+Src]
0x1400448be  lea     rcx, [rbp+57h+var_D0]
0x1400448c2  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x1400448c7  mov     rcx, [rbx+10h]
0x1400448cb  cmp     [rcx+19h], r14b
0x1400448cf  jz      short loc_1400448F2
0x1400448d1  mov     rax, [rbx+8]
0x1400448d5  jmp     short loc_1400448E4
0x1400448d7  cmp     rbx, [rax+10h]
0x1400448db  jnz     short loc_1400448EA
0x1400448dd  mov     rbx, rax
0x1400448e0  mov     rax, [rax+8]
0x1400448e4  cmp     [rax+19h], r14b
0x1400448e8  jz      short loc_1400448D7
0x1400448ea  mov     rbx, rax
0x1400448ed  jmp     loc_140044850
0x1400448f2  mov     rbx, rcx
0x1400448f5  mov     rcx, [rcx]
0x1400448f8  cmp     [rcx+19h], r14b
0x1400448fc  jnz     loc_140044850
0x140044902  mov     rbx, rcx
0x140044905  mov     rax, [rcx]
0x140044908  mov     rcx, rax
0x14004490b  cmp     [rax+19h], r14b
0x14004490f  jz      short loc_140044902
0x140044911  jmp     loc_140044850
0x140044916  mov     rbx, [rdi+118h]
0x14004491d  mov     rbx, [rbx]
0x140044920  cmp     [rbx+19h], r14b
0x140044924  jnz     loc_140044A5D
0x14004492a  lea     rsi, [rbx+28h]
0x14004492e  cmp     [rsi+20h], r14b
0x140044932  jz      loc_140044A0E
0x140044938  mov     rdx, rsi
0x14004493b  lea     rcx, [rbp+57h+var_90]
0x14004493f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140044944  mov     rdx, rax; void *
0x140044947  lea     rcx, [rbp+57h+Src]; Src
0x14004494b  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x140044950  nop
0x140044951  lea     r8, qword_140081AD0
0x140044958  mov     rdx, rax
0x14004495b  lea     rcx, [rbp+57h+var_40]
0x14004495f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x140044964  mov     rdx, rax
0x140044967  mov     rcx, rsi
0x14004496a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14004496f  lea     rcx, [rbp+57h+var_40]; void *
0x140044973  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140044978  nop
0x140044979  lea     rcx, [rbp+57h+Src]; void *
0x14004497d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140044982  mov     r8b, [rbx+20h]; unsigned __int8
0x140044986  lea     rdx, [rbp+57h+Src]; retstr
0x14004498a  mov     rcx, rdi; this
0x14004498d  cmp     [rbx+38h], r14
0x140044991  jz      short loc_1400449C4
0x140044993  call    ?FunctionBlockNamePropertyKeyFromNumber@CMidiEndpointProtocolWorker@@AEAA?AU_DEVPROPKEY@@E@Z; CMidiEndpointProtocolWorker::FunctionBlockNamePropertyKeyFromNumber(uchar)
0x140044998  mov     dword ptr [rbp+57h+var_60+4], r14d
0x14004499c  mov     qword ptr [rbp+57h+var_60+8], r14
0x1400449a0  mov     dword ptr [rbp+57h+var_50], 12h
0x1400449a7  mov     eax, [rbx+38h]
0x1400449aa  lea     eax, ds:2[rax*2]
0x1400449b1  mov     dword ptr [rbp+57h+var_50+4], eax
0x1400449b4  cmp     qword ptr [rbx+40h], 7
0x1400449b9  jbe     short loc_1400449BE
0x1400449bb  mov     rsi, [rsi]
0x1400449be  mov     qword ptr [rbp+57h+var_50+8], rsi
0x1400449c2  jmp     short loc_1400449D9
0x1400449c4  call    ?FunctionBlockNamePropertyKeyFromNumber@CMidiEndpointProtocolWorker@@AEAA?AU_DEVPROPKEY@@E@Z; CMidiEndpointProtocolWorker::FunctionBlockNamePropertyKeyFromNumber(uchar)
0x1400449c9  mov     dword ptr [rbp+57h+var_60+4], r14d
0x1400449cd  mov     qword ptr [rbp+57h+var_60+8], r14
0x1400449d1  mov     qword ptr [rbp+57h+var_50], r14
0x1400449d5  mov     qword ptr [rbp+57h+var_50+8], r14
0x1400449d9  mov     rdx, qword ptr [rbp+57h+var_D0+8]
0x1400449dd  cmp     rdx, [rbp+57h+var_C0]
0x1400449e1  jz      short loc_140044A01
0x1400449e3  movups  xmm0, [rbp+57h+Src]
0x1400449e7  movups  xmmword ptr [rdx], xmm0
0x1400449ea  movups  xmm1, [rbp+57h+var_60]
0x1400449ee  movups  xmmword ptr [rdx+10h], xmm1
0x1400449f2  movups  xmm0, [rbp+57h+var_50]
0x1400449f6  movups  xmmword ptr [rdx+20h], xmm0
0x1400449fa  add     qword ptr [rbp+57h+var_D0+8], 30h ; '0'
0x1400449ff  jmp     short loc_140044A0E
0x140044a01  lea     r8, [rbp+57h+Src]
0x140044a05  lea     rcx, [rbp+57h+var_D0]
0x140044a09  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x140044a0e  mov     rcx, [rbx+10h]
0x140044a12  cmp     [rcx+19h], r14b
0x140044a16  jz      short loc_140044A39
0x140044a18  mov     rax, [rbx+8]
0x140044a1c  jmp     short loc_140044A2B
0x140044a1e  cmp     rbx, [rax+10h]
0x140044a22  jnz     short loc_140044A31
0x140044a24  mov     rbx, rax
0x140044a27  mov     rax, [rax+8]
0x140044a2b  cmp     [rax+19h], r14b
0x140044a2f  jz      short loc_140044A1E
0x140044a31  mov     rbx, rax
0x140044a34  jmp     loc_140044920
0x140044a39  mov     rbx, rcx
0x140044a3c  mov     rcx, [rcx]
0x140044a3f  cmp     [rcx+19h], r14b
0x140044a43  jnz     loc_140044920
0x140044a49  mov     rbx, rcx
0x140044a4c  mov     rax, [rcx]
0x140044a4f  mov     rcx, rax
0x140044a52  cmp     [rax+19h], r14b
0x140044a56  jz      short loc_140044A49
0x140044a58  jmp     loc_140044920
0x140044a5d  mov     [rbp+57h+var_B8], r14
0x140044a61  lea     rcx, [rbp+57h+var_B8]
0x140044a65  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x140044a6b  movups  xmm0, cs:PKEY_MIDI_FunctionBlocksLastUpdateTime
0x140044a72  movups  [rbp+57h+Src], xmm0
0x140044a76  mov     eax, cs:dword_14007A8E8
0x140044a7c  mov     dword ptr [rbp+57h+var_60], eax
0x140044a7f  mov     dword ptr [rbp+57h+var_60+4], r14d
0x140044a83  mov     qword ptr [rbp+57h+var_60+8], r14
0x140044a87  mov     dword ptr [rbp+57h+var_50], 10h
0x140044a8e  mov     dword ptr [rbp+57h+var_50+4], 8
0x140044a95  lea     rax, [rbp+57h+var_B8]
0x140044a99  mov     qword ptr [rbp+57h+var_50+8], rax
0x140044a9d  mov     rdx, qword ptr [rbp+57h+var_D0+8]
0x140044aa1  cmp     rdx, [rbp+57h+var_C0]
0x140044aa5  jz      short loc_140044AC8
0x140044aa7  movups  xmmword ptr [rdx], xmm0
0x140044aaa  movups  xmm0, [rbp+57h+var_60]
0x140044aae  movups  xmmword ptr [rdx+10h], xmm0
0x140044ab2  movups  xmm1, [rbp+57h+var_50]
0x140044ab6  movups  xmmword ptr [rdx+20h], xmm1
0x140044aba  mov     r8, qword ptr [rbp+57h+var_D0+8]
0x140044abe  add     r8, 30h ; '0'
0x140044ac2  mov     qword ptr [rbp+57h+var_D0+8], r8
0x140044ac6  jmp     short loc_140044AD9
0x140044ac8  lea     r8, [rbp+57h+Src]
0x140044acc  lea     rcx, [rbp+57h+var_D0]
0x140044ad0  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x140044ad5  mov     r8, qword ptr [rbp+57h+var_D0+8]
0x140044ad9  mov     rcx, [rdi+0B0h]
0x140044ae0  mov     rax, [rcx]
0x140044ae3  mov     r9, qword ptr [rbp+57h+var_D0]
0x140044ae7  sub     r8, r9
0x140044aea  sar     r8, 4
0x140044aee  mov     rdx, 0AAAAAAAAAAAAAAABh
0x140044af8  imul    r8, rdx
0x140044afc  lea     rdx, [rdi+38h]
0x140044b00  cmp     qword ptr [rdx+18h], 7
0x140044b05  jbe     short loc_140044B0A
0x140044b07  mov     rdx, [rdx]
0x140044b0a  mov     rax, [rax+30h]
0x140044b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044b13  mov     ebx, eax
0x140044b15  test    eax, eax
0x140044b17  jns     short loc_140044B33
0x140044b19  mov     rcx, [rbp+5Fh]; this
0x140044b1d  mov     r9d, eax; char *
0x140044b20  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140044b27  mov     edx, 64Ch; void *
0x140044b2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140044b31  jmp     short loc_140044B3D
0x140044b33  mov     [rdi+88h], r14b
0x140044b3a  mov     ebx, r14d
0x140044b3d  lea     rcx, [rbp+57h+var_D0]
0x140044b41  call    ??1?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@XZ; std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(void)
0x140044b46  mov     eax, ebx
0x140044b48  mov     rcx, [rbp+57h+var_20]
0x140044b4c  xor     rcx, rsp; StackCookie
0x140044b4f  call    __security_check_cookie
0x140044b54  lea     r11, [rsp+110h+var_10]
0x140044b5c  mov     rbx, [r11+28h]
0x140044b60  mov     rsi, [r11+30h]
0x140044b64  mov     rsp, r11
0x140044b67  pop     r14
0x140044b69  pop     rdi
0x140044b6a  pop     rbp
0x140044b6b  retn
```
