# Apx::ApfHelper::GetSymLinkFromCmEventData(_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)

- ea: `0x18000b6e0`
- end: `0x18000b808`
- name: `?GetSymLinkFromCmEventData@ApfHelper@Apx@@SAPEBGW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z`
- size: `296`
- prototype: `__int64 __fastcall(unsigned int, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x180026664`
- `0x180026978`

## callees

- `0x18000a12c`
- `0x18000a1b4`
- `0x18000b6e0`

## pseudocode

```c
__int64 __fastcall Apx::ApfHelper::GetSymLinkFromCmEventData(unsigned int a1, __int64 a2, unsigned int a3)
{
  char *v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rdx

  v6 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids);
    v6 = (char *)WPP_GLOBAL_Control;
  }
  v7 = 0;
  v8 = 24;
  if ( a1 > 1 )
  {
LABEL_13:
    if ( v6 == (char *)&WPP_GLOBAL_Control )
      return v7;
    if ( v6[28] >= 0 || (unsigned __int8)v6[25] < 2u )
      goto LABEL_23;
    goto LABEL_11;
  }
  if ( a3 >= 0x18 )
  {
    if ( a3 - 24 >= 2 )
    {
      v7 = a2 + 24;
      if ( *(_WORD *)(a2 + 24 + 2LL * (((a3 - 24) >> 1) - 1)) )
      {
        if ( v6 != (char *)&WPP_GLOBAL_Control && v6[28] < 0 && (unsigned __int8)v6[25] >= 2u )
        {
          WPP_SF_(*((_QWORD *)v6 + 2), 25, &WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids);
          v6 = (char *)WPP_GLOBAL_Control;
        }
        v7 = 0;
      }
      goto LABEL_23;
    }
    goto LABEL_13;
  }
  if ( v6 == (char *)&WPP_GLOBAL_Control )
    return v7;
  if ( v6[28] < 0 && (unsigned __int8)v6[25] >= 2u )
  {
    v8 = 23;
LABEL_11:
    WPP_SF_d(*((_QWORD *)v6 + 2), v8, &WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids);
    v6 = (char *)WPP_GLOBAL_Control;
  }
LABEL_23:
  if ( v6 != (char *)&WPP_GLOBAL_Control && (v6[28] & 1) != 0 && (unsigned __int8)v6[25] >= 5u )
    WPP_SF_(*((_QWORD *)v6 + 2), 26, &WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids);
  return v7;
}

```

## disassembly

```asm
0x18000b6e0  push    rbx
0x18000b6e2  push    rbp
0x18000b6e3  push    rsi
0x18000b6e4  push    rdi
0x18000b6e5  push    r12
0x18000b6e7  push    r14
0x18000b6e9  push    r15
0x18000b6eb  sub     rsp, 20h
0x18000b6ef  mov     esi, r8d
0x18000b6f2  mov     rbp, rdx
0x18000b6f5  mov     ebx, ecx
0x18000b6f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6fe  lea     r14, WPP_GLOBAL_Control
0x18000b705  lea     r12, WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids
0x18000b70c  cmp     rcx, r14
0x18000b70f  jz      short loc_18000B735
0x18000b711  test    byte ptr [rcx+1Ch], 1
0x18000b715  jz      short loc_18000B735
0x18000b717  cmp     byte ptr [rcx+19h], 5
0x18000b71b  jb      short loc_18000B735
0x18000b71d  mov     rcx, [rcx+10h]
0x18000b721  mov     edx, 16h
0x18000b726  mov     r8, r12
0x18000b729  call    WPP_SF_
0x18000b72e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b735  xor     r15d, r15d
0x18000b738  mov     edi, r15d
0x18000b73b  lea     edx, [r15+18h]
0x18000b73f  test    ebx, ebx
0x18000b741  jz      short loc_18000B748
0x18000b743  cmp     ebx, 1
0x18000b746  jnz     short loc_18000B786
0x18000b748  cmp     esi, edx
0x18000b74a  jnb     short loc_18000B77E
0x18000b74c  cmp     rcx, r14
0x18000b74f  jz      loc_18000B7F6
0x18000b755  test    byte ptr [rcx+1Ch], 80h
0x18000b759  jz      short loc_18000B7D4
0x18000b75b  cmp     byte ptr [rcx+19h], 2
0x18000b75f  jb      short loc_18000B7D4
0x18000b761  mov     edx, 17h
0x18000b766  mov     rcx, [rcx+10h]
0x18000b76a  mov     r9d, esi
0x18000b76d  mov     r8, r12
0x18000b770  call    WPP_SF_d
0x18000b775  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b77c  jmp     short loc_18000B7D4
0x18000b77e  lea     eax, [rsi-18h]
0x18000b781  cmp     eax, 2
0x18000b784  jnb     short loc_18000B799
0x18000b786  cmp     rcx, r14
0x18000b789  jz      short loc_18000B7F6
0x18000b78b  test    byte ptr [rcx+1Ch], 80h
0x18000b78f  jz      short loc_18000B7D4
0x18000b791  cmp     byte ptr [rcx+19h], 2
0x18000b795  jb      short loc_18000B7D4
0x18000b797  jmp     short loc_18000B766
0x18000b799  shr     eax, 1
0x18000b79b  lea     rdi, [rbp+18h]
0x18000b79f  dec     eax
0x18000b7a1  cmp     [rdi+rax*2], r15w
0x18000b7a6  jz      short loc_18000B7D4
0x18000b7a8  cmp     rcx, r14
0x18000b7ab  jz      short loc_18000B7D1
0x18000b7ad  test    byte ptr [rcx+1Ch], 80h
0x18000b7b1  jz      short loc_18000B7D1
0x18000b7b3  cmp     byte ptr [rcx+19h], 2
0x18000b7b7  jb      short loc_18000B7D1
0x18000b7b9  mov     rcx, [rcx+10h]
0x18000b7bd  mov     edx, 19h
0x18000b7c2  mov     r8, r12
0x18000b7c5  call    WPP_SF_
0x18000b7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7d1  mov     rdi, r15
0x18000b7d4  cmp     rcx, r14
0x18000b7d7  jz      short loc_18000B7F6
0x18000b7d9  test    byte ptr [rcx+1Ch], 1
0x18000b7dd  jz      short loc_18000B7F6
0x18000b7df  cmp     byte ptr [rcx+19h], 5
0x18000b7e3  jb      short loc_18000B7F6
0x18000b7e5  mov     rcx, [rcx+10h]
0x18000b7e9  mov     edx, 1Ah
0x18000b7ee  mov     r8, r12
0x18000b7f1  call    WPP_SF_
0x18000b7f6  mov     rax, rdi
0x18000b7f9  add     rsp, 20h
0x18000b7fd  pop     r15
0x18000b7ff  pop     r14
0x18000b801  pop     r12
0x18000b803  pop     rdi
0x18000b804  pop     rsi
0x18000b805  pop     rbp
0x18000b806  pop     rbx
0x18000b807  retn
```
