# TreeUnlinkMulti

- ea: `0x180012d80`
- end: `0x1800130c8`
- name: `TreeUnlinkMulti`
- size: `840`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18004fbf0`
- `0x180060cd0`
- `0x180061760`
- `0x180061e00`
- `0x180062050`
- `0x180062510`
- `0x180062ba0`
- `0x180070b30`

## callees

- `0x18000d270`
- `0x180012d80`
- `0x1800139a0`

## import_xrefs

- `ntoskrnl!RtlDeleteNoSplay` at `0x180012e26`
- `ntoskrnl!RtlDeleteNoSplay` at `0x180012e84`
- `ntoskrnl!RtlDeleteNoSplay` at `0x180012ebe`
- `ntoskrnl!RtlDeleteNoSplay` at `0x180012f1f`
- `ntoskrnl!RtlDeleteNoSplay` at `0x180012f72`
- `ntoskrnl!RtlDeleteNoSplay` at `0x180012e26`
- `ntoskrnl!RtlDeleteNoSplay` at `0x180012e84`
- `ntoskrnl!RtlDeleteNoSplay` at `0x180012ebe`
- `ntoskrnl!RtlDeleteNoSplay` at `0x180012f1f`
- `ntoskrnl!RtlDeleteNoSplay` at `0x180012f72`

## pseudocode

```c
__int64 __fastcall TreeUnlinkMulti(_QWORD *a1, unsigned __int64 a2, __int64 a3)
{
  _QWORD *v3; // rsi
  _QWORD *v7; // rbx
  __int64 result; // rax
  _QWORD *v9; // rdi
  _QWORD *v10; // r15
  _QWORD *v11; // rbp
  PRTL_SPLAY_LINKS *v12; // rdx
  _QWORD *v13; // r15
  _QWORD *v14; // rbp
  PRTL_SPLAY_LINKS *v15; // rdx
  _QWORD *v16; // r12
  _QWORD *v17; // rax
  _QWORD *v18; // r13
  volatile signed __int32 *v19; // r12
  struct _RTL_SPLAY_LINKS *v20; // rcx
  _QWORD *i; // rbx
  _QWORD *v22; // rax
  _QWORD *v23; // rcx
  _QWORD *v24; // rax
  _QWORD *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rbx

  v3 = 0;
  if ( a2 == -1 )
  {
    if ( a3 == -1 )
    {
      for ( i = (_QWORD *)*a1; *a1; i = (_QWORD *)*a1 )
      {
        RtlDeleteNoSplay((PRTL_SPLAY_LINKS)i, (PRTL_SPLAY_LINKS *)i[3]);
        if ( (i[6] & 0x10000) != 0 )
          _InterlockedAnd((volatile signed __int32 *)i + 12, 0xFFFEFFFF);
        i[2] = v3;
        v3 = i;
      }
      return (__int64)v3;
    }
    v9 = (_QWORD *)*a1;
    v10 = (_QWORD *)*a1;
    if ( !*a1 )
      return (__int64)v3;
    while ( 1 )
    {
      while ( v9[5] == a3 )
      {
        v11 = v9;
        v12 = (PRTL_SPLAY_LINKS *)v9[3];
        if ( (_QWORD *)*a1 == v9 )
        {
          RtlDeleteNoSplay((PRTL_SPLAY_LINKS)v9, v12);
          if ( (v9[6] & 0x10000) != 0 )
            _InterlockedAnd((volatile signed __int32 *)v9 + 12, 0xFFFEFFFF);
          v9 = (_QWORD *)*a1;
          v11[2] = v3;
          v10 = v9;
          v3 = v11;
        }
        else
        {
          v18 = (_QWORD *)*v9;
          v19 = (volatile signed __int32 *)(v9 + 6);
          v20 = (struct _RTL_SPLAY_LINKS *)v9;
          v9 = (_QWORD *)*v9;
          RtlDeleteNoSplay(v20, v12);
          if ( (*v19 & 0x10000) != 0 )
            _InterlockedAnd(v19, 0xFFFEFFFF);
          v11[2] = v3;
          v3 = v11;
          if ( v10 == v11 )
            v10 = v18;
        }
LABEL_17:
        if ( !v9 )
          return (__int64)v3;
      }
      if ( v9[1] )
      {
        v9 = (_QWORD *)v9[1];
      }
      else
      {
        if ( !v9[2] )
        {
          if ( v9 == v10 )
          {
LABEL_78:
            v9 = 0;
          }
          else
          {
            v24 = (_QWORD *)*v9;
            v25 = v9;
            while ( 1 )
            {
              for ( ; v24 != v10; v24 = (_QWORD *)*v24 )
              {
                if ( v24[2] )
                  break;
                if ( v25 != (_QWORD *)v24[1] )
                  break;
                v25 = v24;
              }
              v9 = (_QWORD *)v24[2];
              if ( v25 != v9 )
                break;
              if ( v24 == v10 )
              {
LABEL_77:
                if ( v25 == (_QWORD *)v24[2] )
                  goto LABEL_78;
              }
              else
              {
                while ( v25 == (_QWORD *)v24[2] )
                {
                  v25 = v24;
                  v24 = (_QWORD *)*v24;
                  if ( v24 == v10 )
                    goto LABEL_77;
                }
              }
            }
          }
          goto LABEL_17;
        }
        v9 = (_QWORD *)v9[2];
      }
    }
  }
  if ( a3 == -1 )
  {
    v7 = (_QWORD *)*a1;
    if ( *a1 )
    {
      while ( 1 )
      {
        if ( a2 < v7[4] )
        {
          v7 = (_QWORD *)v7[1];
          goto LABEL_7;
        }
        if ( a2 == v7[4] )
          break;
        v7 = (_QWORD *)v7[2];
LABEL_7:
        if ( !v7 )
          return (__int64)v3;
      }
      if ( v7 )
      {
        v13 = v7;
        while ( 1 )
        {
          while ( v7[4] == a2 )
          {
            v14 = v7;
            v15 = (PRTL_SPLAY_LINKS *)v7[3];
            if ( (_QWORD *)*a1 == v7 )
            {
              RtlDeleteNoSplay((PRTL_SPLAY_LINKS)v7, v15);
              if ( (v7[6] & 0x10000) != 0 )
                _InterlockedAnd((volatile signed __int32 *)v7 + 12, 0xFFFEFFFF);
              v7 = (_QWORD *)*a1;
              v14[2] = v3;
              v13 = v7;
              v3 = v14;
            }
            else
            {
              v16 = v7;
              RtlDeleteNoSplay((PRTL_SPLAY_LINKS)v7, v15);
              if ( (v7[6] & 0x10000) != 0 )
                _InterlockedAnd((volatile signed __int32 *)v7 + 12, 0xFFFEFFFF);
              v7[2] = v3;
              v7 = 0;
              v17 = (_QWORD *)*a1;
              v3 = v14;
              if ( *a1 )
              {
                while ( 1 )
                {
                  while ( a2 < v17[4] )
                  {
                    v17 = (_QWORD *)v17[1];
                    if ( !v17 )
                      goto LABEL_34;
                  }
                  if ( a2 == v17[4] )
                    break;
                  v17 = (_QWORD *)v17[2];
                  if ( !v17 )
                    goto LABEL_34;
                }
                if ( v17 )
                  v7 = v17;
              }
LABEL_34:
              if ( v13 == v16 )
                v13 = v7;
            }
LABEL_26:
            if ( !v7 )
              return (__int64)v3;
          }
          if ( v7[1] )
          {
            v7 = (_QWORD *)v7[1];
          }
          else
          {
            if ( !v7[2] )
            {
              if ( v7 == v13 )
              {
LABEL_60:
                v7 = 0;
              }
              else
              {
                v22 = (_QWORD *)*v7;
                v23 = v7;
                while ( 1 )
                {
                  for ( ; v22 != v13; v22 = (_QWORD *)*v22 )
                  {
                    if ( v22[2] )
                      break;
                    if ( v23 != (_QWORD *)v22[1] )
                      break;
                    v23 = v22;
                  }
                  v7 = (_QWORD *)v22[2];
                  if ( v23 != v7 )
                    break;
                  if ( v22 == v13 )
                  {
LABEL_59:
                    if ( v23 == (_QWORD *)v22[2] )
                      goto LABEL_60;
                  }
                  else
                  {
                    while ( v23 == (_QWORD *)v22[2] )
                    {
                      v23 = v22;
                      v22 = (_QWORD *)*v22;
                      if ( v22 == v13 )
                        goto LABEL_59;
                    }
                  }
                }
              }
              goto LABEL_26;
            }
            v7 = (_QWORD *)v7[2];
          }
        }
      }
    }
    return (__int64)v3;
  }
  v26 = TreeLookup();
  v27 = v26;
  if ( !v26 )
    return (__int64)v3;
  TreeUnlink(v26);
  result = v27;
  *(_QWORD *)(v27 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x180012d80  mov     [rsp+arg_10], rbx
0x180012d85  mov     [rsp+arg_18], rbp
0x180012d8a  push    rsi
0x180012d8b  push    rdi
0x180012d8c  push    r12
0x180012d8e  push    r14
0x180012d90  push    r15
0x180012d92  sub     rsp, 20h
0x180012d96  xor     esi, esi
0x180012d98  mov     rbx, r8
0x180012d9b  mov     rdi, rdx
0x180012d9e  mov     r14, rcx
0x180012da1  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180012da5  jz      short loc_180012DEF
0x180012da7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180012dab  jnz     loc_1800130A3
0x180012db1  mov     rbx, [rcx]
0x180012db4  test    rbx, rbx
0x180012db7  jz      short loc_180012DCE
0x180012db9  cmp     rdi, [rbx+20h]
0x180012dbd  jb      short loc_180012DE9
0x180012dbf  jz      loc_180012E5F
0x180012dc5  mov     rbx, [rbx+10h]
0x180012dc9  test    rbx, rbx
0x180012dcc  jnz     short loc_180012DB9
0x180012dce  mov     rax, rsi
0x180012dd1  mov     rbx, [rsp+48h+arg_10]
0x180012dd6  mov     rbp, [rsp+48h+arg_18]
0x180012ddb  add     rsp, 20h
0x180012ddf  pop     r15
0x180012de1  pop     r14
0x180012de3  pop     r12
0x180012de5  pop     rdi
0x180012de6  pop     rsi
0x180012de7  retn
0x180012de9  mov     rbx, [rbx+8]
0x180012ded  jmp     short loc_180012DC9
0x180012def  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180012df3  jz      loc_180012F5F
0x180012df9  mov     rdi, [rcx]
0x180012dfc  mov     r15, rdi
0x180012dff  test    rdi, rdi
0x180012e02  jz      short loc_180012DCE
0x180012e04  mov     [rsp+48h+arg_0], r13
0x180012e09  cmp     [rdi+28h], rbx
0x180012e0d  jnz     loc_180013023
0x180012e13  mov     rbp, rdi
0x180012e16  mov     rdx, [rdi+18h]; Root
0x180012e1a  cmp     [r14], rdi
0x180012e1d  jnz     loc_180012F12
0x180012e23  mov     rcx, rdi; Links
0x180012e26  call    cs:__imp_RtlDeleteNoSplay
0x180012e2d  nop     dword ptr [rax+rax+00h]
0x180012e32  mov     eax, [rdi+30h]
0x180012e35  bt      eax, 10h
0x180012e39  jnb     short loc_180012E43
0x180012e3b  lock and dword ptr [rdi+30h], 0FFFEFFFFh
0x180012e43  mov     rdi, [r14]
0x180012e46  mov     [rbp+10h], rsi
0x180012e4a  mov     r15, rdi
0x180012e4d  mov     rsi, rbp
0x180012e50  test    rdi, rdi
0x180012e53  jnz     short loc_180012E09
0x180012e55  mov     r13, [rsp+48h+arg_0]
0x180012e5a  jmp     loc_180012DCE
0x180012e5f  test    rbx, rbx
0x180012e62  jz      loc_180012DCE
0x180012e68  mov     r15, rbx
0x180012e6b  cmp     [rbx+20h], rdi
0x180012e6f  jnz     loc_180012FA3
0x180012e75  mov     rbp, rbx
0x180012e78  mov     rdx, [rbx+18h]; Root
0x180012e7c  cmp     [r14], rbx
0x180012e7f  jnz     short loc_180012EB8
0x180012e81  mov     rcx, rbx; Links
0x180012e84  call    cs:__imp_RtlDeleteNoSplay
0x180012e8b  nop     dword ptr [rax+rax+00h]
0x180012e90  mov     eax, [rbx+30h]
0x180012e93  bt      eax, 10h
0x180012e97  jnb     short loc_180012EA1
0x180012e99  lock and dword ptr [rbx+30h], 0FFFEFFFFh
0x180012ea1  mov     rbx, [r14]
0x180012ea4  mov     [rbp+10h], rsi
0x180012ea8  mov     r15, rbx
0x180012eab  mov     rsi, rbp
0x180012eae  test    rbx, rbx
0x180012eb1  jnz     short loc_180012E6B
0x180012eb3  jmp     loc_180012DCE
0x180012eb8  mov     rcx, rbp; Links
0x180012ebb  mov     r12, rbx
0x180012ebe  call    cs:__imp_RtlDeleteNoSplay
0x180012ec5  nop     dword ptr [rax+rax+00h]
0x180012eca  mov     eax, [rbx+30h]
0x180012ecd  bt      eax, 10h
0x180012ed1  jnb     short loc_180012EDB
0x180012ed3  lock and dword ptr [rbx+30h], 0FFFEFFFFh
0x180012edb  mov     [rbx+10h], rsi
0x180012edf  xor     ebx, ebx
0x180012ee1  mov     rax, [r14]
0x180012ee4  mov     rsi, rbp
0x180012ee7  test    rax, rax
0x180012eea  jz      short loc_180012EFD
0x180012eec  cmp     rdi, [rax+20h]
0x180012ef0  jb      short loc_180012F07
0x180012ef2  jz      short loc_180012F56
0x180012ef4  mov     rax, [rax+10h]
0x180012ef8  test    rax, rax
0x180012efb  jnz     short loc_180012EEC
0x180012efd  cmp     r15, r12
0x180012f00  jnz     short loc_180012EAE
0x180012f02  mov     r15, rbx
0x180012f05  jmp     short loc_180012EAE
0x180012f07  mov     rax, [rax+8]
0x180012f0b  test    rax, rax
0x180012f0e  jnz     short loc_180012EEC
0x180012f10  jmp     short loc_180012EFD
0x180012f12  mov     r13, [rdi]
0x180012f15  lea     r12, [rdi+30h]
0x180012f19  mov     rcx, rbp; Links
0x180012f1c  mov     rdi, r13
0x180012f1f  call    cs:__imp_RtlDeleteNoSplay
0x180012f26  nop     dword ptr [rax+rax+00h]
0x180012f2b  mov     eax, [r12]
0x180012f2f  bt      eax, 10h
0x180012f33  jnb     short loc_180012F3E
0x180012f35  lock and dword ptr [r12], 0FFFEFFFFh
0x180012f3e  mov     [rbp+10h], rsi
0x180012f42  mov     rsi, rbp
0x180012f45  cmp     r15, rbp
0x180012f48  jnz     loc_180012E50
0x180012f4e  mov     r15, r13
0x180012f51  jmp     loc_180012E50
0x180012f56  test    rax, rax
0x180012f59  cmovnz  rbx, rax
0x180012f5d  jmp     short loc_180012EFD
0x180012f5f  mov     rbx, [rcx]
0x180012f62  test    rbx, rbx
0x180012f65  jz      loc_180012DCE
0x180012f6b  mov     rdx, [rbx+18h]; Root
0x180012f6f  mov     rcx, rbx; Links
0x180012f72  call    cs:__imp_RtlDeleteNoSplay
0x180012f79  nop     dword ptr [rax+rax+00h]
0x180012f7e  mov     eax, [rbx+30h]
0x180012f81  bt      eax, 10h
0x180012f85  jnb     short loc_180012F8F
0x180012f87  lock and dword ptr [rbx+30h], 0FFFEFFFFh
0x180012f8f  mov     [rbx+10h], rsi
0x180012f93  mov     rsi, rbx
0x180012f96  mov     rbx, [r14]
0x180012f99  test    rbx, rbx
0x180012f9c  jnz     short loc_180012F6B
0x180012f9e  jmp     loc_180012DCE
0x180012fa3  mov     rax, [rbx+8]
0x180012fa7  test    rax, rax
0x180012faa  jz      short loc_180012FB4
0x180012fac  mov     rbx, rax
0x180012faf  jmp     loc_180012E6B
0x180012fb4  mov     rax, [rbx+10h]
0x180012fb8  test    rax, rax
0x180012fbb  jnz     short loc_180012FF3
0x180012fbd  cmp     rbx, r15
0x180012fc0  jz      short loc_180012FEC
0x180012fc2  mov     rax, [rbx]
0x180012fc5  mov     rcx, rbx
0x180012fc8  cmp     rax, r15
0x180012fcb  jz      short loc_180012FD4
0x180012fcd  cmp     qword ptr [rax+10h], 0
0x180012fd2  jz      short loc_180012FFB
0x180012fd4  mov     rbx, [rax+10h]
0x180012fd8  cmp     rcx, rbx
0x180012fdb  jnz     loc_180012EAE
0x180012fe1  cmp     rax, r15
0x180012fe4  jnz     short loc_180013010
0x180012fe6  cmp     rcx, [rax+10h]
0x180012fea  jnz     short loc_180012FC8
0x180012fec  xor     ebx, ebx
0x180012fee  jmp     loc_180012EAE
0x180012ff3  mov     rbx, rax
0x180012ff6  jmp     loc_180012E6B
0x180012ffb  cmp     rcx, [rax+8]
0x180012fff  jnz     short loc_180012FD4
0x180013001  mov     rcx, rax
0x180013004  mov     rax, [rax]
0x180013007  cmp     rax, r15
0x18001300a  jnz     short loc_180012FCD
0x18001300c  jmp     short loc_180012FD4
0x180013010  cmp     rcx, [rax+10h]
0x180013014  jnz     short loc_180012FC8
0x180013016  mov     rcx, rax
0x180013019  mov     rax, [rax]
0x18001301c  cmp     rax, r15
0x18001301f  jnz     short loc_180013010
0x180013021  jmp     short loc_180012FE6
0x180013023  mov     rax, [rdi+8]
0x180013027  test    rax, rax
0x18001302a  jz      short loc_180013034
0x18001302c  mov     rdi, rax
0x18001302f  jmp     loc_180012E09
0x180013034  mov     rax, [rdi+10h]
0x180013038  test    rax, rax
0x18001303b  jnz     short loc_180013073
0x18001303d  cmp     rdi, r15
0x180013040  jz      short loc_18001306C
0x180013042  mov     rax, [rdi]
0x180013045  mov     rcx, rdi
0x180013048  cmp     rax, r15
0x18001304b  jz      short loc_180013054
0x18001304d  cmp     qword ptr [rax+10h], 0
0x180013052  jz      short loc_18001307B
0x180013054  mov     rdi, [rax+10h]
0x180013058  cmp     rcx, rdi
0x18001305b  jnz     loc_180012E50
0x180013061  cmp     rax, r15
0x180013064  jnz     short loc_180013090
0x180013066  cmp     rcx, [rax+10h]
0x18001306a  jnz     short loc_180013048
0x18001306c  xor     edi, edi
0x18001306e  jmp     loc_180012E50
0x180013073  mov     rdi, rax
0x180013076  jmp     loc_180012E09
0x18001307b  cmp     rcx, [rax+8]
0x18001307f  jnz     short loc_180013054
0x180013081  mov     rcx, rax
0x180013084  mov     rax, [rax]
0x180013087  cmp     rax, r15
0x18001308a  jnz     short loc_18001304D
0x18001308c  jmp     short loc_180013054
0x180013090  cmp     rcx, [rax+10h]
0x180013094  jnz     short loc_180013048
0x180013096  mov     rcx, rax
0x180013099  mov     rax, [rax]
0x18001309c  cmp     rax, r15
0x18001309f  jnz     short loc_180013090
0x1800130a1  jmp     short loc_180013066
0x1800130a3  call    TreeLookup
0x1800130a8  mov     rbx, rax
0x1800130ab  test    rax, rax
0x1800130ae  jz      loc_180012DCE
0x1800130b4  mov     rcx, rax
0x1800130b7  call    TreeUnlink
0x1800130bc  mov     rax, rbx
0x1800130bf  mov     [rbx+10h], rsi
0x1800130c3  jmp     loc_180012DD1
```
