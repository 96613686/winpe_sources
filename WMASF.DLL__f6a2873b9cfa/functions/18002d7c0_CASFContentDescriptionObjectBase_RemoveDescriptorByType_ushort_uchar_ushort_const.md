# CASFContentDescriptionObjectBase::RemoveDescriptorByType(ushort,uchar,ushort const *)

- ea: `0x18002d7c0`
- end: `0x18002d93c`
- name: `?RemoveDescriptorByType@CASFContentDescriptionObjectBase@@UEAAJGEPEBG@Z`
- size: `380`
- prototype: `__int64 __fastcall(CASFContentDescriptionObjectBase *__hidden this, unsigned __int16, unsigned __int8, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800011c0`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18002d44c`
- `0x18002d6bc`
- `0x18002d7c0`
- `0x180030a00`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFContentDescriptionObjectBase::RemoveDescriptorByType(
        struct IWMSCriticalSection **this,
        __int16 a2,
        char a3,
        const unsigned __int16 *a4)
{
  struct IWMSCriticalSection *v8; // rcx
  int v9; // ebx
  int v10; // ebx
  unsigned int v12; // esi
  unsigned int v13; // ebx
  char *v14; // r14
  __int64 Ptr; // rax
  int v16; // r10d
  __int64 v17; // rdi
  void *v18; // rcx
  _BYTE v19[8]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v20; // [rsp+28h] [rbp-18h] BYREF
  __int16 v21; // [rsp+30h] [rbp-10h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v19, this[4]);
  v8 = this[5];
  if ( !v8 )
  {
    v9 = -1072887818;
LABEL_8:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v19);
    return (unsigned int)v9;
  }
  v20 = 0;
  v9 = ASFFindHeaderObject(
         (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v8,
         (__int64)&CLSID_ASFLanguageListObject,
         (__int64)&IID_IASFLanguageListObject,
         (__int64)&v20);
  if ( v9 < 0 )
    goto LABEL_8;
  v21 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int16 *))(*(_QWORD *)v20 + 120LL))(
          v20,
          a4,
          &v21);
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v10 < 0 )
  {
    v9 = -1072887854;
    goto LABEL_8;
  }
  v12 = *((_DWORD *)this + 158);
  v13 = 0;
  if ( !v12 )
    goto LABEL_21;
  v14 = (char *)(this + 10);
  do
  {
    Ptr = CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::GetPtr(v14, v13);
    v17 = Ptr;
    if ( Ptr && a2 == *(_WORD *)(Ptr + 4) && a3 == *(_BYTE *)Ptr && v21 == *(_WORD *)(Ptr + 2) )
    {
      v18 = *(void **)(Ptr + 8);
      if ( v18 )
        operator delete(v18);
      operator delete(*(void **)(v17 + 16));
      CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::RemoveAt(v14, v13--);
      v16 = 1;
      --v12;
    }
    ++v13;
  }
  while ( v13 < v12 );
  if ( v16 )
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v19);
    return 0;
  }
  else
  {
LABEL_21:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v19);
    return 3222079472LL;
  }
}

```

## disassembly

```asm
0x18002d7c0  mov     [rsp-28h+arg_8], rbx
0x18002d7c5  mov     [rsp-28h+arg_10], rsi
0x18002d7ca  push    rbp
0x18002d7cb  push    rdi
0x18002d7cc  push    r12
0x18002d7ce  push    r14
0x18002d7d0  push    r15
0x18002d7d2  mov     rbp, rsp
0x18002d7d5  sub     rsp, 40h
0x18002d7d9  mov     rax, cs:__security_cookie
0x18002d7e0  xor     rax, rsp
0x18002d7e3  mov     [rbp+var_8], rax
0x18002d7e7  movzx   r12d, dx
0x18002d7eb  mov     rdi, rcx
0x18002d7ee  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002d7f2  mov     rsi, r9
0x18002d7f5  lea     rcx, [rbp+var_20]; this
0x18002d7f9  mov     r15b, r8b
0x18002d7fc  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002d801  mov     rcx, [rdi+28h]
0x18002d805  test    rcx, rcx
0x18002d808  jnz     short loc_18002D811
0x18002d80a  mov     ebx, 0C00D07F6h
0x18002d80f  jmp     short loc_18002D87B
0x18002d811  lea     r9, [rbp+var_18]
0x18002d815  mov     [rbp+var_18], 0
0x18002d81d  lea     r8, IID_IASFLanguageListObject
0x18002d824  lea     rdx, CLSID_ASFLanguageListObject
0x18002d82b  call    ASFFindHeaderObject
0x18002d830  mov     ebx, eax
0x18002d832  test    eax, eax
0x18002d834  js      short loc_18002D87B
0x18002d836  mov     rcx, [rbp+var_18]
0x18002d83a  lea     r8, [rbp+var_10]
0x18002d83e  xor     eax, eax
0x18002d840  mov     rdx, rsi
0x18002d843  mov     [rbp+var_10], ax
0x18002d847  mov     rax, [rcx]
0x18002d84a  mov     rax, [rax+78h]
0x18002d84e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d853  mov     rcx, [rbp+var_18]
0x18002d857  mov     ebx, eax
0x18002d859  test    rcx, rcx
0x18002d85c  jz      short loc_18002D872
0x18002d85e  mov     rdx, [rcx]
0x18002d861  mov     rax, [rdx+10h]
0x18002d865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d86a  mov     [rbp+var_18], 0
0x18002d872  test    ebx, ebx
0x18002d874  jns     short loc_18002D88B
0x18002d876  mov     ebx, 0C00D07D2h
0x18002d87b  lea     rcx, [rbp+var_20]; this
0x18002d87f  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002d884  mov     eax, ebx
0x18002d886  jmp     loc_18002D917
0x18002d88b  mov     esi, [rdi+278h]
0x18002d891  xor     r10d, r10d
0x18002d894  xor     ebx, ebx
0x18002d896  test    esi, esi
0x18002d898  jz      short loc_18002D909
0x18002d89a  lea     r14, [rdi+50h]
0x18002d89e  mov     edx, ebx
0x18002d8a0  mov     rcx, r14
0x18002d8a3  call    ?GetPtr@?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEAAPEAUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@K@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::GetPtr(ulong)
0x18002d8a8  mov     rdi, rax
0x18002d8ab  test    rax, rax
0x18002d8ae  jz      short loc_18002D8F1
0x18002d8b0  cmp     r12w, [rax+4]
0x18002d8b5  jnz     short loc_18002D8F1
0x18002d8b7  cmp     r15b, [rax]
0x18002d8ba  jnz     short loc_18002D8F1
0x18002d8bc  movzx   ecx, word ptr [rax+2]
0x18002d8c0  cmp     [rbp+var_10], cx
0x18002d8c4  jnz     short loc_18002D8F1
0x18002d8c6  mov     rcx, [rax+8]; Block
0x18002d8ca  test    rcx, rcx
0x18002d8cd  jz      short loc_18002D8D4
0x18002d8cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d8d4  mov     rcx, [rdi+10h]; Block
0x18002d8d8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d8dd  mov     edx, ebx
0x18002d8df  mov     rcx, r14
0x18002d8e2  call    ?RemoveAt@?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEAAHKK@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::RemoveAt(ulong,ulong)
0x18002d8e7  dec     ebx
0x18002d8e9  mov     r10d, 1
0x18002d8ef  dec     esi
0x18002d8f1  inc     ebx
0x18002d8f3  cmp     ebx, esi
0x18002d8f5  jb      short loc_18002D89E
0x18002d8f7  test    r10d, r10d
0x18002d8fa  jz      short loc_18002D909
0x18002d8fc  lea     rcx, [rbp+var_20]; this
0x18002d900  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002d905  xor     eax, eax
0x18002d907  jmp     short loc_18002D917
0x18002d909  lea     rcx, [rbp+var_20]; this
0x18002d90d  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002d912  mov     eax, 0C00D07F0h
0x18002d917  mov     rcx, [rbp+var_8]
0x18002d91b  xor     rcx, rsp; StackCookie
0x18002d91e  call    __security_check_cookie
0x18002d923  lea     r11, [rsp+40h+var_s0]
0x18002d928  mov     rbx, [r11+38h]
0x18002d92c  mov     rsi, [r11+40h]
0x18002d930  mov     rsp, r11
0x18002d933  pop     r15
0x18002d935  pop     r14
0x18002d937  pop     r12
0x18002d939  pop     rdi
0x18002d93a  pop     rbp
0x18002d93b  retn
```
