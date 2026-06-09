# ATL::CComClassFactorySingleton<CRemoteAssistance>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1400052e0`
- end: `0x1400053cd`
- name: `?CreateInstance@?$CComClassFactorySingleton@VCRemoteAssistance@@@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `237`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140003ed8`
- `0x1400052e0`
- `0x140005c6c`
- `0x140017010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140005399`
- `KERNEL32!LeaveCriticalSection` at `0x140005399`
- `KERNEL32!LeaveCriticalSection` at `0x140015d9c`
- `KERNEL32!EnterCriticalSection` at `0x140005337`
- `KERNEL32!EnterCriticalSection` at `0x140005337`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactorySingleton<CRemoteAssistance>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 result; // rax
  _QWORD *v8; // rdi
  int v9; // eax
  void *v10; // rsi
  int v11; // eax
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // [rsp+68h] [rbp+20h] BYREF

  result = 2147500035LL;
  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return 2147746064LL;
    }
    else
    {
      if ( !*(_DWORD *)(a1 + 72) )
      {
        v8 = (_QWORD *)(a1 + 80);
        if ( !*(_QWORD *)(a1 + 80) )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
          if ( !*(_DWORD *)(a1 + 72) && !*v8 )
          {
            v12 = 0;
            v9 = ATL::CComObjectCached<CRemoteAssistance>::CreateInstance(&v12);
            *(_DWORD *)(a1 + 72) = v9;
            if ( v9 >= 0 )
            {
              v10 = v12;
              v11 = (**v12)(v12, &IID_IUnknown, v8);
              *(_DWORD *)(a1 + 72) = v11;
              if ( v11 < 0 )
              {
                if ( v10 )
                  ATL::CComObjectCached<CRemoteAssistance>::`scalar deleting destructor'(v10);
              }
            }
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
        }
      }
      result = *(unsigned int *)(a1 + 72);
      if ( !(_DWORD)result )
        return (***(__int64 (__fastcall ****)(_QWORD, __int64, _QWORD *))(a1 + 80))(*(_QWORD *)(a1 + 80), a3, a4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400052e0  mov     [rsp+arg_8], rbx
0x1400052e5  mov     [rsp+arg_0], rcx
0x1400052ea  push    rsi
0x1400052eb  push    rdi
0x1400052ec  push    r12
0x1400052ee  push    r14
0x1400052f0  push    r15
0x1400052f2  sub     rsp, 20h
0x1400052f6  mov     r14, r9
0x1400052f9  mov     r12, r8
0x1400052fc  mov     rbx, rcx
0x1400052ff  mov     eax, 80004003h
0x140005304  test    r9, r9
0x140005307  jz      loc_1400053BB
0x14000530d  mov     qword ptr [r9], 0
0x140005314  test    rdx, rdx
0x140005317  jz      short loc_140005323
0x140005319  mov     eax, 80040110h
0x14000531e  jmp     loc_1400053BB
0x140005323  cmp     dword ptr [rcx+48h], 0
0x140005327  jnz     short loc_14000539F
0x140005329  lea     rdi, [rcx+50h]
0x14000532d  cmp     qword ptr [rdi], 0
0x140005331  jnz     short loc_14000539F
0x140005333  add     rcx, 10h; lpCriticalSection
0x140005337  call    cs:__imp_EnterCriticalSection
0x14000533d  cmp     dword ptr [rbx+48h], 0
0x140005341  jnz     short loc_140005395
0x140005343  cmp     qword ptr [rdi], 0
0x140005347  jnz     short loc_140005395
0x140005349  mov     [rsp+48h+arg_18], 0
0x140005352  lea     rcx, [rsp+48h+arg_18]
0x140005357  call    ?CreateInstance@?$CComObjectCached@VCRemoteAssistance@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObjectCached<CRemoteAssistance>::CreateInstance(ATL::CComObjectCached<CRemoteAssistance> * *)
0x14000535c  mov     [rbx+48h], eax
0x14000535f  test    eax, eax
0x140005361  js      short loc_140005395
0x140005363  mov     rsi, [rsp+48h+arg_18]
0x140005368  mov     rax, [rsi]
0x14000536b  mov     r8, rdi
0x14000536e  lea     rdx, IID_IUnknown
0x140005375  mov     rcx, rsi
0x140005378  mov     rax, [rax]
0x14000537b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005380  mov     [rbx+48h], eax
0x140005383  test    eax, eax
0x140005385  jns     short loc_140005395
0x140005387  test    rsi, rsi
0x14000538a  jz      short loc_140005395
0x14000538c  mov     rcx, rsi
0x14000538f  call    ??_G?$CComObjectCached@VCRemoteAssistance@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<CRemoteAssistance>::`scalar deleting destructor'(uint)
0x140005394  nop
0x140005395  lea     rcx, [rbx+10h]; lpCriticalSection
0x140005399  call    cs:__imp_LeaveCriticalSection
0x14000539f  mov     eax, [rbx+48h]
0x1400053a2  test    eax, eax
0x1400053a4  jnz     short loc_1400053BB
0x1400053a6  mov     rcx, [rbx+50h]
0x1400053aa  mov     rax, [rcx]
0x1400053ad  mov     r8, r14
0x1400053b0  mov     rdx, r12
0x1400053b3  mov     rax, [rax]
0x1400053b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400053bb  mov     rbx, [rsp+48h+arg_8]
0x1400053c0  add     rsp, 20h
0x1400053c4  pop     r15
0x1400053c6  pop     r14
0x1400053c8  pop     r12
0x1400053ca  pop     rdi
0x1400053cb  pop     rsi
0x1400053cc  retn
0x140015d86  push    rbp
0x140015d88  sub     rsp, 20h
0x140015d8c  mov     rbp, rdx
0x140015d8f  mov     rcx, [rbp+50h]
0x140015d93  add     rcx, 10h
0x140015d97  add     rsp, 20h
0x140015d9b  pop     rbp
0x140015d9c  jmp     cs:__imp_LeaveCriticalSection
```
