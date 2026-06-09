# WpcPluginNotifyRoutine

- ea: `0x140004250`
- end: `0x140004313`
- name: `WpcPluginNotifyRoutine`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140004250`
- `0x14002023c`
- `0x140020288`
- `0x140022afc`

## pseudocode

```c
__int64 __fastcall WpcPluginNotifyRoutine(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        void *a6,
        int a7,
        __int64 a8,
        int *a9)
{
  int *v9; // rbx
  unsigned int v11; // ebp
  __int64 v12; // rax
  bool v13; // si
  unsigned int i; // edi
  bool v16; // [rsp+58h] [rbp+10h] BYREF

  v9 = a9;
  v11 = a2;
  *a9 = 0;
  v12 = *a1 - 0x4896EF1A58125A50LL;
  if ( *a1 == 0x4896EF1A58125A50LL )
    v12 = a1[1] - 0x6CCAB39AC6D657BALL;
  v13 = v12 == 0;
  for ( i = 0; i < v11; ++i )
  {
    if ( (int)AiEvaluateAppLockerPolicyClass((__int64)a1, a2, a3 + 32LL * i, a6, (__int64)v9) >= 0 && *v9 < 0 )
    {
      if ( !v13 || (unsigned __int8)AiResultIsExplicitDeny(v9) || (v16 = 0, (int)AiIsAppxInbox(a8, &v16) < 0) || !v16 )
      {
        *v9 = -1073740664;
        return 0;
      }
      *v9 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140004250  mov     [rsp+arg_0], rbx
0x140004255  mov     [rsp+arg_10], rbp
0x14000425a  push    rsi
0x14000425b  push    rdi
0x14000425c  push    r14
0x14000425e  sub     rsp, 30h
0x140004262  mov     rbx, [rsp+48h+arg_40]
0x14000426a  mov     r14, r8
0x14000426d  mov     ebp, edx
0x14000426f  mov     dword ptr [rbx], 0
0x140004275  mov     rax, [rcx]
0x140004278  sub     rax, cs:qword_140015558
0x14000427f  jnz     short loc_14000428C
0x140004281  mov     rax, [rcx+8]
0x140004285  sub     rax, cs:qword_140015560
0x14000428c  test    rax, rax
0x14000428f  setz    sil
0x140004293  xor     edi, edi
0x140004295  cmp     edi, ebp
0x140004297  jnb     short loc_1400042FD
0x140004299  mov     r9, [rsp+48h+arg_28]
0x14000429e  mov     r8d, edi
0x1400042a1  shl     r8, 5
0x1400042a5  add     r8, r14
0x1400042a8  mov     [rsp+48h+var_28], rbx
0x1400042ad  call    AiEvaluateAppLockerPolicyClass
0x1400042b2  test    eax, eax
0x1400042b4  js      short loc_1400042F3
0x1400042b6  cmp     dword ptr [rbx], 0
0x1400042b9  jge     short loc_1400042F3
0x1400042bb  test    sil, sil
0x1400042be  jz      short loc_1400042F7
0x1400042c0  mov     rcx, rbx
0x1400042c3  call    AiResultIsExplicitDeny
0x1400042c8  test    al, al
0x1400042ca  jnz     short loc_1400042F7
0x1400042cc  mov     rcx, [rsp+48h+arg_38]
0x1400042d4  lea     rdx, [rsp+48h+arg_8]
0x1400042d9  mov     [rsp+48h+arg_8], al
0x1400042dd  call    AiIsAppxInbox
0x1400042e2  test    eax, eax
0x1400042e4  js      short loc_1400042F7
0x1400042e6  cmp     [rsp+48h+arg_8], 0
0x1400042eb  jz      short loc_1400042F7
0x1400042ed  mov     dword ptr [rbx], 0
0x1400042f3  inc     edi
0x1400042f5  jmp     short loc_140004295
0x1400042f7  mov     dword ptr [rbx], 0C0000488h
0x1400042fd  mov     rbx, [rsp+48h+arg_0]
0x140004302  xor     eax, eax
0x140004304  mov     rbp, [rsp+48h+arg_10]
0x140004309  add     rsp, 30h
0x14000430d  pop     r14
0x14000430f  pop     rdi
0x140004310  pop     rsi
0x140004311  retn
```
