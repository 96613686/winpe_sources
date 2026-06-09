# CLogHandle::CLogHandle(wchar_t const *,wchar_t const *,bool)

- ea: `0x1400234b0`
- end: `0x1400235e1`
- name: `??0CLogHandle@@QEAA@PEB_W0_N@Z`
- size: `305`
- prototype: `CLogHandle *(CLogHandle *__hidden this, const wchar_t *, const wchar_t *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140023d3c`

## callees

- `0x140002e74`
- `0x140003054`
- `0x140005c40`
- `0x140006184`
- `0x1400234b0`

## string_xrefs

- `0x1400235a8`: `MpCopyAccelerator`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
CLogHandle *__fastcall CLogHandle::CLogHandle(CLogHandle *this, const wchar_t *a2, wchar_t **a3)
{
  void **v5; // rsi
  void **v6; // rdi
  void *v7; // rbp
  void *v8; // rcx
  void *v9; // rbp
  const wchar_t *v10; // r8
  void *v11; // rcx
  int v12; // eax
  int v13; // edx
  const wchar_t *v14; // r8
  int v15; // eax
  int v16; // edx

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0x20000;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0x20000;
  *((_BYTE *)this + 48) = 1;
  v5 = (void **)((char *)this + 56);
  *((_QWORD *)this + 7) = 0;
  v6 = (void **)((char *)this + 64);
  *((_QWORD *)this + 8) = 0;
  v7 = operator new[](0x40000u);
  v8 = *(void **)this;
  if ( *(void **)this != v7 )
  {
    if ( v8 )
    {
      operator delete(v8);
      *(_QWORD *)this = 0;
    }
    *(_QWORD *)this = v7;
  }
  v9 = operator new[](saturated_mul(*((_QWORD *)this + 3), 2u));
  v11 = (void *)*((_QWORD *)this + 2);
  if ( v11 != v9 )
  {
    if ( v11 )
      operator delete(v11);
    *((_QWORD *)this + 2) = v9;
    v11 = v9;
  }
  *((_QWORD *)this + 5) = *((_QWORD *)this + 3);
  *((_QWORD *)this + 4) = v11;
  if ( *v5 )
  {
    operator delete(*v5);
    *v5 = 0;
  }
  v12 = CommonUtil::HrDuplicateStringW((CommonUtil *)v5, a3, v10);
  if ( v12 < 0 )
    CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v12, v13);
  if ( *v6 )
  {
    operator delete(*v6);
    *v6 = 0;
  }
  v15 = CommonUtil::HrDuplicateStringW((CommonUtil *)v6, (wchar_t **)L"MpCopyAccelerator", v14);
  if ( v15 < 0 )
    CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v15, v16);
  return this;
}

```

## disassembly

```asm
0x1400234b0  mov     [rsp+arg_8], rbx
0x1400234b5  mov     [rsp+arg_10], rbp
0x1400234ba  mov     [rsp+arg_0], rcx
0x1400234bf  push    rsi
0x1400234c0  push    rdi
0x1400234c1  push    r14
0x1400234c3  sub     rsp, 20h
0x1400234c7  mov     r14, r8
0x1400234ca  mov     rbx, rcx
0x1400234cd  mov     qword ptr [rcx], 0
0x1400234d4  mov     eax, 20000h
0x1400234d9  mov     [rcx+8], rax
0x1400234dd  mov     qword ptr [rcx+10h], 0
0x1400234e5  mov     [rcx+18h], rax
0x1400234e9  mov     byte ptr [rcx+30h], 1
0x1400234ed  lea     rsi, [rcx+38h]
0x1400234f1  mov     qword ptr [rsi], 0
0x1400234f8  lea     rdi, [rcx+40h]
0x1400234fc  mov     qword ptr [rdi], 0
0x140023503  mov     ecx, 40000h; unsigned __int64
0x140023508  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14002350d  mov     rbp, rax
0x140023510  mov     rcx, [rbx]; void *
0x140023513  cmp     rcx, rax
0x140023516  jz      short loc_14002352C
0x140023518  test    rcx, rcx
0x14002351b  jz      short loc_140023529
0x14002351d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140023522  mov     qword ptr [rbx], 0
0x140023529  mov     [rbx], rbp
0x14002352c  mov     eax, 2
0x140023531  mul     qword ptr [rbx+18h]
0x140023535  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14002353c  cmovb   rax, rcx
0x140023540  mov     rcx, rax; unsigned __int64
0x140023543  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140023548  mov     rbp, rax
0x14002354b  mov     rcx, [rbx+10h]; void *
0x14002354f  cmp     rcx, rax
0x140023552  jz      short loc_140023565
0x140023554  test    rcx, rcx
0x140023557  jz      short loc_14002355E
0x140023559  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002355e  mov     [rbx+10h], rbp
0x140023562  mov     rcx, rbp
0x140023565  mov     rax, [rbx+18h]
0x140023569  mov     [rbx+28h], rax
0x14002356d  mov     [rbx+20h], rcx
0x140023571  mov     rcx, [rsi]; void *
0x140023574  test    rcx, rcx
0x140023577  jz      short loc_140023585
0x140023579  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002357e  mov     qword ptr [rsi], 0
0x140023585  mov     rdx, r14; wchar_t **
0x140023588  mov     rcx, rsi; this
0x14002358b  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::HrDuplicateStringW(wchar_t * *,wchar_t const *)
0x140023590  test    eax, eax
0x140023592  js      short loc_1400235D9
0x140023594  mov     rcx, [rdi]; void *
0x140023597  test    rcx, rcx
0x14002359a  jz      short loc_1400235A8
0x14002359c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400235a1  mov     qword ptr [rdi], 0
0x1400235a8  lea     rdx, aMpcopyaccelera_3; "MpCopyAccelerator"
0x1400235af  mov     rcx, rdi; this
0x1400235b2  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::HrDuplicateStringW(wchar_t * *,wchar_t const *)
0x1400235b7  test    eax, eax
0x1400235b9  js      short loc_1400235D1
0x1400235bb  mov     rax, rbx
0x1400235be  mov     rbx, [rsp+38h+arg_8]
0x1400235c3  mov     rbp, [rsp+38h+arg_10]
0x1400235c8  add     rsp, 20h
0x1400235cc  pop     r14
0x1400235ce  pop     rdi
0x1400235cf  pop     rsi
0x1400235d0  retn
0x1400235d1  mov     ecx, eax; this
0x1400235d3  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x1400235d9  mov     ecx, eax; this
0x1400235db  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
```
