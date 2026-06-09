# Broker::TimeBroker::RegisterPowerNotification(void)

- ea: `0x180015e2c`
- end: `0x180015f34`
- name: `?RegisterPowerNotification@TimeBroker@Broker@@AEAAXXZ`
- size: `264`
- prototype: `void __fastcall(Broker::TimeBroker *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012458`

## callees

- `0x180003840`
- `0x180015e2c`

## import_xrefs

- `POWRPROF!PowerSettingRegisterNotificationEx` at `0x180015eca`
- `POWRPROF!PowerSettingRegisterNotificationEx` at `0x180015eca`

## pseudocode

```c
void __fastcall Broker::TimeBroker::RegisterPowerNotification(Broker::TimeBroker *this)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rbx
  __int128 v4; // [rsp+30h] [rbp-18h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v4 = 0;
  if ( (*((_DWORD *)v2 + 7) & 0x100) != 0 && *((_BYTE *)v2 + 25) >= 4u )
    WPP_SF_(v2[2], 19, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
  *((_QWORD *)&v4 + 1) = 0;
  v3 = (_QWORD *)((char *)this + 176);
  *(_QWORD *)&v4 = TimeBrokerPowerStateChangeCallback;
  if ( (unsigned int)PowerSettingRegisterNotificationEx(&GUID_LOW_POWER_EPOCH, 0xFFFFFFFFLL, 2, &v4, v3) )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
    *v3 = 0;
  }
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
}

```

## disassembly

```asm
0x180015e2c  mov     [rsp+arg_0], rbx
0x180015e31  push    rdi
0x180015e32  sub     rsp, 40h
0x180015e36  mov     rbx, rcx
0x180015e39  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e40  mov     edi, 100h
0x180015e45  test    [rcx+1Ch], edi
0x180015e48  jz      short loc_180015E6C
0x180015e4a  cmp     byte ptr [rcx+19h], 4
0x180015e4e  jb      short loc_180015E6C
0x180015e50  mov     rcx, [rcx+10h]
0x180015e54  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180015e5b  mov     edx, 12h
0x180015e60  call    WPP_SF_
0x180015e65  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e6c  xorps   xmm0, xmm0
0x180015e6f  movups  [rsp+48h+var_18], xmm0
0x180015e74  test    [rcx+1Ch], edi
0x180015e77  jz      short loc_180015E94
0x180015e79  cmp     byte ptr [rcx+19h], 4
0x180015e7d  jb      short loc_180015E94
0x180015e7f  mov     rcx, [rcx+10h]
0x180015e83  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180015e8a  mov     edx, 13h
0x180015e8f  call    WPP_SF_
0x180015e94  lea     rax, ?TimeBrokerPowerStateChangeCallback@@YAKPEAXK0@Z; TimeBrokerPowerStateChangeCallback(void *,ulong,void *)
0x180015e9b  mov     qword ptr [rsp+48h+var_18+8], 0
0x180015ea4  add     rbx, 0B0h
0x180015eab  mov     qword ptr [rsp+48h+var_18], rax
0x180015eb0  lea     r9, [rsp+48h+var_18]
0x180015eb5  mov     [rsp+48h+var_28], rbx
0x180015eba  mov     r8d, 2
0x180015ec0  lea     rcx, GUID_LOW_POWER_EPOCH
0x180015ec7  or      edx, 0FFFFFFFFh
0x180015eca  call    cs:__imp_PowerSettingRegisterNotificationEx
0x180015ed0  test    eax, eax
0x180015ed2  jz      short loc_180015F02
0x180015ed4  mov     rcx, cs:WPP_GLOBAL_Control
0x180015edb  test    [rcx+1Ch], edi
0x180015ede  jz      short loc_180015EFB
0x180015ee0  cmp     byte ptr [rcx+19h], 2
0x180015ee4  jb      short loc_180015EFB
0x180015ee6  mov     rcx, [rcx+10h]
0x180015eea  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180015ef1  mov     edx, 14h
0x180015ef6  call    WPP_SF_
0x180015efb  mov     qword ptr [rbx], 0
0x180015f02  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f09  test    [rcx+1Ch], edi
0x180015f0c  jz      short loc_180015F29
0x180015f0e  cmp     byte ptr [rcx+19h], 4
0x180015f12  jb      short loc_180015F29
0x180015f14  mov     rcx, [rcx+10h]
0x180015f18  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180015f1f  mov     edx, 15h
0x180015f24  call    WPP_SF_
0x180015f29  mov     rbx, [rsp+48h+arg_0]
0x180015f2e  add     rsp, 40h
0x180015f32  pop     rdi
0x180015f33  retn
```
