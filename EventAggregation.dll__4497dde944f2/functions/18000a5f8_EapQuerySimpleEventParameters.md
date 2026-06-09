# EapQuerySimpleEventParameters

- ea: `0x18000a5f8`
- end: `0x18000a9f0`
- name: `EapQuerySimpleEventParameters`
- size: `1016`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180009ff0`
- `0x18000a414`

## callees

- `0x180002e30`
- `0x180003630`
- `0x1800072e0`
- `0x180007b5e`
- `0x1800099f0`
- `0x18000a5f8`
- `0x18000bde9`

## import_xrefs

- `ntdll!RtlGUIDFromString` at `0x18000a6c3`
- `ntdll!RtlGUIDFromString` at `0x18000a6c3`

## pseudocode

```c
__int64 __fastcall EapQuerySimpleEventParameters(HANDLE KeyHandle, __int64 *a2, __int64 a3)
{
  unsigned int v3; // ebx
  _DWORD *v4; // rdi
  unsigned __int16 v5; // r12
  unsigned __int16 v6; // bp
  HANDLE v9; // rax
  ULONG v10; // r13d
  unsigned __int16 v11; // si
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  PVOID v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // rcx
  char *v19; // rcx
  __int64 v20; // rbx
  char *v21; // rax
  unsigned int v22; // ecx
  __int64 v23; // rbx
  char *v24; // rax
  __int64 v25; // rbx
  PVOID v26; // rax
  _DWORD *v27; // rax
  unsigned int v28; // ebp
  __int64 v29; // r15
  __int64 v30; // r14
  void *v31; // rcx
  void *v32; // rcx
  GUID v33; // xmm0
  _DWORD *v36; // [rsp+28h] [rbp-70h]
  struct _UNICODE_STRING GuidString; // [rsp+30h] [rbp-68h] BYREF
  GUID Guid; // [rsp+40h] [rbp-58h] BYREF

  v3 = 0;
  v36 = 0;
  v4 = 0;
  GuidString = 0;
  v5 = 0;
  v6 = 0;
  Guid = 0;
  v9 = KeyHandle;
LABEL_2:
  if ( v6 >= 2u )
  {
LABEL_67:
    v33 = Guid;
    *(_QWORD *)(a3 + 24) = v4;
    *(_WORD *)(a3 + 16) = v5;
    *(GUID *)a3 = v33;
    return v3;
  }
  v10 = 0;
  v11 = 0;
  while ( 1 )
  {
    v12 = EapEnumerateKeyValue(v9, v10);
    v3 = v12;
    if ( v12 == -2147483622 )
    {
      v3 = 0;
LABEL_42:
      if ( !v11 )
        goto LABEL_67;
      if ( !v6 )
      {
        v27 = EaLibAllocate(32LL * v11);
        v36 = v27;
        v4 = v27;
        if ( !v27 )
          return (unsigned int)-1073741801;
        memset_0(v27, 0, 32LL * v11);
        v3 = 0;
        v5 = v11;
      }
      v9 = KeyHandle;
      ++v6;
      goto LABEL_2;
    }
    if ( v12 < 0 )
      goto LABEL_48;
    v13 = *a2;
    v3 = 0;
    v14 = *(unsigned int *)(*a2 + 16);
    if ( (_DWORD)v14 )
    {
      if ( v4 )
      {
        if ( v5 <= v11 )
          goto LABEL_56;
        v15 = EaLibAllocate(v14 + 2);
        v16 = 8LL * v11;
        *(_QWORD *)&v4[v16] = v15;
        if ( !v15 )
        {
LABEL_55:
          v3 = -1073741801;
          goto LABEL_49;
        }
        memset_0(v15, 0, *(unsigned int *)(*a2 + 16) + 2LL);
        memcpy_0(*(void **)&v4[v16], (const void *)(*a2 + 20), *(unsigned int *)(*a2 + 16));
      }
      v17 = *a2;
      switch ( *(_DWORD *)(*a2 + 4) )
      {
        case 1:
          if ( v4 )
          {
            v25 = 8LL * v11;
            v4[v25 + 2] = 2;
            v26 = EaLibAllocate(*(unsigned int *)(*a2 + 12) + 2LL);
            *(_QWORD *)&v4[v25 + 4] = v26;
            if ( !v26 )
              goto LABEL_55;
            memset_0(v26, 0, *(unsigned int *)(*a2 + 12) + 2LL);
            v19 = *(char **)&v4[v25 + 4];
            goto LABEL_38;
          }
          break;
        case 3:
          if ( v4 )
          {
            v23 = 8LL * v11;
            v4[v23 + 2] = 4;
            v24 = (char *)EaLibAllocate(*(unsigned int *)(*a2 + 12));
            *(_QWORD *)&v4[v23 + 6] = v24;
            v19 = v24;
            if ( !v24 )
              goto LABEL_55;
            if ( *(_DWORD *)(*a2 + 12) > 0x1FFFEu )
            {
LABEL_56:
              v3 = -2147483643;
              goto LABEL_49;
            }
            LOWORD(v4[v23 + 4]) = *(_WORD *)(*a2 + 12);
            goto LABEL_38;
          }
          break;
        case 4:
          if ( v4 )
          {
            if ( *(_DWORD *)(v17 + 12) != 4 )
            {
LABEL_57:
              v3 = -1073741811;
              goto LABEL_49;
            }
            v18 = 8LL * v11;
            v4[v18 + 2] = 0;
LABEL_23:
            v19 = (char *)&v4[v18 + 4];
LABEL_38:
            memcpy_0(v19, (const void *)(*a2 + *(unsigned int *)(*a2 + 8)), *(unsigned int *)(*a2 + 12));
          }
          break;
        case 7:
          if ( v4 )
          {
            v20 = 8LL * v11;
            v4[v20 + 2] = 3;
            v21 = (char *)EaLibAllocate(*(unsigned int *)(*a2 + 12));
            *(_QWORD *)&v4[v20 + 6] = v21;
            if ( !v21 )
              goto LABEL_55;
            v22 = *(_DWORD *)(*a2 + 12);
            if ( v22 > 0x1FFFE )
              goto LABEL_56;
            LOWORD(v4[v20 + 4]) = v22 >> 1;
            v19 = v21;
            goto LABEL_38;
          }
          break;
        case 0xB:
          if ( !v4 )
            break;
          if ( *(_DWORD *)(v17 + 12) != 8 )
            goto LABEL_57;
          v18 = 8LL * v11;
          v4[v18 + 2] = 1;
          goto LABEL_23;
        default:
LABEL_54:
          v3 = -1073741811;
          goto LABEL_48;
      }
      ++v11;
      goto LABEL_40;
    }
    if ( *(_DWORD *)(v13 + 4) != 1 )
      goto LABEL_54;
    if ( *(_DWORD *)(v13 + 12) > 0xFFFFu )
      break;
    GuidString.Buffer = (PWSTR)(v13 + *(unsigned int *)(v13 + 8));
    GuidString.MaximumLength = *(_WORD *)(v13 + 12);
    GuidString.Length = GuidString.MaximumLength;
    if ( RtlGUIDFromString(&GuidString, &Guid) < 0 )
      goto LABEL_42;
LABEL_40:
    ++v10;
    v9 = KeyHandle;
  }
  v3 = -2147483643;
LABEL_48:
  if ( !v4 )
    return v3;
LABEL_49:
  v28 = 0;
  if ( !v5 )
    goto LABEL_65;
  v29 = 0;
  while ( 2 )
  {
    v30 = 8 * v29;
    if ( v4[8 * v29 + 2] == 2 )
    {
      v31 = *(void **)&v4[v30 + 4];
      goto LABEL_59;
    }
    if ( (unsigned int)(v4[8 * v29 + 2] - 3) <= 1 )
    {
      v31 = *(void **)&v4[v30 + 6];
LABEL_59:
      if ( v31 )
        EaLibFree(v31);
    }
    v32 = *(void **)&v4[v30];
    if ( v32 )
      EaLibFree(v32);
    ++v28;
    ++v29;
    if ( v28 < v5 )
      continue;
    break;
  }
  v4 = v36;
LABEL_65:
  EaLibFree(v4);
  return v3;
}

```

## disassembly

```asm
0x18000a5f8  mov     [rsp+arg_18], rbx
0x18000a5fd  push    rbp
0x18000a5fe  push    rsi
0x18000a5ff  push    rdi
0x18000a600  push    r12
0x18000a602  push    r13
0x18000a604  push    r14
0x18000a606  push    r15
0x18000a608  sub     rsp, 60h
0x18000a60c  mov     rax, cs:__security_cookie
0x18000a613  xor     rax, rsp
0x18000a616  mov     [rsp+98h+var_48], rax
0x18000a61b  xor     ebx, ebx
0x18000a61d  mov     [rsp+98h+var_78], rcx
0x18000a622  xorps   xmm0, xmm0
0x18000a625  mov     [rsp+98h+var_70], rbx
0x18000a62a  xorps   xmm1, xmm1
0x18000a62d  mov     edi, ebx
0x18000a62f  movups  xmmword ptr [rsp+98h+GuidString.Length], xmm0
0x18000a634  mov     r12d, ebx
0x18000a637  mov     ebp, ebx
0x18000a639  movups  xmmword ptr [rsp+98h+Guid.Data1], xmm1
0x18000a63e  mov     r15, r8
0x18000a641  mov     r14, rdx
0x18000a644  mov     rax, rcx
0x18000a647  mov     ecx, 2
0x18000a64c  cmp     bp, cx
0x18000a64f  jnb     loc_18000A9B6
0x18000a655  mov     r13d, ebx
0x18000a658  mov     esi, ebx
0x18000a65a  mov     r8, r14
0x18000a65d  mov     edx, r13d; Index
0x18000a660  mov     rcx, rax; KeyHandle
0x18000a663  call    EapEnumerateKeyValue
0x18000a668  mov     ebx, eax
0x18000a66a  cmp     eax, 8000001Ah
0x18000a66f  jz      loc_18000A8C6
0x18000a675  test    eax, eax
0x18000a677  js      loc_18000A91B
0x18000a67d  mov     rcx, [r14]
0x18000a680  xor     ebx, ebx
0x18000a682  mov     eax, [rcx+10h]
0x18000a685  test    eax, eax
0x18000a687  jnz     short loc_18000A6D9
0x18000a689  cmp     dword ptr [rcx+4], 1
0x18000a68d  jnz     loc_18000A95D
0x18000a693  cmp     dword ptr [rcx+0Ch], 0FFFFh
0x18000a69a  ja      loc_18000A916
0x18000a6a0  mov     eax, [rcx+8]
0x18000a6a3  lea     rdx, [rsp+98h+Guid]; Guid
0x18000a6a8  add     rax, rcx
0x18000a6ab  mov     [rsp+98h+GuidString.Buffer], rax
0x18000a6b0  movzx   eax, word ptr [rcx+0Ch]
0x18000a6b4  lea     rcx, [rsp+98h+GuidString]; GuidString
0x18000a6b9  mov     [rsp+98h+GuidString.MaximumLength], ax
0x18000a6be  mov     [rsp+98h+GuidString.Length], ax
0x18000a6c3  call    cs:__imp_RtlGUIDFromString
0x18000a6c9  test    eax, eax
0x18000a6cb  js      loc_18000A8C8
0x18000a6d1  lea     eax, [rbx+1]
0x18000a6d4  jmp     loc_18000A8B9
0x18000a6d9  test    rdi, rdi
0x18000a6dc  jz      short loc_18000A730
0x18000a6de  cmp     r12w, si
0x18000a6e2  jbe     loc_18000A96B
0x18000a6e8  lea     rcx, [rax+2]
0x18000a6ec  call    EaLibAllocate
0x18000a6f1  movzx   ebx, si
0x18000a6f4  mov     rcx, rax; void *
0x18000a6f7  shl     rbx, 5
0x18000a6fb  mov     [rbx+rdi], rax
0x18000a6ff  test    rax, rax
0x18000a702  jz      loc_18000A964
0x18000a708  mov     rax, [r14]
0x18000a70b  xor     edx, edx; Val
0x18000a70d  mov     r8d, [rax+10h]
0x18000a711  add     r8, 2; Size
0x18000a715  call    memset_0
0x18000a71a  mov     rdx, [r14]
0x18000a71d  mov     rcx, [rbx+rdi]; void *
0x18000a721  mov     r8d, [rdx+10h]; Size
0x18000a725  add     rdx, 14h; Src
0x18000a729  call    memcpy_0
0x18000a72e  xor     ebx, ebx
0x18000a730  mov     rdx, [r14]
0x18000a733  mov     ecx, [rdx+4]
0x18000a736  sub     ecx, 1
0x18000a739  jz      loc_18000A854
0x18000a73f  sub     ecx, 2
0x18000a742  jz      loc_18000A805
0x18000a748  sub     ecx, 1
0x18000a74b  jz      loc_18000A7E2
0x18000a751  sub     ecx, 3
0x18000a754  jz      short loc_18000A78D
0x18000a756  cmp     ecx, 4
0x18000a759  jnz     loc_18000A95D
0x18000a75f  test    rdi, rdi
0x18000a762  jz      loc_18000A8B1
0x18000a768  cmp     dword ptr [rdx+0Ch], 8
0x18000a76c  jnz     loc_18000A972
0x18000a772  movzx   ecx, si
0x18000a775  shl     rcx, 5
0x18000a779  mov     dword ptr [rcx+rdi+8], 1
0x18000a781  add     rcx, 10h
0x18000a785  add     rcx, rdi
0x18000a788  jmp     loc_18000A89F
0x18000a78d  test    rdi, rdi
0x18000a790  jz      loc_18000A8B1
0x18000a796  movzx   ebx, si
0x18000a799  shl     rbx, 5
0x18000a79d  mov     dword ptr [rbx+rdi+8], 3
0x18000a7a5  mov     rax, [r14]
0x18000a7a8  mov     ecx, [rax+0Ch]
0x18000a7ab  call    EaLibAllocate
0x18000a7b0  mov     [rbx+rdi+18h], rax
0x18000a7b5  mov     r9, rax
0x18000a7b8  test    rax, rax
0x18000a7bb  jz      loc_18000A964
0x18000a7c1  mov     rax, [r14]
0x18000a7c4  mov     ecx, [rax+0Ch]
0x18000a7c7  cmp     ecx, 1FFFEh
0x18000a7cd  ja      loc_18000A96B
0x18000a7d3  shr     ecx, 1
0x18000a7d5  mov     [rbx+rdi+10h], cx
0x18000a7da  mov     rcx, r9
0x18000a7dd  jmp     loc_18000A89F
0x18000a7e2  test    rdi, rdi
0x18000a7e5  jz      loc_18000A8B1
0x18000a7eb  cmp     dword ptr [rdx+0Ch], 4
0x18000a7ef  jnz     loc_18000A972
0x18000a7f5  movzx   ecx, si
0x18000a7f8  shl     rcx, 5
0x18000a7fc  mov     [rcx+rdi+8], ebx
0x18000a800  jmp     loc_18000A781
0x18000a805  test    rdi, rdi
0x18000a808  jz      loc_18000A8B1
0x18000a80e  movzx   ebx, si
0x18000a811  shl     rbx, 5
0x18000a815  mov     dword ptr [rbx+rdi+8], 4
0x18000a81d  mov     rax, [r14]
0x18000a820  mov     ecx, [rax+0Ch]
0x18000a823  call    EaLibAllocate
0x18000a828  mov     [rbx+rdi+18h], rax
0x18000a82d  mov     rcx, rax
0x18000a830  test    rax, rax
0x18000a833  jz      loc_18000A964
0x18000a839  mov     rax, [r14]
0x18000a83c  cmp     dword ptr [rax+0Ch], 1FFFEh
0x18000a843  ja      loc_18000A96B
0x18000a849  movzx   eax, word ptr [rax+0Ch]
0x18000a84d  mov     [rbx+rdi+10h], ax
0x18000a852  jmp     short loc_18000A89F
0x18000a854  test    rdi, rdi
0x18000a857  jz      short loc_18000A8B1
0x18000a859  movzx   ebx, si
0x18000a85c  shl     rbx, 5
0x18000a860  mov     dword ptr [rbx+rdi+8], 2
0x18000a868  mov     rax, [r14]
0x18000a86b  mov     ecx, [rax+0Ch]
0x18000a86e  add     rcx, 2
0x18000a872  call    EaLibAllocate
0x18000a877  mov     [rbx+rdi+10h], rax
0x18000a87c  mov     rcx, rax; void *
0x18000a87f  test    rax, rax
0x18000a882  jz      loc_18000A964
0x18000a888  mov     rax, [r14]
0x18000a88b  xor     edx, edx; Val
0x18000a88d  mov     r8d, [rax+0Ch]
0x18000a891  add     r8, 2; Size
0x18000a895  call    memset_0
0x18000a89a  mov     rcx, [rbx+rdi+10h]; void *
0x18000a89f  mov     rax, [r14]
0x18000a8a2  mov     edx, [rax+8]
0x18000a8a5  mov     r8d, [rax+0Ch]; Size
0x18000a8a9  add     rdx, rax; Src
0x18000a8ac  call    memcpy_0
0x18000a8b1  mov     eax, 1
0x18000a8b6  add     si, ax
0x18000a8b9  add     r13d, eax
0x18000a8bc  mov     rax, [rsp+98h+var_78]
0x18000a8c1  jmp     loc_18000A65A
0x18000a8c6  xor     ebx, ebx
0x18000a8c8  test    si, si
0x18000a8cb  jz      loc_18000A9B6
0x18000a8d1  test    bp, bp
0x18000a8d4  jnz     short loc_18000A909
0x18000a8d6  movzx   ebx, si
0x18000a8d9  shl     rbx, 5
0x18000a8dd  mov     rcx, rbx
0x18000a8e0  call    EaLibAllocate
0x18000a8e5  mov     [rsp+98h+var_70], rax
0x18000a8ea  mov     rdi, rax
0x18000a8ed  test    rax, rax
0x18000a8f0  jz      loc_18000A9AF
0x18000a8f6  mov     r8, rbx; Size
0x18000a8f9  xor     edx, edx; Val
0x18000a8fb  mov     rcx, rax; void *
0x18000a8fe  call    memset_0
0x18000a903  xor     ebx, ebx
0x18000a905  movzx   r12d, si
0x18000a909  mov     rax, [rsp+98h+var_78]
0x18000a90e  inc     bp
0x18000a911  jmp     loc_18000A647
0x18000a916  mov     ebx, 80000005h
0x18000a91b  test    rdi, rdi
0x18000a91e  jz      loc_18000A9C9
0x18000a924  xor     r13d, r13d
0x18000a927  movzx   r12d, r12w
0x18000a92b  mov     rsi, rdi
0x18000a92e  mov     ebp, r13d
0x18000a931  test    r12d, r12d
0x18000a934  jz      short loc_18000A9A5
0x18000a936  mov     r15d, r13d
0x18000a939  lea     edi, [r13+1]
0x18000a93d  mov     r14, r15
0x18000a940  shl     r14, 5
0x18000a944  mov     ecx, [r14+rsi+8]
0x18000a949  sub     ecx, 2
0x18000a94c  jz      short loc_18000A979
0x18000a94e  sub     ecx, edi
0x18000a950  jz      short loc_18000A956
0x18000a952  cmp     ecx, edi
0x18000a954  jnz     short loc_18000A988
0x18000a956  mov     rcx, [r14+rsi+18h]
0x18000a95b  jmp     short loc_18000A97E
0x18000a95d  mov     ebx, 0C000000Dh
0x18000a962  jmp     short loc_18000A91B
0x18000a964  mov     ebx, 0C0000017h
0x18000a969  jmp     short loc_18000A924
0x18000a96b  mov     ebx, 80000005h
0x18000a970  jmp     short loc_18000A924
0x18000a972  mov     ebx, 0C000000Dh
0x18000a977  jmp     short loc_18000A924
0x18000a979  mov     rcx, [r14+rsi+10h]
0x18000a97e  test    rcx, rcx
0x18000a981  jz      short loc_18000A988
0x18000a983  call    EaLibFree
0x18000a988  mov     rcx, [r14+rsi]
0x18000a98c  test    rcx, rcx
0x18000a98f  jz      short loc_18000A996
0x18000a991  call    EaLibFree
0x18000a996  add     ebp, edi
0x18000a998  add     r15, rdi
0x18000a99b  cmp     ebp, r12d
0x18000a99e  jb      short loc_18000A93D
0x18000a9a0  mov     rdi, [rsp+98h+var_70]
0x18000a9a5  mov     rcx, rdi
0x18000a9a8  call    EaLibFree
0x18000a9ad  jmp     short loc_18000A9C9
0x18000a9af  mov     ebx, 0C0000017h
0x18000a9b4  jmp     short loc_18000A9C9
0x18000a9b6  movups  xmm0, xmmword ptr [rsp+98h+Guid.Data1]
0x18000a9bb  mov     [r15+18h], rdi
0x18000a9bf  mov     [r15+10h], r12w
0x18000a9c4  movdqu  xmmword ptr [r15], xmm0
0x18000a9c9  mov     eax, ebx
0x18000a9cb  mov     rcx, [rsp+98h+var_48]
0x18000a9d0  xor     rcx, rsp; StackCookie
0x18000a9d3  call    __security_check_cookie
0x18000a9d8  mov     rbx, [rsp+98h+arg_18]
0x18000a9e0  add     rsp, 60h
0x18000a9e4  pop     r15
0x18000a9e6  pop     r14
0x18000a9e8  pop     r13
0x18000a9ea  pop     r12
0x18000a9ec  pop     rdi
0x18000a9ed  pop     rsi
0x18000a9ee  pop     rbp
0x18000a9ef  retn
```
