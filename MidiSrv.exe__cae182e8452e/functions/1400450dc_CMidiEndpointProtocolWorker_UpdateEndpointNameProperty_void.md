# CMidiEndpointProtocolWorker::UpdateEndpointNameProperty(void)

- ea: `0x1400450dc`
- end: `0x1400452d2`
- name: `?UpdateEndpointNameProperty@CMidiEndpointProtocolWorker@@AEAAJXZ`
- size: `502`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14004249c`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x140013a38`
- `0x14001ddc4`
- `0x1400216cc`
- `0x1400450dc`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1400451d1`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1400451d1`

## string_xrefs

- `0x140045291`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x14004513d`: `CMidiEndpointProtocolWorker::UpdateEndpointNameProperty`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMidiEndpointProtocolWorker::UpdateEndpointNameProperty(CMidiEndpointProtocolWorker *this)
{
  _DWORD *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  char *v5; // rbx
  char *v6; // rax
  void *v7; // rax
  __int64 v8; // rax
  char **v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-E0h]
  char *v14; // [rsp+40h] [rbp-C0h] BYREF
  int v15[2]; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v16; // [rsp+50h] [rbp-B0h] BYREF
  CMidiEndpointProtocolWorker *v17; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v18[32]; // [rsp+60h] [rbp-A0h] BYREF
  char *v19[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v20; // [rsp+90h] [rbp-70h]
  unsigned __int64 v21; // [rsp+98h] [rbp-68h]
  char *Src[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v23; // [rsp+C0h] [rbp-40h] BYREF
  int v24; // [rsp+D0h] [rbp-30h]
  int v25; // [rsp+D4h] [rbp-2Ch]
  __int64 v26; // [rsp+D8h] [rbp-28h]
  int v27; // [rsp+E0h] [rbp-20h]
  int v28; // [rsp+E4h] [rbp-1Ch]
  char **v29; // [rsp+E8h] [rbp-18h]
  __int128 v30; // [rsp+F0h] [rbp-10h]
  int v31; // [rsp+100h] [rbp+0h]
  int v32; // [rsp+104h] [rbp+4h]
  __int64 v33; // [rsp+108h] [rbp+8h]
  int v34; // [rsp+110h] [rbp+10h]
  int v35; // [rsp+114h] [rbp+14h]
  char **v36; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  v5 = (char *)this + 56;
  if ( *v2 > 4u )
  {
    if ( *((_QWORD *)this + 10) <= 7u )
      v6 = (char *)this + 56;
    else
      v6 = *(char **)v5;
    v14 = v6;
    v16 = L"Enter";
    v17 = this;
    *(_QWORD *)v15 = "CMidiEndpointProtocolWorker::UpdateEndpointNameProperty";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)byte_14008C3EB,
      v3,
      v4,
      v15,
      (__int64)&v17,
      &v16,
      &v14);
  }
  v7 = (void *)std::wstring::wstring((__int64)v18, (__int64)this + 216);
  v8 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v7);
  std::operator+<unsigned short>(v19, v8, &qword_140081AD0);
  std::wstring::~wstring(Src);
  if ( !v20 )
    goto LABEL_13;
  v14 = 0;
  GetSystemTimePreciseAsFileTime(&v14);
  v23 = PKEY_MIDI_EndpointProvidedName;
  v24 = 170;
  v25 = 0;
  v26 = 0;
  v27 = 18;
  v28 = 2 * v20 + 2;
  v9 = v19;
  if ( v21 > 7 )
    v9 = (char **)v19[0];
  v29 = v9;
  v30 = PKEY_MIDI_EndpointProvidedNameLastUpdateTime;
  v31 = 172;
  v32 = 0;
  v33 = 0;
  v34 = 16;
  v35 = 8;
  v36 = &v14;
  if ( *((_QWORD *)this + 10) > 7u )
    v5 = *(char **)v5;
  v10 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int128 *))(**((_QWORD **)this + 22) + 48LL))(
          *((_QWORD *)this + 22),
          v5,
          2,
          &v23);
  v11 = v10;
  if ( v10 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4ED,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
      (const char *)(unsigned int)v10,
      v13);
  else
LABEL_13:
    v11 = 0;
  std::wstring::~wstring(v19);
  return v11;
}

```

## disassembly

```asm
0x1400450dc  mov     [rsp-8+arg_8], rbx
0x1400450e1  mov     [rsp-8+arg_10], rdi
0x1400450e6  push    rbp
0x1400450e7  lea     rbp, [rsp-30h]
0x1400450ec  sub     rsp, 130h
0x1400450f3  mov     rax, cs:__security_cookie
0x1400450fa  xor     rax, rsp
0x1400450fd  mov     [rbp+30h+var_10], rax
0x140045101  mov     rdi, rcx
0x140045104  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140045109  mov     rcx, [rax+8]
0x14004510d  mov     eax, [rcx]
0x14004510f  lea     rbx, [rdi+38h]
0x140045113  cmp     eax, 4
0x140045116  jbe     short loc_14004517D
0x140045118  cmp     qword ptr [rbx+18h], 7
0x14004511d  jbe     short loc_140045124
0x14004511f  mov     rax, [rbx]
0x140045122  jmp     short loc_140045127
0x140045124  mov     rax, rbx
0x140045127  mov     [rsp+130h+var_F0], rax
0x14004512c  lea     rax, aEnter; "Enter"
0x140045133  mov     [rsp+130h+var_E0], rax
0x140045138  mov     [rsp+130h+var_D8], rdi
0x14004513d  lea     rax, aCmidiendpointp_14; "CMidiEndpointProtocolWorker::UpdateEndp"...
0x140045144  mov     qword ptr [rsp+130h+var_E8], rax
0x140045149  lea     rax, [rsp+130h+var_F0]
0x14004514e  mov     [rsp+130h+var_F8], rax
0x140045153  lea     rax, [rsp+130h+var_E0]
0x140045158  mov     [rsp+130h+var_100], rax
0x14004515d  lea     rax, [rsp+130h+var_D8]
0x140045162  mov     [rsp+130h+var_108], rax
0x140045167  lea     rax, [rsp+130h+var_E8]
0x14004516c  mov     qword ptr [rsp+130h+var_110], rax; int
0x140045171  lea     rdx, byte_14008C3EB
0x140045178  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14004517d  lea     rdx, [rdi+0D8h]
0x140045184  lea     rcx, [rsp+130h+var_D0]
0x140045189  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14004518e  mov     rdx, rax; void *
0x140045191  lea     rcx, [rbp+30h+Src]; Src
0x140045195  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x14004519a  nop
0x14004519b  lea     r8, qword_140081AD0
0x1400451a2  mov     rdx, rax
0x1400451a5  lea     rcx, [rbp+30h+var_B0]
0x1400451a9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1400451ae  nop
0x1400451af  lea     rcx, [rbp+30h+Src]; void *
0x1400451b3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400451b8  cmp     [rbp+30h+var_A0], 0
0x1400451bd  jz      loc_1400452A4
0x1400451c3  mov     [rsp+130h+var_F0], 0
0x1400451cc  lea     rcx, [rsp+130h+var_F0]
0x1400451d1  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1400451d7  movups  xmm0, cs:PKEY_MIDI_EndpointProvidedName
0x1400451de  movaps  [rbp+30h+var_70], xmm0
0x1400451e2  mov     eax, cs:dword_14007A598
0x1400451e8  mov     [rbp+30h+var_60], eax
0x1400451eb  mov     [rbp+30h+var_5C], 0
0x1400451f2  mov     [rbp+30h+var_58], 0
0x1400451fa  mov     [rbp+30h+var_50], 12h
0x140045201  mov     eax, dword ptr [rbp+30h+var_A0]
0x140045204  lea     eax, ds:2[rax*2]
0x14004520b  mov     [rbp+30h+var_4C], eax
0x14004520e  lea     rax, [rbp+30h+var_B0]
0x140045212  cmp     [rbp+30h+var_98], 7
0x140045217  cmova   rax, [rbp+30h+var_B0]
0x14004521c  mov     [rbp+30h+var_48], rax
0x140045220  movups  xmm0, cs:PKEY_MIDI_EndpointProvidedNameLastUpdateTime
0x140045227  movaps  [rbp+30h+var_40], xmm0
0x14004522b  mov     eax, cs:dword_14007A320
0x140045231  mov     [rbp+30h+var_30], eax
0x140045234  mov     [rbp+30h+var_2C], 0
0x14004523b  mov     [rbp+30h+var_28], 0
0x140045243  mov     [rbp+30h+var_20], 10h
0x14004524a  mov     [rbp+30h+var_1C], 8
0x140045251  lea     rax, [rsp+130h+var_F0]
0x140045256  mov     [rbp+30h+var_18], rax
0x14004525a  mov     rcx, [rdi+0B0h]
0x140045261  mov     rax, [rcx]
0x140045264  cmp     qword ptr [rbx+18h], 7
0x140045269  jbe     short loc_14004526E
0x14004526b  mov     rbx, [rbx]
0x14004526e  lea     r9, [rbp+30h+var_70]
0x140045272  mov     r8d, 2
0x140045278  mov     rdx, rbx
0x14004527b  mov     rax, [rax+30h]
0x14004527f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045284  mov     ebx, eax
0x140045286  test    eax, eax
0x140045288  jns     short loc_1400452A4
0x14004528a  mov     rcx, [rbp+38h]; this
0x14004528e  mov     r9d, eax; char *
0x140045291  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140045298  mov     edx, 4EDh; void *
0x14004529d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400452a2  jmp     short loc_1400452A6
0x1400452a4  xor     ebx, ebx
0x1400452a6  lea     rcx, [rbp+30h+var_B0]; void *
0x1400452aa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400452af  mov     eax, ebx
0x1400452b1  mov     rcx, [rbp+30h+var_10]
0x1400452b5  xor     rcx, rsp; StackCookie
0x1400452b8  call    __security_check_cookie
0x1400452bd  lea     r11, [rsp+130h+var_s0]
0x1400452c5  mov     rbx, [r11+18h]
0x1400452c9  mov     rdi, [r11+20h]
0x1400452cd  mov     rsp, r11
0x1400452d0  pop     rbp
0x1400452d1  retn
```
