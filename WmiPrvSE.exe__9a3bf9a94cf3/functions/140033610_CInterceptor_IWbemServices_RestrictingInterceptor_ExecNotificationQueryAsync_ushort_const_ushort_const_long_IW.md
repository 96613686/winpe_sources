# CInterceptor_IWbemServices_RestrictingInterceptor::ExecNotificationQueryAsync(ushort * const,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140033610`
- end: `0x1400337a6`
- name: `?ExecNotificationQueryAsync@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAG0JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `406`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this@<rcx>, unsigned __int16 *const@<rdx>, unsigned __int16 *const@<r8>, int@<r9d>, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140029824`
- `0x1400310f0`
- `0x140032b60`
- `0x140033610`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140033748`
- `wbemcomn!GetMemLogObject` at `0x140033748`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033753`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033753`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::ExecNotificationQueryAsync(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemServices *a6)
{
  struct IWbemServices *v10; // r12
  int v11; // r13d
  int v12; // ebx
  CMemoryLog *MemLogObject; // rax
  int v15; // [rsp+50h] [rbp-29h] BYREF
  int v16; // [rsp+54h] [rbp-25h] BYREF
  struct IWbemServices *v17; // [rsp+58h] [rbp-21h] BYREF
  struct IUnknown *v18; // [rsp+60h] [rbp-19h] BYREF
  struct IServerSecurity *v19; // [rsp+68h] [rbp-11h] BYREF
  struct IUnknown *v20; // [rsp+70h] [rbp-9h] BYREF
  int v21; // [rsp+D0h] [rbp+57h] BYREF

  v10 = a6;
  v11 = (int)a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      111,
      (unsigned int)WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      a4,
      (char)a5,
      (char)a6);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v12 = -2147217357;
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
    v12 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(
            (struct IUnknown **)this,
            &v15,
            &v20,
            &v19,
            &v16,
            &v17,
            &v21,
            &v18);
    if ( v12 >= 0 )
    {
      v12 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *const, unsigned __int16 *const, _QWORD))v17->lpVtbl->ExecNotificationQueryAsync)(
              v17,
              a2,
              a3,
              a4);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(this, v15, v20, v19, v11, v10, v21, v18);
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v12 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v12);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      112,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140033610  push    rbp
0x140033612  push    rbx
0x140033613  push    rsi
0x140033614  push    rdi
0x140033615  push    r12
0x140033617  push    r13
0x140033619  push    r14
0x14003361b  push    r15
0x14003361d  lea     rbp, [rsp-0Fh]
0x140033622  sub     rsp, 88h
0x140033629  mov     esi, r9d
0x14003362c  mov     r14, r8
0x14003362f  mov     r15, rdx
0x140033632  mov     rdi, rcx
0x140033635  mov     rcx, cs:WPP_GLOBAL_Control
0x14003363c  lea     rax, WPP_GLOBAL_Control
0x140033643  mov     r12, [rbp+47h+arg_28]
0x140033647  mov     r13, [rbp+47h+arg_20]
0x14003364b  cmp     rcx, rax
0x14003364e  jz      short loc_140033688
0x140033650  test    byte ptr [rcx+1Ch], 4
0x140033654  jz      short loc_140033688
0x140033656  cmp     byte ptr [rcx+19h], 5
0x14003365a  jb      short loc_140033688
0x14003365c  mov     rcx, [rcx+10h]
0x140033660  mov     edx, 6Fh ; 'o'
0x140033665  mov     [rsp+0C0h+var_88], r12
0x14003366a  mov     [rsp+0C0h+var_90], r13
0x14003366f  mov     dword ptr [rsp+0C0h+var_98], r9d
0x140033674  mov     r9, r15
0x140033677  mov     [rsp+0C0h+var_A0], r8
0x14003367c  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140033683  call    WPP_SF_SSdqq
0x140033688  lock inc dword ptr [rdi+20h]
0x14003368c  xor     ebx, ebx
0x14003368e  cmp     dword ptr [rdi+1Ch], 1
0x140033692  jnz     short loc_14003369E
0x140033694  mov     ebx, 80041033h
0x140033699  jmp     loc_140033740
0x14003369e  lea     rax, [rbp+47h+var_60]
0x1400336a2  mov     [rbp+47h+var_70], ebx
0x1400336a5  mov     [rsp+0C0h+var_88], rax; struct IUnknown **
0x1400336aa  lea     r9, [rbp+47h+var_58]; struct IServerSecurity **
0x1400336ae  lea     rax, [rbp+47h+arg_0]
0x1400336b2  mov     [rbp+47h+var_50], rbx
0x1400336b6  mov     [rsp+0C0h+var_90], rax; int *
0x1400336bb  lea     r8, [rbp+47h+var_50]; struct IUnknown **
0x1400336bf  lea     rax, [rbp+47h+var_68]
0x1400336c3  mov     [rbp+47h+var_58], rbx
0x1400336c7  mov     [rsp+0C0h+var_98], rax; struct IWbemServices **
0x1400336cc  lea     rdx, [rbp+47h+var_70]; int *
0x1400336d0  lea     rax, [rbp+47h+var_6C]
0x1400336d4  mov     [rbp+47h+var_6C], ebx
0x1400336d7  mov     rcx, rdi; this
0x1400336da  mov     [rsp+0C0h+var_A0], rax; int *
0x1400336df  mov     [rbp+47h+var_68], rbx
0x1400336e3  mov     [rbp+47h+arg_0], ebx
0x1400336e6  mov     [rbp+47h+var_60], rbx
0x1400336ea  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x1400336ef  mov     ebx, eax
0x1400336f1  test    eax, eax
0x1400336f3  js      short loc_140033740
0x1400336f5  mov     rcx, [rbp+47h+var_68]
0x1400336f9  mov     r9d, esi
0x1400336fc  mov     [rsp+0C0h+var_98], r12; struct IWbemServices *
0x140033701  mov     r8, r14
0x140033704  mov     rdx, r15
0x140033707  mov     [rsp+0C0h+var_A0], r13; int
0x14003370c  mov     rax, [rcx]
0x14003370f  mov     rax, [rax+0B8h]
0x140033716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003371b  mov     r9, [rbp+47h+var_58]; struct IServerSecurity *
0x14003371f  mov     ebx, eax
0x140033721  mov     rax, [rbp+47h+var_60]
0x140033725  mov     rcx, rdi; this
0x140033728  mov     r8, [rbp+47h+var_50]; struct IUnknown *
0x14003372c  mov     edx, [rbp+47h+var_70]; int
0x14003372f  mov     [rsp+0C0h+var_88], rax; struct IUnknown *
0x140033734  mov     eax, [rbp+47h+arg_0]
0x140033737  mov     dword ptr [rsp+0C0h+var_90], eax; int
0x14003373b  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140033740  lock dec dword ptr [rdi+20h]
0x140033744  test    ebx, ebx
0x140033746  jns     short loc_140033759
0x140033748  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003374e  mov     rcx, rax
0x140033751  mov     edx, ebx
0x140033753  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140033759  mov     rcx, cs:WPP_GLOBAL_Control
0x140033760  lea     rax, WPP_GLOBAL_Control
0x140033767  cmp     rcx, rax
0x14003376a  jz      short loc_140033790
0x14003376c  test    byte ptr [rcx+1Ch], 4
0x140033770  jz      short loc_140033790
0x140033772  cmp     byte ptr [rcx+19h], 2
0x140033776  jb      short loc_140033790
0x140033778  mov     rcx, [rcx+10h]
0x14003377c  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140033783  mov     edx, 70h ; 'p'
0x140033788  mov     r9d, ebx
0x14003378b  call    WPP_SF_d
0x140033790  mov     eax, ebx
0x140033792  add     rsp, 88h
0x140033799  pop     r15
0x14003379b  pop     r14
0x14003379d  pop     r13
0x14003379f  pop     r12
0x1400337a1  pop     rdi
0x1400337a2  pop     rsi
0x1400337a3  pop     rbx
0x1400337a4  pop     rbp
0x1400337a5  retn
```
