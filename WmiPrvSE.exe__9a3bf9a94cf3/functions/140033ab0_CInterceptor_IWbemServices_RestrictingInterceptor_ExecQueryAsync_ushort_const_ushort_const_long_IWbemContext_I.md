# CInterceptor_IWbemServices_RestrictingInterceptor::ExecQueryAsync(ushort * const,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140033ab0`
- end: `0x140033c46`
- name: `?ExecQueryAsync@CInterceptor_IWbemServices_RestrictingInterceptor@@UEAAJQEAG0JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
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
- `0x140033ab0`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140033be8`
- `wbemcomn!GetMemLogObject` at `0x140033be8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033bf3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140033bf3`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemServices_RestrictingInterceptor::ExecQueryAsync(
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
      107,
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
      v12 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *const, unsigned __int16 *const, _QWORD))v17->lpVtbl->ExecQueryAsync)(
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
      108,
      WPP_2ef91c586edc35547bed035b48d4f238_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140033ab0  push    rbp
0x140033ab2  push    rbx
0x140033ab3  push    rsi
0x140033ab4  push    rdi
0x140033ab5  push    r12
0x140033ab7  push    r13
0x140033ab9  push    r14
0x140033abb  push    r15
0x140033abd  lea     rbp, [rsp-0Fh]
0x140033ac2  sub     rsp, 88h
0x140033ac9  mov     esi, r9d
0x140033acc  mov     r14, r8
0x140033acf  mov     r15, rdx
0x140033ad2  mov     rdi, rcx
0x140033ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x140033adc  lea     rax, WPP_GLOBAL_Control
0x140033ae3  mov     r12, [rbp+47h+arg_28]
0x140033ae7  mov     r13, [rbp+47h+arg_20]
0x140033aeb  cmp     rcx, rax
0x140033aee  jz      short loc_140033B28
0x140033af0  test    byte ptr [rcx+1Ch], 4
0x140033af4  jz      short loc_140033B28
0x140033af6  cmp     byte ptr [rcx+19h], 5
0x140033afa  jb      short loc_140033B28
0x140033afc  mov     rcx, [rcx+10h]
0x140033b00  mov     edx, 6Bh ; 'k'
0x140033b05  mov     [rsp+0C0h+var_88], r12
0x140033b0a  mov     [rsp+0C0h+var_90], r13
0x140033b0f  mov     dword ptr [rsp+0C0h+var_98], r9d
0x140033b14  mov     r9, r15
0x140033b17  mov     [rsp+0C0h+var_A0], r8
0x140033b1c  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140033b23  call    WPP_SF_SSdqq
0x140033b28  lock inc dword ptr [rdi+20h]
0x140033b2c  xor     ebx, ebx
0x140033b2e  cmp     dword ptr [rdi+1Ch], 1
0x140033b32  jnz     short loc_140033B3E
0x140033b34  mov     ebx, 80041033h
0x140033b39  jmp     loc_140033BE0
0x140033b3e  lea     rax, [rbp+47h+var_60]
0x140033b42  mov     [rbp+47h+var_70], ebx
0x140033b45  mov     [rsp+0C0h+var_88], rax; struct IUnknown **
0x140033b4a  lea     r9, [rbp+47h+var_58]; struct IServerSecurity **
0x140033b4e  lea     rax, [rbp+47h+arg_0]
0x140033b52  mov     [rbp+47h+var_50], rbx
0x140033b56  mov     [rsp+0C0h+var_90], rax; int *
0x140033b5b  lea     r8, [rbp+47h+var_50]; struct IUnknown **
0x140033b5f  lea     rax, [rbp+47h+var_68]
0x140033b63  mov     [rbp+47h+var_58], rbx
0x140033b67  mov     [rsp+0C0h+var_98], rax; struct IWbemServices **
0x140033b6c  lea     rdx, [rbp+47h+var_70]; int *
0x140033b70  lea     rax, [rbp+47h+var_6C]
0x140033b74  mov     [rbp+47h+var_6C], ebx
0x140033b77  mov     rcx, rdi; this
0x140033b7a  mov     [rsp+0C0h+var_A0], rax; int *
0x140033b7f  mov     [rbp+47h+var_68], rbx
0x140033b83  mov     [rbp+47h+arg_0], ebx
0x140033b86  mov     [rbp+47h+var_60], rbx
0x140033b8a  call    ?Begin_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01PEAUIWbemContext@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &,IWbemContext *)
0x140033b8f  mov     ebx, eax
0x140033b91  test    eax, eax
0x140033b93  js      short loc_140033BE0
0x140033b95  mov     rcx, [rbp+47h+var_68]
0x140033b99  mov     r9d, esi
0x140033b9c  mov     [rsp+0C0h+var_98], r12; struct IWbemServices *
0x140033ba1  mov     r8, r14
0x140033ba4  mov     rdx, r15
0x140033ba7  mov     [rsp+0C0h+var_A0], r13; int
0x140033bac  mov     rax, [rcx]
0x140033baf  mov     rax, [rax+0A8h]
0x140033bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033bbb  mov     r9, [rbp+47h+var_58]; struct IServerSecurity *
0x140033bbf  mov     ebx, eax
0x140033bc1  mov     rax, [rbp+47h+var_60]
0x140033bc5  mov     rcx, rdi; this
0x140033bc8  mov     r8, [rbp+47h+var_50]; struct IUnknown *
0x140033bcc  mov     edx, [rbp+47h+var_70]; int
0x140033bcf  mov     [rsp+0C0h+var_88], rax; struct IUnknown *
0x140033bd4  mov     eax, [rbp+47h+arg_0]
0x140033bd7  mov     dword ptr [rsp+0C0h+var_90], eax; int
0x140033bdb  call    ?End_IWbemServices@CInterceptor_IWbemServices_RestrictingInterceptor@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemServices_RestrictingInterceptor::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x140033be0  lock dec dword ptr [rdi+20h]
0x140033be4  test    ebx, ebx
0x140033be6  jns     short loc_140033BF9
0x140033be8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140033bee  mov     rcx, rax
0x140033bf1  mov     edx, ebx
0x140033bf3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140033bf9  mov     rcx, cs:WPP_GLOBAL_Control
0x140033c00  lea     rax, WPP_GLOBAL_Control
0x140033c07  cmp     rcx, rax
0x140033c0a  jz      short loc_140033C30
0x140033c0c  test    byte ptr [rcx+1Ch], 4
0x140033c10  jz      short loc_140033C30
0x140033c12  cmp     byte ptr [rcx+19h], 2
0x140033c16  jb      short loc_140033C30
0x140033c18  mov     rcx, [rcx+10h]
0x140033c1c  lea     r8, WPP_2ef91c586edc35547bed035b48d4f238_Traceguids
0x140033c23  mov     edx, 6Ch ; 'l'
0x140033c28  mov     r9d, ebx
0x140033c2b  call    WPP_SF_d
0x140033c30  mov     eax, ebx
0x140033c32  add     rsp, 88h
0x140033c39  pop     r15
0x140033c3b  pop     r14
0x140033c3d  pop     r13
0x140033c3f  pop     r12
0x140033c41  pop     rdi
0x140033c42  pop     rsi
0x140033c43  pop     rbx
0x140033c44  pop     rbp
0x140033c45  retn
```
