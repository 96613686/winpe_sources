# Broker::SebBroker::GetSessionStateName(ulong,void * const,_SebiEventType,_WNF_STATE_NAME *)

- ea: `0x180005cc0`
- end: `0x180005f1e`
- name: `?GetSessionStateName@SebBroker@Broker@@QEAAXKQEAXW4_SebiEventType@@PEAU_WNF_STATE_NAME@@@Z`
- size: `606`
- prototype: `void __fastcall(__int64, int, void *, int, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006360`

## callees

- `0x180005cc0`
- `0x180006d90`
- `0x1800076a0`
- `0x180013920`
- `0x180027010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180005d95`
- `ntdll!RtlEqualSid` at `0x180005d95`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005cf1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005cf1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005f00`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005f00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cf7`

## pseudocode

```c
void __fastcall Broker::SebBroker::GetSessionStateName(__int64 a1, int a2, void *a3, int a4, _QWORD *a5)
{
  DWORD CurrentThreadId; // eax
  __int64 **v7; // rbx
  PSID v8; // r12
  std::_Ref_count_base *v9; // r14
  __int64 *v10; // rbx
  _DWORD *v11; // r15
  _QWORD *v12; // rax
  __int64 v13; // rcx
  _DWORD *v14; // rsi
  volatile signed __int32 *v15; // rdi
  std::_Ref_count_base *v16; // rcx
  __int64 **v17; // rax
  __int64 *i; // rax
  __int64 *j; // rax
  _QWORD *v20; // r13
  int v21; // eax
  __int64 v22; // [rsp+20h] [rbp-58h] BYREF
  char v23; // [rsp+28h] [rbp-50h]
  DWORD v24; // [rsp+2Ch] [rbp-4Ch]
  std::_Ref_count_base *v25[2]; // [rsp+30h] [rbp-48h]
  PSID Sid2; // [rsp+90h] [rbp+18h] BYREF
  int v28; // [rsp+98h] [rbp+20h]

  v28 = a4;
  Sid2 = a3;
  v22 = a1 + 8;
  RtlAcquireSRWLockExclusive(a1 + 8);
  CurrentThreadId = GetCurrentThreadId();
  v7 = *(__int64 ***)(a1 + 16);
  v8 = Sid2;
  *(_OWORD *)v25 = 0;
  v9 = 0;
  v10 = *v7;
  v11 = 0;
  v24 = CurrentThreadId;
  *a5 = 0;
  v23 = 1;
  while ( v10 != *(__int64 **)(a1 + 16) )
  {
    v12 = **(_QWORD ***)v10[5];
    Sid2 = v12;
    while ( v12 != *(_QWORD **)v10[5] )
    {
      if ( v12[5] )
      {
        v13 = v12[6];
        if ( v13 )
          _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
        v14 = (_DWORD *)v12[5];
        v15 = (volatile signed __int32 *)v12[6];
        if ( v14[10] == a2 && RtlEqualSid(*(PSID *)v14, v8) )
        {
          if ( v15 )
            _InterlockedIncrement(v15 + 2);
          v16 = v9;
          v11 = v14;
          v9 = (std::_Ref_count_base *)v15;
          if ( v16 )
            std::_Ref_count_base::_Decref(v16);
        }
        if ( v15 && _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++((__int64 *)&Sid2);
      v12 = Sid2;
    }
    v17 = (__int64 **)v10[2];
    if ( *((_BYTE *)v17 + 25) )
    {
      for ( i = (__int64 *)v10[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
      {
        if ( v10 != (__int64 *)i[2] )
          break;
        v10 = i;
      }
      v10 = i;
    }
    else
    {
      v10 = (__int64 *)v10[2];
      for ( j = *v17; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v10 = j;
    }
  }
  v20 = a5;
  if ( !v11 )
  {
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)&v22);
    return;
  }
  switch ( v28 )
  {
    case 11:
      *(_DWORD *)a5 = v11[16];
      v21 = v11[17];
      goto LABEL_39;
    case 0:
      *(_DWORD *)a5 = v11[18];
      v21 = v11[19];
      goto LABEL_39;
    case 1:
      *(_DWORD *)a5 = v11[20];
      v21 = v11[21];
      goto LABEL_39;
    case 23:
      *(_DWORD *)a5 = v11[14];
      v21 = v11[15];
LABEL_39:
      *((_DWORD *)v20 + 1) = v21;
      break;
  }
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  RtlReleaseSRWLockExclusive(v22);
}

```

## disassembly

```asm
0x180005cc0  mov     [rsp+arg_0], rbx
0x180005cc5  mov     [rsp+arg_18], r9d
0x180005cca  mov     [rsp+Sid2], r8
0x180005ccf  mov     [rsp+arg_8], edx
0x180005cd3  push    rbp
0x180005cd4  push    rsi
0x180005cd5  push    rdi
0x180005cd6  push    r12
0x180005cd8  push    r13
0x180005cda  push    r14
0x180005cdc  push    r15
0x180005cde  sub     rsp, 40h
0x180005ce2  lea     rdi, [rcx+8]
0x180005ce6  mov     rbp, rcx
0x180005ce9  mov     rcx, rdi
0x180005cec  mov     [rsp+78h+var_58], rdi
0x180005cf1  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180005cf7  call    cs:__imp_GetCurrentThreadId
0x180005cfd  mov     r13, [rsp+78h+arg_20]
0x180005d05  xorps   xmm0, xmm0
0x180005d08  mov     rbx, [rbp+10h]
0x180005d0c  mov     r12, [rsp+78h+Sid2]
0x180005d14  movdqu  xmmword ptr [rsp+78h+var_48], xmm0
0x180005d1a  mov     r14, [rsp+78h+var_48+8]
0x180005d1f  mov     rbx, [rbx]
0x180005d22  mov     r15, [rsp+78h+var_48]
0x180005d27  mov     [rsp+78h+var_4C], eax
0x180005d2b  xor     eax, eax
0x180005d2d  mov     [r13+0], rax
0x180005d31  mov     r13d, [rsp+78h+arg_8]
0x180005d39  mov     [rsp+78h+var_50], 1
0x180005d3e  xchg    ax, ax
0x180005d40  cmp     rbx, [rbp+10h]
0x180005d44  jz      loc_180005E6F
0x180005d4a  mov     rax, [rbx+28h]
0x180005d4e  mov     rax, [rax]
0x180005d51  mov     rax, [rax]
0x180005d54  mov     [rsp+78h+Sid2], rax
0x180005d5c  mov     rcx, [rbx+28h]
0x180005d60  cmp     rax, [rcx]
0x180005d63  jz      loc_180005E15
0x180005d69  cmp     qword ptr [rax+28h], 0
0x180005d6e  jz      loc_180005DFB
0x180005d74  mov     rcx, [rax+30h]
0x180005d78  test    rcx, rcx
0x180005d7b  jz      short loc_180005D81
0x180005d7d  lock inc dword ptr [rcx+8]
0x180005d81  mov     rsi, [rax+28h]
0x180005d85  mov     rdi, [rax+30h]
0x180005d89  cmp     [rsi+28h], r13d
0x180005d8d  jnz     short loc_180005DBB
0x180005d8f  mov     rcx, [rsi]; Sid1
0x180005d92  mov     rdx, r12; Sid2
0x180005d95  call    cs:__imp_RtlEqualSid
0x180005d9b  test    al, al
0x180005d9d  jz      short loc_180005DBB
0x180005d9f  test    rdi, rdi
0x180005da2  jz      short loc_180005DA8
0x180005da4  lock inc dword ptr [rdi+8]
0x180005da8  mov     rcx, r14; this
0x180005dab  mov     r15, rsi
0x180005dae  mov     r14, rdi
0x180005db1  test    rcx, rcx
0x180005db4  jz      short loc_180005DBB
0x180005db6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180005dbb  test    rdi, rdi
0x180005dbe  jz      short loc_180005DFB
0x180005dc0  mov     eax, 0FFFFFFFFh
0x180005dc5  lock xadd [rdi+8], eax
0x180005dca  cmp     eax, 1
0x180005dcd  jnz     short loc_180005DFB
0x180005dcf  mov     rax, [rdi]
0x180005dd2  mov     rcx, rdi
0x180005dd5  mov     rax, [rax]
0x180005dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ddd  mov     eax, 0FFFFFFFFh
0x180005de2  lock xadd [rdi+0Ch], eax
0x180005de7  cmp     eax, 1
0x180005dea  jnz     short loc_180005DFB
0x180005dec  mov     rax, [rdi]
0x180005def  mov     rcx, rdi
0x180005df2  mov     rax, [rax+8]
0x180005df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dfb  lea     rcx, [rsp+78h+Sid2]
0x180005e03  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(void)
0x180005e08  mov     rax, [rsp+78h+Sid2]
0x180005e10  jmp     loc_180005D5C
0x180005e15  mov     rax, [rbx+10h]
0x180005e19  cmp     byte ptr [rax+19h], 0
0x180005e1d  jz      short loc_180005E4B
0x180005e1f  mov     rax, [rbx+8]
0x180005e23  cmp     byte ptr [rax+19h], 0
0x180005e27  jnz     short loc_180005E43
0x180005e29  nop     dword ptr [rax+00000000h]
0x180005e30  cmp     rbx, [rax+10h]
0x180005e34  jnz     short loc_180005E43
0x180005e36  mov     rbx, rax
0x180005e39  mov     rax, [rax+8]
0x180005e3d  cmp     byte ptr [rax+19h], 0
0x180005e41  jz      short loc_180005E30
0x180005e43  mov     rbx, rax
0x180005e46  jmp     loc_180005D40
0x180005e4b  mov     rbx, rax
0x180005e4e  mov     rax, [rax]
0x180005e51  cmp     byte ptr [rax+19h], 0
0x180005e55  jnz     loc_180005D40
0x180005e5b  mov     rcx, [rax]
0x180005e5e  mov     rbx, rax
0x180005e61  mov     rax, rcx
0x180005e64  cmp     byte ptr [rcx+19h], 0
0x180005e68  jz      short loc_180005E5B
0x180005e6a  jmp     loc_180005D40
0x180005e6f  mov     r12d, [rsp+78h+arg_18]
0x180005e77  mov     r13, [rsp+78h+arg_20]
0x180005e7f  test    r15, r15
0x180005e82  jnz     short loc_180005E9D
0x180005e84  test    r14, r14
0x180005e87  jz      short loc_180005E91
0x180005e89  mov     rcx, r14; this
0x180005e8c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180005e91  lea     rcx, [rsp+78h+var_58]; this
0x180005e96  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x180005e9b  jmp     short loc_180005F06
0x180005e9d  cmp     r12d, 0Bh
0x180005ea1  jz      short loc_180005EDE
0x180005ea3  test    r12d, r12d
0x180005ea6  jz      short loc_180005ED0
0x180005ea8  sub     r12d, 1
0x180005eac  jz      short loc_180005EC2
0x180005eae  cmp     r12d, 16h
0x180005eb2  jnz     short loc_180005EEE
0x180005eb4  mov     eax, [r15+38h]
0x180005eb8  mov     [r13+0], eax
0x180005ebc  mov     eax, [r15+3Ch]
0x180005ec0  jmp     short loc_180005EEA
0x180005ec2  mov     eax, [r15+50h]
0x180005ec6  mov     [r13+0], eax
0x180005eca  mov     eax, [r15+54h]
0x180005ece  jmp     short loc_180005EEA
0x180005ed0  mov     eax, [r15+48h]
0x180005ed4  mov     [r13+0], eax
0x180005ed8  mov     eax, [r15+4Ch]
0x180005edc  jmp     short loc_180005EEA
0x180005ede  mov     eax, [r15+40h]
0x180005ee2  mov     [r13+0], eax
0x180005ee6  mov     eax, [r15+44h]
0x180005eea  mov     [r13+4], eax
0x180005eee  test    r14, r14
0x180005ef1  jz      short loc_180005EFB
0x180005ef3  mov     rcx, r14; this
0x180005ef6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180005efb  mov     rcx, [rsp+78h+var_58]
0x180005f00  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180005f06  mov     rbx, [rsp+78h+arg_0]
0x180005f0e  add     rsp, 40h
0x180005f12  pop     r15
0x180005f14  pop     r14
0x180005f16  pop     r13
0x180005f18  pop     r12
0x180005f1a  pop     rdi
0x180005f1b  pop     rsi
0x180005f1c  pop     rbp
0x180005f1d  retn
```
