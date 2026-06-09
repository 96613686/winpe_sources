# PrivLogTelemetry::PrivLogTraceLoggingWrite(char const *,int,uchar *,ulong,ushort)

- ea: `0x1800565b4`
- end: `0x1800566d0`
- name: `?PrivLogTraceLoggingWrite@PrivLogTelemetry@@YAXPEBDHPEAEKG@Z`
- size: `284`
- prototype: `void __fastcall(PrivLogTelemetry *__hidden this, const char *, int, unsigned __int8 *, char, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180054e60`

## callees

- `0x180001008`
- `0x1800013ec`
- `0x18000f114`
- `0x1800565b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180056606`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180056606`

## string_xrefs

- `0x1800565e1`: `PrivLogTraceLoggingWrite called without a registered provider`
- `0x1800565e8`: `PrivLogTelemetry::PrivLogTraceLoggingWrite`

## pseudocode

```c
void __fastcall PrivLogTelemetry::PrivLogTraceLoggingWrite(
        PrivLogTelemetry *this,
        const char *a2,
        __int64 a3,
        unsigned __int8 *a4,
        char a5)
{
  int v5; // ebx
  int v7; // esi
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  __int16 v12[2]; // [rsp+60h] [rbp-11h] BYREF
  int v13; // [rsp+64h] [rbp-Dh] BYREF
  int v14; // [rsp+68h] [rbp-9h] BYREF
  PrivLogTelemetry *v15; // [rsp+70h] [rbp-1h] BYREF
  __int64 v16; // [rsp+78h] [rbp+7h] BYREF
  __int64 v17; // [rsp+80h] [rbp+Fh] BYREF
  int v18; // [rsp+88h] [rbp+17h]
  char *v19; // [rsp+90h] [rbp+1Fh] BYREF
  int v20; // [rsp+98h] [rbp+27h]

  v5 = (int)a4;
  v7 = (int)a2;
  if ( dword_180081368 )
  {
    if ( !dword_18008136C )
      dword_18008136C = GetCurrentProcessId();
    if ( (unsigned int)dword_1800804F0 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1800804F0, 0x400000000000LL, a3, a4) )
      {
        v17 = a3;
        v19 = &a5;
        v13 = dword_18008136C;
        v12[0] = 1;
        v16 = 0x80000000LL;
        v18 = v5;
        v20 = 2;
        v14 = v7;
        v15 = this;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
          v9,
          (unsigned int)word_180077B7A,
          v10,
          v11,
          (__int64)&v16,
          (__int64)v12,
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&v13,
          (__int64)&v19,
          (__int64)&v17);
      }
    }
  }
  else
  {
    AslLogCallPrintf(
      1,
      "PrivLogTelemetry::PrivLogTraceLoggingWrite",
      18,
      "PrivLogTraceLoggingWrite called without a registered provider");
  }
}

```

## disassembly

```asm
0x1800565b4  push    rbp
0x1800565b6  push    rbx
0x1800565b7  push    rsi
0x1800565b8  push    rdi
0x1800565b9  push    r14
0x1800565bb  lea     rbp, [rsp-2Fh]
0x1800565c0  sub     rsp, 0A0h
0x1800565c7  cmp     cs:dword_180081368, 0
0x1800565ce  mov     ebx, r9d
0x1800565d1  mov     rdi, r8
0x1800565d4  mov     esi, edx
0x1800565d6  mov     r14, rcx
0x1800565d9  jnz     short loc_1800565FD
0x1800565db  mov     r8d, 12h
0x1800565e1  lea     r9, aPrivlogtracelo; "PrivLogTraceLoggingWrite called without"...
0x1800565e8  lea     rdx, aPrivlogtelemet; "PrivLogTelemetry::PrivLogTraceLoggingWr"...
0x1800565ef  lea     ecx, [r8-11h]
0x1800565f3  call    AslLogCallPrintf
0x1800565f8  jmp     loc_1800566C2
0x1800565fd  cmp     cs:dword_18008136C, 0
0x180056604  jnz     short loc_180056612
0x180056606  call    cs:__imp_GetCurrentProcessId
0x18005660c  mov     cs:dword_18008136C, eax
0x180056612  mov     eax, cs:dword_1800804F0
0x180056618  cmp     eax, 5
0x18005661b  jbe     loc_1800566C2
0x180056621  mov     rdx, 400000000000h
0x18005662b  lea     rcx, dword_1800804F0
0x180056632  call    _tlgKeywordOn
0x180056637  test    al, al
0x180056639  jz      loc_1800566C2
0x18005663f  lea     rax, [rbp+4Fh+arg_20]
0x180056643  mov     [rbp+4Fh+var_40], rdi
0x180056647  mov     [rbp+4Fh+var_30], rax
0x18005664b  lea     rdx, word_180077B7A
0x180056652  mov     eax, cs:dword_18008136C
0x180056658  mov     [rbp+4Fh+var_5C], eax
0x18005665b  mov     eax, 1
0x180056660  mov     [rbp+4Fh+var_60], ax
0x180056664  mov     eax, 80000000h
0x180056669  mov     [rbp+4Fh+var_48], rax
0x18005666d  lea     rax, [rbp+4Fh+var_40]
0x180056671  mov     [rsp+0C0h+var_70], rax
0x180056676  lea     rax, [rbp+4Fh+var_30]
0x18005667a  mov     [rsp+0C0h+var_78], rax
0x18005667f  lea     rax, [rbp+4Fh+var_5C]
0x180056683  mov     [rsp+0C0h+var_80], rax
0x180056688  lea     rax, [rbp+4Fh+var_58]
0x18005668c  mov     [rsp+0C0h+var_88], rax
0x180056691  lea     rax, [rbp+4Fh+var_50]
0x180056695  mov     [rsp+0C0h+var_90], rax
0x18005669a  lea     rax, [rbp+4Fh+var_60]
0x18005669e  mov     [rsp+0C0h+var_98], rax
0x1800566a3  lea     rax, [rbp+4Fh+var_48]
0x1800566a7  mov     [rsp+0C0h+var_A0], rax
0x1800566ac  mov     [rbp+4Fh+var_38], ebx
0x1800566af  mov     [rbp+4Fh+var_28], 2
0x1800566b6  mov     [rbp+4Fh+var_58], esi
0x1800566b9  mov     [rbp+4Fh+var_50], r14
0x1800566bd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U4@U_tlgWrapperPtrSize@@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@6AEBU_tlgWrapperPtrSize@@7@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &)
0x1800566c2  add     rsp, 0A0h
0x1800566c9  pop     r14
0x1800566cb  pop     rdi
0x1800566cc  pop     rsi
0x1800566cd  pop     rbx
0x1800566ce  pop     rbp
0x1800566cf  retn
```
