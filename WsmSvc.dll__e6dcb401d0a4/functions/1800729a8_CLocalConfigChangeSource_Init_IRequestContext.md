# CLocalConfigChangeSource::Init(IRequestContext *)

- ea: `0x1800729a8`
- end: `0x180072b8c`
- name: `?Init@CLocalConfigChangeSource@@AEAAHPEAVIRequestContext@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(char *Context, struct IRequestContext *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800c1bd0`
- `0x1800c1e20`

## callees

- `0x180005d10`
- `0x180071400`
- `0x1800729a8`
- `0x1801123a8`
- `0x18011a6d4`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072aa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072adf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072aa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072adf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180072a00`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180072a00`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180072a14`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180072a14`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800729d6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800729d6`

## string_xrefs

- `0x180072b64`: `onecore\admin\wmi\wmx\config\clocalconfigchangesource.cpp`
- `0x180072aaa`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLocalConfigChangeSource::Init(char *Context, struct IRequestContext *a2)
{
  HANDLE EventW; // rbx
  DWORD LastError; // eax
  void (__fastcall *v7)(struct IRequestContext *, __int64, const wchar_t *, _QWORD); // rbx
  DWORD v8; // eax
  const wchar_t *v9; // r8
  DWORD v10; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids, Context);
  EventW = CreateEventW(0, 0, 0, 0);
  AutoCleanup<AutoHandle,void *>::ReleasePtr(Context + 40);
  *((_QWORD *)Context + 5) = EventW;
  if ( !EventW )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids, LastError);
    }
    v7 = *(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 88LL);
    v8 = GetLastError();
    v9 = L"CreateEvent";
    goto LABEL_14;
  }
  if ( !QueueUserWorkItem(CLocalConfigChangeSource::_RegisterForConfigChanges, Context, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      v10 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids, v10);
    }
    v7 = *(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 88LL);
    v8 = GetLastError();
    v9 = L"QueueUserWorkItem";
LABEL_14:
    v7(a2, 1077134176, v9, v8);
    return 0;
  }
  if ( WaitForSingleObject(*((HANDLE *)Context + 5), 0xFFFFFFFF) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\clocalconfigchangesource.cpp", 124, L"124", 0x54Fu, a2);
  }
  else
  {
    if ( *((_QWORD *)Context + 7) )
      return 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids,
        *((unsigned int *)Context + 16));
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(
      a2,
      *((unsigned int *)Context + 16));
  }
  return 0;
}

```

## disassembly

```asm
0x1800729a8  push    rbx
0x1800729aa  push    rbp
0x1800729ab  push    rsi
0x1800729ac  push    rdi
0x1800729ad  push    r14
0x1800729af  sub     rsp, 30h
0x1800729b3  mov     rsi, rdx
0x1800729b6  mov     rdi, rcx
0x1800729b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800729c0  lea     rbp, WPP_GLOBAL_Control
0x1800729c7  cmp     rcx, rbp
0x1800729ca  jnz     short loc_180072A3D
0x1800729cc  xor     r9d, r9d; lpName
0x1800729cf  xor     r8d, r8d; bInitialState
0x1800729d2  xor     edx, edx; bManualReset
0x1800729d4  xor     ecx, ecx; lpEventAttributes
0x1800729d6  call    cs:__imp_CreateEventW
0x1800729dc  lea     r14, [rdi+28h]
0x1800729e0  mov     rbx, rax
0x1800729e3  mov     rcx, r14
0x1800729e6  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1800729eb  mov     [r14], rbx
0x1800729ee  test    rbx, rbx
0x1800729f1  jz      short loc_180072A63
0x1800729f3  xor     r8d, r8d; Flags
0x1800729f6  lea     rcx, ?_RegisterForConfigChanges@CLocalConfigChangeSource@@CAHPEAX@Z; Function
0x1800729fd  mov     rdx, rdi; Context
0x180072a00  call    cs:__imp_QueueUserWorkItem
0x180072a06  test    eax, eax
0x180072a08  jz      loc_180072B33
0x180072a0e  mov     rcx, [r14]; hHandle
0x180072a11  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180072a14  call    cs:__imp_WaitForSingleObject
0x180072a1a  test    eax, eax
0x180072a1c  jnz     loc_180072B4D
0x180072a22  cmp     qword ptr [rdi+38h], 0
0x180072a27  jz      loc_180072B72
0x180072a2d  mov     eax, 1
0x180072a32  add     rsp, 30h
0x180072a36  pop     r14
0x180072a38  pop     rdi
0x180072a39  pop     rsi
0x180072a3a  pop     rbp
0x180072a3b  pop     rbx
0x180072a3c  retn
0x180072a3d  test    dword ptr [rcx+1Ch], 200000h
0x180072a44  jz      short loc_1800729CC
0x180072a46  mov     rcx, [rcx+10h]
0x180072a4a  lea     r8, WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids
0x180072a51  mov     edx, 0Dh
0x180072a56  mov     r9, rdi
0x180072a59  call    WPP_SF_q
0x180072a5e  jmp     loc_1800729CC
0x180072a63  mov     rax, cs:WPP_GLOBAL_Control
0x180072a6a  cmp     rax, rbp
0x180072a6d  jz      short loc_180072A9D
0x180072a6f  test    dword ptr [rax+1Ch], 400000h
0x180072a76  jz      short loc_180072A9D
0x180072a78  call    cs:__imp_GetLastError
0x180072a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180072a85  lea     r8, WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids
0x180072a8c  mov     edx, 0Eh
0x180072a91  mov     r9d, eax
0x180072a94  mov     rcx, [rcx+10h]
0x180072a98  call    WPP_SF_d
0x180072a9d  mov     rax, [rsi]
0x180072aa0  mov     rbx, [rax+58h]
0x180072aa4  call    cs:__imp_GetLastError
0x180072aaa  lea     r8, aCreateevent; "CreateEvent"
0x180072ab1  jmp     short loc_180072AEC
0x180072ab3  call    cs:__imp_GetLastError
0x180072ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180072ac0  lea     r8, WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids
0x180072ac7  mov     edx, 0Fh
0x180072acc  mov     r9d, eax
0x180072acf  mov     rcx, [rcx+10h]
0x180072ad3  call    WPP_SF_d
0x180072ad8  mov     rax, [rsi]
0x180072adb  mov     rbx, [rax+58h]
0x180072adf  call    cs:__imp_GetLastError
0x180072ae5  lea     r8, aQueueuserworki; "QueueUserWorkItem"
0x180072aec  mov     r9d, eax
0x180072aef  mov     edx, 4033C360h
0x180072af4  mov     rax, rbx
0x180072af7  mov     rcx, rsi
0x180072afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072aff  jmp     short loc_180072B2C
0x180072b01  mov     r9d, [rdi+40h]
0x180072b05  lea     r8, WPP_370815dc9a9336867a18c46a9d5d6ff6_Traceguids
0x180072b0c  mov     rcx, [rcx+10h]
0x180072b10  mov     edx, 10h
0x180072b15  call    WPP_SF_d
0x180072b1a  mov     rax, [rsi]
0x180072b1d  mov     rcx, rsi
0x180072b20  mov     edx, [rdi+40h]
0x180072b23  mov     rax, [rax+48h]
0x180072b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b2c  xor     eax, eax
0x180072b2e  jmp     loc_180072A32
0x180072b33  mov     rax, cs:WPP_GLOBAL_Control
0x180072b3a  cmp     rax, rbp
0x180072b3d  jz      short loc_180072AD8
0x180072b3f  test    dword ptr [rax+1Ch], 400000h
0x180072b46  jz      short loc_180072AD8
0x180072b48  jmp     loc_180072AB3
0x180072b4d  mov     r9d, 54Fh; unsigned int
0x180072b53  mov     [rsp+58h+var_38], rsi; struct IRequestContext *
0x180072b58  lea     r8, a124; "124"
0x180072b5f  mov     edx, 7Ch ; '|'; unsigned int
0x180072b64  lea     rcx, aOnecoreAdminWm_170; "onecore\\admin\\wmi\\wmx\\config\\cloca"...
0x180072b6b  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180072b70  jmp     short loc_180072B2C
0x180072b72  mov     rcx, cs:WPP_GLOBAL_Control
0x180072b79  cmp     rcx, rbp
0x180072b7c  jz      short loc_180072B1A
0x180072b7e  test    dword ptr [rcx+1Ch], 400000h
0x180072b85  jz      short loc_180072B1A
0x180072b87  jmp     loc_180072B01
```
