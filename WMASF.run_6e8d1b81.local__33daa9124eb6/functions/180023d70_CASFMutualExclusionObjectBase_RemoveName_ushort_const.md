# CASFMutualExclusionObjectBase::RemoveName(ushort const *)

- ea: `0x180023d70`
- end: `0x180023ec1`
- name: `?RemoveName@CASFMutualExclusionObjectBase@@UEAAJPEBG@Z`
- size: `337`
- prototype: `__int64 __fastcall(CASFMutualExclusionObjectBase *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800011c0`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18002257c`
- `0x180023b70`
- `0x180023d70`
- `0x1800310c0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFMutualExclusionObjectBase::RemoveName(
        struct IWMSCriticalSection **this,
        const unsigned __int16 *a2)
{
  __int64 (__fastcall ***v4)(__int64, GUID *, __int64 *); // rcx
  int v5; // ebx
  int v6; // ebx
  unsigned int v7; // esi
  char *v8; // rdi
  unsigned int i; // ebx
  _WORD *v10; // rax
  __int64 v11; // rax
  _BYTE v13[8]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v14[16]; // [rsp+28h] [rbp-28h] BYREF
  __int64 v15; // [rsp+38h] [rbp-18h] BYREF
  __int16 v16; // [rsp+40h] [rbp-10h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v13, this[4]);
  v4 = (__int64 (__fastcall ***)(__int64, GUID *, __int64 *))this[5];
  if ( !v4 )
  {
    v5 = -1072887818;
LABEL_14:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v13);
    return (unsigned int)v5;
  }
  v15 = 0;
  v5 = ASFGetHeaderObject(v4, &CLSID_ASFLanguageListObject, (__int64)&IID_IASFLanguageListObject, (__int64)&v15);
  if ( v5 < 0 )
    goto LABEL_14;
  v16 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int16 *))(*(_QWORD *)v15 + 120LL))(v15, a2, &v16);
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v6 < 0 )
  {
    v5 = -1072887854;
    goto LABEL_14;
  }
  v7 = *((_DWORD *)this + 172);
  v8 = (char *)(this + 38);
  for ( i = 0; ; ++i )
  {
    if ( i >= v7 )
    {
      CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v13);
      return 3222079472LL;
    }
    v10 = (_WORD *)CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::operator[](v8, v14, i);
    if ( v16 == *v10 )
      break;
  }
  v11 = CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::operator[](v8, v14, i);
  operator delete(*(void **)(v11 + 8));
  if ( !(unsigned int)CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::RemoveAt(v8, i) )
  {
    v5 = -2147418113;
    goto LABEL_14;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v13);
  return 0;
}

```

## disassembly

```asm
0x180023d70  mov     [rsp-18h+arg_10], rbx
0x180023d75  push    rbp
0x180023d76  push    rsi
0x180023d77  push    rdi
0x180023d78  mov     rbp, rsp
0x180023d7b  sub     rsp, 50h
0x180023d7f  mov     rax, cs:__security_cookie
0x180023d86  xor     rax, rsp
0x180023d89  mov     [rbp+var_8], rax
0x180023d8d  mov     rsi, rdx
0x180023d90  mov     rdi, rcx
0x180023d93  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180023d97  lea     rcx, [rbp+var_30]; this
0x180023d9b  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180023da0  mov     rcx, [rdi+28h]
0x180023da4  test    rcx, rcx
0x180023da7  jnz     short loc_180023DB3
0x180023da9  mov     ebx, 0C00D07F6h
0x180023dae  jmp     loc_180023E7D
0x180023db3  lea     r9, [rbp+var_18]
0x180023db7  mov     [rbp+var_18], 0
0x180023dbf  lea     r8, IID_IASFLanguageListObject
0x180023dc6  lea     rdx, CLSID_ASFLanguageListObject
0x180023dcd  call    ASFGetHeaderObject
0x180023dd2  mov     ebx, eax
0x180023dd4  test    eax, eax
0x180023dd6  js      loc_180023E7D
0x180023ddc  mov     rcx, [rbp+var_18]
0x180023de0  lea     r8, [rbp+var_10]
0x180023de4  xor     eax, eax
0x180023de6  mov     rdx, rsi
0x180023de9  mov     [rbp+var_10], ax
0x180023ded  mov     rax, [rcx]
0x180023df0  mov     rax, [rax+78h]
0x180023df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023df9  mov     rcx, [rbp+var_18]
0x180023dfd  mov     ebx, eax
0x180023dff  test    rcx, rcx
0x180023e02  jz      short loc_180023E18
0x180023e04  mov     rdx, [rcx]
0x180023e07  mov     rax, [rdx+10h]
0x180023e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e10  mov     [rbp+var_18], 0
0x180023e18  test    ebx, ebx
0x180023e1a  jns     short loc_180023E23
0x180023e1c  mov     ebx, 0C00D07D2h
0x180023e21  jmp     short loc_180023E7D
0x180023e23  mov     esi, [rdi+2B0h]
0x180023e29  add     rdi, 130h
0x180023e30  xor     ebx, ebx
0x180023e32  cmp     ebx, esi
0x180023e34  jnb     short loc_180023E97
0x180023e36  mov     r8d, ebx
0x180023e39  lea     rdx, [rbp+var_28]
0x180023e3d  mov     rcx, rdi
0x180023e40  call    ??A?$CTDynArray@UNAME_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBA?AUNAME_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::operator[](ulong)
0x180023e45  movzx   ecx, word ptr [rax]
0x180023e48  cmp     [rbp+var_10], cx
0x180023e4c  jz      short loc_180023E52
0x180023e4e  inc     ebx
0x180023e50  jmp     short loc_180023E32
0x180023e52  mov     r8d, ebx
0x180023e55  lea     rdx, [rbp+var_28]
0x180023e59  mov     rcx, rdi
0x180023e5c  call    ??A?$CTDynArray@UNAME_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBA?AUNAME_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::operator[](ulong)
0x180023e61  mov     rcx, [rax+8]; Block
0x180023e65  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023e6a  mov     edx, ebx
0x180023e6c  mov     rcx, rdi
0x180023e6f  call    ?RemoveAt@?$CTDynArray@UNAME_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEAAHKK@Z; CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::RemoveAt(ulong,ulong)
0x180023e74  test    eax, eax
0x180023e76  jnz     short loc_180023E8A
0x180023e78  mov     ebx, 8000FFFFh
0x180023e7d  lea     rcx, [rbp+var_30]; this
0x180023e81  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180023e86  mov     eax, ebx
0x180023e88  jmp     short loc_180023EA5
0x180023e8a  lea     rcx, [rbp+var_30]; this
0x180023e8e  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180023e93  xor     eax, eax
0x180023e95  jmp     short loc_180023EA5
0x180023e97  lea     rcx, [rbp+var_30]; this
0x180023e9b  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180023ea0  mov     eax, 0C00D07F0h
0x180023ea5  mov     rcx, [rbp+var_8]
0x180023ea9  xor     rcx, rsp; StackCookie
0x180023eac  call    __security_check_cookie
0x180023eb1  mov     rbx, [rsp+50h+arg_10]
0x180023eb9  add     rsp, 50h
0x180023ebd  pop     rdi
0x180023ebe  pop     rsi
0x180023ebf  pop     rbp
0x180023ec0  retn
```
