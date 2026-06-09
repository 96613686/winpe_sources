# CCPLUserMgrBroker::RunTaskFlow(TASK_FLOW_ID,HWND__ *,IUserManager *)

- ea: `0x1400033f0`
- end: `0x140003499`
- name: `?RunTaskFlow@CCPLUserMgrBroker@@UEAAJW4TASK_FLOW_ID@@PEAUHWND__@@PEAUIUserManager@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400033f0`
- `0x14000384c`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall CCPLUserMgrBroker::RunTaskFlow(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  _DWORD *v4; // rdi
  __int64 result; // rax

  v4 = (_DWORD *)(a1 + 120);
  *(_QWORD *)(a1 + 88) = a3;
  *(_DWORD *)(a1 + 96) = a2;
  result = 0;
  *(_DWORD *)(a1 + 104) = -2147023728;
  if ( *(_DWORD *)(a1 + 120) )
  {
    result = *(unsigned int *)(a1 + 124);
    if ( (int)result >= 0 )
      result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_14000C868 + 32LL))(qword_14000C868);
  }
  *v4 = 0;
  if ( (int)result >= 0 )
  {
    if ( !a4
      || (result = *(unsigned int *)(a1 + 124), (int)result >= 0)
      && (result = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, _DWORD *))(*(_QWORD *)qword_14000C868 + 24LL))(
                     qword_14000C868,
                     a4,
                     &GUID_73aecad8_7e70_4e21_8767_82b03c862455,
                     v4),
          (int)result >= 0) )
    {
      result = CCPLUserMgrBroker::_StartThreadWait((PVOID)a1, (WCHAR)CCPLUserMgrBroker::s_RunTaskFlowASTA);
      if ( (int)result >= 0 )
        return *(unsigned int *)(a1 + 104);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400033f0  mov     [rsp+arg_0], rbx
0x1400033f5  mov     [rsp+arg_8], rsi
0x1400033fa  push    rdi
0x1400033fb  sub     rsp, 30h
0x1400033ff  lea     rdi, [rcx+78h]
0x140003403  mov     [rcx+58h], r8
0x140003407  mov     [rcx+60h], edx
0x14000340a  xor     eax, eax
0x14000340c  mov     dword ptr [rcx+68h], 80070490h
0x140003413  mov     rsi, r9
0x140003416  mov     edx, [rdi]
0x140003418  mov     rbx, rcx
0x14000341b  test    edx, edx
0x14000341d  jz      short loc_140003439
0x14000341f  mov     eax, [rcx+7Ch]
0x140003422  test    eax, eax
0x140003424  js      short loc_140003439
0x140003426  mov     rcx, cs:qword_14000C868
0x14000342d  mov     rax, [rcx]
0x140003430  mov     rax, [rax+20h]
0x140003434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003439  mov     dword ptr [rdi], 0
0x14000343f  test    eax, eax
0x140003441  js      short loc_140003489
0x140003443  test    rsi, rsi
0x140003446  jz      short loc_140003473
0x140003448  mov     eax, [rbx+7Ch]
0x14000344b  test    eax, eax
0x14000344d  js      short loc_140003489
0x14000344f  mov     rcx, cs:qword_14000C868
0x140003456  lea     r8, _GUID_73aecad8_7e70_4e21_8767_82b03c862455
0x14000345d  mov     r9, rdi
0x140003460  mov     rdx, rsi
0x140003463  mov     rax, [rcx]
0x140003466  mov     rax, [rax+18h]
0x14000346a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000346f  test    eax, eax
0x140003471  js      short loc_140003489
0x140003473  lea     rdx, ?s_RunTaskFlowASTA@CCPLUserMgrBroker@@CAKPEAX@Z; ch
0x14000347a  mov     rcx, rbx; Context
0x14000347d  call    ?_StartThreadWait@CCPLUserMgrBroker@@AEAAJP6AKPEAX@Z@Z; CCPLUserMgrBroker::_StartThreadWait(ulong (*)(void *))
0x140003482  test    eax, eax
0x140003484  js      short loc_140003489
0x140003486  mov     eax, [rbx+68h]
0x140003489  mov     rbx, [rsp+38h+arg_0]
0x14000348e  mov     rsi, [rsp+38h+arg_8]
0x140003493  add     rsp, 30h
0x140003497  pop     rdi
0x140003498  retn
```
