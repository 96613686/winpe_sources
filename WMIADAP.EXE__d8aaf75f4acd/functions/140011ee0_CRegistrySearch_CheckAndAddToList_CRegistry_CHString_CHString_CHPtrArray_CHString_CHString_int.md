# CRegistrySearch::CheckAndAddToList(CRegistry *,CHString,CHString,CHPtrArray &,CHString,CHString,int)

- ea: `0x140011ee0`
- end: `0x140012038`
- name: `?CheckAndAddToList@CRegistrySearch@@AEAAXPEAVCRegistry@@VCHString@@1AEAVCHPtrArray@@11H@Z`
- size: `344`
- prototype: `void __fastcall(__int64, CRegistry *, CHString *, const unsigned __int16 **, int *, const wchar_t **, const unsigned __int16 **, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013510`

## callees

- `0x14000298c`
- `0x14000ff40`
- `0x14000ffc0`
- `0x140010c50`
- `0x140011ee0`
- `0x140012e50`
- `0x1400147e0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140011f3b`
- `msvcrt!_wcsicmp` at `0x140011f3b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140011fa6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140011fa6`

## pseudocode

```c
void __fastcall CRegistrySearch::CheckAndAddToList(
        __int64 a1,
        CRegistry *a2,
        CHString *a3,
        const unsigned __int16 **a4,
        int *a5,
        const wchar_t **a6,
        const unsigned __int16 **a7,
        int a8)
{
  BOOL v10; // ebx
  const unsigned __int16 **v11; // rdi
  const wchar_t *v12; // rax
  __int64 v13; // rcx
  int v14; // edx
  int v15; // r8d
  bool v16; // zf
  wchar_t *v17; // rbx
  int pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  wchar_t *String2[4]; // [rsp+28h] [rbp-20h] BYREF

  if ( a8 == 3 )
  {
    v10 = 0;
    String2[0] = (wchar_t *)afxPchNil;
    v11 = a6;
    if ( !CRegistry::GetCurrentSubKeyValue((HKEY *)a2, *a7, (struct CHString *)String2) )
      v10 = _wcsicmp(*a6, String2[0]) == 0;
    CHString::~CHString((const unsigned __int16 **)String2);
    goto LABEL_10;
  }
  v11 = a6;
  if ( a8 == 1 )
  {
    v12 = *a6;
    v13 = *(_QWORD *)a3 - (_QWORD)*a6;
    do
    {
      v14 = *(const wchar_t *)((char *)v12 + v13);
      v15 = *v12 - v14;
      if ( v15 )
        break;
      ++v12;
    }
    while ( v14 );
    v10 = v15 == 0;
LABEL_10:
    v16 = !v10;
    goto LABEL_12;
  }
  v16 = (unsigned int)CHString::Find(a3, *a6) == 0;
LABEL_12:
  if ( !v16 )
  {
    v17 = (wchar_t *)CWin32DefaultArena::WbemMemAlloc(8u);
    String2[0] = v17;
    if ( !v17 )
    {
      pExceptionObject = 0;
      throw (CHeap_Exception *)&pExceptionObject;
    }
    *(_QWORD *)v17 = afxPchNil;
    String2[0] = v17;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      CHString::operator=((const unsigned __int16 **)v17, a4);
      CHPtrArray::SetAtGrow((CHPtrArray *)a5, a5[2], v17);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &CHeap_Exception `RTTI Type Descriptor', 0) )
      {
        CHString::`scalar deleting destructor'((CHString *)String2[0], 1u);
        throw;
      }
    }
  }
  CHString::~CHString((const unsigned __int16 **)a3);
  CHString::~CHString(a4);
  CHString::~CHString(v11);
  CHString::~CHString(a7);
}

```

## disassembly

```asm
0x140011ee0  mov     r11, rsp
0x140011ee3  mov     [r11+8], rbx
0x140011ee7  mov     [r11+20h], r9
0x140011eeb  mov     [r11+18h], r8
0x140011eef  push    rsi
0x140011ef0  push    rdi
0x140011ef1  push    r14
0x140011ef3  sub     rsp, 30h
0x140011ef7  mov     r14, r9
0x140011efa  mov     rsi, r8
0x140011efd  mov     r9, rdx
0x140011f00  cmp     [rsp+48h+arg_38], 3
0x140011f08  jnz     short loc_140011F55
0x140011f0a  xor     ebx, ebx
0x140011f0c  mov     rax, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x140011f13  mov     [r11-20h], rax
0x140011f17  lea     r8, [r11-20h]; struct CHString *
0x140011f1b  mov     rdx, [r11+38h]
0x140011f1f  mov     rdx, [rdx]; unsigned __int16 *
0x140011f22  mov     rcx, r9; this
0x140011f25  call    ?GetCurrentSubKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentSubKeyValue(ushort const *,CHString &)
0x140011f2a  mov     rdi, [rsp+48h+arg_28]
0x140011f2f  test    eax, eax
0x140011f31  jnz     short loc_140011F49
0x140011f33  mov     rdx, [rsp+48h+String2]; String2
0x140011f38  mov     rcx, [rdi]; String1
0x140011f3b  call    cs:__imp__wcsicmp
0x140011f41  lea     ecx, [rbx+1]
0x140011f44  test    eax, eax
0x140011f46  cmovz   ebx, ecx
0x140011f49  lea     rcx, [rsp+48h+String2]; this
0x140011f4e  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140011f53  jmp     short loc_140011F8E
0x140011f55  mov     ecx, 1
0x140011f5a  mov     rdi, [rsp+48h+arg_28]
0x140011f5f  cmp     [rsp+48h+arg_38], ecx
0x140011f66  jnz     short loc_140011F92
0x140011f68  mov     rax, [rdi]
0x140011f6b  mov     rcx, [r8]
0x140011f6e  sub     rcx, rax
0x140011f71  movzx   r8d, word ptr [rax]
0x140011f75  movzx   edx, word ptr [rax+rcx]
0x140011f79  sub     r8d, edx
0x140011f7c  jnz     short loc_140011F86
0x140011f7e  add     rax, 2
0x140011f82  test    edx, edx
0x140011f84  jnz     short loc_140011F71
0x140011f86  xor     ebx, ebx
0x140011f88  test    r8d, r8d
0x140011f8b  setz    bl
0x140011f8e  test    ebx, ebx
0x140011f90  jmp     short loc_140011F9F
0x140011f92  mov     rdx, [rdi]; unsigned __int16 *
0x140011f95  mov     rcx, rsi; this
0x140011f98  call    ?Find@CHString@@QEBAHPEBG@Z; CHString::Find(ushort const *)
0x140011f9d  test    eax, eax
0x140011f9f  jz      short loc_140011FE9
0x140011fa1  mov     ecx, 8
0x140011fa6  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140011fac  mov     rbx, rax
0x140011faf  mov     [rsp+48h+String2], rax
0x140011fb4  test    rax, rax
0x140011fb7  jz      short loc_14001201E
0x140011fb9  mov     rax, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x140011fc0  mov     [rbx], rax
0x140011fc3  mov     [rsp+48h+String2], rbx
0x140011fc8  test    rbx, rbx
0x140011fcb  jz      short loc_14001201E
0x140011fcd  mov     rdx, r14
0x140011fd0  mov     rcx, rbx; this
0x140011fd3  call    ??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x140011fd8  mov     r8, rbx; void *
0x140011fdb  mov     rcx, [rsp+48h+arg_20]; this
0x140011fe0  mov     edx, [rcx+8]; int
0x140011fe3  call    ?SetAtGrow@CHPtrArray@@QEAAXHPEAX@Z; CHPtrArray::SetAtGrow(int,void *)
0x140011fe8  nop
0x140011fe9  mov     rcx, rsi; this
0x140011fec  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140011ff1  nop
0x140011ff2  mov     rcx, r14; this
0x140011ff5  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140011ffa  nop
0x140011ffb  mov     rcx, rdi; this
0x140011ffe  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140012003  nop
0x140012004  mov     rcx, [rsp+48h+arg_30]; this
0x14001200c  mov     rbx, [rsp+48h+arg_0]
0x140012011  add     rsp, 30h
0x140012015  pop     r14
0x140012017  pop     rdi
0x140012018  pop     rsi
0x140012019  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x14001201e  mov     [rsp+48h+pExceptionObject], 0
0x140012026  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x14001202d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140012032  call    _CxxThrowException_0
```
