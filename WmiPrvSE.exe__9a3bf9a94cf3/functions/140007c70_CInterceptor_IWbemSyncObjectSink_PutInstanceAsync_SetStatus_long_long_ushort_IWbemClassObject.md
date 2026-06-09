# CInterceptor_IWbemSyncObjectSink_PutInstanceAsync::SetStatus(long,long,ushort *,IWbemClassObject *)

- ea: `0x140007c70`
- end: `0x140007de1`
- name: `?SetStatus@CInterceptor_IWbemSyncObjectSink_PutInstanceAsync@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncObjectSink_PutInstanceAsync *__hidden this, int, int, unsigned __int16 *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140007c70`
- `0x140009120`
- `0x1400234b8`
- `0x140028dd4`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x140007d8c`
- `NCObjAPI!WmiSetAndCommitObject` at `0x140007d8c`
- `wbemcomn!GetMemLogObject` at `0x140007dcb`
- `wbemcomn!GetMemLogObject` at `0x140007dcb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140007dd6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140007dd6`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncObjectSink_PutInstanceAsync::SetStatus(
        CInterceptor_IWbemSyncObjectSink_PutInstanceAsync *this,
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
    WPP_SF_DDqSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, a3, a2, a3, (char)this, (__int64)a4, (char)a5);
  }
  v9 = CCommon_IWbemSyncObjectSink::SetStatus(this, a2, a3, a4, a5);
  v10 = (_QWORD *)*((_QWORD *)this + 21);
  v11 = v9;
  if ( v10 && (a2 & 0xFFFFE0FF) == 0 )
    WmiSetAndCommitObject(
      qword_140061428,
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
      52,
      WPP_48f931ced3963915480c4dfc938e4579_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140007c70  push    rbx
0x140007c72  push    rbp
0x140007c73  push    rsi
0x140007c74  push    rdi
0x140007c75  push    r12
0x140007c77  push    r14
0x140007c79  push    r15
0x140007c7b  sub     rsp, 60h
0x140007c7f  mov     rbp, r9
0x140007c82  mov     r14d, r8d
0x140007c85  mov     esi, edx
0x140007c87  mov     rdi, rcx
0x140007c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007c91  lea     r12, WPP_GLOBAL_Control
0x140007c98  mov     r15, [rsp+98h+arg_20]
0x140007ca0  cmp     rcx, r12
0x140007ca3  jz      short loc_140007CAF
0x140007ca5  test    byte ptr [rcx+1Ch], 4
0x140007ca9  jnz     loc_140007D97
0x140007caf  mov     r9, rbp; unsigned __int16 *
0x140007cb2  mov     [rsp+98h+var_78], r15; struct IWbemClassObject *
0x140007cb7  mov     r8d, r14d; int
0x140007cba  mov     edx, esi; int
0x140007cbc  mov     rcx, rdi; this
0x140007cbf  call    ?SetStatus@CCommon_IWbemSyncObjectSink@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z; CCommon_IWbemSyncObjectSink::SetStatus(long,long,ushort *,IWbemClassObject *)
0x140007cc4  mov     r8, [rdi+0A8h]
0x140007ccb  mov     ebx, eax
0x140007ccd  test    r8, r8
0x140007cd0  jnz     short loc_140007D1D
0x140007cd2  test    ebx, ebx
0x140007cd4  js      loc_140007DCB
0x140007cda  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ce1  cmp     rcx, r12
0x140007ce4  jnz     short loc_140007CF7
0x140007ce6  mov     eax, ebx
0x140007ce8  add     rsp, 60h
0x140007cec  pop     r15
0x140007cee  pop     r14
0x140007cf0  pop     r12
0x140007cf2  pop     rdi
0x140007cf3  pop     rsi
0x140007cf4  pop     rbp
0x140007cf5  pop     rbx
0x140007cf6  retn
0x140007cf7  test    byte ptr [rcx+1Ch], 4
0x140007cfb  jz      short loc_140007CE6
0x140007cfd  cmp     byte ptr [rcx+19h], 2
0x140007d01  jb      short loc_140007CE6
0x140007d03  mov     rcx, [rcx+10h]
0x140007d07  lea     r8, WPP_48f931ced3963915480c4dfc938e4579_Traceguids
0x140007d0e  mov     edx, 34h ; '4'
0x140007d13  mov     r9d, ebx
0x140007d16  call    WPP_SF_d
0x140007d1b  jmp     short loc_140007CE6
0x140007d1d  test    esi, 0FFFFE0FFh
0x140007d23  jnz     short loc_140007CD2
0x140007d25  mov     rcx, [rdi+0A0h]
0x140007d2c  mov     edx, 1
0x140007d31  mov     eax, [rdi+98h]
0x140007d37  mov     r9, [r8+258h]
0x140007d3e  mov     [rsp+98h+var_40], r15
0x140007d43  mov     [rsp+98h+var_48], rbp
0x140007d48  mov     [rsp+98h+var_50], r14d
0x140007d4d  mov     r9, [r9+40h]
0x140007d51  mov     [rsp+98h+var_58], rcx
0x140007d56  mov     rcx, cs:qword_140061428
0x140007d5d  mov     dword ptr [rsp+98h+var_60], eax
0x140007d61  mov     rax, [r8+278h]
0x140007d68  mov     [rsp+98h+var_68], rax
0x140007d6d  mov     rax, [r8+260h]
0x140007d74  mov     [rsp+98h+var_70], rax
0x140007d79  mov     rax, [r8+268h]
0x140007d80  mov     r8, [r8+270h]
0x140007d87  mov     [rsp+98h+var_78], rax
0x140007d8c  call    cs:__imp_WmiSetAndCommitObject
0x140007d92  jmp     loc_140007CD2
0x140007d97  cmp     byte ptr [rcx+19h], 5
0x140007d9b  jb      loc_140007CAF
0x140007da1  mov     rcx, [rcx+10h]
0x140007da5  mov     edx, 33h ; '3'
0x140007daa  mov     [rsp+98h+var_60], r15
0x140007daf  mov     r9d, esi
0x140007db2  mov     [rsp+98h+var_68], rbp
0x140007db7  mov     [rsp+98h+var_70], rdi
0x140007dbc  mov     dword ptr [rsp+98h+var_78], r14d
0x140007dc1  call    WPP_SF_DDqSq
0x140007dc6  jmp     loc_140007CAF
0x140007dcb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140007dd1  mov     rcx, rax
0x140007dd4  mov     edx, ebx
0x140007dd6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140007ddc  jmp     loc_140007CDA
```
