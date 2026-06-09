# CCredUIBrokerBase::_RegisterWaitForCallingProcessTermination(CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *)

- ea: `0x1400182c8`
- end: `0x140018490`
- name: `?_RegisterWaitForCallingProcessTermination@CCredUIBrokerBase@@AEAAXPEAUCREDUI_INFO_INTERNAL@@0@Z`
- size: `456`
- prototype: `void __fastcall(CCredUIBrokerBase *__hidden this, struct CREDUI_INFO_INTERNAL *, struct CREDUI_INFO_INTERNAL *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140017fc0`

## callees

- `0x140013600`
- `0x140017b60`
- `0x1400182c8`
- `0x14001d1ec`

## import_xrefs

- `KERNEL32!RegisterWaitForSingleObject` at `0x1400183f3`
- `KERNEL32!RegisterWaitForSingleObject` at `0x14001841a`
- `KERNEL32!RegisterWaitForSingleObject` at `0x140018479`
- `KERNEL32!RegisterWaitForSingleObject` at `0x1400183f3`
- `KERNEL32!RegisterWaitForSingleObject` at `0x14001841a`
- `KERNEL32!RegisterWaitForSingleObject` at `0x140018479`
- `KERNEL32!GetProcessId` at `0x1400183a2`
- `KERNEL32!GetProcessId` at `0x1400183a2`
- `KERNEL32!OpenEventW` at `0x14001843f`
- `KERNEL32!OpenEventW` at `0x14001843f`
- `KERNEL32!OpenProcess` at `0x1400183b9`
- `KERNEL32!OpenProcess` at `0x1400183b9`
- `KERNEL32!CreateEventW` at `0x140018349`
- `KERNEL32!CreateEventW` at `0x140018349`
- `USER32!GetWindowThreadProcessId` at `0x14001838c`
- `USER32!GetWindowThreadProcessId` at `0x14001838c`

## pseudocode

```c
void __fastcall CCredUIBrokerBase::_RegisterWaitForCallingProcessTermination(
        CCredUIBrokerBase *this,
        struct CREDUI_INFO_INTERNAL *a2,
        struct CREDUI_INFO_INTERNAL *a3)
{
  HANDLE EventW; // rax
  void **v7; // r8
  HWND v8; // rcx
  DWORD ProcessId; // eax
  HANDLE v10; // rax
  const WCHAR *v11; // r8
  HANDLE v12; // rax
  DWORD dwProcessId; // [rsp+68h] [rbp+10h] BYREF

  *(_OWORD *)a3 = *(_OWORD *)a2;
  *((_OWORD *)a3 + 1) = *((_OWORD *)a2 + 1);
  *((_OWORD *)a3 + 2) = *((_OWORD *)a2 + 2);
  *((_OWORD *)a3 + 3) = *((_OWORD *)a2 + 3);
  *((_OWORD *)a3 + 4) = *((_OWORD *)a2 + 4);
  *((_OWORD *)a3 + 5) = *((_OWORD *)a2 + 5);
  *((_OWORD *)a3 + 6) = *((_OWORD *)a2 + 6);
  *((_OWORD *)a3 + 7) = *((_OWORD *)a2 + 7);
  *((_QWORD *)a3 + 16) = *((_QWORD *)a2 + 16);
  if ( (int)CCredUIBrokerBase::_CreateUniqueEventName(this) >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, *((LPCWSTR *)this + 7));
    *((_QWORD *)this + 2) = EventW;
    if ( EventW || (int)ResultFromKnownLastError() >= 0 )
    {
      if ( (int)CallerIdentity::GetCallingProcessHandle((CallerIdentity *)0x100000, (unsigned int)this, v7) >= 0 )
      {
        v8 = (HWND)*((_QWORD *)a2 + 1);
        if ( v8 )
        {
          dwProcessId = 0;
          if ( GetWindowThreadProcessId(v8, &dwProcessId) || (int)ResultFromKnownLastError() >= 0 )
          {
            ProcessId = GetProcessId(*(HANDLE *)this);
            if ( dwProcessId != ProcessId )
            {
              v10 = OpenProcess(0x100000u, 0, dwProcessId);
              *((_QWORD *)this + 5) = v10;
              if ( v10 || (int)ResultFromKnownLastError() >= 0 )
                RegisterWaitForSingleObject(
                  (PHANDLE)this + 6,
                  *((HANDLE *)this + 5),
                  CCredUIBrokerBase::_s_TriggerUIAbort,
                  this,
                  0xFFFFFFFF,
                  8u);
            }
          }
        }
        if ( !RegisterWaitForSingleObject(
                (PHANDLE)this + 1,
                *(HANDLE *)this,
                CCredUIBrokerBase::_s_TriggerUIAbort,
                this,
                0xFFFFFFFF,
                8u) )
          ResultFromKnownLastError();
      }
      v11 = (const WCHAR *)*((_QWORD *)a2 + 11);
      if ( v11 )
      {
        if ( *v11 )
        {
          v12 = OpenEventW(0x100000u, 0, v11);
          *((_QWORD *)this + 4) = v12;
          if ( v12 || (int)ResultFromKnownLastError() >= 0 )
            RegisterWaitForSingleObject(
              (PHANDLE)this + 3,
              *((HANDLE *)this + 4),
              CCredUIBrokerBase::_s_TriggerUIAbort,
              this,
              0xFFFFFFFF,
              8u);
        }
      }
      *((_QWORD *)a3 + 11) = *((_QWORD *)this + 7);
    }
  }
}

```

## disassembly

```asm
0x1400182c8  push    rbx
0x1400182ca  push    rbp
0x1400182cb  push    rsi
0x1400182cc  push    rdi
0x1400182cd  sub     rsp, 38h
0x1400182d1  movups  xmm0, xmmword ptr [rdx]
0x1400182d4  mov     rsi, r8
0x1400182d7  mov     rdi, rdx
0x1400182da  mov     rbx, rcx
0x1400182dd  movups  xmmword ptr [r8], xmm0
0x1400182e1  movups  xmm1, xmmword ptr [rdx+10h]
0x1400182e5  movups  xmmword ptr [r8+10h], xmm1
0x1400182ea  movups  xmm0, xmmword ptr [rdx+20h]
0x1400182ee  movups  xmmword ptr [r8+20h], xmm0
0x1400182f3  movups  xmm1, xmmword ptr [rdx+30h]
0x1400182f7  movups  xmmword ptr [r8+30h], xmm1
0x1400182fc  movups  xmm0, xmmword ptr [rdx+40h]
0x140018300  movups  xmmword ptr [r8+40h], xmm0
0x140018305  movups  xmm1, xmmword ptr [rdx+50h]
0x140018309  movups  xmmword ptr [r8+50h], xmm1
0x14001830e  movups  xmm0, xmmword ptr [rdx+60h]
0x140018312  movups  xmmword ptr [r8+60h], xmm0
0x140018317  movups  xmm1, xmmword ptr [rdx+70h]
0x14001831b  movups  xmmword ptr [r8+70h], xmm1
0x140018320  mov     rax, [rdx+80h]
0x140018327  mov     [r8+80h], rax
0x14001832e  call    ?_CreateUniqueEventName@CCredUIBrokerBase@@AEAAJXZ; CCredUIBrokerBase::_CreateUniqueEventName(void)
0x140018333  xor     ebp, ebp
0x140018335  test    eax, eax
0x140018337  js      loc_140018487
0x14001833d  mov     r9, [rbx+38h]; lpName
0x140018341  lea     edx, [rbp+1]; bManualReset
0x140018344  xor     r8d, r8d; bInitialState
0x140018347  xor     ecx, ecx; lpEventAttributes
0x140018349  call    cs:__imp_CreateEventW
0x14001834f  mov     [rbx+10h], rax
0x140018353  test    rax, rax
0x140018356  jnz     short loc_140018365
0x140018358  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001835d  test    eax, eax
0x14001835f  js      loc_140018487
0x140018365  mov     rdx, rbx; unsigned int
0x140018368  mov     ecx, 100000h; this
0x14001836d  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x140018372  test    eax, eax
0x140018374  js      loc_140018429
0x14001837a  mov     rcx, [rdi+8]; hWnd
0x14001837e  test    rcx, rcx
0x140018381  jz      short loc_1400183F9
0x140018383  lea     rdx, [rsp+58h+dwProcessId]; lpdwProcessId
0x140018388  mov     [rsp+58h+dwProcessId], ebp
0x14001838c  call    cs:__imp_GetWindowThreadProcessId
0x140018392  test    eax, eax
0x140018394  jnz     short loc_14001839F
0x140018396  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001839b  test    eax, eax
0x14001839d  js      short loc_1400183F9
0x14001839f  mov     rcx, [rbx]; Process
0x1400183a2  call    cs:__imp_GetProcessId
0x1400183a8  mov     r8d, [rsp+58h+dwProcessId]; dwProcessId
0x1400183ad  cmp     r8d, eax
0x1400183b0  jz      short loc_1400183F9
0x1400183b2  xor     edx, edx; bInheritHandle
0x1400183b4  mov     ecx, 100000h; dwDesiredAccess
0x1400183b9  call    cs:__imp_OpenProcess
0x1400183bf  mov     [rbx+28h], rax
0x1400183c3  test    rax, rax
0x1400183c6  jnz     short loc_1400183D1
0x1400183c8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400183cd  test    eax, eax
0x1400183cf  js      short loc_1400183F9
0x1400183d1  mov     rdx, [rbx+28h]; hObject
0x1400183d5  lea     rcx, [rbx+30h]; phNewWaitObject
0x1400183d9  mov     [rsp+58h+dwFlags], 8; dwFlags
0x1400183e1  lea     r8, ?_s_TriggerUIAbort@CCredUIBrokerBase@@CAXPEAXE@Z; Callback
0x1400183e8  mov     r9, rbx; Context
0x1400183eb  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1400183f3  call    cs:__imp_RegisterWaitForSingleObject
0x1400183f9  mov     rdx, [rbx]; hObject
0x1400183fc  lea     rcx, [rbx+8]; phNewWaitObject
0x140018400  mov     [rsp+58h+dwFlags], 8; dwFlags
0x140018408  lea     r8, ?_s_TriggerUIAbort@CCredUIBrokerBase@@CAXPEAXE@Z; Callback
0x14001840f  mov     r9, rbx; Context
0x140018412  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x14001841a  call    cs:__imp_RegisterWaitForSingleObject
0x140018420  test    eax, eax
0x140018422  jnz     short loc_140018429
0x140018424  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140018429  mov     r8, [rdi+58h]; lpName
0x14001842d  test    r8, r8
0x140018430  jz      short loc_14001847F
0x140018432  cmp     [r8], bp
0x140018436  jz      short loc_14001847F
0x140018438  xor     edx, edx; bInheritHandle
0x14001843a  mov     ecx, 100000h; dwDesiredAccess
0x14001843f  call    cs:__imp_OpenEventW
0x140018445  mov     [rbx+20h], rax
0x140018449  test    rax, rax
0x14001844c  jnz     short loc_140018457
0x14001844e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140018453  test    eax, eax
0x140018455  js      short loc_14001847F
0x140018457  mov     rdx, [rbx+20h]; hObject
0x14001845b  lea     rcx, [rbx+18h]; phNewWaitObject
0x14001845f  mov     [rsp+58h+dwFlags], 8; dwFlags
0x140018467  lea     r8, ?_s_TriggerUIAbort@CCredUIBrokerBase@@CAXPEAXE@Z; Callback
0x14001846e  mov     r9, rbx; Context
0x140018471  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x140018479  call    cs:__imp_RegisterWaitForSingleObject
0x14001847f  mov     rax, [rbx+38h]
0x140018483  mov     [rsi+58h], rax
0x140018487  add     rsp, 38h
0x14001848b  pop     rdi
0x14001848c  pop     rsi
0x14001848d  pop     rbp
0x14001848e  pop     rbx
0x14001848f  retn
```
