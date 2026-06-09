# StartAddress

- ea: `0x140003a50`
- end: `0x140003b74`
- name: `StartAddress`
- size: `292`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001628`
- `0x1400034a4`
- `0x14000354c`
- `0x140003a50`
- `0x140003f18`
- `0x1400041fc`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140003a6c`
- `KERNEL32!WaitForSingleObject` at `0x140003aaa`
- `KERNEL32!WaitForSingleObject` at `0x140003b23`
- `KERNEL32!WaitForSingleObject` at `0x140003a6c`
- `KERNEL32!WaitForSingleObject` at `0x140003aaa`
- `KERNEL32!WaitForSingleObject` at `0x140003b23`
- `KERNEL32!ReleaseMutex` at `0x140003b13`
- `KERNEL32!ReleaseMutex` at `0x140003b13`

## pseudocode

```c
__int64 __fastcall StartAddress(DWORD *lpThreadParameter)
{
  int v2; // ebx
  __int64 v3; // rax
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+30h] [rbp-18h]

  if ( WaitForSingleObject(hHandle, lpThreadParameter[1]) == 258 )
  {
    v5 = 0;
    v6 = 0;
    v2 = 0;
    while ( 1 )
    {
      dword_1400097C8 = sub_140003F18((__int64 *)&v5, *lpThreadParameter);
      if ( WaitForSingleObject(hMutex, 0) )
        break;
      v3 = *((_QWORD *)&xmmword_1400097D0 + 1);
      if ( *((_QWORD *)&xmmword_1400097D0 + 1) == qword_1400097E0 )
      {
        std::vector<std::vector<FrameDescription>>::_Emplace_reallocate<std::vector<FrameDescription> const &>(
          &xmmword_1400097D0,
          *((_QWORD *)&xmmword_1400097D0 + 1),
          &v5);
      }
      else
      {
        **((_QWORD **)&xmmword_1400097D0 + 1) = 0;
        *(_QWORD *)(v3 + 8) = 0;
        *(_QWORD *)(v3 + 16) = 0;
        std::vector<FrameDescription>::_Construct_n<FrameDescription * const &,FrameDescription * const &>(
          v3,
          (__int64)(*((_QWORD *)&v5 + 1) - v5) >> 4,
          &v5,
          (char *)&v5 + 8);
        *((_QWORD *)&xmmword_1400097D0 + 1) += 24LL;
      }
      ReleaseMutex(hMutex);
      if ( WaitForSingleObject(hHandle, lpThreadParameter[2]) == 258 && ++v2 < 100 )
        continue;
      std::vector<FrameDescription>::_Tidy(&v5);
      return 0;
    }
    if ( (_QWORD)v5 )
      std::_Deallocate<16>(v5, (v6 - v5) & 0xFFFFFFFFFFFFFFF0uLL);
  }
  return 0;
}

```

## disassembly

```asm
0x140003a50  mov     [rsp+arg_0], rbx
0x140003a55  mov     [rsp+arg_8], rsi
0x140003a5a  push    rdi
0x140003a5b  sub     rsp, 40h
0x140003a5f  mov     rdi, rcx
0x140003a62  mov     edx, [rcx+4]; dwMilliseconds
0x140003a65  mov     rcx, cs:hHandle; hHandle
0x140003a6c  call    cs:__imp_WaitForSingleObject
0x140003a72  cmp     eax, 102h
0x140003a77  jnz     loc_140003B62
0x140003a7d  xorps   xmm0, xmm0
0x140003a80  movdqu  [rsp+48h+var_28], xmm0
0x140003a86  xor     esi, esi
0x140003a88  mov     [rsp+48h+var_18], rsi
0x140003a8d  mov     ebx, esi
0x140003a8f  mov     edx, [rdi]
0x140003a91  lea     rcx, [rsp+48h+var_28]
0x140003a96  call    sub_140003F18
0x140003a9b  mov     cs:dword_1400097C8, eax
0x140003aa1  xor     edx, edx; dwMilliseconds
0x140003aa3  mov     rcx, cs:hMutex; hHandle
0x140003aaa  call    cs:__imp_WaitForSingleObject
0x140003ab0  test    eax, eax
0x140003ab2  jnz     loc_140003B47
0x140003ab8  mov     rax, qword ptr cs:xmmword_1400097D0+8
0x140003abf  lea     r8, [rsp+48h+var_28]
0x140003ac4  cmp     rax, cs:qword_1400097E0
0x140003acb  jz      short loc_140003AFD
0x140003acd  mov     [rax], rsi
0x140003ad0  mov     [rax+8], rsi
0x140003ad4  mov     [rax+10h], rsi
0x140003ad8  mov     rdx, qword ptr [rsp+48h+var_28+8]
0x140003add  sub     rdx, qword ptr [rsp+48h+var_28]
0x140003ae2  sar     rdx, 4
0x140003ae6  lea     r9, [rsp+48h+var_28+8]
0x140003aeb  mov     rcx, rax
0x140003aee  call    ??$_Construct_n@AEBQEAUFrameDescription@@AEBQEAU1@@?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@AEAAX_KAEBQEAUFrameDescription@@1@Z; std::vector<FrameDescription>::_Construct_n<FrameDescription * const &,FrameDescription * const &>(unsigned __int64,FrameDescription * const &,FrameDescription * const &)
0x140003af3  add     qword ptr cs:xmmword_1400097D0+8, 18h
0x140003afb  jmp     short loc_140003B0C
0x140003afd  mov     rdx, rax
0x140003b00  lea     rcx, xmmword_1400097D0
0x140003b07  call    ??$_Emplace_reallocate@AEBV?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@?$vector@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@V?$allocator@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@2@@std@@AEAAPEAV?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@1@QEAV21@AEBV21@@Z; std::vector<std::vector<FrameDescription>>::_Emplace_reallocate<std::vector<FrameDescription> const &>(std::vector<FrameDescription> * const,std::vector<FrameDescription> const &)
0x140003b0c  mov     rcx, cs:hMutex; hMutex
0x140003b13  call    cs:__imp_ReleaseMutex
0x140003b19  mov     edx, [rdi+8]; dwMilliseconds
0x140003b1c  mov     rcx, cs:hHandle; hHandle
0x140003b23  call    cs:__imp_WaitForSingleObject
0x140003b29  cmp     eax, 102h
0x140003b2e  jnz     short loc_140003B3B
0x140003b30  inc     ebx
0x140003b32  cmp     ebx, 64h ; 'd'
0x140003b35  jl      loc_140003A8F
0x140003b3b  lea     rcx, [rsp+48h+var_28]
0x140003b40  call    ?_Tidy@?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@AEAAXXZ; std::vector<FrameDescription>::_Tidy(void)
0x140003b45  jmp     short loc_140003B62
0x140003b47  mov     rcx, qword ptr [rsp+48h+var_28]
0x140003b4c  test    rcx, rcx
0x140003b4f  jz      short loc_140003B62
0x140003b51  mov     rdx, [rsp+48h+var_18]
0x140003b56  sub     rdx, rcx
0x140003b59  and     rdx, 0FFFFFFFFFFFFFFF0h
0x140003b5d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140003b62  xor     eax, eax
0x140003b64  mov     rbx, [rsp+48h+arg_0]
0x140003b69  mov     rsi, [rsp+48h+arg_8]
0x140003b6e  add     rsp, 40h
0x140003b72  pop     rdi
0x140003b73  retn
```
