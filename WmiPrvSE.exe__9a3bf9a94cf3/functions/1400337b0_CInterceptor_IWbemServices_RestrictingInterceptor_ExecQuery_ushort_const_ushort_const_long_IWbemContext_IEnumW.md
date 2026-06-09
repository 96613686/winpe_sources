# CInterceptor_IWbemServices_RestrictingInterceptor::ExecQuery(ushort * const,ushort * const,long,IWbemContext *,IEnumWbemClassObject * *)

- ea: `0x1400337b0`
- end: `0x14003395f`
- name: `?ExecQuery@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAG0JPEAUIWbemContext@@PEAPEAUIEnumWbemClassObject@@@Z`
- size: `431`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this@<rcx>, unsigned __int16 *const@<rdx>, unsigned __int16 *const@<r8>, int@<r9d>, struct IWbemContext *, struct IEnumWbemClassObject **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400310f0`
- `0x140032b60`
- `0x1400337b0`
- `0x140035b84`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400338f9`
- `wbemcomn!GetMemLogObject` at `0x1400338f9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033904`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033904`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::ExecQuery(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemServices **a6)
{
  int v10; // r12d
  int v11; // ebx
  CMemoryLog *MemLogObject; // rax
  struct IWbemServices **v14; // [rsp+28h] [rbp-58h]
  int v15; // [rsp+50h] [rbp-30h] BYREF
  int v16; // [rsp+54h] [rbp-2Ch] BYREF
  struct IWbemServices *v17; // [rsp+58h] [rbp-28h] BYREF
  struct IUnknown *v18; // [rsp+60h] [rbp-20h] BYREF
  struct IServerSecurity *v19; // [rsp+68h] [rbp-18h] BYREF
  struct IUnknown *v20; // [rsp+70h] [rbp-10h] BYREF
  int v21; // [rsp+B0h] [rbp+30h] BYREF

  v10 = (int)a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, (_DWORD)a3, (_DWORD)a2, (__int64)a3, a4, (char)a5);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v11 = -2147217357;
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
    v11 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(
            (struct IUnknown **)this,
            &v15,
            &v20,
            &v19,
            &v16,
            &v17,
            &v21,
            &v18);
    if ( v11 >= 0 )
    {
      v14 = a6;
      v11 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *const, unsigned __int16 *const, _QWORD))v17->lpVtbl->ExecQuery)(
              v17,
              a2,
              a3,
              a4);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(
        this,
        v15,
        v20,
        v19,
        v10,
        (struct IWbemServices *)v14,
        v21,
        v18);
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v11 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v11);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      106,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400337b0  mov     [rsp-28h+arg_8], rbx
0x1400337b5  mov     [rsp-28h+arg_10], rsi
0x1400337ba  push    rbp
0x1400337bb  push    rdi
0x1400337bc  push    r12
0x1400337be  push    r14
0x1400337c0  push    r15
0x1400337c2  mov     rbp, rsp
0x1400337c5  sub     rsp, 80h
0x1400337cc  mov     esi, r9d
0x1400337cf  mov     r14, r8
0x1400337d2  mov     r15, rdx
0x1400337d5  mov     rdi, rcx
0x1400337d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400337df  lea     rax, WPP_GLOBAL_Control
0x1400337e6  mov     r12, [rbp+arg_20]
0x1400337ea  cmp     rcx, rax
0x1400337ed  jz      short loc_14003381B
0x1400337ef  test    byte ptr [rcx+1Ch], 4
0x1400337f3  jz      short loc_14003381B
0x1400337f5  cmp     byte ptr [rcx+19h], 5
0x1400337f9  jb      short loc_14003381B
0x1400337fb  mov     rcx, [rcx+10h]
0x1400337ff  mov     edx, 69h ; 'i'
0x140033804  mov     [rsp+80h+var_50], r12
0x140033809  mov     dword ptr [rsp+80h+var_58], r9d
0x14003380e  mov     r9, r15
0x140033811  mov     [rsp+80h+var_60], r8
0x140033816  call    WPP_SF_SSdq
0x14003381b  lock inc dword ptr [rdi+20h]
0x14003381f  cmp     dword ptr [rdi+1Ch], 1
0x140033823  jnz     short loc_14003382F
0x140033825  mov     ebx, 80041033h
0x14003382a  jmp     loc_1400338F1
0x14003382f  lea     rax, [rbp+var_20]
0x140033833  mov     [rbp+var_30], 0
0x14003383a  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x14003383f  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140033843  lea     rax, [rbp+arg_0]
0x140033847  mov     [rbp+var_10], 0
0x14003384f  mov     [rsp+80h+var_50], rax; int *
0x140033854  lea     r8, [rbp+var_10]; struct IUnknown **
0x140033858  lea     rax, [rbp+var_28]
0x14003385c  mov     [rbp+var_18], 0
0x140033864  mov     [rsp+80h+var_58], rax; struct IWbemServices **
0x140033869  lea     rdx, [rbp+var_30]; int *
0x14003386d  lea     rax, [rbp+var_2C]
0x140033871  mov     [rbp+var_2C], 0
0x140033878  mov     rcx, rdi; this
0x14003387b  mov     [rsp+80h+var_60], rax; int *
0x140033880  mov     [rbp+var_28], 0
0x140033888  mov     [rbp+arg_0], 0
0x14003388f  mov     [rbp+var_20], 0
0x140033897  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x14003389c  mov     ebx, eax
0x14003389e  test    eax, eax
0x1400338a0  js      short loc_1400338F1
0x1400338a2  mov     rcx, [rbp+var_28]
0x1400338a6  mov     r9d, esi
0x1400338a9  mov     rdx, [rbp+arg_28]
0x1400338ad  mov     r8, r14
0x1400338b0  mov     [rsp+80h+var_58], rdx; struct IWbemServices *
0x1400338b5  mov     rdx, r15
0x1400338b8  mov     [rsp+80h+var_60], r12; int
0x1400338bd  mov     rax, [rcx]
0x1400338c0  mov     rax, [rax+0A0h]
0x1400338c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400338cc  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x1400338d0  mov     ebx, eax
0x1400338d2  mov     rax, [rbp+var_20]
0x1400338d6  mov     rcx, rdi; this
0x1400338d9  mov     r8, [rbp+var_10]; struct IUnknown *
0x1400338dd  mov     edx, [rbp+var_30]; int
0x1400338e0  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x1400338e5  mov     eax, [rbp+arg_0]
0x1400338e8  mov     dword ptr [rsp+80h+var_50], eax; int
0x1400338ec  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x1400338f1  lock dec dword ptr [rdi+20h]
0x1400338f5  test    ebx, ebx
0x1400338f7  jns     short loc_14003390A
0x1400338f9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400338ff  mov     rcx, rax
0x140033902  mov     edx, ebx
0x140033904  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003390a  mov     rcx, cs:WPP_GLOBAL_Control
0x140033911  lea     rax, WPP_GLOBAL_Control
0x140033918  cmp     rcx, rax
0x14003391b  jz      short loc_140033941
0x14003391d  test    byte ptr [rcx+1Ch], 4
0x140033921  jz      short loc_140033941
0x140033923  cmp     byte ptr [rcx+19h], 2
0x140033927  jb      short loc_140033941
0x140033929  mov     rcx, [rcx+10h]
0x14003392d  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140033934  mov     edx, 6Ah ; 'j'
0x140033939  mov     r9d, ebx
0x14003393c  call    WPP_SF_d
0x140033941  lea     r11, [rsp+80h+var_s0]
0x140033949  mov     eax, ebx
0x14003394b  mov     rbx, [r11+38h]
0x14003394f  mov     rsi, [r11+40h]
0x140033953  mov     rsp, r11
0x140033956  pop     r15
0x140033958  pop     r14
0x14003395a  pop     r12
0x14003395c  pop     rdi
0x14003395d  pop     rbp
0x14003395e  retn
```
