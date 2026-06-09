# CBroker::SebBroker::RegisterSystemNotifications(void)

- ea: `0x180020604`
- end: `0x1800207af`
- name: `?RegisterSystemNotifications@SebBroker@CBroker@@AEAAXXZ`
- size: `427`
- prototype: `void __fastcall(CBroker::SebBroker *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001c57c`

## callees

- `0x180005a50`
- `0x180008c00`
- `0x18001cf50`
- `0x1800202d0`
- `0x180020604`

## import_xrefs

- `POWRPROF!PowerSettingRegisterNotificationEx` at `0x1800206fd`
- `POWRPROF!PowerSettingRegisterNotificationEx` at `0x1800206fd`

## pseudocode

```c
void __fastcall CBroker::SebBroker::RegisterSystemNotifications(CBroker::SebBroker *this)
{
  _QWORD *v2; // rcx
  unsigned int v3; // ebx
  _QWORD *v4; // rdx
  __int64 v5; // [rsp+30h] [rbp-49h] BYREF
  __int128 v6; // [rsp+38h] [rbp-41h] BYREF
  _OWORD v7[5]; // [rsp+50h] [rbp-29h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v5 = 0;
  v3 = 0;
  v6 = 0;
  v7[1] = GUID_BATTERY_PERCENTAGE_REMAINING;
  v7[0] = GUID_GLOBAL_USER_PRESENCE;
  v7[3] = GUID_MONITOR_POWER_ON;
  v7[2] = GUID_ACDC_POWER_SOURCE;
  v7[4] = GUID_LOW_POWER_EPOCH;
  do
  {
    if ( (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 4u )
      WPP_SF_(v2[2], 55, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
    *((_QWORD *)&v6 + 1) = 0;
    *(_QWORD *)&v6 = CBroker::CSystemEventsBrokerSystemNotificationCallback;
    if ( !(unsigned int)PowerSettingRegisterNotificationEx(&v7[v3], 0xFFFFFFFFLL, 2, &v6, &v5) )
    {
      v4 = (_QWORD *)*((_QWORD *)this + 41);
      if ( v4 == *((_QWORD **)this + 42) )
      {
        std::vector<void *>::_Emplace_reallocate<void * const &>((char *)this + 320, v4, &v5);
      }
      else
      {
        *v4 = v5;
        *((_QWORD *)this + 41) += 8LL;
      }
      goto LABEL_15;
    }
    v2 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids, &v7[v3]);
LABEL_15:
      v2 = WPP_GLOBAL_Control;
    }
    ++v3;
    v5 = 0;
  }
  while ( v3 < 5 );
  if ( (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 4u )
    WPP_SF_(v2[2], 57, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
}

```

## disassembly

```asm
0x180020604  push    rbp
0x180020606  push    rbx
0x180020607  push    rsi
0x180020608  push    rdi
0x180020609  lea     rbp, [rsp-3Fh]
0x18002060e  sub     rsp, 0B8h
0x180020615  mov     rax, cs:__security_cookie
0x18002061c  xor     rax, rsp
0x18002061f  mov     [rbp+57h+var_30], rax
0x180020623  mov     rsi, rcx
0x180020626  mov     rcx, cs:WPP_GLOBAL_Control
0x18002062d  test    byte ptr [rcx+1Ch], 1
0x180020631  jz      short loc_180020655
0x180020633  cmp     byte ptr [rcx+19h], 4
0x180020637  jb      short loc_180020655
0x180020639  mov     rcx, [rcx+10h]
0x18002063d  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180020644  mov     edx, 36h ; '6'
0x180020649  call    WPP_SF_
0x18002064e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020655  movups  xmm1, xmmword ptr cs:GUID_BATTERY_PERCENTAGE_REMAINING.Data1
0x18002065c  mov     [rbp+57h+var_A0], 0
0x180020664  xor     ebx, ebx
0x180020666  xorps   xmm0, xmm0
0x180020669  movups  [rbp+57h+var_98], xmm0
0x18002066d  movups  xmm0, xmmword ptr cs:GUID_GLOBAL_USER_PRESENCE.Data1
0x180020674  movdqu  [rbp+57h+var_70], xmm1
0x180020679  movups  xmm1, xmmword ptr cs:GUID_MONITOR_POWER_ON.Data1
0x180020680  movdqu  [rbp+57h+var_80], xmm0
0x180020685  movups  xmm0, xmmword ptr cs:GUID_ACDC_POWER_SOURCE.Data1
0x18002068c  movdqu  [rbp+57h+var_50], xmm1
0x180020691  movdqu  [rbp+57h+var_60], xmm0
0x180020696  movups  xmm0, xmmword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x18002069d  movdqu  [rbp+57h+var_40], xmm0
0x1800206a2  test    byte ptr [rcx+1Ch], 1
0x1800206a6  jz      short loc_1800206C3
0x1800206a8  cmp     byte ptr [rcx+19h], 4
0x1800206ac  jb      short loc_1800206C3
0x1800206ae  mov     rcx, [rcx+10h]
0x1800206b2  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x1800206b9  mov     edx, 37h ; '7'
0x1800206be  call    WPP_SF_
0x1800206c3  lea     rax, ?CSystemEventsBrokerSystemNotificationCallback@CBroker@@YAKPEAXK0@Z; CBroker::CSystemEventsBrokerSystemNotificationCallback(void *,ulong,void *)
0x1800206ca  mov     qword ptr [rbp+57h+var_98+8], 0
0x1800206d2  mov     qword ptr [rbp+57h+var_98], rax
0x1800206d6  lea     rdi, [rbp+57h+var_80]
0x1800206da  movsxd  rax, ebx
0x1800206dd  lea     r9, [rbp+57h+var_98]
0x1800206e1  shl     rax, 4
0x1800206e5  mov     r8d, 2
0x1800206eb  add     rdi, rax
0x1800206ee  or      edx, 0FFFFFFFFh
0x1800206f1  lea     rax, [rbp+57h+var_A0]
0x1800206f5  mov     rcx, rdi
0x1800206f8  mov     [rsp+0D0h+var_B0], rax
0x1800206fd  call    cs:__imp_PowerSettingRegisterNotificationEx
0x180020703  test    eax, eax
0x180020705  jz      short loc_180020734
0x180020707  mov     rcx, cs:WPP_GLOBAL_Control
0x18002070e  test    byte ptr [rcx+1Ch], 1
0x180020712  jz      short loc_180020763
0x180020714  cmp     byte ptr [rcx+19h], 2
0x180020718  jb      short loc_180020763
0x18002071a  mov     rcx, [rcx+10h]
0x18002071e  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180020725  mov     edx, 38h ; '8'
0x18002072a  mov     r9, rdi
0x18002072d  call    WPP_SF__guid_
0x180020732  jmp     short loc_18002075C
0x180020734  lea     rcx, [rsi+140h]
0x18002073b  mov     rdx, [rcx+8]
0x18002073f  cmp     rdx, [rcx+10h]
0x180020743  jz      short loc_180020753
0x180020745  mov     rax, [rbp+57h+var_A0]
0x180020749  mov     [rdx], rax
0x18002074c  add     qword ptr [rcx+8], 8
0x180020751  jmp     short loc_18002075C
0x180020753  lea     r8, [rbp+57h+var_A0]
0x180020757  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x18002075c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020763  inc     ebx
0x180020765  mov     [rbp+57h+var_A0], 0
0x18002076d  cmp     ebx, 5
0x180020770  jb      loc_1800206A2
0x180020776  test    byte ptr [rcx+1Ch], 1
0x18002077a  jz      short loc_180020797
0x18002077c  cmp     byte ptr [rcx+19h], 4
0x180020780  jb      short loc_180020797
0x180020782  mov     rcx, [rcx+10h]
0x180020786  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18002078d  mov     edx, 39h ; '9'
0x180020792  call    WPP_SF_
0x180020797  mov     rcx, [rbp+57h+var_30]
0x18002079b  xor     rcx, rsp; StackCookie
0x18002079e  call    __security_check_cookie
0x1800207a3  add     rsp, 0B8h
0x1800207aa  pop     rdi
0x1800207ab  pop     rsi
0x1800207ac  pop     rbx
0x1800207ad  pop     rbp
0x1800207ae  retn
```
