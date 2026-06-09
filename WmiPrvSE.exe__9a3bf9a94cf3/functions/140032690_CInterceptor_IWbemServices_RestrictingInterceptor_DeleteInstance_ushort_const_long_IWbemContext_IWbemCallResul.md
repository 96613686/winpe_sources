# CInterceptor_IWbemServices_RestrictingInterceptor::DeleteInstance(ushort * const,long,IWbemContext *,IWbemCallResult * *)

- ea: `0x140032690`
- end: `0x14003282a`
- name: `?DeleteInstance@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAGJPEAUIWbemContext@@PEAPEAUIWbemCallResult@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(CInterceptor_IWbemServices_RestrictingInterceptor *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemCallResult **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400234b8`
- `0x1400310f0`
- `0x140032690`
- `0x140032b60`
- `0x140035c5c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400327cb`
- `wbemcomn!GetMemLogObject` at `0x1400327cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400327d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400327d6`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::DeleteInstance(
        CInterceptor_IWbemServices_RestrictingInterceptor *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemCallResult **a5)
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
    WPP_SF_Sdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, a3, (_DWORD)a2, a3, (char)a4);
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
            + 16))(
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids, (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140032690  mov     [rsp-28h+arg_8], rbx
0x140032695  mov     [rsp-28h+arg_10], rsi
0x14003269a  push    rbp
0x14003269b  push    rdi
0x14003269c  push    r13
0x14003269e  push    r14
0x1400326a0  push    r15
0x1400326a2  mov     rbp, rsp
0x1400326a5  sub     rsp, 80h
0x1400326ac  mov     rsi, r9
0x1400326af  mov     r14d, r8d
0x1400326b2  mov     r15, rdx
0x1400326b5  mov     rdi, rcx
0x1400326b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400326bf  lea     r13, WPP_GLOBAL_Control
0x1400326c6  cmp     rcx, r13
0x1400326c9  jz      short loc_1400326F2
0x1400326cb  test    byte ptr [rcx+1Ch], 4
0x1400326cf  jz      short loc_1400326F2
0x1400326d1  cmp     byte ptr [rcx+19h], 5
0x1400326d5  jb      short loc_1400326F2
0x1400326d7  mov     rcx, [rcx+10h]
0x1400326db  mov     edx, 61h ; 'a'
0x1400326e0  mov     [rsp+80h+var_58], r9
0x1400326e5  mov     r9, r15
0x1400326e8  mov     dword ptr [rsp+80h+var_60], r8d
0x1400326ed  call    WPP_SF_Sdq
0x1400326f2  lock inc dword ptr [rdi+20h]
0x1400326f6  cmp     dword ptr [rdi+1Ch], 1
0x1400326fa  jnz     short loc_140032706
0x1400326fc  mov     ebx, 80041033h
0x140032701  jmp     loc_1400327C3
0x140032706  lea     rax, [rbp+var_20]
0x14003270a  mov     [rbp+var_30], 0
0x140032711  mov     [rsp+80h+var_48], rax; struct IUnknown **
0x140032716  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x14003271a  lea     rax, [rbp+arg_0]
0x14003271e  mov     [rbp+var_10], 0
0x140032726  mov     [rsp+80h+var_50], rax; int *
0x14003272b  lea     r8, [rbp+var_10]; struct IUnknown **
0x14003272f  lea     rax, [rbp+var_28]
0x140032733  mov     [rbp+var_18], 0
0x14003273b  mov     [rsp+80h+var_58], rax; struct IWbemServices *
0x140032740  lea     rdx, [rbp+var_30]; int *
0x140032744  lea     rax, [rbp+var_2C]
0x140032748  mov     [rbp+var_2C], 0
0x14003274f  mov     rcx, rdi; this
0x140032752  mov     [rsp+80h+var_60], rax; int *
0x140032757  mov     [rbp+var_28.lpVtbl], 0
0x14003275f  mov     [rbp+arg_0], 0
0x140032766  mov     [rbp+var_20], 0
0x14003276e  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x140032773  mov     ebx, eax
0x140032775  test    eax, eax
0x140032777  js      short loc_1400327C3
0x140032779  mov     rcx, [rbp+var_28.lpVtbl]
0x14003277d  mov     r9, rsi
0x140032780  mov     rdx, [rbp+arg_20]
0x140032784  mov     r8d, r14d
0x140032787  mov     [rsp+80h+var_60], rdx; int
0x14003278c  mov     rdx, r15
0x14003278f  mov     rax, [rcx]
0x140032792  mov     rax, [rax+80h]
0x140032799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003279e  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x1400327a2  mov     ebx, eax
0x1400327a4  mov     rax, [rbp+var_20]
0x1400327a8  mov     rcx, rdi; this
0x1400327ab  mov     r8, [rbp+var_10]; struct IUnknown *
0x1400327af  mov     edx, [rbp+var_30]; int
0x1400327b2  mov     [rsp+80h+var_48], rax; struct IUnknown *
0x1400327b7  mov     eax, [rbp+arg_0]
0x1400327ba  mov     dword ptr [rsp+80h+var_50], eax; int
0x1400327be  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x1400327c3  lock dec dword ptr [rdi+20h]
0x1400327c7  test    ebx, ebx
0x1400327c9  jns     short loc_1400327DC
0x1400327cb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400327d1  mov     rcx, rax
0x1400327d4  mov     edx, ebx
0x1400327d6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400327dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400327e3  cmp     rcx, r13
0x1400327e6  jz      short loc_14003280C
0x1400327e8  test    byte ptr [rcx+1Ch], 4
0x1400327ec  jz      short loc_14003280C
0x1400327ee  cmp     byte ptr [rcx+19h], 2
0x1400327f2  jb      short loc_14003280C
0x1400327f4  mov     rcx, [rcx+10h]
0x1400327f8  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x1400327ff  mov     edx, 62h ; 'b'
0x140032804  mov     r9d, ebx
0x140032807  call    WPP_SF_d
0x14003280c  lea     r11, [rsp+80h+var_s0]
0x140032814  mov     eax, ebx
0x140032816  mov     rbx, [r11+38h]
0x14003281a  mov     rsi, [r11+40h]
0x14003281e  mov     rsp, r11
0x140032821  pop     r15
0x140032823  pop     r14
0x140032825  pop     r13
0x140032827  pop     rdi
0x140032828  pop     rbp
0x140032829  retn
```
