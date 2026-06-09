# WindowsPerformanceRecorder::CControlManager::GetPersistedAutoLoggerKey(ushort *,ulong,bool,ushort const *)

- ea: `0x180048860`
- end: `0x1800488f9`
- name: `?GetPersistedAutoLoggerKey@CControlManager@WindowsPerformanceRecorder@@AEBAJPEAGK_NPEBG@Z`
- size: `153`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, unsigned __int16 *, unsigned int, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180034afc`

## callees

- `0x180009b40`
- `0x180048860`
- `0x18008c010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800488dc`
- `ntdll!RtlNtStatusToDosError` at `0x1800488dc`

## string_xrefs

- `0x1800488b9`: `ETWGlobalLoggerPath`
- `0x1800488a7`: `ETWAutoLoggerPath`

## pseudocode

```c
signed int __fastcall WindowsPerformanceRecorder::CControlManager::GetPersistedAutoLoggerKey(
        WindowsPerformanceRecorder::CControlManager *this,
        unsigned __int16 *a2,
        __int64 a3,
        char a4,
        const unsigned __int16 *a5)
{
  __int128 v7; // xmm1
  signed int result; // eax
  __int64 (__fastcall *v9)(const wchar_t *, const unsigned __int16 *, unsigned __int16 *, __int64, _QWORD); // rax
  const wchar_t *v10; // rcx
  NTSTATUS v11; // eax
  _OWORD v12[2]; // [rsp+30h] [rbp-28h] BYREF

  v7 = *(_OWORD *)((char *)this + 360);
  v12[0] = *(_OWORD *)((char *)this + 344);
  v12[1] = v7;
  if ( !Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)(v12) )
    return -2147467259;
  v9 = (__int64 (__fastcall *)(const wchar_t *, const unsigned __int16 *, unsigned __int16 *, __int64, _QWORD))Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)(v12);
  v10 = L"ETWGlobalLoggerPath";
  if ( !a4 )
    v10 = L"ETWAutoLoggerPath";
  v11 = v9(v10, a5, a2, 520, 0);
  result = RtlNtStatusToDosError(v11);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180048860  mov     rax, rsp
0x180048863  mov     [rax+8], rbx
0x180048867  push    rdi
0x180048868  sub     rsp, 50h
0x18004886c  movups  xmm0, xmmword ptr [rcx+158h]
0x180048873  mov     bl, r9b
0x180048876  mov     rdi, rdx
0x180048879  movups  xmm1, xmmword ptr [rcx+168h]
0x180048880  lea     rcx, [rax-28h]
0x180048884  movups  xmmword ptr [rax-28h], xmm0
0x180048888  movups  xmmword ptr [rax-18h], xmm1
0x18004888c  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x180048891  test    rax, rax
0x180048894  jnz     short loc_18004889D
0x180048896  mov     eax, 80004005h
0x18004889b  jmp     short loc_1800488EE
0x18004889d  lea     rcx, [rsp+58h+var_28]
0x1800488a2  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x1800488a7  lea     rdx, aEtwautologgerp; "ETWAutoLoggerPath"
0x1800488ae  mov     [rsp+58h+var_38], 0
0x1800488b7  test    bl, bl
0x1800488b9  lea     rcx, aEtwgloballogge; "ETWGlobalLoggerPath"
0x1800488c0  mov     r9d, 208h
0x1800488c6  mov     r8, rdi
0x1800488c9  cmovz   rcx, rdx
0x1800488cd  mov     rdx, [rsp+58h+arg_20]
0x1800488d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488da  mov     ecx, eax; Status
0x1800488dc  call    cs:__imp_RtlNtStatusToDosError
0x1800488e2  test    eax, eax
0x1800488e4  jle     short loc_1800488EE
0x1800488e6  movzx   eax, ax
0x1800488e9  or      eax, 80070000h
0x1800488ee  mov     rbx, [rsp+58h+arg_0]
0x1800488f3  add     rsp, 50h
0x1800488f7  pop     rdi
0x1800488f8  retn
```
