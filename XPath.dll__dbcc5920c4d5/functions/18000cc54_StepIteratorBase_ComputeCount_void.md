# StepIteratorBase::ComputeCount(void)

- ea: `0x18000cc54`
- end: `0x18000ccf7`
- name: `?ComputeCount@StepIteratorBase@@AEAAJXZ`
- size: `163`
- prototype: `__int64 __fastcall(StepIteratorBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000db00`

## callees

- `0x1800020b4`
- `0x18000cc54`
- `0x18000e5e0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall StepIteratorBase::ComputeCount(StepIteratorBase *this)
{
  char v1; // bp
  int v2; // r14d
  int v4; // edi
  int v5; // eax
  struct IUnknown *v7; // [rsp+20h] [rbp-48h] BYREF
  int v8; // [rsp+28h] [rbp-40h]
  int v9; // [rsp+2Ch] [rbp-3Ch]
  char v10; // [rsp+30h] [rbp-38h]

  v1 = *((_BYTE *)this + 24);
  v2 = *((_DWORD *)this + 8);
  v7 = 0;
  v8 = 0;
  v9 = 7;
  v10 = 0;
  v4 = XPathNavigatorInternal::InitializePositionTo(&v7, (StepIteratorBase *)((char *)this + 40));
  if ( v4 >= 0 )
  {
    for ( *((_DWORD *)this + 7) = *((_DWORD *)this + 8); ; ++*((_DWORD *)this + 7) )
    {
      v5 = (*(__int64 (__fastcall **)(StepIteratorBase *))(*(_QWORD *)this + 48LL))(this);
      v4 = v5;
      if ( v5 == 1 )
        break;
      if ( v5 < 0 )
        goto LABEL_8;
    }
    *((_BYTE *)this + 24) = v1;
    *((_DWORD *)this + 8) = v2;
    v4 = XPathNavigatorInternal::InitializePositionTo(
           (struct IUnknown **)this + 5,
           (struct XPathNavigatorInternal *)&v7);
    if ( v4 >= 0 )
    {
      *((_BYTE *)this + 25) = 1;
      v4 = 0;
    }
  }
LABEL_8:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000cc54  mov     rax, rsp
0x18000cc57  push    rbx
0x18000cc58  push    rbp
0x18000cc59  push    rsi
0x18000cc5a  push    rdi
0x18000cc5b  push    r14
0x18000cc5d  sub     rsp, 40h
0x18000cc61  mov     bpl, [rcx+18h]
0x18000cc65  lea     rdx, [rcx+28h]; struct XPathNavigatorInternal *
0x18000cc69  mov     r14d, [rcx+20h]
0x18000cc6d  mov     rbx, rcx
0x18000cc70  lea     rcx, [rax-48h]; this
0x18000cc74  mov     qword ptr [rax-48h], 0
0x18000cc7c  mov     dword ptr [rax-40h], 0
0x18000cc83  mov     dword ptr [rax-3Ch], 7
0x18000cc8a  mov     byte ptr [rax-38h], 0
0x18000cc8e  call    ?InitializePositionTo@XPathNavigatorInternal@@QEAAJAEAV1@@Z; XPathNavigatorInternal::InitializePositionTo(XPathNavigatorInternal &)
0x18000cc93  mov     edi, eax
0x18000cc95  test    eax, eax
0x18000cc97  js      short loc_18000CCE0
0x18000cc99  mov     eax, [rbx+20h]
0x18000cc9c  mov     [rbx+1Ch], eax
0x18000cc9f  mov     rax, [rbx]
0x18000cca2  mov     rcx, rbx
0x18000cca5  mov     rax, [rax+30h]
0x18000cca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccae  mov     edi, eax
0x18000ccb0  cmp     eax, 1
0x18000ccb3  jz      short loc_18000CCBE
0x18000ccb5  test    eax, eax
0x18000ccb7  js      short loc_18000CCE0
0x18000ccb9  inc     dword ptr [rbx+1Ch]
0x18000ccbc  jmp     short loc_18000CC9F
0x18000ccbe  lea     rdx, [rsp+68h+var_48]; struct XPathNavigatorInternal *
0x18000ccc3  mov     [rbx+18h], bpl
0x18000ccc7  lea     rcx, [rbx+28h]; this
0x18000cccb  mov     [rbx+20h], r14d
0x18000cccf  call    ?InitializePositionTo@XPathNavigatorInternal@@QEAAJAEAV1@@Z; XPathNavigatorInternal::InitializePositionTo(XPathNavigatorInternal &)
0x18000ccd4  mov     edi, eax
0x18000ccd6  test    eax, eax
0x18000ccd8  js      short loc_18000CCE0
0x18000ccda  mov     byte ptr [rbx+19h], 1
0x18000ccde  xor     edi, edi
0x18000cce0  lea     rcx, [rsp+68h+var_48]
0x18000cce5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ccea  mov     eax, edi
0x18000ccec  add     rsp, 40h
0x18000ccf0  pop     r14
0x18000ccf2  pop     rdi
0x18000ccf3  pop     rsi
0x18000ccf4  pop     rbp
0x18000ccf5  pop     rbx
0x18000ccf6  retn
```
