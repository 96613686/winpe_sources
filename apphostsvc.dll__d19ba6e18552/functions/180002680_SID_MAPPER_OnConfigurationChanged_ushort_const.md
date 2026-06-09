# SID_MAPPER::OnConfigurationChanged(ushort const *)

- ea: `0x180002680`
- end: `0x1800026da`
- name: `?OnConfigurationChanged@SID_MAPPER@@UEAAJPEBG@Z`
- size: `90`
- prototype: `__int64 __fastcall(SID_MAPPER *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callees

- `0x180002680`
- `0x180008464`

## pseudocode

```c
__int64 __fastcall SID_MAPPER::OnConfigurationChanged(SID_MAPPER *this, const unsigned __int16 *a2)
{
  unsigned int v4; // edx
  unsigned __int64 v5; // rax

  if ( *((_DWORD *)this + 48) == 1 )
    return 0;
  v4 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( v5 <= 0x17 )
    return (unsigned int)MULTI_WORK_QUEUE::GetAndQueueWorkItem(
                           (APP_HOST_SERVICE *)((char *)g_pAppHostService + 24),
                           (struct MULTI_WORK_DISPATCH *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
                           1);
  return v4;
}

```

## disassembly

```asm
0x180002680  sub     rsp, 28h
0x180002684  cmp     dword ptr [rcx+0C0h], 1
0x18000268b  mov     r8, rdx
0x18000268e  jnz     short loc_180002694
0x180002690  xor     eax, eax
0x180002692  jmp     short loc_1800026D5
0x180002694  xor     r9d, r9d
0x180002697  mov     edx, r9d
0x18000269a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000269e  inc     rax
0x1800026a1  cmp     [r8+rax*2], r9w
0x1800026a6  jnz     short loc_18000269E
0x1800026a8  cmp     rax, 17h
0x1800026ac  ja      short loc_1800026D3
0x1800026ae  lea     rax, [rcx+8]
0x1800026b2  mov     r8d, 1; unsigned __int64
0x1800026b8  neg     rcx
0x1800026bb  mov     rcx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x1800026c2  sbb     rdx, rdx
0x1800026c5  add     rcx, 18h; this
0x1800026c9  and     rdx, rax; struct MULTI_WORK_DISPATCH *
0x1800026cc  call    ?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z; MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)
0x1800026d1  mov     edx, eax
0x1800026d3  mov     eax, edx
0x1800026d5  add     rsp, 28h
0x1800026d9  retn
```
