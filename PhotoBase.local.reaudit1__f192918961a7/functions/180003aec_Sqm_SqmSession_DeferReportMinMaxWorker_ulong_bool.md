# Sqm::SqmSession::DeferReportMinMaxWorker(ulong,bool)

- ea: `0x180003aec`
- end: `0x180003b99`
- name: `?DeferReportMinMaxWorker@SqmSession@Sqm@@AEAAXK_N@Z`
- size: `173`
- prototype: `void(Sqm::SqmSession *__hidden this, unsigned int, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180003824`
- `0x180003ad4`

## callees

- `0x180003aec`
- `0x180003e94`
- `0x1800049c0`
- `0x180005fbc`
- `0x180006e1c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180003b83`
- `KERNEL32!LeaveCriticalSection` at `0x180003b83`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Sqm::SqmSession::DeferReportMinMaxWorker(Sqm::SqmSession *this, unsigned int a2, char a3)
{
  __int64 *v6; // rdi
  __int64 v7; // rax
  struct _GUID *v8; // rdx
  const struct _EVENT_DESCRIPTOR *v9; // rcx
  __int64 v10; // rax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-18h] BYREF
  char v12; // [rsp+28h] [rbp-10h]

  if ( *((_BYTE *)this + 145) )
  {
    lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 344);
    v12 = 0;
    ATL::CCritSecLock::Lock(&lpCriticalSection);
    v6 = (__int64 *)((char *)this + 224);
    v7 = ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::Find(
           v6,
           a2);
    if ( v7 )
    {
      v9 = &SQM_SETIFMIN_DWORD_V0;
      if ( !a3 )
        v9 = &SQM_SETIFMAX_DWORD_V0;
      _WinSqmDWORDEvent(v9, v8, a2, *(_DWORD *)(v7 + 4));
      v10 = ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::Find(
              v6,
              a2);
      if ( v10 )
        ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::RemoveAt(
          v6,
          v10);
    }
    if ( v12 )
      LeaveCriticalSection(lpCriticalSection);
  }
}

```

## disassembly

```asm
0x180003aec  mov     r11, rsp
0x180003aef  mov     [r11+8], rbx
0x180003af3  mov     [r11+10h], rsi
0x180003af7  push    rdi
0x180003af8  sub     rsp, 30h
0x180003afc  mov     sil, r8b
0x180003aff  mov     ebx, edx
0x180003b01  mov     rdi, rcx
0x180003b04  cmp     byte ptr [rcx+91h], 0
0x180003b0b  jz      short loc_180003B89
0x180003b0d  lea     rax, [rcx+158h]
0x180003b14  mov     [r11-18h], rax
0x180003b18  mov     [rsp+38h+var_10], 0
0x180003b1d  lea     rcx, [r11-18h]; this
0x180003b21  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x180003b26  nop
0x180003b27  add     rdi, 0E0h
0x180003b2e  mov     edx, ebx
0x180003b30  mov     rcx, rdi
0x180003b33  call    ?Find@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@IEBAPEAVCNode@12@K@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::Find(ulong)
0x180003b38  test    rax, rax
0x180003b3b  jz      short loc_180003B77
0x180003b3d  mov     r9d, [rax+4]; unsigned int
0x180003b41  mov     r8d, ebx; unsigned int
0x180003b44  test    sil, sil
0x180003b47  lea     rcx, SQM_SETIFMIN_DWORD_V0
0x180003b4e  jnz     short loc_180003B57
0x180003b50  lea     rcx, SQM_SETIFMAX_DWORD_V0; struct _EVENT_DESCRIPTOR *
0x180003b57  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180003b5c  mov     edx, ebx
0x180003b5e  mov     rcx, rdi
0x180003b61  call    ?Find@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@IEBAPEAVCNode@12@K@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::Find(ulong)
0x180003b66  test    rax, rax
0x180003b69  jz      short loc_180003B77
0x180003b6b  mov     rdx, rax
0x180003b6e  mov     rcx, rdi
0x180003b71  call    ?RemoveAt@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::RemoveAt(__POSITION *)
0x180003b76  nop
0x180003b77  cmp     [rsp+38h+var_10], 0
0x180003b7c  jz      short loc_180003B89
0x180003b7e  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x180003b83  call    cs:__imp_LeaveCriticalSection
0x180003b89  mov     rbx, [rsp+38h+arg_0]
0x180003b8e  mov     rsi, [rsp+38h+arg_8]
0x180003b93  add     rsp, 30h
0x180003b97  pop     rdi
0x180003b98  retn
```
