# AppendGuidToPath(AutoScz &)

- ea: `0x14000e1f0`
- end: `0x14000e276`
- name: `?AppendGuidToPath@@YAJAEAVAutoScz@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(struct AutoScz *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000f02c`

## callees

- `0x1400053c0`
- `0x140006514`
- `0x14000e1f0`
- `0x1400177d8`
- `0x140018298`
- `0x140018740`

## pseudocode

```c
__int64 __fastcall AppendGuidToPath(struct AutoScz *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = 0;
  v2 = SczEnsureBackslashTerminated(a1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v2 = SczAllocGuid(&v8);
    v3 = v2;
    if ( v2 >= 0 )
    {
      v2 = SczAllocConcatSz(a1, v8);
      v3 = v2;
      if ( v2 >= 0 )
      {
        v3 = 0;
        goto LABEL_9;
      }
      v4 = 489;
    }
    else
    {
      v4 = 488;
    }
  }
  else
  {
    v4 = 487;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
    (const char *)(unsigned int)v2,
    v6);
LABEL_9:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v8);
  return v3;
}

```

## disassembly

```asm
0x14000e1f0  mov     [rsp+arg_8], rbx
0x14000e1f5  push    rdi; int
0x14000e1f6  sub     rsp, 20h
0x14000e1fa  mov     rdi, rcx
0x14000e1fd  mov     [rsp+28h+arg_0], 0
0x14000e206  call    SczEnsureBackslashTerminated
0x14000e20b  mov     ebx, eax
0x14000e20d  test    eax, eax
0x14000e20f  jns     short loc_14000E218
0x14000e211  mov     edx, 1E7h
0x14000e216  jmp     short loc_14000E22D
0x14000e218  lea     rcx, [rsp+28h+arg_0]
0x14000e21d  call    SczAllocGuid
0x14000e222  mov     ebx, eax
0x14000e224  test    eax, eax
0x14000e226  jns     short loc_14000E243
0x14000e228  mov     edx, 1E8h; void *
0x14000e22d  mov     rcx, [rsp+28h]; this
0x14000e232  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x14000e239  mov     r9d, eax; char *
0x14000e23c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e241  jmp     short loc_14000E25F
0x14000e243  mov     rdx, [rsp+28h+arg_0]
0x14000e248  mov     rcx, rdi
0x14000e24b  call    SczAllocConcatSz
0x14000e250  mov     ebx, eax
0x14000e252  test    eax, eax
0x14000e254  jns     short loc_14000E25D
0x14000e256  mov     edx, 1E9h
0x14000e25b  jmp     short loc_14000E22D
0x14000e25d  xor     ebx, ebx
0x14000e25f  lea     rcx, [rsp+28h+arg_0]
0x14000e264  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000e269  mov     eax, ebx
0x14000e26b  mov     rbx, [rsp+28h+arg_8]
0x14000e270  add     rsp, 20h
0x14000e274  pop     rdi
0x14000e275  retn
```
