# CMidiSessionTracker::IsValidSession(_GUID,ulong)

- ea: `0x14003b2d0`
- end: `0x14003b472`
- name: `?IsValidSession@CMidiSessionTracker@@UEAAJU_GUID@@K@Z`
- size: `418`
- prototype: `__int64 __fastcall(CMidiSessionTracker *__hidden this, struct _GUID *__struct_ptr, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x140002390`
- `0x1400032f0`
- `0x14000984c`
- `0x14000a6b4`
- `0x14003a5e0`
- `0x14003b2d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003b395`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003b45c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003b395`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003b45c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003b2f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003b2f3`

## string_xrefs

- `0x14003b43b`: `avcore\midi2\service\exe\midisessiontracker.cpp`

## pseudocode

```c
__int64 __fastcall CMidiSessionTracker::IsValidSession(const wchar_t *this, struct _GUID *a2, unsigned int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  _DWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  _DWORD *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+20h] [rbp-39h]
  struct _GUID *v15; // [rsp+58h] [rbp-1h] BYREF
  const wchar_t *v16; // [rsp+60h] [rbp+7h] BYREF
  const wchar_t *v17; // [rsp+68h] [rbp+Fh] BYREF
  const char *v18; // [rsp+70h] [rbp+17h] BYREF
  int v19[4]; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v3 = (struct _RTL_CRITICAL_SECTION *)(this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 24));
  *(struct _GUID *)v19 = *a2;
  CMidiSessionTracker::FindSession(this, &v15, v19, a3);
  if ( v15 == *((struct _GUID **)this + 4) )
  {
    v11 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v11 > 2u )
    {
      LODWORD(v15) = a3;
      v17 = L"Session Invalid. NOT found in the tracker";
      *(_QWORD *)v19 = "CMidiSessionTracker::IsValidSession";
      v18 = (const char *)a2;
      v16 = this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v11,
        (__int64)&byte_14008AD9F,
        v12,
        v13,
        v19,
        (__int64)&v16,
        &v17);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B1,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisessiontracker.cpp",
      (const char *)0x80070490LL,
      v14);
    if ( v3 )
      LeaveCriticalSection(v3);
    return 2147943568LL;
  }
  else
  {
    v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v7 > 4u )
    {
      v16 = L"Session Valid. Found";
      v15 = a2;
      v18 = "CMidiSessionTracker::IsValidSession";
      v17 = this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        (__int64)v7,
        (__int64)byte_14008AA1D,
        v8,
        v9,
        &v18,
        (__int64)&v17,
        &v16);
    }
    if ( v3 )
      LeaveCriticalSection(v3);
    return 0;
  }
}

```

## disassembly

```asm
0x14003b2d0  push    rbp
0x14003b2d2  push    rbx
0x14003b2d3  push    rsi
0x14003b2d4  push    rdi
0x14003b2d5  push    r14
0x14003b2d7  lea     rbp, [rsp-37h]
0x14003b2dc  sub     rsp, 90h
0x14003b2e3  lea     rbx, [rcx+30h]
0x14003b2e7  mov     rdi, rcx
0x14003b2ea  mov     rcx, rbx; lpCriticalSection
0x14003b2ed  mov     r14d, r8d
0x14003b2f0  mov     rsi, rdx
0x14003b2f3  call    cs:__imp_EnterCriticalSection
0x14003b2f9  movups  xmm0, xmmword ptr [rsi]
0x14003b2fc  mov     r9d, r14d
0x14003b2ff  lea     r8, [rbp+57h+var_30]
0x14003b303  lea     rdx, [rbp+57h+var_58]
0x14003b307  mov     rcx, rdi
0x14003b30a  movdqu  xmmword ptr [rbp+57h+var_30], xmm0
0x14003b30f  call    ?FindSession@CMidiSessionTracker@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UMidiSessionEntry@@@std@@@std@@@std@@U_GUID@@K@Z; CMidiSessionTracker::FindSession(_GUID,ulong)
0x14003b314  mov     rax, [rdi+20h]
0x14003b318  cmp     [rbp+57h+var_58], rax
0x14003b31c  jz      loc_14003B3A2
0x14003b322  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003b327  mov     rcx, [rax+8]
0x14003b32b  mov     eax, [rcx]
0x14003b32d  cmp     eax, 4
0x14003b330  jbe     short loc_14003B38D
0x14003b332  lea     rax, aSessionValidFo; "Session Valid. Found"
0x14003b339  mov     [rbp+57h+var_60], r14d
0x14003b33d  mov     [rbp+57h+var_50], rax
0x14003b341  lea     rdx, byte_14008AA1D
0x14003b348  lea     rax, aCmidisessiontr_8; "CMidiSessionTracker::IsValidSession"
0x14003b34f  mov     [rbp+57h+var_58], rsi
0x14003b353  mov     [rbp+57h+var_40], rax
0x14003b357  lea     rax, [rbp+57h+var_60]
0x14003b35b  mov     [rsp+0B0h+var_70], rax
0x14003b360  lea     rax, [rbp+57h+var_58]
0x14003b364  mov     [rsp+0B0h+var_78], rax
0x14003b369  lea     rax, [rbp+57h+var_50]
0x14003b36d  mov     [rsp+0B0h+var_80], rax
0x14003b372  lea     rax, [rbp+57h+var_48]
0x14003b376  mov     [rsp+0B0h+var_88], rax
0x14003b37b  lea     rax, [rbp+57h+var_40]
0x14003b37f  mov     qword ptr [rsp+0B0h+var_90], rax
0x14003b384  mov     [rbp+57h+var_48], rdi
0x14003b388  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x14003b38d  test    rbx, rbx
0x14003b390  jz      short loc_14003B39B
0x14003b392  mov     rcx, rbx; lpCriticalSection
0x14003b395  call    cs:__imp_LeaveCriticalSection
0x14003b39b  xor     eax, eax
0x14003b39d  jmp     loc_14003B464
0x14003b3a2  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003b3a7  mov     rcx, [rax+8]
0x14003b3ab  mov     eax, [rcx]
0x14003b3ad  cmp     eax, 2
0x14003b3b0  jbe     loc_14003B437
0x14003b3b6  mov     rax, [rdi+20h]
0x14003b3ba  mov     rdx, 8E38E38E38E38E39h
0x14003b3c4  sub     rax, [rdi+18h]
0x14003b3c8  sar     rax, 4
0x14003b3cc  imul    rax, rdx
0x14003b3d0  lea     rdx, byte_14008AD9F
0x14003b3d7  mov     dword ptr [rbp+57h+var_58], r14d
0x14003b3db  mov     [rbp+57h+var_60], eax
0x14003b3de  lea     rax, aSessionInvalid; "Session Invalid. NOT found in the track"...
0x14003b3e5  mov     [rbp+57h+var_48], rax
0x14003b3e9  lea     rax, aCmidisessiontr_8; "CMidiSessionTracker::IsValidSession"
0x14003b3f0  mov     qword ptr [rbp+57h+var_30], rax
0x14003b3f4  lea     rax, [rbp+57h+var_60]
0x14003b3f8  mov     [rsp+0B0h+var_68], rax
0x14003b3fd  lea     rax, [rbp+57h+var_58]
0x14003b401  mov     [rsp+0B0h+var_70], rax
0x14003b406  lea     rax, [rbp+57h+var_40]
0x14003b40a  mov     [rsp+0B0h+var_78], rax
0x14003b40f  lea     rax, [rbp+57h+var_48]
0x14003b413  mov     [rsp+0B0h+var_80], rax
0x14003b418  lea     rax, [rbp+57h+var_50]
0x14003b41c  mov     [rsp+0B0h+var_88], rax
0x14003b421  lea     rax, [rbp+57h+var_30]
0x14003b425  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x14003b42a  mov     [rbp+57h+var_40], rsi
0x14003b42e  mov     [rbp+57h+var_50], rdi
0x14003b432  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@7@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14003b437  mov     rcx, [rbp+5Fh]; this
0x14003b43b  lea     r8, aAvcoreMidi2Ser_5; "avcore\\midi2\\service\\exe\\midisessio"...
0x14003b442  mov     edi, 80070490h
0x14003b447  mov     edx, 1B1h; void *
0x14003b44c  mov     r9d, edi; char *
0x14003b44f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b454  test    rbx, rbx
0x14003b457  jz      short loc_14003B462
0x14003b459  mov     rcx, rbx; lpCriticalSection
0x14003b45c  call    cs:__imp_LeaveCriticalSection
0x14003b462  mov     eax, edi
0x14003b464  add     rsp, 90h
0x14003b46b  pop     r14
0x14003b46d  pop     rdi
0x14003b46e  pop     rsi
0x14003b46f  pop     rbx
0x14003b470  pop     rbp
0x14003b471  retn
```
