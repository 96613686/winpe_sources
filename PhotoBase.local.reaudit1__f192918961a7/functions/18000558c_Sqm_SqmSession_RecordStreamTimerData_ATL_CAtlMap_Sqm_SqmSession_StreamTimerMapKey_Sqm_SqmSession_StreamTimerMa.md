# Sqm::SqmSession::RecordStreamTimerData(ATL::CAtlMap<Sqm::SqmSession::StreamTimerMapKey,Sqm::SqmSession::StreamTimerMapValue,Sqm::SqmSession::StreamTimerMapKeyTraits,ATL::CElementTraits<Sqm::SqmSession::StreamTimerMapValue>>::CPair *)

- ea: `0x18000558c`
- end: `0x18000573b`
- name: `?RecordStreamTimerData@SqmSession@Sqm@@AEAAXPEAVCPair@?$CAtlMap@UStreamTimerMapKey@SqmSession@Sqm@@UStreamTimerMapValue@23@VStreamTimerMapKeyTraits@23@V?$CElementTraits@UStreamTimerMapValue@SqmSession@Sqm@@@ATL@@@ATL@@@Z`
- size: `431`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180003cd0`
- `0x180006b20`

## callees

- `0x180002420`
- `0x180002430`
- `0x18000336c`
- `0x1800043dc`
- `0x18000558c`
- `0x180006d68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005700`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005700`
- `KERNEL32!QueryPerformanceCounter` at `0x1800055a1`
- `KERNEL32!QueryPerformanceCounter` at `0x1800055a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Sqm::SqmSession::RecordStreamTimerData(__int64 a1, LARGE_INTEGER *a2)
{
  int v3; // edx
  Base *v4; // rcx
  LARGE_INTEGER v5; // rcx
  LONGLONG v6; // rcx
  double v7; // xmm6_8
  __int64 v8; // rbx
  unsigned __int64 v9; // rsi
  int v10; // edx
  unsigned __int64 v11; // r8
  LARGE_INTEGER v12; // r10
  LARGE_INTEGER v13; // r9
  const wchar_t *v14; // rax
  __int64 v15; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int64 v16; // [rsp+28h] [rbp-50h]
  __int64 v17; // [rsp+30h] [rbp-48h]
  int v18; // [rsp+38h] [rbp-40h]

  if ( !QueryPerformanceCounter(a2 + 3) )
    Base::ThrowLastError(v4);
  v5 = a2[3];
  a2[4].QuadPart += v5.QuadPart - a2[2].QuadPart;
  v6 = v5.QuadPart - a2[2].QuadPart;
  v7 = (double)(int)v6 / (double)(int)a2[1].QuadPart;
  v8 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v9 = a2[6].QuadPart + 2;
  if ( a2[6].QuadPart == -2 )
  {
    v9 = 0;
    v16 = 0;
    v17 = 0;
  }
  else
  {
    if ( !(unsigned __int8)ATL::CAtlArray<_SQM_STREAM_ENTRY,ATL::CElementTraits<_SQM_STREAM_ENTRY>>::GrowBuffer(
                             &v15,
                             v9) )
      ATL::BaseAtlThrow((BasePrivate *)0x8007000ELL, v10);
    ATL::CAtlArray<_SQM_STREAM_ENTRY,ATL::CElementTraits<_SQM_STREAM_ENTRY>>::CallConstructors();
    v16 = v9;
    v8 = v15;
  }
  if ( !v9 || (*(_DWORD *)(v8 + 8) = a2->HighPart, *(_DWORD *)v8 = 1, v9 <= 1) )
LABEL_22:
    ATL::BaseAtlThrow((BasePrivate *)0x80070057LL, v3);
  v11 = 2;
  *(_DWORD *)(v8 + 24) = (int)(v7 * 1000.0 + 0.5);
  *(_DWORD *)(v8 + 16) = 1;
  for ( v12.QuadPart = 0; v12.QuadPart < (unsigned __int64)a2[6].QuadPart; ++v12.QuadPart )
  {
    v3 = 2 * v12.LowPart;
    v13 = a2[5];
    if ( *(_DWORD *)(v13.QuadPart + 16 * v12.QuadPart) == 1 )
    {
      if ( v11 >= v9 )
        goto LABEL_22;
      v6 = 2 * v11;
      *(_DWORD *)(v8 + 8 * v6 + 8) = *(_DWORD *)(v13.QuadPart + 16 * v12.QuadPart + 4);
      *(_DWORD *)(v8 + 8 * v6) = 1;
    }
    else
    {
      if ( *(_DWORD *)(v13.QuadPart + 16 * v12.QuadPart) != 2 )
        ATL::BaseAtlThrow((BasePrivate *)0x80004005LL, v3);
      if ( v11 >= v9 )
        goto LABEL_22;
      v14 = *(const wchar_t **)(v13.QuadPart + 16 * v12.QuadPart + 8);
      v6 = 2 * v11;
      if ( !v14 || !*v14 )
        v14 = L"(null)";
      *(_QWORD *)(v8 + 16 * v11 + 8) = v14;
      *(_DWORD *)(v8 + 16 * v11) = 2;
    }
    ++v11;
  }
  WinSqmAddToStream((struct _GUID *)v6, a2->LowPart, v11, (struct _SQM_STREAM_ENTRY *)v8);
  if ( v8 )
    free((void *)v8);
}

```

## disassembly

```asm
0x18000558c  push    rbx
0x18000558e  push    rbp
0x18000558f  push    rsi
0x180005590  push    rdi
0x180005591  sub     rsp, 58h
0x180005595  movaps  [rsp+78h+var_38], xmm6
0x18000559a  mov     rdi, rdx
0x18000559d  lea     rcx, [rdx+18h]; lpPerformanceCount
0x1800055a1  call    cs:__imp_QueryPerformanceCounter
0x1800055a7  xor     ebp, ebp
0x1800055a9  test    eax, eax
0x1800055ab  jz      loc_18000571F
0x1800055b1  mov     rcx, [rdi+18h]
0x1800055b5  mov     rax, rcx
0x1800055b8  sub     rax, [rdi+10h]
0x1800055bc  add     [rdi+20h], rax
0x1800055c0  sub     rcx, [rdi+10h]
0x1800055c4  xorps   xmm6, xmm6
0x1800055c7  cvtsi2sd xmm6, rcx
0x1800055cc  xorps   xmm0, xmm0
0x1800055cf  cvtsi2sd xmm0, qword ptr [rdi+8]
0x1800055d5  divsd   xmm6, xmm0
0x1800055d9  mov     ebx, ebp
0x1800055db  mov     [rsp+78h+var_58], rbx
0x1800055e0  mov     [rsp+78h+var_50], rbp
0x1800055e5  mov     [rsp+78h+var_48], rbp
0x1800055ea  mov     [rsp+78h+var_40], ebp
0x1800055ee  mov     rsi, [rdi+30h]
0x1800055f2  add     rsi, 2
0x1800055f6  jnz     short loc_180005606
0x1800055f8  mov     esi, ebp
0x1800055fa  mov     [rsp+78h+var_50], rbp
0x1800055ff  mov     [rsp+78h+var_48], rbp
0x180005604  jmp     short loc_18000562A
0x180005606  mov     rdx, rsi
0x180005609  lea     rcx, [rsp+78h+var_58]
0x18000560e  call    ?GrowBuffer@?$CAtlArray@U_SQM_STREAM_ENTRY@@V?$CElementTraits@U_SQM_STREAM_ENTRY@@@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<_SQM_STREAM_ENTRY,ATL::CElementTraits<_SQM_STREAM_ENTRY>>::GrowBuffer(unsigned __int64)
0x180005613  test    al, al
0x180005615  jz      loc_180005725
0x18000561b  call    ?CallConstructors@?$CAtlArray@U_SQM_STREAM_ENTRY@@V?$CElementTraits@U_SQM_STREAM_ENTRY@@@ATL@@@ATL@@CAXPEAU_SQM_STREAM_ENTRY@@_K@Z; ATL::CAtlArray<_SQM_STREAM_ENTRY,ATL::CElementTraits<_SQM_STREAM_ENTRY>>::CallConstructors(_SQM_STREAM_ENTRY *,unsigned __int64)
0x180005620  mov     [rsp+78h+var_50], rsi
0x180005625  mov     rbx, [rsp+78h+var_58]
0x18000562a  test    rsi, rsi
0x18000562d  jz      loc_180005714
0x180005633  mov     eax, [rdi+4]
0x180005636  mov     [rbx+8], eax
0x180005639  mov     r11d, 1
0x18000563f  mov     [rbx], r11d
0x180005642  cmp     rsi, r11
0x180005645  jbe     loc_180005714
0x18000564b  lea     r8d, [r11+1]
0x18000564f  mulsd   xmm6, cs:__real@408f400000000000
0x180005657  addsd   xmm6, cs:__real@3fe0000000000000
0x18000565f  cvttsd2si rax, xmm6
0x180005664  mov     [rbx+18h], eax
0x180005667  mov     [rbx+10h], r11d
0x18000566b  mov     r10, rbp
0x18000566e  cmp     [rdi+30h], rbp
0x180005672  jbe     short loc_1800056ED
0x180005674  cmp     rbp, [rdi+30h]
0x180005678  jnb     loc_180005714
0x18000567e  mov     rdx, r10
0x180005681  add     rdx, rdx
0x180005684  mov     r9, [rdi+28h]
0x180005688  mov     ecx, [r9+rdx*8]
0x18000568c  sub     ecx, r11d
0x18000568f  jz      short loc_1800056C9
0x180005691  cmp     ecx, r11d
0x180005694  jnz     loc_180005730
0x18000569a  cmp     r8, rsi
0x18000569d  jnb     short loc_180005714
0x18000569f  mov     rax, [r9+rdx*8+8]
0x1800056a4  mov     rcx, r8
0x1800056a7  add     rcx, rcx
0x1800056aa  test    rax, rax
0x1800056ad  jz      short loc_1800056B4
0x1800056af  cmp     [rax], bp
0x1800056b2  jnz     short loc_1800056BB
0x1800056b4  lea     rax, aNull; "(null)"
0x1800056bb  mov     [rbx+rcx*8+8], rax
0x1800056c0  mov     dword ptr [rbx+rcx*8], 2
0x1800056c7  jmp     short loc_1800056E1
0x1800056c9  cmp     r8, rsi
0x1800056cc  jnb     short loc_180005714
0x1800056ce  mov     rcx, r8
0x1800056d1  add     rcx, rcx; struct _GUID *
0x1800056d4  mov     eax, [r9+rdx*8+4]
0x1800056d9  mov     [rbx+rcx*8+8], eax
0x1800056dd  mov     [rbx+rcx*8], r11d
0x1800056e1  inc     r8; unsigned int
0x1800056e4  add     r10, r11
0x1800056e7  cmp     r10, [rdi+30h]
0x1800056eb  jb      short loc_18000567E
0x1800056ed  mov     r9, rbx; struct _SQM_STREAM_ENTRY *
0x1800056f0  mov     edx, [rdi]; unsigned int
0x1800056f2  call    ?WinSqmAddToStream@@YAXPEAU_GUID@@KKPEAU_SQM_STREAM_ENTRY@@@Z; WinSqmAddToStream(_GUID *,ulong,ulong,_SQM_STREAM_ENTRY *)
0x1800056f7  nop
0x1800056f8  test    rbx, rbx
0x1800056fb  jz      short loc_180005706
0x1800056fd  mov     rcx, rbx; Block
0x180005700  call    cs:__imp_free
0x180005706  movaps  xmm6, [rsp+78h+var_38]
0x18000570b  add     rsp, 58h
0x18000570f  pop     rdi
0x180005710  pop     rsi
0x180005711  pop     rbp
0x180005712  pop     rbx
0x180005713  retn
0x180005714  mov     ecx, 80070057h; int
0x180005719  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18000571f  call    ?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x180005725  mov     ecx, 8007000Eh; int
0x18000572a  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180005730  mov     ecx, 80004005h; int
0x180005735  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
