# ZTracer::ReportPropagation(int,char const *,int,void const *)

- ea: `0x180002a54`
- end: `0x180002bce`
- name: `?ReportPropagation@ZTracer@@QEAAXHPEBDHPEBX@Z`
- size: `378`
- prototype: `void __fastcall(ZTracer *__hidden this, int, const char *, int, const void *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800034a0`
- `0x1800034e0`
- `0x180003520`

## callees

- `0x180001184`
- `0x1800024bc`
- `0x180002a54`
- `0x180002d8c`
- `0x1800037b4`
- `0x180003854`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002b35`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002b93`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002b35`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002b93`

## pseudocode

```c
void __fastcall ZTracer::ReportPropagation(ZTracer *this, int a2, const char *a3, int a4, const void *a5)
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
          (__int64)byte_180005B9D,
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
      McTemplateU0dsd_EventWriteTransfer(v9, (unsigned int)FlowControl_PropagateNoThis, a2, (_DWORD)a3, a4);
    if ( s_fShouldSpewDebug )
    {
      if ( IsDebuggerPresent() )
        ZTracer::DebugMsg(this, "%s:%s: originated %08x (%d)", "[Z!P] ", a3, a2, a4);
    }
  }
  else
  {
    if ( (Microsoft_Windows_ZTraceMapsEnableBits & 1) != 0 )
      McTemplateU0dspd_EventWriteTransfer(v9, (unsigned int)FlowControl_Propagate, a2, (_DWORD)a3, (char)a5, a4);
    if ( s_fShouldSpewDebug && IsDebuggerPresent() )
      ZTracer::DebugMsg(this, "%s:%s@%p: originated %08x (%d)", "[Z!P] ", a3, a5, a2, a4);
  }
}

```

## disassembly

```asm
0x180002a54  push    rbx
0x180002a56  push    rbp
0x180002a57  push    rsi
0x180002a58  push    rdi
0x180002a59  push    r14
0x180002a5b  sub     rsp, 60h
0x180002a5f  mov     ebx, r9d
0x180002a62  mov     rdi, r8
0x180002a65  mov     esi, edx
0x180002a67  mov     r14, rcx
0x180002a6a  mov     r8d, ebx; int
0x180002a6d  mov     rdx, rdi; char *
0x180002a70  mov     ecx, esi; int
0x180002a72  xor     r9d, r9d; char *
0x180002a75  call    ?UnderErrorUploadLimit@@YAHHPEBDH0@Z; UnderErrorUploadLimit(int,char const *,int,char const *)
0x180002a7a  test    eax, eax
0x180002a7c  jz      short loc_180002AFB
0x180002a7e  mov     eax, cs:dword_180007000
0x180002a84  cmp     eax, 5
0x180002a87  jbe     short loc_180002AFB
0x180002a89  mov     rcx, cs:qword_180007018
0x180002a90  mov     rdx, 400000000000h
0x180002a9a  mov     rax, cs:qword_180007010
0x180002aa1  test    rdx, rax
0x180002aa4  jz      short loc_180002AFB
0x180002aa6  mov     rax, rcx
0x180002aa9  and     rax, rdx
0x180002aac  cmp     rax, rcx
0x180002aaf  jnz     short loc_180002AFB
0x180002ab1  lea     rax, [rsp+88h+var_40]
0x180002ab6  mov     [rsp+88h+var_40], 3000000h
0x180002abf  mov     [rsp+88h+var_50], rax
0x180002ac4  lea     rdx, byte_180005B9D
0x180002acb  lea     rax, [rsp+88h+var_48]
0x180002ad0  mov     [rsp+88h+var_48], ebx
0x180002ad4  mov     [rsp+88h+var_58], rax
0x180002ad9  lea     rax, [rsp+88h+var_38]
0x180002ade  mov     [rsp+88h+var_60], rax
0x180002ae3  lea     rax, [rsp+88h+var_44]
0x180002ae8  mov     [rsp+88h+var_68], rax
0x180002aed  mov     [rsp+88h+var_38], rdi
0x180002af2  mov     [rsp+88h+var_44], esi
0x180002af6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180002afb  mov     rbp, [rsp+88h+arg_20]
0x180002b03  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180002b07  jnz     short loc_180002B66
0x180002b09  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 1
0x180002b10  jz      short loc_180002B28
0x180002b12  mov     r9, rdi
0x180002b15  mov     dword ptr [rsp+88h+var_68], ebx
0x180002b19  mov     r8d, esi
0x180002b1c  lea     rdx, _FlowControl_PropagateNoThis
0x180002b23  call    McTemplateU0dsd_EventWriteTransfer
0x180002b28  cmp     cs:?s_fShouldSpewDebug@@3HA, 0; int s_fShouldSpewDebug
0x180002b2f  jz      loc_180002BC3
0x180002b35  call    cs:__imp_IsDebuggerPresent
0x180002b3b  test    eax, eax
0x180002b3d  jz      loc_180002BC3
0x180002b43  mov     dword ptr [rsp+88h+var_60], ebx
0x180002b47  lea     r8, aZP; "[Z!P] "
0x180002b4e  mov     r9, rdi
0x180002b51  mov     dword ptr [rsp+88h+var_68], esi
0x180002b55  lea     rdx, aSSOriginated08; "%s:%s: originated %08x (%d)"
0x180002b5c  mov     rcx, r14; this
0x180002b5f  call    ?DebugMsg@ZTracer@@QEAAXPEBDZZ; ZTracer::DebugMsg(char const *,...)
0x180002b64  jmp     short loc_180002BC3
0x180002b66  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 1
0x180002b6d  jz      short loc_180002B8A
0x180002b6f  mov     dword ptr [rsp+88h+var_60], ebx
0x180002b73  lea     rdx, _FlowControl_Propagate
0x180002b7a  mov     r9, rdi
0x180002b7d  mov     [rsp+88h+var_68], rbp
0x180002b82  mov     r8d, esi
0x180002b85  call    McTemplateU0dspd_EventWriteTransfer
0x180002b8a  cmp     cs:?s_fShouldSpewDebug@@3HA, 0; int s_fShouldSpewDebug
0x180002b91  jz      short loc_180002BC3
0x180002b93  call    cs:__imp_IsDebuggerPresent
0x180002b99  test    eax, eax
0x180002b9b  jz      short loc_180002BC3
0x180002b9d  mov     dword ptr [rsp+88h+var_58], ebx
0x180002ba1  lea     r8, aZP; "[Z!P] "
0x180002ba8  mov     dword ptr [rsp+88h+var_60], esi
0x180002bac  lea     rdx, aSSPOriginated0; "%s:%s@%p: originated %08x (%d)"
0x180002bb3  mov     r9, rdi
0x180002bb6  mov     [rsp+88h+var_68], rbp
0x180002bbb  mov     rcx, r14; this
0x180002bbe  call    ?DebugMsg@ZTracer@@QEAAXPEBDZZ; ZTracer::DebugMsg(char const *,...)
0x180002bc3  add     rsp, 60h
0x180002bc7  pop     r14
0x180002bc9  pop     rdi
0x180002bca  pop     rsi
0x180002bcb  pop     rbp
0x180002bcc  pop     rbx
0x180002bcd  retn
```
