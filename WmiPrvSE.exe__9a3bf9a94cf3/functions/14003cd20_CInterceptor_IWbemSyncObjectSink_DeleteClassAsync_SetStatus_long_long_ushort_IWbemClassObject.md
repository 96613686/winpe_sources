# CInterceptor_IWbemSyncObjectSink_DeleteClassAsync::SetStatus(long,long,ushort *,IWbemClassObject *)

- ea: `0x14003cd20`
- end: `0x14003ce72`
- name: `?SetStatus@CInterceptor_IWbemSyncObjectSink_DeleteClassAsync@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncObjectSink_DeleteClassAsync *__hidden this, int, int, unsigned __int16 *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009120`
- `0x1400234b8`
- `0x140028dd4`
- `0x14003cd20`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x14003ce16`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14003ce16`
- `wbemcomn!GetMemLogObject` at `0x14003ce20`
- `wbemcomn!GetMemLogObject` at `0x14003ce20`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003ce2b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003ce2b`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncObjectSink_DeleteClassAsync::SetStatus(
        CInterceptor_IWbemSyncObjectSink_DeleteClassAsync *this,
        int a2,
        int a3,
        unsigned __int16 *a4,
        struct IWbemClassObject *a5)
{
  int v9; // eax
  _QWORD *v10; // r8
  int v11; // ebx
  CMemoryLog *MemLogObject; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_DDqSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, a3, a2, a3, (char)this, (__int64)a4, (char)a5);
  }
  v9 = CCommon_IWbemSyncObjectSink::SetStatus(this, a2, a3, a4, a5);
  v10 = (_QWORD *)*((_QWORD *)this + 21);
  v11 = v9;
  if ( v10 && (a2 & 0xFFFFE0FF) == 0 )
    WmiSetAndCommitObject(
      qword_140061418,
      1,
      v10[78],
      *(_QWORD *)(v10[75] + 64LL),
      v10[77],
      v10[76],
      v10[79],
      *((_DWORD *)this + 38));
  if ( v11 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v11);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      WPP_48f931ced3963915480c4dfc938e4579_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14003cd20  mov     rax, rsp
0x14003cd23  push    rbx
0x14003cd24  push    rbp
0x14003cd25  push    rsi
0x14003cd26  push    rdi
0x14003cd27  push    r12
0x14003cd29  push    r14
0x14003cd2b  push    r15
0x14003cd2d  sub     rsp, 60h
0x14003cd31  mov     rbp, r9
0x14003cd34  mov     r14d, r8d
0x14003cd37  mov     esi, edx
0x14003cd39  mov     rdi, rcx
0x14003cd3c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cd43  lea     r12, WPP_GLOBAL_Control
0x14003cd4a  mov     r15, [rsp+98h+arg_20]
0x14003cd52  cmp     rcx, r12
0x14003cd55  jz      short loc_14003CD84
0x14003cd57  test    byte ptr [rcx+1Ch], 4
0x14003cd5b  jz      short loc_14003CD84
0x14003cd5d  cmp     byte ptr [rcx+19h], 5
0x14003cd61  jb      short loc_14003CD84
0x14003cd63  mov     rcx, [rcx+10h]
0x14003cd67  mov     edx, 2Fh ; '/'
0x14003cd6c  mov     [rax-60h], r15
0x14003cd70  mov     [rax-68h], r9
0x14003cd74  mov     r9d, esi
0x14003cd77  mov     [rax-70h], rdi
0x14003cd7b  mov     [rax-78h], r8d
0x14003cd7f  call    WPP_SF_DDqSq
0x14003cd84  mov     r9, rbp; unsigned __int16 *
0x14003cd87  mov     [rsp+98h+var_78], r15; struct IWbemClassObject *
0x14003cd8c  mov     r8d, r14d; int
0x14003cd8f  mov     edx, esi; int
0x14003cd91  mov     rcx, rdi; this
0x14003cd94  call    ?SetStatus@CCommon_IWbemSyncObjectSink@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z; CCommon_IWbemSyncObjectSink::SetStatus(long,long,ushort *,IWbemClassObject *)
0x14003cd99  mov     r8, [rdi+0A8h]
0x14003cda0  mov     ebx, eax
0x14003cda2  test    r8, r8
0x14003cda5  jz      short loc_14003CE1C
0x14003cda7  test    esi, 0FFFFE0FFh
0x14003cdad  jnz     short loc_14003CE1C
0x14003cdaf  mov     rcx, [rdi+0A0h]
0x14003cdb6  mov     edx, 1
0x14003cdbb  mov     eax, [rdi+98h]
0x14003cdc1  mov     r9, [r8+258h]
0x14003cdc8  mov     [rsp+98h+var_40], r15
0x14003cdcd  mov     [rsp+98h+var_48], rbp
0x14003cdd2  mov     [rsp+98h+var_50], r14d
0x14003cdd7  mov     r9, [r9+40h]
0x14003cddb  mov     [rsp+98h+var_58], rcx
0x14003cde0  mov     rcx, cs:qword_140061418
0x14003cde7  mov     [rsp+98h+var_60], eax
0x14003cdeb  mov     rax, [r8+278h]
0x14003cdf2  mov     [rsp+98h+var_68], rax
0x14003cdf7  mov     rax, [r8+260h]
0x14003cdfe  mov     [rsp+98h+var_70], rax
0x14003ce03  mov     rax, [r8+268h]
0x14003ce0a  mov     r8, [r8+270h]
0x14003ce11  mov     [rsp+98h+var_78], rax
0x14003ce16  call    cs:__imp_WmiSetAndCommitObject
0x14003ce1c  test    ebx, ebx
0x14003ce1e  jns     short loc_14003CE31
0x14003ce20  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003ce26  mov     rcx, rax
0x14003ce29  mov     edx, ebx
0x14003ce2b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003ce31  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ce38  cmp     rcx, r12
0x14003ce3b  jz      short loc_14003CE61
0x14003ce3d  test    byte ptr [rcx+1Ch], 4
0x14003ce41  jz      short loc_14003CE61
0x14003ce43  cmp     byte ptr [rcx+19h], 2
0x14003ce47  jb      short loc_14003CE61
0x14003ce49  mov     rcx, [rcx+10h]
0x14003ce4d  lea     r8, WPP_48f931ced3963915480c4dfc938e4579_Traceguids
0x14003ce54  mov     edx, 30h ; '0'
0x14003ce59  mov     r9d, ebx
0x14003ce5c  call    WPP_SF_d
0x14003ce61  mov     eax, ebx
0x14003ce63  add     rsp, 60h
0x14003ce67  pop     r15
0x14003ce69  pop     r14
0x14003ce6b  pop     r12
0x14003ce6d  pop     rdi
0x14003ce6e  pop     rsi
0x14003ce6f  pop     rbp
0x14003ce70  pop     rbx
0x14003ce71  retn
```
