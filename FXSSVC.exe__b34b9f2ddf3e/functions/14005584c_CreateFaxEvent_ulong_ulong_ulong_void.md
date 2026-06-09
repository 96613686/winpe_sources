# CreateFaxEvent(ulong,ulong,ulong,void *)

- ea: `0x14005584c`
- end: `0x140055ac3`
- name: `?CreateFaxEvent@@YAHKKKPEAX@Z`
- size: `631`
- prototype: `__int64 __fastcall(DWORD, DWORD, DWORD, void *)`
- caller_count: `10`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140015d90`
- `0x14001cf70`
- `0x14002f9f0`
- `0x140030520`
- `0x140031b6c`
- `0x14003465c`
- `0x14003ac78`
- `0x14003b2fc`
- `0x140046a7c`
- `0x14004caf0`

## callees

- `0x1400023cc`
- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x14005451c`
- `0x14005584c`
- `0x1400581ec`
- `0x1400818b0`
- `0x140085010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140055a89`
- `KERNEL32!GetLastError` at `0x140055a89`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14005595c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14005595c`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140055a63`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140055a63`

## pseudocode

```c
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
          __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_140055A0B);
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
0x14005584c  push    rbx
0x14005584e  push    rsi
0x14005584f  push    rdi
0x140055850  push    r14
0x140055852  push    r15
0x140055854  sub     rsp, 280h
0x14005585b  mov     rax, cs:__security_cookie
0x140055862  xor     rax, rsp
0x140055865  mov     [rsp+2A8h+var_38], rax
0x14005586d  mov     r15, r9
0x140055870  mov     ebx, r8d
0x140055873  mov     esi, edx
0x140055875  mov     r14d, ecx
0x140055878  xorps   xmm0, xmm0
0x14005587b  xor     eax, eax
0x14005587d  movups  xmmword ptr [rsp+2A8h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x140055882  mov     [rsp+2A8h+var_240], rax
0x140055887  lea     rdi, WPP_GLOBAL_Control
0x14005588e  mov     rcx, cs:WPP_GLOBAL_Control
0x140055895  cmp     rcx, rdi
0x140055898  jz      short loc_1400558C2
0x14005589a  test    byte ptr [rcx+1Ch], 4
0x14005589e  jz      short loc_1400558C2
0x1400558a0  cmp     byte ptr [rcx+19h], 5
0x1400558a4  jb      short loc_1400558C2
0x1400558a6  mov     edx, 82h
0x1400558ab  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x1400558b2  mov     rcx, [rcx+10h]
0x1400558b6  call    WPP_SF_
0x1400558bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400558c2  cmp     cs:?g_bServiceIsDown@@3HA, 1; int g_bServiceIsDown
0x1400558c9  jnz     short loc_1400558F2
0x1400558cb  cmp     rcx, rdi
0x1400558ce  jz      loc_140055A49
0x1400558d4  test    byte ptr [rcx+1Ch], 4
0x1400558d8  jz      loc_140055A49
0x1400558de  cmp     byte ptr [rcx+19h], 3
0x1400558e2  jb      loc_140055A49
0x1400558e8  mov     edx, 83h
0x1400558ed  jmp     loc_140055A39
0x1400558f2  cmp     cs:?g_hDispatchEventsCompPort@@3PEAXEA, 0; void * g_hDispatchEventsCompPort
0x1400558fa  jnz     short loc_140055946
0x1400558fc  cmp     rcx, rdi
0x1400558ff  jz      short loc_140055922
0x140055901  test    byte ptr [rcx+1Ch], 4
0x140055905  jz      short loc_140055922
0x140055907  cmp     byte ptr [rcx+19h], 3
0x14005590b  jb      short loc_140055922
0x14005590d  mov     edx, 84h
0x140055912  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140055919  mov     rcx, [rcx+10h]
0x14005591d  call    WPP_SF_
0x140055922  mov     eax, 1
0x140055927  mov     rcx, [rsp+2A8h+var_38]
0x14005592f  xor     rcx, rsp; StackCookie
0x140055932  call    __security_check_cookie
0x140055937  add     rsp, 280h
0x14005593e  pop     r15
0x140055940  pop     r14
0x140055942  pop     rdi
0x140055943  pop     rsi
0x140055944  pop     rbx
0x140055945  retn
0x140055946  mov     [rsp+2A8h+var_268], 0
0x14005594f  mov     [rsp+2A8h+SystemTimeAsFileTime.dwLowDateTime], 18h
0x140055957  lea     rcx, [rsp+2A8h+SystemTimeAsFileTime.dwHighDateTime]; lpSystemTimeAsFileTime
0x14005595c  call    cs:__imp_GetSystemTimeAsFileTime
0x140055962  mov     dword ptr [rsp+2A8h+var_240], esi
0x140055966  mov     [rsp+2A8h+SystemTimeAsFileTime.dwHighDateTime+8], r14d
0x14005596b  mov     dword ptr [rsp+2A8h+var_240+4], ebx
0x14005596f  mov     rbx, cs:WPP_GLOBAL_Control
0x140055976  test    byte ptr [rbx+1Ch], 4
0x14005597a  jz      short loc_1400559D2
0x14005597c  cmp     byte ptr [rbx+19h], 5
0x140055980  jb      short loc_1400559D2
0x140055982  xor     edx, edx; Val
0x140055984  mov     r8d, 200h; Size
0x14005598a  lea     rcx, [rsp+2A8h+var_238]; void *
0x14005598f  call    memset_0
0x140055994  cmp     rbx, rdi
0x140055997  jz      short loc_1400559D2
0x140055999  lea     eax, [rsi-1]
0x14005599c  cmp     eax, 1Ah
0x14005599f  ja      short loc_1400559AE
0x1400559a1  lea     r9, ?lpszEventCodes@@3PAPEAGA; ushort * near * lpszEventCodes
0x1400559a8  mov     r9, [r9+rax*8]
0x1400559ac  jmp     short loc_1400559B5
0x1400559ae  lea     r9, aInvalidEventCo; "*** INVALID EVENT CODE ***"
0x1400559b5  lea     rax, [rsp+2A8h+var_238]
0x1400559ba  mov     [rsp+2A8h+var_278], rax
0x1400559bf  mov     [rsp+2A8h+var_280], r14d
0x1400559c4  mov     [rsp+2A8h+var_288], esi
0x1400559c8  mov     rcx, [rbx+10h]
0x1400559cc  call    WPP_SF_SDDS
0x1400559d1  nop
0x1400559d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400559d9  mov     ecx, 18h; unsigned __int64
0x1400559de  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400559e3  mov     [rsp+2A8h+var_260], rax
0x1400559e8  test    rax, rax
0x1400559eb  jz      short loc_140055A02
0x1400559ed  mov     r8, r15; void *
0x1400559f0  lea     rdx, [rsp+2A8h+SystemTimeAsFileTime]; struct _FAX_EVENTW *
0x1400559f5  mov     rcx, rax; this
0x1400559f8  call    ??0CFaxEventLegacy@@QEAA@PEBU_FAX_EVENTW@@PEAX@Z; CFaxEventLegacy::CFaxEventLegacy(_FAX_EVENTW const *,void *)
0x1400559fd  mov     rbx, rax
0x140055a00  jmp     short loc_140055A04
0x140055a02  xor     ebx, ebx
0x140055a04  mov     [rsp+2A8h+var_268], rbx
0x140055a09  jmp     short loc_140055A17
0x140055a0b  lea     rdi, WPP_GLOBAL_Control
0x140055a12  mov     rbx, [rsp+2A8h+var_268]
0x140055a17  test    rbx, rbx
0x140055a1a  jnz     short loc_140055A50
0x140055a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140055a23  cmp     rcx, rdi
0x140055a26  jz      short loc_140055A49
0x140055a28  test    byte ptr [rcx+1Ch], 4
0x140055a2c  jz      short loc_140055A49
0x140055a2e  cmp     byte ptr [rcx+19h], 2
0x140055a32  jb      short loc_140055A49
0x140055a34  mov     edx, 88h
0x140055a39  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140055a40  mov     rcx, [rcx+10h]
0x140055a44  call    WPP_SF_
0x140055a49  xor     eax, eax
0x140055a4b  jmp     loc_140055927
0x140055a50  mov     r9, rbx; lpOverlapped
0x140055a53  mov     edx, 8; dwNumberOfBytesTransferred
0x140055a58  lea     r8d, [rdx-7]; dwCompletionKey
0x140055a5c  mov     rcx, cs:?g_hDispatchEventsCompPort@@3PEAXEA; CompletionPort
0x140055a63  call    cs:__imp_PostQueuedCompletionStatus
0x140055a69  test    eax, eax
0x140055a6b  jnz     loc_140055922
0x140055a71  mov     rax, cs:WPP_GLOBAL_Control
0x140055a78  cmp     rax, rdi
0x140055a7b  jz      short loc_140055AAE
0x140055a7d  test    byte ptr [rax+1Ch], 4
0x140055a81  jz      short loc_140055AAE
0x140055a83  cmp     byte ptr [rax+19h], 2
0x140055a87  jb      short loc_140055AAE
0x140055a89  call    cs:__imp_GetLastError
0x140055a8f  mov     edx, 89h
0x140055a94  mov     r9d, eax
0x140055a97  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140055a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140055aa5  mov     rcx, [rcx+10h]
0x140055aa9  call    WPP_SF_d
0x140055aae  mov     rax, [rbx]
0x140055ab1  mov     edx, 1
0x140055ab6  mov     rcx, rbx
0x140055ab9  mov     rax, [rax]
0x140055abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055ac1  jmp     short loc_140055A49
```
