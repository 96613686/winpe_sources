# CInterceptor_IWbemServices_RestrictingInterceptor::GetObjectAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140033d70`
- end: `0x140033f19`
- name: `?GetObjectAsync@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `425`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this@<rcx>, unsigned __int16 *const@<rdx>, int@<r8d>, struct IWbemContext *@<r9>, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140028cfc`
- `0x1400310f0`
- `0x140032b60`
- `0x140033d70`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140033eb3`
- `wbemcomn!GetMemLogObject` at `0x140033eb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033ebe`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033ebe`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::GetObjectAsync(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  int v9; // r12d
  int v10; // ebx
  CMemoryLog *MemLogObject; // rax
  struct IWbemServices **v13; // [rsp+28h] [rbp-58h]
  int v14; // [rsp+50h] [rbp-30h] BYREF
  int v15; // [rsp+54h] [rbp-2Ch] BYREF
  struct IWbemServices v16; // [rsp+58h] [rbp-28h] BYREF
  struct IUnknown *v17; // [rsp+60h] [rbp-20h] BYREF
  struct IServerSecurity *v18; // [rsp+68h] [rbp-18h] BYREF
  struct IUnknown *v19; // [rsp+70h] [rbp-10h] BYREF
  int v20; // [rsp+B0h] [rbp+30h] BYREF

  v9 = (int)a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      79,
      (unsigned int)WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (_DWORD)a2,
      a3,
      (char)a4,
      (char)a5);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v10 = -2147217357;
  }
  else
  {
    v14 = 0;
    v19 = 0;
    v18 = 0;
    v15 = 0;
    v16.lpVtbl = 0;
    v20 = 0;
    v17 = 0;
    v10 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(
            (struct IUnknown **)this,
            &v14,
            &v19,
            &v18,
            &v15,
            (struct IWbemServices **)&v16,
            &v20,
            &v17);
    if ( v10 >= 0 )
    {
      v10 = (*((__int64 (__fastcall **)(struct IWbemServicesVtbl *, unsigned __int16 *const, _QWORD, struct IWbemContext *))v16.lpVtbl->QueryInterface
             + 7))(
              v16.lpVtbl,
              a2,
              a3,
              a4);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(
        this,
        v14,
        v19,
        v18,
        v9,
        (struct IWbemServices *)v13,
        v20,
        v17);
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v10 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v10);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      80,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140033d70  mov     r11, rsp
0x140033d73  mov     [r11+10h], rbx
0x140033d77  mov     [r11+18h], rsi
0x140033d7b  push    rbp
0x140033d7c  push    rdi
0x140033d7d  push    r12
0x140033d7f  push    r14
0x140033d81  push    r15
0x140033d83  mov     rbp, rsp
0x140033d86  sub     rsp, 80h
0x140033d8d  mov     rsi, r9
0x140033d90  mov     r14d, r8d
0x140033d93  mov     r15, rdx
0x140033d96  mov     rdi, rcx
0x140033d99  mov     rcx, cs:WPP_GLOBAL_Control
0x140033da0  lea     rax, WPP_GLOBAL_Control
0x140033da7  mov     r12, [rbp+arg_20]
0x140033dab  cmp     rcx, rax
0x140033dae  jz      short loc_140033DE1
0x140033db0  test    byte ptr [rcx+1Ch], 4
0x140033db4  jz      short loc_140033DE1
0x140033db6  cmp     byte ptr [rcx+19h], 5
0x140033dba  jb      short loc_140033DE1
0x140033dbc  mov     rcx, [rcx+10h]
0x140033dc0  mov     edx, 4Fh ; 'O'
0x140033dc5  mov     [r11-78h], r12
0x140033dc9  mov     [r11-80h], r9
0x140033dcd  mov     r9, r15
0x140033dd0  mov     dword ptr [rsp+80h+var_60], r8d
0x140033dd5  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140033ddc  call    WPP_SF_Sdqq
0x140033de1  lock inc dword ptr [rdi+20h]
0x140033de5  cmp     dword ptr [rdi+1Ch], 1
0x140033de9  jnz     short loc_140033DF5
0x140033deb  mov     ebx, 80041033h
0x140033df0  jmp     loc_140033EAB
0x140033df5  lea     rax, [rbp+var_20]
0x140033df9  mov     [rbp+var_30], 0
0x140033e00  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140033e05  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140033e09  lea     rax, [rbp+arg_0]
0x140033e0d  mov     [rbp+var_10], 0
0x140033e15  mov     [rsp+80h+var_50], rax; int *
0x140033e1a  lea     r8, [rbp+var_10]; struct IUnknown **
0x140033e1e  lea     rax, [rbp+var_28]
0x140033e22  mov     [rbp+var_18], 0
0x140033e2a  mov     [rsp+80h+var_58], rax; struct IWbemServices *
0x140033e2f  lea     rdx, [rbp+var_30]; int *
0x140033e33  lea     rax, [rbp+var_2C]
0x140033e37  mov     [rbp+var_2C], 0
0x140033e3e  mov     rcx, rdi; this
0x140033e41  mov     [rsp+80h+var_60], rax; int *
0x140033e46  mov     [rbp+var_28.lpVtbl], 0
0x140033e4e  mov     [rbp+arg_0], 0
0x140033e55  mov     [rbp+var_20], 0
0x140033e5d  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x140033e62  mov     ebx, eax
0x140033e64  test    eax, eax
0x140033e66  js      short loc_140033EAB
0x140033e68  mov     rcx, [rbp+var_28.lpVtbl]
0x140033e6c  mov     r9, rsi
0x140033e6f  mov     r8d, r14d
0x140033e72  mov     [rsp+80h+var_60], r12; int
0x140033e77  mov     rdx, r15
0x140033e7a  mov     rax, [rcx]
0x140033e7d  mov     rax, [rax+38h]
0x140033e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033e86  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x140033e8a  mov     ebx, eax
0x140033e8c  mov     rax, [rbp+var_20]
0x140033e90  mov     rcx, rdi; this
0x140033e93  mov     r8, [rbp+var_10]; struct IUnknown *
0x140033e97  mov     edx, [rbp+var_30]; int
0x140033e9a  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x140033e9f  mov     eax, [rbp+arg_0]
0x140033ea2  mov     dword ptr [rsp+80h+var_50], eax; int
0x140033ea6  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140033eab  lock dec dword ptr [rdi+20h]
0x140033eaf  test    ebx, ebx
0x140033eb1  jns     short loc_140033EC4
0x140033eb3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140033eb9  mov     rcx, rax
0x140033ebc  mov     edx, ebx
0x140033ebe  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140033ec4  mov     rcx, cs:WPP_GLOBAL_Control
0x140033ecb  lea     rax, WPP_GLOBAL_Control
0x140033ed2  cmp     rcx, rax
0x140033ed5  jz      short loc_140033EFB
0x140033ed7  test    byte ptr [rcx+1Ch], 4
0x140033edb  jz      short loc_140033EFB
0x140033edd  cmp     byte ptr [rcx+19h], 2
0x140033ee1  jb      short loc_140033EFB
0x140033ee3  mov     rcx, [rcx+10h]
0x140033ee7  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140033eee  mov     edx, 50h ; 'P'
0x140033ef3  mov     r9d, ebx
0x140033ef6  call    WPP_SF_d
0x140033efb  lea     r11, [rsp+80h+var_s0]
0x140033f03  mov     eax, ebx
0x140033f05  mov     rbx, [r11+38h]
0x140033f09  mov     rsi, [r11+40h]
0x140033f0d  mov     rsp, r11
0x140033f10  pop     r15
0x140033f12  pop     r14
0x140033f14  pop     r12
0x140033f16  pop     rdi
0x140033f17  pop     rbp
0x140033f18  retn
```
