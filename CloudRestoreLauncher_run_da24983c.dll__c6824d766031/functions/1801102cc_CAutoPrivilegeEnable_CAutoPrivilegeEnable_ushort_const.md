# CAutoPrivilegeEnable::CAutoPrivilegeEnable(ushort const *)

- ea: `0x1801102cc`
- end: `0x180110385`
- name: `??0CAutoPrivilegeEnable@@QEAA@PEBG@Z`
- size: `185`
- prototype: `CAutoPrivilegeEnable *__fastcall(CAutoPrivilegeEnable *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800b708c`

## callees

- `0x18000c6e0`
- `0x1801102cc`
- `0x1801103e0`

## import_xrefs

- `ADVAPI32!AdjustTokenPrivileges` at `0x18011035d`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18011035d`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180110318`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180110318`

## string_xrefs

- `0x18011030a`: `SeTimeZonePrivilege`

## pseudocode

```c
CAutoPrivilegeEnable *__fastcall CAutoPrivilegeEnable::CAutoPrivilegeEnable(
        CAutoPrivilegeEnable *this,
        const unsigned __int16 *a2)
{
  void **v2; // rdi
  void *v4; // rcx
  DWORD ReturnLength; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  v2 = (void **)((char *)this + 8);
  *(_BYTE *)this = 0;
  *((_QWORD *)this + 1) = 0;
  if ( (int)SHOpenEffectiveToken((__int64)this, (__int64)a2, (void **)this + 1) >= 0 )
  {
    NewState = 0;
    if ( LookupPrivilegeValueW(0, L"SeTimeZonePrivilege", &NewState.Privileges[0].Luid) )
    {
      v4 = *v2;
      ReturnLength = 0;
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Attributes = 2;
      *(_BYTE *)this = AdjustTokenPrivileges(v4, 0, &NewState, 0x10u, (PTOKEN_PRIVILEGES)this + 1, &ReturnLength);
    }
  }
  return this;
}

```

## disassembly

```asm
0x1801102cc  mov     [rsp+arg_8], rbx
0x1801102d1  push    rdi
0x1801102d2  sub     rsp, 50h
0x1801102d6  mov     rax, cs:__security_cookie
0x1801102dd  xor     rax, rsp
0x1801102e0  mov     [rsp+58h+var_10], rax
0x1801102e5  lea     rdi, [rcx+8]
0x1801102e9  mov     byte ptr [rcx], 0
0x1801102ec  mov     r8, rdi; void **
0x1801102ef  mov     qword ptr [rdi], 0
0x1801102f6  mov     rbx, rcx
0x1801102f9  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x1801102fe  test    eax, eax
0x180110300  js      short loc_18011036A
0x180110302  xorps   xmm0, xmm0
0x180110305  lea     r8, [rsp+58h+NewState.Privileges]; lpLuid
0x18011030a  lea     rdx, aSetimezonepriv; "SeTimeZonePrivilege"
0x180110311  xor     ecx, ecx; lpSystemName
0x180110313  movups  xmmword ptr [rsp+38h], xmm0
0x180110318  call    cs:__imp_LookupPrivilegeValueW
0x18011031e  test    eax, eax
0x180110320  jz      short loc_18011036A
0x180110322  mov     rcx, [rdi]; TokenHandle
0x180110325  lea     rdx, [rbx+10h]
0x180110329  lea     rax, [rsp+58h+var_28]
0x18011032e  mov     [rsp+58h+var_28], 0
0x180110336  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18011033b  lea     r8, [rsp+58h+NewState]; NewState
0x180110340  mov     [rsp+58h+PreviousState], rdx; PreviousState
0x180110345  mov     r9d, 10h; BufferLength
0x18011034b  xor     edx, edx; DisableAllPrivileges
0x18011034d  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x180110355  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x18011035d  call    cs:__imp_AdjustTokenPrivileges
0x180110363  test    eax, eax
0x180110365  setnz   cl
0x180110368  mov     [rbx], cl
0x18011036a  mov     rax, rbx
0x18011036d  mov     rcx, [rsp+58h+var_10]
0x180110372  xor     rcx, rsp; StackCookie
0x180110375  call    __security_check_cookie
0x18011037a  mov     rbx, [rsp+58h+arg_8]
0x18011037f  add     rsp, 50h
0x180110383  pop     rdi
0x180110384  retn
```
