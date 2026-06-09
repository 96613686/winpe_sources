# CASFMutualExclusionObjectBase::RemoveExclusionRecordName(ushort,ushort const *)

- ea: `0x180023bd0`
- end: `0x180023d5d`
- name: `?RemoveExclusionRecordName@CASFMutualExclusionObjectBase@@UEAAJGPEBG@Z`
- size: `397`
- prototype: `__int64 __fastcall(CASFMutualExclusionObjectBase *__hidden this, unsigned __int16, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800011c0`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180022510`
- `0x18002257c`
- `0x180023b70`
- `0x180023bd0`
- `0x1800310c0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFMutualExclusionObjectBase::RemoveExclusionRecordName(
        struct IWMSCriticalSection **this,
        unsigned __int16 a2,
        const unsigned __int16 *a3)
{
  unsigned int v3; // ebx
  __int64 (__fastcall ***v6)(__int64, GUID *, __int64 *); // rcx
  int v7; // ebx
  char *v8; // rdi
  unsigned int v9; // esi
  int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // r14d
  __int64 v13; // rax
  _WORD *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  _BYTE v19[8]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v20[16]; // [rsp+28h] [rbp-28h] BYREF
  __int64 v21; // [rsp+38h] [rbp-18h] BYREF
  __int16 v22; // [rsp+40h] [rbp-10h] BYREF

  v3 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v19, this[4]);
  v6 = (__int64 (__fastcall ***)(__int64, GUID *, __int64 *))this[5];
  if ( !v6 )
  {
    v7 = -1072887818;
LABEL_15:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v19);
    return (unsigned int)v7;
  }
  v8 = (char *)(this + 10);
  v9 = v3;
  if ( v3 < *((_DWORD *)v8 + 54) )
  {
    v21 = 0;
    v7 = ASFGetHeaderObject(v6, &CLSID_ASFLanguageListObject, (__int64)&IID_IASFLanguageListObject, (__int64)&v21);
    if ( v7 < 0 )
      goto LABEL_15;
    v22 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int16 *))(*(_QWORD *)v21 + 120LL))(
            v21,
            a3,
            &v22);
    if ( v21 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v21 = 0;
    }
    if ( v10 < 0 )
    {
      v7 = -1072887854;
      goto LABEL_15;
    }
    v11 = 0;
    v12 = *(_DWORD *)(CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](v8, v9) + 480);
    while ( v11 < v12 )
    {
      v13 = CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](v8, v9);
      v14 = (_WORD *)CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::operator[](v13 + 96, v20, v11);
      if ( v22 == *v14 )
      {
        v15 = CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](v8, v9);
        v16 = CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::operator[](v15 + 96, v20, v11);
        operator delete(*(void **)(v16 + 8));
        v17 = CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](v8, v9);
        if ( !(unsigned int)CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::RemoveAt(v17 + 96, v11) )
        {
          v7 = -2147418113;
          goto LABEL_15;
        }
        CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v19);
        return 0;
      }
      ++v11;
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v19);
  return 3222079472LL;
}

```

## disassembly

```asm
0x180023bd0  push    rbp
0x180023bd2  push    rbx
0x180023bd3  push    rsi
0x180023bd4  push    rdi
0x180023bd5  push    r14
0x180023bd7  mov     rbp, rsp
0x180023bda  sub     rsp, 50h
0x180023bde  mov     rax, cs:__security_cookie
0x180023be5  xor     rax, rsp
0x180023be8  mov     [rbp+var_8], rax
0x180023bec  movzx   ebx, dx
0x180023bef  mov     rdi, rcx
0x180023bf2  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180023bf6  mov     r14, r8
0x180023bf9  lea     rcx, [rbp+var_30]; this
0x180023bfd  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180023c02  mov     rcx, [rdi+28h]
0x180023c06  test    rcx, rcx
0x180023c09  jnz     short loc_180023C15
0x180023c0b  mov     ebx, 0C00D07F6h
0x180023c10  jmp     loc_180023D1E
0x180023c15  add     rdi, 50h ; 'P'
0x180023c19  mov     esi, ebx
0x180023c1b  cmp     ebx, [rdi+0D8h]
0x180023c21  jnb     loc_180023D38
0x180023c27  lea     r9, [rbp+var_18]
0x180023c2b  mov     [rbp+var_18], 0
0x180023c33  lea     r8, IID_IASFLanguageListObject
0x180023c3a  lea     rdx, CLSID_ASFLanguageListObject
0x180023c41  call    ASFGetHeaderObject
0x180023c46  mov     ebx, eax
0x180023c48  test    eax, eax
0x180023c4a  js      loc_180023D1E
0x180023c50  mov     rcx, [rbp+var_18]
0x180023c54  lea     r8, [rbp+var_10]
0x180023c58  xor     eax, eax
0x180023c5a  mov     rdx, r14
0x180023c5d  mov     [rbp+var_10], ax
0x180023c61  mov     rax, [rcx]
0x180023c64  mov     rax, [rax+78h]
0x180023c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c6d  mov     rcx, [rbp+var_18]
0x180023c71  mov     ebx, eax
0x180023c73  test    rcx, rcx
0x180023c76  jz      short loc_180023C8C
0x180023c78  mov     rdx, [rcx]
0x180023c7b  mov     rax, [rdx+10h]
0x180023c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c84  mov     [rbp+var_18], 0
0x180023c8c  test    ebx, ebx
0x180023c8e  jns     short loc_180023C9A
0x180023c90  mov     ebx, 0C00D07D2h
0x180023c95  jmp     loc_180023D1E
0x180023c9a  mov     edx, esi
0x180023c9c  mov     rcx, rdi
0x180023c9f  call    ??A?$CTDynArray@PEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBAPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](ulong)
0x180023ca4  xor     ebx, ebx
0x180023ca6  mov     r14d, [rax+1E0h]
0x180023cad  cmp     ebx, r14d
0x180023cb0  jnb     loc_180023D38
0x180023cb6  mov     edx, esi
0x180023cb8  mov     rcx, rdi
0x180023cbb  call    ??A?$CTDynArray@PEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBAPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](ulong)
0x180023cc0  mov     r8d, ebx
0x180023cc3  lea     rdx, [rbp+var_28]
0x180023cc7  lea     rcx, [rax+60h]
0x180023ccb  call    ??A?$CTDynArray@UNAME_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBA?AUNAME_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::operator[](ulong)
0x180023cd0  movzx   ecx, word ptr [rax]
0x180023cd3  cmp     [rbp+var_10], cx
0x180023cd7  jz      short loc_180023CDD
0x180023cd9  inc     ebx
0x180023cdb  jmp     short loc_180023CAD
0x180023cdd  mov     edx, esi
0x180023cdf  mov     rcx, rdi
0x180023ce2  call    ??A?$CTDynArray@PEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBAPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](ulong)
0x180023ce7  mov     r8d, ebx
0x180023cea  lea     rdx, [rbp+var_28]
0x180023cee  lea     rcx, [rax+60h]
0x180023cf2  call    ??A?$CTDynArray@UNAME_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBA?AUNAME_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::operator[](ulong)
0x180023cf7  mov     rcx, [rax+8]; Block
0x180023cfb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023d00  mov     edx, esi
0x180023d02  mov     rcx, rdi
0x180023d05  call    ??A?$CTDynArray@PEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBAPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](ulong)
0x180023d0a  mov     edx, ebx
0x180023d0c  lea     rcx, [rax+60h]
0x180023d10  call    ?RemoveAt@?$CTDynArray@UNAME_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEAAHKK@Z; CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::RemoveAt(ulong,ulong)
0x180023d15  test    eax, eax
0x180023d17  jnz     short loc_180023D2B
0x180023d19  mov     ebx, 8000FFFFh
0x180023d1e  lea     rcx, [rbp+var_30]; this
0x180023d22  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180023d27  mov     eax, ebx
0x180023d29  jmp     short loc_180023D46
0x180023d2b  lea     rcx, [rbp+var_30]; this
0x180023d2f  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180023d34  xor     eax, eax
0x180023d36  jmp     short loc_180023D46
0x180023d38  lea     rcx, [rbp+var_30]; this
0x180023d3c  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180023d41  mov     eax, 0C00D07F0h
0x180023d46  mov     rcx, [rbp+var_8]
0x180023d4a  xor     rcx, rsp; StackCookie
0x180023d4d  call    __security_check_cookie
0x180023d52  add     rsp, 50h
0x180023d56  pop     r14
0x180023d58  pop     rdi
0x180023d59  pop     rsi
0x180023d5a  pop     rbx
0x180023d5b  pop     rbp
0x180023d5c  retn
```
