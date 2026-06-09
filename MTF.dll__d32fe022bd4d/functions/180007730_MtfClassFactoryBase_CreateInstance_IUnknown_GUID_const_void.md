# MtfClassFactoryBase::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180007730`
- end: `0x180007850`
- name: `?CreateInstance@MtfClassFactoryBase@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `288`
- prototype: `int(MtfClassFactoryBase *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007860`

## callees

- `0x180006074`
- `0x180007730`
- `0x18002f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MtfClassFactoryBase::CreateInstance(
        MtfClassFactoryBase *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 result; // rax
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  try
  {
    v7 = (*(__int64 (__fastcall **)(MtfClassFactoryBase *))(*(_QWORD *)this + 48LL))(this);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(_QWORD, const struct _GUID *, void **))*MEMORY[0])(0, a3, a4);
      v10 = v9;
      if ( v9 >= 0 )
      {
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"mincore\\TextInput\\Dev\\mtf\\PredictionEngine\\include\\MtfClassFactory.h",
          (const char *)(unsigned int)v9,
          v11);
        result = v10;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"mincore\\TextInput\\Dev\\mtf\\PredictionEngine\\include\\MtfClassFactory.h",
        (const char *)(unsigned int)v7,
        v11);
      result = v8;
    }
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180007730  mov     [rsp+arg_0], rbx
0x180007735  mov     [rsp+arg_8], rsi
0x18000773a  push    rdi; int
0x18000773b  sub     rsp, 20h
0x18000773f  mov     rdi, r9
0x180007742  mov     rsi, r8
0x180007745  test    r9, r9
0x180007748  jnz     short loc_180007754
0x18000774a  mov     eax, 80004003h
0x18000774f  jmp     loc_18000783F
0x180007754  mov     qword ptr [r9], 0
0x18000775b  mov     [rsp+28h+arg_18], 0
0x180007764  mov     rax, [rcx]
0x180007767  lea     r8, [rsp+28h+arg_18]
0x18000776c  mov     rax, [rax+30h]
0x180007770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007775  mov     ebx, eax
0x180007777  test    eax, eax
0x180007779  jns     short loc_1800077BC
0x18000777b  mov     rcx, [rsp+28h]; this
0x180007780  mov     r9d, eax; char *
0x180007783  lea     r8, aMincoreTextinp_10; "mincore\\TextInput\\Dev\\mtf\\Predictio"...
0x18000778a  mov     edx, 51h ; 'Q'; void *
0x18000778f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007794  nop
0x180007795  mov     rcx, [rsp+28h+arg_18]
0x18000779a  mov     [rsp+28h+arg_18], 0
0x1800077a3  test    rcx, rcx
0x1800077a6  jz      short loc_1800077B5
0x1800077a8  mov     rax, [rcx]
0x1800077ab  mov     rax, [rax+10h]
0x1800077af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077b4  nop
0x1800077b5  mov     eax, ebx
0x1800077b7  jmp     loc_18000783F
0x1800077bc  mov     rcx, [rsp+28h+arg_18]
0x1800077c1  mov     rax, [rcx]
0x1800077c4  mov     r8, rdi
0x1800077c7  mov     rdx, rsi
0x1800077ca  mov     rax, [rax]
0x1800077cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077d2  mov     ebx, eax
0x1800077d4  test    eax, eax
0x1800077d6  jns     short loc_180007816
0x1800077d8  mov     rcx, [rsp+28h]; this
0x1800077dd  mov     r9d, eax; char *
0x1800077e0  lea     r8, aMincoreTextinp_10; "mincore\\TextInput\\Dev\\mtf\\Predictio"...
0x1800077e7  mov     edx, 52h ; 'R'; void *
0x1800077ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077f1  nop
0x1800077f2  mov     rcx, [rsp+28h+arg_18]
0x1800077f7  mov     [rsp+28h+arg_18], 0
0x180007800  test    rcx, rcx
0x180007803  jz      short loc_180007812
0x180007805  mov     rax, [rcx]
0x180007808  mov     rax, [rax+10h]
0x18000780c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007811  nop
0x180007812  mov     eax, ebx
0x180007814  jmp     short loc_18000783F
0x180007816  mov     rcx, [rsp+28h+arg_18]
0x18000781b  mov     [rsp+28h+arg_18], 0
0x180007824  test    rcx, rcx
0x180007827  jz      short loc_180007836
0x180007829  mov     rax, [rcx]
0x18000782c  mov     rax, [rax+10h]
0x180007830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007835  nop
0x180007836  xor     eax, eax
0x180007838  jmp     short loc_18000783F
0x18000783a  mov     eax, 80004005h
0x18000783f  mov     rbx, [rsp+28h+arg_0]
0x180007844  mov     rsi, [rsp+28h+arg_8]
0x180007849  add     rsp, 20h
0x18000784d  pop     rdi
0x18000784e  retn
```
