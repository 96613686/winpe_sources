# CPersistedControl::OnNotify(ulong,_GUID const *)

- ea: `0x18002ee60`
- end: `0x18002f02f`
- name: `?OnNotify@CPersistedControl@@EEAAJKPEBU_GUID@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(CPersistedControl *this, __int64, const struct _GUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18001ff7c`
- `0x180022e08`
- `0x18002ee60`
- `0x18003e920`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f00a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f00a`
- `ntdll!EtwEventWriteTransfer` at `0x18002efd2`
- `ntdll!EtwEventWriteTransfer` at `0x18002efd2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002eff2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002eff2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistedControl::OnNotify(CPersistedControl *this, __int64 a2, const struct _GUID *a3)
{
  __int64 v4; // r10
  const WCHAR *v5; // rcx
  __int64 v6; // rax
  int v8; // eax
  struct _TP_TIMER *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-59h] BYREF
  __int64 v12; // [rsp+38h] [rbp-51h] BYREF
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp-49h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-41h] BYREF
  char v15; // [rsp+50h] [rbp-39h]
  _DWORD v16[2]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v17; // [rsp+60h] [rbp-29h]
  unsigned __int16 *v18; // [rsp+70h] [rbp-19h] BYREF
  int v19; // [rsp+78h] [rbp-11h]
  int v20; // [rsp+7Ch] [rbp-Dh]
  __int16 *v21; // [rsp+80h] [rbp-9h]
  int v22; // [rsp+88h] [rbp-1h]
  int v23; // [rsp+8Ch] [rbp+3h]
  const WCHAR *v24; // [rsp+90h] [rbp+7h]
  int v25; // [rsp+98h] [rbp+Fh]
  int v26; // [rsp+9Ch] [rbp+13h]
  __int64 *v27; // [rsp+A0h] [rbp+17h]
  __int64 v28; // [rsp+A8h] [rbp+1Fh]
  char *v29; // [rsp+B0h] [rbp+27h]
  __int64 v30; // [rsp+B8h] [rbp+2Fh]
  __int64 *v31; // [rsp+C0h] [rbp+37h]
  __int64 v32; // [rsp+C8h] [rbp+3Fh]

  if ( !a3 || *(_QWORD *)&a3->Data1 != EVENTCONTEXT_PERSIST || *(_QWORD *)a3->Data4 != 0xFC0CED802AAEF9A1uLL )
  {
    lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 16);
    pftDueTime = 0;
    v15 = 0;
    ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&lpCriticalSection);
    v4 = *((_QWORD *)AudioEndpointBuilderTelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v4 > 4u )
    {
      v5 = (const WCHAR *)*((_QWORD *)this + 9);
      LOBYTE(v11) = *((_BYTE *)this + 92);
      HIDWORD(v11) = *((_DWORD *)this + 22);
      LODWORD(v12) = *((_DWORD *)this + 16);
      v31 = &v11;
      v29 = (char *)&v11 + 4;
      v27 = &v12;
      v32 = 1;
      v30 = 4;
      v28 = 4;
      if ( v5 )
      {
        v6 = -1;
        while ( v5[++v6] != 0 )
          ;
        v8 = 2 * v6 + 2;
      }
      else
      {
        v5 = &LocaleName;
        v8 = 2;
      }
      v25 = v8;
      v16[1] = 4;
      v18 = *(unsigned __int16 **)(v4 + 8);
      v24 = v5;
      v26 = 0;
      v16[0] = 184549376;
      v17 = 0;
      v19 = *v18;
      v21 = &word_180077886;
      v20 = 2;
      v22 = 91;
      v23 = 1;
      HIDWORD(v12) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD))EtwEventWriteTransfer)(
        *(_QWORD *)(v4 + 32),
        v16,
        0,
        0,
        6,
        &v18,
        v11,
        v12,
        pftDueTime);
    }
    v9 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
    *((_BYTE *)this + 92) = 1;
    pftDueTime = (struct _FILETIME)-10000000LL;
    SetThreadpoolTimer(v9, &pftDueTime, 0, 0);
    if ( v15 )
      LeaveCriticalSection(lpCriticalSection);
  }
  return 0;
}

```

## disassembly

```asm
0x18002ee60  mov     [rsp-8+arg_10], rbx
0x18002ee65  push    rbp
0x18002ee66  lea     rbp, [rsp-57h]
0x18002ee6b  sub     rsp, 0E0h
0x18002ee72  mov     rax, cs:__security_cookie
0x18002ee79  xor     rax, rsp
0x18002ee7c  mov     [rbp+57h+var_10], rax
0x18002ee80  mov     rbx, rcx
0x18002ee83  test    r8, r8
0x18002ee86  jz      short loc_18002EEA5
0x18002ee88  mov     rax, [r8]
0x18002ee8b  cmp     rax, cs:EVENTCONTEXT_PERSIST
0x18002ee92  jnz     short loc_18002EEA5
0x18002ee94  mov     rax, [r8+8]
0x18002ee98  cmp     rax, cs:qword_180070DE8
0x18002ee9f  jz      loc_18002F010
0x18002eea5  lea     rax, [rcx+10h]
0x18002eea9  mov     [rsp+0E0h+arg_8], rdi
0x18002eeb1  xor     edi, edi
0x18002eeb3  mov     [rbp+57h+lpCriticalSection], rax
0x18002eeb7  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x18002eebb  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], rdi
0x18002eebf  mov     [rbp+57h+var_90], dil
0x18002eec3  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x18002eec8  call    ?Instance@AudioEndpointBuilderTelemetryProvider@@KAPEAV1@XZ; AudioEndpointBuilderTelemetryProvider::Instance(void)
0x18002eecd  mov     r10, [rax+8]
0x18002eed1  mov     eax, [r10]
0x18002eed4  cmp     eax, 4
0x18002eed7  jbe     loc_18002EFD8
0x18002eedd  movzx   eax, byte ptr [rbx+5Ch]
0x18002eee1  mov     rcx, [rbx+48h]
0x18002eee5  mov     [rbp+57h+var_B0], al
0x18002eee8  mov     eax, [rbx+58h]
0x18002eeeb  mov     [rbp+57h+var_AC], eax
0x18002eeee  mov     eax, [rbx+40h]
0x18002eef1  mov     [rbp+57h+var_A8], eax
0x18002eef4  lea     rax, [rbp+57h+var_B0]
0x18002eef8  mov     [rbp+57h+var_20], rax
0x18002eefc  lea     rax, [rbp+57h+var_AC]
0x18002ef00  mov     [rbp+57h+var_30], rax
0x18002ef04  lea     rax, [rbp+57h+var_A8]
0x18002ef08  mov     [rbp+57h+var_40], rax
0x18002ef0c  mov     [rbp+57h+var_18], 1
0x18002ef14  mov     [rbp+57h+var_28], 4
0x18002ef1c  mov     [rbp+57h+var_38], 4
0x18002ef24  test    rcx, rcx
0x18002ef27  jz      short loc_18002EF44
0x18002ef29  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002ef30  cmp     [rcx+rax*2+2], di
0x18002ef35  lea     rax, [rax+1]
0x18002ef39  jnz     short loc_18002EF30
0x18002ef3b  lea     eax, ds:2[rax*2]
0x18002ef42  jmp     short loc_18002EF50
0x18002ef44  lea     rcx, LocaleName
0x18002ef4b  mov     eax, 2
0x18002ef50  mov     [rbp+57h+var_48], eax
0x18002ef53  lea     rdx, [rbp+57h+var_88]
0x18002ef57  movzx   eax, cs:word_18007787C
0x18002ef5e  xor     r9d, r9d
0x18002ef61  mov     [rbp+57h+var_84], eax
0x18002ef64  xor     r8d, r8d
0x18002ef67  mov     rax, [r10+8]
0x18002ef6b  mov     [rbp+57h+var_70], rax
0x18002ef6f  mov     [rbp+57h+var_50], rcx
0x18002ef73  lea     rcx, _TraceLoggingMetadata
0x18002ef7a  mov     [rbp+57h+var_44], edi
0x18002ef7d  mov     [rbp+57h+var_88], 0B000000h
0x18002ef84  mov     [rbp+57h+var_80], rdi
0x18002ef88  movzx   eax, word ptr [rax]
0x18002ef8b  mov     [rbp+57h+var_68], eax
0x18002ef8e  lea     rax, word_180077886
0x18002ef95  mov     [rbp+57h+var_60], rax
0x18002ef99  lea     rax, _TraceLoggingMetadataEnd
0x18002efa0  sub     eax, ecx
0x18002efa2  mov     [rbp+57h+var_64], 2
0x18002efa9  mov     [rbp+57h+var_58], 5Bh ; '['
0x18002efb0  mov     [rbp+57h+var_54], 1
0x18002efb7  mov     [rbp+57h+var_A4], eax
0x18002efba  mov     eax, [rbp+57h+var_A4]
0x18002efbd  mov     rcx, [r10+20h]
0x18002efc1  lea     rax, [rbp+57h+var_70]
0x18002efc5  mov     [rsp+0E0h+var_B8], rax
0x18002efca  mov     [rsp+0E0h+var_C0], 6
0x18002efd2  call    cs:__imp_EtwEventWriteTransfer
0x18002efd8  mov     rcx, [rbx+38h]; pti
0x18002efdc  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x18002efe0  xor     r9d, r9d; msWindowLength
0x18002efe3  mov     byte ptr [rbx+5Ch], 1
0x18002efe7  xor     r8d, r8d; msPeriod
0x18002efea  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], 0FFFFFFFFFF676980h
0x18002eff2  call    cs:__imp_SetThreadpoolTimer
0x18002eff8  cmp     [rbp+57h+var_90], 0
0x18002effc  mov     rdi, [rsp+0E0h+arg_8]
0x18002f004  jz      short loc_18002F010
0x18002f006  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18002f00a  call    cs:__imp_LeaveCriticalSection
0x18002f010  xor     eax, eax
0x18002f012  mov     rcx, [rbp+57h+var_10]
0x18002f016  xor     rcx, rsp; StackCookie
0x18002f019  call    __security_check_cookie
0x18002f01e  mov     rbx, [rsp+0E0h+arg_10]
0x18002f026  add     rsp, 0E0h
0x18002f02d  pop     rbp
0x18002f02e  retn
```
