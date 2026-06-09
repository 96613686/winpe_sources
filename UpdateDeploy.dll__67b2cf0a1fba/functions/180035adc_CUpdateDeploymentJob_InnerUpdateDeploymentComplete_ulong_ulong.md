# CUpdateDeploymentJob::InnerUpdateDeploymentComplete(ulong,ulong)

- ea: `0x180035adc`
- end: `0x180035c99`
- name: `?InnerUpdateDeploymentComplete@CUpdateDeploymentJob@@AEAAJKK@Z`
- size: `445`
- prototype: `__int64 __fastcall(CUpdateDeploymentJob *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002d3d0`
- `0x180030988`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x180028ce8`
- `0x180028e88`
- `0x180035adc`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035bd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035be9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035bd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035be9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035c35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035c46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035c35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035c46`

## string_xrefs

- `0x180035b11`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180035bb3`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180035c21`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CUpdateDeploymentJob::InnerUpdateDeploymentComplete(
        CUpdateDeploymentJob *this,
        unsigned int a2,
        unsigned int a3)
{
  __int64 v4; // rdx
  int updated; // edi
  __int64 v7; // rdx
  int v8; // eax
  int v9; // [rsp+20h] [rbp-30h]
  unsigned int v10[2]; // [rsp+30h] [rbp-20h] BYREF
  struct IUpdateDeploymentJobStatus *v11; // [rsp+38h] [rbp-18h] BYREF
  struct IUpdateDeploymentStatus *v12; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v10[0] = a3;
  if ( a2 >= *((_DWORD *)this + 172) )
  {
    v4 = 5812;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)0x80070057LL,
      v9);
    return 2147942487LL;
  }
  _mm_lfence();
  if ( a3 >= *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 87) + 8LL * a2) + 544LL) )
  {
    v4 = 5813;
    goto LABEL_3;
  }
  v12 = 0;
  v11 = 0;
  updated = CUpdateDeploymentJob::CreateUpdateDeploymentStatus(this, a2, v10, &v12);
  if ( updated >= 0 )
  {
    if ( v11 )
    {
      (*(void (__fastcall **)(struct IUpdateDeploymentJobStatus *))(*(_QWORD *)v11 + 16LL))(v11);
      v11 = 0;
    }
    updated = CUpdateDeploymentJob::CreateJobDeploymentStatus((__int64)this, &v11);
    if ( updated >= 0 )
    {
      *(_QWORD *)v10 = (char *)this + 928;
      if ( this != (CUpdateDeploymentJob *)-928LL )
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 936));
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, struct IUpdateDeploymentStatus *, struct IUpdateDeploymentJobStatus *))(**((_QWORD **)this + 90) + 24LL))(
             *((_QWORD *)this + 90),
             4,
             0,
             v12,
             v11);
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x16C6,
          (int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
          (const char *)(unsigned int)v8);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
      updated = 0;
      if ( this != (CUpdateDeploymentJob *)-928LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 936));
      goto LABEL_19;
    }
    v7 = 5820;
  }
  else
  {
    v7 = 5819;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
    (const char *)(unsigned int)updated,
    v9);
LABEL_19:
  if ( v11 )
  {
    (*(void (__fastcall **)(struct IUpdateDeploymentJobStatus *))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( v12 )
    (*(void (__fastcall **)(struct IUpdateDeploymentStatus *))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180035adc  push    rbp
0x180035ade  push    rbx
0x180035adf  push    rsi
0x180035ae0  push    rdi
0x180035ae1  push    r14
0x180035ae3  mov     rbp, rsp
0x180035ae6  sub     rsp, 50h
0x180035aea  mov     rax, cs:__security_cookie
0x180035af1  xor     rax, rsp
0x180035af4  mov     [rbp+var_8], rax
0x180035af8  mov     rsi, rcx
0x180035afb  mov     [rbp+var_20], r8d
0x180035aff  cmp     edx, [rcx+2B0h]
0x180035b05  jb      short loc_180035B2B
0x180035b07  mov     edx, 16B4h; void *
0x180035b0c  mov     ebx, 80070057h
0x180035b11  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180035b18  mov     r9d, ebx; char *
0x180035b1b  mov     rcx, [rbp+28h]; this
0x180035b1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035b24  mov     eax, ebx
0x180035b26  jmp     loc_180035C82
0x180035b2b  lfence
0x180035b2e  mov     ecx, edx
0x180035b30  mov     rax, [rsi+2B8h]
0x180035b37  mov     rcx, [rax+rcx*8]
0x180035b3b  cmp     r8d, [rcx+220h]
0x180035b42  jb      short loc_180035B4B
0x180035b44  mov     edx, 16B5h; unsigned int
0x180035b49  jmp     short loc_180035B0C
0x180035b4b  mov     [rbp+var_10], 0
0x180035b53  mov     [rbp+var_18], 0
0x180035b5b  lea     r9, [rbp+var_10]; struct IUpdateDeploymentStatus **
0x180035b5f  lea     r8, [rbp+var_20]; unsigned int *
0x180035b63  mov     rcx, rsi; this
0x180035b66  call    ?CreateUpdateDeploymentStatus@CUpdateDeploymentJob@@AEAAJKPEAKPEAPEAUIUpdateDeploymentStatus@@@Z; CUpdateDeploymentJob::CreateUpdateDeploymentStatus(ulong,ulong *,IUpdateDeploymentStatus * *)
0x180035b6b  mov     edi, eax
0x180035b6d  test    eax, eax
0x180035b6f  jns     short loc_180035B78
0x180035b71  mov     edx, 16BBh
0x180035b76  jmp     short loc_180035BAC
0x180035b78  mov     rcx, [rbp+var_18]
0x180035b7c  test    rcx, rcx
0x180035b7f  jz      short loc_180035B95
0x180035b81  mov     rax, [rcx]
0x180035b84  mov     rax, [rax+10h]
0x180035b88  call    _guard_dispatch_icall
0x180035b8d  mov     [rbp+var_18], 0
0x180035b95  lea     rdx, [rbp+var_18]; struct IUpdateDeploymentJobStatus **
0x180035b99  mov     rcx, rsi; this
0x180035b9c  call    ?CreateJobDeploymentStatus@CUpdateDeploymentJob@@AEAAJPEAPEAUIUpdateDeploymentJobStatus@@@Z; CUpdateDeploymentJob::CreateJobDeploymentStatus(IUpdateDeploymentJobStatus * *)
0x180035ba1  mov     edi, eax
0x180035ba3  test    eax, eax
0x180035ba5  jns     short loc_180035BC4
0x180035ba7  mov     edx, 16BCh; void *
0x180035bac  mov     rcx, [rbp+28h]; this
0x180035bb0  mov     r9d, edi; char *
0x180035bb3  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180035bba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035bbf  jmp     loc_180035C4D
0x180035bc4  lea     rbx, [rsi+3A0h]
0x180035bcb  mov     qword ptr [rbp+var_20], rbx
0x180035bcf  test    rbx, rbx
0x180035bd2  jz      short loc_180035BDF
0x180035bd4  lea     rcx, [rbx+8]; lpCriticalSection
0x180035bd8  call    cs:__imp_EnterCriticalSection
0x180035bde  nop
0x180035bdf  lea     rdi, [rsi+378h]
0x180035be6  mov     rcx, rdi; lpCriticalSection
0x180035be9  call    cs:__imp_EnterCriticalSection
0x180035bef  mov     rcx, [rsi+2D0h]
0x180035bf6  mov     rdx, [rbp+var_18]
0x180035bfa  mov     rax, [rcx]
0x180035bfd  mov     qword ptr [rsp+50h+var_30], rdx; int
0x180035c02  mov     r9, [rbp+var_10]
0x180035c06  xor     r8d, r8d
0x180035c09  lea     edx, [r8+4]
0x180035c0d  mov     rax, [rax+18h]
0x180035c11  call    _guard_dispatch_icall
0x180035c16  mov     rcx, [rbp+28h]; this
0x180035c1a  test    eax, eax
0x180035c1c  jns     short loc_180035C32
0x180035c1e  mov     r9d, eax; char *
0x180035c21  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180035c28  mov     edx, 16C6h; void *
0x180035c2d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035c32  mov     rcx, rdi; lpCriticalSection
0x180035c35  call    cs:__imp_LeaveCriticalSection
0x180035c3b  xor     edi, edi
0x180035c3d  test    rbx, rbx
0x180035c40  jz      short loc_180035C4D
0x180035c42  lea     rcx, [rbx+8]; lpCriticalSection
0x180035c46  call    cs:__imp_LeaveCriticalSection
0x180035c4c  nop
0x180035c4d  mov     rcx, [rbp+var_18]
0x180035c51  test    rcx, rcx
0x180035c54  jz      short loc_180035C6A
0x180035c56  mov     rax, [rcx]
0x180035c59  mov     rax, [rax+10h]
0x180035c5d  call    _guard_dispatch_icall
0x180035c62  mov     [rbp+var_18], 0
0x180035c6a  mov     rcx, [rbp+var_10]
0x180035c6e  test    rcx, rcx
0x180035c71  jz      short loc_180035C80
0x180035c73  mov     rdx, [rcx]
0x180035c76  mov     rax, [rdx+10h]
0x180035c7a  call    _guard_dispatch_icall
0x180035c7f  nop
0x180035c80  mov     eax, edi
0x180035c82  mov     rcx, [rbp+var_8]
0x180035c86  xor     rcx, rsp; StackCookie
0x180035c89  call    __security_check_cookie
0x180035c8e  add     rsp, 50h
0x180035c92  pop     r14
0x180035c94  pop     rdi
0x180035c95  pop     rsi
0x180035c96  pop     rbx
0x180035c97  pop     rbp
0x180035c98  retn
```
