# ZTracer::ReportOrigination(int,char const *,int,void const *)

- ea: `0x1800028d4`
- end: `0x180002a4e`
- name: `?ReportOrigination@ZTracer@@QEAAXHPEBDHPEBX@Z`
- size: `378`
- prototype: `void __fastcall(ZTracer *__hidden this, int, const char *, int, const void *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800033e0`
- `0x180003420`
- `0x180003460`

## callees

- `0x180001184`
- `0x1800024bc`
- `0x1800028d4`
- `0x180002d8c`
- `0x1800037b4`
- `0x180003854`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800029b5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002a13`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800029b5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002a13`

## pseudocode

```c
void __fastcall ZTracer::ReportOrigination(ZTracer *this, int a2, const char *a3, int a4, const void *a5)
{
  int v9; // ecx
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // [rsp+44h] [rbp-44h] BYREF
  __int64 v13; // [rsp+48h] [rbp-40h]
  const char *v14; // [rsp+50h] [rbp-38h] BYREF

  if ( (unsigned int)UnderErrorUploadLimit(a2, a3, a4, 0) )
  {
    if ( (unsigned int)dword_180007000 > 5 )
    {
      v9 = qword_180007018;
      if ( (qword_180007010 & 0x400000000000LL) != 0 && (qword_180007018 & 0x400000000000LL) == qword_180007018 )
      {
        v13 = 50331648;
        v14 = a3;
        v12 = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_180007018,
          (__int64)byte_180005B55,
          v10,
          v11,
          (__int64)&v12,
          &v14);
      }
    }
  }
  if ( a5 == (const void *)-1LL )
  {
    if ( (Microsoft_Windows_ZTraceMapsEnableBits & 1) != 0 )
      McTemplateU0dsd_EventWriteTransfer(v9, (unsigned int)FlowControl_OriginateNoThis, a2, (_DWORD)a3, a4);
    if ( s_fShouldSpewDebug )
    {
      if ( IsDebuggerPresent() )
        ZTracer::DebugMsg(this, "%s:%s: originated %08x (%d)", "[Z!O] ", a3, a2, a4);
    }
  }
  else
  {
    if ( (Microsoft_Windows_ZTraceMapsEnableBits & 1) != 0 )
      McTemplateU0dspd_EventWriteTransfer(v9, (unsigned int)FlowControl_Originate, a2, (_DWORD)a3, (char)a5, a4);
    if ( s_fShouldSpewDebug && IsDebuggerPresent() )
      ZTracer::DebugMsg(this, "%s:%s@%p: originated %08x (%d)", "[Z!O] ", a3, a5, a2, a4);
  }
}

```

## disassembly

```asm
0x1800028d4  push    rbx
0x1800028d6  push    rbp
0x1800028d7  push    rsi
0x1800028d8  push    rdi
0x1800028d9  push    r14
0x1800028db  sub     rsp, 60h
0x1800028df  mov     ebx, r9d
0x1800028e2  mov     rdi, r8
0x1800028e5  mov     esi, edx
0x1800028e7  mov     r14, rcx
0x1800028ea  mov     r8d, ebx; int
0x1800028ed  mov     rdx, rdi; char *
0x1800028f0  mov     ecx, esi; int
0x1800028f2  xor     r9d, r9d; char *
0x1800028f5  call    ?UnderErrorUploadLimit@@YAHHPEBDH0@Z; UnderErrorUploadLimit(int,char const *,int,char const *)
0x1800028fa  test    eax, eax
0x1800028fc  jz      short loc_18000297B
0x1800028fe  mov     eax, cs:dword_180007000
0x180002904  cmp     eax, 5
0x180002907  jbe     short loc_18000297B
0x180002909  mov     rcx, cs:qword_180007018
0x180002910  mov     rdx, 400000000000h
0x18000291a  mov     rax, cs:qword_180007010
0x180002921  test    rdx, rax
0x180002924  jz      short loc_18000297B
0x180002926  mov     rax, rcx
0x180002929  and     rax, rdx
0x18000292c  cmp     rax, rcx
0x18000292f  jnz     short loc_18000297B
0x180002931  lea     rax, [rsp+88h+var_40]
0x180002936  mov     [rsp+88h+var_40], 3000000h
0x18000293f  mov     [rsp+88h+var_50], rax
0x180002944  lea     rdx, byte_180005B55
0x18000294b  lea     rax, [rsp+88h+var_48]
0x180002950  mov     [rsp+88h+var_48], ebx
0x180002954  mov     [rsp+88h+var_58], rax
0x180002959  lea     rax, [rsp+88h+var_38]
0x18000295e  mov     [rsp+88h+var_60], rax
0x180002963  lea     rax, [rsp+88h+var_44]
0x180002968  mov     [rsp+88h+var_68], rax
0x18000296d  mov     [rsp+88h+var_38], rdi
0x180002972  mov     [rsp+88h+var_44], esi
0x180002976  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18000297b  mov     rbp, [rsp+88h+arg_20]
0x180002983  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180002987  jnz     short loc_1800029E6
0x180002989  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 1
0x180002990  jz      short loc_1800029A8
0x180002992  mov     r9, rdi
0x180002995  mov     dword ptr [rsp+88h+var_68], ebx
0x180002999  mov     r8d, esi
0x18000299c  lea     rdx, _FlowControl_OriginateNoThis
0x1800029a3  call    McTemplateU0dsd_EventWriteTransfer
0x1800029a8  cmp     cs:?s_fShouldSpewDebug@@3HA, 0; int s_fShouldSpewDebug
0x1800029af  jz      loc_180002A43
0x1800029b5  call    cs:__imp_IsDebuggerPresent
0x1800029bb  test    eax, eax
0x1800029bd  jz      loc_180002A43
0x1800029c3  mov     dword ptr [rsp+88h+var_60], ebx
0x1800029c7  lea     r8, aZO; "[Z!O] "
0x1800029ce  mov     r9, rdi
0x1800029d1  mov     dword ptr [rsp+88h+var_68], esi
0x1800029d5  lea     rdx, aSSOriginated08; "%s:%s: originated %08x (%d)"
0x1800029dc  mov     rcx, r14; this
0x1800029df  call    ?DebugMsg@ZTracer@@QEAAXPEBDZZ; ZTracer::DebugMsg(char const *,...)
0x1800029e4  jmp     short loc_180002A43
0x1800029e6  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 1
0x1800029ed  jz      short loc_180002A0A
0x1800029ef  mov     dword ptr [rsp+88h+var_60], ebx
0x1800029f3  lea     rdx, _FlowControl_Originate
0x1800029fa  mov     r9, rdi
0x1800029fd  mov     [rsp+88h+var_68], rbp
0x180002a02  mov     r8d, esi
0x180002a05  call    McTemplateU0dspd_EventWriteTransfer
0x180002a0a  cmp     cs:?s_fShouldSpewDebug@@3HA, 0; int s_fShouldSpewDebug
0x180002a11  jz      short loc_180002A43
0x180002a13  call    cs:__imp_IsDebuggerPresent
0x180002a19  test    eax, eax
0x180002a1b  jz      short loc_180002A43
0x180002a1d  mov     dword ptr [rsp+88h+var_58], ebx
0x180002a21  lea     r8, aZO; "[Z!O] "
0x180002a28  mov     dword ptr [rsp+88h+var_60], esi
0x180002a2c  lea     rdx, aSSPOriginated0; "%s:%s@%p: originated %08x (%d)"
0x180002a33  mov     r9, rdi
0x180002a36  mov     [rsp+88h+var_68], rbp
0x180002a3b  mov     rcx, r14; this
0x180002a3e  call    ?DebugMsg@ZTracer@@QEAAXPEBDZZ; ZTracer::DebugMsg(char const *,...)
0x180002a43  add     rsp, 60h
0x180002a47  pop     r14
0x180002a49  pop     rdi
0x180002a4a  pop     rsi
0x180002a4b  pop     rbp
0x180002a4c  pop     rbx
0x180002a4d  retn
```
