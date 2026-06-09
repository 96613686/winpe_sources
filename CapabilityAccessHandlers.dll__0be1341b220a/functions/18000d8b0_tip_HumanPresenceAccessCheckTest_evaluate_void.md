# _tip_HumanPresenceAccessCheckTest::evaluate(void)

- ea: `0x18000d8b0`
- end: `0x18000daa3`
- name: `?evaluate@_tip_HumanPresenceAccessCheckTest@@QEAAXXZ`
- size: `499`
- prototype: `void __fastcall(_tip_HumanPresenceAccessCheckTest *this, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000d630`

## callees

- `0x18000d8b0`
- `0x18000e1f0`

## string_xrefs

- `0x18000d9b0`: `reason::slow_access_force_allowed`
- `0x18000da28`: `reason::slow_access_allowed`

## pseudocode

```c
void __fastcall _tip_HumanPresenceAccessCheckTest::evaluate(_tip_HumanPresenceAccessCheckTest *this, const char *a2)
{
  unsigned __int64 v3; // rcx
  const char *v4; // rax
  __int64 v5; // r8
  __int64 v6; // rdx
  char v7; // r10
  unsigned __int64 v8; // rax
  __int64 v9; // r8
  char v10; // r10
  __int64 v11; // r8
  char v12; // r10
  __int64 v13; // r8
  unsigned __int64 v14; // rax
  const char *v15; // rax
  __int64 v16; // r8
  __int16 v17; // r11
  char v18; // r10
  char v19; // r10
  const char *v20; // rax
  __int16 v21; // r11
  char v22; // r10
  char v23; // r9
  char v24; // r10
  __int16 v25; // r9
  char v26; // r10

  v3 = *((_QWORD *)this + 3);
  if ( !v3 )
  {
    v4 = tip2::details::reason_string((tip2::details *)"reason::uninitialized", a2);
    v6 = *(_QWORD *)(v5 + 8);
    if ( *(_BYTE *)(v6 + 152) != v7 )
      return;
    *(_WORD *)(v6 + 154) = 1;
    goto LABEL_4;
  }
  v8 = *((_QWORD *)this + 4);
  if ( !v8 || (a2 = (const char *)*((unsigned int *)this + 4), !(_DWORD)a2) )
  {
    v4 = tip2::details::reason_string((tip2::details *)"reason::unfinished", a2);
    v6 = *(_QWORD *)(v9 + 8);
    if ( *(_BYTE *)(v6 + 152) == v10 )
    {
      *(_BYTE *)(v6 + 152) = 3;
      *(_WORD *)(v6 + 154) = 6;
      goto LABEL_5;
    }
    return;
  }
  if ( v8 >= v3 )
  {
    v13 = *((_QWORD *)this + 1);
    if ( (*(_DWORD *)(v13 + 56) & 0x200) == 0 )
    {
      if ( *(_BYTE *)(v13 + 152) )
        return;
      *(_WORD *)(v13 + 154) = 16385;
      *(_QWORD *)(v13 + 160) = 0;
      goto LABEL_32;
    }
    v14 = v8 - v3;
    if ( (_DWORD)a2 == 2 )
    {
      if ( v14 <= 0x7D0 )
      {
        v15 = tip2::details::reason_string((tip2::details *)"reason::success_allowed", a2);
        if ( *(_BYTE *)(v16 + 152) != v19 )
          return;
        *(_BYTE *)(v16 + 152) = 1;
        *(_WORD *)(v16 + 154) = 4;
      }
      else
      {
        v15 = tip2::details::reason_string((tip2::details *)"reason::slow_access_force_allowed", a2);
        if ( *(_BYTE *)(v16 + 152) != v18 )
          return;
        *(_BYTE *)(v16 + 152) = v17 + 1;
        *(_WORD *)(v16 + 154) = v17 + 1;
      }
      goto LABEL_20;
    }
    if ( (_DWORD)a2 == 1 )
    {
      if ( v14 <= 0x7D0 )
      {
        v15 = tip2::details::reason_string((tip2::details *)"reason::success_force_allowed", a2);
        if ( *(_BYTE *)(v16 + 152) != v24 )
          return;
        *(_BYTE *)(v16 + 152) = v23;
        *(_WORD *)(v16 + 154) = 5;
LABEL_20:
        *(_QWORD *)(v16 + 160) = v15;
        return;
      }
      v20 = tip2::details::reason_string((tip2::details *)"reason::slow_access_allowed", a2);
      if ( *(_BYTE *)(v13 + 152) != v22 )
        return;
      *(_WORD *)(v13 + 154) = v21;
    }
    else
    {
      v20 = tip2::details::reason_string((tip2::details *)"reason::uninitialized", a2);
      if ( *(_BYTE *)(v13 + 152) != v26 )
        return;
      *(_WORD *)(v13 + 154) = v25;
    }
    *(_QWORD *)(v13 + 160) = v20;
LABEL_32:
    *(_BYTE *)(v13 + 152) = 3;
    return;
  }
  v4 = tip2::details::reason_string((tip2::details *)"reason::timestamp_codeflow_error", a2);
  v6 = *(_QWORD *)(v11 + 8);
  if ( *(_BYTE *)(v6 + 152) == v12 )
  {
    *(_WORD *)(v6 + 154) = 7;
LABEL_4:
    *(_BYTE *)(v6 + 152) = 3;
LABEL_5:
    *(_QWORD *)(v6 + 160) = v4;
  }
}

```

## disassembly

```asm
0x18000d8b0  sub     rsp, 28h
0x18000d8b4  mov     r8, rcx
0x18000d8b7  xor     r10d, r10d
0x18000d8ba  mov     rcx, [rcx+18h]
0x18000d8be  test    rcx, rcx
0x18000d8c1  jnz     short loc_18000D8FC
0x18000d8c3  lea     rcx, aReasonUninitia; "reason::uninitialized"
0x18000d8ca  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d8cf  mov     rdx, [r8+8]; char *
0x18000d8d3  cmp     [rdx+98h], r10b
0x18000d8da  jnz     loc_18000DA9E
0x18000d8e0  mov     word ptr [rdx+9Ah], 1
0x18000d8e9  mov     byte ptr [rdx+98h], 3
0x18000d8f0  mov     [rdx+0A0h], rax
0x18000d8f7  jmp     loc_18000DA9E
0x18000d8fc  mov     rax, [r8+20h]
0x18000d900  test    rax, rax
0x18000d903  jnz     short loc_18000D934
0x18000d905  lea     rcx, aReasonUnfinish_0; "reason::unfinished"
0x18000d90c  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d911  mov     rdx, [r8+8]
0x18000d915  cmp     [rdx+98h], r10b
0x18000d91c  jnz     loc_18000DA9E
0x18000d922  mov     byte ptr [rdx+98h], 3
0x18000d929  mov     word ptr [rdx+9Ah], 6
0x18000d932  jmp     short loc_18000D8F0
0x18000d934  mov     edx, [r8+10h]; char *
0x18000d938  test    edx, edx
0x18000d93a  jz      short loc_18000D905
0x18000d93c  cmp     rax, rcx
0x18000d93f  jnb     short loc_18000D969
0x18000d941  lea     rcx, aReasonTimestam; "reason::timestamp_codeflow_error"
0x18000d948  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d94d  mov     rdx, [r8+8]
0x18000d951  cmp     [rdx+98h], r10b
0x18000d958  jnz     loc_18000DA9E
0x18000d95e  mov     word ptr [rdx+9Ah], 7
0x18000d967  jmp     short loc_18000D8E9
0x18000d969  mov     r8, [r8+8]
0x18000d96d  test    dword ptr [r8+38h], 200h
0x18000d975  jnz     short loc_18000D99A
0x18000d977  cmp     [r8+98h], r10b
0x18000d97e  jnz     loc_18000DA9E
0x18000d984  mov     word ptr [r8+9Ah], 4001h
0x18000d98e  mov     [r8+0A0h], r10
0x18000d995  jmp     loc_18000DA96
0x18000d99a  sub     rax, rcx
0x18000d99d  mov     r11d, 2
0x18000d9a3  cmp     edx, r11d
0x18000d9a6  jnz     short loc_18000DA15
0x18000d9a8  cmp     rax, 7D0h
0x18000d9ae  jbe     short loc_18000D9E8
0x18000d9b0  lea     rcx, aReasonSlowAcce_0; "reason::slow_access_force_allowed"
0x18000d9b7  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d9bc  cmp     [r8+98h], r10b
0x18000d9c3  jnz     loc_18000DA9E
0x18000d9c9  lea     ecx, [r11+1]
0x18000d9cd  mov     [r8+98h], cl
0x18000d9d4  mov     [r8+9Ah], cx
0x18000d9dc  mov     [r8+0A0h], rax
0x18000d9e3  jmp     loc_18000DA9E
0x18000d9e8  lea     rcx, aReasonSuccessA; "reason::success_allowed"
0x18000d9ef  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d9f4  cmp     [r8+98h], r10b
0x18000d9fb  jnz     loc_18000DA9E
0x18000da01  mov     byte ptr [r8+98h], 1
0x18000da09  mov     word ptr [r8+9Ah], 4
0x18000da13  jmp     short loc_18000D9DC
0x18000da15  mov     r9d, 1
0x18000da1b  cmp     edx, r9d
0x18000da1e  jnz     short loc_18000DA72
0x18000da20  cmp     rax, 7D0h
0x18000da26  jbe     short loc_18000DA47
0x18000da28  lea     rcx, aReasonSlowAcce; "reason::slow_access_allowed"
0x18000da2f  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000da34  cmp     [r8+98h], r10b
0x18000da3b  jnz     short loc_18000DA9E
0x18000da3d  mov     [r8+9Ah], r11w
0x18000da45  jmp     short loc_18000DA8F
0x18000da47  lea     rcx, aReasonSuccessF; "reason::success_force_allowed"
0x18000da4e  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000da53  cmp     [r8+98h], r10b
0x18000da5a  jnz     short loc_18000DA9E
0x18000da5c  mov     [r8+98h], r9b
0x18000da63  mov     word ptr [r8+9Ah], 5
0x18000da6d  jmp     loc_18000D9DC
0x18000da72  lea     rcx, aReasonUninitia; "reason::uninitialized"
0x18000da79  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000da7e  cmp     [r8+98h], r10b
0x18000da85  jnz     short loc_18000DA9E
0x18000da87  mov     [r8+9Ah], r9w
0x18000da8f  mov     [r8+0A0h], rax
0x18000da96  mov     byte ptr [r8+98h], 3
0x18000da9e  add     rsp, 28h
0x18000daa2  retn
```
