# NetSetupDeleteObject

- ea: `0x180006710`
- end: `0x180006779`
- name: `NetSetupDeleteObject`
- size: `105`
- prototype: `__int64 __fastcall(__int64, int, __int128 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1800015b0`
- `0x1800016d0`
- `0x180006780`

## pseudocode

```c
__int64 __fastcall NetSetupDeleteObject(__int64 a1, int a2, __int128 *a3)
{
  __int128 v6; // xmm0
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+28h] [rbp-20h]
  __int128 v11; // [rsp+30h] [rbp-18h]

  EtwApiBegin(a1, 6);
  v6 = *a3;
  v9 = a2;
  v11 = v6;
  v10 = a1;
  v7 = NetSetupExecuteInFrame__lambda_c5102060ed1d17dae0210a244e38a8e8_(&v9);
  EtwApiEnd(a1, 6, v7);
  return v7;
}

```

## disassembly

```asm
0x180006710  mov     [rsp+arg_8], rbx
0x180006715  mov     [rsp+arg_10], rsi
0x18000671a  push    rdi
0x18000671b  sub     rsp, 40h
0x18000671f  mov     ebx, edx
0x180006721  mov     rdi, r8
0x180006724  mov     edx, 6
0x180006729  mov     rsi, rcx
0x18000672c  call    EtwApiBegin
0x180006731  movups  xmm0, xmmword ptr [rdi]
0x180006734  mov     eax, [rsp+48h+var_24]
0x180006738  lea     rcx, [rsp+48h+var_28]
0x18000673d  mov     [rsp+48h+var_28], ebx
0x180006741  movdqu  [rsp+48h+var_18], xmm0
0x180006747  mov     [rsp+48h+var_24], eax
0x18000674b  mov     [rsp+48h+var_20], rsi
0x180006750  call    NetSetupExecuteInFrame__lambda_c5102060ed1d17dae0210a244e38a8e8___; NetSetupExecuteInFrame__lambda_c5102060ed1d17dae0210a244e38a8e8_
0x180006755  mov     r8d, eax
0x180006758  mov     edx, 6
0x18000675d  mov     rcx, rsi
0x180006760  mov     ebx, eax
0x180006762  call    EtwApiEnd
0x180006767  mov     rsi, [rsp+48h+arg_10]
0x18000676c  mov     eax, ebx
0x18000676e  mov     rbx, [rsp+48h+arg_8]
0x180006773  add     rsp, 40h
0x180006777  pop     rdi
0x180006778  retn
```
