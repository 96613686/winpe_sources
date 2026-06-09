# Broker::SebEvent::OnDisable(bool)

- ea: `0x1800034d0`
- end: `0x1800036e8`
- name: `?OnDisable@SebEvent@Broker@@QEAAX_N@Z`
- size: `536`
- prototype: `void __fastcall(Broker::SebEvent *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003330`

## callees

- `0x180003120`
- `0x1800034d0`
- `0x180008c00`
- `0x18001d9ac`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800034eb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003599`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800034eb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003599`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000355c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000352f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000355c`
- `ntdll!RtlWakeAddressAll` at `0x180003553`
- `ntdll!RtlWakeAddressAll` at `0x180003553`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180003584`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180003584`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800034f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000359f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800034f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000359f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::SebEvent::OnDisable(Broker::SebEvent *this)
{
  char *v2; // rbx
  __int64 v3; // rdx
  _QWORD *v4; // rcx
  __int64 v5; // rbp
  int v6; // eax
  void **pExceptionObject; // [rsp+40h] [rbp-48h] BYREF
  __int128 v8; // [rsp+48h] [rbp-40h]
  int v9; // [rsp+58h] [rbp-30h]

  v2 = (char *)this + 208;
  RtlAcquireSRWLockExclusive((char *)this + 208);
  GetCurrentThreadId();
  v4 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids,
      *((_QWORD *)this + 28));
    v4 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 33) )
  {
    v5 = *((_QWORD *)this + 22);
    *((_QWORD *)this + 22) = 0;
    *((_DWORD *)this + 33) = 0;
    RtlWakeAddressAll((char *)this + 132, v3);
    RtlReleaseSRWLockExclusive(v2);
    if ( v5 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF__guid_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids,
          *((_QWORD *)this + 28));
      v6 = RtlUnsubscribeWnfNotificationWaitForCompletion(v5);
      if ( (int)(v6 + 0x80000000) >= 0 && v6 != -1073741772 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF__guid_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids,
            *((_QWORD *)this + 28),
            v6);
        v8 = 0;
        v9 = 7;
        pExceptionObject = &Broker::EventInternalError::`vftable';
        throw (Broker::EventInternalError *)&pExceptionObject;
      }
    }
    else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF__guid_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids,
        *((_QWORD *)this + 28),
        *((_DWORD *)this + 33));
    }
    RtlAcquireSRWLockExclusive(v2);
    GetCurrentThreadId();
    v4 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 4u )
    WPP_SF__guid_(v4[2], 33, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, *((_QWORD *)this + 28));
  RtlReleaseSRWLockExclusive(v2);
}

```

## disassembly

```asm
0x1800034d0  push    rbx
0x1800034d2  push    rbp
0x1800034d3  push    rsi
0x1800034d4  push    rdi
0x1800034d5  sub     rsp, 68h
0x1800034d9  mov     rsi, rcx
0x1800034dc  lea     rbx, [rcx+0D0h]
0x1800034e3  mov     [rsp+88h+var_58], rbx
0x1800034e8  mov     rcx, rbx
0x1800034eb  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800034f1  call    cs:__imp_GetCurrentThreadId
0x1800034f7  mov     [rsp+88h+var_4C], eax
0x1800034fb  mov     [rsp+88h+var_50], 1
0x180003500  mov     rcx, cs:WPP_GLOBAL_Control
0x180003507  test    byte ptr [rcx+1Ch], 40h
0x18000350b  jnz     loc_180003619
0x180003511  cmp     dword ptr [rsi+84h], 0
0x180003518  jnz     short loc_180003536
0x18000351a  test    byte ptr [rcx+1Ch], 40h
0x18000351e  jnz     loc_18000364B
0x180003524  mov     rcx, rbx
0x180003527  add     rsp, 68h
0x18000352b  pop     rdi
0x18000352c  pop     rsi
0x18000352d  pop     rbp
0x18000352e  pop     rbx
0x18000352f  jmp     cs:__imp_RtlReleaseSRWLockExclusive
0x180003536  mov     rbp, [rsi+0B0h]
0x18000353d  xor     eax, eax
0x18000353f  mov     [rsi+0B0h], rax
0x180003546  mov     [rsi+84h], eax
0x18000354c  lea     rcx, [rsi+84h]
0x180003553  call    cs:__imp_RtlWakeAddressAll
0x180003559  mov     rcx, rbx
0x18000355c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180003562  mov     [rsp+88h+var_50], 0
0x180003567  test    rbp, rbp
0x18000356a  jz      loc_1800036A1
0x180003570  mov     rcx, cs:WPP_GLOBAL_Control
0x180003577  test    byte ptr [rcx+1Ch], 1
0x18000357b  jnz     loc_180003676
0x180003581  mov     rcx, rbp
0x180003584  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000358a  mov     edx, 80000000h
0x18000358f  lea     ecx, [rax+rdx]
0x180003592  test    edx, ecx
0x180003594  jz      short loc_1800035B1
0x180003596  mov     rcx, rbx
0x180003599  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000359f  call    cs:__imp_GetCurrentThreadId
0x1800035a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035ac  jmp     loc_18000351A
0x1800035b1  cmp     eax, 0C0000034h
0x1800035b6  jz      short loc_180003596
0x1800035b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035bf  test    byte ptr [rcx+1Ch], 40h
0x1800035c3  jz      short loc_1800035EB
0x1800035c5  cmp     byte ptr [rcx+19h], 2
0x1800035c9  jb      short loc_1800035EB
0x1800035cb  mov     edx, 20h ; ' '
0x1800035d0  mov     [rsp+88h+var_68], eax
0x1800035d4  mov     r9, [rsi+0E0h]
0x1800035db  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x1800035e2  mov     rcx, [rcx+10h]
0x1800035e6  call    WPP_SF__guid_D
0x1800035eb  xorps   xmm0, xmm0
0x1800035ee  movups  [rsp+88h+var_40], xmm0
0x1800035f3  mov     [rsp+88h+var_30], 7
0x1800035fb  lea     rax, ??_7EventInternalError@Broker@@6B@; const Broker::EventInternalError::`vftable'
0x180003602  mov     [rsp+88h+pExceptionObject], rax
0x180003607  lea     rdx, _TI3?AUEventInternalError@Broker@@; pThrowInfo
0x18000360e  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180003613  call    _CxxThrowException_0
0x180003619  cmp     byte ptr [rcx+19h], 4
0x18000361d  jb      loc_180003511
0x180003623  mov     edx, 1Dh
0x180003628  mov     r9, [rsi+0E0h]
0x18000362f  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x180003636  mov     rcx, [rcx+10h]
0x18000363a  call    WPP_SF__guid_
0x18000363f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003646  jmp     loc_180003511
0x18000364b  cmp     byte ptr [rcx+19h], 4
0x18000364f  jb      loc_180003524
0x180003655  mov     edx, 21h ; '!'
0x18000365a  mov     r9, [rsi+0E0h]
0x180003661  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x180003668  mov     rcx, [rcx+10h]
0x18000366c  call    WPP_SF__guid_
0x180003671  jmp     loc_180003524
0x180003676  cmp     byte ptr [rcx+19h], 4
0x18000367a  jb      loc_180003581
0x180003680  mov     edx, 1Fh
0x180003685  mov     r9, [rsi+0E0h]
0x18000368c  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x180003693  mov     rcx, [rcx+10h]
0x180003697  call    WPP_SF__guid_
0x18000369c  jmp     loc_180003581
0x1800036a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036a8  test    byte ptr [rcx+1Ch], 40h
0x1800036ac  jz      loc_180003596
0x1800036b2  cmp     byte ptr [rcx+19h], 2
0x1800036b6  jb      loc_180003596
0x1800036bc  mov     edx, 1Eh
0x1800036c1  mov     eax, [rsi+84h]
0x1800036c7  mov     [rsp+88h+var_68], eax
0x1800036cb  mov     r9, [rsi+0E0h]
0x1800036d2  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x1800036d9  mov     rcx, [rcx+10h]
0x1800036dd  call    WPP_SF__guid_D
0x1800036e2  jmp     loc_180003596
```
