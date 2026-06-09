# CTouchSelectionHandle::InitICM(void)

- ea: `0x1801fd280`
- end: `0x1801fd34c`
- name: `?InitICM@CTouchSelectionHandle@@UEAAJXZ`
- size: `204`
- prototype: `__int64 __fastcall(CTouchSelectionHandle *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18013bad0`
- `0x1801fd280`

## import_xrefs

- `NInput!CreateInteractionContext` at `0x1801fd2a3`
- `NInput!CreateInteractionContext` at `0x1801fd2a3`
- `NInput!RegisterOutputCallbackInteractionContext` at `0x1801fd2be`
- `NInput!RegisterOutputCallbackInteractionContext` at `0x1801fd2be`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1801fd2f1`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1801fd2f1`
- `NInput!SetPropertyInteractionContext` at `0x1801fd308`
- `NInput!SetPropertyInteractionContext` at `0x1801fd31b`
- `NInput!SetPropertyInteractionContext` at `0x1801fd32e`
- `NInput!SetPropertyInteractionContext` at `0x1801fd308`
- `NInput!SetPropertyInteractionContext` at `0x1801fd31b`
- `NInput!SetPropertyInteractionContext` at `0x1801fd32e`

## pseudocode

```c
__int64 __fastcall CTouchSelectionHandle::InitICM(CTouchSelectionHandle *this)
{
  _QWORD *v1; // rbx
  __int64 result; // rax
  __int64 v4; // rcx
  _OWORD v5[2]; // [rsp+20h] [rbp-38h] BYREF

  v1 = (_QWORD *)((char *)this + 8);
  result = CreateInteractionContext((char *)this + 8);
  if ( (int)result >= 0 )
  {
    result = RegisterOutputCallbackInteractionContext(*v1, CTouchTracker::OutputCallback, this);
    if ( (int)result >= 0 )
    {
      v4 = *v1;
      v5[0] = _mm_load_si128((const __m128i *)&_xmm);
      v5[1] = _mm_load_si128((const __m128i *)&_xmm);
      result = SetInteractionConfigurationInteractionContext(v4, 4, v5);
      if ( (int)result >= 0 )
      {
        result = SetPropertyInteractionContext(*v1, 1, 1);
        if ( (int)result >= 0 )
        {
          result = SetPropertyInteractionContext(*v1, 2, 1);
          if ( (int)result >= 0 )
            return SetPropertyInteractionContext(*v1, 3, 0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1801fd280  mov     [rsp+arg_8], rbx
0x1801fd285  push    rdi
0x1801fd286  sub     rsp, 50h
0x1801fd28a  mov     rax, cs:__security_cookie
0x1801fd291  xor     rax, rsp
0x1801fd294  mov     [rsp+58h+var_18], rax
0x1801fd299  lea     rbx, [rcx+8]
0x1801fd29d  mov     rdi, rcx
0x1801fd2a0  mov     rcx, rbx
0x1801fd2a3  call    cs:__imp_CreateInteractionContext
0x1801fd2a9  test    eax, eax
0x1801fd2ab  js      loc_1801FD334
0x1801fd2b1  mov     rcx, [rbx]
0x1801fd2b4  lea     rdx, ?OutputCallback@CTouchTracker@@KAXPEAXPEBUINTERACTION_CONTEXT_OUTPUT@@@Z; CTouchTracker::OutputCallback(void *,INTERACTION_CONTEXT_OUTPUT const *)
0x1801fd2bb  mov     r8, rdi
0x1801fd2be  call    cs:__imp_RegisterOutputCallbackInteractionContext
0x1801fd2c4  test    eax, eax
0x1801fd2c6  js      short loc_1801FD334
0x1801fd2c8  movdqa  xmm0, cs:__xmm@00000001000000030000000100000002
0x1801fd2d0  lea     r8, [rsp+58h+var_38]
0x1801fd2d5  movdqa  xmm1, cs:__xmm@00000007000000010000000100000004
0x1801fd2dd  mov     edx, 4
0x1801fd2e2  mov     rcx, [rbx]
0x1801fd2e5  movdqu  [rsp+58h+var_38], xmm0
0x1801fd2eb  movdqu  [rsp+58h+var_28], xmm1
0x1801fd2f1  call    cs:__imp_SetInteractionConfigurationInteractionContext
0x1801fd2f7  test    eax, eax
0x1801fd2f9  js      short loc_1801FD334
0x1801fd2fb  mov     rcx, [rbx]
0x1801fd2fe  mov     edi, 1
0x1801fd303  mov     r8d, edi
0x1801fd306  mov     edx, edi
0x1801fd308  call    cs:__imp_SetPropertyInteractionContext
0x1801fd30e  test    eax, eax
0x1801fd310  js      short loc_1801FD334
0x1801fd312  mov     rcx, [rbx]
0x1801fd315  lea     edx, [rdi+1]
0x1801fd318  mov     r8d, edi
0x1801fd31b  call    cs:__imp_SetPropertyInteractionContext
0x1801fd321  test    eax, eax
0x1801fd323  js      short loc_1801FD334
0x1801fd325  mov     rcx, [rbx]
0x1801fd328  lea     edx, [rdi+2]
0x1801fd32b  xor     r8d, r8d
0x1801fd32e  call    cs:__imp_SetPropertyInteractionContext
0x1801fd334  mov     rcx, [rsp+58h+var_18]
0x1801fd339  xor     rcx, rsp; StackCookie
0x1801fd33c  call    __security_check_cookie
0x1801fd341  mov     rbx, [rsp+58h+arg_8]
0x1801fd346  add     rsp, 50h
0x1801fd34a  pop     rdi
0x1801fd34b  retn
```
