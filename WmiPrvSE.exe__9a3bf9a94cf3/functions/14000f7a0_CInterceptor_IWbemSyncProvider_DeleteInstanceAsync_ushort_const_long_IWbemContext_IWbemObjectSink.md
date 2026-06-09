# CInterceptor_IWbemSyncProvider::DeleteInstanceAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x14000f7a0`
- end: `0x14000f9f8`
- name: `?DeleteInstanceAsync@CInterceptor_IWbemSyncProvider@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemServices *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000d090`
- `0x14000e9a0`
- `0x14000f7a0`
- `0x14000fa00`
- `0x14000fa50`
- `0x14000fcb0`
- `0x1400234b8`
- `0x140028cfc`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14000f7f9`
- `wbemcomn!GetMemLogObject` at `0x14000f99e`
- `wbemcomn!GetMemLogObject` at `0x14000f7f9`
- `wbemcomn!GetMemLogObject` at `0x14000f99e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000f804`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000f9a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000f804`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000f9a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_IWbemSyncProvider::DeleteInstanceAsync(
        CInterceptor_IWbemSyncProvider *this,
        unsigned __int16 *const a2,
        int a3,
        struct IWbemContext *a4,
        struct IWbemServices *a5)
{
  struct IWbemObjectSink *v9; // r12
  int v10; // ebx
  CMemoryLog *v11; // rax
  int v13; // ebx
  CMemoryLog *MemLogObject; // rax
  int v15; // [rsp+20h] [rbp-50h]
  struct IWbemServices **v16; // [rsp+28h] [rbp-48h]
  int v17; // [rsp+40h] [rbp-30h] BYREF
  int v18; // [rsp+44h] [rbp-2Ch] BYREF
  struct IWbemServices *v19; // [rsp+48h] [rbp-28h] BYREF
  struct IUnknown *v20; // [rsp+50h] [rbp-20h] BYREF
  struct IServerSecurity *v21; // [rsp+58h] [rbp-18h] BYREF
  struct IUnknown *v22; // [rsp+60h] [rbp-10h] BYREF
  __int64 v23; // [rsp+68h] [rbp-8h] BYREF
  int v24; // [rsp+A0h] [rbp+30h] BYREF

  v9 = (struct IWbemObjectSink *)a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      108,
      (unsigned int)WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (_DWORD)a2,
      a3,
      (char)a4,
      (char)a5);
  }
  v10 = -2147217372;
  if ( !*((_QWORD *)this + 41) || !*(_DWORD *)(*((_QWORD *)this + 75) + 2028LL) )
    goto LABEL_4;
  v18 = 0;
  v22 = 0;
  v21 = 0;
  v24 = 0;
  v19 = 0;
  v17 = 0;
  v20 = 0;
  v23 = 0;
  v10 = CInterceptor_IWbemSyncProvider::Begin_IWbemServices(this, &v18, &v22, &v21, &v24, &v19, &v17, &v20);
  if ( v10 >= 0 )
  {
    v13 = CMUIPreferredLanguages::Set((CMUIPreferredLanguages *)&v23, a4);
    if ( v13 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v13);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          109,
          WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
          (unsigned int)v13);
      }
    }
    v10 = CInterceptor_IWbemSyncProvider::Helper_DeleteInstanceAsync(this, v24, a2, a3, a4, v9, v19);
    CInterceptor_IWbemSyncProvider::End_IWbemServices(this, v18, v22, v21, v15, (struct IWbemServices *)v16, v17, v20);
  }
  CMUIPreferredLanguages::~CMUIPreferredLanguages((CMUIPreferredLanguages *)&v23);
  if ( v10 < 0 )
  {
LABEL_4:
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, v10);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      110,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000f7a0  mov     [rsp-28h+arg_8], rbx
0x14000f7a5  mov     [rsp-28h+arg_10], rsi
0x14000f7aa  push    rbp
0x14000f7ab  push    rdi
0x14000f7ac  push    r12
0x14000f7ae  push    r14
0x14000f7b0  push    r15
0x14000f7b2  mov     rbp, rsp
0x14000f7b5  sub     rsp, 70h
0x14000f7b9  mov     rsi, r9
0x14000f7bc  mov     r14d, r8d
0x14000f7bf  mov     r15, rdx
0x14000f7c2  mov     rdi, rcx
0x14000f7c5  lea     rax, WPP_GLOBAL_Control
0x14000f7cc  mov     r12, [rbp+arg_20]
0x14000f7d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f7d7  cmp     rcx, rax
0x14000f7da  jz      short loc_14000F7E6
0x14000f7dc  test    byte ptr [rcx+1Ch], 4
0x14000f7e0  jnz     loc_14000F968
0x14000f7e6  mov     ebx, 80041024h
0x14000f7eb  cmp     qword ptr [rdi+148h], 0
0x14000f7f3  jnz     loc_14000F94F
0x14000f7f9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000f7ff  mov     edx, ebx
0x14000f801  mov     rcx, rax
0x14000f804  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000f80a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f811  lea     rax, WPP_GLOBAL_Control
0x14000f818  cmp     rcx, rax
0x14000f81b  jnz     short loc_14000F838
0x14000f81d  mov     eax, ebx
0x14000f81f  lea     r11, [rsp+70h+var_s0]
0x14000f824  mov     rbx, [r11+38h]
0x14000f828  mov     rsi, [r11+40h]
0x14000f82c  mov     rsp, r11
0x14000f82f  pop     r15
0x14000f831  pop     r14
0x14000f833  pop     r12
0x14000f835  pop     rdi
0x14000f836  pop     rbp
0x14000f837  retn
0x14000f838  test    byte ptr [rcx+1Ch], 4
0x14000f83c  jz      short loc_14000F81D
0x14000f83e  cmp     byte ptr [rcx+19h], 2
0x14000f842  jb      short loc_14000F81D
0x14000f844  mov     edx, 6Eh ; 'n'
0x14000f849  mov     r9d, ebx
0x14000f84c  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000f853  mov     rcx, [rcx+10h]
0x14000f857  call    WPP_SF_d
0x14000f85c  jmp     short loc_14000F81D
0x14000f85e  mov     [rbp+var_2C], 0
0x14000f865  mov     [rbp+var_10], 0
0x14000f86d  mov     [rbp+var_18], 0
0x14000f875  mov     [rbp+arg_0], 0
0x14000f87c  mov     [rbp+var_28], 0
0x14000f884  mov     [rbp+var_30], 0
0x14000f88b  mov     [rbp+var_20], 0
0x14000f893  mov     [rbp+var_8], 0
0x14000f89b  lea     rax, [rbp+var_20]
0x14000f89f  mov     [rsp+70h+var_38], rax; struct IUnknown **
0x14000f8a4  lea     rax, [rbp+var_30]
0x14000f8a8  mov     [rsp+70h+var_40], rax; int *
0x14000f8ad  lea     rax, [rbp+var_28]
0x14000f8b1  mov     [rsp+70h+var_48], rax; struct IWbemServices **
0x14000f8b6  lea     rax, [rbp+arg_0]
0x14000f8ba  mov     [rsp+70h+var_50], rax; int *
0x14000f8bf  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x14000f8c3  lea     r8, [rbp+var_10]; struct IUnknown **
0x14000f8c7  lea     rdx, [rbp+var_2C]; int *
0x14000f8cb  mov     rcx, rdi; this
0x14000f8ce  call    ?Begin_IWbemServices@CInterceptor_IWbemSyncProvider@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01@Z; CInterceptor_IWbemSyncProvider::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &)
0x14000f8d3  mov     ebx, eax
0x14000f8d5  test    eax, eax
0x14000f8d7  js      short loc_14000F939
0x14000f8d9  mov     rdx, rsi; struct IWbemContext *
0x14000f8dc  lea     rcx, [rbp+var_8]; this
0x14000f8e0  call    ?Set@CMUIPreferredLanguages@@QEAAJPEAUIWbemContext@@@Z; CMUIPreferredLanguages::Set(IWbemContext *)
0x14000f8e5  mov     ebx, eax
0x14000f8e7  test    eax, eax
0x14000f8e9  js      loc_14000F99E
0x14000f8ef  mov     rax, [rbp+var_28]
0x14000f8f3  mov     [rsp+70h+var_40], rax; struct IWbemServices *
0x14000f8f8  mov     [rsp+70h+var_48], r12; struct IWbemServices *
0x14000f8fd  mov     [rsp+70h+var_50], rsi; int
0x14000f902  mov     r9d, r14d; int
0x14000f905  mov     r8, r15; unsigned __int16 *
0x14000f908  mov     edx, [rbp+arg_0]; int
0x14000f90b  mov     rcx, rdi; this
0x14000f90e  call    ?Helper_DeleteInstanceAsync@CInterceptor_IWbemSyncProvider@@AEAAJHQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z; CInterceptor_IWbemSyncProvider::Helper_DeleteInstanceAsync(int,ushort * const,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)
0x14000f913  mov     ebx, eax
0x14000f915  mov     rax, [rbp+var_20]
0x14000f919  mov     [rsp+70h+var_38], rax; struct IUnknown *
0x14000f91e  mov     eax, [rbp+var_30]
0x14000f921  mov     dword ptr [rsp+70h+var_40], eax; int
0x14000f925  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x14000f929  mov     r8, [rbp+var_10]; struct IUnknown *
0x14000f92d  mov     edx, [rbp+var_2C]; int
0x14000f930  mov     rcx, rdi; this
0x14000f933  call    ?End_IWbemServices@CInterceptor_IWbemSyncProvider@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemSyncProvider::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x14000f938  nop
0x14000f939  lea     rcx, [rbp+var_8]; this
0x14000f93d  call    ??1CMUIPreferredLanguages@@QEAA@XZ; CMUIPreferredLanguages::~CMUIPreferredLanguages(void)
0x14000f942  test    ebx, ebx
0x14000f944  jns     loc_14000F80A
0x14000f94a  jmp     loc_14000F7F9
0x14000f94f  mov     rax, [rdi+258h]
0x14000f956  cmp     dword ptr [rax+7ECh], 0
0x14000f95d  jz      loc_14000F7F9
0x14000f963  jmp     loc_14000F85E
0x14000f968  cmp     byte ptr [rcx+19h], 5
0x14000f96c  jb      loc_14000F7E6
0x14000f972  mov     edx, 6Ch ; 'l'
0x14000f977  mov     [rsp+70h+var_40], r12
0x14000f97c  mov     [rsp+70h+var_48], rsi
0x14000f981  mov     dword ptr [rsp+70h+var_50], r14d
0x14000f986  mov     r9, r15
0x14000f989  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000f990  mov     rcx, [rcx+10h]
0x14000f994  call    WPP_SF_Sdqq
0x14000f999  jmp     loc_14000F7E6
0x14000f99e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000f9a4  mov     edx, ebx
0x14000f9a6  mov     rcx, rax
0x14000f9a9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000f9af  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f9b6  lea     rax, WPP_GLOBAL_Control
0x14000f9bd  cmp     rcx, rax
0x14000f9c0  jz      loc_14000F8EF
0x14000f9c6  test    byte ptr [rcx+1Ch], 4
0x14000f9ca  jz      loc_14000F8EF
0x14000f9d0  cmp     byte ptr [rcx+19h], 2
0x14000f9d4  jb      loc_14000F8EF
0x14000f9da  mov     edx, 6Dh ; 'm'
0x14000f9df  mov     r9d, ebx
0x14000f9e2  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000f9e9  mov     rcx, [rcx+10h]
0x14000f9ed  call    WPP_SF_d
0x14000f9f2  jmp     loc_14000F8EF
```
