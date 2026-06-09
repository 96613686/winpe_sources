# CBroker::SebPublisher::CreateEventsState(void)

- ea: `0x180020cd0`
- end: `0x180020d7b`
- name: `?CreateEventsState@SebPublisher@CBroker@@CAJXZ`
- size: `171`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020bac`

## callees

- `0x18001cf74`
- `0x180020cd0`
- `0x180020d84`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x180020d38`
- `ntdll!RtlInitializeSRWLock` at `0x180020d38`

## pseudocode

```c
__int64 CBroker::SebPublisher::CreateEventsState(void)
{
  unsigned int v0; // edx
  unsigned int i; // edi
  __int64 v2; // rax
  __int64 v3; // r14
  char *v4; // rsi
  __int64 v5; // rbx
  EventStateTable *v6; // rcx
  struct _WNF_STATE_NAME v7; // rdx

  v0 = 0;
  for ( i = 4096; i < 0x1043; ++i )
  {
    v2 = i - 4096;
    v3 = 5 * v2;
    if ( *((_DWORD *)&CBroker::EventPolicyTable + 10 * v2 + 4) == 1
      || *((_DWORD *)&CBroker::EventPolicyTable + 10 * v2 + 4) == 4 )
    {
      if ( *((_DWORD *)&CBroker::EventPolicyTable + 10 * v2) )
      {
        try
        {
          v4 = (char *)operator new(0x18u);
          v5 = *(__int64 *)((char *)&CBroker::EventPolicyTable + 8 * v3 + 4);
          v4[8] = 0;
          RtlInitializeSRWLock(v4);
          *(_QWORD *)(v4 + 12) = v5;
          v7 = *(struct _WNF_STATE_NAME *)((char *)&CBroker::EventPolicyTable + 8 * v3 + 4);
        }
        catch ( std::bad_alloc )
        {
          return 14;
        }
        catch ( ... )
        {
          return 1359;
        }
        v0 = EventStateTable::Insert(v6, v7, (struct CBroker::SebRpcEventState *)v4);
        if ( v0 )
          break;
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180020cd0  mov     [rsp+arg_8], rbx
0x180020cd5  mov     [rsp+arg_10], rsi
0x180020cda  push    rdi
0x180020cdb  push    r14
0x180020cdd  push    r15
0x180020cdf  sub     rsp, 20h
0x180020ce3  xor     edx, edx
0x180020ce5  mov     edi, 1000h
0x180020cea  cmp     edi, 1043h
0x180020cf0  jnb     short loc_180020D63
0x180020cf2  lea     eax, [rdi-1000h]
0x180020cf8  lea     r14, [rax+rax*4]
0x180020cfc  lea     r15, ?EventPolicyTable@CBroker@@3PAU_EventPolicy@1@A; CBroker::_EventPolicy near * CBroker::EventPolicyTable
0x180020d03  cmp     dword ptr [r15+r14*8+10h], 1
0x180020d09  jz      short loc_180020D13
0x180020d0b  cmp     dword ptr [r15+r14*8+10h], 4
0x180020d11  jnz     short loc_180020D5B
0x180020d13  cmp     dword ptr [r15+r14*8], 0
0x180020d18  jz      short loc_180020D5B
0x180020d1a  mov     ecx, 18h; Size
0x180020d1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020d24  mov     rsi, rax
0x180020d27  mov     rbx, [r15+r14*8+4]
0x180020d2c  mov     [rsp+38h+arg_0], rbx
0x180020d31  mov     byte ptr [rax+8], 0
0x180020d35  mov     rcx, rax
0x180020d38  call    cs:__imp_RtlInitializeSRWLock
0x180020d3e  mov     [rsi+0Ch], ebx
0x180020d41  mov     eax, dword ptr [rsp+38h+arg_0+4]
0x180020d45  mov     [rsi+10h], eax
0x180020d48  mov     r8, rsi; struct CBroker::SebRpcEventState *
0x180020d4b  mov     rdx, [r15+r14*8+4]; struct _WNF_STATE_NAME
0x180020d50  call    ?Insert@EventStateTable@@QEAAKU_WNF_STATE_NAME@@PEAVSebRpcEventState@CBroker@@@Z; EventStateTable::Insert(_WNF_STATE_NAME,CBroker::SebRpcEventState *)
0x180020d55  mov     edx, eax
0x180020d57  test    eax, eax
0x180020d59  jnz     short loc_180020D63
0x180020d5b  inc     edi
0x180020d5d  jmp     short loc_180020CEA
0x180020d5f  mov     edx, dword ptr [rsp+38h+arg_0]
0x180020d63  mov     eax, edx
0x180020d65  mov     rbx, [rsp+38h+arg_8]
0x180020d6a  mov     rsi, [rsp+38h+arg_10]
0x180020d6f  add     rsp, 20h
0x180020d73  pop     r15
0x180020d75  pop     r14
0x180020d77  pop     rdi
0x180020d78  retn
0x180020d79  jmp     short loc_180020D5F
```
