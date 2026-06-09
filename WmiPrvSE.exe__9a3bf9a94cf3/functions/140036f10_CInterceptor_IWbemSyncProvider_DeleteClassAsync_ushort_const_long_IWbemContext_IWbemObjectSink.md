# CInterceptor_IWbemSyncProvider::DeleteClassAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140036f10`
- end: `0x140037137`
- name: `?DeleteClassAsync@CInterceptor_IWbemSyncProvider@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `551`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemServices *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000d090`
- `0x14000fa00`
- `0x14000fa50`
- `0x14000fcb0`
- `0x1400234b8`
- `0x140028cfc`
- `0x140036f10`
- `0x140037d60`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140037035`
- `wbemcomn!GetMemLogObject` at `0x1400370d4`
- `wbemcomn!GetMemLogObject` at `0x140037035`
- `wbemcomn!GetMemLogObject` at `0x1400370d4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140037040`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400370df`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140037040`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400370df`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_IWbemSyncProvider::DeleteClassAsync(
        CInterceptor_IWbemSyncProvider *this,
        unsigned __int16 *const a2,
        int a3,
        struct IWbemContext *a4,
        struct IWbemServices *a5)
{
  struct IWbemObjectSink *v9; // r12
  int v10; // ebx
  int v11; // ebx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v13; // rax
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
      94,
      (unsigned int)WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (_DWORD)a2,
      a3,
      (char)a4,
      (char)a5);
  }
  v10 = -2147217372;
  if ( !*((_QWORD *)this + 41) || !*(_DWORD *)(*((_QWORD *)this + 75) + 1868LL) )
    goto LABEL_15;
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
    v11 = CMUIPreferredLanguages::Set((CMUIPreferredLanguages *)&v23, a4);
    if ( v11 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v11);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          95,
          WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
          (unsigned int)v11);
      }
    }
    v10 = CInterceptor_IWbemSyncProvider::Helper_DeleteClassAsync(this, v24, a2, a3, a4, v9, v19);
    CInterceptor_IWbemSyncProvider::End_IWbemServices(this, v18, v22, v21, v15, (struct IWbemServices *)v16, v17, v20);
  }
  CMUIPreferredLanguages::~CMUIPreferredLanguages((CMUIPreferredLanguages *)&v23);
  if ( v10 < 0 )
  {
LABEL_15:
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, v10);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      96,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140036f10  mov     r11, rsp
0x140036f13  mov     [r11+10h], rbx
0x140036f17  mov     [r11+18h], rsi
0x140036f1b  push    rbp
0x140036f1c  push    rdi
0x140036f1d  push    r12
0x140036f1f  push    r14
0x140036f21  push    r15
0x140036f23  mov     rbp, rsp
0x140036f26  sub     rsp, 70h
0x140036f2a  mov     rsi, r9
0x140036f2d  mov     r14d, r8d
0x140036f30  mov     r15, rdx
0x140036f33  mov     rdi, rcx
0x140036f36  lea     rax, WPP_GLOBAL_Control
0x140036f3d  mov     r12, [rbp+arg_20]
0x140036f41  mov     rcx, cs:WPP_GLOBAL_Control
0x140036f48  cmp     rcx, rax
0x140036f4b  jz      short loc_140036F7D
0x140036f4d  test    byte ptr [rcx+1Ch], 4
0x140036f51  jz      short loc_140036F7D
0x140036f53  cmp     byte ptr [rcx+19h], 5
0x140036f57  jb      short loc_140036F7D
0x140036f59  mov     edx, 5Eh ; '^'
0x140036f5e  mov     [r11-68h], r12
0x140036f62  mov     [r11-70h], r9
0x140036f66  mov     [r11-78h], r8d
0x140036f6a  mov     r9, r15
0x140036f6d  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140036f74  mov     rcx, [rcx+10h]
0x140036f78  call    WPP_SF_Sdqq
0x140036f7d  mov     ebx, 80041024h
0x140036f82  cmp     qword ptr [rdi+148h], 0
0x140036f8a  jz      loc_1400370D4
0x140036f90  mov     rax, [rdi+258h]
0x140036f97  cmp     dword ptr [rax+74Ch], 0
0x140036f9e  jz      loc_1400370D4
0x140036fa4  mov     [rbp+var_2C], 0
0x140036fab  mov     [rbp+var_10], 0
0x140036fb3  mov     [rbp+var_18], 0
0x140036fbb  mov     [rbp+arg_0], 0
0x140036fc2  mov     [rbp+var_28], 0
0x140036fca  mov     [rbp+var_30], 0
0x140036fd1  mov     [rbp+var_20], 0
0x140036fd9  mov     [rbp+var_8], 0
0x140036fe1  lea     rax, [rbp+var_20]
0x140036fe5  mov     [rsp+70h+var_38], rax; struct IUnknown **
0x140036fea  lea     rax, [rbp+var_30]
0x140036fee  mov     [rsp+70h+var_40], rax; int *
0x140036ff3  lea     rax, [rbp+var_28]
0x140036ff7  mov     [rsp+70h+var_48], rax; struct IWbemServices **
0x140036ffc  lea     rax, [rbp+arg_0]
0x140037000  mov     [rsp+70h+var_50], rax; int *
0x140037005  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x140037009  lea     r8, [rbp+var_10]; struct IUnknown **
0x14003700d  lea     rdx, [rbp+var_2C]; int *
0x140037011  mov     rcx, rdi; this
0x140037014  call    ?Begin_IWbemServices@CInterceptor_IWbemSyncProvider@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01@Z; CInterceptor_IWbemSyncProvider::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &)
0x140037019  mov     ebx, eax
0x14003701b  test    eax, eax
0x14003701d  js      loc_1400370C7
0x140037023  mov     rdx, rsi; struct IWbemContext *
0x140037026  lea     rcx, [rbp+var_8]; this
0x14003702a  call    ?Set@CMUIPreferredLanguages@@QEAAJPEAUIWbemContext@@@Z; CMUIPreferredLanguages::Set(IWbemContext *)
0x14003702f  mov     ebx, eax
0x140037031  test    eax, eax
0x140037033  jns     short loc_14003707D
0x140037035  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003703b  mov     edx, ebx
0x14003703d  mov     rcx, rax
0x140037040  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140037046  mov     rcx, cs:WPP_GLOBAL_Control
0x14003704d  lea     rax, WPP_GLOBAL_Control
0x140037054  cmp     rcx, rax
0x140037057  jz      short loc_14003707D
0x140037059  test    byte ptr [rcx+1Ch], 4
0x14003705d  jz      short loc_14003707D
0x14003705f  cmp     byte ptr [rcx+19h], 2
0x140037063  jb      short loc_14003707D
0x140037065  mov     edx, 5Fh ; '_'
0x14003706a  mov     r9d, ebx
0x14003706d  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140037074  mov     rcx, [rcx+10h]
0x140037078  call    WPP_SF_d
0x14003707d  mov     rax, [rbp+var_28]
0x140037081  mov     [rsp+70h+var_40], rax; struct IWbemServices *
0x140037086  mov     [rsp+70h+var_48], r12; struct IWbemServices *
0x14003708b  mov     [rsp+70h+var_50], rsi; int
0x140037090  mov     r9d, r14d; int
0x140037093  mov     r8, r15; unsigned __int16 *
0x140037096  mov     edx, [rbp+arg_0]; int
0x140037099  mov     rcx, rdi; this
0x14003709c  call    ?Helper_DeleteClassAsync@CInterceptor_IWbemSyncProvider@@AEAAJHQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z; CInterceptor_IWbemSyncProvider::Helper_DeleteClassAsync(int,ushort * const,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)
0x1400370a1  mov     ebx, eax
0x1400370a3  mov     rax, [rbp+var_20]
0x1400370a7  mov     [rsp+70h+var_38], rax; struct IUnknown *
0x1400370ac  mov     eax, [rbp+var_30]
0x1400370af  mov     dword ptr [rsp+70h+var_40], eax; int
0x1400370b3  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x1400370b7  mov     r8, [rbp+var_10]; struct IUnknown *
0x1400370bb  mov     edx, [rbp+var_2C]; int
0x1400370be  mov     rcx, rdi; this
0x1400370c1  call    ?End_IWbemServices@CInterceptor_IWbemSyncProvider@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemSyncProvider::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x1400370c6  nop
0x1400370c7  lea     rcx, [rbp+var_8]; this
0x1400370cb  call    ??1CMUIPreferredLanguages@@QEAA@XZ; CMUIPreferredLanguages::~CMUIPreferredLanguages(void)
0x1400370d0  test    ebx, ebx
0x1400370d2  jns     short loc_1400370E5
0x1400370d4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400370da  mov     edx, ebx
0x1400370dc  mov     rcx, rax
0x1400370df  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400370e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400370ec  lea     rax, WPP_GLOBAL_Control
0x1400370f3  cmp     rcx, rax
0x1400370f6  jz      short loc_14003711C
0x1400370f8  test    byte ptr [rcx+1Ch], 4
0x1400370fc  jz      short loc_14003711C
0x1400370fe  cmp     byte ptr [rcx+19h], 2
0x140037102  jb      short loc_14003711C
0x140037104  mov     edx, 60h ; '`'
0x140037109  mov     r9d, ebx
0x14003710c  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140037113  mov     rcx, [rcx+10h]
0x140037117  call    WPP_SF_d
0x14003711c  mov     eax, ebx
0x14003711e  lea     r11, [rsp+70h+var_s0]
0x140037123  mov     rbx, [r11+38h]
0x140037127  mov     rsi, [r11+40h]
0x14003712b  mov     rsp, r11
0x14003712e  pop     r15
0x140037130  pop     r14
0x140037132  pop     r12
0x140037134  pop     rdi
0x140037135  pop     rbp
0x140037136  retn
```
