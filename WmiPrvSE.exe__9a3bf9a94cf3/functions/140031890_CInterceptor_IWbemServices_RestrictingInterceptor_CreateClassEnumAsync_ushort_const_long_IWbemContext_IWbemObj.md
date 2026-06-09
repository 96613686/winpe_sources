# CInterceptor_IWbemServices_RestrictingInterceptor::CreateClassEnumAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140031890`
- end: `0x140031a39`
- name: `?CreateClassEnumAsync@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `425`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140028cfc`
- `0x1400310f0`
- `0x140031890`
- `0x140032b60`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400319d3`
- `wbemcomn!GetMemLogObject` at `0x1400319d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400319de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400319de`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::CreateClassEnumAsync(
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
      91,
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
             + 13))(
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
      92,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140031890  mov     r11, rsp
0x140031893  mov     [r11+10h], rbx
0x140031897  mov     [r11+18h], rsi
0x14003189b  push    rbp
0x14003189c  push    rdi
0x14003189d  push    r12
0x14003189f  push    r14
0x1400318a1  push    r15
0x1400318a3  mov     rbp, rsp
0x1400318a6  sub     rsp, 80h
0x1400318ad  mov     rsi, r9
0x1400318b0  mov     r14d, r8d
0x1400318b3  mov     r15, rdx
0x1400318b6  mov     rdi, rcx
0x1400318b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400318c0  lea     rax, WPP_GLOBAL_Control
0x1400318c7  mov     r12, [rbp+arg_20]
0x1400318cb  cmp     rcx, rax
0x1400318ce  jz      short loc_140031901
0x1400318d0  test    byte ptr [rcx+1Ch], 4
0x1400318d4  jz      short loc_140031901
0x1400318d6  cmp     byte ptr [rcx+19h], 5
0x1400318da  jb      short loc_140031901
0x1400318dc  mov     rcx, [rcx+10h]
0x1400318e0  mov     edx, 5Bh ; '['
0x1400318e5  mov     [r11-78h], r12
0x1400318e9  mov     [r11-80h], r9
0x1400318ed  mov     r9, r15
0x1400318f0  mov     dword ptr [rsp+80h+var_60], r8d
0x1400318f5  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x1400318fc  call    WPP_SF_Sdqq
0x140031901  lock inc dword ptr [rdi+20h]
0x140031905  cmp     dword ptr [rdi+1Ch], 1
0x140031909  jnz     short loc_140031915
0x14003190b  mov     ebx, 80041033h
0x140031910  jmp     loc_1400319CB
0x140031915  lea     rax, [rbp+var_20]
0x140031919  mov     [rbp+var_30], 0
0x140031920  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140031925  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140031929  lea     rax, [rbp+arg_0]
0x14003192d  mov     [rbp+var_10], 0
0x140031935  mov     [rsp+80h+var_50], rax; int *
0x14003193a  lea     r8, [rbp+var_10]; struct IUnknown **
0x14003193e  lea     rax, [rbp+var_28]
0x140031942  mov     [rbp+var_18], 0
0x14003194a  mov     [rsp+80h+var_58], rax; struct IWbemServices *
0x14003194f  lea     rdx, [rbp+var_30]; int *
0x140031953  lea     rax, [rbp+var_2C]
0x140031957  mov     [rbp+var_2C], 0
0x14003195e  mov     rcx, rdi; this
0x140031961  mov     [rsp+80h+var_60], rax; int *
0x140031966  mov     [rbp+var_28.lpVtbl], 0
0x14003196e  mov     [rbp+arg_0], 0
0x140031975  mov     [rbp+var_20], 0
0x14003197d  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x140031982  mov     ebx, eax
0x140031984  test    eax, eax
0x140031986  js      short loc_1400319CB
0x140031988  mov     rcx, [rbp+var_28.lpVtbl]
0x14003198c  mov     r9, rsi
0x14003198f  mov     r8d, r14d
0x140031992  mov     [rsp+80h+var_60], r12; int
0x140031997  mov     rdx, r15
0x14003199a  mov     rax, [rcx]
0x14003199d  mov     rax, [rax+68h]
0x1400319a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400319a6  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x1400319aa  mov     ebx, eax
0x1400319ac  mov     rax, [rbp+var_20]
0x1400319b0  mov     rcx, rdi; this
0x1400319b3  mov     r8, [rbp+var_10]; struct IUnknown *
0x1400319b7  mov     edx, [rbp+var_30]; int
0x1400319ba  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x1400319bf  mov     eax, [rbp+arg_0]
0x1400319c2  mov     dword ptr [rsp+80h+var_50], eax; int
0x1400319c6  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x1400319cb  lock dec dword ptr [rdi+20h]
0x1400319cf  test    ebx, ebx
0x1400319d1  jns     short loc_1400319E4
0x1400319d3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400319d9  mov     rcx, rax
0x1400319dc  mov     edx, ebx
0x1400319de  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400319e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400319eb  lea     rax, WPP_GLOBAL_Control
0x1400319f2  cmp     rcx, rax
0x1400319f5  jz      short loc_140031A1B
0x1400319f7  test    byte ptr [rcx+1Ch], 4
0x1400319fb  jz      short loc_140031A1B
0x1400319fd  cmp     byte ptr [rcx+19h], 2
0x140031a01  jb      short loc_140031A1B
0x140031a03  mov     rcx, [rcx+10h]
0x140031a07  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140031a0e  mov     edx, 5Ch ; '\'
0x140031a13  mov     r9d, ebx
0x140031a16  call    WPP_SF_d
0x140031a1b  lea     r11, [rsp+80h+var_s0]
0x140031a23  mov     eax, ebx
0x140031a25  mov     rbx, [r11+38h]
0x140031a29  mov     rsi, [r11+40h]
0x140031a2d  mov     rsp, r11
0x140031a30  pop     r15
0x140031a32  pop     r14
0x140031a34  pop     r12
0x140031a36  pop     rdi
0x140031a37  pop     rbp
0x140031a38  retn
```
