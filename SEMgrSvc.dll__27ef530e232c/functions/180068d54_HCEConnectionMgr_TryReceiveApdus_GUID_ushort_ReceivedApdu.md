# HCEConnectionMgr::TryReceiveApdus(_GUID *,ushort *,_ReceivedApdu * *)

- ea: `0x180068d54`
- end: `0x180068f1b`
- name: `?TryReceiveApdus@HCEConnectionMgr@@QEAAJPEAU_GUID@@PEAGPEAPEAU_ReceivedApdu@@@Z`
- size: `455`
- prototype: `__int64 __fastcall(HCEConnectionMgr *__hidden this, struct _GUID *, unsigned __int16 *, struct _ReceivedApdu **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180067254`

## callees

- `0x1800049c4`
- `0x180068d54`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068e9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068e9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068e13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068e13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068f02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068f02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068d7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068d7d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180068ee9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180068ee9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HCEConnectionMgr::TryReceiveApdus(
        HCEConnectionMgr *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        struct _ReceivedApdu **a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // r13
  int v9; // edi
  __int64 ***v10; // rax
  __int64 **i; // rbx
  __int64 v12; // r15
  struct _ReceivedApdu *v13; // r14
  unsigned __int16 v14; // r9
  __int64 **v15; // rcx
  __int64 *j; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 *v19; // rcx
  _QWORD *v20; // rsi
  _QWORD *v21; // r13
  void *v22; // rcx
  __int64 *v23; // rcx
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+20h] [rbp-58h]

  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  v25 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( a2 && a3 && a4 )
  {
    *a3 = 0;
    *a4 = 0;
    if ( *((_BYTE *)this + 128) )
    {
      v10 = (__int64 ***)*((_QWORD *)this + 14);
      for ( i = *v10; ; i = (__int64 **)*i )
      {
        if ( i == (__int64 **)v10 )
        {
          v9 = -2134834683;
          goto LABEL_27;
        }
        if ( i[3] == *(__int64 **)&a2->Data1 && i[4] == *(__int64 **)a2->Data4 )
          break;
      }
      v9 = (*(__int64 (__fastcall **)(HCEConnectionMgr *, __int64 *))(*(_QWORD *)this + 16LL))(this, (__int64 *)i + 11);
      if ( v9 >= 0 )
      {
        v12 = *((unsigned __int16 *)i + 116);
        v13 = (struct _ReceivedApdu *)CoTaskMemAlloc(24 * v12);
        if ( v13 )
        {
          v14 = 0;
          v15 = (__int64 **)i[28];
          for ( j = *v15; j != (__int64 *)v15; j = (__int64 *)*j )
          {
            v17 = 3LL * v14;
            *((_BYTE *)v13 + 8 * v17) = *((_BYTE *)j + 16);
            *((_DWORD *)v13 + 2 * v17 + 1) = *((_DWORD *)j + 5);
            *((_DWORD *)v13 + 2 * v17 + 2) = *((unsigned __int16 *)j + 12);
            v18 = j[4];
            j[4] = 0;
            *((_QWORD *)v13 + v17 + 2) = v18;
            ++v14;
          }
          v19 = i[28];
          *(_QWORD *)v19[1] = 0;
          v20 = (_QWORD *)*v19;
          if ( *v19 )
          {
            do
            {
              v21 = (_QWORD *)*v20;
              v22 = (void *)v20[4];
              if ( v22 )
                CoTaskMemFree(v22);
              operator delete(v20);
              v20 = v21;
            }
            while ( v21 );
            v8 = v25;
          }
          *i[28] = (__int64)i[28];
          i[28][1] = (__int64)i[28];
          i[29] = 0;
          v23 = i[31];
          if ( v23 )
            SetEvent(v23);
          *a3 = v12;
          *a4 = v13;
        }
        else
        {
          v9 = -2147024882;
        }
      }
    }
    else
    {
      v9 = -2147019873;
    }
  }
  else
  {
    v9 = -2147467261;
  }
LABEL_27:
  LeaveCriticalSection(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180068d54  push    rbx
0x180068d56  push    rbp
0x180068d57  push    rsi
0x180068d58  push    rdi
0x180068d59  push    r12
0x180068d5b  push    r13
0x180068d5d  push    r14
0x180068d5f  push    r15
0x180068d61  sub     rsp, 38h
0x180068d65  mov     rbp, r9
0x180068d68  mov     r12, r8
0x180068d6b  mov     rsi, rdx
0x180068d6e  mov     rdi, rcx
0x180068d71  lea     r13, [rcx+30h]
0x180068d75  mov     [rsp+78h+var_58], r13
0x180068d7a  mov     rcx, r13; lpCriticalSection
0x180068d7d  call    cs:__imp_EnterCriticalSection
0x180068d83  mov     [rsp+78h+var_50], 1
0x180068d88  test    rsi, rsi
0x180068d8b  jnz     short loc_180068D97
0x180068d8d  mov     edi, 80004003h
0x180068d92  jmp     loc_180068EFF
0x180068d97  test    r12, r12
0x180068d9a  jz      short loc_180068D8D
0x180068d9c  test    rbp, rbp
0x180068d9f  jz      short loc_180068D8D
0x180068da1  xor     eax, eax
0x180068da3  mov     [r12], ax
0x180068da8  mov     [rbp+0], rax
0x180068dac  cmp     [rdi+80h], al
0x180068db2  jnz     short loc_180068DBE
0x180068db4  mov     edi, 8007139Fh
0x180068db9  jmp     loc_180068EFF
0x180068dbe  mov     rax, [rdi+70h]
0x180068dc2  mov     rbx, [rax]
0x180068dc5  cmp     rbx, rax
0x180068dc8  jz      loc_180068EFA
0x180068dce  mov     rcx, [rbx+18h]
0x180068dd2  cmp     rcx, [rsi]
0x180068dd5  jnz     short loc_180068DE1
0x180068dd7  mov     rcx, [rbx+20h]
0x180068ddb  cmp     rcx, [rsi+8]
0x180068ddf  jz      short loc_180068DE6
0x180068de1  mov     rbx, [rbx]
0x180068de4  jmp     short loc_180068DC5
0x180068de6  mov     rax, [rdi]
0x180068de9  lea     rdx, [rbx+58h]
0x180068ded  mov     rcx, rdi
0x180068df0  mov     rax, [rax+10h]
0x180068df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068df9  mov     edi, eax
0x180068dfb  test    eax, eax
0x180068dfd  js      loc_180068EFF
0x180068e03  movzx   r15d, word ptr [rbx+0E8h]
0x180068e0b  lea     rcx, [r15+r15*2]
0x180068e0f  shl     rcx, 3; cb
0x180068e13  call    cs:__imp_CoTaskMemAlloc
0x180068e19  mov     r14, rax
0x180068e1c  test    rax, rax
0x180068e1f  jnz     short loc_180068E2B
0x180068e21  mov     edi, 8007000Eh
0x180068e26  jmp     loc_180068EFF
0x180068e2b  xor     r9d, r9d
0x180068e2e  mov     rcx, [rbx+0E0h]
0x180068e35  mov     rax, [rcx]
0x180068e38  cmp     rax, rcx
0x180068e3b  jz      short loc_180068E77
0x180068e3d  movzx   edx, r9w
0x180068e41  lea     r8, [rdx+rdx*2]
0x180068e45  mov     dl, [rax+10h]
0x180068e48  mov     [r14+r8*8], dl
0x180068e4c  mov     edx, [rax+14h]
0x180068e4f  mov     [r14+r8*8+4], edx
0x180068e54  movzx   edx, word ptr [rax+18h]
0x180068e58  mov     [r14+r8*8+8], edx
0x180068e5d  mov     rdx, [rax+20h]
0x180068e61  mov     qword ptr [rax+20h], 0
0x180068e69  mov     [r14+r8*8+10h], rdx
0x180068e6e  inc     r9w
0x180068e72  mov     rax, [rax]
0x180068e75  jmp     short loc_180068E38
0x180068e77  mov     rcx, [rbx+0E0h]
0x180068e7e  mov     rax, [rcx+8]
0x180068e82  mov     qword ptr [rax], 0
0x180068e89  mov     rsi, [rcx]
0x180068e8c  test    rsi, rsi
0x180068e8f  jz      short loc_180068EBD
0x180068e91  mov     r13, [rsi]
0x180068e94  mov     rcx, [rsi+20h]; pv
0x180068e98  test    rcx, rcx
0x180068e9b  jz      short loc_180068EA3
0x180068e9d  call    cs:__imp_CoTaskMemFree
0x180068ea3  mov     edx, 28h ; '('
0x180068ea8  mov     rcx, rsi; Block
0x180068eab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068eb0  mov     rsi, r13
0x180068eb3  test    r13, r13
0x180068eb6  jnz     short loc_180068E91
0x180068eb8  mov     r13, [rsp+78h+var_58]
0x180068ebd  mov     rax, [rbx+0E0h]
0x180068ec4  mov     [rax], rax
0x180068ec7  mov     rax, [rbx+0E0h]
0x180068ece  mov     [rax+8], rax
0x180068ed2  mov     qword ptr [rbx+0E8h], 0
0x180068edd  mov     rcx, [rbx+0F8h]; hEvent
0x180068ee4  test    rcx, rcx
0x180068ee7  jz      short loc_180068EEF
0x180068ee9  call    cs:__imp_SetEvent
0x180068eef  mov     [r12], r15w
0x180068ef4  mov     [rbp+0], r14
0x180068ef8  jmp     short loc_180068EFF
0x180068efa  mov     edi, 80C10205h
0x180068eff  mov     rcx, r13; lpCriticalSection
0x180068f02  call    cs:__imp_LeaveCriticalSection
0x180068f08  mov     eax, edi
0x180068f0a  add     rsp, 38h
0x180068f0e  pop     r15
0x180068f10  pop     r14
0x180068f12  pop     r13
0x180068f14  pop     r12
0x180068f16  pop     rdi
0x180068f17  pop     rsi
0x180068f18  pop     rbp
0x180068f19  pop     rbx
0x180068f1a  retn
```
