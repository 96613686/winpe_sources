# CInterceptor_IWbemServices_RestrictingInterceptor::ExecMethodAsync(ushort * const,ushort * const,long,IWbemContext *,IWbemClassObject *,IWbemObjectSink *)

- ea: `0x140033030`
- end: `0x1400331d8`
- name: `?ExecMethodAsync@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAG0JPEAUIWbemContext@@PEAUIWbemClassObject@@PEAUIWbemObjectSink@@@Z`
- size: `424`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemServices_RestrictingInterceptor *__hidden this@<rcx>, unsigned __int16 *const@<rdx>, unsigned __int16 *const@<r8>, int@<r9d>, struct IWbemContext *, struct IWbemClassObject *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400292f8`
- `0x1400310f0`
- `0x140032b60`
- `0x140033030`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003317a`
- `wbemcomn!GetMemLogObject` at `0x14003317a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033185`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033185`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::ExecMethodAsync(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemServices *a6,
        struct IWbemContext *a7)
{
  struct IWbemServices *v11; // r13
  int v12; // ebx
  CMemoryLog *MemLogObject; // rax
  int v15; // [rsp+20h] [rbp-61h]
  int v16; // [rsp+50h] [rbp-31h] BYREF
  int v17; // [rsp+54h] [rbp-2Dh] BYREF
  struct IWbemServices *v18; // [rsp+58h] [rbp-29h] BYREF
  struct IUnknown *v19; // [rsp+60h] [rbp-21h] BYREF
  struct IServerSecurity *v20; // [rsp+68h] [rbp-19h] BYREF
  struct IUnknown *v21; // [rsp+70h] [rbp-11h] BYREF
  int v22; // [rsp+D0h] [rbp+4Fh] BYREF

  v11 = a6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdqqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      115,
      (unsigned int)WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      a4,
      (char)a6,
      (char)a5,
      (char)a7);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v12 = -2147217357;
  }
  else
  {
    v16 = 0;
    v21 = 0;
    v20 = 0;
    v17 = 0;
    v18 = 0;
    v22 = 0;
    v19 = 0;
    v12 = CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(
            (struct IUnknown **)this,
            &v16,
            &v21,
            &v20,
            &v17,
            &v18,
            &v22,
            &v19);
    if ( v12 >= 0 )
    {
      v15 = (int)a5;
      v12 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *const, unsigned __int16 *const, _QWORD))v18->lpVtbl->ExecMethodAsync)(
              v18,
              a2,
              a3,
              a4);
      CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(this, v16, v21, v20, v15, v11, v22, v19);
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
      116,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140033030  push    rbp
0x140033032  push    rbx
0x140033033  push    rsi
0x140033034  push    rdi
0x140033035  push    r12
0x140033037  push    r13
0x140033039  push    r14
0x14003303b  push    r15
0x14003303d  lea     rbp, [rsp-7]
0x140033042  sub     rsp, 88h
0x140033049  mov     esi, r9d
0x14003304c  mov     r14, r8
0x14003304f  mov     r15, rdx
0x140033052  mov     rdi, rcx
0x140033055  mov     rcx, cs:WPP_GLOBAL_Control
0x14003305c  lea     rax, WPP_GLOBAL_Control
0x140033063  mov     r12, [rbp+3Fh+arg_30]
0x140033067  mov     r13, [rbp+3Fh+arg_28]
0x14003306b  cmp     rcx, rax
0x14003306e  jz      short loc_1400330B1
0x140033070  test    byte ptr [rcx+1Ch], 4
0x140033074  jz      short loc_1400330B1
0x140033076  cmp     byte ptr [rcx+19h], 5
0x14003307a  jb      short loc_1400330B1
0x14003307c  mov     rax, [rbp+3Fh+arg_20]
0x140033080  mov     edx, 73h ; 's'
0x140033085  mov     rcx, [rcx+10h]
0x140033089  mov     [rsp+0C0h+var_80], r12; struct IWbemContext *
0x14003308e  mov     [rsp+0C0h+var_88], rax
0x140033093  mov     [rsp+0C0h+var_90], r13
0x140033098  mov     dword ptr [rsp+0C0h+var_98], r9d
0x14003309d  mov     r9, r15
0x1400330a0  mov     [rsp+0C0h+var_A0], r8
0x1400330a5  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x1400330ac  call    WPP_SF_SSdqqq
0x1400330b1  lock inc dword ptr [rdi+20h]
0x1400330b5  xor     ebx, ebx
0x1400330b7  cmp     dword ptr [rdi+1Ch], 1
0x1400330bb  jnz     short loc_1400330C7
0x1400330bd  mov     ebx, 80041033h
0x1400330c2  jmp     loc_140033172
0x1400330c7  lea     rax, [rbp+3Fh+var_60]
0x1400330cb  mov     [rbp+3Fh+var_70], ebx
0x1400330ce  mov     [rsp+0C0h+var_88], rax; struct IUnknown **
0x1400330d3  lea     r9, [rbp+3Fh+var_58]; struct IServerSecurity **
0x1400330d7  lea     rax, [rbp+3Fh+arg_0]
0x1400330db  mov     [rbp+3Fh+var_50], rbx
0x1400330df  mov     [rsp+0C0h+var_90], rax; int *
0x1400330e4  lea     r8, [rbp+3Fh+var_50]; struct IUnknown **
0x1400330e8  lea     rax, [rbp+3Fh+var_68]
0x1400330ec  mov     [rbp+3Fh+var_58], rbx
0x1400330f0  mov     [rsp+0C0h+var_98], rax; struct IWbemServices **
0x1400330f5  lea     rdx, [rbp+3Fh+var_70]; int *
0x1400330f9  lea     rax, [rbp+3Fh+var_6C]
0x1400330fd  mov     [rbp+3Fh+var_6C], ebx
0x140033100  mov     rcx, rdi; this
0x140033103  mov     [rsp+0C0h+var_A0], rax; int *
0x140033108  mov     [rbp+3Fh+var_68], rbx
0x14003310c  mov     [rbp+3Fh+arg_0], ebx
0x14003310f  mov     [rbp+3Fh+var_60], rbx
0x140033113  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x140033118  mov     ebx, eax
0x14003311a  test    eax, eax
0x14003311c  js      short loc_140033172
0x14003311e  mov     rcx, [rbp+3Fh+var_68]
0x140033122  mov     r9d, esi
0x140033125  mov     rdx, [rbp+3Fh+arg_20]
0x140033129  mov     r8, r14
0x14003312c  mov     [rsp+0C0h+var_90], r12
0x140033131  mov     [rsp+0C0h+var_98], r13; struct IWbemServices *
0x140033136  mov     rax, [rcx]
0x140033139  mov     [rsp+0C0h+var_A0], rdx; int
0x14003313e  mov     rdx, r15
0x140033141  mov     rax, [rax+0C8h]
0x140033148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003314d  mov     r9, [rbp+3Fh+var_58]; struct IServerSecurity *
0x140033151  mov     ebx, eax
0x140033153  mov     rax, [rbp+3Fh+var_60]
0x140033157  mov     rcx, rdi; this
0x14003315a  mov     r8, [rbp+3Fh+var_50]; struct IUnknown *
0x14003315e  mov     edx, [rbp+3Fh+var_70]; int
0x140033161  mov     [rsp+0C0h+var_88], rax; struct IUnknown *
0x140033166  mov     eax, [rbp+3Fh+arg_0]
0x140033169  mov     dword ptr [rsp+0C0h+var_90], eax; int
0x14003316d  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140033172  lock dec dword ptr [rdi+20h]
0x140033176  test    ebx, ebx
0x140033178  jns     short loc_14003318B
0x14003317a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140033180  mov     rcx, rax
0x140033183  mov     edx, ebx
0x140033185  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003318b  mov     rcx, cs:WPP_GLOBAL_Control
0x140033192  lea     rax, WPP_GLOBAL_Control
0x140033199  cmp     rcx, rax
0x14003319c  jz      short loc_1400331C2
0x14003319e  test    byte ptr [rcx+1Ch], 4
0x1400331a2  jz      short loc_1400331C2
0x1400331a4  cmp     byte ptr [rcx+19h], 2
0x1400331a8  jb      short loc_1400331C2
0x1400331aa  mov     rcx, [rcx+10h]
0x1400331ae  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x1400331b5  mov     edx, 74h ; 't'
0x1400331ba  mov     r9d, ebx
0x1400331bd  call    WPP_SF_d
0x1400331c2  mov     eax, ebx
0x1400331c4  add     rsp, 88h
0x1400331cb  pop     r15
0x1400331cd  pop     r14
0x1400331cf  pop     r13
0x1400331d1  pop     r12
0x1400331d3  pop     rdi
0x1400331d4  pop     rsi
0x1400331d5  pop     rbx
0x1400331d6  pop     rbp
0x1400331d7  retn
```
