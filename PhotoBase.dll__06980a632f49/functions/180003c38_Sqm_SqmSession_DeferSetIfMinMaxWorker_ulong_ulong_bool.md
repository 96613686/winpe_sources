# Sqm::SqmSession::DeferSetIfMinMaxWorker(ulong,ulong,bool)

- ea: `0x180003c38`
- end: `0x180003cca`
- name: `?DeferSetIfMinMaxWorker@SqmSession@Sqm@@AEAAXKK_N@Z`
- size: `146`
- prototype: `void __fastcall(Sqm::SqmSession *__hidden this, unsigned int, unsigned int, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180003bd0`
- `0x180003c20`

## callees

- `0x180003c38`
- `0x180003e94`
- `0x1800049c0`
- `0x1800064f0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180003cbb`
- `KERNEL32!LeaveCriticalSection` at `0x180003cbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Sqm::SqmSession::DeferSetIfMinMaxWorker(
        Sqm::SqmSession *this,
        unsigned int a2,
        unsigned int a3,
        char a4)
{
  __int64 v8; // rax
  unsigned int v9; // ecx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-38h] BYREF
  char v11; // [rsp+28h] [rbp-30h]

  if ( *((_BYTE *)this + 145) )
  {
    lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 344);
    v11 = 0;
    ATL::CCritSecLock::Lock(&lpCriticalSection);
    v8 = ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::Find(
           (char *)this + 224,
           a2);
    if ( v8 )
    {
      v9 = *(_DWORD *)(v8 + 4);
      if ( a4 )
      {
        if ( v9 < a3 )
          a3 = *(_DWORD *)(v8 + 4);
      }
      else if ( v9 > a3 )
      {
        a3 = *(_DWORD *)(v8 + 4);
      }
      *(_DWORD *)(v8 + 4) = a3;
    }
    else
    {
      ATL::CRBMap<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::SetAt(
        (char *)this + 224,
        a2,
        a3);
    }
    if ( v11 )
      LeaveCriticalSection(lpCriticalSection);
  }
}

```

## disassembly

```asm
0x180003c38  push    rbx
0x180003c3a  push    rbp
0x180003c3b  push    rsi
0x180003c3c  push    rdi
0x180003c3d  sub     rsp, 38h
0x180003c41  mov     bpl, r9b
0x180003c44  mov     ebx, r8d
0x180003c47  mov     esi, edx
0x180003c49  mov     rdi, rcx
0x180003c4c  cmp     byte ptr [rcx+91h], 0
0x180003c53  jz      short loc_180003CC1
0x180003c55  lea     rax, [rcx+158h]
0x180003c5c  mov     [rsp+58h+lpCriticalSection], rax
0x180003c61  mov     [rsp+58h+var_30], 0
0x180003c66  lea     rcx, [rsp+58h+lpCriticalSection]; this
0x180003c6b  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x180003c70  nop
0x180003c71  mov     edx, esi
0x180003c73  lea     rcx, [rdi+0E0h]
0x180003c7a  call    ?Find@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@IEBAPEAVCNode@12@K@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::Find(ulong)
0x180003c7f  test    rax, rax
0x180003c82  jz      short loc_180003C9D
0x180003c84  mov     ecx, [rax+4]
0x180003c87  test    bpl, bpl
0x180003c8a  jz      short loc_180003C93
0x180003c8c  cmp     ecx, ebx
0x180003c8e  cmovb   ebx, ecx
0x180003c91  jmp     short loc_180003C98
0x180003c93  cmp     ecx, ebx
0x180003c95  cmova   ebx, ecx
0x180003c98  mov     [rax+4], ebx
0x180003c9b  jmp     short loc_180003CAF
0x180003c9d  mov     r8d, ebx
0x180003ca0  mov     edx, esi
0x180003ca2  lea     rcx, [rdi+0E0h]
0x180003ca9  call    ?SetAt@?$CRBMap@KKV?$CElementTraits@K@ATL@@V12@@ATL@@QEAAPEAU__POSITION@@KK@Z; ATL::CRBMap<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::SetAt(ulong,ulong)
0x180003cae  nop
0x180003caf  cmp     [rsp+58h+var_30], 0
0x180003cb4  jz      short loc_180003CC1
0x180003cb6  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180003cbb  call    cs:__imp_LeaveCriticalSection
0x180003cc1  add     rsp, 38h
0x180003cc5  pop     rdi
0x180003cc6  pop     rsi
0x180003cc7  pop     rbp
0x180003cc8  pop     rbx
0x180003cc9  retn
```
