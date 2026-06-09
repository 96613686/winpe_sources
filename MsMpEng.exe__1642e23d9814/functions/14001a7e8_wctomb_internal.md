# _wctomb_internal

- ea: `0x14001a7e8`
- end: `0x14001a998`
- name: `_wctomb_internal`
- size: `432`
- prototype: `__int64 __fastcall(int *, _BYTE *, unsigned __int64, unsigned __int16, __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140012d30`
- `0x140013ce0`

## callees

- `0x140014130`
- `0x140015fe4`
- `0x14001a7e8`
- `0x14001dca4`
- `0x140020554`
- `0x14002a310`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001a946`
- `KERNEL32!GetLastError` at `0x14001a946`

## pseudocode

```c
__int64 __fastcall wctomb_internal(
        int *a1,
        _BYTE *a2,
        unsigned __int64 a3,
        unsigned __int16 a4,
        __crt_cached_ptd_host *a5)
{
  unsigned int v5; // ebx
  __crt_cached_ptd_host *v9; // rdi
  unsigned int v10; // esi
  __int64 v11; // rax
  int v12; // ecx
  int v13; // eax
  __int64 result; // rax
  int v15; // eax
  __int64 v16; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int16 v17; // [rsp+78h] [rbp+20h] BYREF

  v17 = a4;
  v5 = 0;
  if ( !a2 && a3 )
  {
    if ( a1 )
      *a1 = 0;
    return 0;
  }
  if ( a1 )
    *a1 = -1;
  v9 = a5;
  if ( a3 > 0x7FFFFFFF )
  {
    v10 = 22;
LABEL_39:
    *((_DWORD *)v9 + 11) = v10;
    *((_BYTE *)v9 + 48) = 1;
    sub_140015FE4(0, 0, 0, 0, 0, v9);
    return v10;
  }
  if ( !*((_BYTE *)a5 + 40) )
  {
    __crt_cached_ptd_host::update_locale_slow(a5);
    a4 = v17;
  }
  v11 = *((_QWORD *)v9 + 3);
  v12 = *(_DWORD *)(v11 + 12);
  if ( v12 != 65001 )
  {
    if ( !*(_QWORD *)(v11 + 312) )
    {
      if ( a4 > 0xFFu )
      {
        if ( a2 && a3 )
          sub_14002A310(a2, 0, a3);
        goto LABEL_23;
      }
      if ( !a2 )
      {
LABEL_27:
        if ( a1 )
          *a1 = 1;
        return 0;
      }
      if ( a3 )
      {
        *a2 = a4;
        goto LABEL_27;
      }
LABEL_38:
      v10 = 34;
      goto LABEL_39;
    }
    LODWORD(v16) = 0;
    v15 = _acrt_WideCharToMultiByte(v12, 0, (unsigned int)&v17, 1, (_DWORD)a2, a3, 0, (__int64)&v16);
    if ( v15 )
    {
      if ( !(_DWORD)v16 )
      {
        if ( a1 )
          *a1 = v15;
        return 0;
      }
    }
    else if ( GetLastError() == 122 )
    {
      if ( a2 && a3 )
        sub_14002A310(a2, 0, a3);
      goto LABEL_38;
    }
LABEL_23:
    result = 42;
    *((_DWORD *)v9 + 11) = 42;
    *((_BYTE *)v9 + 48) = 1;
    return result;
  }
  v16 = 0;
  v13 = sub_140020554(a2, a4, &v16, v9);
  if ( a1 )
    *a1 = v13;
  if ( v13 <= 4 )
    return 0;
  if ( *((_BYTE *)v9 + 48) )
    return *((unsigned int *)v9 + 11);
  return v5;
}

```

## disassembly

```asm
0x14001a7e8  mov     [rsp+arg_0], rbx
0x14001a7ed  mov     [rsp+arg_10], rbp
0x14001a7f2  mov     [rsp+arg_18], r9w
0x14001a7f8  push    rsi
0x14001a7f9  push    rdi
0x14001a7fa  push    r14
0x14001a7fc  sub     rsp, 40h
0x14001a800  xor     ebx, ebx
0x14001a802  mov     rbp, r8
0x14001a805  mov     r14, rdx
0x14001a808  mov     rsi, rcx
0x14001a80b  test    rdx, rdx
0x14001a80e  jnz     short loc_14001A825
0x14001a810  test    r8, r8
0x14001a813  jz      short loc_14001A825
0x14001a815  test    rcx, rcx
0x14001a818  jz      loc_14001A942
0x14001a81e  mov     [rcx], ebx
0x14001a820  jmp     loc_14001A942
0x14001a825  test    rsi, rsi
0x14001a828  jz      short loc_14001A82D
0x14001a82a  or      dword ptr [rcx], 0FFFFFFFFh
0x14001a82d  mov     rdi, [rsp+58h+arg_20]
0x14001a835  cmp     rbp, 7FFFFFFFh
0x14001a83c  jbe     short loc_14001A848
0x14001a83e  mov     esi, 16h
0x14001a843  jmp     loc_14001A971
0x14001a848  cmp     [rdi+28h], bl
0x14001a84b  jnz     short loc_14001A85B
0x14001a84d  mov     rcx, rdi; this
0x14001a850  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x14001a855  movzx   r9d, [rsp+58h+arg_18]
0x14001a85b  mov     rax, [rdi+18h]
0x14001a85f  mov     ecx, [rax+0Ch]
0x14001a862  cmp     ecx, 0FDE9h
0x14001a868  jnz     short loc_14001A89F
0x14001a86a  movzx   edx, r9w
0x14001a86e  lea     r8, [rsp+58h+arg_8]
0x14001a873  mov     r9, rdi
0x14001a876  mov     [rsp+58h+arg_8], rbx
0x14001a87b  mov     rcx, r14
0x14001a87e  call    sub_140020554
0x14001a883  test    rsi, rsi
0x14001a886  jz      short loc_14001A88A
0x14001a888  mov     [rsi], eax
0x14001a88a  cmp     eax, 4
0x14001a88d  jle     loc_14001A942
0x14001a893  cmp     [rdi+30h], bl
0x14001a896  jz      short loc_14001A89B
0x14001a898  mov     ebx, [rdi+2Ch]
0x14001a89b  mov     eax, ebx
0x14001a89d  jmp     short loc_14001A8D6
0x14001a89f  cmp     [rax+138h], rbx
0x14001a8a6  jnz     short loc_14001A903
0x14001a8a8  mov     eax, 0FFh
0x14001a8ad  cmp     r9w, ax
0x14001a8b1  jbe     short loc_14001A8E9
0x14001a8b3  test    r14, r14
0x14001a8b6  jz      short loc_14001A8CA
0x14001a8b8  test    rbp, rbp
0x14001a8bb  jz      short loc_14001A8CA
0x14001a8bd  mov     r8, rbp
0x14001a8c0  xor     edx, edx
0x14001a8c2  mov     rcx, r14
0x14001a8c5  call    sub_14002A310
0x14001a8ca  mov     eax, 2Ah ; '*'
0x14001a8cf  mov     [rdi+2Ch], eax
0x14001a8d2  mov     byte ptr [rdi+30h], 1
0x14001a8d6  mov     rbx, [rsp+58h+arg_0]
0x14001a8db  mov     rbp, [rsp+58h+arg_10]
0x14001a8e0  add     rsp, 40h
0x14001a8e4  pop     r14
0x14001a8e6  pop     rdi
0x14001a8e7  pop     rsi
0x14001a8e8  retn
0x14001a8e9  test    r14, r14
0x14001a8ec  jz      short loc_14001A8F6
0x14001a8ee  test    rbp, rbp
0x14001a8f1  jz      short loc_14001A96C
0x14001a8f3  mov     [r14], r9b
0x14001a8f6  test    rsi, rsi
0x14001a8f9  jz      short loc_14001A942
0x14001a8fb  mov     dword ptr [rsi], 1
0x14001a901  jmp     short loc_14001A942
0x14001a903  lea     rax, [rsp+58h+arg_8]
0x14001a908  mov     dword ptr [rsp+58h+arg_8], ebx
0x14001a90c  mov     [rsp+58h+var_20], rax
0x14001a911  lea     r8, [rsp+58h+arg_18]
0x14001a916  mov     [rsp+58h+var_28], rbx
0x14001a91b  mov     r9d, 1
0x14001a921  mov     dword ptr [rsp+58h+var_30], ebp
0x14001a925  xor     edx, edx
0x14001a927  mov     [rsp+58h+var_38], r14
0x14001a92c  call    __acrt_WideCharToMultiByte
0x14001a931  test    eax, eax
0x14001a933  jz      short loc_14001A946
0x14001a935  cmp     dword ptr [rsp+58h+arg_8], ebx
0x14001a939  jnz     short loc_14001A8CA
0x14001a93b  test    rsi, rsi
0x14001a93e  jz      short loc_14001A942
0x14001a940  mov     [rsi], eax
0x14001a942  xor     eax, eax
0x14001a944  jmp     short loc_14001A8D6
0x14001a946  call    cs:GetLastError
0x14001a94c  cmp     eax, 7Ah ; 'z'
0x14001a94f  jnz     loc_14001A8CA
0x14001a955  test    r14, r14
0x14001a958  jz      short loc_14001A96C
0x14001a95a  test    rbp, rbp
0x14001a95d  jz      short loc_14001A96C
0x14001a95f  mov     r8, rbp
0x14001a962  xor     edx, edx
0x14001a964  mov     rcx, r14
0x14001a967  call    sub_14002A310
0x14001a96c  mov     esi, 22h ; '"'
0x14001a971  mov     [rdi+2Ch], esi
0x14001a974  xor     r9d, r9d; LineNo
0x14001a977  mov     [rsp+58h+var_30], rdi; __crt_cached_ptd_host *
0x14001a97c  xor     r8d, r8d; FileName
0x14001a97f  xor     edx, edx; FunctionName
0x14001a981  mov     byte ptr [rdi+30h], 1
0x14001a985  xor     ecx, ecx; Expression
0x14001a987  mov     [rsp+58h+var_38], rbx; uintptr_t
0x14001a98c  call    sub_140015FE4
0x14001a991  mov     eax, esi
0x14001a993  jmp     loc_14001A8D6
```
