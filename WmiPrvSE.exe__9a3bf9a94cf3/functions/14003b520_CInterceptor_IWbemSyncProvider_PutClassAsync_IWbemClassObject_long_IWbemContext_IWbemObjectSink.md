# CInterceptor_IWbemSyncProvider::PutClassAsync(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x14003b520`
- end: `0x14003b747`
- name: `?PutClassAsync@CInterceptor_IWbemSyncProvider@@UEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `551`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, struct IWbemClassObject *, int, struct IWbemContext *, struct IWbemServices *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000d090`
- `0x14000fa00`
- `0x14000fa50`
- `0x14000fcb0`
- `0x1400234b8`
- `0x1400304c8`
- `0x14003804c`
- `0x14003b520`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003b645`
- `wbemcomn!GetMemLogObject` at `0x14003b6e4`
- `wbemcomn!GetMemLogObject` at `0x14003b645`
- `wbemcomn!GetMemLogObject` at `0x14003b6e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003b650`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003b6ef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003b650`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003b6ef`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::PutClassAsync(
        CInterceptor_IWbemSyncProvider *this,
        struct IWbemClassObject *a2,
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
    WPP_SF_qdqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      89,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      a2,
      a3,
      a4,
      a5);
  }
  v10 = -2147217372;
  if ( !*((_QWORD *)this + 41) || !*(_DWORD *)(*((_QWORD *)this + 75) + 1860LL) )
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
          90,
          WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
          (unsigned int)v11);
      }
    }
    v10 = CInterceptor_IWbemSyncProvider::Helper_PutClassAsync(this, v24, a2, a3, a4, v9, v19);
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
      91,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14003b520  mov     r11, rsp
0x14003b523  mov     [r11+10h], rbx
0x14003b527  mov     [r11+18h], rsi
0x14003b52b  push    rbp
0x14003b52c  push    rdi
0x14003b52d  push    r12
0x14003b52f  push    r14
0x14003b531  push    r15
0x14003b533  mov     rbp, rsp
0x14003b536  sub     rsp, 70h
0x14003b53a  mov     rsi, r9
0x14003b53d  mov     r14d, r8d
0x14003b540  mov     r15, rdx
0x14003b543  mov     rdi, rcx
0x14003b546  lea     rax, WPP_GLOBAL_Control
0x14003b54d  mov     r12, [rbp+arg_20]
0x14003b551  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b558  cmp     rcx, rax
0x14003b55b  jz      short loc_14003B58D
0x14003b55d  test    byte ptr [rcx+1Ch], 4
0x14003b561  jz      short loc_14003B58D
0x14003b563  cmp     byte ptr [rcx+19h], 5
0x14003b567  jb      short loc_14003B58D
0x14003b569  mov     edx, 59h ; 'Y'
0x14003b56e  mov     [r11-68h], r12
0x14003b572  mov     [r11-70h], r9
0x14003b576  mov     [r11-78h], r8d
0x14003b57a  mov     r9, r15
0x14003b57d  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14003b584  mov     rcx, [rcx+10h]
0x14003b588  call    WPP_SF_qdqq
0x14003b58d  mov     ebx, 80041024h
0x14003b592  cmp     qword ptr [rdi+148h], 0
0x14003b59a  jz      loc_14003B6E4
0x14003b5a0  mov     rax, [rdi+258h]
0x14003b5a7  cmp     dword ptr [rax+744h], 0
0x14003b5ae  jz      loc_14003B6E4
0x14003b5b4  mov     [rbp+var_2C], 0
0x14003b5bb  mov     [rbp+var_10], 0
0x14003b5c3  mov     [rbp+var_18], 0
0x14003b5cb  mov     [rbp+arg_0], 0
0x14003b5d2  mov     [rbp+var_28], 0
0x14003b5da  mov     [rbp+var_30], 0
0x14003b5e1  mov     [rbp+var_20], 0
0x14003b5e9  mov     [rbp+var_8], 0
0x14003b5f1  lea     rax, [rbp+var_20]
0x14003b5f5  mov     [rsp+70h+var_38], rax; struct IUnknown **
0x14003b5fa  lea     rax, [rbp+var_30]
0x14003b5fe  mov     [rsp+70h+var_40], rax; int *
0x14003b603  lea     rax, [rbp+var_28]
0x14003b607  mov     [rsp+70h+var_48], rax; struct IWbemServices **
0x14003b60c  lea     rax, [rbp+arg_0]
0x14003b610  mov     [rsp+70h+var_50], rax; int *
0x14003b615  lea     r9, [rbp+var_18]; struct IServerSecurity **
0x14003b619  lea     r8, [rbp+var_10]; struct IUnknown **
0x14003b61d  lea     rdx, [rbp+var_2C]; int *
0x14003b621  mov     rcx, rdi; this
0x14003b624  call    ?Begin_IWbemServices@CInterceptor_IWbemSyncProvider@@AEAAJAEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@0AEAPEAUIWbemServices@@01@Z; CInterceptor_IWbemSyncProvider::Begin_IWbemServices(int &,IUnknown * &,IServerSecurity * &,int &,IWbemServices * &,int &,IUnknown * &)
0x14003b629  mov     ebx, eax
0x14003b62b  test    eax, eax
0x14003b62d  js      loc_14003B6D7
0x14003b633  mov     rdx, rsi; struct IWbemContext *
0x14003b636  lea     rcx, [rbp+var_8]; this
0x14003b63a  call    ?Set@CMUIPreferredLanguages@@QEAAJPEAUIWbemContext@@@Z; CMUIPreferredLanguages::Set(IWbemContext *)
0x14003b63f  mov     ebx, eax
0x14003b641  test    eax, eax
0x14003b643  jns     short loc_14003B68D
0x14003b645  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003b64b  mov     edx, ebx
0x14003b64d  mov     rcx, rax
0x14003b650  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003b656  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b65d  lea     rax, WPP_GLOBAL_Control
0x14003b664  cmp     rcx, rax
0x14003b667  jz      short loc_14003B68D
0x14003b669  test    byte ptr [rcx+1Ch], 4
0x14003b66d  jz      short loc_14003B68D
0x14003b66f  cmp     byte ptr [rcx+19h], 2
0x14003b673  jb      short loc_14003B68D
0x14003b675  mov     edx, 5Ah ; 'Z'
0x14003b67a  mov     r9d, ebx
0x14003b67d  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14003b684  mov     rcx, [rcx+10h]
0x14003b688  call    WPP_SF_d
0x14003b68d  mov     rax, [rbp+var_28]
0x14003b691  mov     [rsp+70h+var_40], rax; struct IWbemServices *
0x14003b696  mov     [rsp+70h+var_48], r12; struct IWbemServices *
0x14003b69b  mov     [rsp+70h+var_50], rsi; int
0x14003b6a0  mov     r9d, r14d; int
0x14003b6a3  mov     r8, r15; struct IWbemClassObject *
0x14003b6a6  mov     edx, [rbp+arg_0]; int
0x14003b6a9  mov     rcx, rdi; this
0x14003b6ac  call    ?Helper_PutClassAsync@CInterceptor_IWbemSyncProvider@@AEAAJHPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z; CInterceptor_IWbemSyncProvider::Helper_PutClassAsync(int,IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)
0x14003b6b1  mov     ebx, eax
0x14003b6b3  mov     rax, [rbp+var_20]
0x14003b6b7  mov     [rsp+70h+var_38], rax; struct IUnknown *
0x14003b6bc  mov     eax, [rbp+var_30]
0x14003b6bf  mov     dword ptr [rsp+70h+var_40], eax; int
0x14003b6c3  mov     r9, [rbp+var_18]; struct IServerSecurity *
0x14003b6c7  mov     r8, [rbp+var_10]; struct IUnknown *
0x14003b6cb  mov     edx, [rbp+var_2C]; int
0x14003b6ce  mov     rcx, rdi; this
0x14003b6d1  call    ?End_IWbemServices@CInterceptor_IWbemSyncProvider@@AEAAJHPEAUIUnknown@@PEAUIServerSecurity@@HPEAUIWbemServices@@H0@Z; CInterceptor_IWbemSyncProvider::End_IWbemServices(int,IUnknown *,IServerSecurity *,int,IWbemServices *,int,IUnknown *)
0x14003b6d6  nop
0x14003b6d7  lea     rcx, [rbp+var_8]; this
0x14003b6db  call    ??1CMUIPreferredLanguages@@QEAA@XZ; CMUIPreferredLanguages::~CMUIPreferredLanguages(void)
0x14003b6e0  test    ebx, ebx
0x14003b6e2  jns     short loc_14003B6F5
0x14003b6e4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003b6ea  mov     edx, ebx
0x14003b6ec  mov     rcx, rax
0x14003b6ef  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003b6f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b6fc  lea     rax, WPP_GLOBAL_Control
0x14003b703  cmp     rcx, rax
0x14003b706  jz      short loc_14003B72C
0x14003b708  test    byte ptr [rcx+1Ch], 4
0x14003b70c  jz      short loc_14003B72C
0x14003b70e  cmp     byte ptr [rcx+19h], 2
0x14003b712  jb      short loc_14003B72C
0x14003b714  mov     edx, 5Bh ; '['
0x14003b719  mov     r9d, ebx
0x14003b71c  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14003b723  mov     rcx, [rcx+10h]
0x14003b727  call    WPP_SF_d
0x14003b72c  mov     eax, ebx
0x14003b72e  lea     r11, [rsp+70h+var_s0]
0x14003b733  mov     rbx, [r11+38h]
0x14003b737  mov     rsi, [r11+40h]
0x14003b73b  mov     rsp, r11
0x14003b73e  pop     r15
0x14003b740  pop     r14
0x14003b742  pop     r12
0x14003b744  pop     rdi
0x14003b745  pop     rbp
0x14003b746  retn
```
