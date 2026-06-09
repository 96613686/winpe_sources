# CBroker::SebEvent::GetBIEventFlag(void)

- ea: `0x18000fb50`
- end: `0x18000fc09`
- name: `?GetBIEventFlag@SebEvent@CBroker@@QEAAKXZ`
- size: `185`
- prototype: `__int64 __fastcall(CBroker::SebEvent *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f680`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000fb69`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000fb69`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000fbf1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000fbf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb6f`

## pseudocode

```c
__int64 __fastcall CBroker::SebEvent::GetBIEventFlag(CBroker::SebEvent *this)
{
  __int64 v2; // rdx
  int v3; // ecx
  int v4; // eax
  int v5; // ebx
  unsigned int v6; // ebx
  int v7; // edx

  RtlAcquireSRWLockExclusive((char *)this + 240);
  GetCurrentThreadId();
  v2 = 40 * (*((int *)this + 24) - 4096LL);
  v3 = ((*(_DWORD *)((_BYTE *)&CBroker::EventPolicyTable + v2 + 20) & 1) << 11) | 0x400;
  if ( *(_DWORD *)((char *)&CBroker::EventPolicyTable + v2 + 12) )
    v3 = (*(_DWORD *)((_BYTE *)&CBroker::EventPolicyTable + v2 + 20) & 1) << 11;
  v4 = v3 | 0x10000000;
  if ( !*((_DWORD *)this + 54) )
    v4 = v3;
  v5 = v4 | 0x8000000;
  if ( !*((_DWORD *)this + 55) )
    v5 = v4;
  v6 = *(_DWORD *)((char *)&CBroker::EventPolicyTable + v2 + 24) | v5;
  v7 = *((_DWORD *)this + 53);
  if ( v7 )
    v6 = v7 | v6 & 0xFFFF7F1F;
  RtlReleaseSRWLockExclusive((char *)this + 240);
  return v6;
}

```

## disassembly

```asm
0x18000fb50  mov     [rsp+arg_0], rbx
0x18000fb55  mov     [rsp+arg_8], rsi
0x18000fb5a  push    rdi
0x18000fb5b  sub     rsp, 20h
0x18000fb5f  mov     rdi, rcx
0x18000fb62  add     rcx, 0F0h
0x18000fb69  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000fb6f  call    cs:__imp_GetCurrentThreadId
0x18000fb75  movsxd  rax, dword ptr [rdi+60h]
0x18000fb79  lea     r8, ?EventPolicyTable@CBroker@@3PAU_EventPolicy@1@A; CBroker::_EventPolicy near * CBroker::EventPolicyTable
0x18000fb80  sub     rax, 1000h
0x18000fb86  lea     rax, [rax+rax*4]
0x18000fb8a  lea     rdx, ds:0[rax*8]
0x18000fb92  mov     eax, [rdx+r8+14h]
0x18000fb97  and     eax, 1
0x18000fb9a  shl     eax, 0Bh
0x18000fb9d  mov     ecx, eax
0x18000fb9f  bts     ecx, 0Ah
0x18000fba3  cmp     dword ptr [rdx+r8+0Ch], 0
0x18000fba9  cmovnz  ecx, eax
0x18000fbac  mov     eax, ecx
0x18000fbae  bts     eax, 1Ch
0x18000fbb2  cmp     dword ptr [rdi+0D8h], 0
0x18000fbb9  cmovz   eax, ecx
0x18000fbbc  lea     rcx, [rdi+0F0h]
0x18000fbc3  mov     ebx, eax
0x18000fbc5  bts     ebx, 1Bh
0x18000fbc9  cmp     dword ptr [rdi+0DCh], 0
0x18000fbd0  cmovz   ebx, eax
0x18000fbd3  or      ebx, [rdx+r8+18h]
0x18000fbd8  mov     edx, [rdi+0D4h]
0x18000fbde  mov     r8d, ebx
0x18000fbe1  and     r8d, 0FFFF7F1Fh
0x18000fbe8  or      r8d, edx
0x18000fbeb  test    edx, edx
0x18000fbed  cmovnz  ebx, r8d
0x18000fbf1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000fbf7  mov     rsi, [rsp+28h+arg_8]
0x18000fbfc  mov     eax, ebx
0x18000fbfe  mov     rbx, [rsp+28h+arg_0]
0x18000fc03  add     rsp, 20h
0x18000fc07  pop     rdi
0x18000fc08  retn
```
