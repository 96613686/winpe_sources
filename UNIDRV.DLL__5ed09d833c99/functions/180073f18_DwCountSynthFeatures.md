# DwCountSynthFeatures

- ea: `0x180073f18`
- end: `0x180074136`
- name: `DwCountSynthFeatures`
- size: `542`
- prototype: `__int64 __fastcall(unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, __int64), __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180049418`

## callees

- `0x180007150`
- `0x180040318`
- `0x180073db0`
- `0x180073f18`
- `0x180077010`

## string_xrefs

- `0x180073ff2`: `DwCountSynthFeatures: Unable to create synthesized feature for installable Feature index %d.`
- `0x18007402c`: `Internal error:  DwCountSynthFeatures - atrOptInstallable should never be branchless.`
- `0x1800740b9`: `DwCountSynthFeatures: Unable to create synthesized feature for installable option: fea=%d, opt=%d.`

## pseudocode

```c
__int64 __fastcall DwCountSynthFeatures(unsigned int (__fastcall *a1)(_QWORD, __int64, _QWORD, __int64), __int64 a2)
{
  unsigned int v5; // ebp
  unsigned int v6; // r15d
  __int64 v7; // rsi
  __int64 v8; // r13
  __int64 v9; // rax
  __int64 v10; // r12
  __int64 v11; // r11
  int v12; // eax
  unsigned int v13; // edx
  unsigned int v14; // r14d
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // [rsp+30h] [rbp-48h]
  unsigned int v18; // [rsp+80h] [rbp+8h] BYREF
  unsigned int i; // [rsp+90h] [rbp+18h]
  unsigned int v20; // [rsp+98h] [rbp+20h]

  v18 = 0;
  if ( a1 && !*(_DWORD *)(a2 + 296) )
    return 0;
  v5 = 0;
  v6 = 0;
  v7 = *(_QWORD *)(a2 + 264);
  v17 = *(_QWORD *)(a2 + 72);
  v20 = *(_DWORD *)(a2 + 272);
  if ( v20 )
  {
    v8 = 0;
    do
    {
      if ( !a1 )
      {
        v9 = 396 * v8;
        *(_QWORD *)(v9 + v7 + 376) = -1;
        *(_DWORD *)(v9 + v7 + 372) = -1;
      }
      v10 = 396 * v8;
      if ( (unsigned int)BReadDataInGlobalNode((unsigned int *)(396 * v8 + v7 + 16), &v18, a2)
        && *(_DWORD *)(v18 + *(_QWORD *)a2) == 1 )
      {
        if ( a1 )
        {
          if ( !a1(v6, 0xFFFFFFFFLL, v5, a2) )
          {
            WriteDbgTraceErrorGpd(
              (__int64)"DwCountSynthFeatures",
              "DwCountSynthFeatures: Unable to create synthesized feature for installable Feature index %d.",
              v6);
            *(_DWORD *)(v10 + v7 + 380) = -1;
          }
          v11 = v17;
        }
        ++v5;
      }
      v12 = *(_DWORD *)(v10 + v7 + 88);
      if ( v12 != 0x7FFFFFFF )
      {
        if ( v12 >= 0 )
        {
          v13 = *(_DWORD *)(v10 + v7 + 392);
          v14 = 0;
          for ( i = v13; v14 < v13; ++v14 )
          {
            v15 = *(unsigned int *)(v10 + v7 + 88);
            while ( 1 )
            {
              v16 = 5 * v15;
              if ( *(_DWORD *)(v11 + 20 * v15 + 4) == v14 )
                break;
              v15 = *(unsigned int *)(v11 + 20 * v15 + 8);
              if ( (_DWORD)v15 == -1 )
              {
                if ( *(_DWORD *)(v11 + 4 * v16 + 4) != -1 )
                  goto LABEL_30;
                break;
              }
            }
            if ( *(_DWORD *)(v11 + 4 * v16 + 16) == 1
              && *(_DWORD *)(*(unsigned int *)(v11 + 4 * v16 + 12) + *(_QWORD *)a2) == 1 )
            {
              if ( a1 )
              {
                if ( !a1(v6, v14, v5, a2) )
                {
                  WriteDbgTraceErrorGpd(
                    (__int64)"DwCountSynthFeatures",
                    "DwCountSynthFeatures: Unable to create synthesized feature for installable option: fea=%d, opt=%d.",
                    v6,
                    v14);
                  *(_DWORD *)(v10 + v7 + 368) = 0x7FFFFFFF;
                }
                v11 = v17;
                v13 = i;
              }
              ++v5;
            }
LABEL_30:
            ;
          }
        }
        else
        {
          WriteDbgTraceErrorGpd(
            (__int64)"DwCountSynthFeatures",
            "Internal error:  DwCountSynthFeatures - atrOptInstallable should never be branchless.");
        }
      }
      ++v6;
      ++v8;
    }
    while ( v6 < v20 );
  }
  if ( a1 )
    BEnableInvInstallableCombos(a2);
  return v5;
}

```

## disassembly

```asm
0x180073f18  mov     rax, rsp
0x180073f1b  mov     [rax+10h], rbx
0x180073f1f  push    rbp
0x180073f20  push    rsi
0x180073f21  push    rdi
0x180073f22  push    r12
0x180073f24  push    r13
0x180073f26  push    r14
0x180073f28  push    r15
0x180073f2a  sub     rsp, 40h
0x180073f2e  mov     dword ptr [rax+8], 0
0x180073f35  mov     rbx, rdx
0x180073f38  mov     rdi, rcx
0x180073f3b  test    rcx, rcx
0x180073f3e  jz      short loc_180073F50
0x180073f40  cmp     dword ptr [rdx+128h], 0
0x180073f47  jnz     short loc_180073F50
0x180073f49  xor     eax, eax
0x180073f4b  jmp     loc_18007411D
0x180073f50  mov     eax, [rdx+110h]
0x180073f56  xor     ebp, ebp
0x180073f58  mov     r11, [rdx+48h]
0x180073f5c  xor     r15d, r15d
0x180073f5f  mov     rsi, [rdx+108h]
0x180073f66  mov     [rsp+78h+var_48], r11
0x180073f6b  mov     [rsp+78h+arg_18], eax
0x180073f72  test    eax, eax
0x180073f74  jz      loc_18007410E
0x180073f7a  xor     r13d, r13d
0x180073f7d  test    rdi, rdi
0x180073f80  jnz     short loc_180073FA0
0x180073f82  imul    rax, r13, 18Ch
0x180073f89  mov     qword ptr [rax+rsi+178h], 0FFFFFFFFFFFFFFFFh
0x180073f95  mov     dword ptr [rax+rsi+174h], 0FFFFFFFFh
0x180073fa0  imul    r12, r13, 18Ch
0x180073fa7  lea     rcx, [rsi+10h]
0x180073fab  mov     r8, rbx
0x180073fae  add     rcx, r12
0x180073fb1  lea     rdx, [rsp+78h+arg_0]
0x180073fb9  call    BReadDataInGlobalNode
0x180073fbe  test    eax, eax
0x180073fc0  jz      short loc_180074018
0x180073fc2  mov     ecx, [rsp+78h+arg_0]
0x180073fc9  mov     rax, [rbx]
0x180073fcc  cmp     dword ptr [rcx+rax], 1
0x180073fd0  jnz     short loc_180074018
0x180073fd2  test    rdi, rdi
0x180073fd5  jz      short loc_180074016
0x180073fd7  mov     r9, rbx
0x180073fda  mov     r8d, ebp
0x180073fdd  or      edx, 0FFFFFFFFh
0x180073fe0  mov     ecx, r15d
0x180073fe3  mov     rax, rdi
0x180073fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073feb  test    eax, eax
0x180073fed  jnz     short loc_180074011
0x180073fef  mov     r8d, r15d
0x180073ff2  lea     rdx, aDwcountsynthfe_0; "DwCountSynthFeatures: Unable to create "...
0x180073ff9  lea     rcx, aDwcountsynthfe; "DwCountSynthFeatures"
0x180074000  call    WriteDbgTraceErrorGpd
0x180074005  mov     dword ptr [r12+rsi+17Ch], 0FFFFFFFFh
0x180074011  mov     r11, [rsp+78h+var_48]
0x180074016  inc     ebp
0x180074018  mov     eax, [r12+rsi+58h]
0x18007401d  cmp     eax, 7FFFFFFFh
0x180074022  jz      loc_1800740F5
0x180074028  test    eax, eax
0x18007402a  jns     short loc_180074044
0x18007402c  lea     rdx, aInternalErrorD; "Internal error:  DwCountSynthFeatures -"...
0x180074033  lea     rcx, aDwcountsynthfe; "DwCountSynthFeatures"
0x18007403a  call    WriteDbgTraceErrorGpd
0x18007403f  jmp     loc_1800740F5
0x180074044  mov     edx, [r12+rsi+188h]
0x18007404c  xor     r14d, r14d
0x18007404f  mov     [rsp+78h+arg_10], edx
0x180074056  test    edx, edx
0x180074058  jz      loc_1800740F5
0x18007405e  mov     eax, [r12+rsi+58h]
0x180074063  or      r8d, 0FFFFFFFFh
0x180074067  lea     rcx, [rax+rax*4]
0x18007406b  cmp     [r11+rcx*4+4], r14d
0x180074070  jz      short loc_180074083
0x180074072  mov     eax, [r11+rcx*4+8]
0x180074077  cmp     eax, r8d
0x18007407a  jnz     short loc_180074067
0x18007407c  cmp     [r11+rcx*4+4], r8d
0x180074081  jnz     short loc_1800740E9
0x180074083  cmp     dword ptr [r11+rcx*4+10h], 1
0x180074089  jnz     short loc_1800740E9
0x18007408b  mov     ecx, [r11+rcx*4+0Ch]
0x180074090  mov     rax, [rbx]
0x180074093  cmp     dword ptr [rcx+rax], 1
0x180074097  jnz     short loc_1800740E9
0x180074099  test    rdi, rdi
0x18007409c  jz      short loc_1800740E7
0x18007409e  mov     r9, rbx
0x1800740a1  mov     r8d, ebp
0x1800740a4  mov     edx, r14d
0x1800740a7  mov     ecx, r15d
0x1800740aa  mov     rax, rdi
0x1800740ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800740b2  test    eax, eax
0x1800740b4  jnz     short loc_1800740DB
0x1800740b6  mov     r9d, r14d
0x1800740b9  lea     rdx, aDwcountsynthfe_1; "DwCountSynthFeatures: Unable to create "...
0x1800740c0  mov     r8d, r15d
0x1800740c3  lea     rcx, aDwcountsynthfe; "DwCountSynthFeatures"
0x1800740ca  call    WriteDbgTraceErrorGpd
0x1800740cf  mov     dword ptr [r12+rsi+170h], 7FFFFFFFh
0x1800740db  mov     r11, [rsp+78h+var_48]
0x1800740e0  mov     edx, [rsp+78h+arg_10]
0x1800740e7  inc     ebp
0x1800740e9  inc     r14d
0x1800740ec  cmp     r14d, edx
0x1800740ef  jb      loc_18007405E
0x1800740f5  mov     r11, [rsp+78h+var_48]
0x1800740fa  inc     r15d
0x1800740fd  inc     r13
0x180074100  cmp     r15d, [rsp+78h+arg_18]
0x180074108  jb      loc_180073F7D
0x18007410e  test    rdi, rdi
0x180074111  jz      short loc_18007411B
0x180074113  mov     rcx, rbx
0x180074116  call    BEnableInvInstallableCombos
0x18007411b  mov     eax, ebp
0x18007411d  mov     rbx, [rsp+78h+arg_8]
0x180074125  add     rsp, 40h
0x180074129  pop     r15
0x18007412b  pop     r14
0x18007412d  pop     r13
0x18007412f  pop     r12
0x180074131  pop     rdi
0x180074132  pop     rsi
0x180074133  pop     rbp
0x180074134  retn
```
