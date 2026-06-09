# RoutingMgr::UpdateForegroundApplicationState(ulong,bool)

- ea: `0x180035308`
- end: `0x1800354e3`
- name: `?UpdateForegroundApplicationState@RoutingMgr@@IEAAJK_N@Z`
- size: `475`
- prototype: `__int64 __fastcall(RoutingMgr *__hidden this, unsigned int, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180032200`

## callees

- `0x1800010f4`
- `0x1800049a0`
- `0x180035308`
- `0x1800354ec`
- `0x18003f0fc`
- `0x18003f280`
- `0x180040044`
- `0x180040774`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800353e1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800353e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800354b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800354b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035342`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035342`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800353a6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800353a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RoutingMgr::UpdateForegroundApplicationState(RoutingMgr *this, int a2, char a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r12
  int started; // edi
  __int64 v8; // rax
  __int64 i; // rsi
  RoutingRegistrationStore *v10; // r14
  __int64 *j; // rbx
  __int64 *v12; // r15
  unsigned int v13; // ebx
  unsigned int v15; // [rsp+30h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+38h] [rbp-50h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 80);
  v16.Ptr = (ULONGLONG)this + 80;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  LOBYTE(v16.Size) = 1;
  started = 0;
  if ( !a3 && *((_BYTE *)this + 177) )
  {
    v8 = *((_QWORD *)this + 16);
    for ( i = *((_QWORD *)this + 15); i != v8 && (*(_DWORD *)(i + 132) != a2 || *(_BYTE *)(i + 136)); i += 140 )
      ;
    if ( i != v8 )
    {
      *(_BYTE *)(i + 136) = 1;
      SubmitThreadpoolWork(*((PTP_WORK *)this + 51));
      v10 = (RoutingRegistrationStore *)*((_QWORD *)this + 19);
      v15 = 0;
      started = RoutingRegistrationStore::StartTransaction(v10, &v15);
      if ( started < 0 )
      {
LABEL_19:
        v13 = v15;
      }
      else
      {
        for ( j = (__int64 *)**((_QWORD **)v10 + 2); j != *((__int64 **)v10 + 2); j = v12 )
        {
          v12 = (__int64 *)*j;
          if ( !(unsigned int)_o__wcsicmp(j + 2, i) && *((_DWORD *)j + 42) == 1 )
          {
            started = RoutingRegistrationStore::Disable(v10, (struct RoutingEntry *)(j + 2));
            if ( started < 0 )
              goto LABEL_19;
          }
        }
        v13 = v15;
        started = RoutingRegistrationStore::Commit(v10, v15);
        if ( started >= 0 )
          v13 = 0;
      }
      if ( v13 )
        RoutingRegistrationStore::Rollback(v10, v13);
      if ( started >= 0 )
      {
        if ( !*((_BYTE *)this + 176) || (started = RoutingMgr::UpdateRoutingTableInController(this, 0), started >= 0) )
        {
          if ( (unsigned int)dword_18012F048 > 5
            && (qword_18012F058 & 0x200000000000LL) != 0
            && (qword_18012F060 & 0x200000000000LL) == qword_18012F060 )
          {
            tlgWriteTransfer_EventWriteTransfer(
              (__int64)&dword_18012F048,
              (unsigned __int8 *)byte_18011C939,
              0,
              0,
              2u,
              &v16);
          }
        }
      }
    }
  }
  LeaveCriticalSection(v6);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180035308  mov     [rsp+arg_8], rbx
0x18003530d  mov     [rsp+arg_10], rbp
0x180035312  push    rsi
0x180035313  push    rdi
0x180035314  push    r12
0x180035316  push    r14
0x180035318  push    r15
0x18003531a  sub     rsp, 60h
0x18003531e  mov     rax, cs:__security_cookie
0x180035325  xor     rax, rsp
0x180035328  mov     [rsp+88h+var_30], rax
0x18003532d  mov     bl, r8b
0x180035330  mov     r14d, edx
0x180035333  mov     rbp, rcx
0x180035336  lea     r12, [rcx+50h]
0x18003533a  mov     [rsp+88h+var_50], r12
0x18003533f  mov     rcx, r12; lpCriticalSection
0x180035342  call    cs:__imp_EnterCriticalSection
0x180035348  mov     [rsp+88h+var_48], 1
0x18003534d  xor     edi, edi
0x18003534f  test    bl, bl
0x180035351  jnz     loc_1800354B2
0x180035357  cmp     [rbp+0B1h], dil
0x18003535e  jz      loc_1800354B2
0x180035364  mov     rax, [rbp+80h]
0x18003536b  mov     rsi, [rbp+78h]
0x18003536f  jmp     short loc_18003538A
0x180035371  cmp     [rsi+84h], r14d
0x180035378  jnz     short loc_180035383
0x18003537a  cmp     [rsi+88h], dil
0x180035381  jz      short loc_18003538F
0x180035383  add     rsi, 8Ch
0x18003538a  cmp     rsi, rax
0x18003538d  jnz     short loc_180035371
0x18003538f  cmp     rsi, rax
0x180035392  jz      loc_1800354B2
0x180035398  mov     byte ptr [rsi+88h], 1
0x18003539f  mov     rcx, [rbp+198h]; pwk
0x1800353a6  call    cs:__imp_SubmitThreadpoolWork
0x1800353ac  mov     r14, [rbp+98h]
0x1800353b3  mov     [rsp+88h+var_58], edi
0x1800353b7  lea     rdx, [rsp+88h+var_58]; unsigned int *
0x1800353bc  mov     rcx, r14; this
0x1800353bf  call    ?StartTransaction@RoutingRegistrationStore@@AEAAJPEAK@Z; RoutingRegistrationStore::StartTransaction(ulong *)
0x1800353c4  mov     edi, eax
0x1800353c6  test    eax, eax
0x1800353c8  js      short loc_180035424
0x1800353ca  mov     rbx, [r14+10h]
0x1800353ce  mov     rbx, [rbx]
0x1800353d1  cmp     rbx, [r14+10h]
0x1800353d5  jz      short loc_18003540B
0x1800353d7  mov     r15, [rbx]
0x1800353da  mov     rdx, rsi
0x1800353dd  lea     rcx, [rbx+10h]
0x1800353e1  call    cs:__imp__o__wcsicmp
0x1800353e7  test    eax, eax
0x1800353e9  jnz     short loc_180035406
0x1800353eb  cmp     dword ptr [rbx+0A8h], 1
0x1800353f2  jnz     short loc_180035406
0x1800353f4  lea     rdx, [rbx+10h]; struct RoutingEntry *
0x1800353f8  mov     rcx, r14; this
0x1800353fb  call    ?Disable@RoutingRegistrationStore@@AEAAJAEAURoutingEntry@@@Z; RoutingRegistrationStore::Disable(RoutingEntry &)
0x180035400  mov     edi, eax
0x180035402  test    eax, eax
0x180035404  js      short loc_180035424
0x180035406  mov     rbx, r15
0x180035409  jmp     short loc_1800353D1
0x18003540b  mov     ebx, [rsp+88h+var_58]
0x18003540f  mov     edx, ebx; unsigned int
0x180035411  mov     rcx, r14; this
0x180035414  call    ?Commit@RoutingRegistrationStore@@QEAAJK@Z; RoutingRegistrationStore::Commit(ulong)
0x180035419  mov     edi, eax
0x18003541b  xor     eax, eax
0x18003541d  test    edi, edi
0x18003541f  cmovns  ebx, eax
0x180035422  jmp     short loc_180035428
0x180035424  mov     ebx, [rsp+88h+var_58]
0x180035428  test    ebx, ebx
0x18003542a  jz      short loc_180035436
0x18003542c  mov     edx, ebx; unsigned int
0x18003542e  mov     rcx, r14; this
0x180035431  call    ?Rollback@RoutingRegistrationStore@@QEAAJK@Z; RoutingRegistrationStore::Rollback(ulong)
0x180035436  test    edi, edi
0x180035438  js      short loc_1800354B2
0x18003543a  cmp     byte ptr [rbp+0B0h], 0
0x180035441  jz      short loc_180035453
0x180035443  xor     edx, edx; bool
0x180035445  mov     rcx, rbp; this
0x180035448  call    ?UpdateRoutingTableInController@RoutingMgr@@AEAAJ_N@Z; RoutingMgr::UpdateRoutingTableInController(bool)
0x18003544d  mov     edi, eax
0x18003544f  test    eax, eax
0x180035451  js      short loc_1800354B2
0x180035453  mov     ecx, cs:dword_18012F048
0x180035459  cmp     ecx, 5
0x18003545c  jbe     short loc_1800354B2
0x18003545e  mov     rdx, cs:qword_18012F060
0x180035465  mov     rcx, cs:qword_18012F058
0x18003546c  mov     r8, 200000000000h
0x180035476  test    r8, rcx
0x180035479  jz      short loc_1800354B2
0x18003547b  mov     rax, rdx
0x18003547e  and     rax, r8
0x180035481  cmp     rax, rdx
0x180035484  jnz     short loc_1800354B2
0x180035486  lea     rax, [rsp+88h+var_50]
0x18003548b  mov     [rsp+88h+var_60], rax
0x180035490  mov     [rsp+88h+var_68], 2
0x180035498  xor     r9d, r9d
0x18003549b  xor     r8d, r8d
0x18003549e  lea     rdx, byte_18011C939
0x1800354a5  lea     rcx, dword_18012F048
0x1800354ac  call    _tlgWriteTransfer_EventWriteTransfer
0x1800354b1  nop
0x1800354b2  mov     rcx, r12; lpCriticalSection
0x1800354b5  call    cs:__imp_LeaveCriticalSection
0x1800354bb  mov     eax, edi
0x1800354bd  mov     rcx, [rsp+88h+var_30]
0x1800354c2  xor     rcx, rsp; StackCookie
0x1800354c5  call    __security_check_cookie
0x1800354ca  lea     r11, [rsp+88h+var_28]
0x1800354cf  mov     rbx, [r11+38h]
0x1800354d3  mov     rbp, [r11+40h]
0x1800354d7  mov     rsp, r11
0x1800354da  pop     r15
0x1800354dc  pop     r14
0x1800354de  pop     r12
0x1800354e0  pop     rdi
0x1800354e1  pop     rsi
0x1800354e2  retn
```
