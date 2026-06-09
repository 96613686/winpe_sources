# av_packet_copy_props

- ea: `0x18000edf0`
- end: `0x18000eefa`
- name: `av_packet_copy_props`
- size: `266`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180007d18`
- `0x18000f2f0`
- `0x180011534`

## callees

- `0x18000edf0`
- `0x18000ef30`
- `0x18000f190`
- `0x180022758`
- `0x1800227dc`
- `0x180024640`

## pseudocode

```c
__int64 __fastcall av_packet_copy_props(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  __int64 result; // rax
  int v6; // ebp
  __int64 i; // rsi
  __int64 v8; // rdx
  __int64 v9; // r15
  __int64 v10; // r12
  __int64 v11; // rax

  v2 = a1 + 88;
  *(_QWORD *)(a1 + 8) = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(a2 + 16);
  *(_QWORD *)(a1 + 72) = *(_QWORD *)(a2 + 72);
  *(_QWORD *)(a1 + 64) = *(_QWORD *)(a2 + 64);
  *(_DWORD *)(a1 + 40) = *(_DWORD *)(a2 + 40);
  *(_DWORD *)(a1 + 36) = *(_DWORD *)(a2 + 36);
  *(_QWORD *)(a1 + 80) = *(_QWORD *)(a2 + 80);
  *(_QWORD *)(a1 + 96) = *(_QWORD *)(a2 + 96);
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  result = av_buffer_replace(a1 + 88, *(_QWORD *)(a2 + 88));
  _mm_lfence();
  if ( (int)result >= 0 )
  {
    v6 = 0;
    if ( *(int *)(a2 + 56) <= 0 )
    {
      return 0;
    }
    else
    {
      for ( i = 0; ; i += 24 )
      {
        v8 = *(_QWORD *)(a2 + 48);
        v9 = *(_QWORD *)(v8 + i + 8);
        v10 = *(_QWORD *)(v8 + i);
        v11 = av_packet_new_side_data(a1, *(unsigned int *)(v8 + i + 16), v9);
        if ( !v11 )
          break;
        sub_180024640(v11, v10, v9);
        if ( ++v6 >= *(_DWORD *)(a2 + 56) )
          return 0;
      }
      _mm_lfence();
      av_buffer_unref(v2);
      av_packet_free_side_data(a1);
      return 4294967284LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000edf0  mov     rax, rsp
0x18000edf3  mov     [rax+8], rbx
0x18000edf7  mov     [rax+10h], rbp
0x18000edfb  mov     [rax+18h], rsi
0x18000edff  mov     [rax+20h], rdi
0x18000ee03  push    r12
0x18000ee05  push    r14
0x18000ee07  push    r15
0x18000ee09  sub     rsp, 20h
0x18000ee0d  mov     rax, [rdx+8]
0x18000ee11  lea     r14, [rcx+58h]
0x18000ee15  mov     [rcx+8], rax
0x18000ee19  mov     rbx, rdx
0x18000ee1c  mov     rax, [rdx+10h]
0x18000ee20  mov     rdi, rcx
0x18000ee23  mov     [rcx+10h], rax
0x18000ee27  mov     rax, [rdx+48h]
0x18000ee2b  mov     [rcx+48h], rax
0x18000ee2f  mov     rax, [rdx+40h]
0x18000ee33  mov     [rcx+40h], rax
0x18000ee37  mov     eax, [rdx+28h]
0x18000ee3a  mov     [rcx+28h], eax
0x18000ee3d  mov     eax, [rdx+24h]
0x18000ee40  mov     [rcx+24h], eax
0x18000ee43  mov     rax, [rdx+50h]
0x18000ee47  mov     [rcx+50h], rax
0x18000ee4b  mov     rax, [rdx+60h]
0x18000ee4f  mov     [rcx+60h], rax
0x18000ee53  mov     qword ptr [rcx+30h], 0
0x18000ee5b  mov     dword ptr [rcx+38h], 0
0x18000ee62  mov     rcx, r14
0x18000ee65  mov     qword ptr [r14], 0
0x18000ee6c  mov     rdx, [rdx+58h]
0x18000ee70  call    av_buffer_replace
0x18000ee75  lfence
0x18000ee78  test    eax, eax
0x18000ee7a  js      short loc_18000EEC1
0x18000ee7c  xor     ebp, ebp
0x18000ee7e  cmp     [rbx+38h], ebp
0x18000ee81  jle     short loc_18000EEBF
0x18000ee83  xor     esi, esi
0x18000ee85  mov     rdx, [rbx+30h]
0x18000ee89  mov     rcx, rdi
0x18000ee8c  mov     r15, [rdx+rsi+8]
0x18000ee91  mov     r12, [rdx+rsi]
0x18000ee95  mov     r8, r15
0x18000ee98  mov     edx, [rdx+rsi+10h]
0x18000ee9c  call    av_packet_new_side_data
0x18000eea1  test    rax, rax
0x18000eea4  jz      short loc_18000EEE0
0x18000eea6  mov     r8, r15
0x18000eea9  mov     rdx, r12
0x18000eeac  mov     rcx, rax
0x18000eeaf  call    sub_180024640
0x18000eeb4  inc     ebp
0x18000eeb6  add     rsi, 18h
0x18000eeba  cmp     ebp, [rbx+38h]
0x18000eebd  jl      short loc_18000EE85
0x18000eebf  xor     eax, eax
0x18000eec1  mov     rbx, [rsp+38h+arg_0]
0x18000eec6  mov     rbp, [rsp+38h+arg_8]
0x18000eecb  mov     rsi, [rsp+38h+arg_10]
0x18000eed0  mov     rdi, [rsp+38h+arg_18]
0x18000eed5  add     rsp, 20h
0x18000eed9  pop     r15
0x18000eedb  pop     r14
0x18000eedd  pop     r12
0x18000eedf  retn
0x18000eee0  lfence
0x18000eee3  mov     rcx, r14
0x18000eee6  call    av_buffer_unref
0x18000eeeb  mov     rcx, rdi
0x18000eeee  call    av_packet_free_side_data
0x18000eef3  mov     eax, 0FFFFFFF4h
0x18000eef8  jmp     short loc_18000EEC1
```
