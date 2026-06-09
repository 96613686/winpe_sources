# CInterceptor_IWbemSyncProvider::InternalEx_IndicateToConsumer(bool,IWbemClassObject *,long,IWbemClassObject * *)

- ea: `0x14001b484`
- end: `0x14001b632`
- name: `?InternalEx_IndicateToConsumer@CInterceptor_IWbemSyncProvider@@AEAAJ_NPEAUIWbemClassObject@@JPEAPEAU2@@Z`
- size: `430`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemSyncProvider *__hidden this@<rcx>, bool@<dl>, struct IWbemClassObject *@<r8>, int@<r9d>, struct IWbemClassObject **)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140038320`
- `0x14003a570`

## callees

- `0x14001b484`
- `0x14001b638`
- `0x14001c6d8`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14001b58e`
- `wbemcomn!GetMemLogObject` at `0x14001b5c8`
- `wbemcomn!GetMemLogObject` at `0x14001b58e`
- `wbemcomn!GetMemLogObject` at `0x14001b5c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001b599`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001b5d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001b599`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001b5d8`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::InternalEx_IndicateToConsumer(
        CInterceptor_IWbemSyncProvider *this,
        char a2,
        struct IWbemClassObject *a3,
        unsigned int a4,
        struct IWbemClassObject **a5)
{
  struct IUnknown *v7; // r8
  int v9; // ebx
  struct IUnknown *v10; // rdx
  const struct _GUID *v11; // r8
  CMemoryLog *MemLogObject; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  CMemoryLog *v16; // rax
  int v18; // [rsp+40h] [rbp-19h]
  struct IUnknown *v19; // [rsp+48h] [rbp-11h]
  int v20; // [rsp+68h] [rbp+Fh] BYREF
  int v21; // [rsp+6Ch] [rbp+13h] BYREF
  struct IUnknown *v22; // [rsp+70h] [rbp+17h] BYREF
  struct IUnknown *v23; // [rsp+78h] [rbp+1Fh] BYREF
  struct IServerSecurity *v24; // [rsp+80h] [rbp+27h] BYREF
  struct IUnknown *v25; // [rsp+88h] [rbp+2Fh] BYREF
  int v26; // [rsp+B8h] [rbp+5Fh] BYREF

  v7 = (struct IUnknown *)*((_QWORD *)this + 50);
  if ( v7 )
  {
    v20 = 0;
    v25 = 0;
    v24 = 0;
    v22 = 0;
    v26 = 0;
    v23 = 0;
    v9 = CInterceptor_IWbemSyncProvider::Begin_Interface_Events(
           this,
           a2,
           v7,
           &IID_IWbemUnboundObjectSink,
           9u,
           &v20,
           &v25,
           &v24,
           &v21,
           &v22,
           &v26,
           &v23);
    if ( v9 < 0
      || (v9 = ((__int64 (__fastcall *)(struct IUnknown *, struct IWbemClassObject *, _QWORD, struct IWbemClassObject **))v22->lpVtbl[1].QueryInterface)(
                 v22,
                 a3,
                 a4,
                 a5),
          CInterceptor_IWbemSyncProvider::End_Interface_Events(this, v10, v11, 9u, v20, v25, v24, v18, v19, v26, v23),
          v9 < 0) )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v9);
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 151;
      v15 = (unsigned int)v9;
LABEL_13:
      WPP_SF_d(v13[2], v14, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v15);
    }
  }
  else
  {
    v16 = GetMemLogObject();
    v9 = -2147217372;
    CMemoryLog::Write(v16, -2147217372);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 152;
      v15 = 2147749924LL;
      goto LABEL_13;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14001b484  mov     r11, rsp
0x14001b487  mov     [r11+10h], rbx
0x14001b48b  mov     [r11+18h], rsi
0x14001b48f  push    rbp
0x14001b490  push    rdi
0x14001b491  push    r14
0x14001b493  lea     rbp, [r11-57h]
0x14001b497  sub     rsp, 90h
0x14001b49e  mov     r14, r8
0x14001b4a1  mov     esi, r9d
0x14001b4a4  mov     r8, [rcx+190h]; struct IUnknown *
0x14001b4ab  mov     rdi, rcx
0x14001b4ae  test    r8, r8
0x14001b4b1  jz      loc_14001B5C8
0x14001b4b7  lea     rax, [rbp+4Fh+var_30]
0x14001b4bb  mov     [rbp+4Fh+var_40], 0
0x14001b4c2  mov     [r11-50h], rax
0x14001b4c6  lea     r9, IID_IWbemUnboundObjectSink; struct _GUID *
0x14001b4cd  lea     rax, [rbp+4Fh+arg_0]
0x14001b4d1  mov     [rbp+4Fh+var_20], 0
0x14001b4d9  mov     [r11-58h], rax
0x14001b4dd  lea     rax, [rbp+4Fh+var_38]
0x14001b4e1  mov     [r11-60h], rax
0x14001b4e5  lea     rax, [rbp+4Fh+var_3C]
0x14001b4e9  mov     [r11-68h], rax
0x14001b4ed  lea     rax, [rbp+4Fh+var_28]
0x14001b4f1  mov     [r11-70h], rax
0x14001b4f5  lea     rax, [rbp+4Fh+var_20]
0x14001b4f9  mov     [r11-78h], rax
0x14001b4fd  lea     rax, [rbp+4Fh+var_40]
0x14001b501  mov     [r11-80h], rax
0x14001b505  mov     [rsp+0A0h+var_80], 9; unsigned int
0x14001b50d  mov     [rbp+4Fh+var_28], 0
0x14001b515  mov     [rbp+4Fh+var_38], 0
0x14001b51d  mov     [rbp+4Fh+arg_0], 0
0x14001b524  mov     [rbp+4Fh+var_30], 0
0x14001b52c  call    ?Begin_Interface_Events@CInterceptor_IWbemSyncProvider@@AEAAJ_NPEAUIUnknown@@AEBU_GUID@@KAEAHAEAPEAU2@AEAPEAUIServerSecurity@@3434@Z; CInterceptor_IWbemSyncProvider::Begin_Interface_Events(bool,IUnknown *,_GUID const &,ulong,int &,IUnknown * &,IServerSecurity * &,int &,IUnknown * &,int &,IUnknown * &)
0x14001b531  mov     ebx, eax
0x14001b533  test    eax, eax
0x14001b535  js      short loc_14001B58E
0x14001b537  mov     rcx, [rbp+4Fh+var_38]
0x14001b53b  mov     r8d, esi
0x14001b53e  mov     r9, [rbp+4Fh+arg_20]
0x14001b542  mov     rdx, r14
0x14001b545  mov     rax, [rcx]
0x14001b548  mov     rax, [rax+18h]
0x14001b54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b551  mov     ebx, eax
0x14001b553  mov     r9d, 9; unsigned int
0x14001b559  mov     rax, [rbp+4Fh+var_30]
0x14001b55d  mov     rcx, rdi; this
0x14001b560  mov     [rsp+0A0h+var_50], rax; struct IUnknown *
0x14001b565  mov     eax, [rbp+4Fh+arg_0]
0x14001b568  mov     [rsp+0A0h+var_58], eax; int
0x14001b56c  mov     rax, [rbp+4Fh+var_28]
0x14001b570  mov     [rsp+0A0h+var_70], rax; struct IServerSecurity *
0x14001b575  mov     rax, [rbp+4Fh+var_20]
0x14001b579  mov     [rsp+0A0h+var_78], rax; struct IUnknown *
0x14001b57e  mov     eax, [rbp+4Fh+var_40]
0x14001b581  mov     [rsp+0A0h+var_80], eax; int
0x14001b585  call    ?End_Interface_Events@CInterceptor_IWbemSyncProvider@@AEAAJPEAUIUnknown@@AEBU_GUID@@KH0PEAUIServerSecurity@@H0H0@Z; CInterceptor_IWbemSyncProvider::End_Interface_Events(IUnknown *,_GUID const &,ulong,int,IUnknown *,IServerSecurity *,int,IUnknown *,int,IUnknown *)
0x14001b58a  test    ebx, ebx
0x14001b58c  jns     short loc_14001B59F
0x14001b58e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001b594  mov     rcx, rax
0x14001b597  mov     edx, ebx
0x14001b599  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001b59f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b5a6  lea     rax, WPP_GLOBAL_Control
0x14001b5ad  cmp     rcx, rax
0x14001b5b0  jz      short loc_14001B618
0x14001b5b2  test    byte ptr [rcx+1Ch], 4
0x14001b5b6  jz      short loc_14001B618
0x14001b5b8  cmp     byte ptr [rcx+19h], 2
0x14001b5bc  jb      short loc_14001B618
0x14001b5be  mov     edx, 97h
0x14001b5c3  mov     r9d, ebx
0x14001b5c6  jmp     short loc_14001B608
0x14001b5c8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001b5ce  mov     ebx, 80041024h
0x14001b5d3  mov     rcx, rax
0x14001b5d6  mov     edx, ebx
0x14001b5d8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001b5de  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b5e5  lea     rax, WPP_GLOBAL_Control
0x14001b5ec  cmp     rcx, rax
0x14001b5ef  jz      short loc_14001B618
0x14001b5f1  test    byte ptr [rcx+1Ch], 4
0x14001b5f5  jz      short loc_14001B618
0x14001b5f7  cmp     byte ptr [rcx+19h], 2
0x14001b5fb  jb      short loc_14001B618
0x14001b5fd  mov     edx, 98h
0x14001b602  mov     r9d, 80041024h
0x14001b608  mov     rcx, [rcx+10h]
0x14001b60c  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14001b613  call    WPP_SF_d
0x14001b618  lea     r11, [rsp+0A0h+var_10]
0x14001b620  mov     eax, ebx
0x14001b622  mov     rbx, [r11+28h]
0x14001b626  mov     rsi, [r11+30h]
0x14001b62a  mov     rsp, r11
0x14001b62d  pop     r14
0x14001b62f  pop     rdi
0x14001b630  pop     rbp
0x14001b631  retn
```
