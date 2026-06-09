# CInterceptor_IWbemSyncObjectSink_PutClassAsync::SetStatus(long,long,ushort *,IWbemClassObject *)

- ea: `0x14003ce80`
- end: `0x14003cfd2`
- name: `?SetStatus@CInterceptor_IWbemSyncObjectSink_PutClassAsync@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncObjectSink_PutClassAsync *__hidden this, int, int, unsigned __int16 *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009120`
- `0x1400234b8`
- `0x140028dd4`
- `0x14003ce80`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x14003cf76`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14003cf76`
- `wbemcomn!GetMemLogObject` at `0x14003cf80`
- `wbemcomn!GetMemLogObject` at `0x14003cf80`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003cf8b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003cf8b`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncObjectSink_PutClassAsync::SetStatus(
        CInterceptor_IWbemSyncObjectSink_PutClassAsync *this,
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
    WPP_SF_DDqSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, a3, a2, a3, (char)this, (__int64)a4, (char)a5);
  }
  v9 = CCommon_IWbemSyncObjectSink::SetStatus(this, a2, a3, a4, a5);
  v10 = (_QWORD *)*((_QWORD *)this + 21);
  v11 = v9;
  if ( v10 && (a2 & 0xFFFFE0FF) == 0 )
    WmiSetAndCommitObject(
      qword_140061410,
      1,
      v10[78],
      *(_QWORD *)(v10[75] + 64LL),
      v10[77],
      v10[76],
      v10[79],
      *((_DWORD *)this + 38),
      *((_QWORD *)this + 20));
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
      50,
      WPP_48f931ced3963915480c4dfc938e4579_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14003ce80  mov     rax, rsp
0x14003ce83  push    rbx
0x14003ce84  push    rbp
0x14003ce85  push    rsi
0x14003ce86  push    rdi
0x14003ce87  push    r12
0x14003ce89  push    r14
0x14003ce8b  push    r15
0x14003ce8d  sub     rsp, 60h
0x14003ce91  mov     rbp, r9
0x14003ce94  mov     r14d, r8d
0x14003ce97  mov     esi, edx
0x14003ce99  mov     rdi, rcx
0x14003ce9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cea3  lea     r12, WPP_GLOBAL_Control
0x14003ceaa  mov     r15, [rsp+98h+arg_20]
0x14003ceb2  cmp     rcx, r12
0x14003ceb5  jz      short loc_14003CEE4
0x14003ceb7  test    byte ptr [rcx+1Ch], 4
0x14003cebb  jz      short loc_14003CEE4
0x14003cebd  cmp     byte ptr [rcx+19h], 5
0x14003cec1  jb      short loc_14003CEE4
0x14003cec3  mov     rcx, [rcx+10h]
0x14003cec7  mov     edx, 31h ; '1'
0x14003cecc  mov     [rax-60h], r15
0x14003ced0  mov     [rax-68h], r9
0x14003ced4  mov     r9d, esi
0x14003ced7  mov     [rax-70h], rdi
0x14003cedb  mov     [rax-78h], r8d
0x14003cedf  call    WPP_SF_DDqSq
0x14003cee4  mov     r9, rbp; unsigned __int16 *
0x14003cee7  mov     [rsp+98h+var_78], r15; struct IWbemClassObject *
0x14003ceec  mov     r8d, r14d; int
0x14003ceef  mov     edx, esi; int
0x14003cef1  mov     rcx, rdi; this
0x14003cef4  call    ?SetStatus@CCommon_IWbemSyncObjectSink@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z; CCommon_IWbemSyncObjectSink::SetStatus(long,long,ushort *,IWbemClassObject *)
0x14003cef9  mov     r8, [rdi+0A8h]
0x14003cf00  mov     ebx, eax
0x14003cf02  test    r8, r8
0x14003cf05  jz      short loc_14003CF7C
0x14003cf07  test    esi, 0FFFFE0FFh
0x14003cf0d  jnz     short loc_14003CF7C
0x14003cf0f  mov     rcx, [rdi+0A0h]
0x14003cf16  mov     edx, 1
0x14003cf1b  mov     eax, [rdi+98h]
0x14003cf21  mov     r9, [r8+258h]
0x14003cf28  mov     [rsp+98h+var_40], r15
0x14003cf2d  mov     [rsp+98h+var_48], rbp
0x14003cf32  mov     [rsp+98h+var_50], r14d
0x14003cf37  mov     r9, [r9+40h]
0x14003cf3b  mov     [rsp+98h+var_58], rcx
0x14003cf40  mov     rcx, cs:qword_140061410
0x14003cf47  mov     [rsp+98h+var_60], eax
0x14003cf4b  mov     rax, [r8+278h]
0x14003cf52  mov     [rsp+98h+var_68], rax
0x14003cf57  mov     rax, [r8+260h]
0x14003cf5e  mov     [rsp+98h+var_70], rax
0x14003cf63  mov     rax, [r8+268h]
0x14003cf6a  mov     r8, [r8+270h]
0x14003cf71  mov     [rsp+98h+var_78], rax
0x14003cf76  call    cs:__imp_WmiSetAndCommitObject
0x14003cf7c  test    ebx, ebx
0x14003cf7e  jns     short loc_14003CF91
0x14003cf80  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003cf86  mov     rcx, rax
0x14003cf89  mov     edx, ebx
0x14003cf8b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003cf91  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cf98  cmp     rcx, r12
0x14003cf9b  jz      short loc_14003CFC1
0x14003cf9d  test    byte ptr [rcx+1Ch], 4
0x14003cfa1  jz      short loc_14003CFC1
0x14003cfa3  cmp     byte ptr [rcx+19h], 2
0x14003cfa7  jb      short loc_14003CFC1
0x14003cfa9  mov     rcx, [rcx+10h]
0x14003cfad  lea     r8, WPP_48f931ced3963915480c4dfc938e4579_Traceguids
0x14003cfb4  mov     edx, 32h ; '2'
0x14003cfb9  mov     r9d, ebx
0x14003cfbc  call    WPP_SF_d
0x14003cfc1  mov     eax, ebx
0x14003cfc3  add     rsp, 60h
0x14003cfc7  pop     r15
0x14003cfc9  pop     r14
0x14003cfcb  pop     r12
0x14003cfcd  pop     rdi
0x14003cfce  pop     rsi
0x14003cfcf  pop     rbp
0x14003cfd0  pop     rbx
0x14003cfd1  retn
```
