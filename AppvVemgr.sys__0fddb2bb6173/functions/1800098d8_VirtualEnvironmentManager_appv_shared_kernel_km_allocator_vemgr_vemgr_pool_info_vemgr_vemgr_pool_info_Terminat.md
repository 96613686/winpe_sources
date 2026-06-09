# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::TerminateProcesses(appv::shared::kernel::doubly_linked_list<ulong,vemgr::vemgr_pool_info> const &,wchar_t const *,wchar_t const *,ulong)

- ea: `0x1800098d8`
- end: `0x1800099ae`
- name: `?TerminateProcesses@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$doubly_linked_list@KUvemgr_pool_info@vemgr@@@kernel@shared@appv@@PEB_W1K@Z`
- size: `214`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800099b4`
- `0x180015978`

## callees

- `0x1800098d8`
- `0x18000e534`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!ZwTerminateProcess` at `0x18000993e`
- `ntoskrnl!ZwTerminateProcess` at `0x18000993e`
- `ntoskrnl!ZwClose` at `0x180009954`
- `ntoskrnl!ZwClose` at `0x180009954`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::TerminateProcesses(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  unsigned int *v5; // rbx
  int *v6; // r14
  unsigned int v9; // esi
  unsigned int v10; // eax
  int v11; // eax
  HANDLE v12; // rdi
  NTSTATUS v13; // ebp
  __int64 v15; // [rsp+28h] [rbp-40h]
  __int64 v16; // [rsp+30h] [rbp-38h]
  HANDLE ProcessHandle; // [rsp+70h] [rbp+8h] BYREF

  ProcessHandle = a1;
  v5 = *(unsigned int **)(a2 + 24);
  v6 = (int *)(a2 + 8);
  v9 = 0;
  while ( v5 != (unsigned int *)v6 )
  {
    v10 = *v5;
    if ( *v5 == a5 )
      goto LABEL_11;
    ProcessHandle = 0;
    v11 = appv::shared::kernel::open_process_handle(&ProcessHandle, v10);
    if ( v11 < 0 )
    {
      v9 = v11;
LABEL_10:
      LODWORD(v16) = v9;
      LODWORD(v15) = *v5;
      LogWrite(
        1,
        0,
        L"VirtualEnvironmentManager::TerminateProcesses() - ZwTerminateProcess failed. Package %s, user %s, pid %d, error %d",
        a3,
        a4,
        v15,
        v16);
      goto LABEL_11;
    }
    v12 = ProcessHandle;
    v13 = ZwTerminateProcess(ProcessHandle, 0);
    if ( v12 )
      ZwClose(v12);
    if ( v13 < 0 )
    {
      v9 = v13;
      goto LABEL_10;
    }
LABEL_11:
    v5 = (unsigned int *)*((_QWORD *)v5 + 2);
  }
  return v9;
}

```

## disassembly

```asm
0x1800098d8  mov     [rsp+arg_8], rbx
0x1800098dd  mov     [rsp+arg_10], rbp
0x1800098e2  mov     [rsp+ProcessHandle], rcx
0x1800098e7  push    rsi
0x1800098e8  push    rdi
0x1800098e9  push    r12
0x1800098eb  push    r14
0x1800098ed  push    r15
0x1800098ef  sub     rsp, 40h
0x1800098f3  mov     rbx, [rdx+18h]
0x1800098f7  lea     r14, [rdx+8]
0x1800098fb  mov     r15, r9
0x1800098fe  mov     r12, r8
0x180009901  xor     esi, esi
0x180009903  cmp     rbx, r14
0x180009906  jz      loc_180009992
0x18000990c  mov     eax, [rbx]
0x18000990e  cmp     eax, [rsp+68h+arg_20]
0x180009915  jz      short loc_180009989
0x180009917  mov     edx, eax
0x180009919  mov     [rsp+68h+ProcessHandle], 0
0x180009922  lea     rcx, [rsp+68h+ProcessHandle]
0x180009927  call    appv__shared__kernel__open_process_handle
0x18000992c  test    eax, eax
0x18000992e  jns     short loc_180009934
0x180009930  mov     esi, eax
0x180009932  jmp     short loc_180009966
0x180009934  mov     rdi, [rsp+68h+ProcessHandle]
0x180009939  xor     edx, edx; ExitStatus
0x18000993b  mov     rcx, rdi; ProcessHandle
0x18000993e  call    cs:__imp_ZwTerminateProcess
0x180009945  nop     dword ptr [rax+rax+00h]
0x18000994a  mov     ebp, eax
0x18000994c  test    rdi, rdi
0x18000994f  jz      short loc_180009960
0x180009951  mov     rcx, rdi; Handle
0x180009954  call    cs:__imp_ZwClose
0x18000995b  nop     dword ptr [rax+rax+00h]
0x180009960  test    ebp, ebp
0x180009962  jns     short loc_180009989
0x180009964  mov     esi, ebp
0x180009966  mov     eax, [rbx]
0x180009968  lea     r8, aVirtualenviron_19; "VirtualEnvironmentManager::TerminatePro"...
0x18000996f  xor     edx, edx
0x180009971  mov     [rsp+68h+var_38], esi
0x180009975  mov     dword ptr [rsp+68h+var_40], eax
0x180009979  mov     r9, r12
0x18000997c  mov     [rsp+68h+var_48], r15
0x180009981  lea     ecx, [rdx+1]
0x180009984  call    LogWrite
0x180009989  mov     rbx, [rbx+10h]
0x18000998d  jmp     loc_180009903
0x180009992  lea     r11, [rsp+68h+var_28]
0x180009997  mov     eax, esi
0x180009999  mov     rbx, [r11+38h]
0x18000999d  mov     rbp, [r11+40h]
0x1800099a1  mov     rsp, r11
0x1800099a4  pop     r15
0x1800099a6  pop     r14
0x1800099a8  pop     r12
0x1800099aa  pop     rdi
0x1800099ab  pop     rsi
0x1800099ac  retn
```
