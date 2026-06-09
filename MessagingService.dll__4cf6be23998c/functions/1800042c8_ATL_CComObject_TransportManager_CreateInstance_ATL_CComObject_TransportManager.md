# ATL::CComObject<TransportManager>::CreateInstance(ATL::CComObject<TransportManager> * *)

- ea: `0x1800042c8`
- end: `0x1800043af`
- name: `?CreateInstance@?$CComObject@VTransportManager@@@ATL@@SAJPEAPEAV12@@Z`
- size: `231`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003090`

## callees

- `0x180001730`
- `0x1800042c8`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<TransportManager>::CreateInstance(_QWORD *a1)
{
  _QWORD *v1; // rsi
  unsigned int v3; // r14d
  char *v4; // rax
  char *v5; // rbx
  char *v7; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = (char *)operator new(0x68u);
    v5 = v4;
    if ( v4 )
    {
      *(_QWORD *)(v4 + 28) = 0;
      *((_DWORD *)v4 + 9) = 0;
      *(_QWORD *)(v4 + 92) = 0;
      *((_DWORD *)v4 + 25) = 0;
      *((_DWORD *)v4 + 6) = 0;
      *((_QWORD *)v4 + 5) = 0;
      *((_QWORD *)v4 + 6) = 0;
      *((_QWORD *)v4 + 7) = v4 + 56;
      *((_QWORD *)v4 + 8) = v4 + 56;
      *((_QWORD *)v4 + 9) = 0;
      *((_QWORD *)v4 + 10) = 0;
      *((_DWORD *)v4 + 22) = 0;
      *(_QWORD *)v4 = &ATL::CComObject<TransportManager>::`vftable'{for `ITransportTaskScheduler'};
      *((_QWORD *)v4 + 1) = &ATL::CComObject<TransportManager>::`vftable'{for `ITransportTaskCallback'};
      *((_QWORD *)v4 + 2) = &ATL::CComObject<TransportManager>::`vftable'{for `IOneShotTimerCallback'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v5 = 0;
    }
    v7 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v7;
  }
  if ( v5 )
    v3 = 0;
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x1800042c8  mov     [rsp+arg_18], rbx
0x1800042cd  mov     [rsp+arg_0], rcx
0x1800042d2  push    rsi
0x1800042d3  push    rdi
0x1800042d4  push    r14
0x1800042d6  sub     rsp, 20h
0x1800042da  mov     rsi, rcx
0x1800042dd  xor     edi, edi
0x1800042df  test    rcx, rcx
0x1800042e2  jnz     short loc_1800042EE
0x1800042e4  mov     eax, 80004003h
0x1800042e9  jmp     loc_1800043A1
0x1800042ee  mov     [rcx], rdi
0x1800042f1  mov     r14d, 8007000Eh
0x1800042f7  mov     [rsp+38h+arg_8], r14d
0x1800042fc  mov     [rsp+38h+arg_10], rdi
0x180004301  mov     ecx, 68h ; 'h'; Size
0x180004306  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000430b  mov     rbx, rax
0x18000430e  test    rax, rax
0x180004311  jz      short loc_180004379
0x180004313  xor     eax, eax
0x180004315  mov     [rbx+1Ch], rax
0x180004319  mov     [rbx+24h], eax
0x18000431c  mov     [rbx+5Ch], rax
0x180004320  mov     [rbx+64h], eax
0x180004323  mov     [rbx+18h], edi
0x180004326  mov     [rbx+28h], rdi
0x18000432a  mov     [rbx+30h], rdi
0x18000432e  lea     rax, [rbx+38h]
0x180004332  mov     [rax], rax
0x180004335  mov     [rax+8], rax
0x180004339  mov     [rax+10h], rdi
0x18000433d  mov     [rbx+50h], rdi
0x180004341  mov     [rbx+58h], edi
0x180004344  lea     rax, ??_7?$CComObject@VTransportManager@@@ATL@@6BITransportTaskScheduler@@@; const ATL::CComObject<TransportManager>::`vftable'{for `ITransportTaskScheduler'}
0x18000434b  mov     [rbx], rax
0x18000434e  lea     rax, ??_7?$CComObject@VTransportManager@@@ATL@@6BITransportTaskCallback@@@; const ATL::CComObject<TransportManager>::`vftable'{for `ITransportTaskCallback'}
0x180004355  mov     [rbx+8], rax
0x180004359  lea     rax, ??_7?$CComObject@VTransportManager@@@ATL@@6BIOneShotTimerCallback@@@; const ATL::CComObject<TransportManager>::`vftable'{for `IOneShotTimerCallback'}
0x180004360  mov     [rbx+10h], rax
0x180004364  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000436b  mov     rax, [rcx]
0x18000436e  mov     rax, [rax+8]
0x180004372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004377  jmp     short loc_18000437C
0x180004379  mov     rbx, rdi
0x18000437c  mov     [rsp+38h+arg_10], rbx
0x180004381  jmp     short loc_180004394
0x180004383  xor     edi, edi
0x180004385  mov     rsi, [rsp+38h+arg_0]
0x18000438a  mov     r14d, [rsp+38h+arg_8]
0x18000438f  mov     rbx, [rsp+38h+arg_10]
0x180004394  test    rbx, rbx
0x180004397  cmovnz  r14d, edi
0x18000439b  mov     [rsi], rbx
0x18000439e  mov     eax, r14d
0x1800043a1  mov     rbx, [rsp+38h+arg_18]
0x1800043a6  add     rsp, 20h
0x1800043aa  pop     r14
0x1800043ac  pop     rdi
0x1800043ad  pop     rsi
0x1800043ae  retn
```
