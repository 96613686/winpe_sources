# CRuleReader::SettingChecksumWouldAffectReadPath(ushort const *,int *)

- ea: `0x180011ab0`
- end: `0x180011c3c`
- name: `?SettingChecksumWouldAffectReadPath@CRuleReader@@UEAAJPEBGPEAH@Z`
- size: `396`
- prototype: `__int64 __fastcall(CRuleReader *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000ba70`
- `0x18000c048`
- `0x1800108a4`
- `0x180011ab0`
- `0x1800132dc`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180011aec`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180011b9d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180011c27`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180011aec`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180011b9d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180011c27`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRuleReader::SettingChecksumWouldAffectReadPath(
        CRuleReader *this,
        const unsigned __int16 *a2,
        int *a3)
{
  unsigned int v4; // edi
  unsigned int i; // ebx
  bool v6; // r15
  char v7; // r13
  char v8; // r12
  unsigned int j; // ebp
  const WCHAR *v10; // rbx
  unsigned __int64 v11; // r14
  int v12; // eax
  int v14; // [rsp+70h] [rbp+8h] BYREF
  LPCWSTR lpString2; // [rsp+78h] [rbp+10h]
  int *v16; // [rsp+80h] [rbp+18h]
  LPCWSTR lpString1; // [rsp+88h] [rbp+20h] BYREF

  v16 = a3;
  lpString2 = a2;
  v4 = 0;
  *a3 = 0;
  for ( i = 0; i < *((_DWORD *)this + 6); ++i )
  {
    if ( !lstrcmpW(*(LPCWSTR *)(((unsigned __int64)i << 6) + *((_QWORD *)this + 2) + 48), a2) )
    {
      v6 = 0;
      v7 = 1;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpString1);
      v8 = 0;
      for ( j = 0; ; ++j )
      {
        v10 = lpString1;
        if ( j >= *((_DWORD *)this + 6) )
          break;
        v11 = *((_QWORD *)this + 2) + ((unsigned __int64)j << 6);
        v14 = 0;
        v12 = (*(__int64 (__fastcall **)(CRuleReader *, unsigned __int64, int *))(*(_QWORD *)this + 40LL))(
                this,
                v11,
                &v14);
        v4 = v12;
        if ( v12 < 0 )
        {
          if ( g_doStackCaptures )
            DoStackCapture(v12);
          ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
          return v4;
        }
        if ( v14 )
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 5) + 40LL))(
                 *((_QWORD *)this + 5),
                 *(_QWORD *)(v11 + 24),
                 0);
          if ( (v4 & 0x80000000) == 0 )
          {
            if ( lstrcmpW(*(LPCWSTR *)(v11 + 48), lpString2) )
            {
              if ( v8 )
                v6 = lstrcmpW(v10, *(LPCWSTR *)(v11 + 24)) != 0;
              else
                v7 = 0;
              break;
            }
            if ( !v8 )
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(&lpString1, *(_QWORD *)(v11 + 24));
              v8 = 1;
              v6 = 1;
            }
          }
          else
          {
            v4 = 0;
          }
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
      if ( v7 && v6 )
        *v16 = 1;
      return v4;
    }
    a2 = lpString2;
  }
  return v4;
}

```

## disassembly

```asm
0x180011ab0  mov     [rsp+arg_10], r8
0x180011ab5  mov     [rsp+lpString2], rdx
0x180011aba  push    rbx
0x180011abb  push    rbp
0x180011abc  push    rsi
0x180011abd  push    rdi
0x180011abe  push    r12
0x180011ac0  push    r13
0x180011ac2  push    r14
0x180011ac4  push    r15
0x180011ac6  sub     rsp, 28h
0x180011aca  mov     rsi, rcx
0x180011acd  xor     edi, edi
0x180011acf  mov     [r8], edi
0x180011ad2  xor     ebx, ebx
0x180011ad4  cmp     ebx, [rsi+18h]
0x180011ad7  jnb     loc_180011C0C
0x180011add  mov     eax, ebx
0x180011adf  shl     rax, 6
0x180011ae3  mov     rcx, [rsi+10h]
0x180011ae7  mov     rcx, [rax+rcx+30h]; lpString1
0x180011aec  call    cs:__imp_lstrcmpW
0x180011af3  nop     dword ptr [rax+rax+00h]
0x180011af8  test    eax, eax
0x180011afa  jz      short loc_180011B05
0x180011afc  inc     ebx
0x180011afe  mov     rdx, [rsp+68h+lpString2]
0x180011b03  jmp     short loc_180011AD4
0x180011b05  xor     r15b, r15b
0x180011b08  mov     r13b, 1
0x180011b0b  lea     rcx, [rsp+68h+lpString1]
0x180011b13  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180011b18  nop
0x180011b19  xor     r12b, r12b
0x180011b1c  xor     ebp, ebp
0x180011b1e  mov     rbx, [rsp+68h+lpString1]
0x180011b26  cmp     ebp, [rsi+18h]
0x180011b29  jnb     loc_180011BEB
0x180011b2f  mov     r14d, ebp
0x180011b32  shl     r14, 6
0x180011b36  add     r14, [rsi+10h]
0x180011b3a  mov     [rsp+68h+arg_0], 0
0x180011b42  mov     rax, [rsi]
0x180011b45  lea     r8, [rsp+68h+arg_0]
0x180011b4a  mov     rdx, r14
0x180011b4d  mov     rcx, rsi
0x180011b50  mov     rax, [rax+28h]
0x180011b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b59  mov     edi, eax
0x180011b5b  test    eax, eax
0x180011b5d  jns     short loc_180011B6C
0x180011b5f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180011b66  jnz     short loc_180011BD0
0x180011b68  test    eax, eax
0x180011b6a  js      short loc_180011BD8
0x180011b6c  cmp     [rsp+68h+arg_0], 0
0x180011b71  jz      short loc_180011BC9
0x180011b73  mov     rcx, [rsi+28h]
0x180011b77  mov     rax, [rcx]
0x180011b7a  xor     r8d, r8d
0x180011b7d  mov     rdx, [r14+18h]
0x180011b81  mov     rax, [rax+28h]
0x180011b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b8a  mov     edi, eax
0x180011b8c  test    eax, eax
0x180011b8e  jns     short loc_180011B94
0x180011b90  xor     edi, edi
0x180011b92  jmp     short loc_180011BC9
0x180011b94  mov     rdx, [rsp+68h+lpString2]; lpString2
0x180011b99  mov     rcx, [r14+30h]; lpString1
0x180011b9d  call    cs:__imp_lstrcmpW
0x180011ba4  nop     dword ptr [rax+rax+00h]
0x180011ba9  test    eax, eax
0x180011bab  jnz     short loc_180011BE3
0x180011bad  test    r12b, r12b
0x180011bb0  jnz     short loc_180011BC9
0x180011bb2  mov     rdx, [r14+18h]
0x180011bb6  lea     rcx, [rsp+68h+lpString1]
0x180011bbe  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180011bc3  mov     r12b, 1
0x180011bc6  mov     r15b, r12b
0x180011bc9  inc     ebp
0x180011bcb  jmp     loc_180011B1E
0x180011bd0  mov     ecx, eax; int
0x180011bd2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180011bd7  nop
0x180011bd8  lea     rcx, [rbx-18h]; this
0x180011bdc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180011be1  jmp     short loc_180011C0C
0x180011be3  test    r12b, r12b
0x180011be6  jnz     short loc_180011C20
0x180011be8  xor     r13b, r13b
0x180011beb  lea     rcx, [rbx-18h]; this
0x180011bef  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180011bf4  test    r13b, r13b
0x180011bf7  jz      short loc_180011C0C
0x180011bf9  test    r15b, r15b
0x180011bfc  jz      short loc_180011C0C
0x180011bfe  mov     rax, [rsp+68h+arg_10]
0x180011c06  mov     dword ptr [rax], 1
0x180011c0c  mov     eax, edi
0x180011c0e  add     rsp, 28h
0x180011c12  pop     r15
0x180011c14  pop     r14
0x180011c16  pop     r13
0x180011c18  pop     r12
0x180011c1a  pop     rdi
0x180011c1b  pop     rsi
0x180011c1c  pop     rbp
0x180011c1d  pop     rbx
0x180011c1e  retn
0x180011c20  mov     rdx, [r14+18h]; lpString2
0x180011c24  mov     rcx, rbx; lpString1
0x180011c27  call    cs:__imp_lstrcmpW
0x180011c2e  nop     dword ptr [rax+rax+00h]
0x180011c33  test    eax, eax
0x180011c35  setnz   r15b
0x180011c39  jmp     short loc_180011BEB
```
