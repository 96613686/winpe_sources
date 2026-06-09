# uus::Utility::GetArchFolderFromMachine(uint)

- ea: `0x1800028b4`
- end: `0x180002973`
- name: `?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002a14`

## callees

- `0x180001418`
- `0x1800028b4`
- `0x18000593c`
- `0x180010f24`

## pseudocode

```c
__int64 __fastcall uus::Utility::GetArchFolderFromMachine(__int64 a1, int a2)
{
  int v3; // edx
  int v4; // edx
  const char *v5; // rdx
  const wchar_t *v6; // rdx
  __int64 v7; // r8
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-28h] BYREF

  v3 = a2 - 332;
  if ( v3 )
  {
    v4 = v3 - 116;
    if ( v4 )
    {
      v5 = (const char *)(unsigned int)(v4 - 33956);
      if ( (_DWORD)v5 )
      {
        if ( (_DWORD)v5 != 9216 )
        {
          std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, v5);
          throw (std::runtime_error *)pExceptionObject;
        }
        v6 = uus::Const::archArm64;
        v7 = -1;
        do
          ++v7;
        while ( uus::Const::archArm64[v7] );
      }
      else
      {
        v6 = uus::Const::archX64;
        v7 = -1;
        do
          ++v7;
        while ( uus::Const::archX64[v7] );
      }
    }
    else
    {
      v6 = uus::Const::archArm;
      v7 = -1;
      do
        ++v7;
      while ( uus::Const::archArm[v7] );
    }
  }
  else
  {
    v6 = uus::Const::archX86;
    v7 = -1;
    do
      ++v7;
    while ( uus::Const::archX86[v7] );
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct<1,wchar_t const *>(a1, v6, v7);
  return a1;
}

```

## disassembly

```asm
0x1800028b4  push    rbx
0x1800028b6  sub     rsp, 50h
0x1800028ba  xor     eax, eax
0x1800028bc  mov     [rsp+58h+var_38], rcx
0x1800028c1  mov     rbx, rcx
0x1800028c4  sub     edx, 14Ch
0x1800028ca  jz      short loc_180002926
0x1800028cc  sub     edx, 74h ; 't'
0x1800028cf  jz      short loc_18000290F
0x1800028d1  sub     edx, 84A4h; char *
0x1800028d7  jz      short loc_1800028F8
0x1800028d9  cmp     edx, 2400h
0x1800028df  jnz     short loc_180002957
0x1800028e1  mov     rdx, cs:?archArm64@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archArm64
0x1800028e8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800028ec  inc     r8
0x1800028ef  cmp     [rdx+r8*2], ax
0x1800028f4  jnz     short loc_1800028EC
0x1800028f6  jmp     short loc_18000293B
0x1800028f8  mov     rdx, cs:?archX64@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archX64
0x1800028ff  or      r8, 0FFFFFFFFFFFFFFFFh
0x180002903  inc     r8
0x180002906  cmp     [rdx+r8*2], ax
0x18000290b  jnz     short loc_180002903
0x18000290d  jmp     short loc_18000293B
0x18000290f  mov     rdx, cs:?archArm@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archArm
0x180002916  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000291a  inc     r8
0x18000291d  cmp     [rdx+r8*2], ax
0x180002922  jnz     short loc_18000291A
0x180002924  jmp     short loc_18000293B
0x180002926  mov     rdx, cs:?archX86@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archX86
0x18000292d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180002931  inc     r8
0x180002934  cmp     [rdx+r8*2], ax
0x180002939  jnz     short loc_180002931
0x18000293b  xorps   xmm0, xmm0
0x18000293e  movups  xmmword ptr [rcx], xmm0
0x180002941  mov     [rcx+10h], rax
0x180002945  mov     [rcx+18h], rax
0x180002949  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000294e  mov     rax, rbx
0x180002951  add     rsp, 50h
0x180002955  pop     rbx
0x180002956  retn
0x180002957  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18000295c  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180002961  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180002968  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000296d  call    _CxxThrowException
```
