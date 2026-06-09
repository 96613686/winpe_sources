# std::_Insertion_sort_unchecked__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___bool_(__cdecl_)(_WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_const_&__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_const_&)_

- ea: `0x18000869c`
- end: `0x180008935`
- name: `std::_Insertion_sort_unchecked__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___bool_(__cdecl_)(_WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_const_&__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_const_&)_`
- size: `665`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001fa7c`

## callees

- `0x180007f90`
- `0x18000869c`
- `0x1800097f4`
- `0x18001bac4`
- `0x180025308`
- `0x18002a030`
- `0x180041010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Insertion_sort_unchecked__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___bool____cdecl____WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_const____WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_const____(
        __int64 a1,
        __int64 a2,
        unsigned __int8 (__fastcall *a3)(__int16 *, __int64))
{
  __int64 v6; // rsi
  __m128i si128; // xmm6
  unsigned __int64 v8; // rdx
  __int64 v10; // rbx
  __int64 i; // r14
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  __int16 v14; // [rsp+20h] [rbp-60h] BYREF
  __int64 v15; // [rsp+22h] [rbp-5Eh]
  int v16; // [rsp+2Ah] [rbp-56h]
  __int16 v17; // [rsp+2Eh] [rbp-52h]
  __m128i v18; // [rsp+30h] [rbp-50h]
  __int64 v19; // [rsp+40h] [rbp-40h]
  __int128 v20; // [rsp+48h] [rbp-38h]
  char v21; // [rsp+58h] [rbp-28h]
  int v22; // [rsp+5Ch] [rbp-24h]

  if ( a1 != a2 )
  {
    v6 = a1 + 64;
    if ( a1 + 64 != a2 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        std::wstring::wstring((__int64)&v14, v6);
        v19 = *(_QWORD *)(v6 + 32);
        v20 = *(_OWORD *)(v6 + 40);
        v21 = *(_BYTE *)(v6 + 56);
        v22 = *(_DWORD *)(v6 + 60);
        if ( a3(&v14, a1) )
        {
          std::_Move_backward_unchecked__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo____WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___(
            a1,
            v6,
            v6 + 64);
          if ( (__int16 *)a1 != &v14 )
          {
            v8 = *(_QWORD *)(a1 + 24);
            if ( v8 > 7 )
              std::_Deallocate<16>(*(void **)a1, 2 * v8 + 2);
            *(_WORD *)a1 = v14;
            *(_QWORD *)(a1 + 2) = v15;
            *(_DWORD *)(a1 + 10) = v16;
            *(_WORD *)(a1 + 14) = v17;
            *(__m128i *)(a1 + 16) = v18;
            v18 = si128;
            v14 = 0;
          }
          *(_QWORD *)(a1 + 32) = v19;
          *(_OWORD *)(a1 + 40) = v20;
          *(_BYTE *)(a1 + 56) = v21;
          *(_DWORD *)(a1 + 60) = v22;
        }
        else
        {
          v10 = v6;
          for ( i = v6; ; v10 = i )
          {
            i -= 64;
            if ( !a3(&v14, i) )
              break;
            if ( v10 != i )
            {
              v12 = *(_QWORD *)(v10 + 24);
              if ( v12 > 7 )
                std::_Deallocate<16>(*(void **)v10, 2 * v12 + 2);
              *(_QWORD *)(v10 + 16) = 0;
              *(_QWORD *)(v10 + 24) = 7;
              *(_WORD *)v10 = 0;
              *(_OWORD *)v10 = *(_OWORD *)i;
              *(_OWORD *)(v10 + 16) = *(_OWORD *)(i + 16);
              *(_QWORD *)(i + 16) = 0;
              *(_QWORD *)(i + 24) = 7;
              *(_WORD *)i = 0;
            }
            *(_QWORD *)(v10 + 32) = *(_QWORD *)(i + 32);
            *(_OWORD *)(v10 + 40) = *(_OWORD *)(i + 40);
            *(_BYTE *)(v10 + 56) = *(_BYTE *)(i + 56);
            *(_DWORD *)(v10 + 60) = *(_DWORD *)(i + 60);
          }
          if ( (__int16 *)v10 != &v14 )
          {
            v13 = *(_QWORD *)(v10 + 24);
            if ( v13 > 7 )
              std::_Deallocate<16>(*(void **)v10, 2 * v13 + 2);
            *(_WORD *)v10 = v14;
            *(_QWORD *)(v10 + 2) = v15;
            *(_DWORD *)(v10 + 10) = v16;
            *(_WORD *)(v10 + 14) = v17;
            *(__m128i *)(v10 + 16) = v18;
            v18 = si128;
            v14 = 0;
          }
          *(_QWORD *)(v10 + 32) = v19;
          *(_OWORD *)(v10 + 40) = v20;
          *(_BYTE *)(v10 + 56) = v21;
          *(_DWORD *)(v10 + 60) = v22;
        }
        v6 += 64;
        std::wstring::~wstring((__int64)&v14);
      }
      while ( v6 != a2 );
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18000869c  mov     [rsp-28h+arg_8], rbx
0x1800086a1  mov     [rsp-28h+arg_18], rsi
0x1800086a6  push    rbp
0x1800086a7  push    rdi
0x1800086a8  push    r12
0x1800086aa  push    r14
0x1800086ac  push    r15
0x1800086ae  mov     rbp, rsp
0x1800086b1  sub     rsp, 80h
0x1800086b8  movaps  [rsp+80h+var_10], xmm6
0x1800086bd  mov     rax, cs:__security_cookie
0x1800086c4  xor     rax, rsp
0x1800086c7  mov     [rbp+var_20], rax
0x1800086cb  mov     r12, r8
0x1800086ce  mov     r15, rdx
0x1800086d1  mov     rdi, rcx
0x1800086d4  cmp     rcx, rdx
0x1800086d7  jz      loc_1800087C5
0x1800086dd  lea     rsi, [rcx+40h]
0x1800086e1  cmp     rsi, rdx
0x1800086e4  jz      loc_1800087C5
0x1800086ea  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800086f2  mov     rdx, rsi
0x1800086f5  lea     rcx, [rbp+var_60]
0x1800086f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800086fe  mov     rcx, [rsi+20h]
0x180008702  mov     [rbp+var_40], rcx
0x180008706  movups  xmm2, xmmword ptr [rsi+28h]
0x18000870a  movdqu  [rbp+var_38], xmm2
0x18000870f  mov     al, [rsi+38h]
0x180008712  mov     [rbp+var_28], al
0x180008715  mov     eax, [rsi+3Ch]
0x180008718  mov     [rbp+var_24], eax
0x18000871b  mov     rdx, rdi
0x18000871e  lea     rcx, [rbp+var_60]
0x180008722  mov     rax, r12
0x180008725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000872a  test    al, al
0x18000872c  jz      loc_1800087F5
0x180008732  lea     r8, [rsi+40h]
0x180008736  mov     rdx, rsi
0x180008739  mov     rcx, rdi
0x18000873c  call    std___Move_backward_unchecked__WlanSyncTaskCDSToWlan__ComputeNeededChanges____2___ProfileNameFromWlanInfo____WlanSyncTaskCDSToWlan__ComputeNeededChanges____2___ProfileNameFromWlanInfo___
0x180008741  lea     rax, [rbp+var_60]
0x180008745  cmp     rdi, rax
0x180008748  jz      short loc_180008792
0x18000874a  mov     rdx, [rdi+18h]
0x18000874e  cmp     rdx, 7
0x180008752  ja      loc_1800088F5
0x180008758  movzx   eax, [rbp+var_60]
0x18000875c  mov     [rdi], ax
0x18000875f  movsd   xmm0, [rbp+var_5E]
0x180008764  movsd   qword ptr [rdi+2], xmm0
0x180008769  mov     eax, [rbp+var_56]
0x18000876c  mov     [rdi+0Ah], eax
0x18000876f  movzx   eax, [rbp+var_52]
0x180008773  mov     [rdi+0Eh], ax
0x180008777  mov     rax, qword ptr [rbp+var_50]
0x18000877b  mov     [rdi+10h], rax
0x18000877f  mov     rax, qword ptr [rbp+var_50+8]
0x180008783  mov     [rdi+18h], rax
0x180008787  movdqa  [rbp+var_50], xmm6
0x18000878c  xor     eax, eax
0x18000878e  mov     [rbp+var_60], ax
0x180008792  mov     rax, [rbp+var_40]
0x180008796  mov     [rdi+20h], rax
0x18000879a  movups  xmm0, [rbp+var_38]
0x18000879e  movdqu  xmmword ptr [rdi+28h], xmm0
0x1800087a3  mov     al, [rbp+var_28]
0x1800087a6  mov     [rdi+38h], al
0x1800087a9  mov     eax, [rbp+var_24]
0x1800087ac  mov     [rdi+3Ch], eax
0x1800087af  add     rsi, 40h ; '@'
0x1800087b3  lea     rcx, [rbp+var_60]
0x1800087b7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800087bc  cmp     rsi, r15
0x1800087bf  jnz     loc_1800086F2
0x1800087c5  mov     rax, r15
0x1800087c8  mov     rcx, [rbp+var_20]
0x1800087cc  xor     rcx, rsp; StackCookie
0x1800087cf  call    __security_check_cookie
0x1800087d4  lea     r11, [rsp+80h+var_s0]
0x1800087dc  mov     rbx, [r11+38h]
0x1800087e0  mov     rsi, [r11+48h]
0x1800087e4  movaps  xmm6, [rsp+80h+var_10]
0x1800087e9  mov     rsp, r11
0x1800087ec  pop     r15
0x1800087ee  pop     r14
0x1800087f0  pop     r12
0x1800087f2  pop     rdi
0x1800087f3  pop     rbp
0x1800087f4  retn
0x1800087f5  mov     rbx, rsi
0x1800087f8  mov     r14, rsi
0x1800087fb  sub     r14, 40h ; '@'
0x1800087ff  mov     rdx, r14
0x180008802  lea     rcx, [rbp+var_60]
0x180008806  mov     rax, r12
0x180008809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000880e  test    al, al
0x180008810  jz      short loc_180008882
0x180008812  cmp     rbx, r14
0x180008815  jz      short loc_18000885A
0x180008817  mov     rdx, [rbx+18h]
0x18000881b  cmp     rdx, 7
0x18000881f  ja      loc_18000890A
0x180008825  mov     qword ptr [rbx+10h], 0
0x18000882d  mov     qword ptr [rbx+18h], 7
0x180008835  xor     eax, eax
0x180008837  mov     [rbx], ax
0x18000883a  movups  xmm0, xmmword ptr [r14]
0x18000883e  movups  xmmword ptr [rbx], xmm0
0x180008841  movups  xmm1, xmmword ptr [r14+10h]
0x180008846  movups  xmmword ptr [rbx+10h], xmm1
0x18000884a  mov     [r14+10h], rax
0x18000884e  mov     qword ptr [r14+18h], 7
0x180008856  mov     [r14], ax
0x18000885a  mov     rax, [r14+20h]
0x18000885e  mov     [rbx+20h], rax
0x180008862  movups  xmm0, xmmword ptr [r14+28h]
0x180008867  movdqu  xmmword ptr [rbx+28h], xmm0
0x18000886c  mov     al, [r14+38h]
0x180008870  mov     [rbx+38h], al
0x180008873  mov     eax, [r14+3Ch]
0x180008877  mov     [rbx+3Ch], eax
0x18000887a  mov     rbx, r14
0x18000887d  jmp     loc_1800087FB
0x180008882  lea     rax, [rbp+var_60]
0x180008886  cmp     rbx, rax
0x180008889  jz      short loc_1800088D3
0x18000888b  mov     rdx, [rbx+18h]
0x18000888f  cmp     rdx, 7
0x180008893  ja      loc_18000891F
0x180008899  movzx   eax, [rbp+var_60]
0x18000889d  mov     [rbx], ax
0x1800088a0  movsd   xmm0, [rbp+var_5E]
0x1800088a5  movsd   qword ptr [rbx+2], xmm0
0x1800088aa  mov     eax, [rbp+var_56]
0x1800088ad  mov     [rbx+0Ah], eax
0x1800088b0  movzx   eax, [rbp+var_52]
0x1800088b4  mov     [rbx+0Eh], ax
0x1800088b8  mov     rax, qword ptr [rbp+var_50]
0x1800088bc  mov     [rbx+10h], rax
0x1800088c0  mov     rax, qword ptr [rbp+var_50+8]
0x1800088c4  mov     [rbx+18h], rax
0x1800088c8  movdqa  [rbp+var_50], xmm6
0x1800088cd  xor     eax, eax
0x1800088cf  mov     [rbp+var_60], ax
0x1800088d3  mov     rax, [rbp+var_40]
0x1800088d7  mov     [rbx+20h], rax
0x1800088db  movups  xmm0, [rbp+var_38]
0x1800088df  movdqu  xmmword ptr [rbx+28h], xmm0
0x1800088e4  mov     al, [rbp+var_28]
0x1800088e7  mov     [rbx+38h], al
0x1800088ea  mov     eax, [rbp+var_24]
0x1800088ed  mov     [rbx+3Ch], eax
0x1800088f0  jmp     loc_1800087AF
0x1800088f5  lea     rdx, ds:2[rdx*2]
0x1800088fd  mov     rcx, [rdi]
0x180008900  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180008905  jmp     loc_180008758
0x18000890a  lea     rdx, ds:2[rdx*2]
0x180008912  mov     rcx, [rbx]
0x180008915  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000891a  jmp     loc_180008825
0x18000891f  lea     rdx, ds:2[rdx*2]
0x180008927  mov     rcx, [rbx]
0x18000892a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000892f  jmp     loc_180008899
```
