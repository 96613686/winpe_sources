# CInterceptor_IWbemServices_RestrictingInterceptor::GetObjectW(ushort * const,long,IWbemContext *,IWbemClassObject * *,IWbemCallResult * *)

- ea: `0x140033f20`
- end: `0x1400340c0`
- name: `?GetObjectW@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIWbemClassObject@@PEAPEAUIWbemCallResult@@@Z`
- size: `416`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this@<rcx>, unsigned __int16 *const@<rdx>, int@<r8d>, struct IWbemContext *@<r9>, struct IWbemClassObject **, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400310f0`
- `0x140032b60`
- `0x140033f20`
- `0x140035c5c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140034061`
- `wbemcomn!GetMemLogObject` at `0x140034061`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003406c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003406c`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::GetObjectW(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemClassObject **a5,
        struct IWbemServices **a6)
{
  int v10; // ebx
  CMemoryLog *MemLogObject; // rax
  int v13; // [rsp+20h] [rbp-60h]
  struct IWbemServices **v14; // [rsp+28h] [rbp-58h]
  int v15; // [rsp+50h] [rbp-30h] BYREF
  int v16; // [rsp+54h] [rbp-2Ch] BYREF
  struct IWbemServices *v17; // [rsp+58h] [rbp-28h] BYREF
  struct IUnknown *v18; // [rsp+60h] [rbp-20h] BYREF
  struct IServerSecurity *v19; // [rsp+68h] [rbp-18h] BYREF
  struct IUnknown *v20; // [rsp+70h] [rbp-10h] BYREF
  int v21; // [rsp+B0h] [rbp+30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, a3, (_DWORD)a2, a3, (char)a4);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v10 = -2147217357;
  }
  else
  {
    v15 = 0;
    v20 = 0;
    v19 = 0;
    v16 = 0;
    v17 = 0;
    v21 = 0;
    v18 = 0;
    v10 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(
            (struct IUnknown **)this,
            &v15,
            &v20,
            &v19,
            &v16,
            &v17,
            &v21,
            &v18);
    if ( v10 >= 0 )
    {
      v14 = a6;
      v13 = (int)a5;
      v10 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *const, _QWORD, struct IWbemContext *))v17->lpVtbl->GetObjectA)(
              v17,
              a2,
              a3,
              a4);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(
        this,
        v15,
        v20,
        v19,
        v13,
        (struct IWbemServices *)v14,
        v21,
        v18);
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
      78,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140033f20  mov     [rsp-28h+arg_8], rbx
0x140033f25  mov     [rsp-28h+arg_10], rsi
0x140033f2a  push    rbp
0x140033f2b  push    rdi
0x140033f2c  push    r13
0x140033f2e  push    r14
0x140033f30  push    r15
0x140033f32  mov     rbp, rsp
0x140033f35  sub     rsp, 80h
0x140033f3c  mov     rsi, r9
0x140033f3f  mov     r14d, r8d
0x140033f42  mov     r15, rdx
0x140033f45  mov     rdi, rcx
0x140033f48  mov     rcx, cs:WPP_GLOBAL_Control
0x140033f4f  lea     r13, WPP_GLOBAL_Control
0x140033f56  cmp     rcx, r13
0x140033f59  jz      short loc_140033F82
0x140033f5b  test    byte ptr [rcx+1Ch], 4
0x140033f5f  jz      short loc_140033F82
0x140033f61  cmp     byte ptr [rcx+19h], 5
0x140033f65  jb      short loc_140033F82
0x140033f67  mov     rcx, [rcx+10h]
0x140033f6b  mov     edx, 4Dh ; 'M'
0x140033f70  mov     [rsp+80h+var_58], r9
0x140033f75  mov     r9, r15
0x140033f78  mov     dword ptr [rsp+80h+var_60], r8d
0x140033f7d  call    WPP_SF_Sdq
0x140033f82  lock inc dword ptr [rdi+20h]
0x140033f86  cmp     dword ptr [rdi+1Ch], 1
0x140033f8a  jnz     short loc_140033F96
0x140033f8c  mov     ebx, 80041033h
0x140033f91  jmp     loc_140034059
0x140033f96  lea     rax, [rbp+var_20]
0x140033f9a  mov     [rbp+var_30], 0
0x140033fa1  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140033fa6  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140033faa  lea     rax, [rbp+arg_0]
0x140033fae  mov     [rbp+var_10], 0
0x140033fb6  mov     [rsp+80h+var_50], rax; int *
0x140033fbb  lea     r8, [rbp+var_10]; struct IUnknown **
0x140033fbf  lea     rax, [rbp+var_28]
0x140033fc3  mov     [rbp+var_18], 0
0x140033fcb  mov     [rsp+80h+var_58], rax; struct IWbemServices **
0x140033fd0  lea     rdx, [rbp+var_30]; int *
0x140033fd4  lea     rax, [rbp+var_2C]
0x140033fd8  mov     [rbp+var_2C], 0
0x140033fdf  mov     rcx, rdi; this
0x140033fe2  mov     [rsp+80h+var_60], rax; int *
0x140033fe7  mov     [rbp+var_28], 0
0x140033fef  mov     [rbp+arg_0], 0
0x140033ff6  mov     [rbp+var_20], 0
0x140033ffe  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x140034003  mov     ebx, eax
0x140034005  test    eax, eax
0x140034007  js      short loc_140034059
0x140034009  mov     rcx, [rbp+var_28]
0x14003400d  mov     r9, rsi
0x140034010  mov     rdx, [rbp+arg_28]
0x140034014  mov     r8d, r14d
0x140034017  mov     [rsp+80h+var_58], rdx; struct IWbemServices *
0x14003401c  mov     rdx, [rbp+arg_20]
0x140034020  mov     rax, [rcx]
0x140034023  mov     [rsp+80h+var_60], rdx; int
0x140034028  mov     rdx, r15
0x14003402b  mov     rax, [rax+30h]
0x14003402f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034034  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x140034038  mov     ebx, eax
0x14003403a  mov     rax, [rbp+var_20]
0x14003403e  mov     rcx, rdi; this
0x140034041  mov     r8, [rbp+var_10]; struct IUnknown *
0x140034045  mov     edx, [rbp+var_30]; int
0x140034048  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x14003404d  mov     eax, [rbp+arg_0]
0x140034050  mov     dword ptr [rsp+80h+var_50], eax; int
0x140034054  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140034059  lock dec dword ptr [rdi+20h]
0x14003405d  test    ebx, ebx
0x14003405f  jns     short loc_140034072
0x140034061  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140034067  mov     rcx, rax
0x14003406a  mov     edx, ebx
0x14003406c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140034072  mov     rcx, cs:WPP_GLOBAL_Control
0x140034079  cmp     rcx, r13
0x14003407c  jz      short loc_1400340A2
0x14003407e  test    byte ptr [rcx+1Ch], 4
0x140034082  jz      short loc_1400340A2
0x140034084  cmp     byte ptr [rcx+19h], 2
0x140034088  jb      short loc_1400340A2
0x14003408a  mov     rcx, [rcx+10h]
0x14003408e  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140034095  mov     edx, 4Eh ; 'N'
0x14003409a  mov     r9d, ebx
0x14003409d  call    WPP_SF_d
0x1400340a2  lea     r11, [rsp+80h+var_s0]
0x1400340aa  mov     eax, ebx
0x1400340ac  mov     rbx, [r11+38h]
0x1400340b0  mov     rsi, [r11+40h]
0x1400340b4  mov     rsp, r11
0x1400340b7  pop     r15
0x1400340b9  pop     r14
0x1400340bb  pop     r13
0x1400340bd  pop     rdi
0x1400340be  pop     rbp
0x1400340bf  retn
```
