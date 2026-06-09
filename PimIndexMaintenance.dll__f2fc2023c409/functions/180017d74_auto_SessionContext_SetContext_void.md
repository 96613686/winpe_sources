# auto_SessionContext::SetContext(void)

- ea: `0x180017d74`
- end: `0x180017e26`
- name: `?SetContext@auto_SessionContext@@QEAAJXZ`
- size: `178`
- prototype: `__int64 __fastcall(auto_SessionContext *__hidden this)`
- caller_count: `20`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800168e8`
- `0x180016a70`
- `0x180016b68`
- `0x180016db0`
- `0x180016f5c`
- `0x18001706c`
- `0x1800173c4`
- `0x180017638`
- `0x1800177fc`
- `0x180017e2c`
- `0x180017ec8`
- `0x180017f74`
- `0x1800180c4`
- `0x1800183b4`
- `0x180018630`
- `0x180018778`
- `0x180018be4`
- `0x180018c98`
- `0x180018f58`
- `0x180019254`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x18000ee40`
- `0x180010638`
- `0x180017d74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017db5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017db5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017dd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017dd3`
- `ESENT!JetSetSessionContext` at `0x180017dde`
- `ESENT!JetSetSessionContext` at `0x180017dde`

## string_xrefs

- `0x180017d9b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180017dc7`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180017dfc`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall auto_SessionContext::SetContext(LPCRITICAL_SECTION *this)
{
  int v2; // eax
  unsigned int v3; // edi
  __int64 v5; // rcx
  DWORD CurrentThreadId; // eax
  JET_ERR v7; // eax
  unsigned int HresultFromJetError; // ebx

  v2 = ESEDataSource::EnsureDBInitialized((ESEDataSource *)&g_dataSource, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    Log_HREvent(
      (unsigned int)v2,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      31);
    return v3;
  }
  EnterCriticalSection(this[2]);
  if ( *this == (LPCRITICAL_SECTION)-1LL )
    Log_AssertionEvent(
      v5,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      35);
  CurrentThreadId = GetCurrentThreadId();
  v7 = JetSetSessionContext((JET_SESID)*this, CurrentThreadId);
  if ( v7 != -1912 )
  {
    if ( v7 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v7);
      Log_HREvent(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
        45);
      return HresultFromJetError;
    }
    *((_DWORD *)this + 2) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180017d74  mov     [rsp+arg_0], rbx
0x180017d79  push    rdi
0x180017d7a  sub     rsp, 30h
0x180017d7e  mov     rbx, rcx
0x180017d81  xor     edx, edx; unsigned __int16 *
0x180017d83  lea     rcx, ?g_dataSource@@3VESEDataSource@@A; this
0x180017d8a  call    ?EnsureDBInitialized@ESEDataSource@@QEAAJPEBG@Z; ESEDataSource::EnsureDBInitialized(ushort const *)
0x180017d8f  mov     edi, eax
0x180017d91  test    eax, eax
0x180017d93  jns     short loc_180017DB1
0x180017d95  mov     r9d, 1Fh
0x180017d9b  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180017da2  mov     ecx, eax
0x180017da4  lea     edx, [r9-1Eh]
0x180017da8  call    Log_HREvent
0x180017dad  mov     eax, edi
0x180017daf  jmp     short loc_180017E1B
0x180017db1  mov     rcx, [rbx+10h]; lpCriticalSection
0x180017db5  call    cs:__imp_EnterCriticalSection
0x180017dbb  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180017dbf  jnz     short loc_180017DD3
0x180017dc1  mov     r8d, 23h ; '#'
0x180017dc7  lea     rdx, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180017dce  call    Log_AssertionEvent
0x180017dd3  call    cs:__imp_GetCurrentThreadId
0x180017dd9  mov     rcx, [rbx]; sesid
0x180017ddc  mov     edx, eax; ulContext
0x180017dde  call    cs:__imp_JetSetSessionContext
0x180017de4  cmp     eax, 0FFFFF888h
0x180017de9  jz      short loc_180017E19
0x180017deb  test    eax, eax
0x180017ded  jns     short loc_180017E12
0x180017def  mov     ecx, eax; int
0x180017df1  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180017df6  mov     r9d, 2Dh ; '-'
0x180017dfc  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180017e03  xor     edx, edx
0x180017e05  mov     ecx, eax
0x180017e07  mov     ebx, eax
0x180017e09  call    Log_HREvent
0x180017e0e  mov     eax, ebx
0x180017e10  jmp     short loc_180017E1B
0x180017e12  mov     dword ptr [rbx+8], 1
0x180017e19  xor     eax, eax
0x180017e1b  mov     rbx, [rsp+38h+arg_0]
0x180017e20  add     rsp, 30h
0x180017e24  pop     rdi
0x180017e25  retn
```
