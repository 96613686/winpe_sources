# CListenerOperation::ReleaseWhenFinishedActivityOnChannel(void)

- ea: `0x1800c3da8`
- end: `0x1800c40a8`
- name: `?ReleaseWhenFinishedActivityOnChannel@CListenerOperation@@IEAAXXZ`
- size: `768`
- prototype: `void __fastcall(CListenerOperation *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18002c610`

## callees

- `0x180005d10`
- `0x180068b24`
- `0x1800831c0`
- `0x1800a38d0`
- `0x1800c3da8`
- `0x18011349c`
- `0x18011a6d4`
- `0x180123604`
- `0x18017203c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3e23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3fb2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3e23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3fb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c3e1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c3e1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3faa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3faa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c3f11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c3f11`

## string_xrefs

- `0x1800c3e6f`: `onecore\admin\wmi\wmx\service\listeneroperation.cpp`
- `0x1800c3ef8`: `onecore\admin\wmi\wmx\service\listeneroperation.cpp`
- `0x1800c3f93`: `onecore\admin\wmi\wmx\service\listeneroperation.cpp`
- `0x1800c3e41`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CListenerOperation::ReleaseWhenFinishedActivityOnChannel(CListenerOperation *this)
{
  DWORD *v2; // rbx
  DWORD v3; // ecx
  PVOID *v4; // rax
  int v5; // ebx
  bool IsInitialized; // al
  const wchar_t *v7; // rcx
  signed __int32 v8; // eax
  char *v9; // [rsp+40h] [rbp-38h] BYREF
  int v10; // [rsp+48h] [rbp-30h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      &WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids,
      this,
      *((_QWORD *)this + 3));
  v2 = (DWORD *)((char *)this + 168);
  v9 = (char *)this + 168;
  v10 = 0;
  v3 = *((_DWORD *)this + 42);
  if ( v3 )
  {
    SetLastError(v3);
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
      59,
      L"59",
      0x54Fu,
      0);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  }
  if ( *((_BYTE *)this + 225) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\listeneroperation.cpp", 1848, L"1848", 0x54Fu, 0);
  *((_BYTE *)this + 225) = 1;
  while ( *((_WORD *)this + 113) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qLd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        &WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids,
        this,
        *((unsigned __int8 *)this + 226),
        *((unsigned __int8 *)this + 227));
    if ( CWSManCriticalSectionWithConditionVar::WaitForConditionVar(
           (CListenerOperation *)((char *)this + 168),
           0xFFFFFFFF) )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\listeneroperation.cpp", 1859, L"1859", 0x54Fu, 0);
      break;
    }
  }
  if ( *((_BYTE *)this + 248) )
  {
    if ( *((_QWORD *)this + 30) == GetCurrentThreadId() )
    {
      *((_BYTE *)this + 249) = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids, this);
      InCritSec::~InCritSec((InCritSec *)&v9);
      return;
    }
    while ( *((_BYTE *)this + 248) )
    {
      if ( CWSManCriticalSectionWithConditionVar::WaitForConditionVar(
             (CListenerOperation *)((char *)this + 168),
             0xFFFFFFFF) )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\listeneroperation.cpp", 1882, L"1882", 0x54Fu, 0);
        break;
      }
    }
  }
  if ( *v2 )
    SetLastError(*v2);
  else
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids, this);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x1000) != 0 )
    {
      v5 = *((_DWORD *)this + 2) & 0x7FFFFFFF;
      IsInitialized = IOperation::IsInitialized(this);
      v7 = L"true";
      if ( !IsInitialized )
        v7 = L"false";
      WPP_SF_qsSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"@Channel", (__int64)v7, v5);
    }
  }
  v8 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( v8 == 0x80000000 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\operation.cpp", 174, L"174", 0x54Fu, 0);
  }
  else if ( !v8 )
  {
    (*(void (__fastcall **)(CListenerOperation *))(*(_QWORD *)this + 24LL))(this);
  }
}

```

## disassembly

```asm
0x1800c3da8  push    rbx
0x1800c3daa  push    rbp
0x1800c3dab  push    rdi
0x1800c3dac  push    r14
0x1800c3dae  push    r15
0x1800c3db0  sub     rsp, 50h
0x1800c3db4  mov     rdi, rcx
0x1800c3db7  lea     rbp, WPP_GLOBAL_Control
0x1800c3dbe  mov     r14d, 400h
0x1800c3dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3dcb  cmp     rcx, rbp
0x1800c3dce  jz      short loc_1800C3DF7
0x1800c3dd0  test    [rcx+1Ch], r14d
0x1800c3dd4  jz      short loc_1800C3DF7
0x1800c3dd6  mov     edx, 3Bh ; ';'
0x1800c3ddb  mov     rax, [rdi+18h]
0x1800c3ddf  mov     [rsp+78h+var_58], rax
0x1800c3de4  mov     r9, rdi
0x1800c3de7  lea     r8, WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids
0x1800c3dee  mov     rcx, [rcx+10h]
0x1800c3df2  call    WPP_SF_qq
0x1800c3df7  lea     rbx, [rdi+0A8h]
0x1800c3dfe  mov     [rsp+78h+var_38], rbx
0x1800c3e03  mov     [rsp+78h+var_30], 0
0x1800c3e0b  mov     ecx, [rbx]; dwErrCode
0x1800c3e0d  mov     r15d, 54Fh
0x1800c3e13  test    ecx, ecx
0x1800c3e15  jnz     short loc_1800C3E23
0x1800c3e17  lea     rcx, [rbx+8]; lpCriticalSection
0x1800c3e1b  call    cs:__imp_EnterCriticalSection
0x1800c3e21  jmp     short loc_1800C3E4E
0x1800c3e23  call    cs:__imp_SetLastError
0x1800c3e29  mov     [rsp+78h+var_58], 0; struct IRequestContext *
0x1800c3e32  mov     r9d, r15d; unsigned int
0x1800c3e35  lea     r8, a59; "59"
0x1800c3e3c  mov     edx, 3Bh ; ';'; unsigned int
0x1800c3e41  lea     rcx, aOnecoreAdminWm_164; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x1800c3e48  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800c3e4d  nop
0x1800c3e4e  cmp     byte ptr [rdi+0E1h], 0
0x1800c3e55  jz      short loc_1800C3E7B
0x1800c3e57  mov     [rsp+78h+var_58], 0; struct IRequestContext *
0x1800c3e60  mov     r9d, r15d; unsigned int
0x1800c3e63  lea     r8, a1848; "1848"
0x1800c3e6a  mov     edx, 738h; unsigned int
0x1800c3e6f  lea     rcx, aOnecoreAdminWm_69; "onecore\\admin\\wmi\\wmx\\service\\list"...
0x1800c3e76  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800c3e7b  mov     byte ptr [rdi+0E1h], 1
0x1800c3e82  movzx   edx, byte ptr [rdi+0E2h]
0x1800c3e89  movzx   r8d, byte ptr [rdi+0E3h]
0x1800c3e91  mov     al, r8b
0x1800c3e94  or      al, dl
0x1800c3e96  jz      short loc_1800C3F04
0x1800c3e98  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3e9f  cmp     rcx, rbp
0x1800c3ea2  jz      short loc_1800C3ED1
0x1800c3ea4  test    [rcx+1Ch], r14d
0x1800c3ea8  jz      short loc_1800C3ED1
0x1800c3eaa  mov     eax, r8d
0x1800c3ead  mov     r8d, edx
0x1800c3eb0  mov     edx, 3Ch ; '<'
0x1800c3eb5  mov     dword ptr [rsp+78h+var_50], eax
0x1800c3eb9  mov     dword ptr [rsp+78h+var_58], r8d
0x1800c3ebe  mov     r9, rdi
0x1800c3ec1  lea     r8, WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids
0x1800c3ec8  mov     rcx, [rcx+10h]
0x1800c3ecc  call    WPP_SF_qLd
0x1800c3ed1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800c3ed4  mov     rcx, rbx; this
0x1800c3ed7  call    ?WaitForConditionVar@CWSManCriticalSectionWithConditionVar@@QEAAKK@Z; CWSManCriticalSectionWithConditionVar::WaitForConditionVar(ulong)
0x1800c3edc  test    eax, eax
0x1800c3ede  jz      short loc_1800C3E82
0x1800c3ee0  mov     [rsp+78h+var_58], 0; struct IRequestContext *
0x1800c3ee9  mov     r9d, r15d; unsigned int
0x1800c3eec  lea     r8, a1859; "1859"
0x1800c3ef3  mov     edx, 743h; unsigned int
0x1800c3ef8  lea     rcx, aOnecoreAdminWm_69; "onecore\\admin\\wmi\\wmx\\service\\list"...
0x1800c3eff  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800c3f04  cmp     byte ptr [rdi+0F8h], 0
0x1800c3f0b  jz      loc_1800C3FA0
0x1800c3f11  call    cs:__imp_GetCurrentThreadId
0x1800c3f17  mov     eax, eax
0x1800c3f19  cmp     [rdi+0F0h], rax
0x1800c3f20  jnz     short loc_1800C3F63
0x1800c3f22  mov     byte ptr [rdi+0F9h], 1
0x1800c3f29  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3f30  cmp     rcx, rbp
0x1800c3f33  jz      short loc_1800C3F54
0x1800c3f35  test    [rcx+1Ch], r14d
0x1800c3f39  jz      short loc_1800C3F54
0x1800c3f3b  mov     edx, 3Dh ; '='
0x1800c3f40  mov     r9, rdi
0x1800c3f43  lea     r8, WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids
0x1800c3f4a  mov     rcx, [rcx+10h]
0x1800c3f4e  call    WPP_SF_q
0x1800c3f53  nop
0x1800c3f54  lea     rcx, [rsp+78h+var_38]; this
0x1800c3f59  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800c3f5e  jmp     loc_1800C409C
0x1800c3f63  cmp     byte ptr [rdi+0F8h], 0
0x1800c3f6a  jz      short loc_1800C3FA0
0x1800c3f6c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800c3f6f  mov     rcx, rbx; this
0x1800c3f72  call    ?WaitForConditionVar@CWSManCriticalSectionWithConditionVar@@QEAAKK@Z; CWSManCriticalSectionWithConditionVar::WaitForConditionVar(ulong)
0x1800c3f77  test    eax, eax
0x1800c3f79  jz      short loc_1800C3F63
0x1800c3f7b  mov     [rsp+78h+var_58], 0; struct IRequestContext *
0x1800c3f84  mov     r9d, r15d; unsigned int
0x1800c3f87  lea     r8, a1882; "1882"
0x1800c3f8e  mov     edx, 75Ah; unsigned int
0x1800c3f93  lea     rcx, aOnecoreAdminWm_69; "onecore\\admin\\wmi\\wmx\\service\\list"...
0x1800c3f9a  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800c3f9f  nop
0x1800c3fa0  mov     ecx, [rbx]; dwErrCode
0x1800c3fa2  test    ecx, ecx
0x1800c3fa4  jnz     short loc_1800C3FB2
0x1800c3fa6  lea     rcx, [rbx+8]; lpCriticalSection
0x1800c3faa  call    cs:__imp_LeaveCriticalSection
0x1800c3fb0  jmp     short loc_1800C3FB8
0x1800c3fb2  call    cs:__imp_SetLastError
0x1800c3fb8  mov     rax, cs:WPP_GLOBAL_Control
0x1800c3fbf  cmp     rax, rbp
0x1800c3fc2  jz      loc_1800C4052
0x1800c3fc8  test    [rax+1Ch], r14d
0x1800c3fcc  jz      short loc_1800C3FED
0x1800c3fce  mov     edx, 3Eh ; '>'
0x1800c3fd3  mov     r9, rdi
0x1800c3fd6  lea     r8, WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids
0x1800c3fdd  mov     rcx, [rax+10h]
0x1800c3fe1  call    WPP_SF_q
0x1800c3fe6  mov     rax, cs:WPP_GLOBAL_Control
0x1800c3fed  cmp     rax, rbp
0x1800c3ff0  jz      short loc_1800C4052
0x1800c3ff2  test    dword ptr [rax+1Ch], 1000h
0x1800c3ff9  jz      short loc_1800C4052
0x1800c3ffb  mov     ebx, [rdi+8]
0x1800c3ffe  btr     ebx, 1Fh
0x1800c4002  mov     rcx, rdi; this
0x1800c4005  call    ?IsInitialized@IOperation@@QEBA_NXZ; IOperation::IsInitialized(void)
0x1800c400a  lea     rdx, aFalse; "false"
0x1800c4011  lea     rcx, aTrue; "true"
0x1800c4018  test    al, al
0x1800c401a  cmovz   rcx, rdx
0x1800c401e  mov     edx, 0Fh
0x1800c4023  mov     dword ptr [rsp+78h+var_48], ebx; char
0x1800c4027  mov     [rsp+78h+var_50], rcx; __int64
0x1800c402c  lea     rax, aChannel; "@Channel"
0x1800c4033  mov     [rsp+78h+var_58], rax; __int64
0x1800c4038  mov     r9, rdi
0x1800c403b  lea     r8, WPP_e4968f4695e73c65848dbd42e49ea3da_Traceguids
0x1800c4042  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4049  mov     rcx, [rcx+10h]; LoggerHandle
0x1800c404d  call    WPP_SF_qsSd
0x1800c4052  or      eax, 0FFFFFFFFh
0x1800c4055  lock xadd [rdi+8], eax
0x1800c405a  dec     eax
0x1800c405c  cmp     eax, 80000000h
0x1800c4061  jnz     short loc_1800C4089
0x1800c4063  mov     [rsp+78h+var_58], 0; struct IRequestContext *
0x1800c406c  mov     r9d, r15d; unsigned int
0x1800c406f  lea     r8, a174; "174"
0x1800c4076  mov     edx, 0AEh; unsigned int
0x1800c407b  lea     rcx, aOnecoreAdminWm_137; "onecore\\admin\\wmi\\wmx\\stdlib\\opera"...
0x1800c4082  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800c4087  jmp     short loc_1800C409C
0x1800c4089  test    eax, eax
0x1800c408b  jnz     short loc_1800C409C
0x1800c408d  mov     rax, [rdi]
0x1800c4090  mov     rcx, rdi
0x1800c4093  mov     rax, [rax+18h]
0x1800c4097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c409c  add     rsp, 50h
0x1800c40a0  pop     r15
0x1800c40a2  pop     r14
0x1800c40a4  pop     rdi
0x1800c40a5  pop     rbp
0x1800c40a6  pop     rbx
0x1800c40a7  retn
```
