# CSmsDeviceManager::WwanSmsReadDoneCallback(std::shared_ptr<std::vector<uchar,std::allocator<uchar>>> &)

- ea: `0x1800430d0`
- end: `0x180043170`
- name: `?WwanSmsReadDoneCallback@CSmsDeviceManager@@AEAAXAEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Z`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180041aa8`
- `0x1800430d0`
- `0x180051420`
- `0x180051628`
- `0x180053be8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800430f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800430f2`

## string_xrefs

- `0x180043126`: `CSmsDeviceManager::WwanSmsReadDoneCallback`
- `0x180043153`: `CSmsDeviceManager::WwanSmsReadDoneCallback`

## pseudocode

```c
void __fastcall CSmsDeviceManager::WwanSmsReadDoneCallback(__int64 a1, __int64 **a2)
{
  __int64 *v2; // rax
  __int64 v3; // rdi
  DWORD TickCount; // eax
  int v5; // ebx
  const char *GuidDisplayStringInternal; // rax
  CSmsDeviceManager *v7; // rcx

  v2 = *a2;
  if ( *a2 && (v3 = *v2, v2 = (__int64 *)(v2[1] - *v2), v2 == (__int64 *)32) )
  {
    TickCount = GetTickCount();
    v5 = *(_DWORD *)(v3 + 24);
    *(_DWORD *)(v3 + 28) = TickCount;
    GuidDisplayStringInternal = GetGuidDisplayStringInternal((const struct _GUID *)v3, &byte_18008DA30, 0x200u);
    LogSmsRouterInfo(
      "CSmsDeviceManager::WwanSmsReadDoneCallback",
      0x6A0u,
      "Publishing new sms notification for interface=%s, MessageIndex=%d.",
      GuidDisplayStringInternal,
      v5);
    CSmsDeviceManager::PublishSmsReadDoneData(v7, (void *)v3, 0x20u);
  }
  else
  {
    LogSmsRouterError(
      "CSmsDeviceManager::WwanSmsReadDoneCallback",
      0x696u,
      -2147024809,
      "Invalid new sms notification size=0x%08X",
      (_DWORD)v2);
  }
}

```

## disassembly

```asm
0x1800430d0  mov     [rsp+arg_0], rbx
0x1800430d5  push    rdi
0x1800430d6  sub     rsp, 30h
0x1800430da  mov     rax, [rdx]
0x1800430dd  test    rax, rax
0x1800430e0  jz      short loc_180043142
0x1800430e2  mov     rdi, [rax]
0x1800430e5  mov     rax, [rax+8]
0x1800430e9  sub     rax, rdi
0x1800430ec  cmp     rax, 20h ; ' '
0x1800430f0  jnz     short loc_180043142
0x1800430f2  call    cs:__imp_GetTickCount
0x1800430f8  mov     ebx, [rdi+18h]
0x1800430fb  lea     rdx, byte_18008DA30; char *
0x180043102  mov     r8d, 200h; unsigned __int64
0x180043108  mov     [rdi+1Ch], eax
0x18004310b  mov     rcx, rdi; struct _GUID *
0x18004310e  call    ?GetGuidDisplayStringInternal@@YAPEBDPEBU_GUID@@PEAD_K@Z; GetGuidDisplayStringInternal(_GUID const *,char *,unsigned __int64)
0x180043113  mov     r9, rax
0x180043116  mov     dword ptr [rsp+38h+var_18], ebx
0x18004311a  lea     r8, aPublishingNewS; "Publishing new sms notification for int"...
0x180043121  mov     edx, 6A0h; unsigned int
0x180043126  lea     rcx, aCsmsdevicemana_11; "CSmsDeviceManager::WwanSmsReadDoneCallb"...
0x18004312d  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180043132  mov     r8d, 20h ; ' '; unsigned int
0x180043138  mov     rdx, rdi; void *
0x18004313b  call    ?PublishSmsReadDoneData@CSmsDeviceManager@@AEAAXPEAXK@Z; CSmsDeviceManager::PublishSmsReadDoneData(void *,ulong)
0x180043140  jmp     short loc_180043165
0x180043142  lea     r9, aInvalidNewSmsN; "Invalid new sms notification size=0x%08"...
0x180043149  mov     [rsp+38h+var_18], rax
0x18004314e  mov     edx, 696h; unsigned int
0x180043153  lea     rcx, aCsmsdevicemana_11; "CSmsDeviceManager::WwanSmsReadDoneCallb"...
0x18004315a  mov     r8d, 80070057h; int
0x180043160  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180043165  mov     rbx, [rsp+38h+arg_0]
0x18004316a  add     rsp, 30h
0x18004316e  pop     rdi
0x18004316f  retn
```
