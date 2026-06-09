# CInterceptor_IWbemSyncObjectSink_ExecQueryAsync::SetStatus(long,long,ushort *,IWbemClassObject *)

- ea: `0x140008b50`
- end: `0x140008d39`
- name: `?SetStatus@CInterceptor_IWbemSyncObjectSink_ExecQueryAsync@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z`
- size: `489`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemSyncObjectSink_ExecQueryAsync *__hidden this@<rcx>, int@<edx>, int@<r8d>, unsigned __int16 *@<r9>, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140008b50`
- `0x140009120`
- `0x1400095e0`
- `0x14000a130`
- `0x1400234b8`
- `0x140028dd4`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x140008c7b`
- `NCObjAPI!WmiSetAndCommitObject` at `0x140008c7b`
- `wbemcomn!GetMemLogObject` at `0x140008ca5`
- `wbemcomn!GetMemLogObject` at `0x140008ca5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140008cb0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140008cb0`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncObjectSink_ExecQueryAsync::SetStatus(
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
    WPP_SF_DDqSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, a3, a2, a3, (char)this, (__int64)a4, (char)a5);
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
      goto LABEL_10;
    }
    v11 = CCommon_Batching_IWbemSyncObjectSink::SendIndicateObjects((CCommon_Batching_IWbemSyncObjectSink *)this);
    v12 = a3;
    if ( v11 < 0 )
      v12 = v11;
  }
  v13 = CCommon_IWbemSyncObjectSink::SetStatus((CCommon_IWbemSyncObjectSink *)this, a2, v12, a4, a5);
  v9 = WPP_GLOBAL_Control;
  v14 = v13;
LABEL_10:
  v15 = this[31];
  if ( v15 && !v10 )
  {
    WmiSetAndCommitObject(
      qword_140061440,
      1,
      *((_QWORD *)v15 + 78),
      *(_QWORD *)(*((_QWORD *)v15 + 75) + 64LL),
      *((_QWORD *)v15 + 77),
      *((_QWORD *)v15 + 76),
      *((_QWORD *)v15 + 79),
      *((_DWORD *)this + 66));
    v9 = WPP_GLOBAL_Control;
  }
  if ( v14 == -2147217400 )
    return 2147749896LL;
  if ( v14 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v14);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 && *((_BYTE *)v9 + 25) >= 2u )
    WPP_SF_d(v9[2], 58, WPP_48f931ced3963915480c4dfc938e4579_Traceguids, (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140008b50  push    rbx
0x140008b52  push    rbp
0x140008b53  push    rsi
0x140008b54  push    rdi
0x140008b55  push    r12
0x140008b57  push    r14
0x140008b59  push    r15
0x140008b5b  sub     rsp, 70h
0x140008b5f  mov     rbp, r9
0x140008b62  mov     r14d, r8d
0x140008b65  mov     esi, edx
0x140008b67  mov     rbx, rcx
0x140008b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b71  lea     r12, WPP_GLOBAL_Control
0x140008b78  mov     r15, [rsp+0A8h+arg_20]
0x140008b80  cmp     rcx, r12
0x140008b83  jz      short loc_140008B8F
0x140008b85  test    byte ptr [rcx+1Ch], 4
0x140008b89  jnz     loc_140008CDE
0x140008b8f  mov     rax, [rbx+0F8h]
0x140008b96  test    rax, rax
0x140008b99  jz      short loc_140008BAA
0x140008b9b  mov     rcx, rax; this
0x140008b9e  call    ?PerfSet_Health_Data@CInterceptor_IWbemSyncProvider@@QEAAPEAXXZ; CInterceptor_IWbemSyncProvider::PerfSet_Health_Data(void)
0x140008ba3  mov     rcx, cs:WPP_GLOBAL_Control
0x140008baa  mov     edi, esi
0x140008bac  and     edi, 0FFFFE0FFh
0x140008bb2  jnz     loc_140008CCC
0x140008bb8  cmp     [rbx+90h], edi
0x140008bbe  jnz     loc_140008CD4
0x140008bc4  mov     rcx, rbx; this
0x140008bc7  call    ?SendIndicateObjects@CCommon_Batching_IWbemSyncObjectSink@@QEAAJXZ; CCommon_Batching_IWbemSyncObjectSink::SendIndicateObjects(void)
0x140008bcc  test    eax, eax
0x140008bce  mov     r8d, r14d
0x140008bd1  cmovs   r8d, eax; int
0x140008bd5  mov     r9, rbp; unsigned __int16 *
0x140008bd8  mov     [rsp+0A8h+var_88], r15; struct IWbemClassObject *
0x140008bdd  mov     edx, esi; int
0x140008bdf  mov     rcx, rbx; this
0x140008be2  call    ?SetStatus@CCommon_IWbemSyncObjectSink@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z; CCommon_IWbemSyncObjectSink::SetStatus(long,long,ushort *,IWbemClassObject *)
0x140008be7  mov     rcx, cs:WPP_GLOBAL_Control
0x140008bee  mov     esi, eax
0x140008bf0  mov     r8, [rbx+0F8h]
0x140008bf7  test    r8, r8
0x140008bfa  jz      loc_140008C88
0x140008c00  test    edi, edi
0x140008c02  jnz     loc_140008C88
0x140008c08  mov     rax, [rbx+118h]
0x140008c0f  mov     edx, 1
0x140008c14  mov     r9, [r8+258h]
0x140008c1b  mov     rcx, cs:qword_140061440
0x140008c22  mov     [rsp+0A8h+var_48], r15
0x140008c27  mov     [rsp+0A8h+var_50], rbp
0x140008c2c  mov     r9, [r9+40h]
0x140008c30  mov     [rsp+0A8h+var_58], r14d
0x140008c35  mov     [rsp+0A8h+var_60], rax
0x140008c3a  mov     rax, [rbx+110h]
0x140008c41  mov     [rsp+0A8h+var_68], rax
0x140008c46  mov     eax, [rbx+108h]
0x140008c4c  mov     dword ptr [rsp+0A8h+var_70], eax
0x140008c50  mov     rax, [r8+278h]
0x140008c57  mov     [rsp+0A8h+var_78], rax
0x140008c5c  mov     rax, [r8+260h]
0x140008c63  mov     [rsp+0A8h+var_80], rax
0x140008c68  mov     rax, [r8+268h]
0x140008c6f  mov     r8, [r8+270h]
0x140008c76  mov     [rsp+0A8h+var_88], rax
0x140008c7b  call    cs:__imp_WmiSetAndCommitObject
0x140008c81  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c88  cmp     esi, 80041008h
0x140008c8e  jnz     short loc_140008CA1
0x140008c90  mov     eax, esi
0x140008c92  add     rsp, 70h
0x140008c96  pop     r15
0x140008c98  pop     r14
0x140008c9a  pop     r12
0x140008c9c  pop     rdi
0x140008c9d  pop     rsi
0x140008c9e  pop     rbp
0x140008c9f  pop     rbx
0x140008ca0  retn
0x140008ca1  test    esi, esi
0x140008ca3  jns     short loc_140008CBD
0x140008ca5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140008cab  mov     rcx, rax
0x140008cae  mov     edx, esi
0x140008cb0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140008cb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140008cbd  cmp     rcx, r12
0x140008cc0  jz      short loc_140008CC8
0x140008cc2  test    byte ptr [rcx+1Ch], 4
0x140008cc6  jnz     short loc_140008D19
0x140008cc8  mov     eax, esi
0x140008cca  jmp     short loc_140008C92
0x140008ccc  mov     r8d, r14d
0x140008ccf  jmp     loc_140008BD5
0x140008cd4  mov     esi, 80041033h
0x140008cd9  jmp     loc_140008BF0
0x140008cde  cmp     byte ptr [rcx+19h], 5
0x140008ce2  jb      loc_140008B8F
0x140008ce8  mov     rcx, [rcx+10h]
0x140008cec  mov     edx, 39h ; '9'
0x140008cf1  mov     [rsp+0A8h+var_70], r15
0x140008cf6  mov     r9d, esi
0x140008cf9  mov     [rsp+0A8h+var_78], rbp
0x140008cfe  mov     [rsp+0A8h+var_80], rbx
0x140008d03  mov     dword ptr [rsp+0A8h+var_88], r14d
0x140008d08  call    WPP_SF_DDqSq
0x140008d0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008d14  jmp     loc_140008B8F
0x140008d19  cmp     byte ptr [rcx+19h], 2
0x140008d1d  jb      short loc_140008CC8
0x140008d1f  mov     rcx, [rcx+10h]
0x140008d23  lea     r8, WPP_48f931ced3963915480c4dfc938e4579_Traceguids
0x140008d2a  mov     edx, 3Ah ; ':'
0x140008d2f  mov     r9d, esi
0x140008d32  call    WPP_SF_d
0x140008d37  jmp     short loc_140008CC8
```
