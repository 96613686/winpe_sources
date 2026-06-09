# OnDemandBrokerClient::LaunchBackgroundTaskLegacy(ulong,ulong,ushort const *,uchar *,ulong,_OdbLaunchInfo *)

- ea: `0x180005b70`
- end: `0x180005e30`
- name: `?LaunchBackgroundTaskLegacy@OnDemandBrokerClient@@UEAAJKKPEBGPEAEKPEAU_OdbLaunchInfo@@@Z`
- size: `704`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *this, int, int, const unsigned __int16 *, unsigned __int8 *Source, unsigned int SourceSize, struct _OdbLaunchInfo *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003fe0`
- `0x180004010`
- `0x180004d44`
- `0x180004d50`
- `0x180004d78`
- `0x1800056d4`
- `0x1800058f0`
- `0x180005b70`
- `0x180006546`
- `0x180006570`
- `0x180007010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005cfb`
- `msvcrt!memcpy_s` at `0x180005cfb`
- `msvcrt!wcscpy_s` at `0x180005cdc`
- `msvcrt!wcscpy_s` at `0x180005cdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005df9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005df9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005de0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005de0`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180005c10`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180005c10`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::LaunchBackgroundTaskLegacy(
        OnDemandBrokerClient *this,
        int a2,
        int a3,
        const unsigned __int16 *a4,
        unsigned __int8 *Source,
        unsigned int SourceSize,
        struct _OdbLaunchInfo *a7)
{
  OnDemandBrokerClient *v11; // rcx
  int UserSid; // ebx
  OnDemandBrokerClient *v13; // rcx
  struct _ODB_SESSION_ENTRY *v14; // r13
  void *v15; // rax
  _DWORD *v16; // rsi
  __int64 v17; // rbx
  __int128 v18; // xmm6
  _DWORD *v19; // rax
  __int64 v20; // rcx
  _QWORD *v21; // rdx
  HANDLE hObject; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v24; // [rsp+80h] [rbp-88h]
  void *Block; // [rsp+88h] [rbp-80h] BYREF
  struct _ODB_SESSION_ENTRY *v26; // [rsp+90h] [rbp-78h] BYREF
  OnDemandBrokerClient *v27; // [rsp+98h] [rbp-70h]
  struct _OdbLaunchInfo *v28; // [rsp+A0h] [rbp-68h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A8h] [rbp-60h] BYREF
  char v30; // [rsp+B0h] [rbp-58h]
  __int128 v31; // [rsp+B8h] [rbp-50h] BYREF
  wchar_t v32[128]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v33[520]; // [rsp+1C8h] [rbp+C0h] BYREF
  _BYTE v34[24]; // [rsp+3D0h] [rbp+2C8h] BYREF

  v24 = a2;
  v27 = this;
  v28 = a7;
  v26 = 0;
  v31 = 0;
  memset_0(v32, 0, 0x318u);
  Block = 0;
  hObject = 0;
  DevPlat::Shared::SimpleLock::SimpleLock(
    (DevPlat::Shared::SimpleLock *)&lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 16));
  QueryUserToken(0, &hObject);
  UserSid = OnDemandBrokerClient::GetUserSid(v11, hObject, &Block);
  if ( UserSid >= 0 )
  {
    if ( !a4 )
    {
LABEL_3:
      UserSid = -2147024809;
      goto LABEL_24;
    }
    if ( Source )
    {
      if ( !SourceSize )
        goto LABEL_3;
    }
    else if ( SourceSize )
    {
      goto LABEL_3;
    }
    UserSid = OnDemandBrokerClient::FindSessionById((OnDemandBrokerClient *)((char *)this - 8), a2, &v26);
    if ( UserSid >= 0 )
    {
      v14 = v26;
      UserSid = OnDemandBrokerClient::GetXamlLightupInfo(
                  v13,
                  hObject,
                  *(_DWORD *)(*((_QWORD *)v26 + 3) + 76LL),
                  a4,
                  v32);
      if ( UserSid >= 0 )
      {
        v15 = operator new[](SourceSize + 531, (const struct std::nothrow_t *)&std::nothrow);
        v16 = v15;
        if ( v15 )
        {
          if ( Source )
          {
            *(_DWORD *)v15 = a3;
            if ( wcscpy_s((wchar_t *)v15 + 2, 0x104u, a4)
              || (v16[131] = SourceSize, memcpy_s(v16 + 132, SourceSize, Source, SourceSize)) )
            {
              UserSid = -2147418113;
            }
            else
            {
              UserSid = (*(__int64 (__fastcall **)(_QWORD, void *, _QWORD, _QWORD, wchar_t *, _BYTE *, _BYTE *, _DWORD *, unsigned int, struct _OdbLaunchInfo *, _QWORD, __int128 *))(**((_QWORD **)v27 + 9) + 64LL))(
                          *((_QWORD *)v27 + 9),
                          Block,
                          0,
                          v24,
                          v32,
                          v33,
                          v34,
                          v16,
                          SourceSize + 531,
                          v28,
                          0,
                          &v31);
              if ( UserSid >= 0 )
              {
                v17 = *((_QWORD *)v14 + 3);
                v18 = v31;
                v19 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
                if ( v19 )
                {
                  v20 = v17 + 120;
                  v19[8] = a3;
                  *((_OWORD *)v19 + 1) = v18;
                  v19[9] = 0;
                  v21 = *(_QWORD **)(v17 + 128);
                  if ( *v21 != v17 + 120 )
                    __fastfail(3u);
                  *(_QWORD *)v19 = v20;
                  UserSid = 0;
                  *((_QWORD *)v19 + 1) = v21;
                  *v21 = v19;
                  *(_QWORD *)(v20 + 8) = v19;
                }
                else
                {
                  UserSid = -2147024882;
                }
              }
            }
          }
          else
          {
            UserSid = -2147024809;
          }
          operator delete[](v16);
        }
        else
        {
          UserSid = -2147024882;
        }
      }
    }
  }
LABEL_24:
  CloseHandle(hObject);
  operator delete[](Block);
  if ( !v30 )
    LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x180005b70  mov     rax, rsp
0x180005b73  mov     [rax+18h], rbx
0x180005b77  push    rbp
0x180005b78  push    rsi
0x180005b79  push    rdi
0x180005b7a  push    r12
0x180005b7c  push    r13
0x180005b7e  push    r14
0x180005b80  push    r15
0x180005b82  lea     rbp, [rax-338h]
0x180005b89  sub     rsp, 400h
0x180005b90  movaps  xmmword ptr [rax-48h], xmm6
0x180005b94  mov     rax, cs:__security_cookie
0x180005b9b  xor     rax, rsp
0x180005b9e  mov     [rbp+330h+var_50], rax
0x180005ba5  mov     rax, [rbp+330h+arg_30]
0x180005bac  mov     r12d, r8d
0x180005baf  mov     r14, [rbp+330h+Source]
0x180005bb6  mov     r13d, edx
0x180005bb9  mov     [rsp+430h+var_3B8], edx
0x180005bbd  mov     rsi, rcx
0x180005bc0  mov     [rbp+330h+var_3A0], rcx
0x180005bc4  xorps   xmm0, xmm0
0x180005bc7  xor     edx, edx; Val
0x180005bc9  mov     [rbp+330h+var_398], rax
0x180005bcd  mov     r8d, 318h; Size
0x180005bd3  mov     [rbp+330h+var_3A8], 0
0x180005bdb  lea     rcx, [rbp+330h+var_370]; void *
0x180005bdf  mov     r15, r9
0x180005be2  movups  [rbp+330h+var_380], xmm0
0x180005be6  call    memset_0
0x180005beb  lea     rdx, [rsi+10h]; struct _RTL_CRITICAL_SECTION *
0x180005bef  mov     [rbp+330h+Block], 0
0x180005bf7  lea     rcx, [rbp+330h+lpCriticalSection]; this
0x180005bfb  mov     [rsp+430h+hObject], 0
0x180005c04  call    ??0SimpleLock@Shared@DevPlat@@QEAA@PEAU_RTL_CRITICAL_SECTION@@_N@Z; DevPlat::Shared::SimpleLock::SimpleLock(_RTL_CRITICAL_SECTION *,bool)
0x180005c09  lea     rdx, [rsp+430h+hObject]
0x180005c0e  xor     ecx, ecx
0x180005c10  call    cs:__imp_QueryUserToken
0x180005c16  mov     rdx, [rsp+430h+hObject]; void *
0x180005c1b  lea     r8, [rbp+330h+Block]; void **
0x180005c1f  call    ?GetUserSid@OnDemandBrokerClient@@AEAAJPEAXPEAPEAX@Z; OnDemandBrokerClient::GetUserSid(void *,void * *)
0x180005c24  mov     ebx, eax
0x180005c26  test    eax, eax
0x180005c28  js      loc_180005DDB
0x180005c2e  test    r15, r15
0x180005c31  jnz     short loc_180005C3D
0x180005c33  mov     ebx, 80070057h
0x180005c38  jmp     loc_180005DDB
0x180005c3d  mov     edi, dword ptr [rbp+330h+SourceSize]
0x180005c43  test    r14, r14
0x180005c46  jz      short loc_180005C4E
0x180005c48  test    edi, edi
0x180005c4a  jnz     short loc_180005C52
0x180005c4c  jmp     short loc_180005C33
0x180005c4e  test    edi, edi
0x180005c50  jnz     short loc_180005C33
0x180005c52  lea     rcx, [rsi-8]; this
0x180005c56  mov     edx, r13d; unsigned int
0x180005c59  lea     r8, [rbp+330h+var_3A8]; struct _ODB_SESSION_ENTRY **
0x180005c5d  call    ?FindSessionById@OnDemandBrokerClient@@AEAAJKPEAPEAU_ODB_SESSION_ENTRY@@@Z; OnDemandBrokerClient::FindSessionById(ulong,_ODB_SESSION_ENTRY * *)
0x180005c62  mov     ebx, eax
0x180005c64  test    eax, eax
0x180005c66  js      loc_180005DDB
0x180005c6c  mov     r13, [rbp+330h+var_3A8]
0x180005c70  lea     rax, [rbp+330h+var_370]
0x180005c74  mov     rdx, [rsp+430h+hObject]; void *
0x180005c79  mov     r9, r15; unsigned __int16 *
0x180005c7c  mov     [rsp+430h+var_410], rax; struct _XAMLLIGHTUP_INFO *
0x180005c81  mov     r8, [r13+18h]
0x180005c85  mov     r8d, [r8+4Ch]; unsigned int
0x180005c89  call    ?GetXamlLightupInfo@OnDemandBrokerClient@@AEAAJPEAXKPEBGPEAU_XAMLLIGHTUP_INFO@@@Z; OnDemandBrokerClient::GetXamlLightupInfo(void *,ulong,ushort const *,_XAMLLIGHTUP_INFO *)
0x180005c8e  mov     ebx, eax
0x180005c90  test    eax, eax
0x180005c92  js      loc_180005DDB
0x180005c98  lea     ebx, [rdi+213h]
0x180005c9e  mov     ecx, ebx; unsigned __int64
0x180005ca0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005ca7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005cac  mov     rsi, rax
0x180005caf  test    rax, rax
0x180005cb2  jnz     short loc_180005CBE
0x180005cb4  mov     ebx, 8007000Eh
0x180005cb9  jmp     loc_180005DDB
0x180005cbe  test    r14, r14
0x180005cc1  jnz     short loc_180005CCD
0x180005cc3  mov     ebx, 80070057h
0x180005cc8  jmp     loc_180005DD3
0x180005ccd  lea     rcx, [rax+4]; Destination
0x180005cd1  mov     [rax], r12d
0x180005cd4  mov     r8, r15; Source
0x180005cd7  mov     edx, 104h; SizeInWords
0x180005cdc  call    cs:__imp_wcscpy_s
0x180005ce2  test    eax, eax
0x180005ce4  jnz     short loc_180005D05
0x180005ce6  mov     edx, edi; DestinationSize
0x180005ce8  lea     rcx, [rsi+210h]; Destination
0x180005cef  mov     r9d, edi; SourceSize
0x180005cf2  mov     r8, r14; Source
0x180005cf5  mov     [rsi+20Ch], edi
0x180005cfb  call    cs:__imp_memcpy_s
0x180005d01  test    eax, eax
0x180005d03  jz      short loc_180005D0F
0x180005d05  mov     ebx, 8000FFFFh
0x180005d0a  jmp     loc_180005DD3
0x180005d0f  mov     rcx, [rbp+330h+var_3A0]
0x180005d13  lea     rdx, [rbp+330h+var_380]
0x180005d17  mov     r9d, [rsp+430h+var_3B8]
0x180005d1c  lea     r8, [rbp+330h+var_370]
0x180005d20  mov     [rsp+430h+var_3D8], rdx
0x180005d25  mov     rdx, [rbp+330h+var_398]
0x180005d29  mov     rcx, [rcx+48h]
0x180005d2d  mov     [rsp+430h+var_3E0], 0
0x180005d36  mov     [rsp+430h+var_3E8], rdx
0x180005d3b  lea     rdx, [rbp+330h+var_68]
0x180005d42  mov     dword ptr [rsp+430h+var_3F0], ebx
0x180005d46  mov     rax, [rcx]
0x180005d49  mov     qword ptr [rsp+430h+var_3F8], rsi
0x180005d4e  mov     [rsp+430h+var_400], rdx
0x180005d53  lea     rdx, [rbp+330h+var_270]
0x180005d5a  mov     [rsp+430h+var_408], rdx
0x180005d5f  mov     rax, [rax+40h]
0x180005d63  mov     rdx, [rbp+330h+Block]
0x180005d67  mov     [rsp+430h+var_410], r8
0x180005d6c  xor     r8d, r8d
0x180005d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d74  mov     ebx, eax
0x180005d76  test    eax, eax
0x180005d78  js      short loc_180005DD3
0x180005d7a  mov     rbx, [r13+18h]
0x180005d7e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005d85  movaps  xmm6, [rbp+330h+var_380]
0x180005d89  mov     ecx, 28h ; '('; unsigned __int64
0x180005d8e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005d93  test    rax, rax
0x180005d96  jnz     short loc_180005D9F
0x180005d98  mov     ebx, 8007000Eh
0x180005d9d  jmp     short loc_180005DD3
0x180005d9f  lea     rcx, [rbx+78h]
0x180005da3  mov     [rax+20h], r12d
0x180005da7  movdqu  xmmword ptr [rax+10h], xmm6
0x180005dac  mov     dword ptr [rax+24h], 0
0x180005db3  mov     rdx, [rcx+8]
0x180005db7  cmp     [rdx], rcx
0x180005dba  jz      short loc_180005DC3
0x180005dbc  mov     ecx, 3
0x180005dc1  int     29h; Win8: RtlFailFast(ecx)
0x180005dc3  mov     [rax], rcx
0x180005dc6  xor     ebx, ebx
0x180005dc8  mov     [rax+8], rdx
0x180005dcc  mov     [rdx], rax
0x180005dcf  mov     [rcx+8], rax
0x180005dd3  mov     rcx, rsi; Block
0x180005dd6  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005ddb  mov     rcx, [rsp+430h+hObject]; hObject
0x180005de0  call    cs:__imp_CloseHandle
0x180005de6  mov     rcx, [rbp+330h+Block]; Block
0x180005dea  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005def  cmp     [rbp+330h+var_388], 0
0x180005df3  jnz     short loc_180005DFF
0x180005df5  mov     rcx, [rbp+330h+lpCriticalSection]; lpCriticalSection
0x180005df9  call    cs:__imp_LeaveCriticalSection
0x180005dff  mov     eax, ebx
0x180005e01  mov     rcx, [rbp+330h+var_50]
0x180005e08  xor     rcx, rsp; StackCookie
0x180005e0b  call    __security_check_cookie
0x180005e10  lea     r11, [rsp+430h+var_30]
0x180005e18  mov     rbx, [r11+50h]
0x180005e1c  movaps  xmm6, xmmword ptr [r11-10h]
0x180005e21  mov     rsp, r11
0x180005e24  pop     r15
0x180005e26  pop     r14
0x180005e28  pop     r13
0x180005e2a  pop     r12
0x180005e2c  pop     rdi
0x180005e2d  pop     rsi
0x180005e2e  pop     rbp
0x180005e2f  retn
```
