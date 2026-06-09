# CInterceptor_IWbemServices_RestrictingInterceptor::ExecMethod(ushort * const,ushort * const,long,IWbemContext *,IWbemClassObject *,IWbemClassObject * *,IWbemCallResult * *)

- ea: `0x140032d20`
- end: `0x140032ecb`
- name: `?ExecMethod@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAG0JPEAUIWbemContext@@PEAUIWbemClassObject@@PEAPEAU3@PEAPEAUIWbemCallResult@@@Z`
- size: `427`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this@<rcx>, unsigned __int16 *const@<rdx>, unsigned __int16 *const@<r8>, int@<r9d>, struct IWbemContext *, struct IWbemClassObject *, struct IWbemClassObject **, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140029824`
- `0x1400310f0`
- `0x140032b60`
- `0x140032d20`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140032e6d`
- `wbemcomn!GetMemLogObject` at `0x140032e6d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140032e78`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140032e78`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::ExecMethod(
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
  int v15; // [rsp+50h] [rbp-31h] BYREF
  int v16; // [rsp+54h] [rbp-2Dh] BYREF
  struct IWbemServices *v17; // [rsp+58h] [rbp-29h] BYREF
  struct IUnknown *v18; // [rsp+60h] [rbp-21h] BYREF
  struct IServerSecurity *v19; // [rsp+68h] [rbp-19h] BYREF
  struct IUnknown *v20; // [rsp+70h] [rbp-11h] BYREF
  int v21; // [rsp+D0h] [rbp+4Fh] BYREF

  v10 = a6;
  v11 = (int)a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      113,
      (unsigned int)WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      a4,
      (char)a6,
      (char)a5);
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
      v12 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *const, unsigned __int16 *const, _QWORD))v17->lpVtbl->ExecMethod)(
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
      114,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140032d20  push    rbp
0x140032d22  push    rbx
0x140032d23  push    rsi
0x140032d24  push    rdi
0x140032d25  push    r12
0x140032d27  push    r13
0x140032d29  push    r14
0x140032d2b  push    r15
0x140032d2d  lea     rbp, [rsp-7]
0x140032d32  sub     rsp, 88h
0x140032d39  mov     esi, r9d
0x140032d3c  mov     r14, r8
0x140032d3f  mov     r15, rdx
0x140032d42  mov     rdi, rcx
0x140032d45  mov     rcx, cs:WPP_GLOBAL_Control
0x140032d4c  lea     rax, WPP_GLOBAL_Control
0x140032d53  mov     r12, [rbp+3Fh+arg_28]
0x140032d57  mov     r13, [rbp+3Fh+arg_20]
0x140032d5b  cmp     rcx, rax
0x140032d5e  jz      short loc_140032D98
0x140032d60  test    byte ptr [rcx+1Ch], 4
0x140032d64  jz      short loc_140032D98
0x140032d66  cmp     byte ptr [rcx+19h], 5
0x140032d6a  jb      short loc_140032D98
0x140032d6c  mov     rcx, [rcx+10h]
0x140032d70  mov     edx, 71h ; 'q'
0x140032d75  mov     [rsp+0C0h+var_88], r13
0x140032d7a  mov     [rsp+0C0h+var_90], r12
0x140032d7f  mov     dword ptr [rsp+0C0h+var_98], r9d
0x140032d84  mov     r9, r15
0x140032d87  mov     [rsp+0C0h+var_A0], r8
0x140032d8c  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140032d93  call    WPP_SF_SSdqq
0x140032d98  lock inc dword ptr [rdi+20h]
0x140032d9c  xor     ebx, ebx
0x140032d9e  cmp     dword ptr [rdi+1Ch], 1
0x140032da2  jnz     short loc_140032DAE
0x140032da4  mov     ebx, 80041033h
0x140032da9  jmp     loc_140032E65
0x140032dae  lea     rax, [rbp+3Fh+var_60]
0x140032db2  mov     [rbp+3Fh+var_70], ebx
0x140032db5  mov     [rsp+0C0h+var_88], rax; struct IUnknown **
0x140032dba  lea     r9, [rbp+3Fh+var_58]; struct IServerSecurity **
0x140032dbe  lea     rax, [rbp+3Fh+arg_0]
0x140032dc2  mov     [rbp+3Fh+var_50], rbx
0x140032dc6  mov     [rsp+0C0h+var_90], rax; int *
0x140032dcb  lea     r8, [rbp+3Fh+var_50]; struct IUnknown **
0x140032dcf  lea     rax, [rbp+3Fh+var_68]
0x140032dd3  mov     [rbp+3Fh+var_58], rbx
0x140032dd7  mov     [rsp+0C0h+var_98], rax; struct IWbemServices **
0x140032ddc  lea     rdx, [rbp+3Fh+var_70]; int *
0x140032de0  lea     rax, [rbp+3Fh+var_6C]
0x140032de4  mov     [rbp+3Fh+var_6C], ebx
0x140032de7  mov     rcx, rdi; this
0x140032dea  mov     [rsp+0C0h+var_A0], rax; int *
0x140032def  mov     [rbp+3Fh+var_68], rbx
0x140032df3  mov     [rbp+3Fh+arg_0], ebx
0x140032df6  mov     [rbp+3Fh+var_60], rbx
0x140032dfa  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x140032dff  mov     ebx, eax
0x140032e01  test    eax, eax
0x140032e03  js      short loc_140032E65
0x140032e05  mov     rcx, [rbp+3Fh+var_68]
0x140032e09  mov     r9d, esi
0x140032e0c  mov     rdx, [rbp+3Fh+arg_38]
0x140032e13  mov     r8, r14
0x140032e16  mov     [rsp+0C0h+var_88], rdx
0x140032e1b  mov     rdx, [rbp+3Fh+arg_30]
0x140032e1f  mov     rax, [rcx]
0x140032e22  mov     [rsp+0C0h+var_90], rdx
0x140032e27  mov     rdx, r15
0x140032e2a  mov     [rsp+0C0h+var_98], r12; struct IWbemServices *
0x140032e2f  mov     [rsp+0C0h+var_A0], r13; int
0x140032e34  mov     rax, [rax+0C0h]
0x140032e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032e40  mov     r9, [rbp+3Fh+var_58]; struct IServerSecurity *
0x140032e44  mov     ebx, eax
0x140032e46  mov     rax, [rbp+3Fh+var_60]
0x140032e4a  mov     rcx, rdi; this
0x140032e4d  mov     r8, [rbp+3Fh+var_50]; struct IUnknown *
0x140032e51  mov     edx, [rbp+3Fh+var_70]; int
0x140032e54  mov     [rsp+0C0h+var_88], rax; struct IUnknown *
0x140032e59  mov     eax, [rbp+3Fh+arg_0]
0x140032e5c  mov     dword ptr [rsp+0C0h+var_90], eax; int
0x140032e60  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140032e65  lock dec dword ptr [rdi+20h]
0x140032e69  test    ebx, ebx
0x140032e6b  jns     short loc_140032E7E
0x140032e6d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140032e73  mov     rcx, rax
0x140032e76  mov     edx, ebx
0x140032e78  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140032e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140032e85  lea     rax, WPP_GLOBAL_Control
0x140032e8c  cmp     rcx, rax
0x140032e8f  jz      short loc_140032EB5
0x140032e91  test    byte ptr [rcx+1Ch], 4
0x140032e95  jz      short loc_140032EB5
0x140032e97  cmp     byte ptr [rcx+19h], 2
0x140032e9b  jb      short loc_140032EB5
0x140032e9d  mov     rcx, [rcx+10h]
0x140032ea1  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140032ea8  mov     edx, 72h ; 'r'
0x140032ead  mov     r9d, ebx
0x140032eb0  call    WPP_SF_d
0x140032eb5  mov     eax, ebx
0x140032eb7  add     rsp, 88h
0x140032ebe  pop     r15
0x140032ec0  pop     r14
0x140032ec2  pop     r13
0x140032ec4  pop     r12
0x140032ec6  pop     rdi
0x140032ec7  pop     rsi
0x140032ec8  pop     rbx
0x140032ec9  pop     rbp
0x140032eca  retn
```
