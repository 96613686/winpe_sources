# AppReadiness::ServiceThread::GetHandle(void * *)

- ea: `0x180023d20`
- end: `0x180023e19`
- name: `?GetHandle@ServiceThread@AppReadiness@@QEAAXPEAPEAX@Z`
- size: `249`
- prototype: `void(AppReadiness::ServiceThread *__hidden this, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800221a4`

## callees

- `0x180023d20`
- `0x180027a4c`
- `0x18003ecb4`
- `0x1800473d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023d7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023d8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023d7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023d8a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180023db4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180023db4`

## string_xrefs

- `0x180023d5f`: `m_threadHandle.IsValid()`
- `0x180023d4f`: `AppReadiness::ServiceThread::GetHandle`
- `0x180023ddb`: `AppReadiness::ServiceThread::GetHandle`
- `0x180023d3d`: `onecoreuap\shell\appreadiness\src\core\servicethread.cpp`
- `0x180023dc7`: `onecoreuap\shell\appreadiness\src\core\servicethread.cpp`
- `0x180023de9`: `DuplicateHandle(GetCurrentProcess(), m_threadHandle.Get(), GetCurrentProcess(), threadHandle, 0, false, DUPLICATE_SAME_ACCESS)`

## pseudocode

```c
void __fastcall AppReadiness::ServiceThread::GetHandle(AppReadiness::ServiceThread *this, void **a2)
{
  HANDLE CurrentProcess; // rax
  void *v5; // rdi
  void *v6; // rbx
  HANDLE v7; // rax
  int Error; // eax
  _BYTE pExceptionObject[48]; // [rsp+40h] [rbp-38h] BYREF

  if ( !*((_QWORD *)this + 5) )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      -2147019873,
      "m_threadHandle.IsValid()",
      "AppReadiness::ServiceThread::GetHandle",
      "onecoreuap\\shell\\appreadiness\\src\\core\\servicethread.cpp",
      28);
    throw (Windows::HResultException *)pExceptionObject;
  }
  CurrentProcess = GetCurrentProcess();
  v5 = (void *)*((_QWORD *)this + 5);
  v6 = CurrentProcess;
  v7 = GetCurrentProcess();
  if ( !DuplicateHandle(v7, v5, v6, a2, 0, 0, 2u) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        Error,
        "DuplicateHandle(GetCurrentProcess(), m_threadHandle.Get(), GetCurrentProcess(), threadHandle, 0, false, DUPLICATE_SAME_ACCESS)",
        "AppReadiness::ServiceThread::GetHandle",
        "onecoreuap\\shell\\appreadiness\\src\\core\\servicethread.cpp",
        29);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x180023d20  mov     rax, rsp
0x180023d23  mov     [rax+8], rbx
0x180023d27  mov     [rax+10h], rsi
0x180023d2b  push    rdi
0x180023d2c  sub     rsp, 70h
0x180023d30  cmp     qword ptr [rcx+28h], 0
0x180023d35  mov     rsi, rdx
0x180023d38  mov     rdi, rcx
0x180023d3b  jnz     short loc_180023D7D
0x180023d3d  lea     rcx, aOnecoreuapShel_7; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180023d44  mov     dword ptr [rax-50h], 1Ch
0x180023d4b  mov     [rax-58h], rcx
0x180023d4f  lea     r9, aAppreadinessSe_0; "AppReadiness::ServiceThread::GetHandle"
0x180023d56  lea     rcx, [rax-38h]; this
0x180023d5a  mov     edx, 8007139Fh; int
0x180023d5f  lea     r8, aMThreadhandleI_0; "m_threadHandle.IsValid()"
0x180023d66  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180023d6b  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180023d72  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180023d77  call    _CxxThrowException_0
0x180023d7d  call    cs:__imp_GetCurrentProcess
0x180023d83  mov     rdi, [rdi+28h]
0x180023d87  mov     rbx, rax
0x180023d8a  call    cs:__imp_GetCurrentProcess
0x180023d90  mov     [rsp+78h+dwOptions], 2; dwOptions
0x180023d98  mov     r9, rsi; lpTargetHandle
0x180023d9b  mov     rcx, rax; hSourceProcessHandle
0x180023d9e  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x180023da6  mov     r8, rbx; hTargetProcessHandle
0x180023da9  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x180023db1  mov     rdx, rdi; hSourceHandle
0x180023db4  call    cs:__imp_DuplicateHandle
0x180023dba  test    eax, eax
0x180023dbc  jnz     short loc_180023E07
0x180023dbe  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180023dc3  test    eax, eax
0x180023dc5  jns     short loc_180023E07
0x180023dc7  lea     rcx, aOnecoreuapShel_7; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180023dce  mov     [rsp+78h+bInheritHandle], 1Dh; int
0x180023dd6  mov     qword ptr [rsp+78h+dwDesiredAccess], rcx; char *
0x180023ddb  lea     r9, aAppreadinessSe_0; "AppReadiness::ServiceThread::GetHandle"
0x180023de2  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180023de7  mov     edx, eax; int
0x180023de9  lea     r8, aDuplicatehandl; "DuplicateHandle(GetCurrentProcess(), m_"...
0x180023df0  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180023df5  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180023dfc  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180023e01  call    _CxxThrowException_0
0x180023e07  lea     r11, [rsp+78h+var_8]
0x180023e0c  mov     rbx, [r11+10h]
0x180023e10  mov     rsi, [r11+18h]
0x180023e14  mov     rsp, r11
0x180023e17  pop     rdi
0x180023e18  retn
```
