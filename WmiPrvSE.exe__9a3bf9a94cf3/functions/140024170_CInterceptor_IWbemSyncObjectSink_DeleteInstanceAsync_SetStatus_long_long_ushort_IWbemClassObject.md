# CInterceptor_IWbemSyncObjectSink_DeleteInstanceAsync::SetStatus(long,long,ushort *,IWbemClassObject *)

- ea: `0x140024170`
- end: `0x1400242f0`
- name: `?SetStatus@CInterceptor_IWbemSyncObjectSink_DeleteInstanceAsync@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncObjectSink_DeleteInstanceAsync *__hidden this, int, int, unsigned __int16 *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009120`
- `0x1400234b8`
- `0x140024170`
- `0x140028dd4`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x14002426a`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14002426a`
- `wbemcomn!GetMemLogObject` at `0x1400242da`
- `wbemcomn!GetMemLogObject` at `0x1400242da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400242e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400242e5`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncObjectSink_DeleteInstanceAsync::SetStatus(
        CInterceptor_IWbemSyncObjectSink_DeleteInstanceAsync *this,
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
    WPP_SF_DDqSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, a3, a2, a3, (char)this, (__int64)a4, (char)a5);
  }
  v9 = CCommon_IWbemSyncObjectSink::SetStatus(this, a2, a3, a4, a5);
  v10 = (_QWORD *)*((_QWORD *)this + 21);
  v11 = v9;
  if ( v10 && (a2 & 0xFFFFE0FF) == 0 )
    WmiSetAndCommitObject(
      qword_140061430,
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
      46,
      WPP_48f931ced3963915480c4dfc938e4579_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140024170  push    rbx
0x140024172  push    rbp
0x140024173  push    rsi
0x140024174  push    rdi
0x140024175  push    r12
0x140024177  push    r14
0x140024179  push    r15
0x14002417b  sub     rsp, 60h
0x14002417f  mov     rbp, r9
0x140024182  mov     r14d, r8d
0x140024185  mov     esi, edx
0x140024187  mov     rdi, rcx
0x14002418a  mov     rcx, cs:WPP_GLOBAL_Control
0x140024191  lea     r12, WPP_GLOBAL_Control
0x140024198  mov     r15, [rsp+98h+arg_20]
0x1400241a0  cmp     rcx, r12
0x1400241a3  jz      short loc_1400241AF
0x1400241a5  test    byte ptr [rcx+1Ch], 4
0x1400241a9  jnz     loc_1400242A6
0x1400241af  mov     r9, rbp; unsigned __int16 *
0x1400241b2  mov     [rsp+98h+var_78], r15; struct IWbemClassObject *
0x1400241b7  mov     r8d, r14d; int
0x1400241ba  mov     edx, esi; int
0x1400241bc  mov     rcx, rdi; this
0x1400241bf  call    ?SetStatus@CCommon_IWbemSyncObjectSink@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z; CCommon_IWbemSyncObjectSink::SetStatus(long,long,ushort *,IWbemClassObject *)
0x1400241c4  mov     r8, [rdi+0A8h]
0x1400241cb  mov     ebx, eax
0x1400241cd  test    r8, r8
0x1400241d0  jnz     short loc_1400241FB
0x1400241d2  test    ebx, ebx
0x1400241d4  js      loc_1400242DA
0x1400241da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400241e1  cmp     rcx, r12
0x1400241e4  jnz     loc_140024275
0x1400241ea  mov     eax, ebx
0x1400241ec  add     rsp, 60h
0x1400241f0  pop     r15
0x1400241f2  pop     r14
0x1400241f4  pop     r12
0x1400241f6  pop     rdi
0x1400241f7  pop     rsi
0x1400241f8  pop     rbp
0x1400241f9  pop     rbx
0x1400241fa  retn
0x1400241fb  test    esi, 0FFFFE0FFh
0x140024201  jnz     short loc_1400241D2
0x140024203  mov     rcx, [rdi+0A0h]
0x14002420a  mov     edx, 1
0x14002420f  mov     eax, [rdi+98h]
0x140024215  mov     r9, [r8+258h]
0x14002421c  mov     [rsp+98h+var_40], r15
0x140024221  mov     [rsp+98h+var_48], rbp
0x140024226  mov     [rsp+98h+var_50], r14d
0x14002422b  mov     r9, [r9+40h]
0x14002422f  mov     [rsp+98h+var_58], rcx
0x140024234  mov     rcx, cs:qword_140061430
0x14002423b  mov     dword ptr [rsp+98h+var_60], eax
0x14002423f  mov     rax, [r8+278h]
0x140024246  mov     [rsp+98h+var_68], rax
0x14002424b  mov     rax, [r8+260h]
0x140024252  mov     [rsp+98h+var_70], rax
0x140024257  mov     rax, [r8+268h]
0x14002425e  mov     r8, [r8+270h]
0x140024265  mov     [rsp+98h+var_78], rax
0x14002426a  call    cs:__imp_WmiSetAndCommitObject
0x140024270  jmp     loc_1400241D2
0x140024275  test    byte ptr [rcx+1Ch], 4
0x140024279  jz      loc_1400241EA
0x14002427f  cmp     byte ptr [rcx+19h], 2
0x140024283  jb      loc_1400241EA
0x140024289  mov     rcx, [rcx+10h]
0x14002428d  lea     r8, WPP_48f931ced3963915480c4dfc938e4579_Traceguids
0x140024294  mov     edx, 2Eh ; '.'
0x140024299  mov     r9d, ebx
0x14002429c  call    WPP_SF_d
0x1400242a1  jmp     loc_1400241EA
0x1400242a6  cmp     byte ptr [rcx+19h], 5
0x1400242aa  jb      loc_1400241AF
0x1400242b0  mov     rcx, [rcx+10h]
0x1400242b4  mov     edx, 2Dh ; '-'
0x1400242b9  mov     [rsp+98h+var_60], r15
0x1400242be  mov     r9d, esi
0x1400242c1  mov     [rsp+98h+var_68], rbp
0x1400242c6  mov     [rsp+98h+var_70], rdi
0x1400242cb  mov     dword ptr [rsp+98h+var_78], r14d
0x1400242d0  call    WPP_SF_DDqSq
0x1400242d5  jmp     loc_1400241AF
0x1400242da  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400242e0  mov     rcx, rax
0x1400242e3  mov     edx, ebx
0x1400242e5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400242eb  jmp     loc_1400241DA
```
