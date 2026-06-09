# PimIMService::OnLoad(void)

- ea: `0x1800089c4`
- end: `0x180008a52`
- name: `?OnLoad@PimIMService@@QEAAJXZ`
- size: `142`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *pv)`
- caller_count: `8`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180008da0`
- `0x18000c970`
- `0x18000cb30`
- `0x18000cbb0`
- `0x18000cc80`
- `0x18000cee0`
- `0x18000cf70`
- `0x18000d020`

## callees

- `0x180002da8`
- `0x1800089c4`
- `0x180009c7c`
- `0x18000d63c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800089e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800089e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a3a`

## string_xrefs

- `0x180008a16`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::OnLoad(struct _RTL_CRITICAL_SECTION *pv)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // r9

  v1 = pv + 8;
  EnterCriticalSection(pv + 8);
  v3 = FailOnServiceShutdown();
  v4 = v3;
  if ( v3 >= 0 )
  {
    if ( !HIDWORD(pv[5].SpinCount) )
    {
      v3 = PimIMService::SetupEventsAndThreadpool(pv);
      v4 = v3;
      if ( v3 < 0 )
      {
        v5 = 531;
        goto LABEL_6;
      }
      HIDWORD(pv[5].SpinCount) = 1;
    }
    v4 = 0;
    goto LABEL_9;
  }
  v5 = 527;
LABEL_6:
  Log_HREvent(
    (unsigned int)v3,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
    v5);
LABEL_9:
  LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x1800089c4  mov     [rsp+arg_0], rbx
0x1800089c9  mov     [rsp+arg_8], rsi
0x1800089ce  push    rdi
0x1800089cf  sub     rsp, 30h
0x1800089d3  lea     rsi, [rcx+140h]
0x1800089da  mov     rdi, rcx
0x1800089dd  mov     rcx, rsi; lpCriticalSection
0x1800089e0  call    cs:__imp_EnterCriticalSection
0x1800089e6  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x1800089eb  mov     ebx, eax
0x1800089ed  test    eax, eax
0x1800089ef  jns     short loc_1800089F9
0x1800089f1  mov     r9d, 20Fh
0x1800089f7  jmp     short loc_180008A16
0x1800089f9  cmp     dword ptr [rdi+0ECh], 0
0x180008a00  jnz     short loc_180008A35
0x180008a02  mov     rcx, rdi; pv
0x180008a05  call    ?SetupEventsAndThreadpool@PimIMService@@QEAAJXZ; PimIMService::SetupEventsAndThreadpool(void)
0x180008a0a  mov     ebx, eax
0x180008a0c  test    eax, eax
0x180008a0e  jns     short loc_180008A2B
0x180008a10  mov     r9d, 213h
0x180008a16  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008a1d  mov     edx, 1
0x180008a22  mov     ecx, eax
0x180008a24  call    Log_HREvent
0x180008a29  jmp     short loc_180008A37
0x180008a2b  mov     dword ptr [rdi+0ECh], 1
0x180008a35  xor     ebx, ebx
0x180008a37  mov     rcx, rsi; lpCriticalSection
0x180008a3a  call    cs:__imp_LeaveCriticalSection
0x180008a40  mov     rsi, [rsp+38h+arg_8]
0x180008a45  mov     eax, ebx
0x180008a47  mov     rbx, [rsp+38h+arg_0]
0x180008a4c  add     rsp, 30h
0x180008a50  pop     rdi
0x180008a51  retn
```
