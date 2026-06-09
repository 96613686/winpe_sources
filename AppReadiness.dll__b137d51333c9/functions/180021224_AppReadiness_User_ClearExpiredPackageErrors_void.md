# AppReadiness::User::ClearExpiredPackageErrors(void)

- ea: `0x180021224`
- end: `0x180021315`
- name: `?ClearExpiredPackageErrors@User@AppReadiness@@IEAAXXZ`
- size: `241`
- prototype: `void __fastcall(AppReadiness::User *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010afc`

## callees

- `0x180021224`
- `0x18002b63c`
- `0x18005da6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021301`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021301`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002124f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002124f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180021242`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180021242`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180021274`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180021274`

## pseudocode

```c
void __fastcall AppReadiness::User::ClearExpiredPackageErrors(RTL_SRWLOCK *this)
{
  const FILETIME *Ptr; // rbx
  _QWORD *v3; // rax
  RTL_SRWLOCK *v4; // r9
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp+8h] BYREF
  char v6; // [rsp+58h] [rbp+10h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  AcquireSRWLockExclusive(this + 7);
  Ptr = (const FILETIME *)this[31].Ptr;
  while ( Ptr != this[32].Ptr )
  {
    if ( CompareFileTime(&SystemTimeAsFileTime, Ptr) < 0 )
    {
      Ptr += 4;
    }
    else
    {
      BYTE1(this[27].Ptr) = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v3 = (_QWORD *)(*(_QWORD *)&Ptr[2] + 40LL);
        if ( *(_QWORD *)(*(_QWORD *)&Ptr[2] + 64LL) > 7u )
          v3 = (_QWORD *)*v3;
        v4 = this + 8;
        if ( this[11].Ptr > (PVOID)7 )
          v4 = (RTL_SRWLOCK *)v4->Ptr;
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          (unsigned int)&WPP_2779cad321383337b9ccea6dca676a06_Traceguids,
          (_DWORD)v4,
          (__int64)v3);
      }
      Ptr = *(const FILETIME **)std::vector<AppReadiness::ErrorInfo>::erase(&this[31], &v6, Ptr);
    }
  }
  if ( this != (RTL_SRWLOCK *)-56LL )
    ReleaseSRWLockExclusive(this + 7);
}

```

## disassembly

```asm
0x180021224  mov     [rsp+arg_10], rbx
0x180021229  push    rsi
0x18002122a  push    rdi
0x18002122b  push    r14
0x18002122d  sub     rsp, 30h
0x180021231  mov     rdi, rcx
0x180021234  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002123d  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180021242  call    cs:__imp_GetSystemTimeAsFileTime
0x180021248  lea     rsi, [rdi+38h]
0x18002124c  mov     rcx, rsi; SRWLock
0x18002124f  call    cs:__imp_AcquireSRWLockExclusive
0x180021255  lea     r14, [rdi+0F8h]
0x18002125c  mov     rbx, [r14]
0x18002125f  cmp     rbx, [rdi+100h]
0x180021266  jz      loc_1800212F9
0x18002126c  mov     rdx, rbx; lpFileTime2
0x18002126f  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpFileTime1
0x180021274  call    cs:__imp_CompareFileTime
0x18002127a  test    eax, eax
0x18002127c  js      short loc_1800212F0
0x18002127e  mov     byte ptr [rdi+0D9h], 1
0x180021285  mov     rcx, cs:WPP_GLOBAL_Control
0x18002128c  lea     rax, WPP_GLOBAL_Control
0x180021293  cmp     rcx, rax
0x180021296  jz      short loc_1800212D8
0x180021298  test    byte ptr [rcx+1Ch], 4
0x18002129c  jz      short loc_1800212D8
0x18002129e  mov     rax, [rbx+10h]
0x1800212a2  add     rax, 28h ; '('
0x1800212a6  cmp     qword ptr [rax+18h], 7
0x1800212ab  jbe     short loc_1800212B0
0x1800212ad  mov     rax, [rax]
0x1800212b0  cmp     qword ptr [rdi+58h], 7
0x1800212b5  lea     r9, [rdi+40h]
0x1800212b9  jbe     short loc_1800212BE
0x1800212bb  mov     r9, [r9]
0x1800212be  mov     rcx, [rcx+10h]
0x1800212c2  lea     r8, WPP_2779cad321383337b9ccea6dca676a06_Traceguids
0x1800212c9  mov     edx, 1Ah
0x1800212ce  mov     [rsp+48h+var_28], rax
0x1800212d3  call    WPP_SF_SS
0x1800212d8  mov     r8, rbx
0x1800212db  lea     rdx, [rsp+48h+arg_8]
0x1800212e0  mov     rcx, r14
0x1800212e3  call    ?erase@?$vector@UErrorInfo@AppReadiness@@V?$allocator@UErrorInfo@AppReadiness@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UErrorInfo@AppReadiness@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UErrorInfo@AppReadiness@@@std@@@std@@@2@@Z; std::vector<AppReadiness::ErrorInfo>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<AppReadiness::ErrorInfo>>>)
0x1800212e8  mov     rbx, [rax]
0x1800212eb  jmp     loc_18002125F
0x1800212f0  add     rbx, 20h ; ' '
0x1800212f4  jmp     loc_18002125F
0x1800212f9  test    rsi, rsi
0x1800212fc  jz      short loc_180021307
0x1800212fe  mov     rcx, rsi; SRWLock
0x180021301  call    cs:__imp_ReleaseSRWLockExclusive
0x180021307  mov     rbx, [rsp+48h+arg_10]
0x18002130c  add     rsp, 30h
0x180021310  pop     r14
0x180021312  pop     rdi
0x180021313  pop     rsi
0x180021314  retn
```
