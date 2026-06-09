# CFilterSink::GetHandleToImpersonate(void * *)

- ea: `0x14003cb14`
- end: `0x14003cc2c`
- name: `?GetHandleToImpersonate@CFilterSink@@QEAAJPEAPEAX@Z`
- size: `280`
- prototype: `__int64 __fastcall(CFilterSink *__hidden this, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002a090`
- `0x14002d394`

## callees

- `0x140015958`
- `0x1400317a8`
- `0x14003cb14`
- `0x14003de50`
- `0x14004bb64`
- `0x14004bd34`

## string_xrefs

- `0x14003cb63`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx"`
- `0x14003cc06`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx"`
- `0x14003cb57`: `[SrchFilterDaemon] Thread Pipe failed to switch into read mode`
- `0x14003cbfa`: `[SrchFilterDaemon] Thread Pipe failed to switch into write mode`
- `0x14003cb74`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrsink.cxx`
- `0x14003cc17`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrsink.cxx`

## pseudocode

```c
__int64 __fastcall CFilterSink::GetHandleToImpersonate(CFilterSink *this, void **a2)
{
  int v4; // eax
  const wchar_t *v5; // r9
  unsigned int v6; // ebx
  int BufferWithCallback; // ebx
  unsigned int v8; // edx
  void **v10; // rcx
  int v11; // eax
  const wchar_t *v12; // r9
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = (void *)-1LL;
  v4 = CShMPipe::Want2ReadWithCallback(
         *((CShMPipe **)this + 133),
         *((struct ISearchIdleCallback **)this + 332),
         *((_DWORD *)this + 666));
  v6 = v4;
  if ( v4 < 0 )
  {
    if ( v4 != -2147217996 )
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrsink.cxx\"",
        (const wchar_t *)0x10E,
        (unsigned int)L"[SrchFilterDaemon] Thread Pipe failed to switch into read mode",
        v5);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x110,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx",
      (const char *)v6,
      v13);
  }
  BufferWithCallback = CFilterSink::ReadBufferWithCallback(this);
  if ( BufferWithCallback >= 0 )
  {
    v8 = *((_DWORD *)this + 661);
    if ( v8 >= 8 )
    {
      v10 = (void **)*((_QWORD *)this + 329);
      *((_DWORD *)this + 660) += 8;
      *((_QWORD *)this + 329) = v10 + 1;
      *((_DWORD *)this + 661) = v8 - 8;
      *a2 = *v10;
      v11 = CShMPipe::Want2Write(*((CShMPipe **)this + 133), v8);
      BufferWithCallback = v11;
      if ( v11 < 0 )
      {
        if ( v11 != -2147217996 )
          SearchIndexerTrace::Error(
            (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrsink.cxx\"",
            (const wchar_t *)0x12B,
            (unsigned int)L"[SrchFilterDaemon] Thread Pipe failed to switch into write mode",
            v12);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x12D,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx",
          (const char *)(unsigned int)BufferWithCallback,
          v13);
      }
    }
    else
    {
      return (unsigned int)-2147218158;
    }
  }
  return (unsigned int)BufferWithCallback;
}

```

## disassembly

```asm
0x14003cb14  mov     [rsp+arg_0], rbx
0x14003cb19  mov     [rsp+arg_8], rsi
0x14003cb1e  push    rdi; int
0x14003cb1f  sub     rsp, 20h
0x14003cb23  mov     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x14003cb2a  mov     rsi, rdx
0x14003cb2d  mov     r8d, [rcx+0A68h]; unsigned int
0x14003cb34  mov     rdi, rcx
0x14003cb37  mov     rdx, [rcx+0A60h]; struct ISearchIdleCallback *
0x14003cb3e  mov     rcx, [rcx+428h]; this
0x14003cb45  call    ?Want2ReadWithCallback@CShMPipe@@QEAAJPEAUISearchIdleCallback@@K@Z; CShMPipe::Want2ReadWithCallback(ISearchIdleCallback *,ulong)
0x14003cb4a  mov     ebx, eax
0x14003cb4c  test    eax, eax
0x14003cb4e  jns     short loc_14003CB89
0x14003cb50  cmp     eax, 80040DB4h
0x14003cb55  jz      short loc_14003CB6F
0x14003cb57  lea     r8, aSrchfilterdaem_35; "[SrchFilterDaemon] Thread Pipe failed t"...
0x14003cb5e  mov     edx, 10Eh; wchar_t *
0x14003cb63  lea     rcx, aOnecoreuapBase_25; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14003cb6a  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14003cb6f  mov     rcx, [rsp+28h]; this
0x14003cb74  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\appmodel\\search\\sea"...
0x14003cb7b  mov     r9d, ebx; char *
0x14003cb7e  mov     edx, 110h; void *
0x14003cb83  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003cb89  mov     rcx, rdi; this
0x14003cb8c  call    ?ReadBufferWithCallback@CFilterSink@@AEAAJXZ; CFilterSink::ReadBufferWithCallback(void)
0x14003cb91  mov     ebx, eax
0x14003cb93  test    eax, eax
0x14003cb95  js      short loc_14003CBA7
0x14003cb97  mov     edx, [rdi+0A54h]; int
0x14003cb9d  cmp     edx, 8
0x14003cba0  jnb     short loc_14003CBB9
0x14003cba2  mov     ebx, 80040D12h
0x14003cba7  mov     rsi, [rsp+28h+arg_8]
0x14003cbac  mov     eax, ebx
0x14003cbae  mov     rbx, [rsp+28h+arg_0]
0x14003cbb3  add     rsp, 20h
0x14003cbb7  pop     rdi
0x14003cbb8  retn
0x14003cbb9  mov     rcx, [rdi+0A48h]
0x14003cbc0  add     dword ptr [rdi+0A50h], 8
0x14003cbc7  lea     rax, [rcx+8]
0x14003cbcb  mov     [rdi+0A48h], rax
0x14003cbd2  lea     eax, [rdx-8]
0x14003cbd5  mov     [rdi+0A54h], eax
0x14003cbdb  mov     rax, [rcx]
0x14003cbde  mov     [rsi], rax
0x14003cbe1  mov     rcx, [rdi+428h]; this
0x14003cbe8  call    ?Want2Write@CShMPipe@@QEAAJH@Z; CShMPipe::Want2Write(int)
0x14003cbed  mov     ebx, eax
0x14003cbef  test    eax, eax
0x14003cbf1  jns     short loc_14003CBA7
0x14003cbf3  cmp     eax, 80040DB4h
0x14003cbf8  jz      short loc_14003CC12
0x14003cbfa  lea     r8, aSrchfilterdaem_17; "[SrchFilterDaemon] Thread Pipe failed t"...
0x14003cc01  mov     edx, 12Bh; wchar_t *
0x14003cc06  lea     rcx, aOnecoreuapBase_25; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14003cc0d  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14003cc12  mov     rcx, [rsp+28h]; this
0x14003cc17  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\appmodel\\search\\sea"...
0x14003cc1e  mov     r9d, ebx; char *
0x14003cc21  mov     edx, 12Dh; void *
0x14003cc26  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
