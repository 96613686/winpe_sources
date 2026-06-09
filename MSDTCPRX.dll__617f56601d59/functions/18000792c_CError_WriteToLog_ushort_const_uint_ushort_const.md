# CError::WriteToLog(ushort const *,uint,ushort const *,...)

- ea: `0x18000792c`
- end: `0x180007b2d`
- name: `?WriteToLog@CError@@QEAAXPEBGI0ZZ`
- size: `513`
- prototype: `void(CError *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `10`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800011e0`
- `0x180001290`
- `0x180007880`
- `0x18000a280`
- `0x18000ef28`
- `0x180012404`
- `0x180012b9c`
- `0x18007d168`
- `0x18007d218`
- `0x18007d2bc`

## callees

- `0x18000792c`
- `0x18000c304`
- `0x18000c6bc`
- `0x18000e208`
- `0x18000e85c`
- `0x18000fdd4`
- `0x180062658`
- `0x1800626ac`
- `0x18007d490`
- `0x18007d4dc`
- `0x18007de24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008210e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008210e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007967`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007967`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007aae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007aae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007aa6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007aa6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007a91`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007a91`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007ae8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007af5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007b02`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007ae8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007af5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007b02`

## string_xrefs

- `0x180007ac9`: `This is a COM+ Failfast Break\n  Process.Thread=<%d.%d>\n  File: %s:%d\n  hr=0x%08x\n`

## pseudocode

```c
void CError::WriteToLog(CError *this, unsigned __int16 *a2, unsigned int a3, const unsigned __int16 *a4, ...)
{
  const unsigned __int16 *v4; // rax
  int v8; // r15d
  int v9; // r14d
  unsigned __int16 *v10; // rcx
  __int64 v11; // rax
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // r8
  __int64 v15; // rdx
  unsigned __int16 *v16; // rcx
  unsigned int v17; // r8d
  unsigned __int16 *v18; // r9
  void *v19; // r8
  unsigned __int64 v20; // r9
  const unsigned __int16 *v21; // rdx
  int v22; // r8d
  __int64 v23; // rcx
  DWORD CurrentThreadId; // edi
  DWORD CurrentProcessId; // eax
  unsigned __int16 v26; // [rsp+20h] [rbp-78h]
  unsigned int *v27; // [rsp+20h] [rbp-78h]
  struct _EXCEPTION_POINTERS *v28; // [rsp+28h] [rbp-70h]
  unsigned int v29; // [rsp+40h] [rbp-58h] BYREF
  int v30; // [rsp+44h] [rbp-54h]
  __int64 v31; // [rsp+48h] [rbp-50h]
  unsigned __int16 *v32; // [rsp+50h] [rbp-48h] BYREF
  va_list va; // [rsp+C0h] [rbp+28h] BYREF

  va_start(va, a4);
  v4 = a4;
  v8 = 0;
  v9 = 0;
  v30 = 0;
  if ( dword_1800D70D0 )
  {
    EnterCriticalSection(&stru_1800D70A8);
    v9 = 1;
    v30 = 1;
    v4 = a4;
  }
  v10 = 0;
  word_1800D7BF0 = 0;
  if ( v4 )
  {
    StringCchVPrintfW(&word_1800D7BF0, 0x3FDu, v4, va);
    word_1800D83EA = 0;
    v31 = 0;
    v10 = (unsigned __int16 *)word_1800D7BF0;
  }
  if ( (_WORD)v10 )
    StringCchCatW(&word_1800D7BF0, 0x400u, L"\r\n");
  v11 = -1;
  do
    ++v11;
  while ( *(&word_1800D7BF0 + v11) );
  v29 = 1024 - v11;
  AppendApplicationInfo(v10, (unsigned int)a2, &v29);
  if ( *((_DWORD *)this + 10) )
    AppendFailfastMessage(v13, v12, &v29);
  AppendHResult(*(_DWORD *)this, v12, v14, &v29);
  if ( *(_DWORD *)this || *((_DWORD *)this + 10) )
    AppendInternalsInfo(a2, a3, v17, v18, &v29);
  AppendComsvcsFileVersion(v16, v15, &v29);
  v32 = &word_1800D7BF0;
  LogIt(*((_WORD *)this + 2), *((_DWORD *)this + 2), v19, v20, v26, (const unsigned __int16 **const)&v32);
  v23 = 3221225472LL;
  LOBYTE(v8) = (*((_DWORD *)this + 2) & 0xC0000000) == -1073741824;
  if ( v9 )
    LeaveCriticalSection(&stru_1800D70A8);
  if ( *((_DWORD *)this + 10) )
  {
    if ( *((_DWORD *)this + 11) && (IsDebuggerPresent() || MEMORY[0x7FFE02D4]) )
    {
      CurrentThreadId = GetCurrentThreadId();
      CurrentProcessId = GetCurrentProcessId();
      v28 = (struct _EXCEPTION_POINTERS *)a2;
      LODWORD(v27) = CurrentThreadId;
      StringCchPrintfW(
        &word_1800D8C10,
        0x3FFu,
        L"This is a COM+ Failfast Break\n  Process.Thread=<%d.%d>\n  File: %s:%d\n  hr=0x%08x\r\n",
        CurrentProcessId,
        v27);
      OutputDebugStringW(L"\n#####################################################################\n");
      OutputDebugStringW(&word_1800D8C10);
      OutputDebugStringW(L"#####################################################################\n");
    }
    if ( *((_DWORD *)this + 10) )
      FailFastStr((const unsigned __int16 *)v23, v21, v22, v8, *((_DWORD *)this + 11), v28);
  }
}

```

## disassembly

```asm
0x18000792c  mov     [rsp+arg_18], r9
0x180007931  push    rbx
0x180007932  push    rsi
0x180007933  push    rdi
0x180007934  push    r12
0x180007936  push    r13
0x180007938  push    r14
0x18000793a  push    r15
0x18000793c  sub     rsp, 60h
0x180007940  mov     rax, r9
0x180007943  mov     r12d, r8d
0x180007946  mov     r13, rdx
0x180007949  mov     rsi, rcx
0x18000794c  xor     r15d, r15d
0x18000794f  mov     r14d, r15d
0x180007952  mov     [rsp+98h+var_54], r15d
0x180007957  cmp     cs:dword_1800D70D0, r15d
0x18000795e  jz      short loc_18000797E
0x180007960  lea     rcx, stru_1800D70A8; lpCriticalSection
0x180007967  call    cs:__imp_EnterCriticalSection
0x18000796d  lea     r14d, [r15+1]
0x180007971  mov     [rsp+98h+var_54], r14d
0x180007976  mov     rax, [rsp+98h+arg_18]
0x18000797e  mov     ecx, r15d
0x180007981  mov     cs:word_1800D7BF0, cx
0x180007988  lea     rdi, word_1800D7BF0
0x18000798f  test    rax, rax
0x180007992  jz      short loc_1800079C5
0x180007994  mov     [rsp+98h+var_50], r15
0x180007999  lea     r9, [rsp+98h+arg_20]; char *
0x1800079a1  mov     r8, rax; unsigned __int16 *
0x1800079a4  mov     edx, 3FDh; unsigned __int64
0x1800079a9  mov     rcx, rdi; unsigned __int16 *
0x1800079ac  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x1800079b1  mov     cs:word_1800D83EA, r15w
0x1800079b9  mov     [rsp+98h+var_50], r15
0x1800079be  movzx   ecx, cs:word_1800D7BF0
0x1800079c5  mov     ebx, 400h
0x1800079ca  test    cx, cx
0x1800079cd  jz      short loc_1800079E0
0x1800079cf  lea     r8, asc_1800BC5D8; "\r\n"
0x1800079d6  mov     edx, ebx; unsigned __int64
0x1800079d8  mov     rcx, rdi; unsigned __int16 *
0x1800079db  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800079e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800079e4  inc     rax
0x1800079e7  cmp     [rdi+rax*2], r15w
0x1800079ec  jnz     short loc_1800079E4
0x1800079ee  sub     ebx, eax
0x1800079f0  mov     [rsp+98h+var_58], ebx
0x1800079f4  lea     r8, [rsp+98h+var_58]; unsigned int *
0x1800079f9  call    ?AppendApplicationInfo@@YAXPEAGKPEAI@Z; AppendApplicationInfo(ushort *,ulong,uint *)
0x1800079fe  cmp     [rsi+28h], r15d
0x180007a02  jz      short loc_180007A0E
0x180007a04  lea     r8, [rsp+98h+var_58]; unsigned int *
0x180007a09  call    ?AppendFailfastMessage@@YAXPEAGKPEAI@Z; AppendFailfastMessage(ushort *,ulong,uint *)
0x180007a0e  lea     r9, [rsp+98h+var_58]; unsigned int *
0x180007a13  mov     ecx, [rsi]; dwMessageId
0x180007a15  call    ?AppendHResult@@YAXJKPEAGPEAI@Z; AppendHResult(long,ulong,ushort *,uint *)
0x180007a1a  cmp     [rsi], r15d
0x180007a1d  jnz     short loc_180007A25
0x180007a1f  cmp     [rsi+28h], r15d
0x180007a23  jz      short loc_180007A3A
0x180007a25  lea     rax, [rsp+98h+var_58]
0x180007a2a  mov     [rsp+98h+var_78], rax; unsigned __int16
0x180007a2f  mov     edx, r12d; unsigned int
0x180007a32  mov     rcx, r13; unsigned __int16 *
0x180007a35  call    ?AppendInternalsInfo@@YAXPEBGIKPEAGPEAI@Z; AppendInternalsInfo(ushort const *,uint,ulong,ushort *,uint *)
0x180007a3a  lea     r8, [rsp+98h+var_58]; unsigned int *
0x180007a3f  call    ?AppendComsvcsFileVersion@@YAXPEAGKPEAI@Z; AppendComsvcsFileVersion(ushort *,ulong,uint *)
0x180007a44  mov     [rsp+98h+var_48], rdi
0x180007a49  lea     rax, [rsp+98h+var_48]
0x180007a4e  mov     [rsp+98h+var_70], rax; unsigned __int16 **
0x180007a53  mov     edx, [rsi+8]; unsigned int
0x180007a56  movzx   ecx, word ptr [rsi+4]; unsigned __int16
0x180007a5a  call    ?LogIt@@YAXGKPEAX_KGQEAPEBG@Z; LogIt(ushort,ulong,void *,unsigned __int64,ushort,ushort const * * const)
0x180007a5f  mov     eax, [rsi+8]
0x180007a62  mov     ecx, 0C0000000h
0x180007a67  and     eax, ecx
0x180007a69  cmp     eax, ecx
0x180007a6b  setz    r15b
0x180007a6f  test    r14d, r14d
0x180007a72  jz      short loc_180007A81
0x180007a74  lea     rcx, stru_1800D70A8; lpCriticalSection
0x180007a7b  call    cs:__imp_LeaveCriticalSection
0x180007a81  cmp     dword ptr [rsi+28h], 0
0x180007a85  jz      loc_180007B1D
0x180007a8b  cmp     dword ptr [rsi+2Ch], 0
0x180007a8f  jz      short loc_180007B08
0x180007a91  call    cs:__imp_IsDebuggerPresent
0x180007a97  test    eax, eax
0x180007a99  jnz     short loc_180007AA4
0x180007a9b  cmp     ds:7FFE02D4h, al
0x180007aa2  jz      short loc_180007B08
0x180007aa4  mov     ebx, [rsi]
0x180007aa6  call    cs:__imp_GetCurrentThreadId
0x180007aac  mov     edi, eax
0x180007aae  call    cs:__imp_GetCurrentProcessId
0x180007ab4  mov     [rsp+98h+var_60], ebx
0x180007ab8  mov     [rsp+98h+var_68], r12d
0x180007abd  mov     [rsp+98h+var_70], r13; struct _EXCEPTION_POINTERS *
0x180007ac2  mov     dword ptr [rsp+98h+var_78], edi
0x180007ac6  mov     r9d, eax
0x180007ac9  lea     r8, aThisIsAComFail; "This is a COM+ Failfast Break\n  Proces"...
0x180007ad0  mov     edx, 3FFh; unsigned __int64
0x180007ad5  lea     rcx, word_1800D8C10; unsigned __int16 *
0x180007adc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007ae1  lea     rcx, OutputString; "\n#####################################"...
0x180007ae8  call    cs:__imp_OutputDebugStringW
0x180007aee  lea     rcx, word_1800D8C10; lpOutputString
0x180007af5  call    cs:__imp_OutputDebugStringW
0x180007afb  lea     rcx, asc_1800C6F80; "#######################################"...
0x180007b02  call    cs:__imp_OutputDebugStringW
0x180007b08  cmp     dword ptr [rsi+28h], 0
0x180007b0c  jz      short loc_180007B1D
0x180007b0e  mov     eax, [rsi+2Ch]
0x180007b11  mov     dword ptr [rsp+98h+var_78], eax; int
0x180007b15  mov     r9d, r15d; int
0x180007b18  call    ?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z; FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)
0x180007b1d  add     rsp, 60h
0x180007b21  pop     r15
0x180007b23  pop     r14
0x180007b25  pop     r13
0x180007b27  pop     r12
0x180007b29  pop     rdi
0x180007b2a  pop     rsi
0x180007b2b  pop     rbx
0x180007b2c  retn
0x1800820f8  push    rbp
0x1800820fa  sub     rsp, 40h
0x1800820fe  mov     rbp, rdx
0x180082101  cmp     dword ptr [rbp+44h], 0
0x180082105  jz      short loc_180082115
0x180082107  lea     rcx, stru_1800D70A8; lpCriticalSection
0x18008210e  call    cs:__imp_LeaveCriticalSection
0x180082114  nop
0x180082115  add     rsp, 40h
0x180082119  pop     rbp
0x18008211a  retn
```
