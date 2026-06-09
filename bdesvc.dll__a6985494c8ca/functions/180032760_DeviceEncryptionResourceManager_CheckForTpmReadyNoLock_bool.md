# DeviceEncryptionResourceManager::CheckForTpmReadyNoLock(bool *)

- ea: `0x180032760`
- end: `0x180032936`
- name: `?CheckForTpmReadyNoLock@DeviceEncryptionResourceManager@@IEAAJPEA_N@Z`
- size: `470`
- prototype: `__int64 __fastcall(DeviceEncryptionResourceManager *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18003261c`
- `0x180074540`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18002ef64`
- `0x180032760`
- `0x180034070`
- `0x18006a26c`
- `0x18006a594`

## import_xrefs

- `FVEAPI!FveCheckTpmCapability` at `0x180032802`
- `FVEAPI!FveCheckTpmCapability` at `0x180032802`

## string_xrefs

- `0x1800327a6`: `SimulateDETpmNotReady`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeviceEncryptionResourceManager::CheckForTpmReadyNoLock(
        DeviceEncryptionResourceManager *this,
        bool *a2)
{
  int v4; // ebx
  unsigned int v5; // eax
  PVOID *v6; // rcx
  bool v8; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v9[2]; // [rsp+28h] [rbp-58h] BYREF
  _QWORD v10[2]; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v11[3]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v12; // [rsp+60h] [rbp-20h] BYREF

  v12 = 0;
  v8 = 0;
  v4 = 0;
  if ( *((_BYTE *)this + 88) )
  {
LABEL_21:
    *a2 = *((_BYTE *)this + 88);
    if ( !*((_BYTE *)this + 88) )
    {
      v9[0] = 0;
      memset(v11, 0, sizeof(v11));
      v10[1] = v10;
      v10[0] = v10;
      v9[1] = FVE_DE_TPM_NOT_READY_FOR_BITLOCKER;
      FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)v11, (struct _FVEAPI_EVENT_DATA_COLLECTION *)v9);
      FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)v11);
    }
    return (unsigned int)v4;
  }
  NgscbGet_TEST_BooleanOverride(L"SimulateDETpmNotReady", &v8);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids);
    goto LABEL_21;
  }
  *(_QWORD *)&v12 = 0x100000010LL;
  v5 = FveCheckTpmCapability(&v12);
  v4 = v5;
  if ( !v5 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_13:
    if ( DWORD2(v12) )
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
        WPP_SF_d(v6[2], 50, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, DWORD2(v12));
    }
    else
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
        WPP_SF_(v6[2], 51, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids);
      *((_BYTE *)this + 88) = 1;
    }
    goto LABEL_21;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v5);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 >= 0 )
    goto LABEL_13;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180032760  mov     [rsp-18h+arg_10], rbx
0x180032765  mov     [rsp-18h+arg_18], rsi
0x18003276a  push    rbp
0x18003276b  push    rdi
0x18003276c  push    r14
0x18003276e  mov     rbp, rsp
0x180032771  sub     rsp, 80h
0x180032778  mov     rax, cs:__security_cookie
0x18003277f  xor     rax, rsp
0x180032782  mov     [rbp+var_10], rax
0x180032786  mov     r14, rdx
0x180032789  mov     rsi, rcx
0x18003278c  xorps   xmm0, xmm0
0x18003278f  movups  [rbp+var_20], xmm0
0x180032793  mov     [rbp+var_60], 0
0x180032797  xor     ebx, ebx
0x180032799  cmp     [rcx+58h], bl
0x18003279c  jnz     loc_1800328B0
0x1800327a2  lea     rdx, [rbp+var_60]; bool *
0x1800327a6  lea     rcx, aSimulatedetpmn; "SimulateDETpmNotReady"
0x1800327ad  call    ?NgscbGet_TEST_BooleanOverride@@YA_NPEBGPEA_N@Z; NgscbGet_TEST_BooleanOverride(ushort const *,bool *)
0x1800327b2  cmp     [rbp+var_60], bl
0x1800327b5  jz      short loc_1800327F0
0x1800327b7  lea     rdi, WPP_GLOBAL_Control
0x1800327be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327c5  cmp     rcx, rdi
0x1800327c8  jz      loc_1800328B0
0x1800327ce  test    byte ptr [rcx+1Ch], 8
0x1800327d2  jz      loc_1800328B0
0x1800327d8  lea     edx, [rbx+30h]
0x1800327db  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x1800327e2  mov     rcx, [rcx+10h]
0x1800327e6  call    WPP_SF_
0x1800327eb  jmp     loc_1800328B0
0x1800327f0  mov     dword ptr [rbp+var_20], 10h
0x1800327f7  mov     dword ptr [rbp+var_20+4], 1
0x1800327fe  lea     rcx, [rbp+var_20]
0x180032802  call    cs:__imp_FveCheckTpmCapability
0x180032809  nop     dword ptr [rax+rax+00h]
0x18003280e  mov     ebx, eax
0x180032810  lea     rdi, WPP_GLOBAL_Control
0x180032817  test    eax, eax
0x180032819  jz      short loc_180032856
0x18003281b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032822  cmp     rcx, rdi
0x180032825  jz      short loc_18003284C
0x180032827  test    byte ptr [rcx+1Ch], 40h
0x18003282b  jz      short loc_18003284C
0x18003282d  mov     edx, 31h ; '1'
0x180032832  mov     r9d, eax
0x180032835  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x18003283c  mov     rcx, [rcx+10h]
0x180032840  call    WPP_SF_d
0x180032845  mov     rcx, cs:WPP_GLOBAL_Control
0x18003284c  test    ebx, ebx
0x18003284e  js      loc_18003290F
0x180032854  jmp     short loc_18003285D
0x180032856  mov     rcx, cs:WPP_GLOBAL_Control
0x18003285d  mov     r9d, dword ptr [rbp+var_20+8]
0x180032861  test    r9d, r9d
0x180032864  jz      short loc_180032888
0x180032866  cmp     rcx, rdi
0x180032869  jz      short loc_1800328AC
0x18003286b  test    byte ptr [rcx+1Ch], 8
0x18003286f  jz      short loc_1800328AC
0x180032871  mov     edx, 32h ; '2'
0x180032876  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x18003287d  mov     rcx, [rcx+10h]
0x180032881  call    WPP_SF_d
0x180032886  jmp     short loc_1800328AC
0x180032888  cmp     rcx, rdi
0x18003288b  jz      short loc_1800328A8
0x18003288d  test    byte ptr [rcx+1Ch], 8
0x180032891  jz      short loc_1800328A8
0x180032893  mov     edx, 33h ; '3'
0x180032898  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x18003289f  mov     rcx, [rcx+10h]
0x1800328a3  call    WPP_SF_
0x1800328a8  mov     byte ptr [rsi+58h], 1
0x1800328ac  test    ebx, ebx
0x1800328ae  js      short loc_18003290F
0x1800328b0  mov     al, [rsi+58h]
0x1800328b3  mov     [r14], al
0x1800328b6  cmp     byte ptr [rsi+58h], 0
0x1800328ba  jnz     short loc_18003290F
0x1800328bc  mov     [rbp+var_58], 0
0x1800328c4  mov     [rbp+var_38], 0
0x1800328cc  mov     [rbp+var_30], 0
0x1800328d4  mov     [rbp+var_28], 0
0x1800328dc  lea     rax, [rbp+var_48]
0x1800328e0  mov     [rbp+var_40], rax
0x1800328e4  lea     rax, [rbp+var_48]
0x1800328e8  mov     [rbp+var_48], rax
0x1800328ec  lea     rax, FVE_DE_TPM_NOT_READY_FOR_BITLOCKER
0x1800328f3  mov     [rbp+var_50], rax
0x1800328f7  lea     rdx, [rbp+var_58]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x1800328fb  lea     rcx, [rbp+var_38]; this
0x1800328ff  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x180032904  nop
0x180032905  lea     rcx, [rbp+var_38]; this
0x180032909  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x18003290e  nop
0x18003290f  mov     eax, ebx
0x180032911  mov     rcx, [rbp+var_10]
0x180032915  xor     rcx, rsp; StackCookie
0x180032918  call    __security_check_cookie
0x18003291d  lea     r11, [rsp+80h+var_s0]
0x180032925  mov     rbx, [r11+30h]
0x180032929  mov     rsi, [r11+38h]
0x18003292d  mov     rsp, r11
0x180032930  pop     r14
0x180032932  pop     rdi
0x180032933  pop     rbp
0x180032934  retn
```
