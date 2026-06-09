# CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync::SetStatus(long,long,ushort *,IWbemClassObject *)

- ea: `0x140008f30`
- end: `0x140009111`
- name: `?SetStatus@CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z`
- size: `481`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync *__hidden this@<rcx>, int@<edx>, int@<r8d>, unsigned __int16 *@<r9>, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140008f30`
- `0x140009120`
- `0x1400095e0`
- `0x14000a130`
- `0x1400234b8`
- `0x140028dd4`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x1400090bc`
- `NCObjAPI!WmiSetAndCommitObject` at `0x1400090bc`
- `wbemcomn!GetMemLogObject` at `0x140008fda`
- `wbemcomn!GetMemLogObject` at `0x140008fda`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140008fe5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140008fe5`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncObjectSink_CreateInstanceEnumAsync::SetStatus(
        CInterceptor_IWbemSyncProvider **this,
        int a2,
        int a3,
        unsigned __int16 *a4,
        struct IWbemClassObject *a5)
{
  _QWORD *v9; // rcx
  unsigned int v10; // edi
  int v11; // eax
  int v12; // r8d
  int v13; // eax
  int v14; // esi
  CInterceptor_IWbemSyncProvider *v15; // r8
  CMemoryLog *MemLogObject; // rax

  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_DDqSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, a3, a2, a3, (char)this, (__int64)a4, (char)a5);
    v9 = WPP_GLOBAL_Control;
  }
  if ( this[31] )
  {
    CInterceptor_IWbemSyncProvider::PerfSet_Health_Data(this[31]);
    v9 = WPP_GLOBAL_Control;
  }
  v10 = a2 & 0xFFFFE0FF;
  if ( (a2 & 0xFFFFE0FF) != 0 )
  {
    v12 = a3;
  }
  else
  {
    if ( *((_DWORD *)this + 36) )
    {
      v14 = -2147217357;
      goto LABEL_9;
    }
    v11 = CCommon_Batching_IWbemSyncObjectSink::SendIndicateObjects((CCommon_Batching_IWbemSyncObjectSink *)this);
    v12 = a3;
    if ( v11 < 0 )
      v12 = v11;
  }
  v13 = CCommon_IWbemSyncObjectSink::SetStatus((CCommon_IWbemSyncObjectSink *)this, a2, v12, a4, a5);
  v9 = WPP_GLOBAL_Control;
  v14 = v13;
LABEL_9:
  v15 = this[31];
  if ( v15 && !v10 )
  {
    WmiSetAndCommitObject(
      qword_140061438,
      1,
      *((_QWORD *)v15 + 78),
      *(_QWORD *)(*((_QWORD *)v15 + 75) + 64LL),
      *((_QWORD *)v15 + 77),
      *((_QWORD *)v15 + 76),
      *((_QWORD *)v15 + 79),
      *((_DWORD *)this + 66));
    v9 = WPP_GLOBAL_Control;
  }
  if ( v14 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v14);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 && *((_BYTE *)v9 + 25) >= 2u )
    WPP_SF_d(v9[2], 54, WPP_48f931ced3963915480c4dfc938e4579_Traceguids, (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140008f30  push    rbx
0x140008f32  push    rbp
0x140008f33  push    rsi
0x140008f34  push    rdi
0x140008f35  push    r12
0x140008f37  push    r14
0x140008f39  push    r15
0x140008f3b  sub     rsp, 60h
0x140008f3f  mov     rbp, r9
0x140008f42  mov     r14d, r8d
0x140008f45  mov     esi, edx
0x140008f47  mov     rbx, rcx
0x140008f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f51  lea     r12, WPP_GLOBAL_Control
0x140008f58  mov     r15, [rsp+98h+arg_20]
0x140008f60  cmp     rcx, r12
0x140008f63  jnz     loc_14000900C
0x140008f69  mov     rax, [rbx+0F8h]
0x140008f70  test    rax, rax
0x140008f73  jz      short loc_140008F84
0x140008f75  mov     rcx, rax; this
0x140008f78  call    ?PerfSet_Health_Data@CInterceptor_IWbemSyncProvider@@QEAAPEAXXZ; CInterceptor_IWbemSyncProvider::PerfSet_Health_Data(void)
0x140008f7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f84  mov     edi, esi
0x140008f86  and     edi, 0FFFFE0FFh
0x140008f8c  jnz     loc_1400090FF
0x140008f92  cmp     [rbx+90h], edi
0x140008f98  jnz     loc_140009107
0x140008f9e  mov     rcx, rbx; this
0x140008fa1  call    ?SendIndicateObjects@CCommon_Batching_IWbemSyncObjectSink@@QEAAJXZ; CCommon_Batching_IWbemSyncObjectSink::SendIndicateObjects(void)
0x140008fa6  test    eax, eax
0x140008fa8  mov     r8d, r14d
0x140008fab  cmovs   r8d, eax; int
0x140008faf  mov     r9, rbp; unsigned __int16 *
0x140008fb2  mov     [rsp+98h+var_78], r15; struct IWbemClassObject *
0x140008fb7  mov     edx, esi; int
0x140008fb9  mov     rcx, rbx; this
0x140008fbc  call    ?SetStatus@CCommon_IWbemSyncObjectSink@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z; CCommon_IWbemSyncObjectSink::SetStatus(long,long,ushort *,IWbemClassObject *)
0x140008fc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140008fc8  mov     esi, eax
0x140008fca  mov     r8, [rbx+0F8h]
0x140008fd1  test    r8, r8
0x140008fd4  jnz     short loc_140009051
0x140008fd6  test    esi, esi
0x140008fd8  jns     short loc_140008FF2
0x140008fda  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140008fe0  mov     rcx, rax
0x140008fe3  mov     edx, esi
0x140008fe5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140008feb  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ff2  cmp     rcx, r12
0x140008ff5  jnz     loc_1400090CE
0x140008ffb  mov     eax, esi
0x140008ffd  add     rsp, 60h
0x140009001  pop     r15
0x140009003  pop     r14
0x140009005  pop     r12
0x140009007  pop     rdi
0x140009008  pop     rsi
0x140009009  pop     rbp
0x14000900a  pop     rbx
0x14000900b  retn
0x14000900c  test    byte ptr [rcx+1Ch], 4
0x140009010  jz      loc_140008F69
0x140009016  cmp     byte ptr [rcx+19h], 5
0x14000901a  jb      loc_140008F69
0x140009020  mov     rcx, [rcx+10h]
0x140009024  mov     edx, 35h ; '5'
0x140009029  mov     [rsp+98h+var_60], r15
0x14000902e  mov     r9d, esi
0x140009031  mov     [rsp+98h+var_68], rbp
0x140009036  mov     [rsp+98h+var_70], rbx
0x14000903b  mov     dword ptr [rsp+98h+var_78], r14d
0x140009040  call    WPP_SF_DDqSq
0x140009045  mov     rcx, cs:WPP_GLOBAL_Control
0x14000904c  jmp     loc_140008F69
0x140009051  test    edi, edi
0x140009053  jnz     short loc_140008FD6
0x140009055  mov     rax, [rbx+110h]
0x14000905c  mov     edx, 1
0x140009061  mov     r9, [r8+258h]
0x140009068  mov     rcx, cs:qword_140061438
0x14000906f  mov     [rsp+98h+var_40], r15
0x140009074  mov     [rsp+98h+var_48], rbp
0x140009079  mov     r9, [r9+40h]
0x14000907d  mov     [rsp+98h+var_50], r14d
0x140009082  mov     [rsp+98h+var_58], rax
0x140009087  mov     eax, [rbx+108h]
0x14000908d  mov     dword ptr [rsp+98h+var_60], eax
0x140009091  mov     rax, [r8+278h]
0x140009098  mov     [rsp+98h+var_68], rax
0x14000909d  mov     rax, [r8+260h]
0x1400090a4  mov     [rsp+98h+var_70], rax
0x1400090a9  mov     rax, [r8+268h]
0x1400090b0  mov     r8, [r8+270h]
0x1400090b7  mov     [rsp+98h+var_78], rax
0x1400090bc  call    cs:__imp_WmiSetAndCommitObject
0x1400090c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400090c9  jmp     loc_140008FD6
0x1400090ce  test    byte ptr [rcx+1Ch], 4
0x1400090d2  jz      loc_140008FFB
0x1400090d8  cmp     byte ptr [rcx+19h], 2
0x1400090dc  jb      loc_140008FFB
0x1400090e2  mov     rcx, [rcx+10h]
0x1400090e6  lea     r8, WPP_48f931ced3963915480c4dfc938e4579_Traceguids
0x1400090ed  mov     edx, 36h ; '6'
0x1400090f2  mov     r9d, esi
0x1400090f5  call    WPP_SF_d
0x1400090fa  jmp     loc_140008FFB
0x1400090ff  mov     r8d, r14d
0x140009102  jmp     loc_140008FAF
0x140009107  mov     esi, 80041033h
0x14000910c  jmp     loc_140008FCA
```
