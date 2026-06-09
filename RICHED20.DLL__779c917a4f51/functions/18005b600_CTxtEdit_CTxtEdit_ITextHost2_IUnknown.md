# CTxtEdit::CTxtEdit(ITextHost2 *,IUnknown *)

- ea: `0x18005b600`
- end: `0x18005b76a`
- name: `??0CTxtEdit@@QEAA@PEAVITextHost2@@PEAUIUnknown@@@Z`
- size: `362`
- prototype: `CTxtEdit *__fastcall(CTxtEdit *__hidden this, struct ITextHost2 *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180031ba0`

## callees

- `0x18004915c`
- `0x18005b600`
- `0x18008e4a4`
- `0x18008e4c0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18005b667`
- `KERNEL32!EnterCriticalSection` at `0x18005b667`
- `KERNEL32!LeaveCriticalSection` at `0x18005b6b4`
- `KERNEL32!LeaveCriticalSection` at `0x18005b6b4`
- `KERNEL32!GetCurrentThreadId` at `0x18005b673`
- `KERNEL32!GetCurrentThreadId` at `0x18005b673`

## pseudocode

```c
CTxtEdit *__fastcall CTxtEdit::CTxtEdit(CTxtEdit *this, struct ITextHost2 *a2, struct IUnknown *a3)
{
  struct IUnknown *v3; // rdi
  DWORD CurrentThreadId; // eax
  bool v8; // zf
  int ThreadState; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  struct CThreadData *ThreadData; // rax
  CTxtEdit *result; // rax

  v3 = (struct IUnknown *)((char *)this + 232);
  *(_QWORD *)this = &CTxtEdit::`vftable'{for `ITextServices'};
  *((_QWORD *)this + 1) = &CTxtEdit::`vftable'{for `IRichEditOle'};
  *((_QWORD *)this + 2) = &CTxtEdit::`vftable'{for `ITextDocument2'};
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_WORD *)this + 60) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 29) = &CTxtEdit::CUnknown::`vftable';
  EnterCriticalSection(&g_CriticalSection);
  ++CW32System::_cRefs;
  CurrentThreadId = GetCurrentThreadId();
  v8 = !CW32System::_fOleinitCheckDisabled;
  HIDWORD(v3[1].lpVtbl) = CurrentThreadId;
  if ( v8 && CThreadData::_dwTlsIndex != -1 )
  {
    ThreadState = CThreadData::GetThreadState();
    if ( ThreadState )
    {
      if ( ThreadState == 2 )
        goto LABEL_7;
    }
    else
    {
      CThreadData::SetThreadState(1, v10, v11);
    }
    ThreadData = CThreadData::GetThreadData();
    ++*(_DWORD *)ThreadData;
  }
LABEL_7:
  LeaveCriticalSection(&g_CriticalSection);
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_DWORD *)this + 66) = 24;
  if ( a3 )
    v3 = a3;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_DWORD *)this + 60) = 1;
  *((_QWORD *)this + 12) = this;
  *((_WORD *)this + 98) = -1;
  *((_QWORD *)this + 28) = v3;
  *((_QWORD *)this + 6) = a2;
  *((_WORD *)this + 138) = -1;
  *((_WORD *)this + 139) = -1;
  result = this;
  *((_DWORD *)this + 54) = 0x7FFF;
  return result;
}

```

## disassembly

```asm
0x18005b600  push    rbx
0x18005b602  push    rbp
0x18005b603  push    rsi
0x18005b604  push    rdi
0x18005b605  push    r14
0x18005b607  sub     rsp, 20h
0x18005b60b  xor     r14d, r14d
0x18005b60e  lea     rdi, [rcx+0E8h]
0x18005b615  lea     rax, ??_7CTxtEdit@@6BITextServices@@@; const CTxtEdit::`vftable'{for `ITextServices'}
0x18005b61c  mov     rbx, rcx
0x18005b61f  mov     [rcx], rax
0x18005b622  mov     rsi, r8
0x18005b625  lea     rax, ??_7CTxtEdit@@6BIRichEditOle@@@; const CTxtEdit::`vftable'{for `IRichEditOle'}
0x18005b62c  mov     rbp, rdx
0x18005b62f  mov     [rcx+8], rax
0x18005b633  lea     rax, ??_7CTxtEdit@@6BITextDocument2@@@; const CTxtEdit::`vftable'{for `ITextDocument2'}
0x18005b63a  mov     [rcx+10h], rax
0x18005b63e  lea     rax, ??_7CUnknown@CTxtEdit@@6B@; const CTxtEdit::CUnknown::`vftable'
0x18005b645  mov     [rcx+60h], r14
0x18005b649  mov     [rcx+68h], r14
0x18005b64d  mov     [rcx+70h], r14
0x18005b651  mov     [rcx+78h], r14w
0x18005b656  mov     [rcx+80h], r14
0x18005b65d  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005b664  mov     [rdi], rax
0x18005b667  call    cs:__imp_EnterCriticalSection
0x18005b66d  inc     cs:?_cRefs@CW32System@@0KA; ulong CW32System::_cRefs
0x18005b673  call    cs:__imp_GetCurrentThreadId
0x18005b679  cmp     cs:?_fOleinitCheckDisabled@CW32System@@2_NA, r14b; bool CW32System::_fOleinitCheckDisabled
0x18005b680  mov     [rdi+0Ch], eax
0x18005b683  jnz     short loc_18005B6AD
0x18005b685  cmp     cs:?_dwTlsIndex@CThreadData@@0KA, 0FFFFFFFFh; ulong CThreadData::_dwTlsIndex
0x18005b68c  jz      short loc_18005B6AD
0x18005b68e  call    ?GetThreadState@CThreadData@@CA?AW4ThreadState@1@XZ; CThreadData::GetThreadState(void)
0x18005b693  test    eax, eax
0x18005b695  jnz     short loc_18005B6A1
0x18005b697  lea     ecx, [rax+1]
0x18005b69a  call    ?SetThreadState@CThreadData@@CAXW4ThreadState@1@@Z; CThreadData::SetThreadState(CThreadData::ThreadState)
0x18005b69f  jmp     short loc_18005B6A6
0x18005b6a1  cmp     eax, 2
0x18005b6a4  jz      short loc_18005B6AD
0x18005b6a6  call    ?GetThreadData@CThreadData@@CAPEAV1@XZ; CThreadData::GetThreadData(void)
0x18005b6ab  inc     dword ptr [rax]
0x18005b6ad  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005b6b4  call    cs:__imp_LeaveCriticalSection
0x18005b6ba  mov     [rbx+0F8h], r14
0x18005b6c1  test    rsi, rsi
0x18005b6c4  mov     [rbx+100h], r14
0x18005b6cb  mov     dword ptr [rbx+108h], 18h
0x18005b6d5  cmovnz  rdi, rsi
0x18005b6d9  mov     [rbx+118h], r14
0x18005b6e0  or      eax, 0FFFFFFFFh
0x18005b6e3  mov     [rbx+120h], r14
0x18005b6ea  mov     [rbx+40h], r14
0x18005b6ee  mov     [rbx+48h], r14
0x18005b6f2  mov     [rbx+50h], r14
0x18005b6f6  mov     [rbx+58h], r14
0x18005b6fa  mov     [rbx+88h], r14
0x18005b701  mov     [rbx+98h], r14
0x18005b708  mov     [rbx+0A0h], r14
0x18005b70f  mov     [rbx+0A8h], r14
0x18005b716  mov     [rbx+128h], r14
0x18005b71d  mov     [rbx+130h], r14
0x18005b724  mov     dword ptr [rbx+0F0h], 1
0x18005b72e  mov     [rbx+60h], rbx
0x18005b732  mov     [rbx+0C4h], ax
0x18005b739  mov     [rbx+0E0h], rdi
0x18005b740  mov     [rbx+30h], rbp
0x18005b744  mov     [rbx+114h], ax
0x18005b74b  mov     [rbx+116h], ax
0x18005b752  mov     rax, rbx
0x18005b755  mov     dword ptr [rbx+0D8h], 7FFFh
0x18005b75f  add     rsp, 20h
0x18005b763  pop     r14
0x18005b765  pop     rdi
0x18005b766  pop     rsi
0x18005b767  pop     rbp
0x18005b768  pop     rbx
0x18005b769  retn
```
