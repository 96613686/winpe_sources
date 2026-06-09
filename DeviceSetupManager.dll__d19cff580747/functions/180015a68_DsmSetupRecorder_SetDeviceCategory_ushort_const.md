# DsmSetupRecorder::SetDeviceCategory(ushort const *)

- ea: `0x180015a68`
- end: `0x180015b09`
- name: `?SetDeviceCategory@DsmSetupRecorder@@QEAAJPEBG@Z`
- size: `161`
- prototype: `int(DsmSetupRecorder *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800097e4`

## callees

- `0x1800112a4`
- `0x180015474`
- `0x180015a68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015a7e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015a7e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015ade`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015ade`

## string_xrefs

- `0x180015a94`: `onecoreuap\base\devices\setup\dsm\service\setuprecorder.cpp`

## pseudocode

```c
__int64 __fastcall DsmSetupRecorder::SetDeviceCategory(RTL_SRWLOCK *this, const unsigned __int16 *a2)
{
  RTL_SRWLOCK *v2; // rbx
  bool v5; // zf
  unsigned int v6; // ebx
  int v7; // esi
  __int64 i; // rbx
  const WCHAR *v9; // r8
  BOOL bIgnoreCase; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  RTL_SRWLOCK *v13; // [rsp+60h] [rbp+8h] BYREF

  v2 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  v5 = BYTE4(this->Ptr) == 0;
  v13 = v2;
  if ( v5 )
  {
    v6 = -2147467260;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\setuprecorder.cpp",
      (const char *)0x80004004LL,
      bIgnoreCase);
  }
  else
  {
    v7 = -1;
    for ( i = 0; (unsigned int)i < 0xE1; i = (unsigned int)(i + 1) )
    {
      v9 = off_180046160[i];
      if ( v9 && CompareStringOrdinal(a2, -1, v9, -1, 1) == 2 )
      {
        v7 = i;
        break;
      }
    }
    LODWORD(this[4].Ptr) = v7;
    v6 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  return v6;
}

```

## disassembly

```asm
0x180015a68  push    rbx
0x180015a6a  push    rbp
0x180015a6b  push    rsi
0x180015a6c  push    rdi
0x180015a6d  sub     rsp, 38h
0x180015a71  lea     rbx, [rcx+8]
0x180015a75  mov     rdi, rcx
0x180015a78  mov     rcx, rbx; SRWLock
0x180015a7b  mov     rbp, rdx
0x180015a7e  call    cs:__imp_AcquireSRWLockExclusive
0x180015a84  cmp     byte ptr [rdi+4], 0
0x180015a88  mov     [rsp+58h+arg_0], rbx
0x180015a8d  jnz     short loc_180015AAF
0x180015a8f  mov     rcx, [rsp+58h]; this
0x180015a94  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180015a9b  mov     ebx, 80004004h
0x180015aa0  mov     edx, 53h ; 'S'; void *
0x180015aa5  mov     r9d, ebx; char *
0x180015aa8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015aad  jmp     short loc_180015AF4
0x180015aaf  or      esi, 0FFFFFFFFh
0x180015ab2  xor     ebx, ebx
0x180015ab4  cmp     ebx, 0E1h
0x180015aba  jnb     short loc_180015AEF
0x180015abc  lea     r8, off_180046160; "Other"
0x180015ac3  mov     r8, [r8+rbx*8]; lpString2
0x180015ac7  test    r8, r8
0x180015aca  jz      short loc_180015AE9
0x180015acc  or      r9d, 0FFFFFFFFh; cchCount2
0x180015ad0  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180015ad8  or      edx, r9d; cchCount1
0x180015adb  mov     rcx, rbp; lpString1
0x180015ade  call    cs:__imp_CompareStringOrdinal
0x180015ae4  cmp     eax, 2
0x180015ae7  jz      short loc_180015AED
0x180015ae9  inc     ebx
0x180015aeb  jmp     short loc_180015AB4
0x180015aed  mov     esi, ebx
0x180015aef  mov     [rdi+20h], esi
0x180015af2  xor     ebx, ebx
0x180015af4  lea     rcx, [rsp+58h+arg_0]
0x180015af9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015afe  mov     eax, ebx
0x180015b00  add     rsp, 38h
0x180015b04  pop     rdi
0x180015b05  pop     rsi
0x180015b06  pop     rbp
0x180015b07  pop     rbx
0x180015b08  retn
```
