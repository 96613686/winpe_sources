# CRuleReader::SettingChecksumWouldAffectReadPath(ushort const *,int *)

- ea: `0x1800112e0`
- end: `0x180011459`
- name: `?SettingChecksumWouldAffectReadPath@CRuleReader@@UEAAJPEBGPEAH@Z`
- size: `377`
- prototype: `__int64 __fastcall(CRuleReader *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000b518`
- `0x18000bac0`
- `0x18001009c`
- `0x1800112e0`
- `0x1800129d8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001131c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800113c7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001144a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001131c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800113c7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001144a`

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
0x1800112e0  mov     [rsp+arg_10], r8
0x1800112e5  mov     [rsp+lpString2], rdx
0x1800112ea  push    rbx
0x1800112eb  push    rbp
0x1800112ec  push    rsi
0x1800112ed  push    rdi
0x1800112ee  push    r12
0x1800112f0  push    r13
0x1800112f2  push    r14
0x1800112f4  push    r15
0x1800112f6  sub     rsp, 28h
0x1800112fa  mov     rsi, rcx
0x1800112fd  xor     edi, edi
0x1800112ff  mov     [r8], edi
0x180011302  xor     ebx, ebx
0x180011304  cmp     ebx, [rsi+18h]
0x180011307  jnb     loc_180011430
0x18001130d  mov     eax, ebx
0x18001130f  shl     rax, 6
0x180011313  mov     rcx, [rsi+10h]
0x180011317  mov     rcx, [rax+rcx+30h]; lpString1
0x18001131c  call    cs:__imp_lstrcmpW
0x180011322  test    eax, eax
0x180011324  jz      short loc_18001132F
0x180011326  inc     ebx
0x180011328  mov     rdx, [rsp+68h+lpString2]
0x18001132d  jmp     short loc_180011304
0x18001132f  xor     r15b, r15b
0x180011332  mov     r13b, 1
0x180011335  lea     rcx, [rsp+68h+lpString1]
0x18001133d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180011342  nop
0x180011343  xor     r12b, r12b
0x180011346  xor     ebp, ebp
0x180011348  mov     rbx, [rsp+68h+lpString1]
0x180011350  cmp     ebp, [rsi+18h]
0x180011353  jnb     loc_18001140F
0x180011359  mov     r14d, ebp
0x18001135c  shl     r14, 6
0x180011360  add     r14, [rsi+10h]
0x180011364  mov     [rsp+68h+arg_0], 0
0x18001136c  mov     rax, [rsi]
0x18001136f  lea     r8, [rsp+68h+arg_0]
0x180011374  mov     rdx, r14
0x180011377  mov     rcx, rsi
0x18001137a  mov     rax, [rax+28h]
0x18001137e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011383  mov     edi, eax
0x180011385  test    eax, eax
0x180011387  jns     short loc_180011396
0x180011389  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180011390  jnz     short loc_1800113F4
0x180011392  test    eax, eax
0x180011394  js      short loc_1800113FC
0x180011396  cmp     [rsp+68h+arg_0], 0
0x18001139b  jz      short loc_1800113ED
0x18001139d  mov     rcx, [rsi+28h]
0x1800113a1  mov     rax, [rcx]
0x1800113a4  xor     r8d, r8d
0x1800113a7  mov     rdx, [r14+18h]
0x1800113ab  mov     rax, [rax+28h]
0x1800113af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113b4  mov     edi, eax
0x1800113b6  test    eax, eax
0x1800113b8  jns     short loc_1800113BE
0x1800113ba  xor     edi, edi
0x1800113bc  jmp     short loc_1800113ED
0x1800113be  mov     rdx, [rsp+68h+lpString2]; lpString2
0x1800113c3  mov     rcx, [r14+30h]; lpString1
0x1800113c7  call    cs:__imp_lstrcmpW
0x1800113cd  test    eax, eax
0x1800113cf  jnz     short loc_180011407
0x1800113d1  test    r12b, r12b
0x1800113d4  jnz     short loc_1800113ED
0x1800113d6  mov     rdx, [r14+18h]
0x1800113da  lea     rcx, [rsp+68h+lpString1]
0x1800113e2  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800113e7  mov     r12b, 1
0x1800113ea  mov     r15b, r12b
0x1800113ed  inc     ebp
0x1800113ef  jmp     loc_180011348
0x1800113f4  mov     ecx, eax; int
0x1800113f6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800113fb  nop
0x1800113fc  lea     rcx, [rbx-18h]; this
0x180011400  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180011405  jmp     short loc_180011430
0x180011407  test    r12b, r12b
0x18001140a  jnz     short loc_180011443
0x18001140c  xor     r13b, r13b
0x18001140f  lea     rcx, [rbx-18h]; this
0x180011413  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180011418  test    r13b, r13b
0x18001141b  jz      short loc_180011430
0x18001141d  test    r15b, r15b
0x180011420  jz      short loc_180011430
0x180011422  mov     rax, [rsp+68h+arg_10]
0x18001142a  mov     dword ptr [rax], 1
0x180011430  mov     eax, edi
0x180011432  add     rsp, 28h
0x180011436  pop     r15
0x180011438  pop     r14
0x18001143a  pop     r13
0x18001143c  pop     r12
0x18001143e  pop     rdi
0x18001143f  pop     rsi
0x180011440  pop     rbp
0x180011441  pop     rbx
0x180011442  retn
0x180011443  mov     rdx, [r14+18h]; lpString2
0x180011447  mov     rcx, rbx; lpString1
0x18001144a  call    cs:__imp_lstrcmpW
0x180011450  test    eax, eax
0x180011452  setnz   r15b
0x180011456  jmp     short loc_18001140F
```
