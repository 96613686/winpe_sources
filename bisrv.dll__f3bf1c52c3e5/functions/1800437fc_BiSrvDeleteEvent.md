# BiSrvDeleteEvent

- ea: `0x1800437fc`
- end: `0x180043b6b`
- name: `BiSrvDeleteEvent`
- size: `879`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `4`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180043740`
- `0x180065324`
- `0x180091150`
- `0x180092fa0`

## callees

- `0x180001984`
- `0x1800073e4`
- `0x1800075f8`
- `0x180008560`
- `0x1800095b0`
- `0x18000a430`
- `0x18000b9d0`
- `0x18000d7c0`
- `0x18000da50`
- `0x18001027c`
- `0x1800121b0`
- `0x1800437fc`
- `0x18004df58`
- `0x180053100`
- `0x180078e24`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180043a94`
- `ntdll!RtlFreeHeap` at `0x180043a9c`
- `ntdll!RtlFreeHeap` at `0x180043a94`
- `ntdll!RtlFreeHeap` at `0x180043a9c`
- `ntdll!RtlEqualSid` at `0x1800438bb`
- `ntdll!RtlEqualSid` at `0x18004397d`
- `ntdll!RtlEqualSid` at `0x1800438bb`
- `ntdll!RtlEqualSid` at `0x18004397d`

## pseudocode

```c
__int64 __fastcall BiSrvDeleteEvent(void *Source1, __int64 *a2, void *a3)
{
  void *v5; // r14
  int v6; // ebx
  __int64 v7; // r8
  int v8; // esi
  PVOID v9; // rcx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rax
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  void *v19; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v21; // [rsp+68h] [rbp-98h] BYREF
  void *v22; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[400]; // [rsp+80h] [rbp-80h] BYREF

  v19 = Source1;
  v18 = 0;
  v5 = Source1;
  memset_0(v23, 0, 0x182u);
  P = 0;
  BipStorageSynchronizeWithInitialization();
  v6 = BipLookupEventByGuid(v5);
  if ( v6 >= 0 )
  {
    v6 = BipPackageIdFromOptionalFullName(&v18, v23, a2);
    if ( v6 < 0 )
    {
      v8 = 2000;
      goto LABEL_41;
    }
    if ( !a3 || MEMORY[0xA8] && RtlEqualSid(a3, MEMORY[0xA8]) )
    {
      v6 = 0;
      if ( v18
        && !(unsigned __int8)BipPackageIdIsEquivalent(v18, 192)
        && (v6 = -1073741823, v9 = WPP_GLOBAL_Control, (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0)
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
      }
      else if ( v6 >= 0 )
      {
        goto LABEL_34;
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
      v6 = -1073741823;
    }
    if ( !MEMORY[0xB8] )
      goto LABEL_33;
    if ( (unsigned __int8)BipIsDeviceHoloLens(v9) )
    {
      if ( !a3 || MEMORY[0xB8] && RtlEqualSid(a3, MEMORY[0xB8]) )
      {
        v6 = 0;
        if ( v18 )
        {
          if ( !(unsigned __int8)BipPackageIdIsEquivalent(v18, 192) )
          {
            v6 = -1073741823;
            v9 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
          }
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
        v6 = -1073741823;
      }
    }
    if ( v6 < 0 )
    {
LABEL_33:
      v8 = 3000;
      goto LABEL_40;
    }
LABEL_34:
    BipAcquireGlobalLock(v9);
    if ( MEMORY[0x18] >= 0 )
    {
      v6 = BipDeleteEvent(0);
      if ( v6 >= 0 )
      {
        BipLockWatchdogContextDisarmWatchdog(v10);
        LOBYTE(v12) = 1;
        BipSyncReleaseLock(&BipGlobalLock, v12);
        v8 = 0;
        v6 = 0;
        goto LABEL_40;
      }
      v8 = 5000;
    }
    else
    {
      v6 = -1073741275;
      v8 = 4000;
    }
    BipLockWatchdogContextDisarmWatchdog(v10);
    LOBYTE(v11) = 1;
    BipSyncReleaseLock(&BipGlobalLock, v11);
LABEL_40:
    v5 = v19;
    goto LABEL_41;
  }
  v8 = 1000;
LABEL_41:
  if ( v6 < 0 && (unsigned int)dword_1800C3098 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 3, v7) )
  {
    LODWORD(v19) = v8;
    v16 = &BipTraceLoggingNullSid;
    LODWORD(v18) = v6;
    if ( a3 )
      v16 = (__int64 *)a3;
    v21 = a2;
    P = v16;
    v22 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v13,
      (__int64)byte_1800B4759,
      v14,
      v15,
      (__int64 *)&v22,
      &v21,
      (__int64 *)&P,
      (__int64)&v18,
      (__int64)&v19);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800437fc  push    rbp
0x1800437fe  push    rbx
0x1800437ff  push    rsi
0x180043800  push    rdi
0x180043801  push    r12
0x180043803  push    r13
0x180043805  push    r14
0x180043807  lea     rbp, [rsp-120h]
0x18004380f  sub     rsp, 220h
0x180043816  mov     rax, cs:__security_cookie
0x18004381d  xor     rax, rsp
0x180043820  mov     [rbp+150h+var_40], rax
0x180043827  mov     r12, r8
0x18004382a  mov     [rsp+250h+var_1F8], rcx
0x18004382f  mov     r13, rdx
0x180043832  mov     [rsp+250h+var_200], 0
0x18004383b  mov     r14, rcx
0x18004383e  xor     edx, edx; Val
0x180043840  mov     r8d, 182h; Size
0x180043846  lea     rcx, [rbp+150h+var_1D0]; void *
0x18004384a  call    memset_0
0x18004384f  mov     [rsp+250h+P], 0
0x180043858  call    BipStorageSynchronizeWithInitialization
0x18004385d  lea     rdx, [rsp+250h+P]
0x180043862  mov     rcx, r14; Source1
0x180043865  call    BipLookupEventByGuid
0x18004386a  mov     rdi, [rsp+250h+P]
0x18004386f  mov     ebx, eax
0x180043871  test    eax, eax
0x180043873  jns     short loc_18004387F
0x180043875  mov     esi, 3E8h
0x18004387a  jmp     loc_180043A67
0x18004387f  mov     r8, r13
0x180043882  lea     rdx, [rbp+150h+var_1D0]
0x180043886  lea     rcx, [rsp+250h+var_200]
0x18004388b  call    BipPackageIdFromOptionalFullName
0x180043890  mov     ebx, eax
0x180043892  test    eax, eax
0x180043894  jns     short loc_1800438A0
0x180043896  mov     esi, 7D0h
0x18004389b  jmp     loc_180043A67
0x1800438a0  lea     r14, [rdi+0C0h]
0x1800438a7  test    r12, r12
0x1800438aa  jz      short loc_1800438F6
0x1800438ac  mov     rdx, [rdi+0A8h]; Sid2
0x1800438b3  test    rdx, rdx
0x1800438b6  jz      short loc_1800438C5
0x1800438b8  mov     rcx, r12; Sid1
0x1800438bb  call    cs:__imp_RtlEqualSid
0x1800438c1  test    al, al
0x1800438c3  jnz     short loc_1800438F6
0x1800438c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800438cc  test    byte ptr [rcx+1Ch], 40h
0x1800438d0  jz      short loc_1800438ED
0x1800438d2  cmp     byte ptr [rcx+19h], 2
0x1800438d6  jb      short loc_1800438ED
0x1800438d8  mov     rcx, [rcx+10h]
0x1800438dc  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x1800438e3  mov     edx, 0Ah
0x1800438e8  call    WPP_SF_
0x1800438ed  mov     esi, 0C0000001h
0x1800438f2  mov     ebx, esi
0x1800438f4  jmp     short loc_18004394E
0x1800438f6  xor     ebx, ebx
0x1800438f8  mov     esi, 0C0000001h
0x1800438fd  cmp     [rsp+250h+var_200], rbx
0x180043902  jz      short loc_180043946
0x180043904  test    r14, r14
0x180043907  jz      short loc_18004391A
0x180043909  mov     rcx, [rsp+250h+var_200]
0x18004390e  mov     rdx, r14
0x180043911  call    BipPackageIdIsEquivalent
0x180043916  test    al, al
0x180043918  jnz     short loc_180043946
0x18004391a  mov     ebx, esi
0x18004391c  mov     rcx, cs:WPP_GLOBAL_Control
0x180043923  test    byte ptr [rcx+1Ch], 40h
0x180043927  jz      short loc_180043946
0x180043929  cmp     byte ptr [rcx+19h], 2
0x18004392d  jb      short loc_180043946
0x18004392f  mov     rcx, [rcx+10h]
0x180043933  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x18004393a  mov     edx, 0Bh
0x18004393f  call    WPP_SF_
0x180043944  jmp     short loc_18004394E
0x180043946  test    ebx, ebx
0x180043948  jns     loc_180043A07
0x18004394e  cmp     qword ptr [rdi+0B8h], 0
0x180043956  jz      loc_180043A00
0x18004395c  call    BipIsDeviceHoloLens
0x180043961  test    al, al
0x180043963  jz      loc_1800439FC
0x180043969  test    r12, r12
0x18004396c  jz      short loc_1800439B3
0x18004396e  mov     rdx, [rdi+0B8h]; Sid2
0x180043975  test    rdx, rdx
0x180043978  jz      short loc_180043987
0x18004397a  mov     rcx, r12; Sid1
0x18004397d  call    cs:__imp_RtlEqualSid
0x180043983  test    al, al
0x180043985  jnz     short loc_1800439B3
0x180043987  mov     rcx, cs:WPP_GLOBAL_Control
0x18004398e  test    byte ptr [rcx+1Ch], 40h
0x180043992  jz      short loc_1800439AF
0x180043994  cmp     byte ptr [rcx+19h], 2
0x180043998  jb      short loc_1800439AF
0x18004399a  mov     rcx, [rcx+10h]
0x18004399e  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x1800439a5  mov     edx, 0Ah
0x1800439aa  call    WPP_SF_
0x1800439af  mov     ebx, esi
0x1800439b1  jmp     short loc_1800439FC
0x1800439b3  xor     ebx, ebx
0x1800439b5  cmp     [rsp+250h+var_200], rbx
0x1800439ba  jz      short loc_1800439FC
0x1800439bc  test    r14, r14
0x1800439bf  jz      short loc_1800439D2
0x1800439c1  mov     rcx, [rsp+250h+var_200]
0x1800439c6  mov     rdx, r14
0x1800439c9  call    BipPackageIdIsEquivalent
0x1800439ce  test    al, al
0x1800439d0  jnz     short loc_1800439FC
0x1800439d2  mov     ebx, esi
0x1800439d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800439db  test    byte ptr [rcx+1Ch], 40h
0x1800439df  jz      short loc_1800439FC
0x1800439e1  cmp     byte ptr [rcx+19h], 2
0x1800439e5  jb      short loc_1800439FC
0x1800439e7  mov     rcx, [rcx+10h]
0x1800439eb  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x1800439f2  mov     edx, 0Bh
0x1800439f7  call    WPP_SF_
0x1800439fc  test    ebx, ebx
0x1800439fe  jns     short loc_180043A07
0x180043a00  mov     esi, 0BB8h
0x180043a05  jmp     short loc_180043A62
0x180043a07  call    BipAcquireGlobalLock
0x180043a0c  cmp     dword ptr [rdi+18h], 0
0x180043a10  jge     short loc_180043A1E
0x180043a12  mov     ebx, 0C0000225h
0x180043a17  mov     esi, 0FA0h
0x180043a1c  jmp     short loc_180043A36
0x180043a1e  mov     edx, 3
0x180043a23  mov     rcx, rdi; P
0x180043a26  call    BipDeleteEvent
0x180043a2b  mov     ebx, eax
0x180043a2d  test    eax, eax
0x180043a2f  jns     short loc_180043A4B
0x180043a31  mov     esi, 1388h
0x180043a36  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x180043a3b  mov     dl, 1
0x180043a3d  lea     rcx, BipGlobalLock
0x180043a44  call    BipSyncReleaseLock
0x180043a49  jmp     short loc_180043A62
0x180043a4b  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x180043a50  mov     dl, 1
0x180043a52  lea     rcx, BipGlobalLock
0x180043a59  call    BipSyncReleaseLock
0x180043a5e  xor     esi, esi
0x180043a60  xor     ebx, ebx
0x180043a62  mov     r14, [rsp+250h+var_1F8]
0x180043a67  test    rdi, rdi
0x180043a6a  jz      short loc_180043ABD
0x180043a6c  or      eax, 0FFFFFFFFh
0x180043a6f  lock xadd [rdi+1Ch], eax
0x180043a74  cmp     eax, 1
0x180043a77  jnz     short loc_180043ABD
0x180043a79  mov     ecx, [rdi+30h]
0x180043a7c  sub     ecx, eax
0x180043a7e  jz      short loc_180043AAE
0x180043a80  sub     ecx, eax
0x180043a82  jz      short loc_180043AA4
0x180043a84  xor     edx, edx; Flags
0x180043a86  mov     r8, rdi; P
0x180043a89  cmp     ecx, eax
0x180043a8b  mov     rcx, cs:BipHeap; HeapHandle
0x180043a92  jz      short loc_180043A9C
0x180043a94  call    cs:__imp_RtlFreeHeap
0x180043a9a  jmp     short loc_180043ABD
0x180043a9c  call    cs:__imp_RtlFreeHeap
0x180043aa2  jmp     short loc_180043ABD
0x180043aa4  mov     rcx, rdi; struct _BI_WORK_ITEM *
0x180043aa7  call    BipWorkItemCheckQueueDestroy
0x180043aac  jmp     short loc_180043ABD
0x180043aae  mov     rdx, rdi
0x180043ab1  lea     rcx, qword_1800C4600; struct _BI_LOCK *
0x180043ab8  call    BipEventQueueDestroy
0x180043abd  test    ebx, ebx
0x180043abf  jns     loc_180043B48
0x180043ac5  mov     eax, cs:dword_1800C3098
0x180043acb  cmp     eax, 2
0x180043ace  jbe     short loc_180043B48
0x180043ad0  mov     edx, 3
0x180043ad5  lea     rcx, dword_1800C3098
0x180043adc  call    _tlgKeywordOn
0x180043ae1  test    al, al
0x180043ae3  jz      short loc_180043B48
0x180043ae5  test    r12, r12
0x180043ae8  mov     dword ptr [rsp+250h+var_1F8], esi
0x180043aec  lea     rax, BipTraceLoggingNullSid
0x180043af3  mov     dword ptr [rsp+250h+var_200], ebx
0x180043af7  cmovnz  rax, r12
0x180043afb  mov     [rsp+250h+var_1E8], r13
0x180043b00  mov     [rsp+250h+P], rax
0x180043b05  lea     rdx, byte_1800B4759
0x180043b0c  lea     rax, [rsp+250h+var_1F8]
0x180043b11  mov     [rsp+250h+var_1E0], r14
0x180043b16  mov     [rsp+250h+var_210], rax
0x180043b1b  lea     rax, [rsp+250h+var_200]
0x180043b20  mov     [rsp+250h+var_218], rax
0x180043b25  lea     rax, [rsp+250h+P]
0x180043b2a  mov     [rsp+250h+var_220], rax
0x180043b2f  lea     rax, [rsp+250h+var_1E8]
0x180043b34  mov     [rsp+250h+var_228], rax
0x180043b39  lea     rax, [rsp+250h+var_1E0]
0x180043b3e  mov     [rsp+250h+var_230], rax
0x180043b43  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSid<_SID>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSid<_SID> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180043b48  mov     eax, ebx
0x180043b4a  mov     rcx, [rbp+150h+var_40]
0x180043b51  xor     rcx, rsp; StackCookie
0x180043b54  call    __security_check_cookie
0x180043b59  add     rsp, 220h
0x180043b60  pop     r14
0x180043b62  pop     r13
0x180043b64  pop     r12
0x180043b66  pop     rdi
0x180043b67  pop     rsi
0x180043b68  pop     rbx
0x180043b69  pop     rbp
0x180043b6a  retn
```
