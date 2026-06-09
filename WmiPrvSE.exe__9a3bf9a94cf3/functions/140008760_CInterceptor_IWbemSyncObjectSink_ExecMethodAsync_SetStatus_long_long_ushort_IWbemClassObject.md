# CInterceptor_IWbemSyncObjectSink_ExecMethodAsync::SetStatus(long,long,ushort *,IWbemClassObject *)

- ea: `0x140008760`
- end: `0x140008953`
- name: `?SetStatus@CInterceptor_IWbemSyncObjectSink_ExecMethodAsync@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z`
- size: `499`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemSyncObjectSink_ExecMethodAsync *__hidden this@<rcx>, int@<edx>, int@<r8d>, unsigned __int16 *@<r9>, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140008760`
- `0x140009120`
- `0x1400095e0`
- `0x14000a130`
- `0x1400234b8`
- `0x140028dd4`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x140008895`
- `NCObjAPI!WmiSetAndCommitObject` at `0x140008895`
- `wbemcomn!GetMemLogObject` at `0x14000890f`
- `wbemcomn!GetMemLogObject` at `0x14000890f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000891a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000891a`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncObjectSink_ExecMethodAsync::SetStatus(
        CInterceptor_IWbemSyncProvider **this,
        int a2,
        int a3,
        unsigned __int16 *a4,
        struct IWbemClassObject *a5)
{
  _QWORD *v9; // rcx
  unsigned int v10; // esi
  int v11; // eax
  int v12; // r8d
  int v13; // eax
  int v14; // ebx
  CInterceptor_IWbemSyncProvider *v15; // r8
  CMemoryLog *MemLogObject; // rax

  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_DDqSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, a3, a2, a3, (char)this, (__int64)a4, (char)a5);
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
      qword_140061450,
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
    WPP_SF_d(v9[2], 60, WPP_48f931ced3963915480c4dfc938e4579_Traceguids, (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140008760  push    rbx
0x140008762  push    rbp
0x140008763  push    rsi
0x140008764  push    rdi
0x140008765  push    r12
0x140008767  push    r14
0x140008769  push    r15
0x14000876b  sub     rsp, 70h
0x14000876f  mov     rbp, r9
0x140008772  mov     r14d, r8d
0x140008775  mov     ebx, edx
0x140008777  mov     rdi, rcx
0x14000877a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008781  lea     r12, WPP_GLOBAL_Control
0x140008788  mov     r15, [rsp+0A8h+arg_20]
0x140008790  cmp     rcx, r12
0x140008793  jz      short loc_14000879F
0x140008795  test    byte ptr [rcx+1Ch], 4
0x140008799  jnz     loc_1400088D4
0x14000879f  mov     rax, [rdi+0F8h]
0x1400087a6  test    rax, rax
0x1400087a9  jz      short loc_1400087BA
0x1400087ab  mov     rcx, rax; this
0x1400087ae  call    ?PerfSet_Health_Data@CInterceptor_IWbemSyncProvider@@QEAAPEAXXZ; CInterceptor_IWbemSyncProvider::PerfSet_Health_Data(void)
0x1400087b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087ba  mov     esi, ebx
0x1400087bc  and     esi, 0FFFFE0FFh
0x1400087c2  jnz     loc_1400088C2
0x1400087c8  cmp     [rdi+90h], esi
0x1400087ce  jnz     loc_1400088CA
0x1400087d4  mov     rcx, rdi; this
0x1400087d7  call    ?SendIndicateObjects@CCommon_Batching_IWbemSyncObjectSink@@QEAAJXZ; CCommon_Batching_IWbemSyncObjectSink::SendIndicateObjects(void)
0x1400087dc  test    eax, eax
0x1400087de  mov     r8d, r14d
0x1400087e1  cmovs   r8d, eax; int
0x1400087e5  mov     r9, rbp; unsigned __int16 *
0x1400087e8  mov     [rsp+0A8h+var_88], r15; struct IWbemClassObject *
0x1400087ed  mov     edx, ebx; int
0x1400087ef  mov     rcx, rdi; this
0x1400087f2  call    ?SetStatus@CCommon_IWbemSyncObjectSink@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z; CCommon_IWbemSyncObjectSink::SetStatus(long,long,ushort *,IWbemClassObject *)
0x1400087f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087fe  mov     ebx, eax
0x140008800  mov     r8, [rdi+0F8h]
0x140008807  test    r8, r8
0x14000880a  jz      loc_1400088A2
0x140008810  test    esi, esi
0x140008812  jnz     loc_1400088A2
0x140008818  mov     rax, [rdi+120h]
0x14000881f  lea     edx, [rsi+1]
0x140008822  mov     r9, [r8+258h]
0x140008829  mov     rcx, cs:qword_140061450
0x140008830  mov     [rsp+0A8h+var_40], r15
0x140008835  mov     [rsp+0A8h+var_48], rbp
0x14000883a  mov     r9, [r9+40h]
0x14000883e  mov     [rsp+0A8h+var_50], r14d
0x140008843  mov     [rsp+0A8h+var_58], rax
0x140008848  mov     rax, [rdi+118h]
0x14000884f  mov     [rsp+0A8h+var_60], rax
0x140008854  mov     rax, [rdi+110h]
0x14000885b  mov     [rsp+0A8h+var_68], rax
0x140008860  mov     eax, [rdi+108h]
0x140008866  mov     dword ptr [rsp+0A8h+var_70], eax
0x14000886a  mov     rax, [r8+278h]
0x140008871  mov     [rsp+0A8h+var_78], rax
0x140008876  mov     rax, [r8+260h]
0x14000887d  mov     [rsp+0A8h+var_80], rax
0x140008882  mov     rax, [r8+268h]
0x140008889  mov     r8, [r8+270h]
0x140008890  mov     [rsp+0A8h+var_88], rax
0x140008895  call    cs:__imp_WmiSetAndCommitObject
0x14000889b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400088a2  test    ebx, ebx
0x1400088a4  js      short loc_14000890F
0x1400088a6  cmp     rcx, r12
0x1400088a9  jz      short loc_1400088B1
0x1400088ab  test    byte ptr [rcx+1Ch], 4
0x1400088af  jnz     short loc_14000892C
0x1400088b1  mov     eax, ebx
0x1400088b3  add     rsp, 70h
0x1400088b7  pop     r15
0x1400088b9  pop     r14
0x1400088bb  pop     r12
0x1400088bd  pop     rdi
0x1400088be  pop     rsi
0x1400088bf  pop     rbp
0x1400088c0  pop     rbx
0x1400088c1  retn
0x1400088c2  mov     r8d, r14d
0x1400088c5  jmp     loc_1400087E5
0x1400088ca  mov     ebx, 80041033h
0x1400088cf  jmp     loc_140008800
0x1400088d4  cmp     byte ptr [rcx+19h], 5
0x1400088d8  jb      loc_14000879F
0x1400088de  mov     rcx, [rcx+10h]
0x1400088e2  mov     edx, 3Bh ; ';'
0x1400088e7  mov     [rsp+0A8h+var_70], r15
0x1400088ec  mov     r9d, ebx
0x1400088ef  mov     [rsp+0A8h+var_78], rbp
0x1400088f4  mov     [rsp+0A8h+var_80], rdi
0x1400088f9  mov     dword ptr [rsp+0A8h+var_88], r14d
0x1400088fe  call    WPP_SF_DDqSq
0x140008903  mov     rcx, cs:WPP_GLOBAL_Control
0x14000890a  jmp     loc_14000879F
0x14000890f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140008915  mov     rcx, rax
0x140008918  mov     edx, ebx
0x14000891a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140008920  mov     rcx, cs:WPP_GLOBAL_Control
0x140008927  jmp     loc_1400088A6
0x14000892c  cmp     byte ptr [rcx+19h], 2
0x140008930  jb      loc_1400088B1
0x140008936  mov     rcx, [rcx+10h]
0x14000893a  lea     r8, WPP_48f931ced3963915480c4dfc938e4579_Traceguids
0x140008941  mov     edx, 3Ch ; '<'
0x140008946  mov     r9d, ebx
0x140008949  call    WPP_SF_d
0x14000894e  jmp     loc_1400088B1
```
