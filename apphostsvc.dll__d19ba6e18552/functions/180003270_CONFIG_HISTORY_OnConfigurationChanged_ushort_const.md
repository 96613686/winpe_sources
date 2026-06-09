# CONFIG_HISTORY::OnConfigurationChanged(ushort const *)

- ea: `0x180003270`
- end: `0x1800032e8`
- name: `?OnConfigurationChanged@CONFIG_HISTORY@@UEAAJPEBG@Z`
- size: `120`
- prototype: `__int64 __fastcall(CONFIG_HISTORY *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180003270`
- `0x180008464`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003293`
- `msvcrt!_wcsicmp` at `0x1800032d0`
- `msvcrt!_wcsicmp` at `0x180003293`
- `msvcrt!_wcsicmp` at `0x1800032d0`

## pseudocode

```c
__int64 __fastcall CONFIG_HISTORY::OnConfigurationChanged(CONFIG_HISTORY *this, const unsigned __int16 *a2)
{
  unsigned int v2; // esi

  v2 = 0;
  if ( *((_DWORD *)this + 31) != 1 )
  {
    if ( _wcsicmp(a2, L"MACHINE/WEBROOT/APPHOST") )
    {
      if ( !_wcsicmp(a2, L"MACHINE") )
        _InterlockedExchange((volatile __int32 *)this + 30, 1);
    }
    else
    {
      _InterlockedExchange((volatile __int32 *)this + 30, 1);
      return (unsigned int)MULTI_WORK_QUEUE::GetAndQueueWorkItem(
                             (APP_HOST_SERVICE *)((char *)g_pAppHostService + 24),
                             (struct MULTI_WORK_DISPATCH *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
                             1u);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180003270  push    rbx
0x180003272  push    rbp
0x180003273  push    rsi
0x180003274  push    rdi
0x180003275  sub     rsp, 28h
0x180003279  xor     esi, esi
0x18000327b  mov     rbp, rdx
0x18000327e  mov     rbx, rcx
0x180003281  lea     edi, [rsi+1]
0x180003284  cmp     [rcx+7Ch], edi
0x180003287  jz      short loc_1800032DD
0x180003289  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180003290  mov     rcx, rbp; String1
0x180003293  call    cs:__imp__wcsicmp
0x180003299  test    eax, eax
0x18000329b  jnz     short loc_1800032C6
0x18000329d  mov     eax, edi
0x18000329f  mov     r8d, edi; unsigned __int64
0x1800032a2  xchg    eax, [rbx+78h]
0x1800032a5  mov     rcx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x1800032ac  lea     rax, [rbx+8]
0x1800032b0  neg     rbx
0x1800032b3  sbb     rdx, rdx
0x1800032b6  add     rcx, 18h; this
0x1800032ba  and     rdx, rax; struct MULTI_WORK_DISPATCH *
0x1800032bd  call    ?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z; MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)
0x1800032c2  mov     esi, eax
0x1800032c4  jmp     short loc_1800032DD
0x1800032c6  lea     rdx, aMachine; "MACHINE"
0x1800032cd  mov     rcx, rbp; String1
0x1800032d0  call    cs:__imp__wcsicmp
0x1800032d6  test    eax, eax
0x1800032d8  jnz     short loc_1800032DD
0x1800032da  xchg    edi, [rbx+78h]
0x1800032dd  mov     eax, esi
0x1800032df  add     rsp, 28h
0x1800032e3  pop     rdi
0x1800032e4  pop     rsi
0x1800032e5  pop     rbp
0x1800032e6  pop     rbx
0x1800032e7  retn
```
