# CommonUtil::UtilConvertStringSidToSid(void * *,ushort const *)

- ea: `0x1800df240`
- end: `0x1800df2d5`
- name: `?UtilConvertStringSidToSid@CommonUtil@@YAJPEAPEAXPEBG@Z`
- size: `149`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, LPCWSTR StringSid, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c8b44`
- `0x1800cee78`
- `0x1800d1e1c`
- `0x1800dea40`

## callees

- `0x1800159a0`
- `0x1800df240`
- `0x1800df368`
- `0x1800e1690`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800df2c2`
- `KERNEL32!LocalFree` at `0x1800df2c2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800df261`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800df261`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilConvertStringSidToSid(
        CommonUtil *this,
        LPCWSTR StringSid,
        const unsigned __int16 *a3)
{
  int v3; // edi
  __int64 v5; // rdx
  __int64 v6; // rcx
  void *v7; // r8
  unsigned int LastFailure; // ebx
  PSID Sid; // [rsp+50h] [rbp+18h] BYREF

  v3 = (int)StringSid;
  Sid = 0;
  if ( ConvertStringSidToSidW(StringSid, &Sid) )
  {
    LastFailure = CommonUtil::UtilDuplicateSid(this, (void **)Sid, v7);
  }
  else
  {
    LastFailure = HrGetLastFailure(v6, v5);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_ee4acfd975e835558bdcbd8589408d45_Traceguids,
        v3,
        LastFailure);
  }
  if ( Sid )
    LocalFree(Sid);
  return LastFailure;
}

```

## disassembly

```asm
0x1800df240  mov     [rsp+arg_0], rbx
0x1800df245  push    rdi
0x1800df246  sub     rsp, 30h
0x1800df24a  mov     rdi, rdx
0x1800df24d  mov     [rsp+38h+Sid], 0
0x1800df256  mov     rbx, rcx
0x1800df259  lea     rdx, [rsp+38h+Sid]; Sid
0x1800df25e  mov     rcx, rdi; StringSid
0x1800df261  call    cs:__imp_ConvertStringSidToSidW
0x1800df267  test    eax, eax
0x1800df269  jnz     short loc_1800DF2A9
0x1800df26b  call    HrGetLastFailure
0x1800df270  mov     ebx, eax
0x1800df272  mov     rcx, cs:WPP_GLOBAL_Control
0x1800df279  lea     rax, WPP_GLOBAL_Control
0x1800df280  cmp     rcx, rax
0x1800df283  jz      short loc_1800DF2B8
0x1800df285  test    byte ptr [rcx+1Ch], 1
0x1800df289  jz      short loc_1800DF2B8
0x1800df28b  mov     rcx, [rcx+10h]
0x1800df28f  lea     r8, WPP_ee4acfd975e835558bdcbd8589408d45_Traceguids
0x1800df296  mov     edx, 0Eh
0x1800df29b  mov     [rsp+38h+var_18], ebx
0x1800df29f  mov     r9, rdi
0x1800df2a2  call    WPP_SF_Sd
0x1800df2a7  jmp     short loc_1800DF2B8
0x1800df2a9  mov     rdx, [rsp+38h+Sid]; void **
0x1800df2ae  mov     rcx, rbx; this
0x1800df2b1  call    ?UtilDuplicateSid@CommonUtil@@YAJPEAPEAXPEAX@Z; CommonUtil::UtilDuplicateSid(void * *,void *)
0x1800df2b6  mov     ebx, eax
0x1800df2b8  mov     rcx, [rsp+38h+Sid]; hMem
0x1800df2bd  test    rcx, rcx
0x1800df2c0  jz      short loc_1800DF2C8
0x1800df2c2  call    cs:__imp_LocalFree
0x1800df2c8  mov     eax, ebx
0x1800df2ca  mov     rbx, [rsp+38h+arg_0]
0x1800df2cf  add     rsp, 30h
0x1800df2d3  pop     rdi
0x1800df2d4  retn
```
