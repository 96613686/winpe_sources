# CPenProcess::Relinquish(void)

- ea: `0x18002d13c`
- end: `0x18002d21f`
- name: `?Relinquish@CPenProcess@@QEAAHXZ`
- size: `227`
- prototype: `__int64 __fastcall(CPenProcess *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800286b0`

## callees

- `0x1800010f8`
- `0x180012dc0`
- `0x180015630`
- `0x18001a508`
- `0x18002b4cc`
- `0x18002d13c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d19a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d19a`

## string_xrefs

- `0x18002d1cf`: `PENSERVICE_CPenProcess::Relinquish`

## pseudocode

```c
__int64 __fastcall CPenProcess::Relinquish(CPenProcess *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  void **v4; // rdi

  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v2,
      (int)&dword_18003AB9C);
  v3 = (void *)*((_QWORD *)this + 136);
  v4 = (void **)((char *)this + 1096);
  if ( !v3 )
  {
    v3 = *v4;
    if ( !*v4 )
      return 0;
  }
  if ( !WaitForSingleObject(v3, 0) )
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
      WPP_SF_sS(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        20,
        (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
        (unsigned int)"PENSERVICE_CPenProcess::Relinquish",
        (__int64)this + 36);
    *((_DWORD *)this + 270) = 4;
    SH<void *,SH_HANDLE>::Reset((char *)this + 1088);
    SafeReleaseAndCloseMutex((void **)this + 137);
    *((_DWORD *)this + 271) = 0;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18002d13c  mov     [rsp+arg_0], rbx
0x18002d141  mov     [rsp+arg_8], rsi
0x18002d146  push    rdi
0x18002d147  sub     rsp, 30h
0x18002d14b  mov     eax, cs:dword_1800411A8
0x18002d151  mov     rbx, rcx
0x18002d154  cmp     eax, 5
0x18002d157  jbe     short loc_18002D17A
0x18002d159  mov     edx, 4000000h
0x18002d15e  lea     rcx, dword_1800411A8
0x18002d165  call    _tlgKeywordOn
0x18002d16a  test    al, al
0x18002d16c  jz      short loc_18002D17A
0x18002d16e  lea     rdx, dword_18003AB9C
0x18002d175  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002d17a  lea     rsi, [rbx+440h]
0x18002d181  mov     rcx, [rsi]
0x18002d184  lea     rdi, [rbx+448h]
0x18002d18b  test    rcx, rcx
0x18002d18e  jnz     short loc_18002D198
0x18002d190  mov     rcx, [rdi]; hHandle
0x18002d193  test    rcx, rcx
0x18002d196  jz      short loc_18002D206
0x18002d198  xor     edx, edx; dwMilliseconds
0x18002d19a  call    cs:__imp_WaitForSingleObject
0x18002d1a0  test    eax, eax
0x18002d1a2  jnz     short loc_18002D20A
0x18002d1a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1ab  lea     rax, WPP_GLOBAL_Control
0x18002d1b2  cmp     rcx, rax
0x18002d1b5  jz      short loc_18002D1E2
0x18002d1b7  test    byte ptr [rcx+1Ch], 10h
0x18002d1bb  jz      short loc_18002D1E2
0x18002d1bd  mov     rcx, [rcx+10h]
0x18002d1c1  lea     rax, [rbx+24h]
0x18002d1c5  mov     edx, 14h
0x18002d1ca  mov     [rsp+38h+var_18], rax
0x18002d1cf  lea     r9, aPenserviceCpen_8; "PENSERVICE_CPenProcess::Relinquish"
0x18002d1d6  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x18002d1dd  call    WPP_SF_sS
0x18002d1e2  mov     rcx, rsi
0x18002d1e5  mov     dword ptr [rbx+438h], 4
0x18002d1ef  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18002d1f4  mov     rcx, rdi; void **
0x18002d1f7  call    ?SafeReleaseAndCloseMutex@@YAXAEAPEAX@Z; SafeReleaseAndCloseMutex(void * &)
0x18002d1fc  mov     dword ptr [rbx+43Ch], 0
0x18002d206  xor     eax, eax
0x18002d208  jmp     short loc_18002D20F
0x18002d20a  mov     eax, 1
0x18002d20f  mov     rbx, [rsp+38h+arg_0]
0x18002d214  mov     rsi, [rsp+38h+arg_8]
0x18002d219  add     rsp, 30h
0x18002d21d  pop     rdi
0x18002d21e  retn
```
