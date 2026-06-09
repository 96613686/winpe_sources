# CSebiDeletePublisherInstance(CBroker::SebPublisher *)

- ea: `0x180015b10`
- end: `0x180015bad`
- name: `?CSebiDeletePublisherInstance@@YAKPEAVSebPublisher@CBroker@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(struct CBroker::SebPublisher *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015aa0`
- `0x180020e20`

## callees

- `0x180014fec`
- `0x180015b10`
- `0x180016de0`
- `0x18001d9ac`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180015b22`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180015b22`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180015b91`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180015b91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015b28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015b28`

## pseudocode

```c
__int64 __fastcall CSebiDeletePublisherInstance(struct CBroker::SebPublisher *a1)
{
  struct CBroker::SebPublisher *v1; // rbx
  EventStateTable *v2; // rcx
  CBroker::SebRpcEventState *v3; // rax
  Broker::Win32Error *v5[2]; // [rsp+20h] [rbp-48h] BYREF
  char v6; // [rsp+30h] [rbp-38h]
  DWORD CurrentThreadId; // [rsp+34h] [rbp-34h]
  void **pExceptionObject; // [rsp+38h] [rbp-30h] BYREF
  __int128 v9; // [rsp+40h] [rbp-28h]
  int v10; // [rsp+50h] [rbp-18h]
  struct CBroker::SebPublisher *v11; // [rsp+70h] [rbp+8h]

  v1 = a1;
  v5[1] = a1;
  RtlAcquireSRWLockExclusive(a1);
  CurrentThreadId = GetCurrentThreadId();
  v6 = 1;
  if ( *((_BYTE *)v1 + 8) )
  {
    v3 = EventStateTable::Find(v2, *(struct _WNF_STATE_NAME *)((char *)v1 + 24));
    if ( !v3 )
    {
      try
      {
        v9 = 0;
        v10 = 7;
        pExceptionObject = &Broker::EventInternalError::`vftable';
        throw (Broker::EventInternalError *)&pExceptionObject;
      }
      catch ( std::bad_alloc )
      {
        v1 = v11;
        goto LABEL_4;
      }
      catch ( Broker::Win32Error *v5 )
      {
        v1 = v11;
        goto LABEL_4;
      }
      catch ( ... )
      {
        v1 = v11;
        goto LABEL_4;
      }
    }
    CBroker::SebRpcEventState::UpdateRefcount(v3, 0);
    *((_BYTE *)v1 + 8) = 0;
  }
LABEL_4:
  RtlReleaseSRWLockExclusive(v1);
  return 0;
}

```

## disassembly

```asm
0x180015b10  mov     [rsp+arg_0], rcx
0x180015b15  push    rbx
0x180015b16  sub     rsp, 60h
0x180015b1a  mov     rbx, rcx
0x180015b1d  mov     [rsp+68h+var_40], rcx
0x180015b22  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180015b28  call    cs:__imp_GetCurrentThreadId
0x180015b2e  mov     [rsp+68h+var_34], eax
0x180015b32  mov     [rsp+68h+var_38], 1
0x180015b37  cmp     byte ptr [rbx+8], 0
0x180015b3b  jz      short loc_180015B86
0x180015b3d  mov     rdx, [rbx+18h]; struct _WNF_STATE_NAME
0x180015b41  call    ?Find@EventStateTable@@QEAAPEAVSebRpcEventState@CBroker@@U_WNF_STATE_NAME@@@Z; EventStateTable::Find(_WNF_STATE_NAME)
0x180015b46  test    rax, rax
0x180015b49  jnz     short loc_180015B78
0x180015b4b  xorps   xmm0, xmm0
0x180015b4e  movups  [rsp+68h+var_28], xmm0
0x180015b53  mov     [rsp+68h+var_18], 7
0x180015b5b  lea     rax, ??_7EventInternalError@Broker@@6B@; const Broker::EventInternalError::`vftable'
0x180015b62  mov     [rsp+68h+pExceptionObject], rax
0x180015b67  lea     rdx, _TI3?AUEventInternalError@Broker@@; pThrowInfo
0x180015b6e  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180015b73  call    _CxxThrowException_0
0x180015b78  xor     edx, edx; unsigned __int8
0x180015b7a  mov     rcx, rax; this
0x180015b7d  call    ?UpdateRefcount@SebRpcEventState@CBroker@@QEAAKE@Z; CBroker::SebRpcEventState::UpdateRefcount(uchar)
0x180015b82  mov     byte ptr [rbx+8], 0
0x180015b86  mov     [rsp+68h+arg_8], 0
0x180015b8e  mov     rcx, rbx
0x180015b91  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180015b97  mov     eax, [rsp+68h+arg_8]
0x180015b9b  add     rsp, 60h
0x180015b9f  pop     rbx
0x180015ba0  retn
0x180015ba1  jmp     short loc_180015BA5
0x180015ba3  jmp     short $+2
0x180015ba5  mov     rbx, [rsp+68h+arg_0]
0x180015baa  jmp     short loc_180015B8E
```
