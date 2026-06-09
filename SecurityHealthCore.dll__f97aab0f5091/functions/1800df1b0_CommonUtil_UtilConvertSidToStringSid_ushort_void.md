# CommonUtil::UtilConvertSidToStringSid(ushort * *,void *)

- ea: `0x1800df1b0`
- end: `0x1800df238`
- name: `?UtilConvertSidToStringSid@CommonUtil@@YAJPEAPEAGPEAX@Z`
- size: `136`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, PSID Sid, void *)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180079a00`
- `0x1800c0b00`
- `0x1800c3950`
- `0x1800c7ffc`
- `0x1800df59c`

## callees

- `0x18000d7fc`
- `0x1800df1b0`
- `0x1800dfc38`
- `0x1800e1690`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800df22a`
- `KERNEL32!LocalFree` at `0x1800df22a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800df1cd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800df1cd`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilConvertSidToStringSid(CommonUtil *this, PSID Sid, void *a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  const unsigned __int16 *v6; // r8
  unsigned int LastFailure; // ebx
  LPWSTR StringSid; // [rsp+40h] [rbp+18h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    LastFailure = CommonUtil::HrDuplicateStringW(this, (unsigned __int16 **)StringSid, v6);
  }
  else
  {
    LastFailure = HrGetLastFailure(v5, v4);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ee4acfd975e835558bdcbd8589408d45_Traceguids, LastFailure);
  }
  if ( StringSid )
    LocalFree(StringSid);
  return LastFailure;
}

```

## disassembly

```asm
0x1800df1b0  push    rbx
0x1800df1b2  sub     rsp, 20h
0x1800df1b6  mov     rax, rdx
0x1800df1b9  mov     [rsp+28h+StringSid], 0
0x1800df1c2  mov     rbx, rcx
0x1800df1c5  lea     rdx, [rsp+28h+StringSid]; StringSid
0x1800df1ca  mov     rcx, rax; Sid
0x1800df1cd  call    cs:__imp_ConvertSidToStringSidW
0x1800df1d3  test    eax, eax
0x1800df1d5  jnz     short loc_1800DF211
0x1800df1d7  call    HrGetLastFailure
0x1800df1dc  mov     ebx, eax
0x1800df1de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800df1e5  lea     rax, WPP_GLOBAL_Control
0x1800df1ec  cmp     rcx, rax
0x1800df1ef  jz      short loc_1800DF220
0x1800df1f1  test    byte ptr [rcx+1Ch], 1
0x1800df1f5  jz      short loc_1800DF220
0x1800df1f7  mov     rcx, [rcx+10h]
0x1800df1fb  lea     r8, WPP_ee4acfd975e835558bdcbd8589408d45_Traceguids
0x1800df202  mov     edx, 0Fh
0x1800df207  mov     r9d, ebx
0x1800df20a  call    WPP_SF_d
0x1800df20f  jmp     short loc_1800DF220
0x1800df211  mov     rdx, [rsp+28h+StringSid]; unsigned __int16 **
0x1800df216  mov     rcx, rbx; this
0x1800df219  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x1800df21e  mov     ebx, eax
0x1800df220  mov     rcx, [rsp+28h+StringSid]; hMem
0x1800df225  test    rcx, rcx
0x1800df228  jz      short loc_1800DF230
0x1800df22a  call    cs:__imp_LocalFree
0x1800df230  mov     eax, ebx
0x1800df232  add     rsp, 20h
0x1800df236  pop     rbx
0x1800df237  retn
```
