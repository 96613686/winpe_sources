# UpdateMachineSidCache

- ea: `0x1800258f8`
- end: `0x1800259cb`
- name: `UpdateMachineSidCache`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800256c8`

## callees

- `0x180004d91`
- `0x18000f35c`
- `0x18000f7e4`
- `0x180024754`
- `0x1800258f8`
- `0x18002c6c8`

## import_xrefs

- `msvcrt!free` at `0x1800259be`
- `msvcrt!free` at `0x1800259be`
- `ADVAPI32!GetLengthSid` at `0x180025916`
- `ADVAPI32!GetLengthSid` at `0x180025916`
- `mqsec!SetFalconKeyValue` at `0x18002593e`
- `mqsec!SetFalconKeyValue` at `0x18002593e`
- `mqsec!MQSec_UpdateLocalMachineSid` at `0x1800259b2`
- `mqsec!MQSec_UpdateLocalMachineSid` at `0x1800259b2`

## string_xrefs

- `0x180025937`: `security\MachineAccount`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void UpdateMachineSidCache()
{
  unsigned int v0; // edi
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF
  DWORD LengthSid; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v3; // [rsp+58h] [rbp+10h] BYREF
  PSID pSid; // [rsp+60h] [rbp+18h] BYREF

  pSid = 0;
  GetMachineSid(&pSid);
  LengthSid = GetLengthSid(pSid);
  v3 = 3;
  v0 = SetFalconKeyValue(L"security\\MachineAccount", &v3, pSid, &LengthSid);
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_f073386f5643352810e6d9a62b947684_Traceguids, v0);
    LogMsgNTStatus(v0, (wchar_t *)L"joinstat", 0x5E9u);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v0);
    throw (bad_win32_error *)pExceptionObject;
  }
  MQSec_UpdateLocalMachineSid(pSid);
  free(pSid);
}

```

## disassembly

```asm
0x1800258f8  push    rdi
0x1800258fa  sub     rsp, 40h
0x1800258fe  mov     [rsp+48h+pSid], 0
0x180025907  lea     rcx, [rsp+48h+pSid]
0x18002590c  call    GetMachineSid
0x180025911  mov     rcx, [rsp+48h+pSid]; pSid
0x180025916  call    cs:__imp_GetLengthSid
0x18002591c  mov     [rsp+48h+arg_0], eax
0x180025920  mov     [rsp+48h+arg_8], 3
0x180025928  lea     r9, [rsp+48h+arg_0]
0x18002592d  mov     r8, [rsp+48h+pSid]
0x180025932  lea     rdx, [rsp+48h+arg_8]
0x180025937  lea     rcx, aSecurityMachin; "security\\MachineAccount"
0x18002593e  call    cs:__imp_?SetFalconKeyValue@@YAJPEB_WPEAKPEBX1@Z; SetFalconKeyValue(wchar_t const *,ulong *,void const *,ulong *)
0x180025944  mov     edi, eax
0x180025946  test    eax, eax
0x180025948  jz      short loc_1800259AD
0x18002594a  lea     rax, WPP_GLOBAL_Control
0x180025951  mov     rcx, cs:WPP_GLOBAL_Control
0x180025958  cmp     rcx, rax
0x18002595b  jz      short loc_18002597B
0x18002595d  test    byte ptr [rcx+1Ch], 1
0x180025961  jz      short loc_18002597B
0x180025963  mov     edx, 53h ; 'S'
0x180025968  mov     r9d, edi
0x18002596b  lea     r8, WPP_f073386f5643352810e6d9a62b947684_Traceguids
0x180025972  mov     rcx, [rcx+10h]
0x180025976  call    WPP_SF_d
0x18002597b  mov     r8d, 5E9h; unsigned __int16
0x180025981  lea     rdx, aJoinstat; "joinstat"
0x180025988  mov     ecx, edi; int
0x18002598a  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18002598f  mov     edx, edi; unsigned int
0x180025991  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180025996  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18002599b  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x1800259a2  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800259a7  call    _CxxThrowException_0
0x1800259ad  mov     rcx, [rsp+48h+pSid]
0x1800259b2  call    cs:__imp_?MQSec_UpdateLocalMachineSid@@YAXPEAX@Z; MQSec_UpdateLocalMachineSid(void *)
0x1800259b8  nop
0x1800259b9  mov     rcx, [rsp+48h+pSid]; Block
0x1800259be  call    cs:__imp_free
0x1800259c4  nop
0x1800259c5  add     rsp, 40h
0x1800259c9  pop     rdi
0x1800259ca  retn
```
