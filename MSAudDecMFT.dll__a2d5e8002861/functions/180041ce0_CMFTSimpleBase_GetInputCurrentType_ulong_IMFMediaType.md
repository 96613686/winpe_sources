# CMFTSimpleBase::GetInputCurrentType(ulong,IMFMediaType * *)

- ea: `0x180041ce0`
- end: `0x180041db8`
- name: `?GetInputCurrentType@CMFTSimpleBase@@UEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(CMFTSimpleBase *this, int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180036d70`
- `0x180041ce0`
- `0x1800960c0`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180041d46`
- `MFPlat!MFCreateMediaType` at `0x180041d46`

## pseudocode

```c
__int64 __fastcall CMFTSimpleBase::GetInputCurrentType(CMFTSimpleBase *this, int a2, struct IMFMediaType **a3)
{
  HRESULT v7; // ebx
  CMFTSimpleBase *v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = this;
  (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 208LL))(this);
  if ( a2 )
  {
    (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 216LL))(this);
    return 3222091443LL;
  }
  else if ( *((_QWORD *)this + 5) )
  {
    v7 = MFCreateMediaType(a3);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 256LL))(*((_QWORD *)this + 5), *a3);
      if ( v7 < 0 )
      {
        if ( *a3 )
        {
          ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
          *a3 = 0;
        }
      }
    }
    (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 216LL))(this);
    return (unsigned int)v7;
  }
  else
  {
    CMFTSimpleBase::LockIt::~LockIt((CMFTSimpleBase::LockIt *)&v8);
    return 3222105440LL;
  }
}

```

## disassembly

```asm
0x180041ce0  mov     [rsp+arg_8], rbx
0x180041ce5  mov     [rsp+arg_10], rsi
0x180041cea  push    rdi
0x180041ceb  sub     rsp, 20h
0x180041cef  mov     rsi, r8
0x180041cf2  mov     ebx, edx
0x180041cf4  mov     rdi, rcx
0x180041cf7  mov     [rsp+28h+arg_0], rcx
0x180041cfc  mov     rax, [rcx]
0x180041cff  mov     rax, [rax+0D0h]
0x180041d06  call    cs:__guard_dispatch_icall_fptr
0x180041d0c  test    ebx, ebx
0x180041d0e  jz      short loc_180041D2B
0x180041d10  mov     rax, [rdi]
0x180041d13  mov     rcx, rdi
0x180041d16  mov     rax, [rax+0D8h]
0x180041d1d  call    cs:__guard_dispatch_icall_fptr
0x180041d23  nop
0x180041d24  mov     eax, 0C00D36B3h
0x180041d29  jmp     short loc_180041DA7
0x180041d2b  cmp     qword ptr [rdi+28h], 0
0x180041d30  jnz     short loc_180041D43
0x180041d32  lea     rcx, [rsp+28h+arg_0]; this
0x180041d37  call    ??1LockIt@CMFTSimpleBase@@QEAA@XZ; CMFTSimpleBase::LockIt::~LockIt(void)
0x180041d3c  mov     eax, 0C00D6D60h
0x180041d41  jmp     short loc_180041DA7
0x180041d43  mov     rcx, rsi; ppMFType
0x180041d46  call    cs:__imp_MFCreateMediaType
0x180041d4d  nop     dword ptr [rax+rax+00h]
0x180041d52  mov     ebx, eax
0x180041d54  test    eax, eax
0x180041d56  js      short loc_180041D91
0x180041d58  mov     rcx, [rdi+28h]
0x180041d5c  mov     rax, [rcx]
0x180041d5f  mov     rdx, [rsi]
0x180041d62  mov     rax, [rax+100h]
0x180041d69  call    cs:__guard_dispatch_icall_fptr
0x180041d6f  mov     ebx, eax
0x180041d71  test    eax, eax
0x180041d73  jns     short loc_180041D91
0x180041d75  mov     rcx, [rsi]
0x180041d78  test    rcx, rcx
0x180041d7b  jz      short loc_180041D91
0x180041d7d  mov     rax, [rcx]
0x180041d80  mov     rax, [rax+10h]
0x180041d84  call    cs:__guard_dispatch_icall_fptr
0x180041d8a  mov     qword ptr [rsi], 0
0x180041d91  mov     rax, [rdi]
0x180041d94  mov     rcx, rdi
0x180041d97  mov     rax, [rax+0D8h]
0x180041d9e  call    cs:__guard_dispatch_icall_fptr
0x180041da4  nop
0x180041da5  mov     eax, ebx
0x180041da7  mov     rbx, [rsp+28h+arg_8]
0x180041dac  mov     rsi, [rsp+28h+arg_10]
0x180041db1  add     rsp, 20h
0x180041db5  pop     rdi
0x180041db6  retn
```
