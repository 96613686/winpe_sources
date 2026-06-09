# OnDemandBrokerClient::CancelBackgroundTaskLegacy(ulong,ulong,bool)

- ea: `0x180005230`
- end: `0x18000532f`
- name: `?CancelBackgroundTaskLegacy@OnDemandBrokerClient@@UEAAJKK_N@Z`
- size: `255`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *this, unsigned int, int, char)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003fe0`
- `0x180004010`
- `0x180004d44`
- `0x180005230`
- `0x1800056d4`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000531a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000531a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005301`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005301`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180005276`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180005276`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::CancelBackgroundTaskLegacy(
        OnDemandBrokerClient *this,
        unsigned int a2,
        int a3,
        char a4)
{
  OnDemandBrokerClient *v8; // rcx
  int UserSid; // ebx
  __int64 **v10; // rcx
  __int64 *i; // rax
  __int64 v12; // rcx
  void *Block; // [rsp+40h] [rbp-38h] BYREF
  struct _ODB_SESSION_ENTRY *v15[2]; // [rsp+50h] [rbp-28h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-18h] BYREF
  char v17; // [rsp+68h] [rbp-10h]
  HANDLE hObject; // [rsp+B0h] [rbp+38h] BYREF

  v15[0] = 0;
  Block = 0;
  hObject = 0;
  DevPlat::Shared::SimpleLock::SimpleLock(
    (DevPlat::Shared::SimpleLock *)&lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 16));
  QueryUserToken(0, &hObject);
  UserSid = OnDemandBrokerClient::GetUserSid(v8, hObject, &Block);
  if ( UserSid >= 0 )
  {
    UserSid = OnDemandBrokerClient::FindSessionById((OnDemandBrokerClient *)((char *)this - 8), a2, v15);
    if ( UserSid >= 0 )
    {
      v10 = (__int64 **)(*((_QWORD *)v15[0] + 3) + 120LL);
      for ( i = *v10; i != (__int64 *)v10; i = (__int64 *)*i )
      {
        if ( *((_DWORD *)i + 8) == a3 )
        {
          v12 = *((_QWORD *)this + 9);
          *(_OWORD *)v15 = *((_OWORD *)i + 1);
          UserSid = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, struct _ODB_SESSION_ENTRY **, char, int))(*(_QWORD *)v12 + 80LL))(
                      v12,
                      Block,
                      a2,
                      v15,
                      a4,
                      5632);
          goto LABEL_9;
        }
      }
      UserSid = -2147023728;
    }
  }
LABEL_9:
  CloseHandle(hObject);
  operator delete[](Block);
  if ( !v17 )
    LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x180005230  push    rbp
0x180005232  push    rbx
0x180005233  push    rsi
0x180005234  push    rdi
0x180005235  push    r14
0x180005237  push    r15
0x180005239  mov     rbp, rsp
0x18000523c  sub     rsp, 78h
0x180005240  mov     esi, edx
0x180005242  mov     [rbp+var_28], 0
0x18000524a  lea     rdx, [rcx+10h]; struct _RTL_CRITICAL_SECTION *
0x18000524e  mov     [rbp+Block], 0
0x180005256  mov     rdi, rcx
0x180005259  mov     [rbp+hObject], 0
0x180005261  lea     rcx, [rbp+lpCriticalSection]; this
0x180005265  mov     r15b, r9b
0x180005268  mov     r14d, r8d
0x18000526b  call    ??0SimpleLock@Shared@DevPlat@@QEAA@PEAU_RTL_CRITICAL_SECTION@@_N@Z; DevPlat::Shared::SimpleLock::SimpleLock(_RTL_CRITICAL_SECTION *,bool)
0x180005270  lea     rdx, [rbp+hObject]
0x180005274  xor     ecx, ecx
0x180005276  call    cs:__imp_QueryUserToken
0x18000527c  mov     rdx, [rbp+hObject]; void *
0x180005280  lea     r8, [rbp+Block]; void **
0x180005284  call    ?GetUserSid@OnDemandBrokerClient@@AEAAJPEAXPEAPEAX@Z; OnDemandBrokerClient::GetUserSid(void *,void * *)
0x180005289  mov     ebx, eax
0x18000528b  test    eax, eax
0x18000528d  js      short loc_1800052FD
0x18000528f  lea     rcx, [rdi-8]; this
0x180005293  mov     edx, esi; unsigned int
0x180005295  lea     r8, [rbp+var_28]; struct _ODB_SESSION_ENTRY **
0x180005299  call    ?FindSessionById@OnDemandBrokerClient@@AEAAJKPEAPEAU_ODB_SESSION_ENTRY@@@Z; OnDemandBrokerClient::FindSessionById(ulong,_ODB_SESSION_ENTRY * *)
0x18000529e  mov     ebx, eax
0x1800052a0  test    eax, eax
0x1800052a2  js      short loc_1800052FD
0x1800052a4  mov     rax, [rbp+var_28]
0x1800052a8  mov     rcx, [rax+18h]
0x1800052ac  add     rcx, 78h ; 'x'
0x1800052b0  mov     rax, [rcx]
0x1800052b3  cmp     rax, rcx
0x1800052b6  jz      short loc_1800052F8
0x1800052b8  cmp     [rax+20h], r14d
0x1800052bc  jz      short loc_1800052C3
0x1800052be  mov     rax, [rax]
0x1800052c1  jmp     short loc_1800052B3
0x1800052c3  movups  xmm0, xmmword ptr [rax+10h]
0x1800052c7  mov     rcx, [rdi+48h]
0x1800052cb  lea     r9, [rbp+var_28]
0x1800052cf  mov     rdx, [rbp+Block]
0x1800052d3  mov     r8d, esi
0x1800052d6  mov     [rsp+78h+var_50], 1600h
0x1800052de  movdqu  xmmword ptr [rbp+var_28], xmm0
0x1800052e3  mov     rax, [rcx]
0x1800052e6  mov     [rsp+78h+var_58], r15b
0x1800052eb  mov     rax, [rax+50h]
0x1800052ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052f4  mov     ebx, eax
0x1800052f6  jmp     short loc_1800052FD
0x1800052f8  mov     ebx, 80070490h
0x1800052fd  mov     rcx, [rbp+hObject]; hObject
0x180005301  call    cs:__imp_CloseHandle
0x180005307  mov     rcx, [rbp+Block]; Block
0x18000530b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005310  cmp     [rbp+var_10], 0
0x180005314  jnz     short loc_180005320
0x180005316  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18000531a  call    cs:__imp_LeaveCriticalSection
0x180005320  mov     eax, ebx
0x180005322  add     rsp, 78h
0x180005326  pop     r15
0x180005328  pop     r14
0x18000532a  pop     rdi
0x18000532b  pop     rsi
0x18000532c  pop     rbx
0x18000532d  pop     rbp
0x18000532e  retn
```
