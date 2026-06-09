# DeleteTimer

- ea: `0x180003ac0`
- end: `0x180003c7d`
- name: `DeleteTimer`
- size: `445`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003ac0`
- `0x180004b80`
- `0x180008ff0`
- `0x180009130`
- `0x18000b734`
- `0x18000c1c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c45`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180003b29`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180003b29`

## string_xrefs

- `0x180003b4d`: `DeleteTimer`

## pseudocode

```c
__int64 __fastcall DeleteTimer(__int64 a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // edi
  int v4; // eax
  void *v5; // rdx
  void *v6; // rcx
  __int64 v8; // rdx
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF

  v12 = a1;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v3 = 0;
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 )
    {
      WPP_SF_q(v2[2], 29, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, a1);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    v4 = *(_DWORD *)(a1 + 8);
    if ( (v4 & 1) != 0 )
    {
      v5 = *(void **)(a1 + 48);
      v6 = *(void **)a1;
      *(_DWORD *)(a1 + 8) = v4 & 0xFFFFFFFD;
      if ( !DeleteTimerQueueTimer(v6, v5, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, LastError, a1);
      }
      *(_DWORD *)(a1 + 8) &= ~1u;
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_11;
      v8 = 31;
    }
    else
    {
      if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 4) == 0 )
        goto LABEL_11;
      v8 = 32;
    }
    WPP_SF_q(v2[2], v8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, a1);
LABEL_11:
    FreeMemory(&v12, "DeleteTimer", 214);
LABEL_12:
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_13;
  }
  v3 = 87;
  if ( v2 == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)v2 + 28) & 4) != 0 )
  {
    WPP_SF_(v2[2], 28, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
    goto LABEL_12;
  }
LABEL_13:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_L(v2[2], 33, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180003ac0  mov     [rsp+arg_10], rbx
0x180003ac5  mov     [rsp+arg_0], rcx
0x180003aca  push    rsi
0x180003acb  sub     rsp, 30h
0x180003acf  mov     rbx, rcx
0x180003ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ad9  lea     rsi, WPP_GLOBAL_Control
0x180003ae0  cmp     rcx, rsi
0x180003ae3  jz      short loc_180003AEF
0x180003ae5  test    byte ptr [rcx+1Ch], 8
0x180003ae9  jnz     loc_180003BCE
0x180003aef  mov     [rsp+38h+arg_8], rdi
0x180003af4  test    rbx, rbx
0x180003af7  jz      loc_180003BEF
0x180003afd  xor     edi, edi
0x180003aff  cmp     rcx, rsi
0x180003b02  jz      short loc_180003B0E
0x180003b04  test    byte ptr [rcx+1Ch], 2
0x180003b08  jnz     loc_180003C21
0x180003b0e  mov     eax, [rbx+8]
0x180003b11  test    al, 1
0x180003b13  jz      short loc_180003B7C
0x180003b15  mov     rdx, [rbx+30h]; Timer
0x180003b19  and     eax, 0FFFFFFFDh
0x180003b1c  mov     rcx, [rbx]; TimerQueue
0x180003b1f  mov     r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180003b26  mov     [rbx+8], eax
0x180003b29  call    cs:__imp_DeleteTimerQueueTimer
0x180003b2f  test    eax, eax
0x180003b31  jz      loc_180003C45
0x180003b37  and     dword ptr [rbx+8], 0FFFFFFFEh
0x180003b3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b42  cmp     rcx, rsi
0x180003b45  jnz     short loc_180003BC1
0x180003b47  mov     r8d, 0D6h
0x180003b4d  lea     rdx, aDeletetimer_0; "DeleteTimer"
0x180003b54  lea     rcx, [rsp+38h+arg_0]
0x180003b59  call    FreeMemory
0x180003b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b65  cmp     rcx, rsi
0x180003b68  jnz     short loc_180003BA1
0x180003b6a  mov     rbx, [rsp+38h+arg_10]
0x180003b6f  mov     eax, edi
0x180003b71  mov     rdi, [rsp+38h+arg_8]
0x180003b76  add     rsp, 30h
0x180003b7a  pop     rsi
0x180003b7b  retn
0x180003b7c  cmp     rcx, rsi
0x180003b7f  jz      short loc_180003B47
0x180003b81  test    byte ptr [rcx+1Ch], 4
0x180003b85  jz      short loc_180003B47
0x180003b87  mov     edx, 20h ; ' '
0x180003b8c  mov     rcx, [rcx+10h]
0x180003b90  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x180003b97  mov     r9, rbx
0x180003b9a  call    WPP_SF_q
0x180003b9f  jmp     short loc_180003B47
0x180003ba1  test    byte ptr [rcx+1Ch], 8
0x180003ba5  jz      short loc_180003B6A
0x180003ba7  mov     rcx, [rcx+10h]
0x180003bab  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x180003bb2  mov     edx, 21h ; '!'
0x180003bb7  mov     r9d, edi
0x180003bba  call    WPP_SF_L
0x180003bbf  jmp     short loc_180003B6A
0x180003bc1  test    byte ptr [rcx+1Ch], 2
0x180003bc5  jz      short loc_180003B47
0x180003bc7  mov     edx, 1Fh
0x180003bcc  jmp     short loc_180003B8C
0x180003bce  mov     rcx, [rcx+10h]
0x180003bd2  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x180003bd9  mov     edx, 1Bh
0x180003bde  call    WPP_SF_
0x180003be3  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bea  jmp     loc_180003AEF
0x180003bef  mov     edi, 57h ; 'W'
0x180003bf4  cmp     rcx, rsi
0x180003bf7  jz      loc_180003B6A
0x180003bfd  test    byte ptr [rcx+1Ch], 4
0x180003c01  jz      loc_180003B65
0x180003c07  mov     rcx, [rcx+10h]
0x180003c0b  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x180003c12  mov     edx, 1Ch
0x180003c17  call    WPP_SF_
0x180003c1c  jmp     loc_180003B5E
0x180003c21  mov     rcx, [rcx+10h]
0x180003c25  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x180003c2c  mov     edx, 1Dh
0x180003c31  mov     r9, rbx
0x180003c34  call    WPP_SF_q
0x180003c39  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c40  jmp     loc_180003B0E
0x180003c45  call    cs:__imp_GetLastError
0x180003c4b  mov     edi, eax
0x180003c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c54  cmp     rcx, rsi
0x180003c57  jz      loc_180003B37
0x180003c5d  test    byte ptr [rcx+1Ch], 4
0x180003c61  jz      loc_180003B37
0x180003c67  mov     rcx, [rcx+10h]
0x180003c6b  mov     r9d, eax
0x180003c6e  mov     [rsp+38h+var_18], rbx
0x180003c73  call    WPP_SF_dq
0x180003c78  jmp     loc_180003B37
```
