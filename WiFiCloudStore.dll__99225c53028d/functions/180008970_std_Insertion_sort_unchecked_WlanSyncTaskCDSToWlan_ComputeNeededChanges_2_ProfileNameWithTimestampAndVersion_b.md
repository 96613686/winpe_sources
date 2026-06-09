# std::_Insertion_sort_unchecked__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___bool_(__cdecl_)(_WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_const_&__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_const_&)_

- ea: `0x180008970`
- end: `0x180008bb5`
- name: `std::_Insertion_sort_unchecked__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___bool_(__cdecl_)(_WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_const_&__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_const_&)_`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e290`

## callees

- `0x180008970`
- `0x180008bc0`
- `0x1800097f4`
- `0x180025308`
- `0x180028b1c`
- `0x18002a030`
- `0x180041010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Insertion_sort_unchecked__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___bool____cdecl____WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_const____WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_const____(
        __int64 a1,
        __int64 a2,
        unsigned __int8 (__fastcall *a3)(__int16 *, __int64))
{
  __int64 v7; // rbx
  __m128i si128; // xmm6
  __int64 v9; // rdi
  __int64 i; // rsi
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  __int64 v13; // rsi
  __int64 v14; // rdi
  __int16 v15; // [rsp+20h] [rbp-78h] BYREF
  __int64 v16; // [rsp+22h] [rbp-76h]
  int v17; // [rsp+2Ah] [rbp-6Eh]
  __int16 v18; // [rsp+2Eh] [rbp-6Ah]
  __m128i v19; // [rsp+30h] [rbp-68h]
  __int64 v20; // [rsp+40h] [rbp-58h]
  __int64 v21; // [rsp+48h] [rbp-50h]
  char v22; // [rsp+50h] [rbp-48h]
  int v23; // [rsp+54h] [rbp-44h]

  if ( a1 != a2 )
  {
    v7 = a1 + 56;
    if ( a1 + 56 != a2 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        std::wstring::wstring((__int64)&v15, v7);
        v20 = *(_QWORD *)(v7 + 32);
        v21 = *(_QWORD *)(v7 + 40);
        v22 = *(_BYTE *)(v7 + 48);
        v23 = *(_DWORD *)(v7 + 52);
        if ( a3(&v15, a1) )
        {
          v13 = v7 + 56;
          v14 = v7 + 56;
          while ( v7 != a1 )
          {
            v7 -= 56;
            v14 -= 56;
            WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion::operator_(v14, v7);
          }
          WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion::operator_(a1, &v15);
          v7 = v13;
        }
        else
        {
          v9 = v7;
          for ( i = v7; ; v9 = i )
          {
            i -= 56;
            if ( !a3(&v15, i) )
              break;
            if ( v9 != i )
            {
              v11 = *(_QWORD *)(v9 + 24);
              if ( v11 > 7 )
                std::_Deallocate<16>(*(void **)v9, 2 * v11 + 2);
              *(_QWORD *)(v9 + 16) = 0;
              *(_QWORD *)(v9 + 24) = 7;
              *(_WORD *)v9 = 0;
              *(_OWORD *)v9 = *(_OWORD *)i;
              *(_OWORD *)(v9 + 16) = *(_OWORD *)(i + 16);
              *(_QWORD *)(i + 16) = 0;
              *(_QWORD *)(i + 24) = 7;
              *(_WORD *)i = 0;
            }
            *(_QWORD *)(v9 + 32) = *(_QWORD *)(i + 32);
            *(_QWORD *)(v9 + 40) = *(_QWORD *)(i + 40);
            *(_BYTE *)(v9 + 48) = *(_BYTE *)(i + 48);
            *(_DWORD *)(v9 + 52) = *(_DWORD *)(i + 52);
          }
          if ( (__int16 *)v9 != &v15 )
          {
            v12 = *(_QWORD *)(v9 + 24);
            if ( v12 > 7 )
              std::_Deallocate<16>(*(void **)v9, 2 * v12 + 2);
            *(_WORD *)v9 = v15;
            *(_QWORD *)(v9 + 2) = v16;
            *(_DWORD *)(v9 + 10) = v17;
            *(_WORD *)(v9 + 14) = v18;
            *(__m128i *)(v9 + 16) = v19;
            v19 = si128;
            v15 = 0;
          }
          *(_QWORD *)(v9 + 32) = v20;
          *(_QWORD *)(v9 + 40) = v21;
          *(_BYTE *)(v9 + 48) = v22;
          *(_DWORD *)(v9 + 52) = v23;
          v7 += 56;
        }
        std::wstring::_Tidy_deallocate(&v15);
      }
      while ( v7 != a2 );
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180008970  mov     [rsp+arg_8], rbx
0x180008975  mov     [rsp+arg_18], rbp
0x18000897a  push    rsi
0x18000897b  push    rdi
0x18000897c  push    r12
0x18000897e  push    r14
0x180008980  push    r15
0x180008982  sub     rsp, 70h
0x180008986  movaps  [rsp+98h+var_38], xmm6
0x18000898b  mov     rax, cs:__security_cookie
0x180008992  xor     rax, rsp
0x180008995  mov     [rsp+98h+var_40], rax
0x18000899a  mov     r14, r8
0x18000899d  mov     r15, rdx
0x1800089a0  mov     rbp, rcx
0x1800089a3  cmp     rcx, rdx
0x1800089a6  jnz     short loc_1800089D6
0x1800089a8  mov     rax, r15
0x1800089ab  mov     rcx, [rsp+98h+var_40]
0x1800089b0  xor     rcx, rsp; StackCookie
0x1800089b3  call    __security_check_cookie
0x1800089b8  lea     r11, [rsp+98h+var_28]
0x1800089bd  mov     rbx, [r11+38h]
0x1800089c1  mov     rbp, [r11+48h]
0x1800089c5  movaps  xmm6, [rsp+98h+var_38]
0x1800089ca  mov     rsp, r11
0x1800089cd  pop     r15
0x1800089cf  pop     r14
0x1800089d1  pop     r12
0x1800089d3  pop     rdi
0x1800089d4  pop     rsi
0x1800089d5  retn
0x1800089d6  lea     rbx, [rcx+38h]
0x1800089da  cmp     rbx, r15
0x1800089dd  jz      short loc_1800089A8
0x1800089df  xor     r12d, r12d
0x1800089e2  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800089ea  nop     word ptr [rax+rax+00h]
0x1800089f0  mov     rdx, rbx
0x1800089f3  lea     rcx, [rsp+98h+var_78]
0x1800089f8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800089fd  mov     rcx, [rbx+20h]
0x180008a01  mov     [rsp+98h+var_58], rcx
0x180008a06  mov     rax, [rbx+28h]
0x180008a0a  mov     [rsp+98h+var_50], rax
0x180008a0f  movzx   eax, byte ptr [rbx+30h]
0x180008a13  mov     [rsp+98h+var_48], al
0x180008a17  mov     eax, [rbx+34h]
0x180008a1a  mov     [rsp+98h+var_44], eax
0x180008a1e  mov     rdx, rbp
0x180008a21  lea     rcx, [rsp+98h+var_78]
0x180008a26  mov     rax, r14
0x180008a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a2e  test    al, al
0x180008a30  jnz     loc_180008B51
0x180008a36  mov     rdi, rbx
0x180008a39  mov     rsi, rbx
0x180008a3c  nop     dword ptr [rax+00h]
0x180008a40  sub     rsi, 38h ; '8'
0x180008a44  mov     rdx, rsi
0x180008a47  lea     rcx, [rsp+98h+var_78]
0x180008a4c  mov     rax, r14
0x180008a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a54  test    al, al
0x180008a56  jz      short loc_180008ABB
0x180008a58  cmp     rdi, rsi
0x180008a5b  jz      short loc_180008A99
0x180008a5d  mov     rdx, [rdi+18h]
0x180008a61  cmp     rdx, 7
0x180008a65  ja      loc_180008B8A
0x180008a6b  mov     [rdi+10h], r12
0x180008a6f  mov     qword ptr [rdi+18h], 7
0x180008a77  mov     [rdi], r12w
0x180008a7b  movups  xmm0, xmmword ptr [rsi]
0x180008a7e  movups  xmmword ptr [rdi], xmm0
0x180008a81  movups  xmm1, xmmword ptr [rsi+10h]
0x180008a85  movups  xmmword ptr [rdi+10h], xmm1
0x180008a89  mov     [rsi+10h], r12
0x180008a8d  mov     qword ptr [rsi+18h], 7
0x180008a95  mov     [rsi], r12w
0x180008a99  mov     rax, [rsi+20h]
0x180008a9d  mov     [rdi+20h], rax
0x180008aa1  mov     rax, [rsi+28h]
0x180008aa5  mov     [rdi+28h], rax
0x180008aa9  movzx   eax, byte ptr [rsi+30h]
0x180008aad  mov     [rdi+30h], al
0x180008ab0  mov     eax, [rsi+34h]
0x180008ab3  mov     [rdi+34h], eax
0x180008ab6  mov     rdi, rsi
0x180008ab9  jmp     short loc_180008A40
0x180008abb  lea     rax, [rsp+98h+var_78]
0x180008ac0  cmp     rdi, rax
0x180008ac3  jz      short loc_180008B14
0x180008ac5  mov     rdx, [rdi+18h]
0x180008ac9  cmp     rdx, 7
0x180008acd  ja      loc_180008B9F
0x180008ad3  movzx   eax, [rsp+98h+var_78]
0x180008ad8  mov     [rdi], ax
0x180008adb  movsd   xmm0, [rsp+98h+var_76]
0x180008ae1  movsd   qword ptr [rdi+2], xmm0
0x180008ae6  mov     eax, [rsp+98h+var_6E]
0x180008aea  mov     [rdi+0Ah], eax
0x180008aed  movzx   eax, [rsp+98h+var_6A]
0x180008af2  mov     [rdi+0Eh], ax
0x180008af6  mov     rax, qword ptr [rsp+98h+var_68]
0x180008afb  mov     [rdi+10h], rax
0x180008aff  mov     rax, qword ptr [rsp+98h+var_68+8]
0x180008b04  mov     [rdi+18h], rax
0x180008b08  movdqu  [rsp+98h+var_68], xmm6
0x180008b0e  mov     [rsp+98h+var_78], r12w
0x180008b14  mov     rax, [rsp+98h+var_58]
0x180008b19  mov     [rdi+20h], rax
0x180008b1d  mov     rax, [rsp+98h+var_50]
0x180008b22  mov     [rdi+28h], rax
0x180008b26  movzx   eax, [rsp+98h+var_48]
0x180008b2b  mov     [rdi+30h], al
0x180008b2e  mov     eax, [rsp+98h+var_44]
0x180008b32  mov     [rdi+34h], eax
0x180008b35  add     rbx, 38h ; '8'
0x180008b39  lea     rcx, [rsp+98h+var_78]
0x180008b3e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180008b43  cmp     rbx, r15
0x180008b46  jnz     loc_1800089F0
0x180008b4c  jmp     loc_1800089A8
0x180008b51  lea     rsi, [rbx+38h]
0x180008b55  mov     rdi, rsi
0x180008b58  cmp     rbx, rbp
0x180008b5b  jz      short loc_180008B78
0x180008b5d  nop     dword ptr [rax]
0x180008b60  sub     rbx, 38h ; '8'
0x180008b64  sub     rdi, 38h ; '8'
0x180008b68  mov     rdx, rbx
0x180008b6b  mov     rcx, rdi
0x180008b6e  call    _WlanSyncTaskCDSToWlan__ComputeNeededChanges____2___ProfileNameWithTimestampAndVersion__operator_
0x180008b73  cmp     rbx, rbp
0x180008b76  jnz     short loc_180008B60
0x180008b78  lea     rdx, [rsp+98h+var_78]
0x180008b7d  mov     rcx, rbp
0x180008b80  call    _WlanSyncTaskCDSToWlan__ComputeNeededChanges____2___ProfileNameWithTimestampAndVersion__operator_
0x180008b85  mov     rbx, rsi
0x180008b88  jmp     short loc_180008B39
0x180008b8a  lea     rdx, ds:2[rdx*2]
0x180008b92  mov     rcx, [rdi]
0x180008b95  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180008b9a  jmp     loc_180008A6B
0x180008b9f  lea     rdx, ds:2[rdx*2]
0x180008ba7  mov     rcx, [rdi]
0x180008baa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180008baf  jmp     loc_180008AD3
```
