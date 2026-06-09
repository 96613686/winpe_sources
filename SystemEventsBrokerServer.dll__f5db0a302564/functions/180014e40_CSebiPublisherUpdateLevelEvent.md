# _CSebiPublisherUpdateLevelEvent

- ea: `0x180014e40`
- end: `0x180014fe3`
- name: `_CSebiPublisherUpdateLevelEvent`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180014e40`
- `0x180014fec`
- `0x18001cf50`
- `0x18001d9ac`
- `0x1800223e0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180014e91`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180014f0b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180014e91`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180014f0b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180014f91`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180014fbe`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180014f91`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180014fbe`
- `ntdll!RtlPublishWnfStateData` at `0x180014f7e`
- `ntdll!RtlPublishWnfStateData` at `0x180014f7e`
- `ntdll!RtlNtStatusToDosError` at `0x180014f86`
- `ntdll!RtlNtStatusToDosError` at `0x180014f86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014e97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014f11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014e97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014f11`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CSebiPublisherUpdateLevelEvent(__int64 a1, char a2, __int64 a3)
{
  EventStateTable *v6; // rcx
  struct CBroker::SebRpcEventState *v7; // rax
  struct CBroker::SebRpcEventState *v8; // rsi
  ULONG v9; // ebx
  unsigned __int8 v10; // dl
  NTSTATUS v11; // eax
  void **pExceptionObject; // [rsp+50h] [rbp-1068h] BYREF
  __int128 v14; // [rsp+58h] [rbp-1060h]
  int v15; // [rsp+68h] [rbp-1050h]
  int v16; // [rsp+70h] [rbp-1048h]
  _DWORD v17[1024]; // [rsp+80h] [rbp-1038h] BYREF

  if ( !a3 )
    return 87;
  if ( *(_QWORD *)(a3 + 16) != a1 )
    return 6;
  RtlAcquireSRWLockExclusive(a3);
  GetCurrentThreadId();
  if ( a2 )
  {
    if ( !*(_BYTE *)(a3 + 8) )
    {
LABEL_7:
      v7 = EventStateTable::Find(v6, *(struct _WNF_STATE_NAME *)(a3 + 24));
      v8 = v7;
      if ( !v7 )
      {
        v14 = 0;
        v15 = 1;
        pExceptionObject = &Broker::Win32Error::`vftable';
        v16 = 1168;
        throw (Broker::Win32Error *)&pExceptionObject;
      }
      RtlAcquireSRWLockExclusive(v7);
      GetCurrentThreadId();
      v10 = *((_BYTE *)v8 + 8) + 1;
      if ( !a2 )
        v10 = *((_BYTE *)v8 + 8) - 1;
      *((_BYTE *)v8 + 8) = v10;
      v17[1] = -1;
      if ( v10 <= 1u )
        v17[0] = v10 != 0 ? 3 : 1;
      else
        v17[0] = (v10 != 0 ? 3 : 1) | (v10 << 14);
      v11 = RtlPublishWnfStateData(*(_QWORD *)((char *)v8 + 12), 0, v17, 8, 0);
      v9 = RtlNtStatusToDosError(v11);
      RtlReleaseSRWLockExclusive(v8);
      if ( !v9 )
      {
        *(_BYTE *)(a3 + 8) = a2 != 0;
        v9 = 0;
      }
      goto LABEL_18;
    }
  }
  else if ( *(_BYTE *)(a3 + 8) )
  {
    goto LABEL_7;
  }
  v9 = 87;
LABEL_18:
  RtlReleaseSRWLockExclusive(a3);
  return v9;
}

```

## disassembly

```asm
0x180014e40  push    rbx
0x180014e42  push    rsi
0x180014e43  push    rdi
0x180014e44  push    r14
0x180014e46  mov     eax, 1098h
0x180014e4b  call    _alloca_probe
0x180014e50  sub     rsp, rax
0x180014e53  mov     rax, cs:__security_cookie
0x180014e5a  xor     rax, rsp
0x180014e5d  mov     [rsp+10B8h+var_38], rax
0x180014e65  mov     rdi, r8
0x180014e68  mov     r14b, dl
0x180014e6b  test    r8, r8
0x180014e6e  jnz     short loc_180014E79
0x180014e70  lea     eax, [r8+57h]
0x180014e74  jmp     loc_180014FC6
0x180014e79  cmp     [r8+10h], rcx
0x180014e7d  jz      short loc_180014E89
0x180014e7f  mov     eax, 6
0x180014e84  jmp     loc_180014FC6
0x180014e89  mov     [rsp+10B8h+var_1080], rdi
0x180014e8e  mov     rcx, rdi
0x180014e91  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180014e97  call    cs:__imp_GetCurrentThreadId
0x180014e9d  mov     [rsp+10B8h+var_1074], eax
0x180014ea1  mov     ebx, 1
0x180014ea6  mov     [rsp+10B8h+var_1078], bl
0x180014eaa  test    r14b, r14b
0x180014ead  jz      short loc_180014EF8
0x180014eaf  cmp     byte ptr [rdi+8], 0
0x180014eb3  jnz     short loc_180014EFE
0x180014eb5  mov     rdx, [rdi+18h]; struct _WNF_STATE_NAME
0x180014eb9  call    ?Find@EventStateTable@@QEAAPEAVSebRpcEventState@CBroker@@U_WNF_STATE_NAME@@@Z; EventStateTable::Find(_WNF_STATE_NAME)
0x180014ebe  mov     rsi, rax
0x180014ec1  test    rax, rax
0x180014ec4  jnz     short loc_180014F08
0x180014ec6  xorps   xmm0, xmm0
0x180014ec9  movups  [rsp+10B8h+var_1060], xmm0
0x180014ece  mov     [rsp+10B8h+var_1050], ebx
0x180014ed2  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180014ed9  mov     [rsp+10B8h+pExceptionObject], rax
0x180014ede  mov     [rsp+10B8h+var_1048], 490h
0x180014ee6  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180014eed  lea     rcx, [rsp+10B8h+pExceptionObject]; pExceptionObject
0x180014ef2  call    _CxxThrowException_0
0x180014ef8  cmp     byte ptr [rdi+8], 0
0x180014efc  jnz     short loc_180014EB5
0x180014efe  mov     ebx, 57h ; 'W'
0x180014f03  jmp     loc_180014FB2
0x180014f08  mov     rcx, rsi
0x180014f0b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180014f11  call    cs:__imp_GetCurrentThreadId
0x180014f17  mov     cl, [rsi+8]
0x180014f1a  mov     al, cl
0x180014f1c  sub     al, bl
0x180014f1e  add     cl, bl
0x180014f20  movzx   edx, cl
0x180014f23  movzx   eax, al
0x180014f26  test    r14b, r14b
0x180014f29  cmovz   edx, eax
0x180014f2c  mov     [rsi+8], dl
0x180014f2f  mov     al, dl
0x180014f31  neg     al
0x180014f33  sbb     ecx, ecx
0x180014f35  and     ecx, 2
0x180014f38  add     ecx, ebx
0x180014f3a  mov     [rsp+10B8h+var_1034], 0FFFFFFFFh
0x180014f45  cmp     dl, bl
0x180014f47  jbe     short loc_180014F5A
0x180014f49  movzx   eax, dl
0x180014f4c  shl     eax, 0Eh
0x180014f4f  or      eax, ecx
0x180014f51  mov     [rsp+10B8h+var_1038], eax
0x180014f58  jmp     short loc_180014F61
0x180014f5a  mov     [rsp+10B8h+var_1038], ecx
0x180014f61  mov     [rsp+10B8h+var_1098], 0
0x180014f6a  mov     r9d, 8
0x180014f70  lea     r8, [rsp+10B8h+var_1038]
0x180014f78  xor     edx, edx
0x180014f7a  mov     rcx, [rsi+0Ch]
0x180014f7e  call    cs:__imp_RtlPublishWnfStateData
0x180014f84  mov     ecx, eax; Status
0x180014f86  call    cs:__imp_RtlNtStatusToDosError
0x180014f8c  mov     ebx, eax
0x180014f8e  mov     rcx, rsi
0x180014f91  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180014f97  test    ebx, ebx
0x180014f99  jz      short loc_180014F9D
0x180014f9b  jmp     short loc_180014FB2
0x180014f9d  test    r14b, r14b
0x180014fa0  setnz   al
0x180014fa3  mov     [rdi+8], al
0x180014fa6  xor     ebx, ebx
0x180014fa8  jmp     short loc_180014FB2
0x180014faa  jmp     short loc_180014FAE
0x180014fac  jmp     short $+2
0x180014fae  mov     ebx, [rsp+10B8h+var_1088]
0x180014fb2  cmp     [rsp+10B8h+var_1078], 0
0x180014fb7  jz      short loc_180014FC4
0x180014fb9  mov     rcx, [rsp+10B8h+var_1080]
0x180014fbe  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180014fc4  mov     eax, ebx
0x180014fc6  mov     rcx, [rsp+10B8h+var_38]
0x180014fce  xor     rcx, rsp; StackCookie
0x180014fd1  call    __security_check_cookie
0x180014fd6  add     rsp, 1098h
0x180014fdd  pop     r14
0x180014fdf  pop     rdi
0x180014fe0  pop     rsi
0x180014fe1  pop     rbx
0x180014fe2  retn
```
