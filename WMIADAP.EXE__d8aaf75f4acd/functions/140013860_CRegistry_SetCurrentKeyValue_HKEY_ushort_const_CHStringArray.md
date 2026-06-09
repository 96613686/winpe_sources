# CRegistry::SetCurrentKeyValue(HKEY__ *,ushort const *,CHStringArray &)

- ea: `0x140013860`
- end: `0x1400139e8`
- name: `?SetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHStringArray@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(CRegistry *this, HKEY, const unsigned __int16 *, struct CHStringArray *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013a80`

## callees

- `0x140001a6f`
- `0x14000298c`
- `0x140006284`
- `0x14000ff40`
- `0x1400111d0`
- `0x140012490`
- `0x140013860`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400139bf`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400139bf`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1400138f2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1400138f2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400139b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400139b4`

## pseudocode

```c
__int64 __fastcall CRegistry::SetCurrentKeyValue(
        CRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3,
        struct CHStringArray *a4)
{
  int v7; // esi
  unsigned int i; // ebx
  const unsigned __int16 *v9; // rax
  __int64 cbData; // rsi
  BYTE *v11; // rax
  BYTE *lpData; // r14
  unsigned __int16 *Buffer; // rax
  const unsigned __int16 *v14; // rax
  __int64 v15; // r15
  unsigned int j; // ebx
  unsigned int v17; // ebx
  int pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  BYTE *v20; // [rsp+38h] [rbp-30h]
  const unsigned __int16 *v21; // [rsp+88h] [rbp+20h] BYREF

  v7 = 0;
  for ( i = 0; (signed int)i < *((_DWORD *)a4 + 2); ++i )
  {
    CHStringArray::GetAt(a4, &v21, i);
    if ( v21 == afxPchNil )
      v9 = (const unsigned __int16 *)byte_140024890;
    else
      v9 = v21 - 6;
    v7 += 2 * *((_DWORD *)v9 + 1) + 2;
    CHString::~CHString(&v21);
  }
  cbData = (unsigned int)(v7 + 2);
  v11 = (BYTE *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)cbData, 2u));
  lpData = v11;
  v20 = v11;
  if ( !v11 )
  {
    pExceptionObject = 0;
    throw (CHeap_Exception *)&pExceptionObject;
  }
  try
  {
    memset_0(v11, 0, 2 * cbData);
    v15 = 0;
    for ( j = 0; (signed int)j < *((_DWORD *)a4 + 2); ++j )
    {
      CHStringArray::GetAt(a4, &v21, j);
      Buffer = CHString::GetBuffer(&v21, 0);
      StringCchCopyW((unsigned __int16 *)&lpData[2 * v15], (unsigned int)(cbData - v15), Buffer);
      v14 = (const unsigned __int16 *)byte_140024890;
      if ( v21 != afxPchNil )
        v14 = v21 - 6;
      v15 = (unsigned int)(*((_DWORD *)v14 + 1) + 1 + v15);
      CHString::~CHString(&v21);
    }
    v17 = RegSetValueExW(a2, a3, 0, 7u, lpData, cbData);
    CWin32DefaultArena::WbemMemFree(lpData);
    v20 = 0;
  }
  catch ( CHeap_Exception )
  {
    CWin32DefaultArena::WbemMemFree(v20);
    throw;
  }
  memset_0(v11, 0, 2 * cbData);
}

```

## disassembly

```asm
0x140013860  mov     [rsp+arg_0], rbx
0x140013865  mov     [rsp+arg_8], rsi
0x14001386a  push    rdi
0x14001386b  push    r12
0x14001386d  push    r13
0x14001386f  push    r14
0x140013871  push    r15
0x140013873  sub     rsp, 40h
0x140013877  mov     rdi, r9
0x14001387a  mov     r12, r8
0x14001387d  mov     r13, rdx
0x140013880  xor     esi, esi
0x140013882  xor     ebx, ebx
0x140013884  cmp     [r9+8], ebx
0x140013888  jle     short loc_1400138D8
0x14001388a  mov     r8d, ebx
0x14001388d  lea     rdx, [rsp+68h+arg_18]
0x140013895  mov     rcx, rdi
0x140013898  call    ?GetAt@CHStringArray@@QEBA?AVCHString@@H@Z; CHStringArray::GetAt(int)
0x14001389d  mov     rax, [rsp+68h+arg_18]
0x1400138a5  cmp     rax, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x1400138ac  jnz     short loc_1400138B7
0x1400138ae  lea     rax, byte_140024890
0x1400138b5  jmp     short loc_1400138BB
0x1400138b7  add     rax, 0FFFFFFFFFFFFFFF4h
0x1400138bb  mov     eax, [rax+4]
0x1400138be  lea     esi, [rsi+rax*2]
0x1400138c1  add     esi, 2
0x1400138c4  lea     rcx, [rsp+68h+arg_18]; this
0x1400138cc  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1400138d1  inc     ebx
0x1400138d3  cmp     ebx, [rdi+8]
0x1400138d6  jl      short loc_14001388A
0x1400138d8  mov     eax, 2
0x1400138dd  add     esi, eax
0x1400138df  mov     ebx, esi
0x1400138e1  mul     rbx
0x1400138e4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400138eb  cmovb   rax, rcx
0x1400138ef  mov     rcx, rax
0x1400138f2  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1400138f8  mov     r14, rax
0x1400138fb  mov     [rsp+68h+var_30], rax
0x140013900  test    rax, rax
0x140013903  jnz     short loc_14001391B
0x140013905  mov     [rsp+68h+pExceptionObject], eax
0x140013909  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x140013910  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x140013915  call    _CxxThrowException_0
0x14001391b  lea     r8, [rsi+rsi]; Size
0x14001391f  xor     edx, edx; Val
0x140013921  mov     rcx, r14; void *
0x140013924  call    memset_0
0x140013929  xor     r15d, r15d
0x14001392c  xor     ebx, ebx
0x14001392e  cmp     ebx, [rdi+8]
0x140013931  jge     short loc_14001399C
0x140013933  mov     r8d, ebx
0x140013936  lea     rdx, [rsp+68h+arg_18]
0x14001393e  mov     rcx, rdi
0x140013941  call    ?GetAt@CHStringArray@@QEBA?AVCHString@@H@Z; CHStringArray::GetAt(int)
0x140013946  nop
0x140013947  xor     edx, edx; int
0x140013949  lea     rcx, [rsp+68h+arg_18]; this
0x140013951  call    ?GetBuffer@CHString@@QEAAPEAGH@Z; CHString::GetBuffer(int)
0x140013956  mov     edx, esi
0x140013958  sub     edx, r15d; unsigned __int64
0x14001395b  lea     rcx, [r14+r15*2]; unsigned __int16 *
0x14001395f  mov     r8, rax; unsigned __int16 *
0x140013962  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140013967  mov     r11, [rsp+68h+arg_18]
0x14001396f  cmp     r11, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x140013976  lea     rax, byte_140024890
0x14001397d  jz      short loc_140013983
0x14001397f  lea     rax, [r11-0Ch]
0x140013983  mov     eax, [rax+4]
0x140013986  inc     eax
0x140013988  add     r15d, eax
0x14001398b  lea     rcx, [rsp+68h+arg_18]; this
0x140013993  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140013998  inc     ebx
0x14001399a  jmp     short loc_14001392E
0x14001399c  mov     [rsp+68h+cbData], esi; cbData
0x1400139a0  mov     [rsp+68h+lpData], r14; lpData
0x1400139a5  mov     r9d, 7; dwType
0x1400139ab  xor     r8d, r8d; Reserved
0x1400139ae  mov     rdx, r12; lpValueName
0x1400139b1  mov     rcx, r13; hKey
0x1400139b4  call    cs:__imp_RegSetValueExW
0x1400139ba  mov     ebx, eax
0x1400139bc  mov     rcx, r14
0x1400139bf  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1400139c5  mov     [rsp+68h+var_30], 0
0x1400139ce  mov     eax, ebx
0x1400139d0  mov     rbx, [rsp+68h+arg_0]
0x1400139d5  mov     rsi, [rsp+68h+arg_8]
0x1400139da  add     rsp, 40h
0x1400139de  pop     r15
0x1400139e0  pop     r14
0x1400139e2  pop     r13
0x1400139e4  pop     r12
0x1400139e6  pop     rdi
0x1400139e7  retn
```
