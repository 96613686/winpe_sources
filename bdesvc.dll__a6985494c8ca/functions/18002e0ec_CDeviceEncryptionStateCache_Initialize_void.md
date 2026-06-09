# CDeviceEncryptionStateCache::Initialize(void)

- ea: `0x18002e0ec`
- end: `0x18002e2b0`
- name: `?Initialize@CDeviceEncryptionStateCache@@QEAAJXZ`
- size: `452`
- prototype: `__int64 __fastcall(CDeviceEncryptionStateCache *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180020084`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18002b6ac`
- `0x18002e0ec`
- `0x18002e2b8`
- `0x180054ce8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e13b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e1cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e13b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e1cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e15a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e15a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1ea`

## string_xrefs

- `0x18002e17a`: `CacheAvailableEvent`
- `0x18002e20a`: `UpdateCacheEvent`

## pseudocode

```c
__int64 __fastcall CDeviceEncryptionStateCache::Initialize(CDeviceEncryptionStateCache *this)
{
  HANDLE EventW; // rax
  signed int v3; // eax
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  HANDLE v8; // rax
  signed int LastError; // eax
  unsigned int v10; // eax
  const char *v12; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  EventW = CreateEventW(0, 1, 0, 0);
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(
    (char *)this + 32,
    EventW);
  if ( *((_QWORD *)this + 5) )
  {
    v8 = CreateEventW(0, 0, 0, 0);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(
      (char *)this + 48,
      v8);
    if ( *((_QWORD *)this + 7) )
    {
      v10 = CDeviceEncryptionStateCache::InvalidateCache(this);
      v4 = v10;
      if ( !v10 )
      {
LABEL_22:
        v5 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_23;
      }
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v4;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_23;
      v6 = 86;
      v7 = v10;
LABEL_21:
      WPP_SF_d(v5[2], v6, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v7);
      goto LABEL_22;
    }
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x41F,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)v4,
      (int)"UpdateCacheEvent",
      v12);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v6 = 85;
        goto LABEL_10;
      }
LABEL_23:
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
        WPP_SF_(v5[2], 87, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x411,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)v4,
      (int)"CacheAvailableEvent",
      v12);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v6 = 84;
LABEL_10:
        v7 = v4;
        goto LABEL_21;
      }
      goto LABEL_23;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18002e0ec  mov     [rsp+arg_0], rbx
0x18002e0f1  mov     [rsp+arg_8], rsi
0x18002e0f6  push    rdi
0x18002e0f7  sub     rsp, 30h
0x18002e0fb  mov     rbx, rcx
0x18002e0fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e105  lea     rdi, WPP_GLOBAL_Control
0x18002e10c  lea     rsi, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x18002e113  cmp     rcx, rdi
0x18002e116  jz      short loc_18002E12F
0x18002e118  test    byte ptr [rcx+1Ch], 20h
0x18002e11c  jz      short loc_18002E12F
0x18002e11e  mov     rcx, [rcx+10h]
0x18002e122  mov     edx, 53h ; 'S'
0x18002e127  mov     r8, rsi
0x18002e12a  call    WPP_SF_
0x18002e12f  xor     r9d, r9d; lpName
0x18002e132  xor     r8d, r8d; bInitialState
0x18002e135  xor     ecx, ecx; lpEventAttributes
0x18002e137  lea     edx, [r9+1]; bManualReset
0x18002e13b  call    cs:__imp_CreateEventW
0x18002e142  nop     dword ptr [rax+rax+00h]
0x18002e147  mov     rdx, rax
0x18002e14a  lea     rcx, [rbx+20h]
0x18002e14e  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x18002e153  cmp     qword ptr [rbx+28h], 0
0x18002e158  jnz     short loc_18002E1C1
0x18002e15a  call    cs:__imp_GetLastError
0x18002e161  nop     dword ptr [rax+rax+00h]
0x18002e166  mov     ebx, eax
0x18002e168  test    eax, eax
0x18002e16a  jle     short loc_18002E175
0x18002e16c  movzx   ebx, ax
0x18002e16f  or      ebx, 80070000h
0x18002e175  mov     rcx, [rsp+38h]; this
0x18002e17a  lea     rax, aCacheavailable; "CacheAvailableEvent"
0x18002e181  mov     r9d, ebx; char *
0x18002e184  mov     qword ptr [rsp+38h+var_18], rax; int
0x18002e189  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x18002e190  mov     edx, 411h; void *
0x18002e195  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002e19a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e1a1  cmp     rcx, rdi
0x18002e1a4  jz      loc_18002E29D
0x18002e1aa  test    byte ptr [rcx+1Ch], 40h
0x18002e1ae  jz      loc_18002E281
0x18002e1b4  mov     edx, 54h ; 'T'
0x18002e1b9  mov     r9d, ebx
0x18002e1bc  jmp     loc_18002E26E
0x18002e1c1  xor     r9d, r9d; lpName
0x18002e1c4  xor     r8d, r8d; bInitialState
0x18002e1c7  xor     edx, edx; bManualReset
0x18002e1c9  xor     ecx, ecx; lpEventAttributes
0x18002e1cb  call    cs:__imp_CreateEventW
0x18002e1d2  nop     dword ptr [rax+rax+00h]
0x18002e1d7  mov     rdx, rax
0x18002e1da  lea     rcx, [rbx+30h]
0x18002e1de  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x18002e1e3  cmp     qword ptr [rbx+38h], 0
0x18002e1e8  jnz     short loc_18002E246
0x18002e1ea  call    cs:__imp_GetLastError
0x18002e1f1  nop     dword ptr [rax+rax+00h]
0x18002e1f6  mov     ebx, eax
0x18002e1f8  test    eax, eax
0x18002e1fa  jle     short loc_18002E205
0x18002e1fc  movzx   ebx, ax
0x18002e1ff  or      ebx, 80070000h
0x18002e205  mov     rcx, [rsp+38h]; this
0x18002e20a  lea     rax, aUpdatecacheeve; "UpdateCacheEvent"
0x18002e211  mov     r9d, ebx; char *
0x18002e214  mov     qword ptr [rsp+38h+var_18], rax; int
0x18002e219  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x18002e220  mov     edx, 41Fh; void *
0x18002e225  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002e22a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e231  cmp     rcx, rdi
0x18002e234  jz      short loc_18002E29D
0x18002e236  test    byte ptr [rcx+1Ch], 40h
0x18002e23a  jz      short loc_18002E281
0x18002e23c  mov     edx, 55h ; 'U'
0x18002e241  jmp     loc_18002E1B9
0x18002e246  mov     rcx, rbx; this
0x18002e249  call    ?InvalidateCache@CDeviceEncryptionStateCache@@QEAAJXZ; CDeviceEncryptionStateCache::InvalidateCache(void)
0x18002e24e  mov     ebx, eax
0x18002e250  test    eax, eax
0x18002e252  jz      short loc_18002E27A
0x18002e254  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e25b  cmp     rcx, rdi
0x18002e25e  jz      short loc_18002E29D
0x18002e260  test    byte ptr [rcx+1Ch], 40h
0x18002e264  jz      short loc_18002E281
0x18002e266  mov     edx, 56h ; 'V'
0x18002e26b  mov     r9d, eax
0x18002e26e  mov     rcx, [rcx+10h]
0x18002e272  mov     r8, rsi
0x18002e275  call    WPP_SF_d
0x18002e27a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e281  cmp     rcx, rdi
0x18002e284  jz      short loc_18002E29D
0x18002e286  test    byte ptr [rcx+1Ch], 20h
0x18002e28a  jz      short loc_18002E29D
0x18002e28c  mov     rcx, [rcx+10h]
0x18002e290  mov     edx, 57h ; 'W'
0x18002e295  mov     r8, rsi
0x18002e298  call    WPP_SF_
0x18002e29d  mov     rsi, [rsp+38h+arg_8]
0x18002e2a2  mov     eax, ebx
0x18002e2a4  mov     rbx, [rsp+38h+arg_0]
0x18002e2a9  add     rsp, 30h
0x18002e2ad  pop     rdi
0x18002e2ae  retn
```
