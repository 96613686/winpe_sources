# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::count(_EVENT_DESCRIPTOR const &)

- ea: `0x180018a88`
- end: `0x180018bad`
- name: `?count@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@QEBA_KAEBU_EVENT_DESCRIPTOR@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017b30`

## callees

- `0x180018a88`
- `0x180027444`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::count(
        __int64 a1,
        __int16 *a2)
{
  __int64 *v2; // rbx
  __int64 *v3; // rsi
  __int64 *v4; // rcx
  __int64 *v5; // r8
  unsigned __int16 v6; // r9
  unsigned __int8 v7; // al
  unsigned __int64 v8; // rax
  unsigned __int16 v9; // r8
  unsigned __int8 v10; // al
  __int64 v11; // rdi
  __int64 *v12; // rax
  __int64 *i; // rcx

  v2 = *(__int64 **)(a1 + 8);
  v3 = v2;
  v4 = (__int64 *)v2[1];
  v5 = v4;
  if ( !*((_BYTE *)v4 + 41) )
  {
    v6 = *a2;
    do
    {
      if ( v6 < *((_WORD *)v5 + 12)
        || v6 <= *((_WORD *)v5 + 12)
        && ((v7 = *((_BYTE *)v5 + 26), *((_BYTE *)a2 + 2) < v7)
         || *((_BYTE *)a2 + 2) <= v7
         && ((v8 = v5[3], *(_QWORD *)a2 < v8) || *(_QWORD *)a2 <= v8 && *((_QWORD *)a2 + 1) < (unsigned __int64)v5[4])) )
      {
        v3 = v5;
        v5 = (__int64 *)*v5;
      }
      else
      {
        v5 = (__int64 *)v5[2];
      }
    }
    while ( !*((_BYTE *)v5 + 41) );
    if ( !*((_BYTE *)v4 + 41) )
    {
      v9 = *a2;
      do
      {
        if ( *((_WORD *)v4 + 12) < v9
          || *((_WORD *)v4 + 12) <= v9
          && ((v10 = *((_BYTE *)a2 + 2), *((_BYTE *)v4 + 26) < v10)
           || *((_BYTE *)v4 + 26) <= v10
           && ((unsigned __int64)v4[3] < *(_QWORD *)a2
            || (unsigned __int64)v4[3] <= *(_QWORD *)a2 && (unsigned __int64)v4[4] < *((_QWORD *)a2 + 1))) )
        {
          v4 = (__int64 *)v4[2];
        }
        else
        {
          v2 = v4;
          v4 = (__int64 *)*v4;
        }
      }
      while ( !*((_BYTE *)v4 + 41) );
    }
  }
  v11 = 0;
  while ( v2 != v3 )
  {
    ++v11;
    if ( *((_BYTE *)v2 + 41) )
      invalid_parameter(0, 0, 0, 0, 0);
    v12 = (__int64 *)v2[2];
    if ( *((_BYTE *)v12 + 41) )
    {
      for ( i = (__int64 *)v2[1]; !*((_BYTE *)i + 41) && v2 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v2 = i;
      v2 = i;
    }
    else
    {
      do
      {
        v2 = v12;
        v12 = (__int64 *)*v12;
      }
      while ( !*((_BYTE *)v12 + 41) );
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180018a88  mov     [rsp+arg_0], rbx
0x180018a8d  mov     [rsp+arg_8], rsi
0x180018a92  push    rdi
0x180018a93  sub     rsp, 30h
0x180018a97  mov     rbx, [rcx+8]
0x180018a9b  mov     rsi, rbx
0x180018a9e  mov     rcx, [rbx+8]
0x180018aa2  mov     r8, rcx
0x180018aa5  cmp     byte ptr [rcx+29h], 0
0x180018aa9  jnz     loc_180018B3D
0x180018aaf  movzx   r9d, word ptr [rdx]
0x180018ab3  cmp     r9w, [r8+18h]
0x180018ab8  jb      short loc_180018AE7
0x180018aba  ja      short loc_180018AE1
0x180018abc  mov     al, [r8+1Ah]
0x180018ac0  cmp     [rdx+2], al
0x180018ac3  jb      short loc_180018AE7
0x180018ac5  ja      short loc_180018AE1
0x180018ac7  mov     rax, [r8+18h]
0x180018acb  cmp     [rdx], rax
0x180018ace  jb      short loc_180018AE7
0x180018ad0  ja      short loc_180018AE1
0x180018ad2  mov     rax, [r8+20h]
0x180018ad6  cmp     [rdx+8], rax
0x180018ada  setb    al
0x180018add  test    al, al
0x180018adf  jnz     short loc_180018AE7
0x180018ae1  mov     r8, [r8+10h]
0x180018ae5  jmp     short loc_180018AED
0x180018ae7  mov     rsi, r8
0x180018aea  mov     r8, [r8]
0x180018aed  cmp     byte ptr [r8+29h], 0
0x180018af2  jz      short loc_180018AB3
0x180018af4  cmp     byte ptr [rcx+29h], 0
0x180018af8  jnz     short loc_180018B3D
0x180018afa  movzx   r8d, word ptr [rdx]
0x180018afe  cmp     [rcx+18h], r8w
0x180018b03  jb      short loc_180018B33
0x180018b05  ja      short loc_180018B2B
0x180018b07  mov     al, [rdx+2]
0x180018b0a  cmp     [rcx+1Ah], al
0x180018b0d  jb      short loc_180018B33
0x180018b0f  ja      short loc_180018B2B
0x180018b11  mov     rax, [rdx]
0x180018b14  cmp     [rcx+18h], rax
0x180018b18  jb      short loc_180018B33
0x180018b1a  ja      short loc_180018B2B
0x180018b1c  mov     rax, [rdx+8]
0x180018b20  cmp     [rcx+20h], rax
0x180018b24  setb    al
0x180018b27  test    al, al
0x180018b29  jnz     short loc_180018B33
0x180018b2b  mov     rbx, rcx
0x180018b2e  mov     rcx, [rcx]
0x180018b31  jmp     short loc_180018B37
0x180018b33  mov     rcx, [rcx+10h]
0x180018b37  cmp     byte ptr [rcx+29h], 0
0x180018b3b  jz      short loc_180018AFE
0x180018b3d  xor     edi, edi
0x180018b3f  jmp     short loc_180018B95
0x180018b41  inc     rdi
0x180018b44  cmp     byte ptr [rbx+29h], 0
0x180018b48  jz      short loc_180018B61
0x180018b4a  and     [rsp+38h+var_18], 0
0x180018b50  xor     r9d, r9d; LineNo
0x180018b53  xor     r8d, r8d; FileName
0x180018b56  xor     edx, edx; FunctionName
0x180018b58  xor     ecx, ecx; Expression
0x180018b5a  call    _invalid_parameter
0x180018b5f  jmp     short loc_180018B95
0x180018b61  mov     rax, [rbx+10h]
0x180018b65  cmp     byte ptr [rax+29h], 0
0x180018b69  jnz     short loc_180018B79
0x180018b6b  mov     rbx, rax
0x180018b6e  mov     rax, [rax]
0x180018b71  cmp     byte ptr [rax+29h], 0
0x180018b75  jz      short loc_180018B6B
0x180018b77  jmp     short loc_180018B95
0x180018b79  mov     rcx, [rbx+8]
0x180018b7d  jmp     short loc_180018B8C
0x180018b7f  cmp     rbx, [rcx+10h]
0x180018b83  jnz     short loc_180018B92
0x180018b85  mov     rbx, rcx
0x180018b88  mov     rcx, [rcx+8]
0x180018b8c  cmp     byte ptr [rcx+29h], 0
0x180018b90  jz      short loc_180018B7F
0x180018b92  mov     rbx, rcx
0x180018b95  cmp     rbx, rsi
0x180018b98  jnz     short loc_180018B41
0x180018b9a  mov     rbx, [rsp+38h+arg_0]
0x180018b9f  mov     rax, rdi
0x180018ba2  mov     rsi, [rsp+38h+arg_8]
0x180018ba7  add     rsp, 30h
0x180018bab  pop     rdi
0x180018bac  retn
```
