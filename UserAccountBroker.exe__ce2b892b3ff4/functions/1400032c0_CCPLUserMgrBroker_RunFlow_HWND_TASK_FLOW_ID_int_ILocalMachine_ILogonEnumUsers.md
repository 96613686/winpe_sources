# CCPLUserMgrBroker::RunFlow(HWND__ *,TASK_FLOW_ID,int,ILocalMachine *,ILogonEnumUsers *)

- ea: `0x1400032c0`
- end: `0x1400033e3`
- name: `?RunFlow@CCPLUserMgrBroker@@UEAAJPEAUHWND__@@W4TASK_FLOW_ID@@HPEAUILocalMachine@@PEAUILogonEnumUsers@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400032c0`
- `0x14000384c`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall CCPLUserMgrBroker::RunFlow(__int64 a1, __int64 a2, int a3, int a4, __int64 a5, __int64 a6)
{
  _DWORD *v6; // rdi
  __int64 result; // rax

  v6 = (_DWORD *)(a1 + 136);
  *(_QWORD *)(a1 + 88) = a2;
  *(_DWORD *)(a1 + 96) = a3;
  result = 0;
  *(_DWORD *)(a1 + 104) = -2147023728;
  *(_DWORD *)(a1 + 100) = a4;
  if ( *(_DWORD *)(a1 + 136) )
  {
    result = *(unsigned int *)(a1 + 140);
    if ( (int)result >= 0 )
      result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_14000C868 + 32LL))(qword_14000C868);
  }
  *v6 = 0;
  if ( (int)result >= 0 )
  {
    if ( !a5
      || (result = *(unsigned int *)(a1 + 140), (int)result >= 0)
      && (result = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, _DWORD *))(*(_QWORD *)qword_14000C868 + 24LL))(
                     qword_14000C868,
                     a5,
                     &GUID_e93cf64b_c14d_4a1a_9572_adab3c2e9461,
                     v6),
          (int)result >= 0) )
    {
      result = 0;
      if ( *(_DWORD *)(a1 + 152) )
      {
        result = *(unsigned int *)(a1 + 156);
        if ( (int)result >= 0 )
          result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_14000C868 + 32LL))(qword_14000C868);
      }
      *(_DWORD *)(a1 + 152) = 0;
      if ( (int)result >= 0 )
      {
        if ( !a6
          || (result = *(unsigned int *)(a1 + 156), (int)result >= 0)
          && (result = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64))(*(_QWORD *)qword_14000C868 + 24LL))(
                         qword_14000C868,
                         a6,
                         &GUID_3ee328ab_8f69_420a_9b86_7080f22af38b,
                         a1 + 152),
              (int)result >= 0) )
        {
          result = CCPLUserMgrBroker::_StartThreadWait((PVOID)a1, (WCHAR)CCPLUserMgrBroker::s_RunFlowASTA);
          if ( (int)result >= 0 )
            return *(unsigned int *)(a1 + 104);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400032c0  mov     [rsp+arg_0], rbx
0x1400032c5  push    rdi
0x1400032c6  sub     rsp, 30h
0x1400032ca  lea     rdi, [rcx+88h]
0x1400032d1  mov     [rcx+58h], rdx
0x1400032d5  mov     [rcx+60h], r8d
0x1400032d9  xor     eax, eax
0x1400032db  mov     dword ptr [rcx+68h], 80070490h
0x1400032e2  mov     rbx, rcx
0x1400032e5  mov     [rcx+64h], r9d
0x1400032e9  mov     edx, [rdi]
0x1400032eb  test    edx, edx
0x1400032ed  jz      short loc_14000330C
0x1400032ef  mov     eax, [rcx+8Ch]
0x1400032f5  test    eax, eax
0x1400032f7  js      short loc_14000330C
0x1400032f9  mov     rcx, cs:qword_14000C868
0x140003300  mov     rax, [rcx]
0x140003303  mov     rax, [rax+20h]
0x140003307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000330c  mov     dword ptr [rdi], 0
0x140003312  test    eax, eax
0x140003314  js      loc_1400033D8
0x14000331a  mov     rdx, [rsp+38h+arg_20]
0x14000331f  test    rdx, rdx
0x140003322  jz      short loc_140003357
0x140003324  mov     eax, [rbx+8Ch]
0x14000332a  test    eax, eax
0x14000332c  js      loc_1400033D8
0x140003332  mov     rcx, cs:qword_14000C868
0x140003339  lea     r8, _GUID_e93cf64b_c14d_4a1a_9572_adab3c2e9461
0x140003340  mov     r9, rdi
0x140003343  mov     rax, [rcx]
0x140003346  mov     rax, [rax+18h]
0x14000334a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000334f  test    eax, eax
0x140003351  js      loc_1400033D8
0x140003357  lea     rdi, [rbx+98h]
0x14000335e  xor     eax, eax
0x140003360  mov     edx, [rdi]
0x140003362  test    edx, edx
0x140003364  jz      short loc_140003383
0x140003366  mov     eax, [rbx+9Ch]
0x14000336c  test    eax, eax
0x14000336e  js      short loc_140003383
0x140003370  mov     rcx, cs:qword_14000C868
0x140003377  mov     rax, [rcx]
0x14000337a  mov     rax, [rax+20h]
0x14000337e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003383  mov     dword ptr [rdi], 0
0x140003389  test    eax, eax
0x14000338b  js      short loc_1400033D8
0x14000338d  mov     rdx, [rsp+38h+arg_28]
0x140003392  test    rdx, rdx
0x140003395  jz      short loc_1400033C2
0x140003397  mov     eax, [rbx+9Ch]
0x14000339d  test    eax, eax
0x14000339f  js      short loc_1400033D8
0x1400033a1  mov     rcx, cs:qword_14000C868
0x1400033a8  lea     r8, _GUID_3ee328ab_8f69_420a_9b86_7080f22af38b
0x1400033af  mov     r9, rdi
0x1400033b2  mov     rax, [rcx]
0x1400033b5  mov     rax, [rax+18h]
0x1400033b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033be  test    eax, eax
0x1400033c0  js      short loc_1400033D8
0x1400033c2  lea     rdx, ?s_RunFlowASTA@CCPLUserMgrBroker@@CAKPEAX@Z; ch
0x1400033c9  mov     rcx, rbx; Context
0x1400033cc  call    ?_StartThreadWait@CCPLUserMgrBroker@@AEAAJP6AKPEAX@Z@Z; CCPLUserMgrBroker::_StartThreadWait(ulong (*)(void *))
0x1400033d1  test    eax, eax
0x1400033d3  js      short loc_1400033D8
0x1400033d5  mov     eax, [rbx+68h]
0x1400033d8  mov     rbx, [rsp+38h+arg_0]
0x1400033dd  add     rsp, 30h
0x1400033e1  pop     rdi
0x1400033e2  retn
```
