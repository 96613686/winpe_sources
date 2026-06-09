# CDeviceEncryptionStateCache::InvalidateCache(void)

- ea: `0x180054ce8`
- end: `0x180054e1f`
- name: `?InvalidateCache@CDeviceEncryptionStateCache@@QEAAJXZ`
- size: `311`
- prototype: `__int64 __fastcall(CDeviceEncryptionStateCache *__hidden this)`
- caller_count: `6`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800090d0`
- `0x18002db24`
- `0x18002e0ec`
- `0x1800553b0`
- `0x180055700`
- `0x180055a10`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000a010`
- `0x18002b6ac`
- `0x180054ce8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054cfb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054cfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054e07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054e07`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180054dcb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180054dcb`

## string_xrefs

- `0x180054da3`: `WorkerThreadLauncher`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDeviceEncryptionStateCache::InvalidateCache(HANDLE *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  int v3; // eax
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  const char *v7; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (struct _RTL_CRITICAL_SECTION *)(this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 8));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  if ( *((_BYTE *)this + 104) )
  {
    v4 = 0;
    SetEvent(this[7]);
    goto LABEL_13;
  }
  v3 = WorkerThreadLauncher((__int64)CDeviceEncryptionStateCache::UpdateCacheThreadEntry, (__int64)this, 7, 0);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v4);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (v4 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x450,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)v4,
      (int)"WorkerThreadLauncher",
      v7);
LABEL_13:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
    WPP_SF_(v5[2], 90, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  if ( v2 )
    LeaveCriticalSection(v2);
  return v4;
}

```

## disassembly

```asm
0x180054ce8  push    rbx
0x180054cea  push    rbp
0x180054ceb  push    rsi
0x180054cec  push    rdi
0x180054ced  sub     rsp, 38h
0x180054cf1  mov     rdi, rcx
0x180054cf4  lea     rsi, [rcx+40h]
0x180054cf8  mov     rcx, rsi; lpCriticalSection
0x180054cfb  call    cs:__imp_EnterCriticalSection
0x180054d02  nop     dword ptr [rax+rax+00h]
0x180054d07  mov     [rsp+58h+arg_0], rsi
0x180054d0c  lea     rbp, WPP_GLOBAL_Control
0x180054d13  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d1a  cmp     rcx, rbp
0x180054d1d  jz      short loc_180054D3A
0x180054d1f  test    byte ptr [rcx+1Ch], 20h
0x180054d23  jz      short loc_180054D3A
0x180054d25  mov     edx, 58h ; 'X'
0x180054d2a  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x180054d31  mov     rcx, [rcx+10h]
0x180054d35  call    WPP_SF_
0x180054d3a  cmp     byte ptr [rdi+68h], 0
0x180054d3e  jnz     loc_180054DC5
0x180054d44  xor     r9d, r9d
0x180054d47  lea     r8d, [r9+7]
0x180054d4b  mov     rdx, rdi
0x180054d4e  lea     rcx, ?UpdateCacheThreadEntry@CDeviceEncryptionStateCache@@CAIPEAX@Z; CDeviceEncryptionStateCache::UpdateCacheThreadEntry(void *)
0x180054d55  call    ?WorkerThreadLauncher@@YAKP6AIPEAX@Z0W4WorkerThreadFlags@@PEAK@Z; WorkerThreadLauncher(uint (*)(void *),void *,WorkerThreadFlags,ulong *)
0x180054d5a  mov     ebx, eax
0x180054d5c  test    eax, eax
0x180054d5e  jle     short loc_180054D69
0x180054d60  movzx   ebx, ax
0x180054d63  or      ebx, 80070000h
0x180054d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d70  cmp     rcx, rbp
0x180054d73  jz      short loc_180054D9A
0x180054d75  test    byte ptr [rcx+1Ch], 40h
0x180054d79  jz      short loc_180054D9A
0x180054d7b  mov     edx, 59h ; 'Y'
0x180054d80  mov     r9d, ebx
0x180054d83  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x180054d8a  mov     rcx, [rcx+10h]
0x180054d8e  call    WPP_SF_d
0x180054d93  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d9a  test    ebx, ebx
0x180054d9c  jns     short loc_180054DDE
0x180054d9e  mov     rcx, [rsp+58h]; this
0x180054da3  lea     rax, aWorkerthreadla; "WorkerThreadLauncher"
0x180054daa  mov     qword ptr [rsp+58h+var_38], rax; int
0x180054daf  mov     r9d, ebx; char *
0x180054db2  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x180054db9  mov     edx, 450h; void *
0x180054dbe  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180054dc3  jmp     short loc_180054DD7
0x180054dc5  xor     ebx, ebx
0x180054dc7  mov     rcx, [rdi+38h]; hEvent
0x180054dcb  call    cs:__imp_SetEvent
0x180054dd2  nop     dword ptr [rax+rax+00h]
0x180054dd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180054dde  cmp     rcx, rbp
0x180054de1  jz      short loc_180054DFF
0x180054de3  test    byte ptr [rcx+1Ch], 20h
0x180054de7  jz      short loc_180054DFF
0x180054de9  mov     edx, 5Ah ; 'Z'
0x180054dee  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x180054df5  mov     rcx, [rcx+10h]
0x180054df9  call    WPP_SF_
0x180054dfe  nop
0x180054dff  test    rsi, rsi
0x180054e02  jz      short loc_180054E13
0x180054e04  mov     rcx, rsi; lpCriticalSection
0x180054e07  call    cs:__imp_LeaveCriticalSection
0x180054e0e  nop     dword ptr [rax+rax+00h]
0x180054e13  mov     eax, ebx
0x180054e15  add     rsp, 38h
0x180054e19  pop     rdi
0x180054e1a  pop     rsi
0x180054e1b  pop     rbp
0x180054e1c  pop     rbx
0x180054e1d  retn
```
