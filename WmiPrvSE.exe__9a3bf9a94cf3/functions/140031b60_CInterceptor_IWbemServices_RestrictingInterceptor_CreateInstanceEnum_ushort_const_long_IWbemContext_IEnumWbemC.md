# CInterceptor_IWbemServices_RestrictingInterceptor::CreateInstanceEnum(ushort * const,long,IWbemContext *,IEnumWbemClassObject * *)

- ea: `0x140031b60`
- end: `0x140031cfa`
- name: `?CreateInstanceEnum@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IEnumWbemClassObject **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400310f0`
- `0x140031b60`
- `0x140032b60`
- `0x140035c5c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140031c9b`
- `wbemcomn!GetMemLogObject` at `0x140031c9b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140031ca6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140031ca6`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::CreateInstanceEnum(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IEnumWbemClassObject **a5)
{
  int v9; // ebx
  CMemoryLog *MemLogObject; // rax
  int v12; // [rsp+20h] [rbp-60h]
  struct IWbemServices **v13; // [rsp+28h] [rbp-58h]
  int v14; // [rsp+50h] [rbp-30h] BYREF
  int v15; // [rsp+54h] [rbp-2Ch] BYREF
  struct IWbemServices v16; // [rsp+58h] [rbp-28h] BYREF
  struct IUnknown *v17; // [rsp+60h] [rbp-20h] BYREF
  struct IServerSecurity *v18; // [rsp+68h] [rbp-18h] BYREF
  struct IUnknown *v19; // [rsp+70h] [rbp-10h] BYREF
  int v20; // [rsp+B0h] [rbp+30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, a3, (_DWORD)a2, a3, (char)a4);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v9 = -2147217357;
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
    v9 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(
           (struct IUnknown **)this,
           &v14,
           &v19,
           &v18,
           &v15,
           (struct IWbemServices **)&v16,
           &v20,
           &v17);
    if ( v9 >= 0 )
    {
      v12 = (int)a5;
      v9 = (*((__int64 (__fastcall **)(struct IWbemServicesVtbl *, unsigned __int16 *const, _QWORD, struct IWbemContext *))v16.lpVtbl->QueryInterface
            + 18))(
             v16.lpVtbl,
             a2,
             a3,
             a4);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(
        this,
        v14,
        v19,
        v18,
        v12,
        (struct IWbemServices *)v13,
        v20,
        v17);
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v9 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v9);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      102,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140031b60  mov     [rsp-28h+arg_8], rbx
0x140031b65  mov     [rsp-28h+arg_10], rsi
0x140031b6a  push    rbp
0x140031b6b  push    rdi
0x140031b6c  push    r13
0x140031b6e  push    r14
0x140031b70  push    r15
0x140031b72  mov     rbp, rsp
0x140031b75  sub     rsp, 80h
0x140031b7c  mov     rsi, r9
0x140031b7f  mov     r14d, r8d
0x140031b82  mov     r15, rdx
0x140031b85  mov     rdi, rcx
0x140031b88  mov     rcx, cs:WPP_GLOBAL_Control
0x140031b8f  lea     r13, WPP_GLOBAL_Control
0x140031b96  cmp     rcx, r13
0x140031b99  jz      short loc_140031BC2
0x140031b9b  test    byte ptr [rcx+1Ch], 4
0x140031b9f  jz      short loc_140031BC2
0x140031ba1  cmp     byte ptr [rcx+19h], 5
0x140031ba5  jb      short loc_140031BC2
0x140031ba7  mov     rcx, [rcx+10h]
0x140031bab  mov     edx, 65h ; 'e'
0x140031bb0  mov     [rsp+80h+var_58], r9
0x140031bb5  mov     r9, r15
0x140031bb8  mov     dword ptr [rsp+80h+var_60], r8d
0x140031bbd  call    WPP_SF_Sdq
0x140031bc2  lock inc dword ptr [rdi+20h]
0x140031bc6  cmp     dword ptr [rdi+1Ch], 1
0x140031bca  jnz     short loc_140031BD6
0x140031bcc  mov     ebx, 80041033h
0x140031bd1  jmp     loc_140031C93
0x140031bd6  lea     rax, [rbp+var_20]
0x140031bda  mov     [rbp+var_30], 0
0x140031be1  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140031be6  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140031bea  lea     rax, [rbp+arg_0]
0x140031bee  mov     [rbp+var_10], 0
0x140031bf6  mov     [rsp+80h+var_50], rax; int *
0x140031bfb  lea     r8, [rbp+var_10]; struct IUnknown **
0x140031bff  lea     rax, [rbp+var_28]
0x140031c03  mov     [rbp+var_18], 0
0x140031c0b  mov     [rsp+80h+var_58], rax; struct IWbemServices *
0x140031c10  lea     rdx, [rbp+var_30]; int *
0x140031c14  lea     rax, [rbp+var_2C]
0x140031c18  mov     [rbp+var_2C], 0
0x140031c1f  mov     rcx, rdi; this
0x140031c22  mov     [rsp+80h+var_60], rax; int *
0x140031c27  mov     [rbp+var_28.lpVtbl], 0
0x140031c2f  mov     [rbp+arg_0], 0
0x140031c36  mov     [rbp+var_20], 0
0x140031c3e  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x140031c43  mov     ebx, eax
0x140031c45  test    eax, eax
0x140031c47  js      short loc_140031C93
0x140031c49  mov     rcx, [rbp+var_28.lpVtbl]
0x140031c4d  mov     r9, rsi
0x140031c50  mov     rdx, [rbp+arg_20]
0x140031c54  mov     r8d, r14d
0x140031c57  mov     [rsp+80h+var_60], rdx; int
0x140031c5c  mov     rdx, r15
0x140031c5f  mov     rax, [rcx]
0x140031c62  mov     rax, [rax+90h]
0x140031c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031c6e  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x140031c72  mov     ebx, eax
0x140031c74  mov     rax, [rbp+var_20]
0x140031c78  mov     rcx, rdi; this
0x140031c7b  mov     r8, [rbp+var_10]; struct IUnknown *
0x140031c7f  mov     edx, [rbp+var_30]; int
0x140031c82  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x140031c87  mov     eax, [rbp+arg_0]
0x140031c8a  mov     dword ptr [rsp+80h+var_50], eax; int
0x140031c8e  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140031c93  lock dec dword ptr [rdi+20h]
0x140031c97  test    ebx, ebx
0x140031c99  jns     short loc_140031CAC
0x140031c9b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140031ca1  mov     rcx, rax
0x140031ca4  mov     edx, ebx
0x140031ca6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140031cac  mov     rcx, cs:WPP_GLOBAL_Control
0x140031cb3  cmp     rcx, r13
0x140031cb6  jz      short loc_140031CDC
0x140031cb8  test    byte ptr [rcx+1Ch], 4
0x140031cbc  jz      short loc_140031CDC
0x140031cbe  cmp     byte ptr [rcx+19h], 2
0x140031cc2  jb      short loc_140031CDC
0x140031cc4  mov     rcx, [rcx+10h]
0x140031cc8  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140031ccf  mov     edx, 66h ; 'f'
0x140031cd4  mov     r9d, ebx
0x140031cd7  call    WPP_SF_d
0x140031cdc  lea     r11, [rsp+80h+var_s0]
0x140031ce4  mov     eax, ebx
0x140031ce6  mov     rbx, [r11+38h]
0x140031cea  mov     rsi, [r11+40h]
0x140031cee  mov     rsp, r11
0x140031cf1  pop     r15
0x140031cf3  pop     r14
0x140031cf5  pop     r13
0x140031cf7  pop     rdi
0x140031cf8  pop     rbp
0x140031cf9  retn
```
