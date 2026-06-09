# CInterceptor_IWbemSyncObjectSink_GetObjectAsync::SetStatus(long,long,ushort *,IWbemClassObject *)

- ea: `0x1400089e0`
- end: `0x140008b48`
- name: `?SetStatus@CInterceptor_IWbemSyncObjectSink_GetObjectAsync@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncObjectSink_GetObjectAsync *__hidden this, int, int, unsigned __int16 *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400089e0`
- `0x140009120`
- `0x1400234b8`
- `0x140028dd4`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x140008ab1`
- `NCObjAPI!WmiSetAndCommitObject` at `0x140008ab1`
- `wbemcomn!GetMemLogObject` at `0x140008b32`
- `wbemcomn!GetMemLogObject` at `0x140008b32`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140008b3d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140008b3d`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncObjectSink_GetObjectAsync::SetStatus(
        CInterceptor_IWbemSyncObjectSink_GetObjectAsync *this,
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
    WPP_SF_DDqSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, a3, a2, a3, (char)this, (__int64)a4, (char)a5);
  }
  v9 = CCommon_IWbemSyncObjectSink::SetStatus(this, a2, a3, a4, a5);
  v10 = (_QWORD *)*((_QWORD *)this + 21);
  v11 = v9;
  if ( v10 && (a2 & 0xFFFFE0FF) == 0 )
    WmiSetAndCommitObject(
      qword_140061408,
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
      44,
      WPP_48f931ced3963915480c4dfc938e4579_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400089e0  push    rbx
0x1400089e2  push    rbp
0x1400089e3  push    rsi
0x1400089e4  push    rdi
0x1400089e5  push    r12
0x1400089e7  push    r14
0x1400089e9  push    r15
0x1400089eb  sub     rsp, 60h
0x1400089ef  mov     rbp, r9
0x1400089f2  mov     r14d, r8d
0x1400089f5  mov     esi, edx
0x1400089f7  mov     rdi, rcx
0x1400089fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a01  lea     r12, WPP_GLOBAL_Control
0x140008a08  mov     r15, [rsp+98h+arg_20]
0x140008a10  cmp     rcx, r12
0x140008a13  jz      short loc_140008A1F
0x140008a15  test    byte ptr [rcx+1Ch], 4
0x140008a19  jnz     loc_140008AFE
0x140008a1f  mov     r9, rbp; unsigned __int16 *
0x140008a22  mov     [rsp+98h+var_78], r15; struct IWbemClassObject *
0x140008a27  mov     r8d, r14d; int
0x140008a2a  mov     edx, esi; int
0x140008a2c  mov     rcx, rdi; this
0x140008a2f  call    ?SetStatus@CCommon_IWbemSyncObjectSink@@UEAAJJJPEAGPEAUIWbemClassObject@@@Z; CCommon_IWbemSyncObjectSink::SetStatus(long,long,ushort *,IWbemClassObject *)
0x140008a34  mov     r8, [rdi+0A8h]
0x140008a3b  mov     ebx, eax
0x140008a3d  test    r8, r8
0x140008a40  jz      short loc_140008AB7
0x140008a42  test    esi, 0FFFFE0FFh
0x140008a48  jnz     short loc_140008AB7
0x140008a4a  mov     rcx, [rdi+0A0h]
0x140008a51  mov     edx, 1
0x140008a56  mov     eax, [rdi+98h]
0x140008a5c  mov     r9, [r8+258h]
0x140008a63  mov     [rsp+98h+var_40], r15
0x140008a68  mov     [rsp+98h+var_48], rbp
0x140008a6d  mov     [rsp+98h+var_50], r14d
0x140008a72  mov     r9, [r9+40h]
0x140008a76  mov     [rsp+98h+var_58], rcx
0x140008a7b  mov     rcx, cs:qword_140061408
0x140008a82  mov     dword ptr [rsp+98h+var_60], eax
0x140008a86  mov     rax, [r8+278h]
0x140008a8d  mov     [rsp+98h+var_68], rax
0x140008a92  mov     rax, [r8+260h]
0x140008a99  mov     [rsp+98h+var_70], rax
0x140008a9e  mov     rax, [r8+268h]
0x140008aa5  mov     r8, [r8+270h]
0x140008aac  mov     [rsp+98h+var_78], rax
0x140008ab1  call    cs:__imp_WmiSetAndCommitObject
0x140008ab7  test    ebx, ebx
0x140008ab9  js      short loc_140008B32
0x140008abb  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ac2  cmp     rcx, r12
0x140008ac5  jnz     short loc_140008AD8
0x140008ac7  mov     eax, ebx
0x140008ac9  add     rsp, 60h
0x140008acd  pop     r15
0x140008acf  pop     r14
0x140008ad1  pop     r12
0x140008ad3  pop     rdi
0x140008ad4  pop     rsi
0x140008ad5  pop     rbp
0x140008ad6  pop     rbx
0x140008ad7  retn
0x140008ad8  test    byte ptr [rcx+1Ch], 4
0x140008adc  jz      short loc_140008AC7
0x140008ade  cmp     byte ptr [rcx+19h], 2
0x140008ae2  jb      short loc_140008AC7
0x140008ae4  mov     rcx, [rcx+10h]
0x140008ae8  lea     r8, WPP_48f931ced3963915480c4dfc938e4579_Traceguids
0x140008aef  mov     edx, 2Ch ; ','
0x140008af4  mov     r9d, ebx
0x140008af7  call    WPP_SF_d
0x140008afc  jmp     short loc_140008AC7
0x140008afe  cmp     byte ptr [rcx+19h], 5
0x140008b02  jb      loc_140008A1F
0x140008b08  mov     rcx, [rcx+10h]
0x140008b0c  mov     edx, 2Bh ; '+'
0x140008b11  mov     [rsp+98h+var_60], r15
0x140008b16  mov     r9d, esi
0x140008b19  mov     [rsp+98h+var_68], rbp
0x140008b1e  mov     [rsp+98h+var_70], rdi
0x140008b23  mov     dword ptr [rsp+98h+var_78], r14d
0x140008b28  call    WPP_SF_DDqSq
0x140008b2d  jmp     loc_140008A1F
0x140008b32  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140008b38  mov     rcx, rax
0x140008b3b  mov     edx, ebx
0x140008b3d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140008b43  jmp     loc_140008ABB
```
