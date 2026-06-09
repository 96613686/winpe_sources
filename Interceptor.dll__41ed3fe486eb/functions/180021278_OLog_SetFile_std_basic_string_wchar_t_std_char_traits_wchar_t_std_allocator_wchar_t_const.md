# OLog::SetFile(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180021278`
- end: `0x180021356`
- name: `?SetFile@OLog@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800054f0`

## callees

- `0x180004044`
- `0x180021278`
- `0x180021358`
- `0x180021610`
- `0x180021d84`
- `0x1800266e0`
- `0x1800282a0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800212c7`
- `KERNEL32!CloseHandle` at `0x1800212c7`

## string_xrefs

- `0x18002132e`: `A log file is already open.`

## pseudocode

```c
void OLog::SetFile()
{
  OLog *v0; // rbx
  void *v1; // rcx
  _QWORD *v2; // rax
  _BYTE pExceptionObject[912]; // [rsp+20h] [rbp-3A8h] BYREF

  v0 = OLog::sinstance;
  if ( *((_QWORD *)OLog::sinstance + 3) )
  {
    OLog::Flush(OLog::sinstance, *(_BYTE *)OLog::sinstance);
    v1 = (void *)*((_QWORD *)v0 + 14);
    if ( v1 != (void *)-1LL )
    {
      CloseHandle(v1);
      v2 = (_QWORD *)((char *)v0 + 80);
      *((_QWORD *)v0 + 14) = -1;
      *((_QWORD *)v0 + 12) = 0;
      if ( *((_QWORD *)v0 + 13) > 7u )
        v2 = (_QWORD *)*v2;
      *(_WORD *)v2 = 0;
    }
  }
  if ( *((_QWORD *)v0 + 14) != -1 )
  {
    OException::OException(pExceptionObject, 47, L"A log file is already open.");
    throw (OException *)pExceptionObject;
  }
  std::wstring::operator=((char *)v0 + 8);
  OLog::EnsureUniqueFileName(v0);
}

```

## disassembly

```asm
0x180021278  mov     [rsp+arg_0], rbx
0x18002127d  mov     [rsp+arg_10], rbp
0x180021282  mov     [rsp+arg_18], rsi
0x180021287  push    rdi
0x180021288  sub     rsp, 3C0h
0x18002128f  mov     rax, cs:__security_cookie
0x180021296  xor     rax, rsp
0x180021299  mov     [rsp+3C8h+var_18], rax
0x1800212a1  mov     rbx, cs:?sinstance@OLog@@2PEAV1@EA; OLog * OLog::sinstance
0x1800212a8  xor     ebp, ebp
0x1800212aa  mov     rsi, rdx
0x1800212ad  cmp     [rbx+18h], rbp
0x1800212b1  jz      short loc_1800212EA
0x1800212b3  mov     dl, [rbx]
0x1800212b5  mov     rcx, rbx
0x1800212b8  call    ?Flush@OLog@@QEAAXW4MinimumSeverity@Logging@Mso@@@Z; OLog::Flush(Mso::Logging::MinimumSeverity)
0x1800212bd  mov     rcx, [rbx+70h]; hObject
0x1800212c1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800212c5  jz      short loc_1800212EA
0x1800212c7  call    cs:__imp_CloseHandle
0x1800212cd  lea     rax, [rbx+50h]
0x1800212d1  mov     qword ptr [rbx+70h], 0FFFFFFFFFFFFFFFFh
0x1800212d9  mov     [rax+10h], rbp
0x1800212dd  cmp     qword ptr [rax+18h], 7
0x1800212e2  jbe     short loc_1800212E7
0x1800212e4  mov     rax, [rax]
0x1800212e7  mov     [rax], bp
0x1800212ea  cmp     qword ptr [rbx+70h], 0FFFFFFFFFFFFFFFFh
0x1800212ef  jnz     short loc_18002132E
0x1800212f1  mov     rdx, rsi
0x1800212f4  lea     rcx, [rbx+8]; void *
0x1800212f8  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800212fd  mov     rcx, rbx; this
0x180021300  call    ?EnsureUniqueFileName@OLog@@AEAAXXZ; OLog::EnsureUniqueFileName(void)
0x180021305  mov     rcx, [rsp+3C8h+var_18]
0x18002130d  xor     rcx, rsp; StackCookie
0x180021310  call    __security_check_cookie
0x180021315  lea     r11, [rsp+3C8h+var_8]
0x18002131d  mov     rbx, [r11+10h]
0x180021321  mov     rbp, [r11+20h]
0x180021325  mov     rsi, [r11+28h]
0x180021329  mov     rsp, r11
0x18002132c  pop     rdi
0x18002132d  retn
0x18002132e  lea     r8, aALogFileIsAlre; "A log file is already open."
0x180021335  mov     edx, 2Fh ; '/'
0x18002133a  lea     rcx, [rsp+3C8h+pExceptionObject]
0x18002133f  call    ??$?0$0BM@@OException@@QEAA@W4exceptionType@et@@AEAY0BM@$$CB_W@Z; OException::OException(et::exceptionType,wchar_t const (&)[28])
0x180021344  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18002134b  lea     rcx, [rsp+3C8h+pExceptionObject]; pExceptionObject
0x180021350  call    _CxxThrowException
```
