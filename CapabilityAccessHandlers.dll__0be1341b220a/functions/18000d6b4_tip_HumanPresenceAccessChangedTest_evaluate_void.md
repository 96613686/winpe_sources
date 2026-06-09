# _tip_HumanPresenceAccessChangedTest::evaluate(void)

- ea: `0x18000d6b4`
- end: `0x18000d8aa`
- name: `?evaluate@_tip_HumanPresenceAccessChangedTest@@QEAAXXZ`
- size: `502`
- prototype: `void __fastcall(_tip_HumanPresenceAccessChangedTest *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d610`

## callees

- `0x18000d6b4`
- `0x18000e1f0`

## pseudocode

```c
void __fastcall _tip_HumanPresenceAccessChangedTest::evaluate(_tip_HumanPresenceAccessChangedTest *this)
{
  const char *v1; // rdx
  const char *v3; // rax
  __int64 v4; // r8
  __int64 v5; // rdx
  char v6; // r9
  unsigned __int64 v7; // rcx
  __int64 v8; // r8
  char v9; // r9
  unsigned __int64 v10; // rax
  __int64 v11; // r8
  char v12; // r9
  __int64 v13; // r8
  char v14; // r9
  __int64 v15; // r8
  unsigned __int64 v16; // rax
  const char *v17; // rax
  __int64 v18; // r8
  char v19; // r9
  char v20; // r9
  char v21; // r9
  char v22; // r9

  v1 = (const char *)*((_QWORD *)this + 2);
  if ( !v1 )
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::uninitialized", 0);
    v5 = *(_QWORD *)(v4 + 8);
    if ( *(_BYTE *)(v5 + 152) != v6 )
      return;
    *(_WORD *)(v5 + 154) = 1;
    goto LABEL_4;
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    v10 = *((_QWORD *)this + 4);
    if ( v10 )
    {
      if ( v10 < v7 || v10 < (unsigned __int64)v1 || v7 < (unsigned __int64)v1 )
      {
        v3 = tip2::details::reason_string((tip2::details *)"reason::timestamp_codeflow_error", v1);
        v5 = *(_QWORD *)(v13 + 8);
        if ( *(_BYTE *)(v5 + 152) == v14 )
        {
          *(_BYTE *)(v5 + 152) = 3;
          *(_WORD *)(v5 + 154) = 8;
          goto LABEL_5;
        }
      }
      else
      {
        v15 = *((_QWORD *)this + 1);
        if ( (*(_DWORD *)(v15 + 56) & 0x200) != 0 )
        {
          v16 = v10 - v7;
          if ( v7 - (unsigned __int64)v1 <= 0x7D0 )
          {
            if ( v16 <= 0x7D0 )
            {
              v17 = tip2::details::reason_string((tip2::details *)"reason::success", (const char *)0x7D0);
              if ( *(_BYTE *)(v18 + 152) != v22 )
                return;
              *(_BYTE *)(v18 + 152) = 1;
              *(_WORD *)(v18 + 154) = 6;
            }
            else
            {
              v17 = tip2::details::reason_string(
                      (tip2::details *)"reason::slow_custom_capability_revoke",
                      (const char *)0x7D0);
              if ( *(_BYTE *)(v18 + 152) != v21 )
                return;
              *(_BYTE *)(v18 + 152) = 3;
              *(_WORD *)(v18 + 154) = 5;
            }
          }
          else if ( v16 <= 0x7D0 )
          {
            v17 = tip2::details::reason_string((tip2::details *)"reason::slow_capability_revoke", (const char *)0x7D0);
            if ( *(_BYTE *)(v18 + 152) != v20 )
              return;
            *(_BYTE *)(v18 + 152) = 3;
            *(_WORD *)(v18 + 154) = 4;
          }
          else
          {
            v17 = tip2::details::reason_string((tip2::details *)"reason::slow_all_revokes", (const char *)0x7D0);
            if ( *(_BYTE *)(v18 + 152) != v19 )
              return;
            *(_BYTE *)(v18 + 152) = 3;
            *(_WORD *)(v18 + 154) = 3;
          }
          *(_QWORD *)(v18 + 160) = v17;
        }
        else if ( !*(_BYTE *)(v15 + 152) )
        {
          *(_BYTE *)(v15 + 152) = 3;
          *(_WORD *)(v15 + 154) = 16385;
          *(_QWORD *)(v15 + 160) = 0;
        }
      }
    }
    else
    {
      v3 = tip2::details::reason_string((tip2::details *)"reason::unfinished", v1);
      v5 = *(_QWORD *)(v11 + 8);
      if ( *(_BYTE *)(v5 + 152) == v12 )
      {
        *(_WORD *)(v5 + 154) = 7;
        goto LABEL_4;
      }
    }
  }
  else
  {
    v3 = tip2::details::reason_string((tip2::details *)"reason::unfinished_capability_revoke", v1);
    v5 = *(_QWORD *)(v8 + 8);
    if ( *(_BYTE *)(v5 + 152) == v9 )
    {
      *(_WORD *)(v5 + 154) = 2;
LABEL_4:
      *(_BYTE *)(v5 + 152) = 3;
LABEL_5:
      *(_QWORD *)(v5 + 160) = v3;
    }
  }
}

```

## disassembly

```asm
0x18000d6b4  sub     rsp, 28h
0x18000d6b8  mov     rdx, [rcx+10h]; char *
0x18000d6bc  xor     r9d, r9d
0x18000d6bf  mov     r8, rcx
0x18000d6c2  test    rdx, rdx
0x18000d6c5  jnz     short loc_18000D700
0x18000d6c7  lea     rcx, aReasonUninitia; "reason::uninitialized"
0x18000d6ce  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d6d3  mov     rdx, [r8+8]
0x18000d6d7  cmp     [rdx+98h], r9b
0x18000d6de  jnz     loc_18000D8A5
0x18000d6e4  mov     word ptr [rdx+9Ah], 1
0x18000d6ed  mov     byte ptr [rdx+98h], 3
0x18000d6f4  mov     [rdx+0A0h], rax
0x18000d6fb  jmp     loc_18000D8A5
0x18000d700  mov     rcx, [rcx+18h]
0x18000d704  test    rcx, rcx
0x18000d707  jnz     short loc_18000D731
0x18000d709  lea     rcx, aReasonUnfinish; "reason::unfinished_capability_revoke"
0x18000d710  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d715  mov     rdx, [r8+8]
0x18000d719  cmp     [rdx+98h], r9b
0x18000d720  jnz     loc_18000D8A5
0x18000d726  mov     word ptr [rdx+9Ah], 2
0x18000d72f  jmp     short loc_18000D6ED
0x18000d731  mov     rax, [r8+20h]
0x18000d735  test    rax, rax
0x18000d738  jnz     short loc_18000D762
0x18000d73a  lea     rcx, aReasonUnfinish_0; "reason::unfinished"
0x18000d741  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d746  mov     rdx, [r8+8]
0x18000d74a  cmp     [rdx+98h], r9b
0x18000d751  jnz     loc_18000D8A5
0x18000d757  mov     word ptr [rdx+9Ah], 7
0x18000d760  jmp     short loc_18000D6ED
0x18000d762  cmp     rax, rcx
0x18000d765  jnb     short loc_18000D799
0x18000d767  lea     rcx, aReasonTimestam; "reason::timestamp_codeflow_error"
0x18000d76e  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d773  mov     rdx, [r8+8]
0x18000d777  cmp     [rdx+98h], r9b
0x18000d77e  jnz     loc_18000D8A5
0x18000d784  mov     byte ptr [rdx+98h], 3
0x18000d78b  mov     word ptr [rdx+9Ah], 8
0x18000d794  jmp     loc_18000D6F4
0x18000d799  cmp     rax, rdx
0x18000d79c  jb      short loc_18000D767
0x18000d79e  cmp     rcx, rdx
0x18000d7a1  jb      short loc_18000D767
0x18000d7a3  mov     r8, [r8+8]
0x18000d7a7  test    dword ptr [r8+38h], 200h
0x18000d7af  jnz     short loc_18000D7DC
0x18000d7b1  cmp     [r8+98h], r9b
0x18000d7b8  jnz     loc_18000D8A5
0x18000d7be  mov     byte ptr [r8+98h], 3
0x18000d7c6  mov     word ptr [r8+9Ah], 4001h
0x18000d7d0  mov     [r8+0A0h], r9
0x18000d7d7  jmp     loc_18000D8A5
0x18000d7dc  sub     rax, rcx
0x18000d7df  sub     rcx, rdx
0x18000d7e2  mov     edx, 7D0h; char *
0x18000d7e7  cmp     rcx, rdx
0x18000d7ea  jbe     short loc_18000D849
0x18000d7ec  cmp     rax, rdx
0x18000d7ef  jbe     short loc_18000D820
0x18000d7f1  lea     rcx, aReasonSlowAllR; "reason::slow_all_revokes"
0x18000d7f8  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d7fd  cmp     [r8+98h], r9b
0x18000d804  jnz     loc_18000D8A5
0x18000d80a  mov     ecx, 3
0x18000d80f  mov     [r8+98h], cl
0x18000d816  mov     [r8+9Ah], cx
0x18000d81e  jmp     short loc_18000D89E
0x18000d820  lea     rcx, aReasonSlowCapa; "reason::slow_capability_revoke"
0x18000d827  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d82c  cmp     [r8+98h], r9b
0x18000d833  jnz     short loc_18000D8A5
0x18000d835  mov     byte ptr [r8+98h], 3
0x18000d83d  mov     word ptr [r8+9Ah], 4
0x18000d847  jmp     short loc_18000D89E
0x18000d849  cmp     rax, rdx
0x18000d84c  jbe     short loc_18000D877
0x18000d84e  lea     rcx, aReasonSlowCust; "reason::slow_custom_capability_revoke"
0x18000d855  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d85a  cmp     [r8+98h], r9b
0x18000d861  jnz     short loc_18000D8A5
0x18000d863  mov     byte ptr [r8+98h], 3
0x18000d86b  mov     word ptr [r8+9Ah], 5
0x18000d875  jmp     short loc_18000D89E
0x18000d877  lea     rcx, aReasonSuccess; "reason::success"
0x18000d87e  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d883  cmp     [r8+98h], r9b
0x18000d88a  jnz     short loc_18000D8A5
0x18000d88c  mov     byte ptr [r8+98h], 1
0x18000d894  mov     word ptr [r8+9Ah], 6
0x18000d89e  mov     [r8+0A0h], rax
0x18000d8a5  add     rsp, 28h
0x18000d8a9  retn
```
