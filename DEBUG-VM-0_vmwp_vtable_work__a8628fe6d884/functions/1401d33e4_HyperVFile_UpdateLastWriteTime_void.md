# HyperVFile::UpdateLastWriteTime(void)

- ea: `0x1401d33e4`
- end: `0x1401d34c1`
- name: `?UpdateLastWriteTime@HyperVFile@@IEAAXXZ`
- size: `221`
- prototype: `void __fastcall(HyperVFile *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400554c0`

## callees

- `0x140132940`
- `0x1401d33e4`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1401d3453`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1401d3453`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1401d342a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1401d3469`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1401d342a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1401d3469`

## pseudocode

```c
void __fastcall HyperVFile::UpdateLastWriteTime(HyperVFile *this)
{
  FILETIME *v2; // rbx
  FILETIME v3; // rax
  FILETIME FileTime1; // [rsp+20h] [rbp-28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+28h] [rbp-20h] BYREF

  (*(void (__fastcall **)(_QWORD, FILETIME *))(**((_QWORD **)this + 75) + 168LL))(*((_QWORD *)this + 75), &FileTime1);
  v2 = (FILETIME *)((char *)this + 776);
  if ( CompareFileTime(&FileTime1, (const FILETIME *)this + 97) <= 0 )
  {
    v3 = (FILETIME)(*(_QWORD *)v2 + 1LL);
    SystemTimeAsFileTime = 0;
    FileTime1 = v3;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) < 0 )
      FileTime1 = SystemTimeAsFileTime;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 176LL))(*((_QWORD *)this + 75));
  }
  *v2 = FileTime1;
}

```

## disassembly

```asm
0x1401d33e4  mov     [rsp+arg_8], rbx
0x1401d33e9  push    rdi
0x1401d33ea  sub     rsp, 40h
0x1401d33ee  mov     rax, cs:__security_cookie
0x1401d33f5  xor     rax, rsp
0x1401d33f8  mov     [rsp+48h+var_18], rax
0x1401d33fd  mov     rdi, rcx
0x1401d3400  lea     rdx, [rsp+48h+FileTime1]
0x1401d3405  mov     rcx, [rcx+258h]
0x1401d340c  mov     rax, [rcx]
0x1401d340f  mov     rax, [rax+0A8h]
0x1401d3416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401d341b  lea     rbx, [rdi+308h]
0x1401d3422  mov     rdx, rbx; lpFileTime2
0x1401d3425  lea     rcx, [rsp+48h+FileTime1]; lpFileTime1
0x1401d342a  call    cs:__imp_CompareFileTime
0x1401d3431  nop     dword ptr [rax+rax+00h]
0x1401d3436  test    eax, eax
0x1401d3438  jg      short loc_1401D34A0
0x1401d343a  mov     rax, [rbx]
0x1401d343d  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1401d3442  inc     rax
0x1401d3445  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1401d344e  mov     qword ptr [rsp+48h+FileTime1.dwLowDateTime], rax
0x1401d3453  call    cs:__imp_GetSystemTimeAsFileTime
0x1401d345a  nop     dword ptr [rax+rax+00h]
0x1401d345f  lea     rdx, [rsp+48h+SystemTimeAsFileTime]; lpFileTime2
0x1401d3464  lea     rcx, [rsp+48h+FileTime1]; lpFileTime1
0x1401d3469  call    cs:__imp_CompareFileTime
0x1401d3470  nop     dword ptr [rax+rax+00h]
0x1401d3475  test    eax, eax
0x1401d3477  jns     short loc_1401D3485
0x1401d3479  mov     rdx, qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x1401d347e  mov     qword ptr [rsp+48h+FileTime1.dwLowDateTime], rdx
0x1401d3483  jmp     short loc_1401D348A
0x1401d3485  mov     rdx, qword ptr [rsp+48h+FileTime1.dwLowDateTime]
0x1401d348a  mov     rcx, [rdi+258h]
0x1401d3491  mov     rax, [rcx]
0x1401d3494  mov     rax, [rax+0B0h]
0x1401d349b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401d34a0  mov     rax, qword ptr [rsp+48h+FileTime1.dwLowDateTime]
0x1401d34a5  mov     [rbx], rax
0x1401d34a8  mov     rcx, [rsp+48h+var_18]
0x1401d34ad  xor     rcx, rsp; StackCookie
0x1401d34b0  call    __security_check_cookie
0x1401d34b5  mov     rbx, [rsp+48h+arg_8]
0x1401d34ba  add     rsp, 40h
0x1401d34be  pop     rdi
0x1401d34bf  retn
```
