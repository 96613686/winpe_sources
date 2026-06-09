# CInterceptor_IWbemServices_RestrictingInterceptor::CancelAsyncCall(IWbemObjectSink *)

- ea: `0x140031340`
- end: `0x1400314a0`
- name: `?CancelAsyncCall@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJPEAUIWbemObjectSink@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140030438`
- `0x1400310f0`
- `0x140031340`
- `0x140032b60`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140031452`
- `wbemcomn!GetMemLogObject` at `0x140031452`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003145d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003145d`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::CancelAsyncCall(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        struct IWbemObjectSink *a2)
{
  int v4; // ebx
  CMemoryLog *MemLogObject; // rax
  int v7; // [rsp+20h] [rbp-50h]
  struct IWbemServices **v8; // [rsp+28h] [rbp-48h]
  IWbemServices v9; // [rsp+50h] [rbp-20h] BYREF
  struct IUnknown *v10; // [rsp+58h] [rbp-18h] BYREF
  struct IServerSecurity *v11; // [rsp+60h] [rbp-10h] BYREF
  struct IUnknown *v12; // [rsp+68h] [rbp-8h] BYREF
  int v13; // [rsp+A0h] [rbp+30h] BYREF
  int v14; // [rsp+B0h] [rbp+40h] BYREF
  int v15; // [rsp+B8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, a2);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v4 = -2147217357;
  }
  else
  {
    v14 = 0;
    v12 = 0;
    v11 = 0;
    v15 = 0;
    v9.lpVtbl = 0;
    v13 = 0;
    v10 = 0;
    v4 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(
           (struct IUnknown **)this,
           &v14,
           &v12,
           &v11,
           &v15,
           (struct IWbemServices **)&v9,
           &v13,
           &v10);
    if ( v4 >= 0 )
    {
      v4 = (*((__int64 (__fastcall **)(struct IWbemServicesVtbl *, struct IWbemObjectSink *))v9.lpVtbl->QueryInterface
            + 4))(
             v9.lpVtbl,
             a2);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(
        this,
        v14,
        v12,
        v11,
        v7,
        (struct IWbemServices *)v8,
        v13,
        v10);
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v4 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v4);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140031340  push    rbp
0x140031342  push    rbx
0x140031343  push    rsi
0x140031344  push    rdi
0x140031345  push    r15
0x140031347  mov     rbp, rsp
0x14003134a  sub     rsp, 70h
0x14003134e  mov     rsi, rdx
0x140031351  mov     rdi, rcx
0x140031354  mov     rcx, cs:WPP_GLOBAL_Control
0x14003135b  lea     r15, WPP_GLOBAL_Control
0x140031362  cmp     rcx, r15
0x140031365  jz      short loc_14003138B
0x140031367  test    byte ptr [rcx+1Ch], 4
0x14003136b  jz      short loc_14003138B
0x14003136d  cmp     byte ptr [rcx+19h], 5
0x140031371  jb      short loc_14003138B
0x140031373  mov     rcx, [rcx+10h]
0x140031377  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x14003137e  mov     edx, 49h ; 'I'
0x140031383  mov     r9, rsi
0x140031386  call    WPP_SF_q
0x14003138b  lock inc dword ptr [rdi+20h]
0x14003138f  cmp     dword ptr [rdi+1Ch], 1
0x140031393  jnz     short loc_14003139F
0x140031395  mov     ebx, 80041033h
0x14003139a  jmp     loc_14003144A
0x14003139f  lea     rax, [rbp+var_18]
0x1400313a3  mov     [rbp+arg_10], 0
0x1400313aa  mov     [rsp+70h+var_38], rax; struct IUnknown **
0x1400313af  lea     r9, [rbp+var_10]; struct IServerSecurity **
0x1400313b3  lea     rax, [rbp+arg_0]
0x1400313b7  mov     [rbp+var_8], 0
0x1400313bf  mov     [rsp+70h+var_40], rax; int *
0x1400313c4  lea     r8, [rbp+var_8]; struct IUnknown **
0x1400313c8  lea     rax, [rbp+var_20]
0x1400313cc  mov     [rbp+var_10], 0
0x1400313d4  mov     [rsp+70h+var_48], rax; struct IWbemServices *
0x1400313d9  lea     rdx, [rbp+arg_10]; int *
0x1400313dd  lea     rax, [rbp+arg_18]
0x1400313e1  mov     [rbp+arg_18], 0
0x1400313e8  mov     rcx, rdi; this
0x1400313eb  mov     [rsp+70h+var_50], rax; int
0x1400313f0  mov     [rbp+var_20.lpVtbl], 0
0x1400313f8  mov     [rbp+arg_0], 0
0x1400313ff  mov     [rbp+var_18], 0
0x140031407  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x14003140c  mov     ebx, eax
0x14003140e  test    eax, eax
0x140031410  js      short loc_14003144A
0x140031412  mov     rcx, [rbp+var_20.lpVtbl]
0x140031416  mov     rdx, rsi
0x140031419  mov     rax, [rcx]
0x14003141c  mov     rax, [rax+20h]
0x140031420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031425  mov     r9, [rbp+var_10]; struct IServerSecurity *
0x140031429  mov     ebx, eax
0x14003142b  mov     rax, [rbp+var_18]
0x14003142f  mov     rcx, rdi; this
0x140031432  mov     r8, [rbp+var_8]; struct IUnknown *
0x140031436  mov     edx, [rbp+arg_10]; int
0x140031439  mov     [rsp+70h+var_38], rax; struct IUnknown *
0x14003143e  mov     eax, [rbp+arg_0]
0x140031441  mov     dword ptr [rsp+70h+var_40], eax; int
0x140031445  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x14003144a  lock dec dword ptr [rdi+20h]
0x14003144e  test    ebx, ebx
0x140031450  jns     short loc_140031463
0x140031452  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140031458  mov     rcx, rax
0x14003145b  mov     edx, ebx
0x14003145d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140031463  mov     rcx, cs:WPP_GLOBAL_Control
0x14003146a  cmp     rcx, r15
0x14003146d  jz      short loc_140031493
0x14003146f  test    byte ptr [rcx+1Ch], 4
0x140031473  jz      short loc_140031493
0x140031475  cmp     byte ptr [rcx+19h], 2
0x140031479  jb      short loc_140031493
0x14003147b  mov     rcx, [rcx+10h]
0x14003147f  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140031486  mov     edx, 4Ah ; 'J'
0x14003148b  mov     r9d, ebx
0x14003148e  call    WPP_SF_d
0x140031493  mov     eax, ebx
0x140031495  add     rsp, 70h
0x140031499  pop     r15
0x14003149b  pop     rdi
0x14003149c  pop     rsi
0x14003149d  pop     rbx
0x14003149e  pop     rbp
0x14003149f  retn
```
