# WaaSRemediationAgent::SetTaskCompleted(long)

- ea: `0x180061574`
- end: `0x18006164e`
- name: `?SetTaskCompleted@WaaSRemediationAgent@@AEAAJJ@Z`
- size: `218`
- prototype: `__int64 __fastcall(WaaSRemediationAgent *this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180062a70`

## callees

- `0x18002e81c`
- `0x180061574`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006158c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006158c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006161e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006161e`

## string_xrefs

- `0x1800615cd`: `WaaS Remediation agent encountered an error when reporting task completion. hr = 0x%08x`
- `0x18006162b`: `Failed to set task completed. hr = 0x%08x`
- `0x18006159e`: `Task handler status is unexpectedly missing.`

## pseudocode

```c
__int64 __fastcall WaaSRemediationAgent::SetTaskCompleted(WaaSRemediationAgent *this, unsigned int a2)
{
  __int64 v4; // rcx
  int v5; // edi
  int v6; // eax
  __int64 v7; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v4 = *((_QWORD *)this + 18);
  if ( v4 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 32LL))(v4, a2);
    v5 = v6;
    if ( v6 < 0 )
      LogLevelW(
        2u,
        L"WaaS Remediation agent encountered an error when reporting task completion. hr = 0x%08x",
        (unsigned int)v6);
  }
  else
  {
    v5 = -2147418113;
    LogLevelW(2u, L"Task handler status is unexpectedly missing.");
  }
  if ( *((_BYTE *)this + 128) && *((_BYTE *)this + 129) )
    *((_BYTE *)this + 129) = 0;
  v7 = *((_QWORD *)this + 18);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 18) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( v5 < 0 )
    LogLevelW(2u, L"Failed to set task completed. hr = 0x%08x", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180061574  mov     [rsp+arg_0], rbx
0x180061579  mov     [rsp+arg_8], rsi
0x18006157e  push    rdi
0x18006157f  sub     rsp, 20h
0x180061583  mov     rbx, rcx
0x180061586  mov     edi, edx
0x180061588  add     rcx, 58h ; 'X'; lpCriticalSection
0x18006158c  call    cs:__imp_EnterCriticalSection
0x180061592  mov     rcx, [rbx+90h]
0x180061599  test    rcx, rcx
0x18006159c  jnz     short loc_1800615B6
0x18006159e  lea     rdx, aTaskHandlerSta; "Task handler status is unexpectedly mis"...
0x1800615a5  mov     ecx, 2; unsigned __int8
0x1800615aa  mov     edi, 8000FFFFh
0x1800615af  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800615b4  jmp     short loc_1800615DE
0x1800615b6  mov     rax, [rcx]
0x1800615b9  mov     edx, edi
0x1800615bb  mov     rax, [rax+20h]
0x1800615bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800615c4  mov     edi, eax
0x1800615c6  test    eax, eax
0x1800615c8  jns     short loc_1800615DE
0x1800615ca  mov     r8d, eax
0x1800615cd  lea     rdx, aWaasRemediatio_3; "WaaS Remediation agent encountered an e"...
0x1800615d4  mov     ecx, 2; unsigned __int8
0x1800615d9  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800615de  cmp     byte ptr [rbx+80h], 0
0x1800615e5  jz      short loc_1800615F7
0x1800615e7  cmp     byte ptr [rbx+81h], 0
0x1800615ee  jz      short loc_1800615F7
0x1800615f0  mov     byte ptr [rbx+81h], 0
0x1800615f7  mov     rcx, [rbx+90h]
0x1800615fe  test    rcx, rcx
0x180061601  jz      short loc_18006161A
0x180061603  mov     rax, [rcx]
0x180061606  mov     rax, [rax+10h]
0x18006160a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006160f  mov     qword ptr [rbx+90h], 0
0x18006161a  lea     rcx, [rbx+58h]; lpCriticalSection
0x18006161e  call    cs:__imp_LeaveCriticalSection
0x180061624  test    edi, edi
0x180061626  jns     short loc_18006163C
0x180061628  mov     r8d, edi
0x18006162b  lea     rdx, aFailedToSetTas; "Failed to set task completed. hr = 0x%0"...
0x180061632  mov     ecx, 2; unsigned __int8
0x180061637  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006163c  mov     rbx, [rsp+28h+arg_0]
0x180061641  mov     eax, edi
0x180061643  mov     rsi, [rsp+28h+arg_8]
0x180061648  add     rsp, 20h
0x18006164c  pop     rdi
0x18006164d  retn
```
