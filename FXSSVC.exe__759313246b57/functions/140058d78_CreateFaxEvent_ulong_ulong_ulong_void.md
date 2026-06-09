# CreateFaxEvent(ulong,ulong,ulong,void *)

- ea: `0x140058d78`
- end: `0x140059005`
- name: `?CreateFaxEvent@@YAHKKKPEAX@Z`
- size: `653`
- prototype: `__int64 __fastcall(DWORD, DWORD, DWORD, void *)`
- caller_count: `10`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140016690`
- `0x14001dbc0`
- `0x1400311d0`
- `0x140031d80`
- `0x14003354c`
- `0x140036268`
- `0x14003cd94`
- `0x14003d470`
- `0x140049678`
- `0x14004fbd0`

## callees

- `0x1400023ec`
- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x1400579f8`
- `0x140058d78`
- `0x14005b798`
- `0x140086ec0`
- `0x14008b010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140058fc2`
- `KERNEL32!GetLastError` at `0x140058fc2`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140058e89`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140058e89`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140058f96`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140058f96`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateFaxEvent(DWORD a1, DWORD a2, DWORD a3, void *a4)
{
  CMapDeviceId *v8; // rcx
  __int64 v9; // rdx
  CMapDeviceId *v11; // rbx
  int v12; // edx
  int v13; // r8d
  __int64 v14; // rax
  const wchar_t *v15; // r9
  CFaxEventLegacy *v16; // rax
  struct _OVERLAPPED *v17; // rbx
  DWORD LastError; // eax
  __int64 v19; // rax
  struct _OVERLAPPED *v20; // [rsp+40h] [rbp-268h]
  exception *v21; // [rsp+50h] [rbp-258h] BYREF
  struct _FAX_EVENTW SystemTimeAsFileTime; // [rsp+58h] [rbp-250h] BYREF
  _BYTE v23[512]; // [rsp+70h] [rbp-238h] BYREF

  memset(&SystemTimeAsFileTime, 0, sizeof(SystemTimeAsFileTime));
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( g_bServiceIsDown != 1 )
  {
    if ( g_hDispatchEventsCompPort )
    {
      SystemTimeAsFileTime.SizeOfStruct = 24;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime.TimeStamp);
      SystemTimeAsFileTime.EventId = a2;
      SystemTimeAsFileTime.DeviceId = a1;
      SystemTimeAsFileTime.JobId = a3;
      v11 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        memset_0(v23, 0, sizeof(v23));
        if ( v11 != (CMapDeviceId *)&WPP_GLOBAL_Control )
        {
          v14 = a2 - 1;
          if ( (unsigned int)v14 > 0x1A )
            v15 = L"*** INVALID EVENT CODE ***";
          else
            v15 = (const wchar_t *)(&lpszEventCodes)[v14];
          WPP_SF_SDDS(*((_QWORD *)v11 + 2), v12, v13, (int)v15, a2, a1, (__int64)v23);
        }
      }
      v16 = (CFaxEventLegacy *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        if ( v16 )
          v17 = (struct _OVERLAPPED *)CFaxEventLegacy::CFaxEventLegacy(v16, &SystemTimeAsFileTime, a4);
        else
          v17 = 0;
        v20 = v17;
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', &v21) )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = (*(__int64 (__fastcall **)(exception *))(*(_QWORD *)v21 + 8LL))(v21);
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v19);
          }
          v17 = v20;
          __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_140058F3E);
        }
      }
      if ( !v17 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 0;
        }
        v9 = 136;
        goto LABEL_33;
      }
      if ( !PostQueuedCompletionStatus(g_hDispatchEventsCompPort, 8u, 1u, v17) )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            137,
            &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids,
            LastError);
        }
        (*(void (__fastcall **)(struct _OVERLAPPED *, __int64))v17->Internal)(v17, 1);
        return 0;
      }
    }
    else if ( v8 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 && *((_BYTE *)v8 + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)v8 + 2), 132, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids);
    }
    return 1;
  }
  if ( v8 == (CMapDeviceId *)&WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 4) == 0 || *((_BYTE *)v8 + 25) < 3u )
    return 0;
  v9 = 131;
LABEL_33:
  WPP_SF_(*((_QWORD *)v8 + 2), v9, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140058d78  push    rbx
0x140058d7a  push    rsi
0x140058d7b  push    rdi
0x140058d7c  push    r14
0x140058d7e  push    r15
0x140058d80  sub     rsp, 280h
0x140058d87  mov     rax, cs:__security_cookie
0x140058d8e  xor     rax, rsp
0x140058d91  mov     [rsp+2A8h+var_38], rax
0x140058d99  mov     r15, r9
0x140058d9c  mov     ebx, r8d
0x140058d9f  mov     esi, edx
0x140058da1  mov     r14d, ecx
0x140058da4  xorps   xmm0, xmm0
0x140058da7  xor     eax, eax
0x140058da9  movups  xmmword ptr [rsp+2A8h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x140058dae  mov     [rsp+2A8h+var_240], rax
0x140058db3  lea     rdi, WPP_GLOBAL_Control
0x140058dba  mov     rcx, cs:WPP_GLOBAL_Control
0x140058dc1  cmp     rcx, rdi
0x140058dc4  jz      short loc_140058DEE
0x140058dc6  test    byte ptr [rcx+1Ch], 4
0x140058dca  jz      short loc_140058DEE
0x140058dcc  cmp     byte ptr [rcx+19h], 5
0x140058dd0  jb      short loc_140058DEE
0x140058dd2  mov     edx, 82h
0x140058dd7  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140058dde  mov     rcx, [rcx+10h]
0x140058de2  call    WPP_SF_
0x140058de7  mov     rcx, cs:WPP_GLOBAL_Control
0x140058dee  cmp     cs:?g_bServiceIsDown@@3HA, 1; int g_bServiceIsDown
0x140058df5  jnz     short loc_140058E1E
0x140058df7  cmp     rcx, rdi
0x140058dfa  jz      loc_140058F7C
0x140058e00  test    byte ptr [rcx+1Ch], 4
0x140058e04  jz      loc_140058F7C
0x140058e0a  cmp     byte ptr [rcx+19h], 3
0x140058e0e  jb      loc_140058F7C
0x140058e14  mov     edx, 83h
0x140058e19  jmp     loc_140058F6C
0x140058e1e  cmp     cs:?g_hDispatchEventsCompPort@@3PEAXEA, 0; void * g_hDispatchEventsCompPort
0x140058e26  jnz     short loc_140058E73
0x140058e28  cmp     rcx, rdi
0x140058e2b  jz      short loc_140058E4E
0x140058e2d  test    byte ptr [rcx+1Ch], 4
0x140058e31  jz      short loc_140058E4E
0x140058e33  cmp     byte ptr [rcx+19h], 3
0x140058e37  jb      short loc_140058E4E
0x140058e39  mov     edx, 84h
0x140058e3e  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140058e45  mov     rcx, [rcx+10h]
0x140058e49  call    WPP_SF_
0x140058e4e  mov     eax, 1
0x140058e53  mov     rcx, [rsp+2A8h+var_38]
0x140058e5b  xor     rcx, rsp; StackCookie
0x140058e5e  call    __security_check_cookie
0x140058e63  add     rsp, 280h
0x140058e6a  pop     r15
0x140058e6c  pop     r14
0x140058e6e  pop     rdi
0x140058e6f  pop     rsi
0x140058e70  pop     rbx
0x140058e71  retn
0x140058e73  mov     [rsp+2A8h+var_268], 0
0x140058e7c  mov     [rsp+2A8h+SystemTimeAsFileTime.dwLowDateTime], 18h
0x140058e84  lea     rcx, [rsp+2A8h+SystemTimeAsFileTime.dwHighDateTime]; lpSystemTimeAsFileTime
0x140058e89  call    cs:__imp_GetSystemTimeAsFileTime
0x140058e90  nop     dword ptr [rax+rax+00h]
0x140058e95  mov     dword ptr [rsp+2A8h+var_240], esi
0x140058e99  mov     [rsp+2A8h+SystemTimeAsFileTime.dwHighDateTime+8], r14d
0x140058e9e  mov     dword ptr [rsp+2A8h+var_240+4], ebx
0x140058ea2  mov     rbx, cs:WPP_GLOBAL_Control
0x140058ea9  test    byte ptr [rbx+1Ch], 4
0x140058ead  jz      short loc_140058F05
0x140058eaf  cmp     byte ptr [rbx+19h], 5
0x140058eb3  jb      short loc_140058F05
0x140058eb5  xor     edx, edx; Val
0x140058eb7  mov     r8d, 200h; Size
0x140058ebd  lea     rcx, [rsp+2A8h+var_238]; void *
0x140058ec2  call    memset_0
0x140058ec7  cmp     rbx, rdi
0x140058eca  jz      short loc_140058F05
0x140058ecc  lea     eax, [rsi-1]
0x140058ecf  cmp     eax, 1Ah
0x140058ed2  ja      short loc_140058EE1
0x140058ed4  lea     r9, ?lpszEventCodes@@3PAPEAGA; ushort * near * lpszEventCodes
0x140058edb  mov     r9, [r9+rax*8]
0x140058edf  jmp     short loc_140058EE8
0x140058ee1  lea     r9, aInvalidEventCo; "*** INVALID EVENT CODE ***"
0x140058ee8  lea     rax, [rsp+2A8h+var_238]
0x140058eed  mov     [rsp+2A8h+var_278], rax
0x140058ef2  mov     [rsp+2A8h+var_280], r14d
0x140058ef7  mov     [rsp+2A8h+var_288], esi
0x140058efb  mov     rcx, [rbx+10h]
0x140058eff  call    WPP_SF_SDDS
0x140058f04  nop
0x140058f05  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140058f0c  mov     ecx, 18h; unsigned __int64
0x140058f11  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140058f16  mov     [rsp+2A8h+var_260], rax
0x140058f1b  test    rax, rax
0x140058f1e  jz      short loc_140058F35
0x140058f20  mov     r8, r15; void *
0x140058f23  lea     rdx, [rsp+2A8h+SystemTimeAsFileTime]; struct _FAX_EVENTW *
0x140058f28  mov     rcx, rax; this
0x140058f2b  call    ??0CFaxEventLegacy@@QEAA@PEBU_FAX_EVENTW@@PEAX@Z; CFaxEventLegacy::CFaxEventLegacy(_FAX_EVENTW const *,void *)
0x140058f30  mov     rbx, rax
0x140058f33  jmp     short loc_140058F37
0x140058f35  xor     ebx, ebx
0x140058f37  mov     [rsp+2A8h+var_268], rbx
0x140058f3c  jmp     short loc_140058F4A
0x140058f3e  lea     rdi, WPP_GLOBAL_Control
0x140058f45  mov     rbx, [rsp+2A8h+var_268]
0x140058f4a  test    rbx, rbx
0x140058f4d  jnz     short loc_140058F83
0x140058f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140058f56  cmp     rcx, rdi
0x140058f59  jz      short loc_140058F7C
0x140058f5b  test    byte ptr [rcx+1Ch], 4
0x140058f5f  jz      short loc_140058F7C
0x140058f61  cmp     byte ptr [rcx+19h], 2
0x140058f65  jb      short loc_140058F7C
0x140058f67  mov     edx, 88h
0x140058f6c  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140058f73  mov     rcx, [rcx+10h]
0x140058f77  call    WPP_SF_
0x140058f7c  xor     eax, eax
0x140058f7e  jmp     loc_140058E53
0x140058f83  mov     r9, rbx; lpOverlapped
0x140058f86  mov     edx, 8; dwNumberOfBytesTransferred
0x140058f8b  lea     r8d, [rdx-7]; dwCompletionKey
0x140058f8f  mov     rcx, cs:?g_hDispatchEventsCompPort@@3PEAXEA; CompletionPort
0x140058f96  call    cs:__imp_PostQueuedCompletionStatus
0x140058f9d  nop     dword ptr [rax+rax+00h]
0x140058fa2  test    eax, eax
0x140058fa4  jnz     loc_140058E4E
0x140058faa  mov     rax, cs:WPP_GLOBAL_Control
0x140058fb1  cmp     rax, rdi
0x140058fb4  jz      short loc_140058FED
0x140058fb6  test    byte ptr [rax+1Ch], 4
0x140058fba  jz      short loc_140058FED
0x140058fbc  cmp     byte ptr [rax+19h], 2
0x140058fc0  jb      short loc_140058FED
0x140058fc2  call    cs:__imp_GetLastError
0x140058fc9  nop     dword ptr [rax+rax+00h]
0x140058fce  mov     edx, 89h
0x140058fd3  mov     r9d, eax
0x140058fd6  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140058fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x140058fe4  mov     rcx, [rcx+10h]
0x140058fe8  call    WPP_SF_d
0x140058fed  mov     rax, [rbx]
0x140058ff0  mov     edx, 1
0x140058ff5  mov     rcx, rbx
0x140058ff8  mov     rax, [rax]
0x140058ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059000  jmp     loc_140058F7C
```
