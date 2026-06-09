# CInterceptor_IWbemSyncObjectSink_CreateClassEnumAsync::SetStatus(long,long,ushort *,IWbemClassObject *)

- ea: `0x1400248f0`
- end: `0x140024a66`
- name: `?SetStatus@CInterceptor_IWbemSyncObjectSink_CreateClassEnumAsync@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z`
- size: `374`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncObjectSink_CreateClassEnumAsync *__hidden this, int, int, unsigned __int16 *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140009d40`
- `0x14000a130`
- `0x1400234b8`
- `0x1400248f0`
- `0x140028dd4`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x1400249d2`
- `NCObjAPI!WmiSetAndCommitObject` at `0x1400249d2`
- `wbemcomn!GetMemLogObject` at `0x140024a33`
- `wbemcomn!GetMemLogObject` at `0x140024a33`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140024a3e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140024a3e`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncObjectSink_CreateClassEnumAsync::SetStatus(
        CInterceptor_IWbemSyncObjectSink_CreateClassEnumAsync *this,
        int a2,
        int a3,
        unsigned __int16 *a4,
        struct IWbemClassObject *a5)
{
  CInterceptor_IWbemSyncProvider *v9; // rcx
  int v10; // eax
  _QWORD *v11; // r8
  int v12; // ebx
  CMemoryLog *MemLogObject; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_DDqSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, a3, a2, a3, (char)this, (__int64)a4, (char)a5);
  }
  v9 = (CInterceptor_IWbemSyncProvider *)*((_QWORD *)this + 31);
  if ( v9 )
    CInterceptor_IWbemSyncProvider::PerfSet_Health_Data(v9);
  v10 = CCommon_Batching_IWbemSyncObjectSink::SetStatus(this, a2, a3, a4, a5);
  v11 = (_QWORD *)*((_QWORD *)this + 31);
  v12 = v10;
  if ( v11 && (a2 & 0xFFFFE0FF) == 0 )
    WmiSetAndCommitObject(
      qword_140061420,
      1,
      v11[78],
      *(_QWORD *)(v11[75] + 64LL),
      v11[77],
      v11[76],
      v11[79],
      *((_DWORD *)this + 66));
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
      56,
      WPP_48f931ced3963915480c4dfc938e4579_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400248f0  push    rbx
0x1400248f2  push    rbp
0x1400248f3  push    rsi
0x1400248f4  push    rdi
0x1400248f5  push    r12
0x1400248f7  push    r14
0x1400248f9  push    r15
0x1400248fb  sub     rsp, 60h
0x1400248ff  mov     rbp, r9
0x140024902  mov     r14d, r8d
0x140024905  mov     esi, edx
0x140024907  mov     rdi, rcx
0x14002490a  mov     rcx, cs:WPP_GLOBAL_Control
0x140024911  lea     r12, WPP_GLOBAL_Control
0x140024918  mov     r15, [rsp+98h+arg_20]
0x140024920  cmp     rcx, r12
0x140024923  jz      short loc_14002492F
0x140024925  test    byte ptr [rcx+1Ch], 4
0x140024929  jnz     loc_1400249FF
0x14002492f  mov     rcx, [rdi+0F8h]; this
0x140024936  test    rcx, rcx
0x140024939  jz      short loc_140024940
0x14002493b  call    ?PerfSet_Health_Data@CInterceptor_IWbemSyncProvider@@QEAAPEAXXZ; CInterceptor_IWbemSyncProvider::PerfSet_Health_Data(void)
0x140024940  mov     r9, rbp; unsigned __int16 *
0x140024943  mov     [rsp+98h+var_78], r15; struct IWbemClassObject *
0x140024948  mov     r8d, r14d; int
0x14002494b  mov     edx, esi; int
0x14002494d  mov     rcx, rdi; this
0x140024950  call    ?SetStatus@CCommon_Batching_IWbemSyncObjectSink@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z; CCommon_Batching_IWbemSyncObjectSink::SetStatus(long,long,ushort *,IWbemClassObject *)
0x140024955  mov     r8, [rdi+0F8h]
0x14002495c  mov     ebx, eax
0x14002495e  test    r8, r8
0x140024961  jz      short loc_1400249D8
0x140024963  test    esi, 0FFFFE0FFh
0x140024969  jnz     short loc_1400249D8
0x14002496b  mov     rcx, [rdi+110h]
0x140024972  mov     edx, 1
0x140024977  mov     eax, [rdi+108h]
0x14002497d  mov     r9, [r8+258h]
0x140024984  mov     [rsp+98h+var_40], r15
0x140024989  mov     [rsp+98h+var_48], rbp
0x14002498e  mov     [rsp+98h+var_50], r14d
0x140024993  mov     r9, [r9+40h]
0x140024997  mov     [rsp+98h+var_58], rcx
0x14002499c  mov     rcx, cs:qword_140061420
0x1400249a3  mov     dword ptr [rsp+98h+var_60], eax
0x1400249a7  mov     rax, [r8+278h]
0x1400249ae  mov     [rsp+98h+var_68], rax
0x1400249b3  mov     rax, [r8+260h]
0x1400249ba  mov     [rsp+98h+var_70], rax
0x1400249bf  mov     rax, [r8+268h]
0x1400249c6  mov     r8, [r8+270h]
0x1400249cd  mov     [rsp+98h+var_78], rax
0x1400249d2  call    cs:__imp_WmiSetAndCommitObject
0x1400249d8  test    ebx, ebx
0x1400249da  js      short loc_140024A33
0x1400249dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400249e3  cmp     rcx, r12
0x1400249e6  jz      short loc_1400249EE
0x1400249e8  test    byte ptr [rcx+1Ch], 4
0x1400249ec  jnz     short loc_140024A46
0x1400249ee  mov     eax, ebx
0x1400249f0  add     rsp, 60h
0x1400249f4  pop     r15
0x1400249f6  pop     r14
0x1400249f8  pop     r12
0x1400249fa  pop     rdi
0x1400249fb  pop     rsi
0x1400249fc  pop     rbp
0x1400249fd  pop     rbx
0x1400249fe  retn
0x1400249ff  cmp     byte ptr [rcx+19h], 5
0x140024a03  jb      loc_14002492F
0x140024a09  mov     rcx, [rcx+10h]
0x140024a0d  mov     edx, 37h ; '7'
0x140024a12  mov     [rsp+98h+var_60], r15
0x140024a17  mov     r9d, esi
0x140024a1a  mov     [rsp+98h+var_68], rbp
0x140024a1f  mov     [rsp+98h+var_70], rdi
0x140024a24  mov     dword ptr [rsp+98h+var_78], r14d
0x140024a29  call    WPP_SF_DDqSq
0x140024a2e  jmp     loc_14002492F
0x140024a33  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140024a39  mov     rcx, rax
0x140024a3c  mov     edx, ebx
0x140024a3e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140024a44  jmp     short loc_1400249DC
0x140024a46  cmp     byte ptr [rcx+19h], 2
0x140024a4a  jb      short loc_1400249EE
0x140024a4c  mov     rcx, [rcx+10h]
0x140024a50  lea     r8, WPP_48f931ced3963915480c4dfc938e4579_Traceguids
0x140024a57  mov     edx, 38h ; '8'
0x140024a5c  mov     r9d, ebx
0x140024a5f  call    WPP_SF_d
0x140024a64  jmp     short loc_1400249EE
```
