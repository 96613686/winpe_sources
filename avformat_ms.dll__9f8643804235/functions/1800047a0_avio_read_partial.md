# avio_read_partial

- ea: `0x1800047a0`
- end: `0x180004861`
- name: `avio_read_partial`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003f80`
- `0x1800047a0`
- `0x180005ac0`
- `0x18001d6e0`
- `0x18001d740`

## pseudocode

```c
__int64 __fastcall avio_read_partial(__int64 a1, __m128i *a2, int a3)
{
  __int64 result; // rax
  __int64 (__fastcall *v7)(_QWORD); // rax
  int v8; // esi

  if ( a3 < 0 )
    return 4294967274LL;
  v7 = *(__int64 (__fastcall **)(_QWORD))(a1 + 48);
  if ( v7 && *(_DWORD *)(a1 + 88) )
  {
    _mm_lfence();
    _mm_lfence();
    result = v7(*(_QWORD *)(a1 + 40));
    if ( (int)result > 0 )
      *(_QWORD *)(a1 + 72) += (int)result;
  }
  else
  {
    _mm_lfence();
    v8 = *(_DWORD *)(a1 + 32) - *(_DWORD *)(a1 + 24);
    if ( !v8 )
    {
      sub_180005AC0(a1);
      v8 = *(_DWORD *)(a1 + 32) - *(_DWORD *)(a1 + 24);
    }
    if ( v8 > a3 )
      v8 = a3;
    sub_18001D740(a2, *(const __m128i **)(a1 + 24), v8);
    *(_QWORD *)(a1 + 24) += v8;
    if ( v8 )
      goto LABEL_15;
    result = *(unsigned int *)(a1 + 84);
    if ( (_DWORD)result )
      return result;
    if ( !(unsigned int)avio_feof(a1) )
    {
LABEL_15:
      _mm_lfence();
      return (unsigned int)v8;
    }
    else
    {
      return 3753488571LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800047a0  mov     [rsp+arg_0], rbx
0x1800047a5  mov     [rsp+arg_8], rbp
0x1800047aa  mov     [rsp+arg_10], rsi
0x1800047af  push    rdi
0x1800047b0  sub     rsp, 20h
0x1800047b4  mov     ebx, r8d
0x1800047b7  mov     rbp, rdx
0x1800047ba  mov     rdi, rcx
0x1800047bd  test    r8d, r8d
0x1800047c0  jns     short loc_1800047CC
0x1800047c2  mov     eax, 0FFFFFFEAh
0x1800047c7  jmp     loc_18000484C
0x1800047cc  mov     rax, [rcx+30h]
0x1800047d0  test    rax, rax
0x1800047d3  jz      short loc_1800047F8
0x1800047d5  cmp     dword ptr [rcx+58h], 0
0x1800047d9  jz      short loc_1800047F8
0x1800047db  lfence
0x1800047de  lfence
0x1800047e1  mov     rcx, [rcx+28h]
0x1800047e5  call    cs:__guard_dispatch_icall_fptr
0x1800047eb  test    eax, eax
0x1800047ed  jle     short loc_18000484C
0x1800047ef  movsxd  rcx, eax
0x1800047f2  add     [rdi+48h], rcx
0x1800047f6  jmp     short loc_18000484C
0x1800047f8  lfence
0x1800047fb  mov     esi, [rcx+20h]
0x1800047fe  sub     esi, [rcx+18h]
0x180004801  jnz     short loc_18000480E
0x180004803  call    sub_180005AC0
0x180004808  mov     esi, [rdi+20h]
0x18000480b  sub     esi, [rdi+18h]
0x18000480e  mov     rdx, [rdi+18h]
0x180004812  cmp     esi, ebx
0x180004814  mov     rcx, rbp
0x180004817  cmovg   esi, ebx
0x18000481a  movsxd  rbx, esi
0x18000481d  mov     r8, rbx
0x180004820  call    sub_18001D740
0x180004825  add     [rdi+18h], rbx
0x180004829  test    esi, esi
0x18000482b  jnz     short loc_180004847
0x18000482d  mov     eax, [rdi+54h]
0x180004830  test    eax, eax
0x180004832  jnz     short loc_18000484C
0x180004834  mov     rcx, rdi
0x180004837  call    avio_feof
0x18000483c  test    eax, eax
0x18000483e  jz      short loc_180004847
0x180004840  mov     eax, 0DFB9B0BBh
0x180004845  jmp     short loc_18000484C
0x180004847  lfence
0x18000484a  mov     eax, esi
0x18000484c  mov     rbx, [rsp+28h+arg_0]
0x180004851  mov     rbp, [rsp+28h+arg_8]
0x180004856  mov     rsi, [rsp+28h+arg_10]
0x18000485b  add     rsp, 20h
0x18000485f  pop     rdi
0x180004860  retn
```
