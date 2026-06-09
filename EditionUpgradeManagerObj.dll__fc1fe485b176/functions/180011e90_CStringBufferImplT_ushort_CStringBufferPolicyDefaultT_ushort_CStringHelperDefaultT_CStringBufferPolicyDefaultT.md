# CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::AppendFormat(ushort const *,...)

- ea: `0x180011e90`
- end: `0x180011fa4`
- name: `?AppendFormat@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@QEAAJPEBGZZ`
- size: `276`
- prototype: `__int64(__int64, const unsigned __int16 *, ...)`
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800156d0`
- `0x180015864`
- `0x1800161b0`
- `0x180016320`
- `0x180016bcc`
- `0x180016d34`
- `0x1800170b0`

## callees

- `0x1800079fc`
- `0x1800090dc`
- `0x180009480`
- `0x18000b448`
- `0x180011e90`
- `0x1800124e8`

## pseudocode

```c
__int64 CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::AppendFormat(
        __int64 a1,
        const unsigned __int16 *a2,
        ...)
{
  unsigned int *v4; // rsi
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  unsigned int v8; // r14d
  int StringCch; // eax
  va_list va; // [rsp+80h] [rbp+18h] BYREF

  va_start(va, a2);
  v4 = (unsigned int *)(a1 + 8);
  if ( *(_QWORD *)a1 )
    goto LABEL_6;
  *(_DWORD *)(a1 + 12) = 0;
  *v4 = 0;
  v5 = CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::Check2Grow(
         a1,
         1024);
  v6 = v5;
  if ( v5 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v5);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( (v6 & 0x80000000) == 0 )
  {
LABEL_6:
    v8 = 1024;
    while ( 1 )
    {
      StringCch = StringCchVPrintfW(
                    (unsigned __int16 *)(*(_QWORD *)a1 + 2LL * *v4),
                    *(_DWORD *)(a1 + 12) - *v4 + 1,
                    a2,
                    va);
      v6 = StringCch;
      if ( StringCch >= 0 )
        break;
      if ( StringCch != -2147024774 )
        goto LABEL_15;
      *(_WORD *)(*(_QWORD *)a1 + 2LL * *v4) = 0;
      if ( v8 >= 0x8000 )
      {
        StringCch = CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::Check2Grow(
                      a1,
                      1024);
        v6 = StringCch;
        if ( StringCch < 0 )
          goto LABEL_15;
      }
      else
      {
        StringCch = CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::Check2Grow(
                      a1,
                      v8);
        v6 = StringCch;
        if ( StringCch < 0 )
          goto LABEL_15;
        v8 *= 2;
      }
    }
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(*(_WORD **)a1, v4);
    v6 = StringCch;
    if ( StringCch >= 0 )
      goto LABEL_17;
LABEL_15:
    v7 = (unsigned int)StringCch;
  }
  else
  {
    v7 = v6;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
LABEL_17:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( (v6 & 0x80000000) != 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  return v6;
}

```

## disassembly

```asm
0x180011e90  mov     rax, rsp
0x180011e93  mov     [rax+10h], rdx
0x180011e97  mov     [rax+18h], r8
0x180011e9b  mov     [rax+20h], r9
0x180011e9f  push    rbx
0x180011ea0  push    rbp
0x180011ea1  push    rsi
0x180011ea2  push    rdi
0x180011ea3  push    r13
0x180011ea5  push    r14
0x180011ea7  sub     rsp, 38h
0x180011eab  cmp     qword ptr [rcx], 0
0x180011eaf  lea     r13, [rax+18h]
0x180011eb3  mov     rbp, rdx
0x180011eb6  mov     qword ptr [rax-48h], 0
0x180011ebe  mov     rdi, rcx
0x180011ec1  lea     rsi, [rcx+8]
0x180011ec5  jnz     short loc_180011EFA
0x180011ec7  mov     edx, 400h
0x180011ecc  mov     dword ptr [rcx+0Ch], 0
0x180011ed3  mov     dword ptr [rsi], 0
0x180011ed9  call    ?Check2Grow@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@AEAAJKH@Z; CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::Check2Grow(ulong,int)
0x180011ede  mov     ebx, eax
0x180011ee0  test    eax, eax
0x180011ee2  jns     short loc_180011EEB
0x180011ee4  mov     ecx, eax
0x180011ee6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180011eeb  mov     ecx, ebx
0x180011eed  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180011ef2  test    ebx, ebx
0x180011ef4  jns     short loc_180011EFA
0x180011ef6  mov     ecx, ebx
0x180011ef8  jmp     short loc_180011F77
0x180011efa  mov     r14d, 400h
0x180011f00  mov     ecx, [rsi]
0x180011f02  mov     r9, r13; char *
0x180011f05  mov     rax, [rdi]
0x180011f08  mov     r8, rbp; unsigned __int16 *
0x180011f0b  mov     edx, [rdi+0Ch]
0x180011f0e  sub     edx, ecx
0x180011f10  inc     edx; unsigned __int64
0x180011f12  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x180011f16  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x180011f1b  mov     ebx, eax
0x180011f1d  test    eax, eax
0x180011f1f  jns     short loc_180011F64
0x180011f21  cmp     eax, 8007007Ah
0x180011f26  jnz     short loc_180011F75
0x180011f28  mov     ecx, [rsi]
0x180011f2a  xor     eax, eax
0x180011f2c  mov     rdx, [rdi]
0x180011f2f  mov     [rdx+rcx*2], ax
0x180011f33  mov     rcx, rdi
0x180011f36  cmp     r14d, 8000h
0x180011f3d  jnb     short loc_180011F52
0x180011f3f  mov     edx, r14d
0x180011f42  call    ?Check2Grow@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@AEAAJKH@Z; CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::Check2Grow(ulong,int)
0x180011f47  mov     ebx, eax
0x180011f49  test    eax, eax
0x180011f4b  js      short loc_180011F75
0x180011f4d  add     r14d, r14d
0x180011f50  jmp     short loc_180011F00
0x180011f52  mov     edx, 400h
0x180011f57  call    ?Check2Grow@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@AEAAJKH@Z; CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::Check2Grow(ulong,int)
0x180011f5c  mov     ebx, eax
0x180011f5e  test    eax, eax
0x180011f60  jns     short loc_180011F00
0x180011f62  jmp     short loc_180011F75
0x180011f64  mov     rcx, [rdi]
0x180011f67  mov     rdx, rsi
0x180011f6a  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180011f6f  mov     ebx, eax
0x180011f71  test    eax, eax
0x180011f73  jns     short loc_180011F7C
0x180011f75  mov     ecx, eax
0x180011f77  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180011f7c  mov     ecx, ebx
0x180011f7e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180011f83  test    ebx, ebx
0x180011f85  jns     short loc_180011F8E
0x180011f87  mov     ecx, ebx
0x180011f89  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180011f8e  mov     ecx, ebx
0x180011f90  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180011f95  mov     eax, ebx
0x180011f97  add     rsp, 38h
0x180011f9b  pop     r14
0x180011f9d  pop     r13
0x180011f9f  pop     rdi
0x180011fa0  pop     rsi
0x180011fa1  pop     rbp
0x180011fa2  pop     rbx
0x180011fa3  retn
```
